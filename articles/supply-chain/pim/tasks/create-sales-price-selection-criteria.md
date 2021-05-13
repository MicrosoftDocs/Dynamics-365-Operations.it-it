---
title: Creare criteri di selezione di prezzo di vendita
description: In questa procedura viene illustrato come creare un criterio di selezione del prezzo di vendita per i modelli basati sugli attributi.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 69d22c3321beaa2667ee20bff00acd746714b993
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920533"
---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="c4006-103">Creare criteri di selezione di prezzo di vendita</span><span class="sxs-lookup"><span data-stu-id="c4006-103">Create sales price selection criteria</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c4006-104">In questa procedura viene illustrato come creare un criterio di selezione del prezzo di vendita per i modelli basati sugli attributi.</span><span class="sxs-lookup"><span data-stu-id="c4006-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="c4006-105">L'esecuzione di questa procedura richiede almeno un modello di prezzo di vendita disponibile.</span><span class="sxs-lookup"><span data-stu-id="c4006-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="c4006-106">In questo esempio viene utilizzato il modello di prezzo di vendita della soluzione Speaker nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="c4006-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="c4006-107">In genere, un responsabile di prodotto usa questa procedura.</span><span class="sxs-lookup"><span data-stu-id="c4006-107">Typically, a product manager uses this procedure.</span></span>

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="c4006-108">Aggiungere un nuovo criterio per un modello di prezzo di vendita esistente</span><span class="sxs-lookup"><span data-stu-id="c4006-108">Add a new criterion for an existing sales price model</span></span>

1. <span data-ttu-id="c4006-109">Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.</span><span class="sxs-lookup"><span data-stu-id="c4006-109">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="c4006-110">Nell'elenco, selezionare la riga per il modello prodotto della soluzione Speaker, ma non fare clic sul collegamento corrispondente al nome del modello.</span><span class="sxs-lookup"><span data-stu-id="c4006-110">In the list, select the row for the Speaker solution product model, but don't select the link for the model name.</span></span>
1. <span data-ttu-id="c4006-111">Nel Riquadro azioni selezionare **Modello**.</span><span class="sxs-lookup"><span data-stu-id="c4006-111">On the Action Pane, select **Model**.</span></span>
1. <span data-ttu-id="c4006-112">Selezionare **Criteri modello di prezzo**</span><span class="sxs-lookup"><span data-stu-id="c4006-112">Select **Price model criteria**.</span></span>
1. <span data-ttu-id="c4006-113">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c4006-113">Select **New**.</span></span>
1. <span data-ttu-id="c4006-114">Nel campo **Nome** digitare "Gruppo clienti 10".</span><span class="sxs-lookup"><span data-stu-id="c4006-114">In the **Name** field, type 'Customer group 10'.</span></span>
    * <span data-ttu-id="c4006-115">Il nome del criterio per il modello del prezzo viene utilizzato per identificare i criteri di selezione sottostanti.</span><span class="sxs-lookup"><span data-stu-id="c4006-115">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
1. <span data-ttu-id="c4006-116">Nel campo **Modello di prezzo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c4006-116">In the **Price model** field, enter or select a value.</span></span>
1. <span data-ttu-id="c4006-117">Nel campo **Tipo di ordine** selezionare *Ordine cliente*.</span><span class="sxs-lookup"><span data-stu-id="c4006-117">In the **Order type** field, select *Sales order*.</span></span>
    * <span data-ttu-id="c4006-118">Il tipo di ordine determina i campi di database da rendere disponibili per la query di selezione.</span><span class="sxs-lookup"><span data-stu-id="c4006-118">The order type determines the database fields that will be available for the selection query.</span></span>  
1. <span data-ttu-id="c4006-119">Immettere una data nel campo **Data di inizio validità**.</span><span class="sxs-lookup"><span data-stu-id="c4006-119">In the **Valid from** field, enter a date.</span></span>
1. <span data-ttu-id="c4006-120">Nel campo **Data scadenza** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="c4006-120">In the **Expire by** field, enter a date.</span></span>
1. <span data-ttu-id="c4006-121">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c4006-121">Select **Save**.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="c4006-122">Creare la query per i criteri di selezione</span><span class="sxs-lookup"><span data-stu-id="c4006-122">Create the query for the selection criteria</span></span>

1. <span data-ttu-id="c4006-123">Seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c4006-123">Select **Edit**.</span></span>
2. <span data-ttu-id="c4006-124">Selezionare **Clienti** nel campo *Tabella*.</span><span class="sxs-lookup"><span data-stu-id="c4006-124">In the **Table** field, select *Customers*.</span></span>
3. <span data-ttu-id="c4006-125">Selezionare **Gruppo di clienti** nel campo *Campo*.</span><span class="sxs-lookup"><span data-stu-id="c4006-125">In the **Field** field, select *Customer group*.</span></span>
    * <span data-ttu-id="c4006-126">In questo esempio, useremo uno specifico gruppo di clienti per i criteri di selezione.</span><span class="sxs-lookup"><span data-stu-id="c4006-126">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="c4006-127">Nel campo **Criteri** selezionare *Gruppo di clienti 10*.</span><span class="sxs-lookup"><span data-stu-id="c4006-127">In the **Criteria** field, select *Customer group 10*.</span></span>
5. <span data-ttu-id="c4006-128">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4006-128">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]