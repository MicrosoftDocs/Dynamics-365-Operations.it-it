---
title: Tipo di destinazione stampante ER
description: In questo argomento viene descritto come configurare una destinazione stampante per ogni componente CARTELLA o FILE di un formato ER configurato per generare documenti in uscita nei formati PDF o di Microsoft Office (Excel/Word).
author: NickSelin
manager: AnnBe
ms.date: 01/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 58e067baa130458e3a8e788d978604f208140a03
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019847"
---
# <a name="PrinterDestinationType"></a>Destinazione stampante

[!include [banner](../includes/banner.md)]

È possibile inviare un documento generato direttamente a una stampante di rete per la stampa diretta.

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, è necessario installare e configurare l'agente di distribuzione documenti e quindi registrare le stampanti di rete. Per ulteriori informazioni, vedere [Installare l'agente di distribuzione documenti per abilitare la stampa di rete](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).

## <a name="make-the-printer-destination-available"></a>Rendere disponibile la destinazione Stampante

Per rendere disponibile la destinazione **Stampante** nell'istanza corrente di Microsoft Dynamics 365 Finance, accedere all'area di lavoro **Gestione funzionalità** e attivare le seguenti funzionalità, in questo ordine:

1. Convertire i documenti in uscita per la creazione di report elettronici dai formati di Microsoft Office in PDF
2. Agente di distribuzione dei documenti come destinazione della creazione di report elettronici per i documenti in uscita

[![Attivazione della funzionalità Destinazione stampante ER in Gestione funzionalità](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>Applicabilità

La destinazione **Stampante** può essere configurata solo per i componenti di file utilizzati per generare output in formato PDF stampabile (PDF Merger o elementi di formato di file PDF) oppure in formato Microsoft Office Excel/Word (file Excel). Quando l'output viene generato in formato PDF, viene inviato a una stampante. Quando l'output viene generato in un formato Microsoft Office, viene automaticamente convertito in formato PDF e quindi inviato a una stampante.

### <a name="limitations"></a>Limiti

Questa funzionalità è una funzionalità di anteprima ed è soggetta alle condizioni d'uso descritte in [Condizioni d'uso supplementari per le anteprime di Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2105274).

La destinazione **Stampante** è implementata solo per le distribuzioni cloud.

### <a name="use-the-printer-destination"></a>Utilizzare la destinazione Stampante

1. Impostare l'opzione **Abilitato** su **Sì** per inviare un documento generato a una stampante.
2. Nel campo **Nome stampante**, selezionare la stampante di rete necessaria.
3. Impostare l'opzione **Salvare nell'archivio di stampa?** su **Sì** per archiviare l'output generato nell'archivio di stampa, di modo che sia disponibile per ulteriori stampe. Per accedere all'output archiviato in un secondo momento, selezionare **Amministrazione organizzazione** \> **Richieste di informazioni e report** \> **Report archivio**.

[![Utilizzare la destinazione Stampante](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> L'opzione **Converti in PDF** non deve essere attivata quando si configura la destinazione **Stampante**. La conversione in PDF per scopi di stampa avverrà anche se l'opzione è disattivata.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica dei report elettronici](general-electronic-reporting.md)
- [Destinazioni dei report elettronici](electronic-reporting-destinations.md)
