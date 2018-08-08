---
title: "Specificare la modalità di smaltimento dei resi"
description: "Specificare la modalità di smaltimento dei resi."
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e6fcdfec083aeb9c58d63f6e03542758e4d07e4d
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="specify-how-to-dispose-of-returned-items"></a><span data-ttu-id="129e1-103">Specificare la modalità di smaltimento dei resi</span><span class="sxs-lookup"><span data-stu-id="129e1-103">Specify how to dispose of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="129e1-104">Quando si gestisce un ordine di reso, è necessario specificare un codice motivo reso per identificare poiché il prodotto viene restituito.</span><span class="sxs-lookup"><span data-stu-id="129e1-104">When you handle a return order, you must specify a reason return code to identify why the product is being returned.</span></span> <span data-ttu-id="129e1-105">È inoltre necessario specificare un codice smaltimento e un'azione di smaltimento per determinare cosa deve essere effettuato con il prodotto restituito.</span><span class="sxs-lookup"><span data-stu-id="129e1-105">You must also specify a disposition code and a disposition action to determine what should be done with the returned product itself.</span></span>

<span data-ttu-id="129e1-106">È possibile applicare un codice smaltimento quando si crea l'ordine di reso, si registra l'arrivo dell'articolo, si aggiorna il documento di trasporto specificando che l'articolo è arrivato oppure quando si termina un ordine di quarantena.</span><span class="sxs-lookup"><span data-stu-id="129e1-106">A disposition code can be applied when you create the return order, register item arrival or packing-slip update an item arrival, and end a quarantine order.</span></span>

<span data-ttu-id="129e1-107">È possibile definire tutti i codici smaltimento necessari per il processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="129e1-107">You can define any disposition codes that you need in order to support the business processes.</span></span> <span data-ttu-id="129e1-108">Nella tabella riportata di seguito è disponibile l'insieme dei codici più comunemente utilizzati per specificare la modalità di smaltimento dei resi.</span><span class="sxs-lookup"><span data-stu-id="129e1-108">The following table provides a set of typically used codes to assign return-item disposition.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="129e1-109">Tipo di smaltimento</span><span class="sxs-lookup"><span data-stu-id="129e1-109">Disposition type</span></span></p></th>
<th><p><span data-ttu-id="129e1-110">Codice comune</span><span class="sxs-lookup"><span data-stu-id="129e1-110">Common code</span></span></p></th>
<th><p><span data-ttu-id="129e1-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="129e1-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="129e1-112">Dismissione</span><span class="sxs-lookup"><span data-stu-id="129e1-112">Disposal</span></span></p></td>
<td><p><span data-ttu-id="129e1-113">SC</span><span class="sxs-lookup"><span data-stu-id="129e1-113">SC</span></span></p></td>
<td><p><span data-ttu-id="129e1-114">Scarto/distruzione</span><span class="sxs-lookup"><span data-stu-id="129e1-114">Scrap/Destroy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129e1-115">Dismissione</span><span class="sxs-lookup"><span data-stu-id="129e1-115">Disposal</span></span></p></td>
<td><p><span data-ttu-id="129e1-116">Controller di dominio</span><span class="sxs-lookup"><span data-stu-id="129e1-116">DC</span></span></p></td>
<td><p><span data-ttu-id="129e1-117">Donazione in beneficenza</span><span class="sxs-lookup"><span data-stu-id="129e1-117">Donate to Charity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129e1-118">Dismissione</span><span class="sxs-lookup"><span data-stu-id="129e1-118">Disposal</span></span></p></td>
<td><p><span data-ttu-id="129e1-119">TD</span><span class="sxs-lookup"><span data-stu-id="129e1-119">TD</span></span></p></td>
<td><p><span data-ttu-id="129e1-120">Dismissione effettuata da terzi</span><span class="sxs-lookup"><span data-stu-id="129e1-120">Third-Party Disposal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129e1-121">Dismissione</span><span class="sxs-lookup"><span data-stu-id="129e1-121">Disposal</span></span></p></td>
<td><p><span data-ttu-id="129e1-122">SL</span><span class="sxs-lookup"><span data-stu-id="129e1-122">SL</span></span></p></td>
<td><p><span data-ttu-id="129e1-123">Realizzo</span><span class="sxs-lookup"><span data-stu-id="129e1-123">Salvage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129e1-124">Dismissione</span><span class="sxs-lookup"><span data-stu-id="129e1-124">Disposal</span></span></p></td>
<td><p><span data-ttu-id="129e1-125">TS</span><span class="sxs-lookup"><span data-stu-id="129e1-125">TS</span></span></p></td>
<td><p><span data-ttu-id="129e1-126">Vendita a terzi (mercati secondari)</span><span class="sxs-lookup"><span data-stu-id="129e1-126">Third-Party Sale (Secondary Markets)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129e1-127">Riparazione/Modifica</span><span class="sxs-lookup"><span data-stu-id="129e1-127">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="129e1-128">RW</span><span class="sxs-lookup"><span data-stu-id="129e1-128">RW</span></span></p></td>
<td><p><span data-ttu-id="129e1-129">Rilavorazione</span><span class="sxs-lookup"><span data-stu-id="129e1-129">Rework</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129e1-130">Riparazione/Modifica</span><span class="sxs-lookup"><span data-stu-id="129e1-130">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="129e1-131">RF</span><span class="sxs-lookup"><span data-stu-id="129e1-131">RF</span></span></p></td>
<td><p><span data-ttu-id="129e1-132">Rifabbricazione/rinnovamento</span><span class="sxs-lookup"><span data-stu-id="129e1-132">Remanufacture/Refurbish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129e1-133">Riparazione/Modifica</span><span class="sxs-lookup"><span data-stu-id="129e1-133">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="129e1-134">MD</span><span class="sxs-lookup"><span data-stu-id="129e1-134">MD</span></span></p></td>
<td><p><span data-ttu-id="129e1-135">Modifica</span><span class="sxs-lookup"><span data-stu-id="129e1-135">Modify</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129e1-136">Riparazione/Modifica</span><span class="sxs-lookup"><span data-stu-id="129e1-136">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="129e1-137">RP</span><span class="sxs-lookup"><span data-stu-id="129e1-137">RP</span></span></p></td>
<td><p><span data-ttu-id="129e1-138">Riparazione</span><span class="sxs-lookup"><span data-stu-id="129e1-138">Repair</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129e1-139">Riparazione/Modifica</span><span class="sxs-lookup"><span data-stu-id="129e1-139">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="129e1-140">RV</span><span class="sxs-lookup"><span data-stu-id="129e1-140">RV</span></span></p></td>
<td><p><span data-ttu-id="129e1-141">Restituzione al fornitore</span><span class="sxs-lookup"><span data-stu-id="129e1-141">Return to Vendor</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129e1-142">Altro</span><span class="sxs-lookup"><span data-stu-id="129e1-142">Other</span></span></p></td>
<td><p><span data-ttu-id="129e1-143">AI</span><span class="sxs-lookup"><span data-stu-id="129e1-143">AI</span></span></p></td>
<td><p><span data-ttu-id="129e1-144">Utilizzo degli articoli così come sono</span><span class="sxs-lookup"><span data-stu-id="129e1-144">Use as is</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129e1-145">Altro</span><span class="sxs-lookup"><span data-stu-id="129e1-145">Other</span></span></p></td>
<td><p><span data-ttu-id="129e1-146">RS</span><span class="sxs-lookup"><span data-stu-id="129e1-146">RS</span></span></p></td>
<td><p><span data-ttu-id="129e1-147">Rivendita</span><span class="sxs-lookup"><span data-stu-id="129e1-147">Resale</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129e1-148">Altro</span><span class="sxs-lookup"><span data-stu-id="129e1-148">Other</span></span></p></td>
<td><p><span data-ttu-id="129e1-149">EX</span><span class="sxs-lookup"><span data-stu-id="129e1-149">EX</span></span></p></td>
<td><p><span data-ttu-id="129e1-150">Scambia</span><span class="sxs-lookup"><span data-stu-id="129e1-150">Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129e1-151">Altro</span><span class="sxs-lookup"><span data-stu-id="129e1-151">Other</span></span></p></td>
<td><p><span data-ttu-id="129e1-152">MS</span><span class="sxs-lookup"><span data-stu-id="129e1-152">MS</span></span></p></td>
<td><p><span data-ttu-id="129e1-153">Varie</span><span class="sxs-lookup"><span data-stu-id="129e1-153">Miscellaneous</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="129e1-154">Per ogni codice smaltimento definito, è necessario selezionare un'azione di smaltimento.</span><span class="sxs-lookup"><span data-stu-id="129e1-154">For each disposition code that you define, you must select a disposition action.</span></span> <span data-ttu-id="129e1-155">L'azione di smaltimento determina le implicazioni fisiche e finanziarie dei codici smaltimento.</span><span class="sxs-lookup"><span data-stu-id="129e1-155">The disposition action determines the physical and financial implications of the disposition codes.</span></span> <span data-ttu-id="129e1-156">Ad esempio, l'azione di smaltimento determina la gestione fisica dell'articolo reso, il relativo effetto finanziario e se è richiesto l'invio al cliente di un articolo sostitutivo.</span><span class="sxs-lookup"><span data-stu-id="129e1-156">For example, the disposition action determines the physical handling of the returned item, the financial effect of the returned item, and if a replacement item must be sent to the customer.</span></span> <span data-ttu-id="129e1-157">È possibile definire un numero illimitato di codici smaltimento in base alle proprie esigenze, ma è possibile scegliere solo tra sei azioni di smaltimento predefinite.</span><span class="sxs-lookup"><span data-stu-id="129e1-157">You can define an unlimited number of disposition codes according to your business needs, but there are only six predefined disposition actions that you can select from.</span></span> <span data-ttu-id="129e1-158">Nella tabella seguente vengono illustrate le azioni di smaltimento e le relative definizioni.</span><span class="sxs-lookup"><span data-stu-id="129e1-158">The following table provides the disposition actions and their definitions.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="129e1-159">Azione di smaltimento</span><span class="sxs-lookup"><span data-stu-id="129e1-159">Disposition action</span></span></p></th>
<th><p><span data-ttu-id="129e1-160">descrizione</span><span class="sxs-lookup"><span data-stu-id="129e1-160">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="129e1-161"><strong>Avere</strong></span><span class="sxs-lookup"><span data-stu-id="129e1-161"><strong>Credit</strong></span></span></p></td>
<td><p><span data-ttu-id="129e1-162">Restituire l'articolo al magazzino ed effettuare l'accredito al cliente.</span><span class="sxs-lookup"><span data-stu-id="129e1-162">Return the item to inventory and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129e1-163"><strong>Solo credito</strong></span><span class="sxs-lookup"><span data-stu-id="129e1-163"><strong>Credit only</strong></span></span></p></td>
<td><p><span data-ttu-id="129e1-164">Effettuare l'accredito al cliente senza richiedere o prevedere la restituzione dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="129e1-164">Credit the customer without requiring or expecting the item to be returned.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129e1-165"><strong>Scarti</strong></span><span class="sxs-lookup"><span data-stu-id="129e1-165"><strong>Scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="129e1-166">Scartare l'articolo ed effettuare l'accredito al cliente.</span><span class="sxs-lookup"><span data-stu-id="129e1-166">Scrap the item and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129e1-167"><strong>Sostituzione e credito</strong></span><span class="sxs-lookup"><span data-stu-id="129e1-167"><strong>Replace and credit</strong></span></span></p></td>
<td><p><span data-ttu-id="129e1-168">Restituire l'articolo al magazzino, creare un ordine sostitutivo ed effettuare l'accredito al cliente.</span><span class="sxs-lookup"><span data-stu-id="129e1-168">Return the item to inventory, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129e1-169"><strong>Sostituzione e scarto</strong></span><span class="sxs-lookup"><span data-stu-id="129e1-169"><strong>Replace and scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="129e1-170">Scartare l'articolo, creare un ordine sostitutivo ed effettuare l'accredito al cliente.</span><span class="sxs-lookup"><span data-stu-id="129e1-170">Scrap the item, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129e1-171"><strong>Reso a cliente</strong></span><span class="sxs-lookup"><span data-stu-id="129e1-171"><strong>Return to customer</strong></span></span></p></td>
<td><p><span data-ttu-id="129e1-172">Rifiutare l'articolo reso e restituirlo al cliente.</span><span class="sxs-lookup"><span data-stu-id="129e1-172">Reject the returned item and return it to the customer.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a><span data-ttu-id="129e1-173">Selezionare un codice smaltimento per un ordine di quarantena</span><span class="sxs-lookup"><span data-stu-id="129e1-173">Select a disposition code for a quarantine order</span></span>

1.  <span data-ttu-id="129e1-174">Fare clic su **Gestione articoli** \> **Periodico** \> **Gestione qualità** \> **Ordini di quarantena**.</span><span class="sxs-lookup"><span data-stu-id="129e1-174">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="129e1-175">In caso di ordini di quarantena esistenti, selezionare un'azione nel campo **Codice smaltimento** della scheda **Panoramica**.</span><span class="sxs-lookup"><span data-stu-id="129e1-175">For an existing quarantine order, select an action from the **Disposition code** field on the **Overview** tab.</span></span>



## <a name="see-also"></a><span data-ttu-id="129e1-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="129e1-176">See also</span></span>

<span data-ttu-id="129e1-177">[Ordine di quarantena (modulo)](https://technet.microsoft.com/en-us/library/aa554073(v=ax.60))</span><span class="sxs-lookup"><span data-stu-id="129e1-177">[Quarantine order (form)](https://technet.microsoft.com/en-us/library/aa554073(v=ax.60))</span></span>

<span data-ttu-id="129e1-178">[Codici smaltimento (modulo)](https://technet.microsoft.com/en-us/library/hh597113\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="129e1-178">[Disposition codes (form)](https://technet.microsoft.com/en-us/library/hh597113\(v=ax.60\))</span></span>

  



