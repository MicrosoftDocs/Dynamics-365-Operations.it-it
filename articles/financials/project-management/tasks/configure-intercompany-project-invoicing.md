---
title: Configurare la fatturazione del progetto interaziendale
description: In questo argomento viene illustrato come impostare la fatturazione del progetto tra due società dell'organizzazione.
author: KimANelson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, InterCompanyTradingRelationSetupVendor, SysDataAreaSelectLookup, ProjParameters, ProjPosting, ProjTransferPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c89b17c09a4f145b5a4ca9cdd127b4e635447d4b
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867321"
---
# <a name="configure-intercompany-project-invoicing"></a><span data-ttu-id="a67cd-103">Configurare la fatturazione del progetto interaziendale</span><span class="sxs-lookup"><span data-stu-id="a67cd-103">Configure intercompany project invoicing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a67cd-104">In questo argomento viene illustrato come impostare la fatturazione del progetto tra due società dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a67cd-104">This topic shows how to set up project invoicing between two companies in your organization.</span></span> <span data-ttu-id="a67cd-105">Questa attività utilizza il set di dati dimostrativi USSI.</span><span class="sxs-lookup"><span data-stu-id="a67cd-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="a67cd-106">Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Fornitori > Tutti i fornitori**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-106">In the navigation pane, go to **Modules > Accounts payable > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="a67cd-107">Trovare e selezionare il record desiderato nell'elenco **Tutti i fornitori**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-107">In the **All vendors** list, find and select the desired record.</span></span>
3. <span data-ttu-id="a67cd-108">Nel riquadro azioni fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-108">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="a67cd-109">Selezionare **Interaziendale**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-109">Select **Intercompany**.</span></span>
5. <span data-ttu-id="a67cd-110">Impostare **Attiva** su **Sì** per attivare il commercio interaziendale.</span><span class="sxs-lookup"><span data-stu-id="a67cd-110">Set **Active** to **Yes** to enable intercompany trading.</span></span>
6. <span data-ttu-id="a67cd-111">Nel campo **Società cliente**, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a67cd-111">In the **Customer company** field, enter or select a value.</span></span>
7. <span data-ttu-id="a67cd-112">Nel campo **Account personale** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a67cd-112">In the **My account** field, enter or select a value.</span></span>
8. <span data-ttu-id="a67cd-113">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-113">Select **Save**.</span></span>
9. <span data-ttu-id="a67cd-114">Chiudere le pagine per tornare alla home page.</span><span class="sxs-lookup"><span data-stu-id="a67cd-114">Close the pages to return to the home page.</span></span>
10. <span data-ttu-id="a67cd-115">Nel pannello di navigazione, andare a **Moduli > Gestione progetti e contabilità > Impostazione > Parametri Gestione progetti e contabilità**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-115">In the navigation pane, go to **Modules > Project management and accounting > Setup > Project management and accounting parameters**.</span></span>
11. <span data-ttu-id="a67cd-116">Selezionare la scheda **Interaziendale**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-116">Select the **Intercompany** tab.</span></span>
12. <span data-ttu-id="a67cd-117">Spostare il dispositivo di scorrimento su **Sì** per abilitare la programmazione delle risorse interaziendale e dei fogli presenze.</span><span class="sxs-lookup"><span data-stu-id="a67cd-117">Move the slider to **Yes** to enable intercompany resource scheduling and timesheets.</span></span>
13. <span data-ttu-id="a67cd-118">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a67cd-118">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="a67cd-119">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-119">Select **New**.</span></span>
15. <span data-ttu-id="a67cd-120">Nel campo **Persona giuridica richiedente** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a67cd-120">In the **Borrowing legal entity** field, enter or select a value.</span></span>
16. <span data-ttu-id="a67cd-121">Selezionare la casella di controllo **Accumula ricavi**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-121">Select the **Accrue revenue** check box.</span></span>
17. <span data-ttu-id="a67cd-122">Nel campo **Categoria di foglio presenze predefinita** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a67cd-122">In the **Default timesheet category** field, enter or select a value.</span></span>
18. <span data-ttu-id="a67cd-123">Nel campo **Categoria di spesa predefinita** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a67cd-123">In the **Default expense category** field, enter or select a value.</span></span>
19. <span data-ttu-id="a67cd-124">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-124">Select **Save**.</span></span>
20. <span data-ttu-id="a67cd-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a67cd-125">Close the page.</span></span>
21. <span data-ttu-id="a67cd-126">Nel pannello di navigazione, andare a **Moduli > Gestione progetti e contabilità > Impostazioni > Registrazione > Impostazioni registrazione contabile**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-126">In the navigation pane, go to **Modules > Project management and accounting > Setup > Posting > Ledger posting setup**.</span></span>
22. <span data-ttu-id="a67cd-127">Selezionare un'opzione nel campo **Tipi di conto CoGe**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-127">In the **Ledger account types** field, select an option.</span></span>
23. <span data-ttu-id="a67cd-128">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-128">Select **New**.</span></span>
24. <span data-ttu-id="a67cd-129">Nel campo **Conto principale** della nuova riga, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="a67cd-129">In the **Main account** field of the new row, specify the desired values.</span></span>
25. <span data-ttu-id="a67cd-130">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-130">Select **Save**.</span></span>
26. <span data-ttu-id="a67cd-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a67cd-131">Close the page.</span></span>
27. <span data-ttu-id="a67cd-132">Nel pannello di navigazione, andare a **Moduli > Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di trasferimento**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-132">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Transfer price**.</span></span>
28. <span data-ttu-id="a67cd-133">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-133">Select **New**.</span></span>
29. <span data-ttu-id="a67cd-134">Nel campo **Data di validità**, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="a67cd-134">In the **Effective date** field, enter a date.</span></span>
30. <span data-ttu-id="a67cd-135">Nel campo **Persona giuridica richiedente** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a67cd-135">In the **Borrowing legal entity** field, enter or select a value.</span></span>
31. <span data-ttu-id="a67cd-136">Nel campo **Modello di prezzo di trasferimento** selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="a67cd-136">In the **Transfer price model** field, select an option.</span></span>
32. <span data-ttu-id="a67cd-137">Immettere un numero nel campo **Determinazione prezzo**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-137">In the **Pricing** field, enter a number.</span></span>
33. <span data-ttu-id="a67cd-138">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-138">Select **Save**.</span></span>

