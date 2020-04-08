---
title: Impostare i periodi di liquidazione IVA
description: In questo argomento viene illustrato come impostare periodi di liquidazione IVA in Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5972c44261a6ebd49df0fcbcef9a8c60aaa487e2
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144722"
---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="af432-103">Impostare i periodi di liquidazione IVA</span><span class="sxs-lookup"><span data-stu-id="af432-103">Set up sales tax settlement periods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="af432-104">In questo argomento viene illustrato come impostare periodi di liquidazione IVA.</span><span class="sxs-lookup"><span data-stu-id="af432-104">This topic explains how to set up sales tax settlement periods.</span></span> <span data-ttu-id="af432-105">I periodi di liquidazione IVA contengono informazioni sugli intervalli periodici in cui l'IVA deve essere dichiarata e pagata.</span><span class="sxs-lookup"><span data-stu-id="af432-105">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="af432-106">Un processo di liquidazione può essere eseguito per un periodo di liquidazione per un intervallo di date specifico.</span><span class="sxs-lookup"><span data-stu-id="af432-106">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="af432-107">Tutti i codici IVA associati al periodo di liquidazione verranno liquidati.</span><span class="sxs-lookup"><span data-stu-id="af432-107">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="af432-108">A seconda dell'impostazione dell'ufficio IVA correlato, la soggettività tributaria viene registrata in un conto fornitore o CoGe.</span><span class="sxs-lookup"><span data-stu-id="af432-108">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>

<span data-ttu-id="af432-109">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="af432-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="af432-110">Nel pannello di navigazione andare a **Moduli > Imposta > Imposte indirette > IVA > Periodi liquidazione IVA**.</span><span class="sxs-lookup"><span data-stu-id="af432-110">In the navigation pane, go to **Modules > Tax > Indirect taxes > Sales tax > Sales tax settlement periods**.</span></span>
2. <span data-ttu-id="af432-111">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="af432-111">Select **New**.</span></span>
3. <span data-ttu-id="af432-112">Nel campo **Periodo di liquidazione** digitare un calore.</span><span class="sxs-lookup"><span data-stu-id="af432-112">In the **Settlement period** field, type a value.</span></span>
4. <span data-ttu-id="af432-113">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="af432-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="af432-114">Nel campo **Ufficio** selezionare l'ufficio IVA che riceve i report e i pagamenti creati per il periodo di liquidazione.</span><span class="sxs-lookup"><span data-stu-id="af432-114">In the **Authority** field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="af432-115">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="af432-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="af432-116">Nel campo **Termini di pagamento** fare clic sul record desiderato del menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="af432-116">In the **Terms of payment** field, select the desired record in the drop-down menu.</span></span> <span data-ttu-id="af432-117">L'ufficio IVA relativo può essere impostato come fornitore e la liquidazione VAT creerà una fattura fornitore aperta.</span><span class="sxs-lookup"><span data-stu-id="af432-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="af432-118">Termini di pagamento definisce la data di scadenza della fattura fornitore aperta.</span><span class="sxs-lookup"><span data-stu-id="af432-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
8. <span data-ttu-id="af432-119">Selezionare un tipo per gli intervalli del periodo di liquidazione.</span><span class="sxs-lookup"><span data-stu-id="af432-119">Select a type for the settlement period intervals.</span></span>
9. <span data-ttu-id="af432-120">Immettere il numero di unità dell'intervallo periodico per periodo.</span><span class="sxs-lookup"><span data-stu-id="af432-120">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="af432-121">Ad esempio, un trimestre ha 3 mesi.</span><span class="sxs-lookup"><span data-stu-id="af432-121">For example, a quarter has 3 months.</span></span>
10. <span data-ttu-id="af432-122">Selezionare o deselezionare la casella di controllo **Utilizza elaborazione batch per liquidazione IVA**.</span><span class="sxs-lookup"><span data-stu-id="af432-122">Select or clear the **Use batch processing for sales tax settlement** check box.</span></span> <span data-ttu-id="af432-123">Il processo di liquidazione per il periodo di liquidazione può essere elaborato come processo batch in background.</span><span class="sxs-lookup"><span data-stu-id="af432-123">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="af432-124">Si consigliano tantissime transazioni IVA all'interno di un intervallo periodico.</span><span class="sxs-lookup"><span data-stu-id="af432-124">This is recommended for a large number of tax transactions within a period interval.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="af432-125">Attualmente questo non è supportato in Spagna, in Giappone e nei Paesi Bassi.</span><span class="sxs-lookup"><span data-stu-id="af432-125">Currently this is not supported in Spain, Japan, and the Netherlands.</span></span>
11. <span data-ttu-id="af432-126">Selezionare o deselezionare la casella di controllo **Impedisci generazione transazioni contropartita fiscale**.</span><span class="sxs-lookup"><span data-stu-id="af432-126">Select or clear the **Prevent generating offset tax transactions** check box.</span></span> <span data-ttu-id="af432-127">Per impostazione predefinita, il sistema genera transazioni di contropartita fiscale durante il processo di liquidazione, la cui causa può creare problemi in caso di un numero elevato di transazioni fiscali in un determinato intervallo periodico.</span><span class="sxs-lookup"><span data-stu-id="af432-127">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="af432-128">Selezionare questa casella di controllo per impedire la generazione di transazioni di contropartita fiscale.</span><span class="sxs-lookup"><span data-stu-id="af432-128">Select this check box to prevent generating offset tax transactions.</span></span>
12. <span data-ttu-id="af432-129">Espandere la scheda **Intervalli periodici**.</span><span class="sxs-lookup"><span data-stu-id="af432-129">Expand the **Period intervals** tab.</span></span>
13. <span data-ttu-id="af432-130">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="af432-130">Select **Add**.</span></span>
14. <span data-ttu-id="af432-131">Immettere una data nella nuova riga del campo **Dal**.</span><span class="sxs-lookup"><span data-stu-id="af432-131">In the **From date** field in the new row, enter a date.</span></span>
15. <span data-ttu-id="af432-132">Nel campo **Al** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="af432-132">In the **To date** field, enter a date.</span></span>
16. <span data-ttu-id="af432-133">Selezionare **Nuovo intervallo periodico**.</span><span class="sxs-lookup"><span data-stu-id="af432-133">Select **New period interval**.</span></span> <span data-ttu-id="af432-134">Una volta che il primo intervallo periodico è stato immesso, i nuovi periodi possono essere creati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="af432-134">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="af432-135">È possibile tornare e aggiungere nuovi intervalli periodici in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="af432-135">You can come back and add new period intervals as required.</span></span>  
17. <span data-ttu-id="af432-136">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="af432-136">Close the page.</span></span>

