--- 
title: "Calcolare l'ammortamento del cespite tra più persone giuridiche"
description: In questa procedura viene illustrato come impostare ed eseguire il processo di ammortamento per molteplici persone giuridiche.
author: saraschi2
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d804480167414cd038f8229db312dc9c52d131f8
ms.openlocfilehash: 4c45da124136b7fecb916d2ff9098c8ffeff6cb1
ms.contentlocale: it-it
ms.lasthandoff: 11/02/2017

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="b36c1-103">Calcolare l'ammortamento del cespite tra più persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="b36c1-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b36c1-104">L'ammortamento del cespite può essere eseguito tra persone giuridiche in un unico passaggio.</span><span class="sxs-lookup"><span data-stu-id="b36c1-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="b36c1-105">In questa procedura viene illustrato come impostare ed eseguire il processo per molteplici persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="b36c1-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="b36c1-106">Viene utilizzato il ruolo Ragioniere.</span><span class="sxs-lookup"><span data-stu-id="b36c1-106">It uses the accountant role.</span></span>  

<span data-ttu-id="b36c1-107">Questa registrazione utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="b36c1-107">This recording uses the USMF demo company.</span></span>


<span data-ttu-id="b36c1-108">Sottoattività in 16 passaggi: impostare i giornali di registrazione per l'esecuzione dell'ammortamento interaziendale.</span><span class="sxs-lookup"><span data-stu-id="b36c1-108">Steps (16) Sub-task: Set up cross company depreciation run journals.</span></span> 

1. <span data-ttu-id="b36c1-109">Innanzitutto, è necessario impostare i giornali di registrazione da utilizzare nell'esecuzione dell'ammortamento interaziendale in ogni persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="b36c1-109">First, you must set up the journals to be used in the cross company depreciation run in each legal entity.</span></span> <span data-ttu-id="b36c1-110">Passare a Cespiti > Impostazione > Parametri cespiti.</span><span class="sxs-lookup"><span data-stu-id="b36c1-110">Go to Fixed assets > Setup > Fixed assets parameters.</span></span> 
2. <span data-ttu-id="b36c1-111">Espandere l'area Proposte di cespite.</span><span class="sxs-lookup"><span data-stu-id="b36c1-111">Expand the Fixed asset proposals section.</span></span> 
3. <span data-ttu-id="b36c1-112">Creare un record con il nome del giornale di registrazione da utilizzare per ciascun livello di registrazione nella persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="b36c1-112">Create a record with the journal name to be used for each posting layer in the legal entity.</span></span> <span data-ttu-id="b36c1-113">Se i registri non vengono registrati nella contabilità generale, il livello di registrazione Nessuno deve essere selezionato con il giornale di registrazione associato.</span><span class="sxs-lookup"><span data-stu-id="b36c1-113">If books do not post to the general ledger, then the None posting layer should be selected with the associated journal.</span></span> <span data-ttu-id="b36c1-114">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="b36c1-114">Click Add.</span></span> 
4. <span data-ttu-id="b36c1-115">Nel campo Livello registrazione, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b36c1-115">In the Posting layer field, enter or select a value.</span></span> 
5. <span data-ttu-id="b36c1-116">Nel campo Nome giornale di registrazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b36c1-116">In the Journal name field, enter or select a value.</span></span> 
6. <span data-ttu-id="b36c1-117">Ripetere l'impostazione del giornale di registrazione nella pagina Parametri Cespiti in ogni persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="b36c1-117">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span> 

<span data-ttu-id="b36c1-118">Sottoattività: calcolare l'ammortamento</span><span class="sxs-lookup"><span data-stu-id="b36c1-118">Sub-task: Calculate depreciation</span></span>

1. <span data-ttu-id="b36c1-119">Utilizzare la pagina Crea proposta di ammortamento per iniziare l'esecuzione dell'ammortamento tra le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="b36c1-119">Use the Create depreciation proposal page to start your depreciation run across legal entities.</span></span> <span data-ttu-id="b36c1-120">Andare a Cespiti > Scritture contabili > Crea proposta di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="b36c1-120">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span> 
2. <span data-ttu-id="b36c1-121">Nel campo Livello registrazione, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b36c1-121">In the Posting layer field, enter or select a value.</span></span> 
3. <span data-ttu-id="b36c1-122">Per impostazione predefinita, il nome del giornale di registrazione è quello indicato in Parametri Cespiti.</span><span class="sxs-lookup"><span data-stu-id="b36c1-122">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="b36c1-123">Può essere modificato qui per la persona giuridica corrente.</span><span class="sxs-lookup"><span data-stu-id="b36c1-123">It can be changed here for the current legal entity.</span></span> 
4. <span data-ttu-id="b36c1-124">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="b36c1-124">In the To date field, enter a date.</span></span> 
5. <span data-ttu-id="b36c1-125">Selezionare le persone giuridiche da includere nell'esecuzione dell'ammortamento.</span><span class="sxs-lookup"><span data-stu-id="b36c1-125">Select the legal entities to be included in the depreciation run.</span></span> <span data-ttu-id="b36c1-126">Solo le persone giuridiche con giornali di registrazione impostati per le proposte cespite nella pagina Parametri Cespiti verranno visualizzate nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b36c1-126">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span> 
6. <span data-ttu-id="b36c1-127">Quando attivata, l'opzione Registra giornali registrerà automaticamente i giornali di registrazione ammortamento quando vengono creati.</span><span class="sxs-lookup"><span data-stu-id="b36c1-127">When enabled, the Post journals option will automatically post the depreciation journals when they are created.</span></span> <span data-ttu-id="b36c1-128">Se non è selezionata, i giornali di registrazione verranno creati, ma non registrati, di modo che sia possibile esaminare i dettagli prima della registrazione.</span><span class="sxs-lookup"><span data-stu-id="b36c1-128">When not selected, the journals will be created, but not posted, so you can review the details before posting.</span></span> <span data-ttu-id="b36c1-129">Selezionare Sì nel campo Registra giornali.</span><span class="sxs-lookup"><span data-stu-id="b36c1-129">Select Yes in the Post journals field.</span></span> 
7. <span data-ttu-id="b36c1-130">I campi di filtro includono cespiti, gruppi e registri per le persone giuridiche selezionate per questa esecuzione dell'ammortamento.</span><span class="sxs-lookup"><span data-stu-id="b36c1-130">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span> 
8. <span data-ttu-id="b36c1-131">L'opzione Elaborazione batch è attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b36c1-131">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="b36c1-132">Quando questa opzione è attivata, la creazione e la registrazione del giornale di registrazione ammortamento vengono eseguite in background.</span><span class="sxs-lookup"><span data-stu-id="b36c1-132">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span> 
9. <span data-ttu-id="b36c1-133">Fare clic su Crea giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="b36c1-133">Click Create journal.</span></span> 
10. <span data-ttu-id="b36c1-134">È necessario visualizzare i giornali di registrazione ammortamento creati nelle rispettive persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="b36c1-134">You must view the depreciation journals created in the respective legal entities.</span></span> <span data-ttu-id="b36c1-135">Andare a Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="b36c1-135">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>

