---
title: Spese per operazioni di non conformità
description: Questo argomento descrive come spese di gestione qualità che possano essere utilizzate con le operazioni per una non conformità.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 382890232bff47a885840af1eb7e91d27bb46cae
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022302"
---
# <a name="charges-for-nonconformance-operations"></a><span data-ttu-id="0d3e1-103">Spese per operazioni di non conformità</span><span class="sxs-lookup"><span data-stu-id="0d3e1-103">Charges for nonconformance operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0d3e1-104">Questo argomento descrive come spese di gestione qualità che possano essere utilizzate con le operazioni per una non conformità.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-104">This topic describes how to create quality charges that can be used with operations for a nonconformance.</span></span>

<span data-ttu-id="0d3e1-105">Puoi Utilizzare la pagina **Spese gesione qualità** per definire i tipi di spese che è possibile aggiungere alle operazioni per una non conformità.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-105">You use the **Quality charges** page to define the types of charges that can be added to operations for a nonconformance.</span></span> <span data-ttu-id="0d3e1-106">Le spese ti consentono di tenere traccia dei dettagli sulle commissioni o sugli addebiti che devi a un cliente per prodotti non conformi o che un fornitore ti deve per prodotti non conformi che hai ricevuto.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-106">Charges let you track details about fees or charges that you owe to a customer for nonconforming products, or that a vendor owes to you for nonconforming products that you received.</span></span> <span data-ttu-id="0d3e1-107">È inoltre possibile utilizzare gli addebiti per tenere traccia dei costi necessari ai fornitori o ai servizi esterni per eseguire un'operazione.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-107">You might also use charges to track costs that are required for external vendors or services to perform an operation.</span></span>

## <a name="examples-of-quality-charges"></a><span data-ttu-id="0d3e1-108">Esempi di spese di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="0d3e1-108">Examples of quality charges</span></span>

<span data-ttu-id="0d3e1-109">Lavori per un'azienda manifatturiera.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-109">You work for a manufacturing company.</span></span> <span data-ttu-id="0d3e1-110">La tua azienda ha contratti con diversi fornitori.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-110">Your company has contracts with several vendors.</span></span> <span data-ttu-id="0d3e1-111">Tali contratti definiscono gli standard per la spedizione puntuale, i danni e la qualità del prodotto degli articoli.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-111">Those contracts outline standards for on-time shipment, damages, and product quality for items.</span></span> <span data-ttu-id="0d3e1-112">Allo stesso modo, molti dei tuoi clienti hanno accordi con la tua azienda su resi, danni e qualità del prodotto.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-112">Likewise, several of your customers have agreements with your company about returns, damages, and product quality.</span></span>

<span data-ttu-id="0d3e1-113">Una struttura tariffaria è definita per ogni circostanza e specificata nel contratto.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-113">A fee structure is defined for each circumstance and specified in the contract.</span></span> <span data-ttu-id="0d3e1-114">È possibile configurare le spese di gestione qualità per delineare i vari tipi di addebiti, ad esempio *Danni*, *Spedizione in ritardo*, e *Qualità*.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-114">You can configure quality charges to outline the various types of charges, such as *Damages*, *Late shipment*, and *Quality*.</span></span> <span data-ttu-id="0d3e1-115">Quindi, quando crei una non conformità, aggiungi una o più operazioni.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-115">Then, when you create a nonconformance, you add one or more operations.</span></span> <span data-ttu-id="0d3e1-116">Per ogni operazione, selezioni **Spese** per definire i dettagli sulle tariffe.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-116">For each operation, you select **Charges** to define the details about the fees.</span></span>

## <a name="create-a-quality-charge"></a><span data-ttu-id="0d3e1-117">Creare una spesa di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="0d3e1-117">Create a quality charge</span></span>

1. <span data-ttu-id="0d3e1-118">Andare a **Gestione articoli \> Impostazioni \> Gestione qualità \> Spese gestione qualità**.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-118">Go to **Inventory management \> Setup \> Quality management \> Quality charges**.</span></span>
1. <span data-ttu-id="0d3e1-119">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-119">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="0d3e1-120">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="0d3e1-120">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="0d3e1-121">**Codice spese** - Immettere un ID o un nome univoco per la spesa di gestione qualità.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-121">**Charges code** – Enter a unique ID or name for the quality charge.</span></span>
    - <span data-ttu-id="0d3e1-122">**Descrizione** - Immettere una descrizione dettagliata della spesa di gestione qualità.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-122">**Description** – Enter a detailed description of the quality charge.</span></span>

1. <span data-ttu-id="0d3e1-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0d3e1-123">Close the page.</span></span>

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a><span data-ttu-id="0d3e1-124">Aggiungere una spesa di gestione qualità a un'operazione per una non conformità</span><span class="sxs-lookup"><span data-stu-id="0d3e1-124">Add a quality charge to an operation for a nonconformance</span></span>

<span data-ttu-id="0d3e1-125">Per dettagli su come aggiungere operazioni a una non conformità e applicarvi spese, vedere [Operazioni per non conformità](quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0d3e1-125">For details about how to add operations to a nonconformance and apply charges to them, see [Operations for nonconformances](quality-operations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0d3e1-126">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0d3e1-126">Additional resources</span></span>

- [<span data-ttu-id="0d3e1-127">Panoramica gestione qualità</span><span class="sxs-lookup"><span data-stu-id="0d3e1-127">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="0d3e1-128">Abilitare la gestione della qualità e della non conformità</span><span class="sxs-lookup"><span data-stu-id="0d3e1-128">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="0d3e1-129">Lavoratori responsabili dell'approvazione delle non conformità</span><span class="sxs-lookup"><span data-stu-id="0d3e1-129">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="0d3e1-130">Aree di quarantena per non conformità</span><span class="sxs-lookup"><span data-stu-id="0d3e1-130">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="0d3e1-131">Tipi di diagnostica per non conformità</span><span class="sxs-lookup"><span data-stu-id="0d3e1-131">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="0d3e1-132">Spese di gestione qualità per non conformità</span><span class="sxs-lookup"><span data-stu-id="0d3e1-132">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="0d3e1-133">Operazioni per non conformità</span><span class="sxs-lookup"><span data-stu-id="0d3e1-133">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="0d3e1-134">Gestione qualità per i processi di magazzino</span><span class="sxs-lookup"><span data-stu-id="0d3e1-134">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
