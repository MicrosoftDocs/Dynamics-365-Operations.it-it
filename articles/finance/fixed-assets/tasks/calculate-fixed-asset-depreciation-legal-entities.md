---
title: Calcolare l'ammortamento del cespite tra più persone giuridiche
description: L'ammortamento del cespite può essere eseguito tra persone giuridiche in un unico passaggio.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d228c387e8a6bf956f729a69e2296130db32dbd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210049"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="1ae21-103">Calcolare l'ammortamento del cespite tra più persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="1ae21-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1ae21-104">L'ammortamento del cespite può essere eseguito tra persone giuridiche in un unico passaggio.</span><span class="sxs-lookup"><span data-stu-id="1ae21-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="1ae21-105">In questa procedura viene illustrato come impostare ed eseguire il processo per molteplici persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="1ae21-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="1ae21-106">Utilizza il ruolo Ragioniere e i dati dimostrativi della persona giuridica USMF.</span><span class="sxs-lookup"><span data-stu-id="1ae21-106">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="set-up-cross-company-depreciation-run-journals"></a><span data-ttu-id="1ae21-107">Impostare i giornali di registrazione per l'esecuzione dell'ammortamento interaziendale</span><span class="sxs-lookup"><span data-stu-id="1ae21-107">Set up cross company depreciation run journals</span></span>
1. <span data-ttu-id="1ae21-108">Passare a Cespiti > Impostazione > Parametri cespiti.</span><span class="sxs-lookup"><span data-stu-id="1ae21-108">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="1ae21-109">Espandere l'area Proposte di cespite.</span><span class="sxs-lookup"><span data-stu-id="1ae21-109">Expand the Fixed asset proposals section.</span></span>
3. <span data-ttu-id="1ae21-110">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="1ae21-110">Click Add.</span></span>
4. <span data-ttu-id="1ae21-111">Nel campo Livello registrazione, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1ae21-111">In the Posting layer field, enter or select a value.</span></span>
5. <span data-ttu-id="1ae21-112">Nel campo Nome giornale di registrazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1ae21-112">In the Journal name field, enter or select a value.</span></span>
    * <span data-ttu-id="1ae21-113">Ripetere l'impostazione del giornale di registrazione nella pagina Parametri Cespiti in ogni persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="1ae21-113">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span>  

## <a name="depreciation-run"></a><span data-ttu-id="1ae21-114">Esecuzione ammortamento</span><span class="sxs-lookup"><span data-stu-id="1ae21-114">Depreciation run</span></span>
1. <span data-ttu-id="1ae21-115">Andare a Cespiti > Scritture contabili > Crea proposta di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="1ae21-115">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="1ae21-116">Nel campo Livello registrazione, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1ae21-116">In the Posting layer field, enter or select a value.</span></span>
    * <span data-ttu-id="1ae21-117">Per impostazione predefinita, il nome del giornale di registrazione è quello indicato in Parametri Cespiti.</span><span class="sxs-lookup"><span data-stu-id="1ae21-117">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="1ae21-118">Può essere modificato qui per la persona giuridica corrente.</span><span class="sxs-lookup"><span data-stu-id="1ae21-118">It can be changed here for the current legal entity.</span></span>  
3. <span data-ttu-id="1ae21-119">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="1ae21-119">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="1ae21-120">Selezionare le persone giuridiche da includere nell'esecuzione dell'ammortamento.</span><span class="sxs-lookup"><span data-stu-id="1ae21-120">Select the legal entities to be included in the depreciation run.</span></span>  
    * <span data-ttu-id="1ae21-121">Solo le persone giuridiche con giornali di registrazione impostati per le proposte cespite nella pagina Parametri Cespiti verranno visualizzate nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1ae21-121">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span>  
4. <span data-ttu-id="1ae21-122">Selezionare Sì nel campo Registra giornali.</span><span class="sxs-lookup"><span data-stu-id="1ae21-122">Select Yes in the Post journals field.</span></span>
    * <span data-ttu-id="1ae21-123">I campi di filtro includono cespiti, gruppi e registri per le persone giuridiche selezionate per questa esecuzione dell'ammortamento.</span><span class="sxs-lookup"><span data-stu-id="1ae21-123">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span>  
    * <span data-ttu-id="1ae21-124">L'opzione Elaborazione batch è attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1ae21-124">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="1ae21-125">Quando questa opzione è attivata, la creazione e la registrazione del giornale di registrazione ammortamento vengono eseguite in background.</span><span class="sxs-lookup"><span data-stu-id="1ae21-125">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span>  
5. <span data-ttu-id="1ae21-126">Fare clic su Crea giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="1ae21-126">Click Create journal.</span></span>
6. <span data-ttu-id="1ae21-127">Andare a Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="1ae21-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]