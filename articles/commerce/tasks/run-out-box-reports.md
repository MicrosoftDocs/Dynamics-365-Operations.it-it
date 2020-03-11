---
title: Generare ed eseguire report predefiniti
description: Utilizzare la guida attività per eseguire report predefiniti in Headquarters da diverse aree di lavoro e report di richieste di informazioni e vendite presenti in Commerce.
author: ashishmsft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailCategoryAndProductWorkspace, RetailOrgHierarchyTreeLookup, SrsReportViewerForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5f9931a39e4ca2141ed5b43086226c7fcc7cbd7c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023016"
---
# <a name="generate-and-run-out-of-box-reports"></a><span data-ttu-id="9caf0-103">Generare ed eseguire report predefiniti</span><span class="sxs-lookup"><span data-stu-id="9caf0-103">Generate and run out of box reports</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="9caf0-104">Utilizzare la guida attività per eseguire report predefiniti in Headquarters da diverse aree di lavoro e report di richieste di informazioni e vendite presenti in Commerce.</span><span class="sxs-lookup"><span data-stu-id="9caf0-104">Use this task guide to run out of box reports in Headquarters from different workspaces and Inquiries & Sales reports located in Commerce.</span></span>

<span data-ttu-id="9caf0-105">La società di dati dimostrativi utilizzata per creare questa registrazione è USRT.</span><span class="sxs-lookup"><span data-stu-id="9caf0-105">The demo data company used to create this recording is USRT.</span></span> <span data-ttu-id="9caf0-106">Questa registrazione è destinata al ruolo di amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="9caf0-106">This recording is intended for the System administrator role.</span></span>

## <a name="launch-reports-from-workspaces"></a><span data-ttu-id="9caf0-107">Avviare report da aree di lavoro</span><span class="sxs-lookup"><span data-stu-id="9caf0-107">Launch reports from workspaces</span></span>
1. <span data-ttu-id="9caf0-108">Passare a Retail e Commerce > Prodotti e categorie > Gestione categorie e prodotti.</span><span class="sxs-lookup"><span data-stu-id="9caf0-108">Go to Retail and Commerce > Products and categories > Category and product management.</span></span>
2. <span data-ttu-id="9caf0-109">Fare clic sulla freccia per espandere o comprimere la sezione Report.</span><span class="sxs-lookup"><span data-stu-id="9caf0-109">Click the arrow to expand or collapse the Reports section.</span></span>
3. <span data-ttu-id="9caf0-110">Fare clic su Report prodotti principali.</span><span class="sxs-lookup"><span data-stu-id="9caf0-110">Click Top products report.</span></span>
4. <span data-ttu-id="9caf0-111">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="9caf0-111">In the From date field, enter a date.</span></span>
5. <span data-ttu-id="9caf0-112">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="9caf0-112">In the To date field, enter a date.</span></span>
6. <span data-ttu-id="9caf0-113">Nel campo Canale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="9caf0-113">In the Channel field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="9caf0-114">Nella struttura, selezionare 'Contoso Retail\Contoso Retail USA\Central\Houston'.</span><span class="sxs-lookup"><span data-stu-id="9caf0-114">In the tree, select 'Contoso Retail\Contoso Retail USA\Central\Houston'.</span></span>
    * <span data-ttu-id="9caf0-115">Viene visualizzata la gerarchia organizzativa vendita al dettaglio predefinita per lo scopo di report di Commerce.</span><span class="sxs-lookup"><span data-stu-id="9caf0-115">This shows the default organization hierarchy for Commerce reporting purpose.</span></span>   <span data-ttu-id="9caf0-116">Passare ad Amministrazione organizzazione > Organizzazioni > Scopi gerarchia organizzativa e scegliere Report per commercio in Gerarchie assegnate, quindi controllare il nome della gerarchia per cui è selezionata la colonna predefinita.</span><span class="sxs-lookup"><span data-stu-id="9caf0-116">Go to Organization administration > Organizations > Organization hierarchy purposes and choose Commerce reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span> <span data-ttu-id="9caf0-117">Come parte dei dati dimostrativi (utilizzati per questa registrazione di attività) si noterà che Punti vendita per area è la gerarchia organizzativa predefinita per lo scopo di report.</span><span class="sxs-lookup"><span data-stu-id="9caf0-117">As part of demo data (used for this task recording) you would notice, Stores by Region, is the default organization hierarchy for the reporting purpose.</span></span>     
8. <span data-ttu-id="9caf0-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9caf0-118">Click OK.</span></span>
9. <span data-ttu-id="9caf0-119">Selezionare un'opzione nel campo Visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="9caf0-119">In the View field, select an option.</span></span>
10. <span data-ttu-id="9caf0-120">Selezionare un'opzione nel campo Per.</span><span class="sxs-lookup"><span data-stu-id="9caf0-120">In the By field, select an option.</span></span>
11. <span data-ttu-id="9caf0-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9caf0-121">Click OK.</span></span>

## <a name="launch-reports-from-the-inquiries-and-sales-reports"></a><span data-ttu-id="9caf0-122">Avviare i report dalle richieste di informazioni e dai report di vendita</span><span class="sxs-lookup"><span data-stu-id="9caf0-122">Launch reports from the inquiries and sales reports</span></span>
1. <span data-ttu-id="9caf0-123">Passare a Retail e Commerce > Richieste di informazioni e report > Report vendite > Report vendite di categoria.</span><span class="sxs-lookup"><span data-stu-id="9caf0-123">Go to Retail and Commerce > Inquiries and reports > Sales reports > Category sales report.</span></span>
2. <span data-ttu-id="9caf0-124">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="9caf0-124">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="9caf0-125">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="9caf0-125">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="9caf0-126">Nel campo Canale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="9caf0-126">In the Channel field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="9caf0-127">Nella struttura, selezionare 'Contoso Retail\Contoso Retail USA\West\Seattle'.</span><span class="sxs-lookup"><span data-stu-id="9caf0-127">In the tree, select 'Contoso Retail\Contoso Retail USA\West\Seattle'.</span></span>
    * <span data-ttu-id="9caf0-128">Viene visualizzata la gerarchia organizzativa vendita al dettaglio predefinita per lo scopo di report di Commerce.</span><span class="sxs-lookup"><span data-stu-id="9caf0-128">This shows the default organization hierarchy for Commerce reporting purpose.</span></span> <span data-ttu-id="9caf0-129">Passare ad Amministrazione organizzazione > Organizzazioni > Scopi gerarchia organizzativa e scegliere Report per commercio in Gerarchie assegnate, quindi controllare il nome della gerarchia per cui è selezionata la colonna predefinita.</span><span class="sxs-lookup"><span data-stu-id="9caf0-129">Go to Organization administration > Organizations > Organization hierarchy purposes and choose Commerce reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span> <span data-ttu-id="9caf0-130">Come parte dei dati dimostrativi (utilizzati per questa registrazione di attività) si noterà che Punti vendita per area è la gerarchia organizzativa predefinita per lo scopo di report.</span><span class="sxs-lookup"><span data-stu-id="9caf0-130">As part of demo data (used for this task recording) you would notice, Stores by Region, is the default organization hierarchy for the reporting purpose.</span></span>     
6. <span data-ttu-id="9caf0-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9caf0-131">Click OK.</span></span>
7. <span data-ttu-id="9caf0-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9caf0-132">Click OK.</span></span>

## <a name="export-an-hq-reports"></a><span data-ttu-id="9caf0-133">Esportare i report di una sede centrale</span><span class="sxs-lookup"><span data-stu-id="9caf0-133">Export an HQ reports</span></span>
1. <span data-ttu-id="9caf0-134">Passare a Retail e Commerce > Richieste di informazioni e report > Report vendite > Report vendite organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9caf0-134">Go to Retail and Commerce > Inquiries and reports > Sales reports > Organization sales report.</span></span>
2. <span data-ttu-id="9caf0-135">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="9caf0-135">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="9caf0-136">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="9caf0-136">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="9caf0-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9caf0-137">Click OK.</span></span>
5. <span data-ttu-id="9caf0-138">Fare clic su Esporta.</span><span class="sxs-lookup"><span data-stu-id="9caf0-138">Click Export.</span></span>
6. <span data-ttu-id="9caf0-139">Fare clic su PDF.</span><span class="sxs-lookup"><span data-stu-id="9caf0-139">Click PDF.</span></span>
