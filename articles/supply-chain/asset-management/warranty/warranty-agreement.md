---
title: Contratti di garanzia
description: In questo argomento vengono descritti i contratti di garanzia in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 71905d5b362c80d48b78210b59cacfb1e7899757
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874695"
---
# <a name="warranty-agreements"></a><span data-ttu-id="b2968-103">Contratti di garanzia</span><span class="sxs-lookup"><span data-stu-id="b2968-103">Warranty agreements</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="b2968-104">In Gestione cespiti, è possibile impostare i termini di garanzia che possono essere associati a un cespite o a un tipo di cespite.</span><span class="sxs-lookup"><span data-stu-id="b2968-104">In Asset Management, you can set up warranty terms that can be connected to an asset or an asset type.</span></span> <span data-ttu-id="b2968-105">I termini di garanzia vengono creati per un periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="b2968-105">Warranty terms are created for a specific period.</span></span> <span data-ttu-id="b2968-106">La garanzia può essere impostata per fornire una copertura totale o parziale ed è possibile impostare i termini relativi a ore, spese e articoli.</span><span class="sxs-lookup"><span data-stu-id="b2968-106">Warranty can be set up to provide full coverage or partial coverage, and you can set up terms that are related to hours, expenses, and items.</span></span>

<span data-ttu-id="b2968-107">Il primo passo consiste nel creare tutti i contratti di garanzia fornitore relativi all'attrezzatura aziendale.</span><span class="sxs-lookup"><span data-stu-id="b2968-107">The first step is to create any vendor warranty agreements that you have for your equipment.</span></span> <span data-ttu-id="b2968-108">Successivamente, si associano i contratti di garanzia a cespiti o tipi di cespite.</span><span class="sxs-lookup"><span data-stu-id="b2968-108">You then attach warranty agreements to assets or asset types.</span></span> <span data-ttu-id="b2968-109">I contratti di garanzia fornitore vengono utilizzati solo a scopo informativo.</span><span class="sxs-lookup"><span data-stu-id="b2968-109">Vendor warranty agreements are used only for informational purposes.</span></span> <span data-ttu-id="b2968-110">Se la garanzia fornitore viene impostata in un cespite, è possibile visualizzare il periodo di copertura della garanzia nel cespite.</span><span class="sxs-lookup"><span data-stu-id="b2968-110">If vendor warranty is set up on an asset, you can see the warranty coverage period on the asset.</span></span>

## <a name="create-a-warranty-agreement"></a><span data-ttu-id="b2968-111">Creare un contratto di garanzia</span><span class="sxs-lookup"><span data-stu-id="b2968-111">Create a warranty agreement</span></span>

<span data-ttu-id="b2968-112">Un contratto di garanzia può includere varie righe del contratto per coprire la garanzia relativa a ore, spese e articoli.</span><span class="sxs-lookup"><span data-stu-id="b2968-112">A warranty agreement can include several agreement lines to cover the warranty for work hours, expenses, and items.</span></span>

1. <span data-ttu-id="b2968-113">Selezionare **Gestione cespiti** \> **Impostazione** \> **Cespiti** \>**Garanzia**.</span><span class="sxs-lookup"><span data-stu-id="b2968-113">Select **Asset management** \> **Setup** \> **Assets** \> **Warranty**.</span></span>
2. <span data-ttu-id="b2968-114">Selezionare **Nuovo** per creare un prodotto.</span><span class="sxs-lookup"><span data-stu-id="b2968-114">Select **New** to create a product.</span></span>
3. <span data-ttu-id="b2968-115">Nel campo **Garanzia**, immettere un ID garanzia.</span><span class="sxs-lookup"><span data-stu-id="b2968-115">In the **Warranty** field, enter a warranty ID.</span></span>
4. <span data-ttu-id="b2968-116">Nel campo **Nome** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="b2968-116">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="b2968-117">Nella Scheda dettaglio **Dettagli**, il campo **Cespiti** visualizza il numero di cespiti attivi che utilizzano il contratto di garanzia.</span><span class="sxs-lookup"><span data-stu-id="b2968-117">On the **Details** FastTab, the **Assets** field shows the number of active assets that use the warranty agreement.</span></span>

5. <span data-ttu-id="b2968-118">Nelle Schede dettaglio **Garanzia ore** e **Garanzia articoli**, seguire questi passaggi per aggiungere righe che devono essere incluse in un contratto di garanzia relativo a ore o articoli:</span><span class="sxs-lookup"><span data-stu-id="b2968-118">On the **Hour warranty** and **Item warranty** FastTabs, follow these steps to add lines that should be included in a warranty agreement that pertains to hours or items:</span></span>

    1. <span data-ttu-id="b2968-119">Selezionare **Aggiungi riga** per aggiungere una nuova condizione alla garanzia.</span><span class="sxs-lookup"><span data-stu-id="b2968-119">Select **Add line** to add a new condition to the warranty.</span></span> <span data-ttu-id="b2968-120">Un numero di riga sequenziale viene immesso automaticamente nel campo **Riga**.</span><span class="sxs-lookup"><span data-stu-id="b2968-120">A sequential line number is automatically entered in the **Line** field.</span></span>
    2. <span data-ttu-id="b2968-121">Nel campo **Periodo** selezionare il tipo di periodo di garanzia.</span><span class="sxs-lookup"><span data-stu-id="b2968-121">In the **Period** field, select the type of warranty period.</span></span>
    3. <span data-ttu-id="b2968-122">Nel campo **Intervallo** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="b2968-122">In the **Interval** field, enter a number.</span></span> <span data-ttu-id="b2968-123">Questo campo definisce il numero di periodi per i quali la garanzia deve essere valida.</span><span class="sxs-lookup"><span data-stu-id="b2968-123">This field defines the number of periods that the warranty should be valid for.</span></span>
    4. <span data-ttu-id="b2968-124">Nel campo **Percentuale**, immettere la percentuale di copertura per la riga della garanzia.</span><span class="sxs-lookup"><span data-stu-id="b2968-124">In the **Percent** field, enter the coverage percentage for the warranty line.</span></span> <span data-ttu-id="b2968-125">La percentuale indica quanto è coperto dalla società.</span><span class="sxs-lookup"><span data-stu-id="b2968-125">The percentage indicates how much is covered by your company.</span></span>

![Figura 1](media/01-warranty.png)
