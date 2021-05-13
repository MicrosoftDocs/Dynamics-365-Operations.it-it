---
title: Gestire DBA per un modello di configurazione prodotto
description: L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b4ad73265e321b6339c061a7866b55cb2769954b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921319"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="27509-103">Gestire DBA per un modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="27509-103">Maintain BOM for a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="27509-104">L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente.</span><span class="sxs-lookup"><span data-stu-id="27509-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="27509-105">Il modello High end speaker della società di dati dimostrativi USMF è utilizzato per creare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="27509-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>

## <a name="add-a-bom-line"></a><span data-ttu-id="27509-106">Aggiungere una riga DBA</span><span class="sxs-lookup"><span data-stu-id="27509-106">Add a BOM line</span></span>

1. <span data-ttu-id="27509-107">Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.</span><span class="sxs-lookup"><span data-stu-id="27509-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="27509-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="27509-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="27509-109">Selezionare High end speaker per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="27509-109">Select the High end speaker for this procedure.</span></span>  
1. <span data-ttu-id="27509-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="27509-110">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="27509-111">Espandere la sezione **Righe DBA**.</span><span class="sxs-lookup"><span data-stu-id="27509-111">Expand the **BOM lines** section.</span></span>
1. <span data-ttu-id="27509-112">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="27509-112">Select **Add**.</span></span>
1. <span data-ttu-id="27509-113">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="27509-113">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="27509-114">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="27509-114">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="27509-115">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="27509-115">Select **Save**.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="27509-116">Aggiungere i dettagli riga DBA</span><span class="sxs-lookup"><span data-stu-id="27509-116">Add BOM line details</span></span>

1. <span data-ttu-id="27509-117">Selezionare **Dettagli riga DBA**.</span><span class="sxs-lookup"><span data-stu-id="27509-117">Select **BOM line details**.</span></span>
2. <span data-ttu-id="27509-118">Nel campo **Numero articolo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="27509-118">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="27509-119">Ad esempio, è possibile selezionare l'articolo M0055.</span><span class="sxs-lookup"><span data-stu-id="27509-119">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="27509-120">Per ogni proprietà di riga DBA, è possibile scegliere se prende un valore fisso o viene sottoposta al mapping a un attributo.</span><span class="sxs-lookup"><span data-stu-id="27509-120">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="27509-121">Selezionare la casella di controllo **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="27509-121">Select the **Set** check box.</span></span>
4. <span data-ttu-id="27509-122">Selezionare *Sì* nel campo **Calcolo**.</span><span class="sxs-lookup"><span data-stu-id="27509-122">Select *Yes* in the **Calculation** field.</span></span>
    * <span data-ttu-id="27509-123">Impostando la proprietà **Calcolo** su *Sì*, si garantisce che la riga DBA venga inclusa nei calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="27509-123">Setting the **Calculation** property to *Yes* ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="27509-124">Seleziona la scheda **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="27509-124">Select the **Setup** tab.</span></span>
6. <span data-ttu-id="27509-125">Selezionare la casella di controllo **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="27509-125">Select the **Set** check box.</span></span>
7. <span data-ttu-id="27509-126">Nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="27509-126">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="27509-127">Il campo Quantità determina la quantità dell'articolo che verrà incluso nella DBA.</span><span class="sxs-lookup"><span data-stu-id="27509-127">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="27509-128">Ovviamente può essere utilizzato per il mapping di attributo.</span><span class="sxs-lookup"><span data-stu-id="27509-128">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="27509-129">Selezionare la scheda **Dimensione**.</span><span class="sxs-lookup"><span data-stu-id="27509-129">Select the **Dimension** tab.</span></span>
    * <span data-ttu-id="27509-130">Verificare se le dimensioni prodotto sono attive e nel qual caso è necessario assegnare un valore o un attributo.</span><span class="sxs-lookup"><span data-stu-id="27509-130">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="27509-131">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="27509-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]