---
title: Configurare condivisione dati interaziendali finanziari
description: Questa procedura mostra come configurare, abilitare, convalidare e risolvere i conflitti quando vengono condivisi i dati tra due società.
author: aprilolson
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportRnr, DMFExecutionHistoryWorkspace, DMFExecutionHistorySummary, DMFExecutionHistoryEntities,  SysDataSharingConfiguration, SysDataSharingDiscrepencies
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aeb9e85d3263d78a8412bd3c300dae8bb1d840ef
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685195"
---
# <a name="configure-financial-cross-company-data-sharing"></a><span data-ttu-id="55cf7-103">Configurare condivisione dati interaziendali finanziari</span><span class="sxs-lookup"><span data-stu-id="55cf7-103">Configure financial cross-company data sharing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="55cf7-104">Questa procedura mostra come configurare, abilitare, convalidare e risolvere i conflitti quando vengono condivisi i dati tra due società.</span><span class="sxs-lookup"><span data-stu-id="55cf7-104">This procedure shows how to configure, enable, validate, and resolve conflicts when sharing data between companies.</span></span> <span data-ttu-id="55cf7-105">Utilizza la società USMF e il modello di condivisione dei dati finanziari.</span><span class="sxs-lookup"><span data-stu-id="55cf7-105">It uses the USMF company and the Financial data sharing template.</span></span>

<span data-ttu-id="55cf7-106">Questa guida attività richiede la piattaforma 7.1 o una versione successiva di Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="55cf7-106">This task guide requires Dynamics AX platform 7.1 or later.</span></span>

1. <span data-ttu-id="55cf7-107">Selezionare **Pannello di navigazione > Moduli > Amministrazione sistema > Aree di lavoro > Gestione dati**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-107">Go to **Navigation pane > Modules > System administration > Workspaces > Data management**.</span></span>
2. <span data-ttu-id="55cf7-108">Fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-108">Click **Import**.</span></span>
3. <span data-ttu-id="55cf7-109">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-109">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="55cf7-110">Nel campo **Formato dati di origine** selezionare il tipo di "pacchetto".</span><span class="sxs-lookup"><span data-stu-id="55cf7-110">In the **Source data format** field, select the 'Package' type.</span></span> <span data-ttu-id="55cf7-111">Fare clic su **Carica**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-111">Click **Upload**.</span></span> <span data-ttu-id="55cf7-112">Spostarsi nell'ubicazione del file pacchetto del modello di condivisione dei dati finanziari e selezionare il file.</span><span class="sxs-lookup"><span data-stu-id="55cf7-112">Navigate to the location of the Financial data sharing template package file and select that file.</span></span>
5. <span data-ttu-id="55cf7-113">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-113">Click **Save**.</span></span>
6. <span data-ttu-id="55cf7-114">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="55cf7-114">In the list, mark the selected row.</span></span> <span data-ttu-id="55cf7-115">Selezionare i criteri appena creati di condivisione dei dati.</span><span class="sxs-lookup"><span data-stu-id="55cf7-115">Select the data sharing policy that was just created.</span></span>  
7. <span data-ttu-id="55cf7-116">Fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-116">Click **Import**.</span></span>
8. <span data-ttu-id="55cf7-117">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-117">Click **Close**.</span></span>
9. <span data-ttu-id="55cf7-118">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="55cf7-118">Refresh the page.</span></span>
10. <span data-ttu-id="55cf7-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="55cf7-119">Close the page.</span></span>
11. <span data-ttu-id="55cf7-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="55cf7-120">Close the page.</span></span>
12. <span data-ttu-id="55cf7-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="55cf7-121">Close the page.</span></span>
13. <span data-ttu-id="55cf7-122">Selezionare **Pannello di navigazione > Moduli > Amministrazione sistema > Impostazione > Configura condivisione dati interaziendali**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-122">Go to **Navigation pane > Modules > System administration > Setup > Configure cross-company data sharing**.</span></span>
14. <span data-ttu-id="55cf7-123">Nell'elenco trovare e selezionare **Giorni di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-123">In the list, find and select **Payment days**.</span></span>
15. <span data-ttu-id="55cf7-124">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-124">Click **Add**.</span></span>
16. <span data-ttu-id="55cf7-125">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="55cf7-125">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="55cf7-126">Digitare "USSI" nel campo **Società**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-126">In the **Company** field, type 'USSI'.</span></span>
18. <span data-ttu-id="55cf7-127">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-127">Click **Add**.</span></span>
19. <span data-ttu-id="55cf7-128">Digitare "USMF" nel campo **Società**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-128">In the **Company** field, type 'USMF'.</span></span>
20. <span data-ttu-id="55cf7-129">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-129">Click **Save**.</span></span>
21. <span data-ttu-id="55cf7-130">Fare clic su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-130">Click **Enable**.</span></span>
22. <span data-ttu-id="55cf7-131">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-131">Click **Yes**.</span></span>
23. <span data-ttu-id="55cf7-132">Fare clic su **Cerca problemi di condivisione**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-132">Click **Find sharing issues**.</span></span>
24. <span data-ttu-id="55cf7-133">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-133">Click **Yes**.</span></span>
25. <span data-ttu-id="55cf7-134">Fare clic su **Aggiorna valore campo**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-134">Click **Update field value**.</span></span>
26. <span data-ttu-id="55cf7-135">Fare clic su **Utilizza valore di società 1**.</span><span class="sxs-lookup"><span data-stu-id="55cf7-135">Click **Use value from company 1**.</span></span>
27. <span data-ttu-id="55cf7-136">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="55cf7-136">Refresh the page.</span></span>
28. <span data-ttu-id="55cf7-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="55cf7-137">Close the page.</span></span>

