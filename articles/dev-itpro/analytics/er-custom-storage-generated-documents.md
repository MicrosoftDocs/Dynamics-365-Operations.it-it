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
ms.openlocfilehash: 3ea9de81045dfd01ffec2c8a1d98ea2ba4f2c49a
ms.sourcegitcommit: 0e01d3907b70261aee2df3e3ce0dde2f1343a43a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2019
ms.locfileid: "770090"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a><span data-ttu-id="0f38a-103">Specificare un percorso di archiviazione personalizzato per i documenti generati</span><span class="sxs-lookup"><span data-stu-id="0f38a-103">Specify a custom storage location for generated documents</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0f38a-104">L'API del framework per la creazione di report elettronici (ER) consente di estendere l'elenco di percorsi di archiviazione per i documenti generati con i formati ER.</span><span class="sxs-lookup"><span data-stu-id="0f38a-104">The application programming interface (API) of the Electronic reporting (ER) framework lets you extend the list of storage locations for documents that ER formats generate.</span></span> <span data-ttu-id="0f38a-105">In questo argomento viene fornita una panoramica delle operazioni principali da completare per aggiungere un percorso di archiviazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0f38a-105">This topic includes an overview of the main tasks that you must complete to add a custom storage location.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f38a-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0f38a-106">Prerequisites</span></span>

<span data-ttu-id="0f38a-107">È necessario distribuire una topologia di Microsoft Dynamics 365 for Finance and Operations che supporta la compilazione continua.</span><span class="sxs-lookup"><span data-stu-id="0f38a-107">You must deploy a Microsoft Dynamics 365 for Finance and Operations topology that supports continuous build.</span></span> <span data-ttu-id="0f38a-108">Per ulteriori informazioni, vedere [Distribuire topologie che supportino compilazione continua e automazione test](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation). È necessario avere accesso alla topologia di Finance and Operations per uno dei seguenti ruoli:</span><span class="sxs-lookup"><span data-stu-id="0f38a-108">(For more information, see [Deploy topologies that support continuous build and test automation](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) You must have access to this Finance and Operations topology for one of the following roles:</span></span>

- <span data-ttu-id="0f38a-109">Sviluppatore per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="0f38a-109">Electronic reporting developer</span></span>
- <span data-ttu-id="0f38a-110">Consulente funzionale per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="0f38a-110">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="0f38a-111">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="0f38a-111">System administrator</span></span>

<span data-ttu-id="0f38a-112">È inoltre necessario avere accesso all'ambiente di sviluppo per questa topologia di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0f38a-112">You must also have access to the development environment for this Finance and Operations topology.</span></span>

## <a name="create-or-import-an-er-format-configuration"></a><span data-ttu-id="0f38a-113">Creare o importare una configurazione dei formati ER</span><span class="sxs-lookup"><span data-stu-id="0f38a-113">Create or import an ER format configuration</span></span>

<span data-ttu-id="0f38a-114">Nella topologia di Finance and Operations corrente, [creare un nuovo formato ER](tasks/er-format-configuration-2016-11.md) per generare documenti per i quali si intende aggiungere un percorso di archiviazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0f38a-114">In the current Finance and Operations topology, [create a new ER format](tasks/er-format-configuration-2016-11.md) to generate documents that you plan to add a custom storage location for.</span></span> <span data-ttu-id="0f38a-115">In alternativa, [importare un formato ER esistente in questa topologia](general-electronic-reporting-manage-configuration-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="0f38a-115">Alternatively, [import an existing ER format into this topology](general-electronic-reporting-manage-configuration-lifecycle.md).</span></span>

![Pagina Progettazione formati](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> <span data-ttu-id="0f38a-117">Il formato ER creato o importato deve contenere almeno uno dei seguenti elementi di formato:</span><span class="sxs-lookup"><span data-stu-id="0f38a-117">The ER format that you create or import must contain at least one of the following format elements:</span></span>
>
> - <span data-ttu-id="0f38a-118">File</span><span class="sxs-lookup"><span data-stu-id="0f38a-118">File</span></span>
> - <span data-ttu-id="0f38a-119">Cartella</span><span class="sxs-lookup"><span data-stu-id="0f38a-119">Folder</span></span>
> - <span data-ttu-id="0f38a-120">Merger</span><span class="sxs-lookup"><span data-stu-id="0f38a-120">Merger</span></span>
> - <span data-ttu-id="0f38a-121">Allegato</span><span class="sxs-lookup"><span data-stu-id="0f38a-121">Attachment</span></span>

## <a name="create-a-new-document-type"></a><span data-ttu-id="0f38a-122">Creare un nuovo tipo di documento</span><span class="sxs-lookup"><span data-stu-id="0f38a-122">Create a new document type</span></span>

<span data-ttu-id="0f38a-123">Per specificare il modo in cui vengono instradati i documenti generati con formati ER, è necessario configurare le [destinazioni ER](electronic-reporting-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0f38a-123">To specify how documents that an ER format generates are routed, you must configure [ER destinations](electronic-reporting-destinations.md).</span></span> <span data-ttu-id="0f38a-124">In ogni destinazione ER configurata per archiviare i documenti generati come file, è necessario specificare un tipo di documento del framework di gestione di documenti.</span><span class="sxs-lookup"><span data-stu-id="0f38a-124">In each ER destination that is configured to store generated documents as files, you must specify a document type of the Document management framework.</span></span> <span data-ttu-id="0f38a-125">È possibile utilizzare differenti tipi di documento per instradare documenti generati da diversi formati ER.</span><span class="sxs-lookup"><span data-stu-id="0f38a-125">Different document types can be used to route documents that different ER formats generate.</span></span>

1. <span data-ttu-id="0f38a-126">Aggiungere un nuovo [tipo di documento](../../fin-and-ops/organization-administration/configure-document-management.md) per il formato ER creato o importato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0f38a-126">Add a new [document type](../../fin-and-ops/organization-administration/configure-document-management.md) for the ER format that you created or imported earlier.</span></span> <span data-ttu-id="0f38a-127">Nell'illustrazione seguente, il tipo di documento è **FileX**.</span><span class="sxs-lookup"><span data-stu-id="0f38a-127">In the illustration that follows, the document type is **FileX**.</span></span>
2. <span data-ttu-id="0f38a-128">Per differenziare questo tipo di documento da altri tipi di documento, includere una parola chiave specifica nel relativo nome.</span><span class="sxs-lookup"><span data-stu-id="0f38a-128">To differentiate this document type from other document types, include a specific keyword in its name.</span></span> <span data-ttu-id="0f38a-129">Ad esempio, nell'illustrazione seguente, il nome è **(LOCAL) folder**.</span><span class="sxs-lookup"><span data-stu-id="0f38a-129">For example, in the illustration that follows, the name is **(LOCAL) folder**.</span></span>
3. <span data-ttu-id="0f38a-130">Nel campo **Classe**, specificare **Attach file**.</span><span class="sxs-lookup"><span data-stu-id="0f38a-130">In the **Class** field, specify **Attach file**.</span></span>
4. <span data-ttu-id="0f38a-131">Nel campo **Gruppo**, specificare **File**.</span><span class="sxs-lookup"><span data-stu-id="0f38a-131">In the **Group** field, specify **File**.</span></span>

![Pagina Tipi di documento](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> <span data-ttu-id="0f38a-133">I tipi di documento sono specifici della società.</span><span class="sxs-lookup"><span data-stu-id="0f38a-133">Document types are company-specific.</span></span> <span data-ttu-id="0f38a-134">Per utilizzare un formato ER con una destinazione configurata in più società, è necessario configurare un tipo di documento distinto in ogni società.</span><span class="sxs-lookup"><span data-stu-id="0f38a-134">To use an ER format with a configured destination in multiple companies, you must configure a separate document type in each company.</span></span>

## <a name="review-source-code"></a><span data-ttu-id="0f38a-135">Esaminare il codice sorgente</span><span class="sxs-lookup"><span data-stu-id="0f38a-135">Review source code</span></span>

<span data-ttu-id="0f38a-136">Esaminare il codice del metodo **insertFile ()** della classe **ERDocuManagement**.</span><span class="sxs-lookup"><span data-stu-id="0f38a-136">Review the code of the **insertFile()** method of the **ERDocuManagement** class.</span></span> <span data-ttu-id="0f38a-137">Si noti che l'evento **AttachingFile ()** viene generato quando il file generato viene allegato a un record.</span><span class="sxs-lookup"><span data-stu-id="0f38a-137">Notice that the **AttachingFile()** event is raised while the generated file is attached to a record.</span></span>

```
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

<span data-ttu-id="0f38a-138">L'evento **AttachingFile ()** viene generato quando le seguenti destinazioni ER vengono elaborate:</span><span class="sxs-lookup"><span data-stu-id="0f38a-138">The **AttachingFile()** event is raised when the following ER destinations are processed:</span></span>

- <span data-ttu-id="0f38a-139">**Archivio** - Quando la destinazione viene utilizzata, un nuovo record per il formato ER eseguito viene creato nella tabella ERFormatMappingRunJobTable.</span><span class="sxs-lookup"><span data-stu-id="0f38a-139">**Archive** – When this destination is used, a new record for the ER format that is run is created in the ERFormatMappingRunJobTable table.</span></span> <span data-ttu-id="0f38a-140">Il campo **Archiviato** in questo record è impostato su **False**.</span><span class="sxs-lookup"><span data-stu-id="0f38a-140">The **Archived** field in this record is set to **False**.</span></span> <span data-ttu-id="0f38a-141">Se il formato ER viene eseguito correttamente, il documento generato è allegato a questo record e l'evento **AttachingFile ()** viene generato.</span><span class="sxs-lookup"><span data-stu-id="0f38a-141">If the ER format is successfully run, the generated document is attached to this record, and the **AttachingFile()** event is raised.</span></span> <span data-ttu-id="0f38a-142">Il tipo di documento selezionato in questa destinazione ER determina il percorso di archiviazione per il file allegato (Archiviazione di Microsoft Azure o una cartella Microsoft SharePoint ).</span><span class="sxs-lookup"><span data-stu-id="0f38a-142">The document type that is selected in this ER destination determines the storage location for the attached file (Microsoft Azure Storage or a Microsoft SharePoint folder).</span></span>
- <span data-ttu-id="0f38a-143">**Archivio processi** - Quando questa destinazione viene utilizzata, un nuovo record per il formato ER eseguito viene creato nella tabella ERFormatMappingRunJobTable.</span><span class="sxs-lookup"><span data-stu-id="0f38a-143">**Job archive** – When this destination is used, a new record for the ER form that is run is created in the ERFormatMappingRunJobTable table.</span></span> <span data-ttu-id="0f38a-144">Il campo **Archiviato** in questo record è impostato su **True**.</span><span class="sxs-lookup"><span data-stu-id="0f38a-144">The **Archived** field in this record is set to **True**.</span></span> <span data-ttu-id="0f38a-145">Se il formato ER viene eseguito correttamente, il documento generato è allegato a questo record e l'evento **AttachingFile ()** viene generato.</span><span class="sxs-lookup"><span data-stu-id="0f38a-145">If the ER format is successfully run, the generated document is attached to this record, and the **AttachingFile()** event is raised.</span></span> <span data-ttu-id="0f38a-146">Il tipo di documento configurato nei parametri ER determina il percorso di archiviazione per il file allegato (Archiviazione di Azure o una cartella di SharePoint).</span><span class="sxs-lookup"><span data-stu-id="0f38a-146">The document type that is configured in the ER parameters determines the storage location for the attached file (Azure Storage or a SharePoint folder).</span></span>

![Pagina Parametri per la creazione di report elettronici](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a><span data-ttu-id="0f38a-148">Configurare una destinazione ER</span><span class="sxs-lookup"><span data-stu-id="0f38a-148">Configure an ER destination</span></span>

1. <span data-ttu-id="0f38a-149">Configurare la destinazione archiviata per uno degli elementi menzionati in precedenza (file, cartella, merger o allegato) del formato ER creato o importato.</span><span class="sxs-lookup"><span data-stu-id="0f38a-149">Configure the archived destination for one of the previously mentioned elements (file, folder, merger, or attachment) of the ER format that you created or imported.</span></span> <span data-ttu-id="0f38a-150">Per informazioni, vedere [Configurare destinazioni ER](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).</span><span class="sxs-lookup"><span data-stu-id="0f38a-150">For guidance, see [ER Configure destinations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).</span></span>
2. <span data-ttu-id="0f38a-151">Utilizzare il tipo di documento aggiunto in precedenza per la destinazione configurata.</span><span class="sxs-lookup"><span data-stu-id="0f38a-151">Use the document type that you added earlier for the configured destination.</span></span> <span data-ttu-id="0f38a-152">Ad esempio in questo argomento, il tipo di documento è **FileX**.</span><span class="sxs-lookup"><span data-stu-id="0f38a-152">(For the example in this topic, the document type is **FileX**.)</span></span>

![Finestra di dialogo Impostazioni destinazione](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a><span data-ttu-id="0f38a-154">Modificare il codice sorgente</span><span class="sxs-lookup"><span data-stu-id="0f38a-154">Modify source code</span></span>

1. <span data-ttu-id="0f38a-155">Aggiungere una nuova classe al progetto di Microsoft Visual Studio e scrivere codice per la sottoscrizione all'evento **AttachingFile ()** menzionato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0f38a-155">Add a new class to your Microsoft Visual Studio project, and write code to subscribe to the **AttachingFile()** event that was mentioned earlier.</span></span> <span data-ttu-id="0f38a-156">Per ulteriori informazioni sul modello di estendibilità utilizzato, vedere [Rispondere con EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result). Ad esempio, nella nuova classe, scrivere codice che esegue le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="0f38a-156">(For more information about the extensibility pattern that is used, see [Respond by using EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) For example, in the new class, write code that performs the following actions:</span></span>

    1. <span data-ttu-id="0f38a-157">Archiviare file generati in una cartella del file system locale del server che esegue il servizio Server oggetti applicativi (AOS).</span><span class="sxs-lookup"><span data-stu-id="0f38a-157">Store generated files in a folder of the local file system of the server that runs the Application Object Server (AOS) service.</span></span>
    2. <span data-ttu-id="0f38a-158">Archiviare questi file generati solo quando il nuovo tipo di documento (ad esempio, il tipo **FileX** con la parola chiave "(LOCAL)" nel relativo nome) è utilizzato quando un file è allegato al record nel log dei processi di esecuzione ER.</span><span class="sxs-lookup"><span data-stu-id="0f38a-158">Store these generated files only when the new document type (for example, the **FileX** type that has the "(LOCAL)" keyword in its name) is used while a file is attached to the record in the ER execution job log.</span></span>

    ```
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

2. <span data-ttu-id="0f38a-159">Ricompilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="0f38a-159">Rebuild your project.</span></span>

## <a name="run-the-er-format-that-you-created-or-imported"></a><span data-ttu-id="0f38a-160">Eseguire il formato ER creato o importato</span><span class="sxs-lookup"><span data-stu-id="0f38a-160">Run the ER format that you created or imported</span></span>

1. <span data-ttu-id="0f38a-161">Eseguire il formato ER creato o importato.</span><span class="sxs-lookup"><span data-stu-id="0f38a-161">Execute the ER format that you created or imported.</span></span>
2. <span data-ttu-id="0f38a-162">Accedere a **Amministrazione organizzazione \> Creazione di report elettronici \> Processi di creazione report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="0f38a-162">Go to **Organization administration \> Electronic reporting \> Electronic reporting jobs**.</span></span> <span data-ttu-id="0f38a-163">Trovare il record creato per questo processo di esecuzione e che ha generato il file ad esso allegato.</span><span class="sxs-lookup"><span data-stu-id="0f38a-163">Find the record that was created for this execution job, and that has the generated file attached to it.</span></span>
3. <span data-ttu-id="0f38a-164">Esplorare la cartella **C:\\0** per trovare lo stesso file generato.</span><span class="sxs-lookup"><span data-stu-id="0f38a-164">Explore the local **C:\\0** folder to find same generated file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0f38a-165">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0f38a-165">Additional resources</span></span>

- [<span data-ttu-id="0f38a-166">Destinazioni dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="0f38a-166">Electronic reporting destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="0f38a-167">Estendibilità home page</span><span class="sxs-lookup"><span data-stu-id="0f38a-167">Extensibility home page</span></span>](../extensibility/extensibility-home-page.md)
