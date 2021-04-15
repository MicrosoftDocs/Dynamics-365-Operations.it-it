---
title: Specificare la modalità di smaltimento dei resi
description: Specificare la modalità di smaltimento dei resi.
author: ShylaThompson
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3eaeb2589329809e57ac01aba85067e94c15477c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817487"
---
# <a name="specify-how-to-dispose-of-returned-items"></a><span data-ttu-id="0862e-103">Specificare la modalità di smaltimento dei resi</span><span class="sxs-lookup"><span data-stu-id="0862e-103">Specify how to dispose of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="0862e-104">Quando si gestisce un ordine di reso, è necessario specificare un codice motivo reso per identificare poiché il prodotto viene restituito.</span><span class="sxs-lookup"><span data-stu-id="0862e-104">When you handle a return order, you must specify a reason return code to identify why the product is being returned.</span></span> <span data-ttu-id="0862e-105">È inoltre necessario specificare un codice smaltimento e un'azione di smaltimento per determinare cosa deve essere effettuato con il prodotto restituito.</span><span class="sxs-lookup"><span data-stu-id="0862e-105">You must also specify a disposition code and a disposition action to determine what should be done with the returned product itself.</span></span>

<span data-ttu-id="0862e-106">È possibile applicare un codice smaltimento quando si crea l'ordine di reso, si registra l'arrivo dell'articolo, si aggiorna il documento di trasporto specificando che l'articolo è arrivato oppure quando si termina un ordine di quarantena.</span><span class="sxs-lookup"><span data-stu-id="0862e-106">A disposition code can be applied when you create the return order, register item arrival or packing-slip update an item arrival, and end a quarantine order.</span></span>

<span data-ttu-id="0862e-107">È possibile definire tutti i codici smaltimento necessari per il processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="0862e-107">You can define any disposition codes that you need in order to support the business processes.</span></span> <span data-ttu-id="0862e-108">Nella tabella riportata di seguito è disponibile l'insieme dei codici più comunemente utilizzati per specificare la modalità di smaltimento dei resi.</span><span class="sxs-lookup"><span data-stu-id="0862e-108">The following table provides a set of typically used codes to assign return-item disposition.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0862e-109">Tipo di smaltimento</span><span class="sxs-lookup"><span data-stu-id="0862e-109">Disposition type</span></span></p></th>
<th><p><span data-ttu-id="0862e-110">Codice comune</span><span class="sxs-lookup"><span data-stu-id="0862e-110">Common code</span></span></p></th>
<th><p><span data-ttu-id="0862e-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0862e-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0862e-112">Dismissione</span><span class="sxs-lookup"><span data-stu-id="0862e-112">Disposal</span></span></p></td>
<td><p><span data-ttu-id="0862e-113">SC</span><span class="sxs-lookup"><span data-stu-id="0862e-113">SC</span></span></p></td>
<td><p><span data-ttu-id="0862e-114">Scarto/distruzione</span><span class="sxs-lookup"><span data-stu-id="0862e-114">Scrap/Destroy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0862e-115">Dismissione</span><span class="sxs-lookup"><span data-stu-id="0862e-115">Disposal</span></span></p></td>
<td><p><span data-ttu-id="0862e-116">Controller di dominio</span><span class="sxs-lookup"><span data-stu-id="0862e-116">DC</span></span></p></td>
<td><p><span data-ttu-id="0862e-117">Donazione in beneficenza</span><span class="sxs-lookup"><span data-stu-id="0862e-117">Donate to Charity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0862e-118">Dismissione</span><span class="sxs-lookup"><span data-stu-id="0862e-118">Disposal</span></span></p></td>
<td><p><span data-ttu-id="0862e-119">TD</span><span class="sxs-lookup"><span data-stu-id="0862e-119">TD</span></span></p></td>
<td><p><span data-ttu-id="0862e-120">Dismissione effettuata da terzi</span><span class="sxs-lookup"><span data-stu-id="0862e-120">Third-Party Disposal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0862e-121">Dismissione</span><span class="sxs-lookup"><span data-stu-id="0862e-121">Disposal</span></span></p></td>
<td><p><span data-ttu-id="0862e-122">SL</span><span class="sxs-lookup"><span data-stu-id="0862e-122">SL</span></span></p></td>
<td><p><span data-ttu-id="0862e-123">Realizzo</span><span class="sxs-lookup"><span data-stu-id="0862e-123">Salvage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0862e-124">Dismissione</span><span class="sxs-lookup"><span data-stu-id="0862e-124">Disposal</span></span></p></td>
<td><p><span data-ttu-id="0862e-125">TS</span><span class="sxs-lookup"><span data-stu-id="0862e-125">TS</span></span></p></td>
<td><p><span data-ttu-id="0862e-126">Vendita a terzi (mercati secondari)</span><span class="sxs-lookup"><span data-stu-id="0862e-126">Third-Party Sale (Secondary Markets)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0862e-127">Riparazione/Modifica</span><span class="sxs-lookup"><span data-stu-id="0862e-127">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="0862e-128">RW</span><span class="sxs-lookup"><span data-stu-id="0862e-128">RW</span></span></p></td>
<td><p><span data-ttu-id="0862e-129">Rilavorazione</span><span class="sxs-lookup"><span data-stu-id="0862e-129">Rework</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0862e-130">Riparazione/Modifica</span><span class="sxs-lookup"><span data-stu-id="0862e-130">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="0862e-131">RF</span><span class="sxs-lookup"><span data-stu-id="0862e-131">RF</span></span></p></td>
<td><p><span data-ttu-id="0862e-132">Rifabbricazione/rinnovamento</span><span class="sxs-lookup"><span data-stu-id="0862e-132">Remanufacture/Refurbish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0862e-133">Riparazione/Modifica</span><span class="sxs-lookup"><span data-stu-id="0862e-133">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="0862e-134">MD</span><span class="sxs-lookup"><span data-stu-id="0862e-134">MD</span></span></p></td>
<td><p><span data-ttu-id="0862e-135">Modifica</span><span class="sxs-lookup"><span data-stu-id="0862e-135">Modify</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0862e-136">Riparazione/Modifica</span><span class="sxs-lookup"><span data-stu-id="0862e-136">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="0862e-137">RP</span><span class="sxs-lookup"><span data-stu-id="0862e-137">RP</span></span></p></td>
<td><p><span data-ttu-id="0862e-138">Riparazione</span><span class="sxs-lookup"><span data-stu-id="0862e-138">Repair</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0862e-139">Riparazione/Modifica</span><span class="sxs-lookup"><span data-stu-id="0862e-139">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="0862e-140">RV</span><span class="sxs-lookup"><span data-stu-id="0862e-140">RV</span></span></p></td>
<td><p><span data-ttu-id="0862e-141">Restituzione al fornitore</span><span class="sxs-lookup"><span data-stu-id="0862e-141">Return to Vendor</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0862e-142">Altro</span><span class="sxs-lookup"><span data-stu-id="0862e-142">Other</span></span></p></td>
<td><p><span data-ttu-id="0862e-143">AI</span><span class="sxs-lookup"><span data-stu-id="0862e-143">AI</span></span></p></td>
<td><p><span data-ttu-id="0862e-144">Utilizzo degli articoli così come sono</span><span class="sxs-lookup"><span data-stu-id="0862e-144">Use as is</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0862e-145">Altro</span><span class="sxs-lookup"><span data-stu-id="0862e-145">Other</span></span></p></td>
<td><p><span data-ttu-id="0862e-146">RS</span><span class="sxs-lookup"><span data-stu-id="0862e-146">RS</span></span></p></td>
<td><p><span data-ttu-id="0862e-147">Rivendita</span><span class="sxs-lookup"><span data-stu-id="0862e-147">Resale</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0862e-148">Altro</span><span class="sxs-lookup"><span data-stu-id="0862e-148">Other</span></span></p></td>
<td><p><span data-ttu-id="0862e-149">EX</span><span class="sxs-lookup"><span data-stu-id="0862e-149">EX</span></span></p></td>
<td><p><span data-ttu-id="0862e-150">Scambia</span><span class="sxs-lookup"><span data-stu-id="0862e-150">Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0862e-151">Altro</span><span class="sxs-lookup"><span data-stu-id="0862e-151">Other</span></span></p></td>
<td><p><span data-ttu-id="0862e-152">MS</span><span class="sxs-lookup"><span data-stu-id="0862e-152">MS</span></span></p></td>
<td><p><span data-ttu-id="0862e-153">Varie</span><span class="sxs-lookup"><span data-stu-id="0862e-153">Miscellaneous</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0862e-154">Per ogni codice smaltimento definito, è necessario selezionare un'azione di smaltimento.</span><span class="sxs-lookup"><span data-stu-id="0862e-154">For each disposition code that you define, you must select a disposition action.</span></span> <span data-ttu-id="0862e-155">L'azione di smaltimento determina le implicazioni fisiche e finanziarie dei codici smaltimento.</span><span class="sxs-lookup"><span data-stu-id="0862e-155">The disposition action determines the physical and financial implications of the disposition codes.</span></span> <span data-ttu-id="0862e-156">Ad esempio, l'azione di smaltimento determina la gestione fisica dell'articolo reso, il relativo effetto finanziario e se è richiesto l'invio al cliente di un articolo sostitutivo.</span><span class="sxs-lookup"><span data-stu-id="0862e-156">For example, the disposition action determines the physical handling of the returned item, the financial effect of the returned item, and if a replacement item must be sent to the customer.</span></span> <span data-ttu-id="0862e-157">È possibile definire un numero illimitato di codici smaltimento in base alle proprie esigenze, ma è possibile scegliere solo tra sei azioni di smaltimento predefinite.</span><span class="sxs-lookup"><span data-stu-id="0862e-157">You can define an unlimited number of disposition codes according to your business needs, but there are only six predefined disposition actions that you can select from.</span></span> <span data-ttu-id="0862e-158">Nella tabella seguente vengono illustrate le azioni di smaltimento e le relative definizioni.</span><span class="sxs-lookup"><span data-stu-id="0862e-158">The following table provides the disposition actions and their definitions.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0862e-159">Azione di smaltimento</span><span class="sxs-lookup"><span data-stu-id="0862e-159">Disposition action</span></span></p></th>
<th><p><span data-ttu-id="0862e-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0862e-160">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0862e-161"><strong>Avere</strong></span><span class="sxs-lookup"><span data-stu-id="0862e-161"><strong>Credit</strong></span></span></p></td>
<td><p><span data-ttu-id="0862e-162">Restituire l'articolo al magazzino ed effettuare l'accredito al cliente.</span><span class="sxs-lookup"><span data-stu-id="0862e-162">Return the item to inventory and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0862e-163"><strong>Solo credito</strong></span><span class="sxs-lookup"><span data-stu-id="0862e-163"><strong>Credit only</strong></span></span></p></td>
<td><p><span data-ttu-id="0862e-164">Effettuare l'accredito al cliente senza richiedere o prevedere la restituzione dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="0862e-164">Credit the customer without requiring or expecting the item to be returned.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0862e-165"><strong>Scarti</strong></span><span class="sxs-lookup"><span data-stu-id="0862e-165"><strong>Scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="0862e-166">Scartare l'articolo ed effettuare l'accredito al cliente.</span><span class="sxs-lookup"><span data-stu-id="0862e-166">Scrap the item and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0862e-167"><strong>Sostituzione e credito</strong></span><span class="sxs-lookup"><span data-stu-id="0862e-167"><strong>Replace and credit</strong></span></span></p></td>
<td><p><span data-ttu-id="0862e-168">Restituire l'articolo al magazzino, creare un ordine sostitutivo ed effettuare l'accredito al cliente.</span><span class="sxs-lookup"><span data-stu-id="0862e-168">Return the item to inventory, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0862e-169"><strong>Sostituzione e scarto</strong></span><span class="sxs-lookup"><span data-stu-id="0862e-169"><strong>Replace and scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="0862e-170">Scartare l'articolo, creare un ordine sostitutivo ed effettuare l'accredito al cliente.</span><span class="sxs-lookup"><span data-stu-id="0862e-170">Scrap the item, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0862e-171"><strong>Reso a cliente</strong></span><span class="sxs-lookup"><span data-stu-id="0862e-171"><strong>Return to customer</strong></span></span></p></td>
<td><p><span data-ttu-id="0862e-172">Rifiutare l'articolo reso e restituirlo al cliente.</span><span class="sxs-lookup"><span data-stu-id="0862e-172">Reject the returned item and return it to the customer.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a><span data-ttu-id="0862e-173">Selezionare un codice smaltimento per un ordine di quarantena</span><span class="sxs-lookup"><span data-stu-id="0862e-173">Select a disposition code for a quarantine order</span></span>

1.  <span data-ttu-id="0862e-174">Fare clic su **Gestione articoli** \> **Periodico** \> **Gestione qualità** \> **Ordini di quarantena**.</span><span class="sxs-lookup"><span data-stu-id="0862e-174">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="0862e-175">In caso di ordini di quarantena esistenti, selezionare un'azione nel campo **Codice smaltimento** della scheda **Panoramica**.</span><span class="sxs-lookup"><span data-stu-id="0862e-175">For an existing quarantine order, select an action from the **Disposition code** field on the **Overview** tab.</span></span>



## <a name="see-also"></a><span data-ttu-id="0862e-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0862e-176">See also</span></span>

<span data-ttu-id="0862e-177">[Ordine di quarantena (modulo)](https://technet.microsoft.com/library/aa554073(v=ax.60))</span><span class="sxs-lookup"><span data-stu-id="0862e-177">[Quarantine order (form)](https://technet.microsoft.com/library/aa554073(v=ax.60))</span></span>

<span data-ttu-id="0862e-178">[Codici smaltimento (modulo)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="0862e-178">[Disposition codes (form)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))</span></span>

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]