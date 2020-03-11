---
title: Specificare un percorso di archiviazione personalizzato per i documenti generati
description: In questo argomento viene descritto come estendere l'elenco di percorsi di archiviazione per documenti generati con i formati per la creazione di report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: 98c08ae2ab4c7cceadb6caaf98fa431e56be4b97
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042736"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a>Specificare un percorso di archiviazione personalizzato per i documenti generati

[!include[banner](../includes/banner.md)]

L'API del framework per la creazione di report elettronici (ER) consente di estendere l'elenco di percorsi di archiviazione per i documenti generati con i formati ER. In questo argomento viene fornita una panoramica delle operazioni principali da completare per aggiungere un percorso di archiviazione personalizzato.

## <a name="prerequisites"></a>Prerequisiti

È necessario distribuire una topologia che supporta la compilazione continua. Per ulteriori informazioni, vedere [Distribuire topologie che supportino compilazione continua e automazione test](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation). È necessario avere accesso a questa topologia per uno dei seguenti ruoli:

- Sviluppatore per la creazione di report elettronici
- Consulente funzionale per la creazione di report elettronici
- Amministratore di sistema

È inoltre necessario avere accesso all'ambiente di sviluppo per questa topologia.

## <a name="create-or-import-an-er-format-configuration"></a>Creare o importare una configurazione dei formati ER

Nella topologia corrente, [creare un nuovo formato ER](tasks/er-format-configuration-2016-11.md) per generare documenti per i quali si intende aggiungere un percorso di archiviazione personalizzato. In alternativa, [importare un formato ER esistente in questa topologia](general-electronic-reporting-manage-configuration-lifecycle.md).

![Pagina Progettazione formati](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> Il formato ER creato o importato deve contenere almeno uno dei seguenti elementi di formato:
>
> - File
> - Cartella
> - Merger
> - Allegato

## <a name="create-a-new-document-type"></a>Creare un nuovo tipo di documento

Per specificare il modo in cui vengono instradati i documenti generati con formati ER, è necessario configurare le [destinazioni dei report elettronici (ER)](electronic-reporting-destinations.md). In ogni destinazione ER configurata per archiviare i documenti generati come file, è necessario specificare un tipo di documento del framework di gestione di documenti. È possibile utilizzare differenti tipi di documento per instradare documenti generati da diversi formati ER.

1. Aggiungere un nuovo [tipo di documento](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management) per il formato ER creato o importato in precedenza. Nell'illustrazione seguente, il tipo di documento è **FileX**.
2. Per differenziare questo tipo di documento da altri tipi di documento, includere una parola chiave specifica nel relativo nome. Ad esempio, nell'illustrazione seguente, il nome è **(LOCAL) folder**.
3. Nel campo **Classe**, specificare **Attach file**.
4. Nel campo **Gruppo**, specificare **File**.

![Pagina Tipi di documento](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> I tipi di documento sono specifici della società. Per utilizzare un formato ER con una destinazione configurata in più società, è necessario configurare un tipo di documento distinto in ogni società.

## <a name="review-source-code"></a>Esaminare il codice sorgente

Esaminare il codice del metodo **insertFile ()** della classe **ERDocuManagement**. Si noti che l'evento **AttachingFile ()** viene generato quando il file generato viene allegato a un record.


```xpp
/// <summary>
/// Inserts file as attachment in Document Management.
/// </summary>
/// <param name = "_owner">A record as the attachment owner.</param>
/// <param name = "_stream">The file stream.</param>
/// <param name = "_filePath">The file path with name.</param>
/// <param name = "_attachmentName">The name of file attachment.</param>
/// <returns>The reference to inserted file.</returns>
[Hookable(false)]
public DocuRef insertFile(
    Common _owner, 
    System.IO.Stream _stream, 
    str _filePath, 
    str _attachmentName, 
    DocuTypeId _docuTypeId)
{
    DocuRef docuRef;
    if (_stream)
    {
        DocuType::createDefaults();
        if (!this.isDocuTypeValid(_docuTypeId))
        {
            throw error(strFmt("@ElectronicReporting:DocuTypeIsNotValid", _docuTypeId));
        }
        var args = ERDocuManagementAttachingFileEventArgs::construct(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        ERDocuManagementEvents::onAttachingFile(args);
        if (args.isHandled())
        {
            docuRef = args.getDocuRef();
        }
        else
        {
            docuRef = this.attachFile(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        }
    }
    return docuRef;
}
```

L'evento **AttachingFile ()** viene generato quando le seguenti destinazioni ER vengono elaborate:

- **Archivio** - Quando la destinazione viene utilizzata, un nuovo record per il formato ER eseguito viene creato nella tabella ERFormatMappingRunJobTable. Il campo **Archiviato** in questo record è impostato su **False**. Se il formato ER viene eseguito correttamente, il documento generato è allegato a questo record e l'evento **AttachingFile ()** viene generato. Il tipo di documento selezionato in questa destinazione ER determina il percorso di archiviazione per il file allegato (Archiviazione di Microsoft Azure o una cartella Microsoft SharePoint ).
- **Archivio processi** - Quando questa destinazione viene utilizzata, un nuovo record per il formato ER eseguito viene creato nella tabella ERFormatMappingRunJobTable. Il campo **Archiviato** in questo record è impostato su **True**. Se il formato ER viene eseguito correttamente, il documento generato è allegato a questo record e l'evento **AttachingFile ()** viene generato. Il tipo di documento configurato nei parametri ER determina il percorso di archiviazione per il file allegato (Archiviazione di Azure o una cartella di SharePoint).

![Pagina Parametri per la creazione di report elettronici](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a>Configurare una destinazione ER

1. Configurare la destinazione archiviata per uno degli elementi menzionati in precedenza (file, cartella, merger o allegato) del formato ER creato o importato. Per informazioni, vedere [Configurare destinazioni ER](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).
2. Utilizzare il tipo di documento aggiunto in precedenza per la destinazione configurata. Ad esempio in questo argomento, il tipo di documento è **FileX**.

![Finestra di dialogo Impostazioni destinazione](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a>Modificare il codice sorgente

1. Aggiungere una nuova classe al progetto di Microsoft Visual Studio e scrivere codice per la sottoscrizione all'evento **AttachingFile ()** menzionato in precedenza. Per ulteriori informazioni sul modello di estendibilità utilizzato, vedere [Rispondere con EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result). Ad esempio, nella nuova classe, scrivere codice che esegue le seguenti azioni:

    1. Archiviare file generati in una cartella del file system locale del server che esegue il servizio Server oggetti applicativi (AOS).
    2. Archiviare questi file generati solo quando il nuovo tipo di documento (ad esempio, il tipo **FileX** con la parola chiave "(LOCAL)" nel relativo nome) è utilizzato quando un file è allegato al record nel log dei processi di esecuzione ER.

    ```xpp
    class ERDocuSubscriptionSample
    {
        void new()
        {
        }
        [SubscribesTo(classStr(ERDocuManagementEvents), 
        staticDelegateStr(ERDocuManagementEvents, 
        attachingFile))]
        public static void ERDocuManagementEvents_attachingFile(ERDocuManagementAttachingFileEventArgs _args)
        {
            if (!_args.isHandled())
            {
                DocuType docuType = DocuType::find(_args.getDocuTypeId());
                if (strContains(docuType.Name, '(LOCAL)'))
                {
                    _args.markAsHandled();
                    var stream = _args.getStream();
                    if (stream.CanSeek)
                    {
                        stream.Seek(0, System.IO.SeekOrigin::Begin);
                    }
                    using (var localStream = System.IO.File::OpenWrite(@'c:\0\' + _args.getAttachmentName()))
                    {
                        stream.CopyTo(localStream);
                    }
                }
            }
        }
    }
    ```

2. Ricompilare il progetto.

## <a name="run-the-er-format-that-you-created-or-imported"></a>Eseguire il formato ER creato o importato

1. Eseguire il formato ER creato o importato.
2. Accedere a **Amministrazione organizzazione \> Creazione di report elettronici \> Processi di creazione report elettronici**. Trovare il record creato per questo processo di esecuzione e che ha generato il file ad esso allegato.
3. Esplorare la cartella **C:\\0** per trovare lo stesso file generato.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Destinazioni dei report elettronici (ER)](electronic-reporting-destinations.md)
- [Estendibilità home page](../extensibility/extensibility-home-page.md)
