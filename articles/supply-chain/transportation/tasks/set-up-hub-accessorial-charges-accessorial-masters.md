--- 
title: Impostare le spese accessorie per l'hub e le spese accessorie principali
description: Questa procedura mostra come creare spese accessorie principali per un hub e come utilizzare tali dati per creare spese accessorie per l'hub.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 9959c20f9a8fd07cbf0cfd76f7760b44d7b5cae1
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a><span data-ttu-id="201be-103">Impostare le spese accessorie per l'hub e le spese accessorie principali</span><span class="sxs-lookup"><span data-stu-id="201be-103">Set up hub accessorial charges and accessorial masters</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="201be-104">Questa procedura mostra come creare spese accessorie principali per un hub e come utilizzare tali dati per creare spese accessorie per l'hub.</span><span class="sxs-lookup"><span data-stu-id="201be-104">This procedure shows how to create an accessorial master for a hub and use that master to create a hub accessorial charge.</span></span> <span data-ttu-id="201be-105">La procedura utilizza il set di dati di USMF.</span><span class="sxs-lookup"><span data-stu-id="201be-105">The procedure uses the USMF dataset.</span></span> <span data-ttu-id="201be-106">Questa impostazione viene in genere eseguita dal coordinatore dei trasporti.</span><span class="sxs-lookup"><span data-stu-id="201be-106">This set up will typically be done by a transportation coordinator.</span></span>


## <a name="set-up-a-hub-master"></a><span data-ttu-id="201be-107">Impostare un hub principale</span><span class="sxs-lookup"><span data-stu-id="201be-107">Set up a hub master</span></span>
1. <span data-ttu-id="201be-108">Andare a Gestione trasporto > Impostazioni > Valutazione > Rappresentazioni generali accessorie.</span><span class="sxs-lookup"><span data-stu-id="201be-108">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="201be-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="201be-109">Click New.</span></span>
3. <span data-ttu-id="201be-110">Nel campo Spese accessorie principali digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="201be-110">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="201be-111">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="201be-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="201be-112">Nel campo Tipo di spese accessorie selezionare "Hub".</span><span class="sxs-lookup"><span data-stu-id="201be-112">In the Accessorial type field, select 'Hub'.</span></span>
6. <span data-ttu-id="201be-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="201be-113">Click Save.</span></span>
7. <span data-ttu-id="201be-114">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="201be-114">Close the page.</span></span>

## <a name="set-up-a-hub-accessorial-charge"></a><span data-ttu-id="201be-115">Impostare una spesa accessoria per l'hub</span><span class="sxs-lookup"><span data-stu-id="201be-115">Set up a hub accessorial charge</span></span>
1. <span data-ttu-id="201be-116">Andare a Gestione trasporto > Impostazioni > Valutazione > Spese accessorie hub.</span><span class="sxs-lookup"><span data-stu-id="201be-116">Go to Transportation management > Setup > Rating > Hub accessorial charges.</span></span>
2. <span data-ttu-id="201be-117">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="201be-117">Click New.</span></span>
3. <span data-ttu-id="201be-118">Nel campo ID spese accessorie hub digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="201be-118">In the Hub accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="201be-119">Nel campo Hub fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="201be-119">In the Hub field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="201be-120">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="201be-120">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="201be-121">Selezionare un'opzione nel campo Posizione hub.</span><span class="sxs-lookup"><span data-stu-id="201be-121">In the Hub position field, select an option.</span></span>
    * <span data-ttu-id="201be-122">È possibile creare la spesa come spesa di prelievo o di consegna.</span><span class="sxs-lookup"><span data-stu-id="201be-122">You can either create the charge as a pickup or drop-off.</span></span> <span data-ttu-id="201be-123">A seconda della selezione, la spesa verrà applicata al segmento di trasporto corrispondente nel percorso.</span><span class="sxs-lookup"><span data-stu-id="201be-123">Depending on your selection the charge will be applied to the corresponding transportation segment on your route.</span></span>  
7. <span data-ttu-id="201be-124">Nel campo Spese accessorie principali fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="201be-124">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="201be-125">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="201be-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="201be-126">Selezionare i dati master creati.</span><span class="sxs-lookup"><span data-stu-id="201be-126">Select the master you just created.</span></span>  
9. <span data-ttu-id="201be-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="201be-127">Click Save.</span></span>
10. <span data-ttu-id="201be-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="201be-128">Close the page.</span></span>


