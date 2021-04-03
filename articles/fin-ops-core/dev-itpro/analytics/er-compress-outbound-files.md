---
title: Comprimere documenti di grandi dimensioni generati nei rapporti elettronici
description: In questo argomento viene illustrato come comprimere documenti di grandi dimensioni generati da un formato di report elettronico (ER).
author: NickSelin
manager: kfend
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERFormatDestinationTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 8a8f55b33624b057a6abf9af5084209ac6a0c778
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562336"
---
# <a name="compress-large-documents-that-are-generated-in-electronic-reporting"></a>Comprimere documenti di grandi dimensioni generati nei rapporti elettronici 

[!include [banner](../includes/banner.md)]

Puoi usare il [framework dei reporting elettronici (ER) ](general-electronic-reporting.md) per configurare una soluzione che recupera i dati transazionali per generare un documento in uscita. Questo documento generato potrebbe essere abbastanza grande. Quando viene generato questo tipo di documento, viene utilizzata la memoria [Application Object Server (AOS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-tools/access-instances#location-of-packages-source-code-and-other-aos-configurations) per contenerlo. Ad un certo punto, il documento deve essere scaricato dalla tua applicazione Microsoft Dynamics 365 Finance. Attualmente, la dimensione massima di un singolo documento generato in ER è limitata a 2 gigabyte (GB). Inoltre, Finance attualmente [limita](https://fix.lcs.dynamics.com/Issue/Details?kb=4569432&bugId=453907&dbType=3) la dimensione di un file scaricato a 1 GB. Pertanto, è necessario configurare una soluzione ER che riduca la probabilità che queste limitazioni vengano superate e che si riceva un'eccezione di tipo **Flusso troppo lungo** o **Overflow o underflow durante un'operazione aritmetica**.

Quando si configura una soluzione, è possibile modificare il formato ER nella finestra di progettazione operazioni aggiungendo un elemento radice del tipo **Cartella** per comprimere il contenuto generato da uno qualsiasi dei suoi elementi nidificati. La compressione funziona "just in time", in modo da ridurre l'utilizzo massimo della memoria e la dimensione del file che verrà scaricato.

> [!NOTE]
> La compressione dei file richiede un'ulteriore percentuale di utilizzo della CPU.

Per ulteriori informazioni su questo approccio, completa gli esempi in questo argomento.

## <a name="example-compress-an-outbound-document"></a>Esempio: comprimere un documento in uscita

Questo esempio mostra come un utente con il ruolo **Amministratore di sistema** o **Consulente funzionale per la reportistica elettronica** assegnato può configurare un formato ER per comprimere un documento generato.

### <a name="prerequisites"></a>Prerequisiti

Prima di completare le procedure in questo argomento, è necessario completare i seguenti passaggi:

1. [Attivare un provider di configurazioni](er-defer-xml-element.md#activate-a-configuration-provider).
2. [Importare le configurazioni ER di esempio](er-defer-xml-element.md#import-the-sample-er-configurations).
3. [Esaminare il formato importato](er-defer-xml-element.md#review-the-imported-format).

> [!NOTE]
> Attualmente, la struttura del formato inizia dall'elemento **Report** del tipo **File** e contiene elementi XML. Pertanto, verrà generato un documento in uscita in formato XML e non verrà utilizzata alcuna compressione.

### <a name="generate-an-er-format-to-get-an-uncompressed-document"></a>Generare un formato ER per ottenere un documento non compresso

1. [Eseguire il formato importato](er-defer-xml-element.md#run-the-imported-format).
2. Si noti che la dimensione del documento generato in formato XML è di 3 kilobyte (KB).

    ![Anteprima del documento in uscita non compresso](./media/er-compress-outbound-files1.png)

### <a name="modify-the-format-to-compress-the-generated-output"></a>Modificare il formato per comprimere l'output generato

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni, espandere **Modello di apprendimento di elementi differiti**.
3. Seleziona la configurazione **Formato per ottenere i elementi XML differiti**.
4. Seleziona **Progettazione** per modificare la struttura del formato.
5. Nella pagina **Progettazione formati**, nella scheda **Formato** seleziona **Aggiungi radice** per aggiungere un elemento del formato radice.
6. Nella finestra di dialogo **Aggiungi**, seleziona **Comune\\Cartella**.
7. Seleziona **OK** per confermare l'aggiunta del nuovo elemento radice.
8. Selezionare **Salva**.

> [!NOTE]
> La struttura del formato parte dall'elemento del tipo **Cartella**. Questo elemento genererà l'output come file compresso (zip). Quando un documento generato dall'elemento **Report** viene inserito in un file zip in uscita, il suo contenuto verrà compresso per ridurre le dimensioni del file in uscita.

### <a name="generate-an-er-format-to-get-a-compressed-document"></a>Generare un formato ER per ottenere un documento compresso

1. Nella pagina **Progettazione formati**, selezionare **Esegui**.
2. Scarica il file zip proposto dal browser Web e aprilo per esaminarlo.
3. Si noti che la dimensione del documento generato in formato ZIP è di 1 KB.

    > [!NOTE] 
    > Il rapporto di compressione del file XML contenuto in questo file zip è dell'87%. Il rapporto di compressione dipende dai dati che vengono compressi.

    ![Anteprima del documento in uscita compresso](./media/er-compress-outbound-files2.png)

> [!NOTE]
> Se la [destinazione](electronic-reporting-destinations.md) ER è configurata per l'elemento di formato che genera l'output (l'elemento **Report** in questo esempio), la compressione dell'output verrà ignorata.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dei report elettronici](general-electronic-reporting.md)

[Destinazioni dei report elettronici](electronic-reporting-destinations.md)

[Differire l'esecuzione di elementi XML in formati ER](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]