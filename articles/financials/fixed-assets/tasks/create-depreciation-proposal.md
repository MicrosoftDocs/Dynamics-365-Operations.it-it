---
title: Crea proposta di ammortamento
description: In questa procedura viene descritto come le proposte di ammortamento batch vengono eseguite e viene illustrato come proporre l'ammortamento per i cespiti.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: d11554ee5f26ef5a85e799194d2f75757a31c254
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---

# <a name="create-depreciation-proposal"></a><span data-ttu-id="08b4c-103">Crea proposta di ammortamento</span><span class="sxs-lookup"><span data-stu-id="08b4c-103">Create depreciation proposal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="08b4c-104">In questa procedura viene descritto come le proposte di ammortamento batch vengono eseguite e viene illustrato come proporre l'ammortamento per i cespiti.</span><span class="sxs-lookup"><span data-stu-id="08b4c-104">This procedure describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="08b4c-105">In questa attività viene utilizzata la società dimostrativa USMF e il ruolo Ragioniere.</span><span class="sxs-lookup"><span data-stu-id="08b4c-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-depreciation-proposal"></a><span data-ttu-id="08b4c-106">Crea proposta di ammortamento</span><span class="sxs-lookup"><span data-stu-id="08b4c-106">Create depreciation proposal</span></span>
1. <span data-ttu-id="08b4c-107">Andare a Cespiti > Scritture contabili > Crea proposta di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="08b4c-107">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="08b4c-108">Nel campo Nome giornale di registrazione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="08b4c-108">In the Name of journal field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="08b4c-109">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="08b4c-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="08b4c-110">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="08b4c-110">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="08b4c-111">Selezionare l'opzione Riepilogo ammortamento per riepilogare gli ammortamenti mensili in una riga del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="08b4c-111">Select the Summarize depreciation option to summarize monthly depreciations into one journal line.</span></span>  
    * <span data-ttu-id="08b4c-112">Ad esempio, se il valore di Data finale è il 31 marzo 2015, è possibile che venga generata la seguente descrizione: "Ammortamento dal 31 gennaio 2015".</span><span class="sxs-lookup"><span data-stu-id="08b4c-112">For example, if the To date value is March 31, 2015, the following description is generated: “Depreciation since January 31, 2015.”</span></span> <span data-ttu-id="08b4c-113">Il campo Data nelle righe proposte del giornale di registrazione verrà quindi impostato su 31 marzo 2015.</span><span class="sxs-lookup"><span data-stu-id="08b4c-113">The Date field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    * <span data-ttu-id="08b4c-114">La proposta di ammortamento può essere filtrata per cespite, gruppo cespite o altri criteri utilizzando l'opzione Filtro.</span><span class="sxs-lookup"><span data-stu-id="08b4c-114">The depreciation proposal can be filtered by asset, asset group, or other criteria using the Filter option.</span></span>  
    * <span data-ttu-id="08b4c-115">Quando si utilizza Crea proposte di acquisizione o ammortamento per il modulo cespiti, è possibile proporre l'ammortamento in batch.</span><span class="sxs-lookup"><span data-stu-id="08b4c-115">When you use the Create acquisition or depreciation proposals for fixed assets form, you can propose depreciation in batches.</span></span> <span data-ttu-id="08b4c-116">Si consiglia questa procedura per le proposte di dimensioni più grandi che utilizzeranno più risorse di sistema.</span><span class="sxs-lookup"><span data-stu-id="08b4c-116">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="08b4c-117">Se si seleziona l'opzione batch, è comunque possibile completare altre attività durante tale periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="08b4c-117">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="08b4c-118">Quando si propone l'ammortamento in questo modo, l'ammortamento viene calcolato per i modelli di valore dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="08b4c-118">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  
5. <span data-ttu-id="08b4c-119">Fare clic su Crea giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="08b4c-119">Click Create journal.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="08b4c-120">Verificare voci di ammortamento</span><span class="sxs-lookup"><span data-stu-id="08b4c-120">Review depreciation entries</span></span>
1. <span data-ttu-id="08b4c-121">Andare a Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="08b4c-121">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="08b4c-122">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="08b4c-122">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="08b4c-123">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="08b4c-123">Click Lines.</span></span>
4. <span data-ttu-id="08b4c-124">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="08b4c-124">Click Post.</span></span>


