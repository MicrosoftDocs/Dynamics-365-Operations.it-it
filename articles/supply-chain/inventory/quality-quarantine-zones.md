---
title: Aree di quarantena per non conformità
description: Questo argomento descrive come creare e utilizzare aree di quarantena per le non conformità.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80f4b9dfc7882af4570bf1908784b8d114396402
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021806"
---
# <a name="quarantine-zones-for-nonconformances"></a><span data-ttu-id="486d3-103">Aree di quarantena per non conformità</span><span class="sxs-lookup"><span data-stu-id="486d3-103">Quarantine zones for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="486d3-104">Questo argomento descrive come creare e utilizzare aree di quarantena per le non conformità.</span><span class="sxs-lookup"><span data-stu-id="486d3-104">This topic describes how to create and use quarantine zones for nonconformances.</span></span>

<span data-ttu-id="486d3-105">Utilizzare la pagina **Aree quarantena** per definire le zone che possono essere assegnate alle non conformità.</span><span class="sxs-lookup"><span data-stu-id="486d3-105">You use the **Quarantine zones** page to define zones that can be assigned to nonconformances.</span></span> <span data-ttu-id="486d3-106">Quando crei una non conformità, puoi impostare i campi **Area quarantena** e **Tipo di quarantena** della scheda **Generale** della pagina **Non conformità**.</span><span class="sxs-lookup"><span data-stu-id="486d3-106">When you create a nonconformance, you can set the **Quarantine zone** and **Quarantine type** fields on the **General** tab of the **Non conformances** page.</span></span> <span data-ttu-id="486d3-107">Il capo **Area quarantena** indica in genere l'area o la ubicazione in cui si trova l'articolo.</span><span class="sxs-lookup"><span data-stu-id="486d3-107">The **Quarantine zone** field typically indicates the area or location where the item is located.</span></span> <span data-ttu-id="486d3-108">Il campo **Tipo di quarantena** definisce l'articolo come *Utilizzo limitato* o *Inutilizzabile*.</span><span class="sxs-lookup"><span data-stu-id="486d3-108">The **Quarantine type** field defines the item as either *Restricted usage* or *Unusable*.</span></span>

<span data-ttu-id="486d3-109">Quando si stampa un report di non conformità o di correzioni per una non conformità, è possibile visualizzare l'area di quarantena in cui si trova l'articolo.</span><span class="sxs-lookup"><span data-stu-id="486d3-109">When you print a nonconformance or corrections report for a nonconformance, you can view the quarantine zone where the item is located.</span></span>

<span data-ttu-id="486d3-110">È inoltre possibile stampare un tag di non conformità per una non conformità.</span><span class="sxs-lookup"><span data-stu-id="486d3-110">You can also print a nonconformance tag for a nonconformance.</span></span> <span data-ttu-id="486d3-111">Questo report mostra l'area di quarantena assegnata e le informazioni sull'utilizzo per fornire istruzioni sulla modalità di gestione del materiale difettoso.</span><span class="sxs-lookup"><span data-stu-id="486d3-111">This report shows the assigned quarantine zone and information about usage to provide guidance about how defective material should be handled.</span></span> <span data-ttu-id="486d3-112">Le aree di quarantena possono corrispondere alle ubicazioni di magazzino o alle risorse operative.</span><span class="sxs-lookup"><span data-stu-id="486d3-112">The quarantine zones might correspond to inventory locations or operations resources.</span></span>

## <a name="examples-of-quarantine-zones"></a><span data-ttu-id="486d3-113">Esempi di aree di quarantena</span><span class="sxs-lookup"><span data-stu-id="486d3-113">Examples of quarantine zones</span></span>

### <a name="example-1"></a><span data-ttu-id="486d3-114">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="486d3-114">Example 1</span></span>

<span data-ttu-id="486d3-115">Lavori in un'azienda di produzione di elettronica che produce e distribuisce televisori, altoparlanti e lettori multimediali.</span><span class="sxs-lookup"><span data-stu-id="486d3-115">You work at an electronics manufacturing company that produces and distributes televisions, speakers, and media players.</span></span> <span data-ttu-id="486d3-116">In questo caso, puoi configurare una area di quarantena per rappresentare ogni tipo di prodotto.</span><span class="sxs-lookup"><span data-stu-id="486d3-116">In this case, you can configure a quarantine zone to represent each type of product.</span></span>

### <a name="example-2"></a><span data-ttu-id="486d3-117">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="486d3-117">Example 2</span></span>

<span data-ttu-id="486d3-118">Tre contenitori e due scaffali vengono utilizzati per conservare gli articoli non conformi.</span><span class="sxs-lookup"><span data-stu-id="486d3-118">Three bins and two racks are used to store items that are nonconforming.</span></span> <span data-ttu-id="486d3-119">In questo caso, è possibile configurare cinque aree di quarantena, una per ogni contenitore e ogni rack.</span><span class="sxs-lookup"><span data-stu-id="486d3-119">In this case, you can configure five quarantine zones, one for each bin and each rack.</span></span>

## <a name="create-a-quarantine-zone"></a><span data-ttu-id="486d3-120">Creare un'area di quarantena</span><span class="sxs-lookup"><span data-stu-id="486d3-120">Create a quarantine zone</span></span>

1. <span data-ttu-id="486d3-121">Andare a **Gestione articoli \> Impostazioni \> Gestione qualità \> Aree quarantena**.</span><span class="sxs-lookup"><span data-stu-id="486d3-121">Go to **Inventory management \> Setup \> Quality management \> Quarantine zones**.</span></span>
1. <span data-ttu-id="486d3-122">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="486d3-122">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="486d3-123">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="486d3-123">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="486d3-124">**Area quarantena** - Immettere un ID o un nome univoco per la area di quarantena.</span><span class="sxs-lookup"><span data-stu-id="486d3-124">**Quarantine zone** – Enter a unique ID or name for the quarantine zone.</span></span>
    - <span data-ttu-id="486d3-125">**Descrizione** - Immettere una descrizione dettagliata della area di quarantena.</span><span class="sxs-lookup"><span data-stu-id="486d3-125">**Description** – Enter a detailed description of the quarantine zone.</span></span>

1. <span data-ttu-id="486d3-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="486d3-126">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="486d3-127">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="486d3-127">Additional resources</span></span>

- [<span data-ttu-id="486d3-128">Panoramica gestione qualità</span><span class="sxs-lookup"><span data-stu-id="486d3-128">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="486d3-129">Abilitare la gestione della qualità e della non conformità</span><span class="sxs-lookup"><span data-stu-id="486d3-129">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="486d3-130">Lavoratori responsabili dell'approvazione delle non conformità</span><span class="sxs-lookup"><span data-stu-id="486d3-130">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="486d3-131">Tipi di problemi per non conformità</span><span class="sxs-lookup"><span data-stu-id="486d3-131">Problem types for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="486d3-132">Tipi di diagnostica per non conformità</span><span class="sxs-lookup"><span data-stu-id="486d3-132">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="486d3-133">Spese di gestione qualità per non conformità</span><span class="sxs-lookup"><span data-stu-id="486d3-133">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="486d3-134">Operazioni per non conformità</span><span class="sxs-lookup"><span data-stu-id="486d3-134">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="486d3-135">Gestione qualità per i processi di magazzino</span><span class="sxs-lookup"><span data-stu-id="486d3-135">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
