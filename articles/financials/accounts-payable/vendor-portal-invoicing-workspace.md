---
title: Area di lavoro fatturazione di collaborazione fornitore
description: "In questo argomento viene descritto come è possibile visualizzare le fatture fornitore e inviare le fatture dall'area di lavoro Fatturazione di collaborazione fornitore."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221534
ms.assetid: c4ed62f3-d351-41d7-a2ad-790576cde4ab
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 6b05dbef279b06fefc1eccd87689693edf2a418e
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="vendor-collaboration-invoicing-workspace"></a><span data-ttu-id="26136-103">Area di lavoro fatturazione di collaborazione fornitore</span><span class="sxs-lookup"><span data-stu-id="26136-103">Vendor collaboration invoicing workspace</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="26136-104">In questo argomento viene descritto come è possibile visualizzare le fatture fornitore e inviare le fatture dall'area di lavoro Fatturazione di collaborazione fornitore.</span><span class="sxs-lookup"><span data-stu-id="26136-104">This topic explains how you can view vendor invoices and submit invoices from the vendor collaboration invoicing workspace.</span></span>

<span data-ttu-id="26136-105">L'area di lavoro **Fatturazione di collaborazione fornitore** può essere utilizzata per visualizzare informazioni sulle fatture fornitore e inviare fatture a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition usando le funzionalità del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="26136-105">The **Vendor collaboration invoicing** workspace can be used to view vendor invoice information and to submit invoices to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition using workflow capabilities.</span></span>


<a name="vendor-collaboration-invoicing-workspace"></a><span data-ttu-id="26136-106">Area di lavoro fatturazione di collaborazione fornitore</span><span class="sxs-lookup"><span data-stu-id="26136-106">Vendor collaboration invoicing workspace</span></span>
----------------------------------------

### <a name="summary-tiles"></a><span data-ttu-id="26136-107">Sezioni Riepilogo</span><span class="sxs-lookup"><span data-stu-id="26136-107">Summary tiles</span></span>

<span data-ttu-id="26136-108">I riquadri **Riepilogo** offrono una panoramica delle fatture per il fornitore selezionato.</span><span class="sxs-lookup"><span data-stu-id="26136-108">The **Summary** tiles give an overview of the invoices for the selected vendor.</span></span> <span data-ttu-id="26136-109">È possibile visualizzare le fatture in base allo stato.</span><span class="sxs-lookup"><span data-stu-id="26136-109">You can view invoices by their state.</span></span>
-   <span data-ttu-id="26136-110">Le fatture bozza non sono state inviate al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="26136-110">Draft invoices have not been submitted to workflow.</span></span>
-   <span data-ttu-id="26136-111">Le fatture inviate e non approvate sono quelle che il fornitore ha inviato, ma che non sono state registrate in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="26136-111">Submitted, not approved invoices are those invoices that the vendor has submitted, but they have not been posted in Finance and Operations.</span></span>
-   <span data-ttu-id="26136-112">Le fatture approvate e non pagate sono quelle registrate in Finance and Operations, ma non ancora interamente pagate.</span><span class="sxs-lookup"><span data-stu-id="26136-112">Approved, not paid invoices are those that have been posted in Finance and Operations, but they have not yet been fully paid.</span></span>
-   <span data-ttu-id="26136-113">Le fatture pagate sono quelle che sono state interamente pagate in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="26136-113">Paid invoices are those that have been fully paid in Finance and Operations.</span></span>

<span data-ttu-id="26136-114">Fare clic su un riquadro per aprire una visualizzazione filtrata della pagina **Elenco fatture**.</span><span class="sxs-lookup"><span data-stu-id="26136-114">Clicking on a tile will open a filtered view of the **Invoices list** page.</span></span>
### <a name="tabular-lists"></a><span data-ttu-id="26136-115">Elenchi tabulari</span><span class="sxs-lookup"><span data-stu-id="26136-115">Tabular lists</span></span>

<span data-ttu-id="26136-116">Nella sezione **Elenchi tabulari** lo stato di fatturazione è suddiviso in simili modi ai riquadri riepilogo: Elenchi bozza e inviati, non approvati.</span><span class="sxs-lookup"><span data-stu-id="26136-116">In the **Tabular lists** section, the status of the invoicing is broken down in similar ways as the summary tiles: Draft and Submitted, not approved lists.</span></span> <span data-ttu-id="26136-117">Quando in stato di bozza, una fattura può essere inviata al flusso di lavoro o essere eliminata.</span><span class="sxs-lookup"><span data-stu-id="26136-117">While in the Draft state, an invoice can be submitted to workflow or deleted.</span></span> <span data-ttu-id="26136-118">L'ultimo elenco tabulare è un'opzione per trovare le fatture.</span><span class="sxs-lookup"><span data-stu-id="26136-118">The last tabular list is an option to find invoices.</span></span> <span data-ttu-id="26136-119">È possibile filtrare mentre si cerca, per consentire ricerche più rapide.</span><span class="sxs-lookup"><span data-stu-id="26136-119">You can filter as you search, to allow for faster searches.</span></span>
<span data-ttu-id="26136-120">Pagina elenco Tutte le fatture fornitore</span><span class="sxs-lookup"><span data-stu-id="26136-120">All vendor invoices list page</span></span>
-----------------------------

<span data-ttu-id="26136-121">È possibile visualizzare tutte le fatture fornitore registrate e non registrate nella pagina elenco **Fatture di collaborazione fornitore**.</span><span class="sxs-lookup"><span data-stu-id="26136-121">You can view all posted and unposted vendor invoices on the **Vendor collaboration invoices** list page.</span></span> <span data-ttu-id="26136-122">È possibile utilizzare questa pagina elenco per visualizzare lo stato di pagamento delle fatture.</span><span class="sxs-lookup"><span data-stu-id="26136-122">You can use this list page to view the payment status of the invoices.</span></span> <span data-ttu-id="26136-123">Gli stati di pagamento sono Non registrato, Non pagato, Pagato parzialmente e Interamente pagato.</span><span class="sxs-lookup"><span data-stu-id="26136-123">The payment statuses include Unposted, Unpaid, Partially paid, and Fully paid.</span></span>
<span data-ttu-id="26136-124">Creare una nuova fattura da un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="26136-124">Creating a new invoice from a purchase order</span></span>
--------------------------------------------

<span data-ttu-id="26136-125">È possibile creare una nuova fattura fornitore selezionando l'azione **Nuovo** nell'area di lavoro **Fatturazione di collaborazione fornitore**.</span><span class="sxs-lookup"><span data-stu-id="26136-125">You can create a new vendor invoice by selecting the **New** action on the **Vendor collaboration invoicing** workspace.</span></span> <span data-ttu-id="26136-126">Il numero dell'ordine fornitore e il numero di fattura devono essere forniti dal fornitore.</span><span class="sxs-lookup"><span data-stu-id="26136-126">The purchase order number and invoice number must be provided by the vendor.</span></span> <span data-ttu-id="26136-127">Per impostazione predefinita, tutte righe dell'ordine fornitore verranno visualizzate nella nuova fattura.</span><span class="sxs-lookup"><span data-stu-id="26136-127">By default, all of the lines from the vendor's purchase order will appear on the new invoice.</span></span> <span data-ttu-id="26136-128">La informazioni su quantità e costi possono essere modificate prima di inviare la fattura fornitore al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="26136-128">The quantity and cost information can be edited prior to submitting the vendor invoice to workflow.</span></span> <span data-ttu-id="26136-129">È possibile allegare file, note, immagini e URL a una fattura prima di inviarla.</span><span class="sxs-lookup"><span data-stu-id="26136-129">You can attach files, notes, images, and URLs to an invoice before submitting it.</span></span>



<span data-ttu-id="26136-130">Per ulteriori informazioni, vedere  [Collaborazione con i fornitori tramite il portale fornitori](../../supply-chain/procurement/collaborate-vendors-vendor-portal.md)</span><span class="sxs-lookup"><span data-stu-id="26136-130">For more information, see [Collaborating with vendors by using the Vendor portal](../../supply-chain/procurement/collaborate-vendors-vendor-portal.md)</span></span>




