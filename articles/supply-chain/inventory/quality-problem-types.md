---
title: Tipi di problemi per non conformità
description: Questo argomento descrive come creare e utilizzare i tipi di problemi per le non conformità.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 742edec8570610efe41a2c627efd1df586e0733e
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022158"
---
# <a name="problem-types-for-nonconformances"></a><span data-ttu-id="9a7f2-103">Tipi di problemi per non conformità</span><span class="sxs-lookup"><span data-stu-id="9a7f2-103">Problem types for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9a7f2-104">Questo argomento descrive come creare e utilizzare i tipi di problemi per le non conformità.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-104">This topic describes how to create and use problem types for nonconformances.</span></span>

<span data-ttu-id="9a7f2-105">Utilizzare la pagina **Tipi di problemi** per definire una classificazione dei problemi relativi alla qualità che possono verificarsi per i vari tipi di non conformità.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-105">You use the **Problem types** page to define a classification of the quality problems that might occur for the various nonconformance types.</span></span> <span data-ttu-id="9a7f2-106">Per ogni tipo di problema creato, è necessario specificare i tipi di non conformità con cui può essere utilizzato il tipo di problema.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-106">For each problem type that you create, you must specify the types of nonconformances that the problem type can be used with.</span></span> <span data-ttu-id="9a7f2-107">È possibile impostare i seguenti tipi di non conformità:</span><span class="sxs-lookup"><span data-stu-id="9a7f2-107">You can set up the following nonconformance types:</span></span>

- <span data-ttu-id="9a7f2-108">**Interno** - Le non conformità di questo tipo sono correlate alle scorte disponibili (ad esempio, ordini di controllo qualità o ordini di quarantena).</span><span class="sxs-lookup"><span data-stu-id="9a7f2-108">**Internal** – Nonconformances of this type are related to on-hand inventory (for example, quality orders or quarantine orders).</span></span>
- <span data-ttu-id="9a7f2-109">**Cliente** - Non conformità di questo tipo sono correlate agli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-109">**Customer** – Nonconformances of this type are related to sales orders.</span></span>
- <span data-ttu-id="9a7f2-110">**Fornitore** - Non conformità di questo tipo sono correlate agli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-110">**Vendor** – Nonconformances of this type are related to purchase orders.</span></span>
- <span data-ttu-id="9a7f2-111">**Richiesta di assistenza** - Non conformità di questo tipo sono correlate agli ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-111">**Service request** – Nonconformances of this type are related to service orders.</span></span>
- <span data-ttu-id="9a7f2-112">**Produzione** - Non conformità di questo tipo sono correlate agli ordini batch o di produzione.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-112">**Production** – Nonconformances of this type are related to batch orders or production orders.</span></span>
- <span data-ttu-id="9a7f2-113">**Produzione co-prodotti** - Non conformità di questo tipo sono correlate agli ordini batch per co-prodotti.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-113">**Co-product production** – Nonconformances of this type are related to batch orders for co-products.</span></span>

<span data-ttu-id="9a7f2-114">Quando crei un nuovo tipo di problema, seleziona **Tipi di non conformità** nel riquadro azioni per creare un elenco di uno o più tipi di non conformità autorizzati per il tipo di problema.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-114">When you create a new problem type, select **Non conformance types** on the Action Pane to create a list of one or more nonconformance types that are authorized for the problem type.</span></span> <span data-ttu-id="9a7f2-115">Un tipo di problema riguardante un codice di articolo difettoso potrebbe ad esempio essere applicato a tutti i tipi di non conformità.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-115">For example, a problem type that is related to a defect code might apply to all nonconformance types.</span></span> <span data-ttu-id="9a7f2-116">Tuttavia, un tipo di problema correlato ai reclami dei clienti potrebbe applicarsi solo ai tipi di non conformità **Cliente** e **Richiesta di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-116">However, a problem type that is related to customer complaints might apply only to the **Customer** and **Service request** nonconformance types.</span></span>

## <a name="examples-of-problem-types"></a><span data-ttu-id="9a7f2-117">Esempi di tipi di problemi:</span><span class="sxs-lookup"><span data-stu-id="9a7f2-117">Examples of problem types</span></span>

<span data-ttu-id="9a7f2-118">Di seguito sono riportati alcuni esempi di scenari per i tipi di problemi che possono essere utilizzati con i diversi tipi di non conformità:</span><span class="sxs-lookup"><span data-stu-id="9a7f2-118">Here are some examples of scenarios for problem types that can be used with the different nonconformance types:</span></span>

- <span data-ttu-id="9a7f2-119">**Cliente:** Un cliente ha presentato un reclamo, un cliente ha effettuato un reso o le specifiche di qualità non sono state soddisfatte.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-119">**Customer:** A customer filed a complaint, a customer made a return, or quality specifications weren't met.</span></span>
- <span data-ttu-id="9a7f2-120">**Fornitore:** Il prodotto è stato danneggiato, le specifiche di qualità non sono state soddisfatte o è stato ricevuto il prodotto sbagliato.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-120">**Vendor:** The product was damaged, quality specifications weren't met, or the wrong product was received.</span></span>
- <span data-ttu-id="9a7f2-121">**Richiesta di assistenza:** Le specifiche di qualità non sono state soddisfatte, un cliente ha presentato un reclamo o è necessaria la manutenzione di una macchina.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-121">**Service request:** Quality specifications weren't met, a customer filed a complaint, or machine maintenance is required.</span></span>
- <span data-ttu-id="9a7f2-122">**Produzione:** Le specifiche di qualità non sono state soddisfatte, è necessaria la manutenzione della macchina o il prodotto è stato danneggiato.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-122">**Production:** Quality specifications weren't met, machine maintenance is required, or the product was damaged.</span></span>
- <span data-ttu-id="9a7f2-123">**Produzione co-prodotti:** Le specifiche di qualità non sono state soddisfatte, è necessaria la manutenzione della macchina o il prodotto è stato danneggiato.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-123">**Co-product production:** Quality specifications weren't met, machine maintenance is required, or the product was damaged.</span></span>

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a><span data-ttu-id="9a7f2-124">Creare un tipo di problema e assegnarlo ai tipi di non conformità</span><span class="sxs-lookup"><span data-stu-id="9a7f2-124">Create a problem type and assign it to nonconformance types</span></span>

1. <span data-ttu-id="9a7f2-125">Andare a **Gestione articoli \> Impostazioni \> Gestione qualità \> Tipi di problema**.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-125">Go to **Inventory management \> Setup \> Quality management \> Problem types**.</span></span>
1. <span data-ttu-id="9a7f2-126">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-126">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="9a7f2-127">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="9a7f2-127">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="9a7f2-128">**Tipo di problema** - Immettere un ID o un nome univoco per il tipo di problema.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-128">**Problem type** – Enter a unique ID or name for the problem type.</span></span>
    - <span data-ttu-id="9a7f2-129">**Descrizione** - Immettere una descrizione dettagliata del tipo di problema.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-129">**Description** – Enter a detailed description of the problem type.</span></span>

1. <span data-ttu-id="9a7f2-130">Mentre la nuova riga è ancora selezionata, seleziona **Tipi di non conformità** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-130">While the new row is still selected, select **Non conformance types** on the Action Pane.</span></span>
1. <span data-ttu-id="9a7f2-131">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-131">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="9a7f2-132">Quindi, per la nuova riga, imposta il campo **Tipo di non conformità** sul tipo di non conformità che si desidera consentire per il tipo di problema.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-132">Then, for the new row, set the **Non conformance type** field to the nonconformance type that you want to allow for the problem type.</span></span>
1. <span data-ttu-id="9a7f2-133">Ripetere il passaggio precedente per ogni tipo di non conformità aggiuntivo che si desidera autorizzare per il tipo di problema.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-133">Repeat the previous step for each additional nonconformance type that you want to authorize for the problem type.</span></span>
1. <span data-ttu-id="9a7f2-134">Chiudere le pagine.</span><span class="sxs-lookup"><span data-stu-id="9a7f2-134">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9a7f2-135">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9a7f2-135">Additional resources</span></span>

- [<span data-ttu-id="9a7f2-136">Panoramica gestione qualità</span><span class="sxs-lookup"><span data-stu-id="9a7f2-136">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="9a7f2-137">Abilitare la gestione della qualità e della non conformità</span><span class="sxs-lookup"><span data-stu-id="9a7f2-137">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="9a7f2-138">Lavoratori responsabili dell'approvazione delle non conformità</span><span class="sxs-lookup"><span data-stu-id="9a7f2-138">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="9a7f2-139">Aree di quarantena per non conformità</span><span class="sxs-lookup"><span data-stu-id="9a7f2-139">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="9a7f2-140">Tipi di diagnostica per non conformità</span><span class="sxs-lookup"><span data-stu-id="9a7f2-140">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="9a7f2-141">Spese di gestione qualità per non conformità</span><span class="sxs-lookup"><span data-stu-id="9a7f2-141">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="9a7f2-142">Operazioni per non conformità</span><span class="sxs-lookup"><span data-stu-id="9a7f2-142">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="9a7f2-143">Gestione qualità per i processi di magazzino</span><span class="sxs-lookup"><span data-stu-id="9a7f2-143">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
