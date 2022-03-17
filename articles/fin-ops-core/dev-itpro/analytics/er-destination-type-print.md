---
title: Tipo di destinazione stampante ER
description: Questo argomento spiega come configurare una destinazione stampante per ogni componente FOLDER o FILE di un formato di creazione di report elettronici (ER).
author: NickSelin
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2513fc4f86519c71602089cd46e9757813b1a708
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388290"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>Destinazione stampante

[!include [banner](../includes/banner.md)]

È possibile inviare un documento generato direttamente a una stampante di rete per la stampa diretta.

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, è necessario installare e configurare l'agente di distribuzione documenti e quindi registrare le stampanti di rete. Per ulteriori informazioni, vedere [Installare l'agente di distribuzione documenti per abilitare la stampa di rete](./install-document-routing-agent.md).

## <a name="make-the-printer-destination-available"></a>Rendere disponibile la destinazione Stampante

Per rendere disponibile la destinazione **Stampante** nell'istanza corrente di Microsoft Dynamics 365 Finance, accedere all'area di lavoro **Gestione funzionalità** e attivare le seguenti funzionalità, in questo ordine:

1. Convertire i documenti in uscita per la creazione di report elettronici dai formati di Microsoft Office in PDF
2. Agente di distribuzione dei documenti come destinazione della creazione di report elettronici per i documenti in uscita

[![Attivazione della funzionalità Destinazione stampante ER in Gestione funzionalità.](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>Applicabilità

#### <a name="pdf-printing"></a>Stampa PDF

Nelle versioni di Finance prima della versione 10.0.18, la destinazione **Stampante** può essere configurata solo per i componenti di file utilizzati per generare output in formato PDF stampabile (**PDF Merger** o elementi di formato di **file PDF**) oppure in formato Microsoft Office Excel/Word (**file Excel**). Quando l'output viene generato in formato PDF, viene inviato a una stampante. Quando l'output viene generato in un formato Office utilizzando l'elemento di formato **file Excel**, viene automaticamente convertito in formato PDF e quindi inviato a una stampante.

Tuttavia, a partire dalla versione 10.0.18, è possibile configurare la destinazione **Stampante** per l'elemento di formato **File comune**. Questo elemento di formato viene utilizzato principalmente per generare output in formato TXT o XML. È possibile configurare un formato ER che contiene l'elemento di formato **File comune** come l'elemento di formato radice e l'elemento di formato **Contenuto binario** come l'unico elemento nidificato sotto di esso. In questo caso, l'elemento di formato **File comune** produrrà l'output nel formato specificato dall'associazione configurata per l'elemento di formato **Contenuto binario**. Ad esempio, puoi configurare questo binding su [compilare](tasks/er-document-management-files-5.md#modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format) questo elemento con il contenuto di un allegato [Gestione documenti](../../fin-ops/organization-administration/configure-document-management.md) in formato PDF o Office (Excel o Word). È possibile stampare l'output utilizzando la destinazione **Stampante** configurata. 

> [!NOTE]
> Quando selezioni l'elemento di formato **Comune\\File** per configurare la destinazione **Stampante**, non c'è modo di garantire, in fase di progettazione, che l'elemento selezionato produca output in formato PDF o output che può essere convertito in formato PDF. Pertanto, viene visualizzato il seguente messaggio di avviso: "Assicurarsi che l'output generato dal componente di formato selezionato possa essere convertito in PDF. In caso contrario, deseleziona l'opzione "Converti in PDF". È necessario adottare misure per evitare problemi di runtime quando viene fornito output non PDF o convertibile in PDF per la stampa in runtime. Se si prevede di ricevere l'output in formato Office (Excel o Word), l'opzione **Converti in PDF** deve essere selezionata.
>
> Nella versione 10.0.26 e successive, per utilizzare l'opzione **Converti in PDF**, è necessario selezionare **PDF** per il parametro **Tipo di distribuzione documento** della destinazione **Stampante** configurata.

#### <a name="zpl-printing"></a>Stampa ZPL

Nella versione 10.0.26 e successive, puoi configurare la destinazione **Stampante** per l'elemento di formato **Comune\\File** selezionando **ZPL** per il parametro **Tipo di distribuzione documento**. In questo caso, l'opzione **Converti in PDF** viene ignorata in fase di esecuzione e l'output TXT o XML viene inviato direttamente a una stampante selezionata utilizzando il contratto Zebra Programming Language (ZPL) dell'[agente di distribuzione documenti (DRA)](install-document-routing-agent.md). Utilizza questa funzionalità per un formato ER che rappresenta un layout di etichetta ZPL II per stampare varie etichette.

[![Impostazione del parametro Tipo di distribuzione documenti nella finestra di dialogo Impostazioni destinazione.](./media/ER_Destinations-SetDocumentRoutingType.png)](./media/ER_Destinations-SetDocumentRoutingType.png)

Per ulteriori informazioni su questa funzionalità, vedi [Progettare una nuova soluzione ER per stampare etichette ZPL](er-design-zpl-labels.md).

### <a name="limitations"></a>Limiti

La destinazione **Stampante** è implementata solo per le distribuzioni cloud.

### <a name="use-the-printer-destination"></a>Utilizzare la destinazione Stampante

1. Impostare l'opzione **Abilitato** su **Sì** per inviare un documento generato a una stampante.
2. Nel campo **Nome stampante**, selezionare la stampante di rete necessaria.
3. Impostare l'opzione **Salvare nell'archivio di stampa?** su **Sì** per archiviare l'output generato nell'archivio di stampa, di modo che sia disponibile per ulteriori stampe. Per accedere all'output archiviato in un secondo momento, selezionare **Amministrazione organizzazione** \> **Richieste di informazioni e report** \> **Report archivio**.

[![Utilizzo della destinazione Stampante.](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> L'opzione **Converti in PDF** non deve essere attivata quando si configura la destinazione **Stampante**. La conversione in PDF per scopi di stampa avverrà anche se l'opzione è disattivata.

Per usare uno specifico [orientamento di pagina](electronic-reporting-destinations.md#SelectPdfPageOrientation) quando si stampa un documento in uscita in formato Excel, è necessario attivare l'opzione **Converti in PDF**. Quando si imposta l'opzione **Converti in PDF** su **Sì**, il campo **Orientamento pagina** diventa disponibile. Nel campo **Orientamento pagina** è possibile selezionare un orientamento di pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica dei report elettronici](general-electronic-reporting.md)
- [Destinazioni dei report elettronici](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
