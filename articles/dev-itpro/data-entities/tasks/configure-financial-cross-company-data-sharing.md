---
title: Configurare condivisione dati interaziendali finanziari
description: Questa procedura mostra come configurare, abilitare, convalidare e risolvere i conflitti quando vengono condivisi i dati tra due società.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportRnr, DMFExecutionHistoryWorkspace, DMFExecutionHistorySummary, DMFExecutionHistoryEntities,  SysDataSharingConfiguration, SysDataSharingDiscrepencies
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 049ffeee7db95cc2e5a31526d5d99026303456be
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848257"
---
# <a name="configure-financial-cross-company-data-sharing"></a><span data-ttu-id="c56e6-103">Configurare condivisione dati interaziendali finanziari</span><span class="sxs-lookup"><span data-stu-id="c56e6-103">Configure financial cross-company data sharing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c56e6-104">Questa procedura mostra come configurare, abilitare, convalidare e risolvere i conflitti quando vengono condivisi i dati tra due società.</span><span class="sxs-lookup"><span data-stu-id="c56e6-104">This procedure shows how to configure, enable, validate, and resolve conflicts when sharing data between companies.</span></span> <span data-ttu-id="c56e6-105">Utilizza la società USMF e il modello di condivisione dei dati finanziari.</span><span class="sxs-lookup"><span data-stu-id="c56e6-105">It uses the USMF company and the Financial data sharing template.</span></span>



<span data-ttu-id="c56e6-106">Questa guida attività richiede la piattaforma 7.1 o una versione successiva di Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="c56e6-106">This task guide requires Dynamics AX platform 7.1 or later.</span></span>

1. <span data-ttu-id="c56e6-107">Andare a Amministrazione sistema > Aree di lavoro > Gestione dati.</span><span class="sxs-lookup"><span data-stu-id="c56e6-107">Go to System administration > Workspaces > Data management.</span></span>
2. <span data-ttu-id="c56e6-108">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="c56e6-108">Click Import.</span></span>
3. <span data-ttu-id="c56e6-109">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="c56e6-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="c56e6-110">Nel campo Formato dati di origine selezionare Tipo di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c56e6-110">In the Source data format field, select the Package type.</span></span>
    * <span data-ttu-id="c56e6-111">Fare clic su Carica.</span><span class="sxs-lookup"><span data-stu-id="c56e6-111">Click Upload.</span></span> <span data-ttu-id="c56e6-112">Spostarsi nell'ubicazione del file pacchetto del modello di condivisione dei dati finanziari e selezionare il file.</span><span class="sxs-lookup"><span data-stu-id="c56e6-112">Navigate to the location of the Financial data sharing template package file and select that file.</span></span>  
5. <span data-ttu-id="c56e6-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c56e6-113">Click Save.</span></span>
6. <span data-ttu-id="c56e6-114">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c56e6-114">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="c56e6-115">Selezionare i criteri appena creati di condivisione dei dati.</span><span class="sxs-lookup"><span data-stu-id="c56e6-115">Select the data sharing policy that was just created.</span></span>  
7. <span data-ttu-id="c56e6-116">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="c56e6-116">Click Import.</span></span>
8. <span data-ttu-id="c56e6-117">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="c56e6-117">Click Close.</span></span>
9. <span data-ttu-id="c56e6-118">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="c56e6-118">Refresh the page.</span></span>
10. <span data-ttu-id="c56e6-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c56e6-119">Close the page.</span></span>
11. <span data-ttu-id="c56e6-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c56e6-120">Close the page.</span></span>
12. <span data-ttu-id="c56e6-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c56e6-121">Close the page.</span></span>
13. <span data-ttu-id="c56e6-122">Andare a Amministrazione sistema > Impostazione > Configura condivisione dati interaziendali.</span><span class="sxs-lookup"><span data-stu-id="c56e6-122">Go to System administration > Setup > Configure cross-company data sharing.</span></span>
14. <span data-ttu-id="c56e6-123">Nell'elenco trovare e selezionare Giorni di pagamento.</span><span class="sxs-lookup"><span data-stu-id="c56e6-123">In the list, find and select Payment days.</span></span>
15. <span data-ttu-id="c56e6-124">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="c56e6-124">Click Add.</span></span>
16. <span data-ttu-id="c56e6-125">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c56e6-125">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="c56e6-126">Digitare "USSI" nel campo Società.</span><span class="sxs-lookup"><span data-stu-id="c56e6-126">In the Company field, type 'USSI'.</span></span>
18. <span data-ttu-id="c56e6-127">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="c56e6-127">Click Add.</span></span>
19. <span data-ttu-id="c56e6-128">Digitare "USMF" nel campo Società.</span><span class="sxs-lookup"><span data-stu-id="c56e6-128">In the Company field, type 'USMF'.</span></span>
20. <span data-ttu-id="c56e6-129">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c56e6-129">Click Save.</span></span>
21. <span data-ttu-id="c56e6-130">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="c56e6-130">Click Enable.</span></span>
22. <span data-ttu-id="c56e6-131">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="c56e6-131">Click Yes.</span></span>
23. <span data-ttu-id="c56e6-132">Fare clic su Cerca problemi di condivisione.</span><span class="sxs-lookup"><span data-stu-id="c56e6-132">Click Find sharing issues.</span></span>
24. <span data-ttu-id="c56e6-133">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="c56e6-133">Click Yes.</span></span>
25. <span data-ttu-id="c56e6-134">Fare clic su Aggiorna valore campo.</span><span class="sxs-lookup"><span data-stu-id="c56e6-134">Click Update field value.</span></span>
26. <span data-ttu-id="c56e6-135">Fare clic su Utilizza valore di società 1.</span><span class="sxs-lookup"><span data-stu-id="c56e6-135">Click Use value from company 1.</span></span>
27. <span data-ttu-id="c56e6-136">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="c56e6-136">Refresh the page.</span></span>
28. <span data-ttu-id="c56e6-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c56e6-137">Close the page.</span></span>

