--- 
title: Configurare i diritti di accesso per un controller oggetto di costo
description: Utilizzare questa procedura per configurare i diritti di accesso per un controller oggetto di costo.
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b0647e1ec55d23607d07f38105e42af498ad1174
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="configure-access-rights-for-a-cost-object-controller"></a><span data-ttu-id="a32e8-103">Configurare i diritti di accesso per un controller oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a32e8-103">Configure access rights for a cost object controller</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a32e8-104">Utilizzare questa procedura per configurare i diritti di accesso per un controller oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="a32e8-104">Use this procedure to configure access rights for a cost object controller.</span></span> <span data-ttu-id="a32e8-105">Questa registrazione utilizza i dati dimostrativi della società USP2.</span><span class="sxs-lookup"><span data-stu-id="a32e8-105">This recording uses the USP2 demo data company.</span></span>


## <a name="assign-the-cost-object-controller-role"></a><span data-ttu-id="a32e8-106">Assegnare il ruolo di controller oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="a32e8-106">Assign the cost object controller role</span></span>
1. <span data-ttu-id="a32e8-107">Andare a Amministrazione sistema > Utenti > Utenti.</span><span class="sxs-lookup"><span data-stu-id="a32e8-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="a32e8-108">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="a32e8-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="a32e8-109">Ad esempio, filtrare il campo Nome utente in base al valore "alicia".</span><span class="sxs-lookup"><span data-stu-id="a32e8-109">For example, filter on the User name field with a value of 'alicia'.</span></span>
3. <span data-ttu-id="a32e8-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a32e8-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a32e8-111">Fare clic su Assegna ruoli.</span><span class="sxs-lookup"><span data-stu-id="a32e8-111">Click Assign roles.</span></span>
5. <span data-ttu-id="a32e8-112">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="a32e8-112">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="a32e8-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a32e8-113">Click OK.</span></span>

## <a name="enable-access-list-security"></a><span data-ttu-id="a32e8-114">Abilitare la sicurezza dell'elenco di accessi</span><span class="sxs-lookup"><span data-stu-id="a32e8-114">Enable access list security</span></span>
1. <span data-ttu-id="a32e8-115">Andare a Contabilità industriale > Dimensioni > Gerarchie di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="a32e8-115">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="a32e8-116">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="a32e8-116">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a32e8-117">Selezionare Organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a32e8-117">Select Organization.</span></span>  
3. <span data-ttu-id="a32e8-118">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="a32e8-118">Click Edit.</span></span>
4. <span data-ttu-id="a32e8-119">Selezionare Sì nel campo Gerarchia elenco accessi.</span><span class="sxs-lookup"><span data-stu-id="a32e8-119">Select Yes in the Access list hierarchy field.</span></span>
5. <span data-ttu-id="a32e8-120">Fare clic su Visualizza gerarchia.</span><span class="sxs-lookup"><span data-stu-id="a32e8-120">Click View hierarchy.</span></span>

## <a name="assign-access-rights-to-user"></a><span data-ttu-id="a32e8-121">Assegnare i diritti di accesso all'utente</span><span class="sxs-lookup"><span data-stu-id="a32e8-121">Assign access rights to user</span></span>
1. <span data-ttu-id="a32e8-122">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a32e8-122">Click New.</span></span>
2. <span data-ttu-id="a32e8-123">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a32e8-123">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="a32e8-124">Nel campo ID utente, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a32e8-124">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="a32e8-125">Selezionare Amministratore.</span><span class="sxs-lookup"><span data-stu-id="a32e8-125">Select Admin.</span></span>  
4. <span data-ttu-id="a32e8-126">Nella struttura selezionare "Organization\CEO\CFO\FIM".</span><span class="sxs-lookup"><span data-stu-id="a32e8-126">In the tree, select 'Organization\CEO\CFO\FIM'.</span></span>
5. <span data-ttu-id="a32e8-127">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a32e8-127">Click New.</span></span>
6. <span data-ttu-id="a32e8-128">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a32e8-128">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="a32e8-129">Nel campo ID utente, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a32e8-129">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="a32e8-130">Selezionare Alicia.</span><span class="sxs-lookup"><span data-stu-id="a32e8-130">Select Alicia.</span></span>  
8. <span data-ttu-id="a32e8-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a32e8-131">Click Save.</span></span>

## <a name="enable-access-rights-in-cost-accounting"></a><span data-ttu-id="a32e8-132">Abilitare i diritti di accesso nella contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="a32e8-132">Enable access rights in Cost accounting</span></span>
1. <span data-ttu-id="a32e8-133">Andare a Contabilità industriale > Impostazioni > Parametri.</span><span class="sxs-lookup"><span data-stu-id="a32e8-133">Go to Cost accounting > Setup > Parameters.</span></span>
2. <span data-ttu-id="a32e8-134">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="a32e8-134">Click the General tab.</span></span>
3. <span data-ttu-id="a32e8-135">Selezionare Sì nel campo Abilita accesso in visualizzazione per membri di dimensione oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="a32e8-135">Select Yes in the Enable view access for cost object dimension members field.</span></span>
4. <span data-ttu-id="a32e8-136">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a32e8-136">Click Save.</span></span>
5. <span data-ttu-id="a32e8-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a32e8-137">Close the page.</span></span>
6. <span data-ttu-id="a32e8-138">Andare a Contabilità industriale > Impostazioni > Configurazione area di lavoro controllo costi.</span><span class="sxs-lookup"><span data-stu-id="a32e8-138">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
7. <span data-ttu-id="a32e8-139">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="a32e8-139">Click Edit.</span></span>
8. <span data-ttu-id="a32e8-140">Selezionare Sì nel campo Pubblicato.</span><span class="sxs-lookup"><span data-stu-id="a32e8-140">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="a32e8-141">Se si seleziona Sì, gli utenti assegnati a uno di questi quattro ruoli possono visualizzare il report nell'area di lavoro di controllo costi: responsabile della contabilità industriale, contabile, addetto alla contabilità e controller oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="a32e8-141">If you select Yes, a user who is assigned one of the following four roles can see the reports in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, and cost object controller.</span></span> <span data-ttu-id="a32e8-142">Se si seleziona No, solo un utente assegnato a uno di questi ruoli può visualizzare il report nell'area di lavoro di controllo costi: responsabile della contabilità industriale, contabile e addetto alla contabilità.</span><span class="sxs-lookup"><span data-stu-id="a32e8-142">If you select No, only a user who is assigned one of the following roles can see the reports: cost accounting manager, cost accountant, and cost accountant clerk.</span></span>    
9. <span data-ttu-id="a32e8-143">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a32e8-143">Click Save.</span></span>

