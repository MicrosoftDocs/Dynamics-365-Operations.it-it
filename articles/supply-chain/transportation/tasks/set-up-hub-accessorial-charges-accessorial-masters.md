---
title: Impostare le spese accessorie per l'hub e le spese accessorie principali
description: Questa procedura mostra come creare spese accessorie principali per un hub e come utilizzare tali dati per creare spese accessorie per l'hub.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSCarrierAccessorial,TMSAccessorialMaster, TMSHubAccessorial
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad89afe0a21261c57311c439153b969d837748e4
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2020
ms.locfileid: "4431609"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a><span data-ttu-id="2649e-103">Impostare le spese accessorie per l'hub e le spese accessorie principali</span><span class="sxs-lookup"><span data-stu-id="2649e-103">Set up hub accessorial charges and accessorial masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2649e-104">Questa procedura mostra come creare spese accessorie principali per un hub e come utilizzare tali dati per creare spese accessorie per l'hub.</span><span class="sxs-lookup"><span data-stu-id="2649e-104">This procedure shows how to create an accessorial master for a hub and use that master to create a hub accessorial charge.</span></span> <span data-ttu-id="2649e-105">La procedura utilizza il set di dati di USMF.</span><span class="sxs-lookup"><span data-stu-id="2649e-105">The procedure uses the USMF dataset.</span></span> <span data-ttu-id="2649e-106">Questa impostazione viene in genere eseguita dal coordinatore dei trasporti.</span><span class="sxs-lookup"><span data-stu-id="2649e-106">This set up will typically be done by a transportation coordinator.</span></span>


## <a name="set-up-a-hub-master"></a><span data-ttu-id="2649e-107">Impostare un hub principale</span><span class="sxs-lookup"><span data-stu-id="2649e-107">Set up a hub master</span></span>
1. <span data-ttu-id="2649e-108">Andare a Gestione trasporto > Impostazioni > Valutazione > Rappresentazioni generali accessorie.</span><span class="sxs-lookup"><span data-stu-id="2649e-108">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="2649e-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2649e-109">Click New.</span></span>
3. <span data-ttu-id="2649e-110">Nel campo Spese accessorie principali digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2649e-110">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="2649e-111">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="2649e-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="2649e-112">Nel campo Tipo di spese accessorie selezionare "Hub".</span><span class="sxs-lookup"><span data-stu-id="2649e-112">In the Accessorial type field, select 'Hub'.</span></span>
6. <span data-ttu-id="2649e-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2649e-113">Click Save.</span></span>
7. <span data-ttu-id="2649e-114">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2649e-114">Close the page.</span></span>

## <a name="set-up-a-hub-accessorial-charge"></a><span data-ttu-id="2649e-115">Impostare una spesa accessoria per l'hub</span><span class="sxs-lookup"><span data-stu-id="2649e-115">Set up a hub accessorial charge</span></span>
1. <span data-ttu-id="2649e-116">Andare a Gestione trasporto > Impostazioni > Valutazione > Spese accessorie hub.</span><span class="sxs-lookup"><span data-stu-id="2649e-116">Go to Transportation management > Setup > Rating > Hub accessorial charges.</span></span>
2. <span data-ttu-id="2649e-117">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2649e-117">Click New.</span></span>
3. <span data-ttu-id="2649e-118">Nel campo ID spese accessorie hub digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2649e-118">In the Hub accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="2649e-119">Nel campo Hub fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2649e-119">In the Hub field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="2649e-120">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="2649e-120">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="2649e-121">Selezionare un'opzione nel campo Posizione hub.</span><span class="sxs-lookup"><span data-stu-id="2649e-121">In the Hub position field, select an option.</span></span>
    * <span data-ttu-id="2649e-122">È possibile creare la spesa come spesa di prelievo o di consegna.</span><span class="sxs-lookup"><span data-stu-id="2649e-122">You can either create the charge as a pickup or drop-off.</span></span> <span data-ttu-id="2649e-123">A seconda della selezione, la spesa verrà applicata al segmento di trasporto corrispondente nel percorso.</span><span class="sxs-lookup"><span data-stu-id="2649e-123">Depending on your selection the charge will be applied to the corresponding transportation segment on your route.</span></span>  
7. <span data-ttu-id="2649e-124">Nel campo Spese accessorie principali fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2649e-124">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="2649e-125">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2649e-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2649e-126">Selezionare i dati master creati.</span><span class="sxs-lookup"><span data-stu-id="2649e-126">Select the master you just created.</span></span>  
9. <span data-ttu-id="2649e-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2649e-127">Click Save.</span></span>
10. <span data-ttu-id="2649e-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2649e-128">Close the page.</span></span>

