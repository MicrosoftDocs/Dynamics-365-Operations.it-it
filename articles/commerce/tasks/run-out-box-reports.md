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
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d3dd941eb4e682e61c8b3d10ef0ccd14239f090c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232715"
---
# <a name="generate-and-run-out-of-box-reports"></a><span data-ttu-id="febed-103">Generare ed eseguire report predefiniti</span><span class="sxs-lookup"><span data-stu-id="febed-103">Generate and run out of box reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="febed-104">Utilizzare la guida attività per eseguire report predefiniti in Headquarters da diverse aree di lavoro e report di richieste di informazioni e vendite presenti in Commerce.</span><span class="sxs-lookup"><span data-stu-id="febed-104">Use this task guide to run out of box reports in Headquarters from different workspaces and Inquiries & Sales reports located in Commerce.</span></span>

<span data-ttu-id="febed-105">La società di dati dimostrativi utilizzata per creare questa registrazione è USRT.</span><span class="sxs-lookup"><span data-stu-id="febed-105">The demo data company used to create this recording is USRT.</span></span> <span data-ttu-id="febed-106">Questa registrazione è destinata al ruolo di amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="febed-106">This recording is intended for the System administrator role.</span></span>

## <a name="launch-reports-from-workspaces"></a><span data-ttu-id="febed-107">Avviare report da aree di lavoro</span><span class="sxs-lookup"><span data-stu-id="febed-107">Launch reports from workspaces</span></span>
1. <span data-ttu-id="febed-108">Passare a Retail e Commerce > Prodotti e categorie > Gestione categorie e prodotti.</span><span class="sxs-lookup"><span data-stu-id="febed-108">Go to Retail and Commerce > Products and categories > Category and product management.</span></span>
2. <span data-ttu-id="febed-109">Fare clic sulla freccia per espandere o comprimere la sezione Report.</span><span class="sxs-lookup"><span data-stu-id="febed-109">Click the arrow to expand or collapse the Reports section.</span></span>
3. <span data-ttu-id="febed-110">Fare clic su Report prodotti principali.</span><span class="sxs-lookup"><span data-stu-id="febed-110">Click Top products report.</span></span>
4. <span data-ttu-id="febed-111">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="febed-111">In the From date field, enter a date.</span></span>
5. <span data-ttu-id="febed-112">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="febed-112">In the To date field, enter a date.</span></span>
6. <span data-ttu-id="febed-113">Nel campo Canale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="febed-113">In the Channel field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="febed-114">Nella struttura, selezionare 'Contoso Retail\Contoso Retail USA\Central\Houston'.</span><span class="sxs-lookup"><span data-stu-id="febed-114">In the tree, select 'Contoso Retail\Contoso Retail USA\Central\Houston'.</span></span>
    * <span data-ttu-id="febed-115">Viene visualizzata la gerarchia organizzativa vendita al dettaglio predefinita per lo scopo di report di Commerce.</span><span class="sxs-lookup"><span data-stu-id="febed-115">This shows the default organization hierarchy for Commerce reporting purpose.</span></span>   <span data-ttu-id="febed-116">Passare ad Amministrazione organizzazione > Organizzazioni > Scopi gerarchia organizzativa e scegliere Report per commercio in Gerarchie assegnate, quindi controllare il nome della gerarchia per cui è selezionata la colonna predefinita.</span><span class="sxs-lookup"><span data-stu-id="febed-116">Go to Organization administration > Organizations > Organization hierarchy purposes and choose Commerce reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span> <span data-ttu-id="febed-117">Come parte dei dati dimostrativi (utilizzati per questa registrazione di attività) si noterà che Punti vendita per area è la gerarchia organizzativa predefinita per lo scopo di report.</span><span class="sxs-lookup"><span data-stu-id="febed-117">As part of demo data (used for this task recording) you would notice, Stores by Region, is the default organization hierarchy for the reporting purpose.</span></span>     
8. <span data-ttu-id="febed-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="febed-118">Click OK.</span></span>
9. <span data-ttu-id="febed-119">Selezionare un'opzione nel campo Visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="febed-119">In the View field, select an option.</span></span>
10. <span data-ttu-id="febed-120">Selezionare un'opzione nel campo Per.</span><span class="sxs-lookup"><span data-stu-id="febed-120">In the By field, select an option.</span></span>
11. <span data-ttu-id="febed-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="febed-121">Click OK.</span></span>

## <a name="launch-reports-from-the-inquiries-and-sales-reports"></a><span data-ttu-id="febed-122">Avviare i report dalle richieste di informazioni e dai report di vendita</span><span class="sxs-lookup"><span data-stu-id="febed-122">Launch reports from the inquiries and sales reports</span></span>
1. <span data-ttu-id="febed-123">Passare a Retail e Commerce > Richieste di informazioni e report > Report vendite > Report vendite di categoria.</span><span class="sxs-lookup"><span data-stu-id="febed-123">Go to Retail and Commerce > Inquiries and reports > Sales reports > Category sales report.</span></span>
2. <span data-ttu-id="febed-124">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="febed-124">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="febed-125">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="febed-125">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="febed-126">Nel campo Canale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="febed-126">In the Channel field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="febed-127">Nella struttura, selezionare 'Contoso Retail\Contoso Retail USA\West\Seattle'.</span><span class="sxs-lookup"><span data-stu-id="febed-127">In the tree, select 'Contoso Retail\Contoso Retail USA\West\Seattle'.</span></span>
    * <span data-ttu-id="febed-128">Viene visualizzata la gerarchia organizzativa vendita al dettaglio predefinita per lo scopo di report di Commerce.</span><span class="sxs-lookup"><span data-stu-id="febed-128">This shows the default organization hierarchy for Commerce reporting purpose.</span></span> <span data-ttu-id="febed-129">Passare ad Amministrazione organizzazione > Organizzazioni > Scopi gerarchia organizzativa e scegliere Report per commercio in Gerarchie assegnate, quindi controllare il nome della gerarchia per cui è selezionata la colonna predefinita.</span><span class="sxs-lookup"><span data-stu-id="febed-129">Go to Organization administration > Organizations > Organization hierarchy purposes and choose Commerce reporting and under Assigned hierarchies, check the hierarchy name for which Default column is checked.</span></span> <span data-ttu-id="febed-130">Come parte dei dati dimostrativi (utilizzati per questa registrazione di attività) si noterà che Punti vendita per area è la gerarchia organizzativa predefinita per lo scopo di report.</span><span class="sxs-lookup"><span data-stu-id="febed-130">As part of demo data (used for this task recording) you would notice, Stores by Region, is the default organization hierarchy for the reporting purpose.</span></span>     
6. <span data-ttu-id="febed-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="febed-131">Click OK.</span></span>
7. <span data-ttu-id="febed-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="febed-132">Click OK.</span></span>

## <a name="export-an-hq-reports"></a><span data-ttu-id="febed-133">Esportare i report di una sede centrale</span><span class="sxs-lookup"><span data-stu-id="febed-133">Export an HQ reports</span></span>
1. <span data-ttu-id="febed-134">Passare a Retail e Commerce > Richieste di informazioni e report > Report vendite > Report vendite organizzazione.</span><span class="sxs-lookup"><span data-stu-id="febed-134">Go to Retail and Commerce > Inquiries and reports > Sales reports > Organization sales report.</span></span>
2. <span data-ttu-id="febed-135">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="febed-135">In the From date field, enter a date.</span></span>
3. <span data-ttu-id="febed-136">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="febed-136">In the To date field, enter a date.</span></span>
4. <span data-ttu-id="febed-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="febed-137">Click OK.</span></span>
5. <span data-ttu-id="febed-138">Fare clic su Esporta.</span><span class="sxs-lookup"><span data-stu-id="febed-138">Click Export.</span></span>
6. <span data-ttu-id="febed-139">Fare clic su PDF.</span><span class="sxs-lookup"><span data-stu-id="febed-139">Click PDF.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]