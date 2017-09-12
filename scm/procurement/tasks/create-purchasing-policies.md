--- 
title: Creazione di criteri di acquisto
description: Questa procedura vi mostra come creare criteri acquisto da allineare con i vostri processi aziendali per acquistare.
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c2b3a66443394f5bfbe51b6685513281025d68fd
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-purchasing-policies"></a><span data-ttu-id="4348c-103">Creazione di criteri di acquisto</span><span class="sxs-lookup"><span data-stu-id="4348c-103">Create purchasing policies</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4348c-104">Questa procedura vi mostra come creare criteri acquisto da allineare con i vostri processi aziendali per acquistare.</span><span class="sxs-lookup"><span data-stu-id="4348c-104">This procedure shows you how to create purchasing policies to align with your business processes for purchasing.</span></span> <span data-ttu-id="4348c-105">Prima di creare criteri di acquisto, è necessario impostare i parametri dei criteri di acquisto.</span><span class="sxs-lookup"><span data-stu-id="4348c-105">Before you can create purchasing policies, you must set up the purchasing policy parameters.</span></span> <span data-ttu-id="4348c-106">È possibile creare, modificare e ritirare criteri di acquisto, ma non eliminarli.</span><span class="sxs-lookup"><span data-stu-id="4348c-106">It’s possible to create, modify, and retire a purchasing policy, but you can’t delete a purchasing policy.</span></span> <span data-ttu-id="4348c-107">In genere questa procedura sarà svolta da un responsabile acquisti.</span><span class="sxs-lookup"><span data-stu-id="4348c-107">This procedure would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="4348c-108">È necessario impostare le classificazioni del contratto di acquisto prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="4348c-108">You can use this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-policy-parameters"></a><span data-ttu-id="4348c-109">Impostazione dei parametri di criteri</span><span class="sxs-lookup"><span data-stu-id="4348c-109">Set up policy parameters</span></span>
1. <span data-ttu-id="4348c-110">Andare a Criteri di acquisto.</span><span class="sxs-lookup"><span data-stu-id="4348c-110">Go to Purchasing policies.</span></span>
2. <span data-ttu-id="4348c-111">Fare clic su Parametri.</span><span class="sxs-lookup"><span data-stu-id="4348c-111">Click Parameters.</span></span>
    * <span data-ttu-id="4348c-112">Le regole di precedenza dei criteri si applicano ai livelli differenti nella vostra organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4348c-112">Policy precedence rules apply to different levels in your organization.</span></span> <span data-ttu-id="4348c-113">Le unità organizzative visualizzate dipendono dalla vostra gerarchia organizzativa e da a quali livelli nella gerarchia è stato assegnato lo scopo di controllo interno di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="4348c-113">The organizational units that are shown depend on your organizational hierarchy, and on which levels in the hierarchy have been assigned the purpose of Procurement internal control.</span></span> <span data-ttu-id="4348c-114">Per esempio, la vostra organizzazione potrebbe avere persone giuridiche, centri di costo, regioni e reparti, ma può essere che soltanto alcuni di questi abbiano uno scopo di gerarchia di controllo interno di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="4348c-114">For example, your organization might have legal entities, cost centers, regions, and departments, but it may be that only some of these have a hierarchy purpose of Procurement internal control.</span></span> <span data-ttu-id="4348c-115">Come impostazione predefinita, l'organizzazione di tipo Società è disponibile.</span><span class="sxs-lookup"><span data-stu-id="4348c-115">As a default, the organization of type Company is available.</span></span>  
3. <span data-ttu-id="4348c-116">Fare clic sulla scheda Parametri tipo di regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="4348c-116">Click the Policy rule type parameters tab.</span></span>
4. <span data-ttu-id="4348c-117">Nella struttura, selezionare 'Regola di controllo criteri di acquisto/richiesta di acquisto'.</span><span class="sxs-lookup"><span data-stu-id="4348c-117">In the tree, select 'Purchasing policy\Purchase requisition control rule'.</span></span>
    * <span data-ttu-id="4348c-118">L'ordine di precedenza per la risoluzione dei criteri viene definito a livello dei criteri.</span><span class="sxs-lookup"><span data-stu-id="4348c-118">You define the order of precedence for policy resolution at the policy level.</span></span> <span data-ttu-id="4348c-119">Tuttavia, per alcuni tipi di criteri è possibile sostituire l'ordine di precedenza per singoli tipi di regole dei criteri.</span><span class="sxs-lookup"><span data-stu-id="4348c-119">However, for some policy types, you can override the order of precedence for individual policy rule types.</span></span> <span data-ttu-id="4348c-120">Per esempio, potreste definire l'ordine di precedenza affinchè i criteri di acquisto siano: centro di costo, reparto, società.</span><span class="sxs-lookup"><span data-stu-id="4348c-120">For example, you might define the order of precedence for purchasing policies to be: cost center, department, company.</span></span> <span data-ttu-id="4348c-121">Per la regola dei criteri di catalogo l'ordine di precedenza potrebbe essere il seguente: reparto, centro di costo, società.</span><span class="sxs-lookup"><span data-stu-id="4348c-121">For the catalog policy rule, you might want the order of precedence to be: department, cost center, company.</span></span> <span data-ttu-id="4348c-122">È possibile modificare l'ordine di precedenza per la regola dei criteri di catalogo.</span><span class="sxs-lookup"><span data-stu-id="4348c-122">You can change the order of precedence for the Catalog policy rule.</span></span> <span data-ttu-id="4348c-123">Quando un lavoratore crea una richiesta, il catalogo che viene visualizzato varia in base ai criteri associati al reparto del lavoratore, al centro di costo e infine alla società.</span><span class="sxs-lookup"><span data-stu-id="4348c-123">When a worker creates a requisition, the catalog that is displayed is determined by the policies that are associated with the worker’s department, then their cost center, and then their company.</span></span>  
    * <span data-ttu-id="4348c-124">Se c'è più di un livello organizzativo elencato, potete usare le frecce su/giù per impostare l'ordine di precedenza per la regola di controllo di richiesta di acquisto.</span><span class="sxs-lookup"><span data-stu-id="4348c-124">If there’s more than one organizational level listed, you can use the Up/Down arrows to set the order of precedence for the Purchase requisition control rule.</span></span>  
5. <span data-ttu-id="4348c-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4348c-125">Close the page.</span></span>

## <a name="create-a-new-policy"></a><span data-ttu-id="4348c-126">Crea nuovi criteri</span><span class="sxs-lookup"><span data-stu-id="4348c-126">Create a new policy</span></span>
1. <span data-ttu-id="4348c-127">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4348c-127">Click New.</span></span>
2. <span data-ttu-id="4348c-128">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="4348c-128">In the Name field, type a value.</span></span>
3. <span data-ttu-id="4348c-129">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="4348c-129">In the Description field, type a value.</span></span>
    * <span data-ttu-id="4348c-130">I singoli criteri di acquisto possono solo essere applicati a una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="4348c-130">A single purchasing policy can only apply to one organization hierarchy.</span></span> <span data-ttu-id="4348c-131">Per esempio, potreste avere una gerarchia chiamata "Geografica" e una "Reparto" e avere criteri di acquisto diversi per ciascuna.</span><span class="sxs-lookup"><span data-stu-id="4348c-131">For example, you could have one hierarchy called “Geographic” and one called “Department”, and have a different purchasing policy for each.</span></span>  
    * <span data-ttu-id="4348c-132">Selezionare un'organizzazione a cui il criterio dovrebbe applicarsi.</span><span class="sxs-lookup"><span data-stu-id="4348c-132">Select an organization that the policy should apply to.</span></span>  
4. <span data-ttu-id="4348c-133">Fare clic sulla freccia per aggiungere l'organizzazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="4348c-133">Click the arrow to add the selected organization.</span></span>
    * <span data-ttu-id="4348c-134">Potete ripetere questo processo per aggiungere più organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4348c-134">You can repeat this process to add more organizations.</span></span>  

## <a name="add-a-policy-rule"></a><span data-ttu-id="4348c-135">Aggiungere una regola dei criteri</span><span class="sxs-lookup"><span data-stu-id="4348c-135">Add a policy rule</span></span>
1. <span data-ttu-id="4348c-136">Nell'elenco Tipo di regola dei criteri, selezionare Regola scopo richiesta.</span><span class="sxs-lookup"><span data-stu-id="4348c-136">In the Policy rule type list, select Requisition purpose rule.</span></span>
    * <span data-ttu-id="4348c-137">Creerete una regola che fissa lo scopo richiesta predefinito sul tipo Consumo ma che permette che il tipo Rifornimento sia selezionato invece.</span><span class="sxs-lookup"><span data-stu-id="4348c-137">You’ll create a rule that sets the default requisition purpose to type Consumption but allows the Replenishment type to be selected instead.</span></span>  
2. <span data-ttu-id="4348c-138">Fare clic su Crea regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="4348c-138">Click Create policy rule.</span></span>
3. <span data-ttu-id="4348c-139">Selezionare Sì nel campo Consenti forzatura manuale.</span><span class="sxs-lookup"><span data-stu-id="4348c-139">Select Yes in the Allow manual override field.</span></span>
4. <span data-ttu-id="4348c-140">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="4348c-140">Click Close.</span></span>
    * <span data-ttu-id="4348c-141">Ora è possibile impostare altre regole dei criteri per i criteri di acquisto.</span><span class="sxs-lookup"><span data-stu-id="4348c-141">Now you can set up other policy rules for the purchasing policy.</span></span>   <span data-ttu-id="4348c-142">Si noti che un tipo di regola di criteri non può avere regole sovrapposte attive allo stesso tempo all'interno di un singolo criterio di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="4348c-142">Note that a Policy rule type cannot have overlapping rules that are active at the same time within a single procurement policy.</span></span>  
5. <span data-ttu-id="4348c-143">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4348c-143">Close the page.</span></span>
6. <span data-ttu-id="4348c-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4348c-144">Close the page.</span></span>


