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
ms.openlocfilehash: 5a616dcfdd755efc9bf0473e9239acb9127f11f8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818159"
---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="aed27-103">Creare criteri di selezione di prezzo di vendita</span><span class="sxs-lookup"><span data-stu-id="aed27-103">Create sales price selection criteria</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="aed27-104">In questa procedura viene illustrato come creare un criterio di selezione del prezzo di vendita per i modelli basati sugli attributi.</span><span class="sxs-lookup"><span data-stu-id="aed27-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="aed27-105">L'esecuzione di questa procedura richiede almeno un modello di prezzo di vendita disponibile.</span><span class="sxs-lookup"><span data-stu-id="aed27-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="aed27-106">In questo esempio viene utilizzato il modello di prezzo di vendita della soluzione Speaker nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="aed27-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="aed27-107">In genere, un responsabile di prodotto usa questa procedura.</span><span class="sxs-lookup"><span data-stu-id="aed27-107">Typically, a product manager uses this procedure.</span></span>


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="aed27-108">Aggiungere un nuovo criterio per un modello di prezzo di vendita esistente</span><span class="sxs-lookup"><span data-stu-id="aed27-108">Add a new criterion for an existing sales price model</span></span>
1. <span data-ttu-id="aed27-109">Fare clic su Definizione modello di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="aed27-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="aed27-110">Fare clic su Modelli di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="aed27-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="aed27-111">Nell'elenco, selezionare la riga per il modello prodotto della soluzione Speaker, ma non fare clic sul collegamento corrispondente al nome del modello.</span><span class="sxs-lookup"><span data-stu-id="aed27-111">In the list, select the row for the Speaker solution product model, but don't click the link for the model name.</span></span>
4. <span data-ttu-id="aed27-112">Nel riquadro azioni, fare clic su Modello.</span><span class="sxs-lookup"><span data-stu-id="aed27-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="aed27-113">Fare clic su Criteri modello di prezzo.</span><span class="sxs-lookup"><span data-stu-id="aed27-113">Click Price model criteria.</span></span>
6. <span data-ttu-id="aed27-114">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="aed27-114">Click New.</span></span>
7. <span data-ttu-id="aed27-115">Nel campo Nome digitare "Gruppo clienti 10".</span><span class="sxs-lookup"><span data-stu-id="aed27-115">In the Name field, type 'Customer group 10'.</span></span>
    * <span data-ttu-id="aed27-116">Il nome del criterio per il modello del prezzo viene utilizzato per identificare i criteri di selezione sottostanti.</span><span class="sxs-lookup"><span data-stu-id="aed27-116">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
8. <span data-ttu-id="aed27-117">Nel campo Modello di prezzo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="aed27-117">In the Price model field, enter or select a value.</span></span>
9. <span data-ttu-id="aed27-118">Nel campo Tipo di ordine selezionare Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="aed27-118">In the Order type field, select Sales order.</span></span>
    * <span data-ttu-id="aed27-119">Il tipo di ordine determina i campi di database da rendere disponibili per la query di selezione.</span><span class="sxs-lookup"><span data-stu-id="aed27-119">The order type determines the database fields that will be available for the selection query.</span></span>  
10. <span data-ttu-id="aed27-120">Immettere una data nel campo Data di inizio validità.</span><span class="sxs-lookup"><span data-stu-id="aed27-120">In the Valid from field, enter a date.</span></span>
11. <span data-ttu-id="aed27-121">Nel campo Data scadenza immettere una data.</span><span class="sxs-lookup"><span data-stu-id="aed27-121">In the Expire by field, enter a date.</span></span>
12. <span data-ttu-id="aed27-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="aed27-122">Click Save.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="aed27-123">Creare la query per i criteri di selezione</span><span class="sxs-lookup"><span data-stu-id="aed27-123">Create the query for the selection criteria</span></span>
1. <span data-ttu-id="aed27-124">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="aed27-124">Click Edit.</span></span>
2. <span data-ttu-id="aed27-125">Selezionare Clienti nel campo Tabella.</span><span class="sxs-lookup"><span data-stu-id="aed27-125">In the Table field, select Customers.</span></span> 
3. <span data-ttu-id="aed27-126">Selezionare Gruppo di clienti nel campo Campo.</span><span class="sxs-lookup"><span data-stu-id="aed27-126">In the Field field, select Customer group.</span></span>
    * <span data-ttu-id="aed27-127">In questo esempio, useremo uno specifico gruppo di clienti per i criteri di selezione.</span><span class="sxs-lookup"><span data-stu-id="aed27-127">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="aed27-128">Nel campo Criteri selezionare Gruppo di clienti 10.</span><span class="sxs-lookup"><span data-stu-id="aed27-128">In the Criteria field, select Customer group 10.</span></span> 
5. <span data-ttu-id="aed27-129">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="aed27-129">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]