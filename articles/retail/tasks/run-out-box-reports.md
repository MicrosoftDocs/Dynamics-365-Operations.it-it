---
title: Generare ed eseguire report predefiniti
description: Utilizzare la guida attività per eseguire report predefiniti nelle sedi centrali da diverse aree di lavoro e report di richieste di informazioni e vendite presenti in Vendita al dettaglio e commercio.
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
ms.openlocfilehash: afd4509bc9bdff345e48a590a12cc84ae25aebb8
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2018437"
---
# <a name="generate-and-run-out-of-box-reports"></a><span data-ttu-id="f6141-103">Generare ed eseguire report predefiniti</span><span class="sxs-lookup"><span data-stu-id="f6141-103">Generate and run out of box reports</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="f6141-104">Utilizzare la guida attività per eseguire report predefiniti nelle sedi centrali da diverse aree di lavoro e report di richieste di informazioni e vendite presenti in Vendita al dettaglio e commercio.</span><span class="sxs-lookup"><span data-stu-id="f6141-104">Use this task guide to run out of box reports in headquarters from different workspaces and Inquiries & Sales reports located under Retail & Commerce.</span></span>



<span data-ttu-id="f6141-105">La società di dati dimostrativi utilizzata per creare questa registrazione è USRT.</span><span class="sxs-lookup"><span data-stu-id="f6141-105">The demo data company used to create this recording is USRT.</span></span> <span data-ttu-id="f6141-106">Questa registrazione è destinata al ruolo di amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="f6141-106">This recording is intended for the System administrator role.</span></span>


## <a name="launch-reports-from-workspaces"></a><span data-ttu-id="f6141-107">Avviare report da aree di lavoro</span><span class="sxs-lookup"><span data-stu-id="f6141-107">Launch reports from workspaces</span></span>
1. <span data-ttu-id="f6141-108">Passare a Vendita al dettaglio e commercio > Prodotti e categorie > Gestione categorie e prodotti.</span><span class="sxs-lookup"><span data-stu-id="f6141-108">Go to Retail and commerce > Products and categories > Category and product management.</span></span>
2. <span data-ttu-id="f6141-109">Fare clic sulla freccia per espandere o comprimere la sezione Report.</span><span class="sxs-lookup"><span data-stu-id="f6141-109">Click the arrow to expand or collapse the Reports section.</span></span>
3. <span data-ttu-id="f6141-110">Fare clic su Report prodotti principali.</span><span class="sxs-lookup"><span data-stu-id="f6141-110">Click Top products report.</span></span>
4. <span data-ttu-id="f6141-111">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="f6141-111">In the From date field, enter a date.</span></span>
5. <span data-ttu-id="f6141-112">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="f6141-112">In the To date field, enter a date.</span></span>
6. <span data-ttu-id="f6141-113">Nel campo Canale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f6141-113">In the Channel field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="f6141-114">Nella struttura, selezionare 'Contoso Retail\Contoso Retail USA\Central\Houston'.</span><span class="sxs-lookup"><span data-stu-id="f6141-114">In the tree, select 'Contoso Retail\Contoso Retail USA\Central\Houston'.</span></span>
    * <span data-ttu-id="f6141-115">Viene visualizzata la gerarchia organizzativa vendita al dettaglio predefinita per lo scopo di report per vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f6141-115">This shows the default retail organization hierarchy for Retail reporting purpose.</span></span>   <span data-ttu-id="f6141-116">Passare ad Amministrazione organizzazione > Organizzazioni > Scopi gerarchia organizzativa e scegliere Report per vendita al dettaglio in Gerarchie assegnate, quindi controllare il nome della gerarchia per cui è selezionata la colonna predefinita.</span><span class="sxs-lookup"><span data-stu-id="f6141-116">Go to Organization administration >  Organizations > Organization hierarchy purposes and choose Retail reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span> <span data-ttu-id="f6141-117">Come parte dei dati dimostrativi (utilizzati per questa registrazione di attività) si noterà che Punti vendita al dettaglio per area è la gerarchia organizzativa predefinita per lo scopo di report per vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f6141-117">As part of demo data (used for this task recording) you would notice, Retail Stores by Region, is the default organization hierarchy for the Retail reporting purpose.</span></span>     
8. <span data-ttu-id="f6141-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f6141-118">Click OK.</span></span>
9. <span data-ttu-id="f6141-119">Selezionare un'opzione nel campo Visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="f6141-119">In the View field, select an option.</span></span>
10. <span data-ttu-id="f6141-120">Selezionare un'opzione nel campo Per.</span><span class="sxs-lookup"><span data-stu-id="f6141-120">In the By field, select an option.</span></span>
11. <span data-ttu-id="f6141-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f6141-121">Click OK.</span></span>

## <a name="launch-reports-from-the-inquiries-and-sales-reports-located-under-retail--commerce-app-link"></a><span data-ttu-id="f6141-122">Avviare i report dalle richieste di informazioni e dai report di vendita che si trovano nel collegamento dell'app Vendita al dettaglio e commercio.</span><span class="sxs-lookup"><span data-stu-id="f6141-122">Launch reports from the inquiries and sales reports located under Retail & Commerce app link.</span></span>
1. <span data-ttu-id="f6141-123">Passare a Vendita al dettaglio e commercio > Richieste di informazioni e report > Report vendite > Report vendite di categoria.</span><span class="sxs-lookup"><span data-stu-id="f6141-123">Go to Retail and commerce > Inquiries and reports > Sales reports > Category sales report.</span></span>
2. <span data-ttu-id="f6141-124">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="f6141-124">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="f6141-125">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="f6141-125">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="f6141-126">Nel campo Canale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f6141-126">In the Channel field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="f6141-127">Nella struttura, selezionare 'Contoso Retail\Contoso Retail USA\West\Seattle'.</span><span class="sxs-lookup"><span data-stu-id="f6141-127">In the tree, select 'Contoso Retail\Contoso Retail USA\West\Seattle'.</span></span>
    * <span data-ttu-id="f6141-128">Viene visualizzata la gerarchia organizzativa vendita al dettaglio predefinita per lo scopo di report per vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f6141-128">This shows the default retail organization hierarchy for Retail reporting purpose.</span></span>   <span data-ttu-id="f6141-129">Passare ad Amministrazione organizzazione > Organizzazioni > Scopi gerarchia organizzativa e scegliere Report per vendita al dettaglio in Gerarchie assegnate, quindi controllare il nome della gerarchia per cui è selezionata la colonna predefinita.</span><span class="sxs-lookup"><span data-stu-id="f6141-129">Go to Organization administration  > Organizations > Organization hierarchy purposes and choose Retail reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span> <span data-ttu-id="f6141-130">Come parte dei dati dimostrativi (utilizzati per questa registrazione di attività) si noterà che Punti vendita al dettaglio per area è la gerarchia organizzativa predefinita per lo scopo di report per vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f6141-130">As part of demo data (used for this task recording) you would notice, Retail Stores by Region, is the default organization hierarchy for the Retail reporting purpose.</span></span>     
6. <span data-ttu-id="f6141-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f6141-131">Click OK.</span></span>
7. <span data-ttu-id="f6141-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f6141-132">Click OK.</span></span>

## <a name="export-an-hq-reports"></a><span data-ttu-id="f6141-133">Esportare i report di una sede centrale</span><span class="sxs-lookup"><span data-stu-id="f6141-133">Export an HQ reports</span></span>
1. <span data-ttu-id="f6141-134">Passare a Vendita al dettaglio e commercio > Richieste di informazioni e report > Report vendite > Report vendite organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f6141-134">Go to Retail and commerce > Inquiries and reports > Sales reports > Organization sales report.</span></span>
2. <span data-ttu-id="f6141-135">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="f6141-135">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="f6141-136">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="f6141-136">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="f6141-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f6141-137">Click OK.</span></span>
5. <span data-ttu-id="f6141-138">Fare clic su Esporta.</span><span class="sxs-lookup"><span data-stu-id="f6141-138">Click Export.</span></span>
6. <span data-ttu-id="f6141-139">Fare clic su PDF.</span><span class="sxs-lookup"><span data-stu-id="f6141-139">Click PDF.</span></span>

