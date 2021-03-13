---
title: Tipo di destinazione stampante ER
description: Questo argomento spiega come configurare una destinazione stampante per ogni componente FOLDER o FILE di un formato di creazione di report elettronici (ER).
author: NickSelin
manager: AnnBe
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: c6e298f62ec69f349eb713d66313e535c7e01881
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094081"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a><span data-ttu-id="1e462-103">Destinazione stampante</span><span class="sxs-lookup"><span data-stu-id="1e462-103">Printer destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1e462-104">È possibile inviare un documento generato direttamente a una stampante di rete per la stampa diretta.</span><span class="sxs-lookup"><span data-stu-id="1e462-104">You can send a generated document directly to a network printer for direct printing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1e462-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1e462-105">Prerequisites</span></span>

<span data-ttu-id="1e462-106">Prima di iniziare, è necessario installare e configurare l'agente di distribuzione documenti e quindi registrare le stampanti di rete.</span><span class="sxs-lookup"><span data-stu-id="1e462-106">Before you begin, you must install and configure the Document Routing Agent, and then register the network printers.</span></span> <span data-ttu-id="1e462-107">Per ulteriori informazioni, vedere [Installare l'agente di distribuzione documenti per abilitare la stampa di rete](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span><span class="sxs-lookup"><span data-stu-id="1e462-107">For more information, see [Install the Document Routing Agent to enable network printing](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span></span>

## <a name="make-the-printer-destination-available"></a><span data-ttu-id="1e462-108">Rendere disponibile la destinazione Stampante</span><span class="sxs-lookup"><span data-stu-id="1e462-108">Make the Printer destination available</span></span>

<span data-ttu-id="1e462-109">Per rendere disponibile la destinazione **Stampante** nell'istanza corrente di Microsoft Dynamics 365 Finance, accedere all'area di lavoro **Gestione funzionalità** e attivare le seguenti funzionalità, in questo ordine:</span><span class="sxs-lookup"><span data-stu-id="1e462-109">To make the **Printer** destination available in the current instance of Microsoft Dynamics 365 Finance, go to the **Feature management** workspace, and turn on the following features, in this order:</span></span>

1. <span data-ttu-id="1e462-110">Convertire i documenti in uscita per la creazione di report elettronici dai formati di Microsoft Office in PDF</span><span class="sxs-lookup"><span data-stu-id="1e462-110">Convert Electronic Reporting outbound documents from Microsoft Office formats to PDF</span></span>
2. <span data-ttu-id="1e462-111">Agente di distribuzione dei documenti come destinazione della creazione di report elettronici per i documenti in uscita</span><span class="sxs-lookup"><span data-stu-id="1e462-111">Document Routing Agent as Electronic Reporting destination for outbound documents</span></span>

<span data-ttu-id="1e462-112">[![Attivazione della funzionalità Destinazione stampante ER in Gestione funzionalità](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span><span class="sxs-lookup"><span data-stu-id="1e462-112">[![Turning on the ER printer destination feature in Feature management](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span></span>

### <a name="applicability"></a><span data-ttu-id="1e462-113">Applicabilità</span><span class="sxs-lookup"><span data-stu-id="1e462-113">Applicability</span></span>

<span data-ttu-id="1e462-114">La destinazione **Stampante** può essere configurata solo per i componenti di file utilizzati per generare output in formato PDF stampabile (PDF Merger o elementi di formato di file PDF) oppure in formato Microsoft Office Excel/Word (file Excel).</span><span class="sxs-lookup"><span data-stu-id="1e462-114">The **Printer** destination can be configured only for file components that are used to generate output in either printable PDF format (PDF Merger or PDF file format elements) or Microsoft Office Excel/Word format (Excel file).</span></span> <span data-ttu-id="1e462-115">Quando l'output viene generato in formato PDF, viene inviato a una stampante.</span><span class="sxs-lookup"><span data-stu-id="1e462-115">When output is generated in PDF format, it's sent to a printer.</span></span> <span data-ttu-id="1e462-116">Quando l'output viene generato in un formato Microsoft Office, viene automaticamente convertito in formato PDF e quindi inviato a una stampante.</span><span class="sxs-lookup"><span data-stu-id="1e462-116">When output is generated in Microsoft Office format, it's automatically converted to PDF format and then sent to a printer.</span></span>

### <a name="limitations"></a><span data-ttu-id="1e462-117">Limiti</span><span class="sxs-lookup"><span data-stu-id="1e462-117">Limitations</span></span>

<span data-ttu-id="1e462-118">Questa funzionalità è una funzionalità di anteprima ed è soggetta alle condizioni d'uso descritte in [Condizioni d'uso supplementari per le anteprime di Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2105274).</span><span class="sxs-lookup"><span data-stu-id="1e462-118">This feature is a preview feature and is subject to the terms of use that are described in [Supplemental Terms of Use for Microsoft Dynamics 365 Previews](https://go.microsoft.com/fwlink/?linkid=2105274).</span></span>

<span data-ttu-id="1e462-119">La destinazione **Stampante** è implementata solo per le distribuzioni cloud.</span><span class="sxs-lookup"><span data-stu-id="1e462-119">The **Printer** destination is implemented only for cloud deployments.</span></span>

### <a name="use-the-printer-destination"></a><span data-ttu-id="1e462-120">Utilizzare la destinazione Stampante</span><span class="sxs-lookup"><span data-stu-id="1e462-120">Use the Printer destination</span></span>

1. <span data-ttu-id="1e462-121">Impostare l'opzione **Abilitato** su **Sì** per inviare un documento generato a una stampante.</span><span class="sxs-lookup"><span data-stu-id="1e462-121">Set the **Enabled** option to **Yes** to send a generated document to a printer.</span></span>
2. <span data-ttu-id="1e462-122">Nel campo **Nome stampante**, selezionare la stampante di rete necessaria.</span><span class="sxs-lookup"><span data-stu-id="1e462-122">In the **Printer name** field, select the required network printer.</span></span>
3. <span data-ttu-id="1e462-123">Impostare l'opzione **Salvare nell'archivio di stampa?** su **Sì** per archiviare l'output generato nell'archivio di stampa, di modo che sia disponibile per ulteriori stampe.</span><span class="sxs-lookup"><span data-stu-id="1e462-123">Set the **Save in print archive?** option to **Yes** to store the generated output in the print archive, so that it's available for further printing.</span></span> <span data-ttu-id="1e462-124">Per accedere all'output archiviato in un secondo momento, selezionare **Amministrazione organizzazione** \> **Richieste di informazioni e report** \> **Report archivio**.</span><span class="sxs-lookup"><span data-stu-id="1e462-124">To access archived output later, go to **Organization administration** \> **Inquiries and reports** \> **Report archive**.</span></span>

<span data-ttu-id="1e462-125">[![Utilizzare la destinazione Stampante](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span><span class="sxs-lookup"><span data-stu-id="1e462-125">[![Using the Printer destination](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span></span>

> [!NOTE]
> <span data-ttu-id="1e462-126">L'opzione **Converti in PDF** non deve essere attivata quando si configura la destinazione **Stampante**.</span><span class="sxs-lookup"><span data-stu-id="1e462-126">The **Convert to PDF** option doesn't have to be turned on when you configure the **Printer** destination.</span></span> <span data-ttu-id="1e462-127">La conversione in PDF per scopi di stampa avverrà anche se l'opzione è disattivata.</span><span class="sxs-lookup"><span data-stu-id="1e462-127">The PDF conversion for printing purposes will occur even if the option is turned off.</span></span>

<span data-ttu-id="1e462-128">Per usare uno specifico [orientamento di pagina](electronic-reporting-destinations.md#SelectPdfPageOrientation) quando si stampa un documento in uscita in formato Excel, è necessario attivare l'opzione **Converti in PDF**.</span><span class="sxs-lookup"><span data-stu-id="1e462-128">To use a specific [page orientation](electronic-reporting-destinations.md#SelectPdfPageOrientation) when you print an outbound document in Excel format, you must turn on the **Convert to PDF** option.</span></span> <span data-ttu-id="1e462-129">Quando si imposta l'opzione **Converti in PDF** su **Sì**, il campo **Orientamento pagina** diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="1e462-129">When you set the **Convert to PDF** option to **Yes**, the **Page orientation** field becomes available.</span></span> <span data-ttu-id="1e462-130">Nel campo **Orientamento pagina** è possibile selezionare un orientamento di pagina.</span><span class="sxs-lookup"><span data-stu-id="1e462-130">In the **Page orientation** field, you can select a page orientation.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1e462-131">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1e462-131">Additional resources</span></span>

- [<span data-ttu-id="1e462-132">Panoramica dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="1e462-132">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="1e462-133">Destinazioni dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="1e462-133">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
