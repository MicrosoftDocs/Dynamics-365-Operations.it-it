---
title: Creare una proposta di ammortamento
description: In questo argomento viene descritto come le proposte di ammortamento batch vengono eseguite e viene illustrato come proporre l'ammortamento per i cespiti.
author: abruer
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 90c24e9d89c055ea95ca5f25cd85ef4042476a90
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187063"
---
# <a name="create-a-depreciation-proposal"></a><span data-ttu-id="cc1ee-103">Creare una proposta di ammortamento</span><span class="sxs-lookup"><span data-stu-id="cc1ee-103">Create a depreciation proposal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cc1ee-104">In questo argomento viene descritto come le proposte di ammortamento batch vengono eseguite e viene illustrato come proporre l'ammortamento per i cespiti.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-104">This topic describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="cc1ee-105">In questa attività viene utilizzata la società dimostrativa USMF e il ruolo Ragioniere.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-a-depreciation-proposal"></a><span data-ttu-id="cc1ee-106">Creare una proposta di ammortamento</span><span class="sxs-lookup"><span data-stu-id="cc1ee-106">Create a depreciation proposal</span></span>
1. <span data-ttu-id="cc1ee-107">Nel pannello di navigazione, andare a **Moduli > Cespiti > Scritture contabili > Crea proposta di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Create depreciation proposal**.</span></span>
2. <span data-ttu-id="cc1ee-108">Nel campo **Nome giornale di registrazione**, selezionare un'opzione dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-108">In the **Name of journal** field, select an option from the drop-down menu.</span></span>
3. <span data-ttu-id="cc1ee-109">Nel campo **Al** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-109">In the **To date** field, enter a date.</span></span>

    - <span data-ttu-id="cc1ee-110">Selezionare l'opzione **Riepilogo ammortamento** per riepilogare gli ammortamenti mensili in una riga del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-110">Select the **Summarize depreciation** option to summarize monthly depreciations into one journal line.</span></span>  
    - <span data-ttu-id="cc1ee-111">Ad esempio, se il valore di Data finale è il 31 marzo 2015, è possibile che venga generata la seguente descrizione: "Ammortamento dal 31 gennaio 2015".</span><span class="sxs-lookup"><span data-stu-id="cc1ee-111">For example, if the To date value is March 31, 2015, the following description is generated: “Depreciation since January 31, 2015.”</span></span> <span data-ttu-id="cc1ee-112">Il campo **Data** nelle righe proposte del giornale di registrazione verrà quindi impostato su 31 marzo 2015.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-112">The **Date** field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    - <span data-ttu-id="cc1ee-113">La proposta di ammortamento può essere filtrata per cespite, gruppo cespite o altri criteri utilizzando l'opzione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-113">The depreciation proposal can be filtered by asset, asset group, or other criteria using the **Filter** option.</span></span>  
    - <span data-ttu-id="cc1ee-114">Quando si utilizza **Crea proposte di acquisizione o ammortamento per il modulo cespiti**, è possibile proporre l'ammortamento in batch.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-114">When you use the **Create acquisition or depreciation proposals for fixed assets** form, you can propose depreciation in batches.</span></span> <span data-ttu-id="cc1ee-115">Si consiglia questa procedura per le proposte di dimensioni più grandi che utilizzeranno più risorse di sistema.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-115">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="cc1ee-116">Se si seleziona l'opzione batch, è comunque possibile completare altre attività durante tale periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-116">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="cc1ee-117">Quando si propone l'ammortamento in questo modo, l'ammortamento viene calcolato per i modelli di valore dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-117">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  

4. <span data-ttu-id="cc1ee-118">Selezionare **Crea giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-118">Select **Create journal**.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="cc1ee-119">Verificare voci di ammortamento</span><span class="sxs-lookup"><span data-stu-id="cc1ee-119">Review depreciation entries</span></span>
1. <span data-ttu-id="cc1ee-120">Nel pannello di navigazione, andare a **Moduli > Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti**.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-120">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="cc1ee-121">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-121">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="cc1ee-122">Selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-122">Select **Lines**.</span></span>
4. <span data-ttu-id="cc1ee-123">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="cc1ee-123">Select **Post**.</span></span>

