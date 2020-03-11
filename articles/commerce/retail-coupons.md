---
title: Impostare buoni sconto per le vendite al dettaglio
description: In questo argomento viene fornita una panoramica dei buoni sconto e illustra come configurarli.
author: scott-tucker
manager: AnnBe
ms.date: 05/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailCoupon, RetailParameters, RetailSharedParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: scotttuc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 4c580e40ae1f0398ab9f8437d42ddcb2979558c3
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057373"
---
# <a name="set-up-coupons-for-retail-sales"></a><span data-ttu-id="320ed-103">Impostare buoni sconto per le vendite al dettaglio</span><span class="sxs-lookup"><span data-stu-id="320ed-103">Set up coupons for retail sales</span></span>

[!include [banner](includes/banner.md)]

## <a name="overview-of-coupons"></a><span data-ttu-id="320ed-104">Panoramica dei buoni sconto</span><span class="sxs-lookup"><span data-stu-id="320ed-104">Overview of coupons</span></span>

<span data-ttu-id="320ed-105">I buoni sconto sono codici e codici a barre utilizzati per aggiungere sconti alle transazioni.</span><span class="sxs-lookup"><span data-stu-id="320ed-105">Coupons are codes and bar codes that are used to add discounts to transactions.</span></span> <span data-ttu-id="320ed-106">Ogni buono sconto può avere più codici e ogni codice può avere una propria data di validità.</span><span class="sxs-lookup"><span data-stu-id="320ed-106">Each coupon can have multiple codes, and each code can have its own effective dates.</span></span>

<span data-ttu-id="320ed-107">Ogni buono sconto è relativo a uno sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-107">Each coupon is related to one discount.</span></span> <span data-ttu-id="320ed-108">I gruppi di prezzi associati allo sconto definiscono i clienti che possono utilizzare un buono sconto o i canali in cui un buono sconto è valido.</span><span class="sxs-lookup"><span data-stu-id="320ed-108">The price groups that are associated with the discount define the customers that can use a coupon or the channels where a coupon is valid.</span></span>

<span data-ttu-id="320ed-109">Essenzialmente, i buoni sconto rappresentano una convalida aggiuntiva sugli sconti.</span><span class="sxs-lookup"><span data-stu-id="320ed-109">Essentially, coupons are additional validation on top of discounts.</span></span> <span data-ttu-id="320ed-110">Il buono sconto fornisce i codici e i codici a barre necessari dei buoni sconto, insieme a intervalli di date per tali codici.</span><span class="sxs-lookup"><span data-stu-id="320ed-110">The coupon provides the coupon codes and bar codes that are required, together with date ranges for those codes.</span></span> <span data-ttu-id="320ed-111">Il buono sconto fornisce inoltre i limiti facoltativi di utilizzo e le proprietà obbligatorie del cliente.</span><span class="sxs-lookup"><span data-stu-id="320ed-111">The coupon also provides optional usage limits and customer required properties.</span></span> <span data-ttu-id="320ed-112">Lo sconto fornisce un set di prodotti per cui il buono sconto è valido.</span><span class="sxs-lookup"><span data-stu-id="320ed-112">The discount provides the set of products that the coupon is valid for.</span></span> <span data-ttu-id="320ed-113">I gruppi di prezzi per lo sconto forniscono il set di clienti, canali o cataloghi per cui il buono sconto è valido.</span><span class="sxs-lookup"><span data-stu-id="320ed-113">The price groups for the discount provide the set of customers, channels, or catalogs that the coupon is valid for.</span></span>

<span data-ttu-id="320ed-114">Per creare un buono sconto, verranno creati separatamente lo sconto e il buono sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-114">To create a coupon, you create the discount and the coupon separately.</span></span> <span data-ttu-id="320ed-115">Quindi vengono collegati selezionando lo sconto nella pagina dei buoni sconto in Commerce.</span><span class="sxs-lookup"><span data-stu-id="320ed-115">You then link them by selecting the discount on the coupon page in Commerce.</span></span>

> [!NOTE]
> <span data-ttu-id="320ed-116">Dopo che un buono sconto è stato collegato a uno sconto, diversi campi presenti nella pagina dei buoni sconto in Commerce diventano di sola lettura, poiché vengono gestiti dalle impostazioni del buono sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-116">After a coupon is linked to a discount, several fields on the discount page in Commerce become read-only, because they are managed by the coupon's settings.</span></span> <span data-ttu-id="320ed-117">Questi campi includono i campi per lo stato e gli intervalli di date standard.</span><span class="sxs-lookup"><span data-stu-id="320ed-117">These fields include the fields for the status and standard date ranges.</span></span>

### <a name="limited-use-coupons"></a><span data-ttu-id="320ed-118">Buoni sconti a utilizzo limitato</span><span class="sxs-lookup"><span data-stu-id="320ed-118">Limited-use coupons</span></span>

<span data-ttu-id="320ed-119">I buoni sconto possono essere configurati come a utilizzo limitato.</span><span class="sxs-lookup"><span data-stu-id="320ed-119">Coupons can be configured as limited-use coupons.</span></span> <span data-ttu-id="320ed-120">Il limite di utilizzo può essere definito per cliente o canale, o come limite globale.</span><span class="sxs-lookup"><span data-stu-id="320ed-120">The usage limit can be defined per customer or channel, or as a global limit.</span></span> <span data-ttu-id="320ed-121">Questo limite viene applicato quando il codice o il codice a barre viene immesso o letto nel POS o durante la registrazione dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="320ed-121">This limit is enforced when the code or bar code is entered or scanned in POS or during sales order entry.</span></span>

<span data-ttu-id="320ed-122">Il limite viene applicato per codice buono sconto su un buono sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-122">The limit is enforced per coupon code on a coupon.</span></span> <span data-ttu-id="320ed-123">Ad esempio, un singolo buono sconto che contiene due codici buono sconto può essere utilizzato due volte: una volta per ogni codice del buono sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-123">For example, a single-use coupon that has two coupon codes can be used two times: one time for each coupon code.</span></span> <span data-ttu-id="320ed-124">Ogni codice su un buono sconto può essere impostato indipendentemente su Attivo.</span><span class="sxs-lookup"><span data-stu-id="320ed-124">Each code on a coupon can be independently set to active.</span></span>

> [!NOTE]
> <span data-ttu-id="320ed-125">Dopo che un numero di buono sconto ha raggiunto il limite di utilizzo, il sistema *non* modifica automaticamente lo stato del codice del buono sconto utilizzato a "Utilizzato".</span><span class="sxs-lookup"><span data-stu-id="320ed-125">Once a coupon code has reached its usage limit, the system does *not* automatically change the status of the coupon code to "Used".</span></span> <span data-ttu-id="320ed-126">Il sistema, tuttavia, non consente l'ulteriore utilizzo di un numero di buono sconto che ha raggiunto il limite di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="320ed-126">The system however, does not allow further usage of a coupon code which has reached its usage limit.</span></span> <span data-ttu-id="320ed-127">Se lo stato di un numero di buono sconto viene impostato manualmente su un valore diverso da "Attivo", il codice di buono sconto non può essere utilizzato in nessun canale.</span><span class="sxs-lookup"><span data-stu-id="320ed-127">If the status of a coupon code is manually set to anything apart from "Active" then this coupon code cannot be used in any channel.</span></span>

## <a name="managing-coupons"></a><span data-ttu-id="320ed-128">Gestione dei buoni sconto</span><span class="sxs-lookup"><span data-stu-id="320ed-128">Managing coupons</span></span>

<span data-ttu-id="320ed-129">Lo sconto e il buono sconto devono essere creati separatamente.</span><span class="sxs-lookup"><span data-stu-id="320ed-129">You must create the discount and the coupon separately.</span></span> <span data-ttu-id="320ed-130">Quindi vengono collegati selezionando lo sconto nella pagina del buono sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-130">You then link them by selecting the discount on the coupon page.</span></span> <span data-ttu-id="320ed-131">Dopo che un buono sconto è stato collegato a uno sconto, diversi campi per lo sconto diventano di sola lettura, poiché vengono gestiti dalle impostazioni del buono sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-131">After you link a coupon to a discount, several fields for the discount become read-only, because they are managed by the coupon's settings.</span></span> <span data-ttu-id="320ed-132">Questi campi includono i campi per lo stato e gli intervalli di date standard.</span><span class="sxs-lookup"><span data-stu-id="320ed-132">These fields include the fields for the status and standard date ranges.</span></span>

<span data-ttu-id="320ed-133">Essenzialmente, i buoni sconto ora rappresentano una convalida aggiuntiva sugli sconti.</span><span class="sxs-lookup"><span data-stu-id="320ed-133">Essentially, coupons are now additional validation on top of discounts.</span></span> <span data-ttu-id="320ed-134">Il buono sconto fornisce i codici e i codici a barre necessari dei buoni sconto, insieme a intervalli di date, limite di utilizzo e la proprietà obbligatoria del cliente.</span><span class="sxs-lookup"><span data-stu-id="320ed-134">The coupon provides the coupon codes and bar codes, together with date ranges, the usage limits, and the customer required property.</span></span> <span data-ttu-id="320ed-135">Lo sconto fornisce un set di prodotti per cui il buono sconto è valido.</span><span class="sxs-lookup"><span data-stu-id="320ed-135">The discount provides the set of products that the coupon is valid for.</span></span> <span data-ttu-id="320ed-136">I gruppi di prezzi dello sconto forniscono il set di clienti, canali o cataloghi per cui il buono sconto è valido.</span><span class="sxs-lookup"><span data-stu-id="320ed-136">The discount's price groups provide the set of customers, channels, or catalogs that the coupon is valid for.</span></span>

## <a name="system-setup-for-coupons"></a><span data-ttu-id="320ed-137">Configurazione di sistema per i buoni sconto</span><span class="sxs-lookup"><span data-stu-id="320ed-137">System setup for coupons</span></span>

<span data-ttu-id="320ed-138">Prima di impostare un buono sconto, è necessario impostare il codice a barre del buono sconto e due sequenze numeriche di buoni sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-138">Before you can set up a coupon, you must set up the coupon bar code and two coupon number sequences.</span></span>

1. <span data-ttu-id="320ed-139">Nella pagina **Caratteri maschera**, creare un nuovo carattere maschera per il codice buono sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-139">On the **Mask characters** page, create a new mask character for the coupon code.</span></span> <span data-ttu-id="320ed-140">È possibile selezionare qualsiasi carattere non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="320ed-140">You can select any unused character.</span></span>
2. <span data-ttu-id="320ed-141">Nella pagina **Impostazione maschera codice a barre**, creare una nuova maschera codice a barre.</span><span class="sxs-lookup"><span data-stu-id="320ed-141">On the **Bar code mask setup** page, create a new bar code mask.</span></span> <span data-ttu-id="320ed-142">Impostare il campo **Tipo** su **Buono sconto**.</span><span class="sxs-lookup"><span data-stu-id="320ed-142">Set the **Type** field to **Coupon**.</span></span>
3. <span data-ttu-id="320ed-143">Nella pagina **Impostazione codice a barre**, creare un nuovo codice a barre che utilizza la maschera codice a barre appena creata.</span><span class="sxs-lookup"><span data-stu-id="320ed-143">On the **Bar code setup** page, create a new bar code that uses the bar code mask that you just created.</span></span>
4. <span data-ttu-id="320ed-144">Nella pagina **Sequenze numeriche**, creare due nuove sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="320ed-144">On the **Number sequences** page, create two new number sequences.</span></span> <span data-ttu-id="320ed-145">Una sequenza è per l'ID del codice di buono sconto e l'altra sequenza è per il numero di buono sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-145">One sequence is for the coupon code ID, and the other sequence is for the coupon number.</span></span> <span data-ttu-id="320ed-146">L'ID del codice buono sconto è l'identificatore univoco per ciascun codice buono sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-146">The coupon code ID is the unique identifier for each coupon code for a coupon.</span></span> <span data-ttu-id="320ed-147">Il numero del buono sconto è l'identificatore univoco per un buono sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-147">The coupon number is the unique identifier for a coupon.</span></span> <span data-ttu-id="320ed-148">Ciascun buono sconto può avere più codici e codici a barre che attivano il buono sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-148">Each coupon can have multiple codes and bar codes that trigger the coupon.</span></span>

    > [!NOTE]
    > <span data-ttu-id="320ed-149">Per entrambe le sequenze numeriche, è necessario impostare il campo **Ambito** su **Società**.</span><span class="sxs-lookup"><span data-stu-id="320ed-149">For both number sequences, you must set the **Scope** field to **Company**.</span></span> <span data-ttu-id="320ed-150">Nella maggior parte dei casi, è necessario generare automaticamente entrambe i numeri della sequenza.</span><span class="sxs-lookup"><span data-stu-id="320ed-150">In most cases, you should automatically generate both sequence numbers.</span></span>

5. <span data-ttu-id="320ed-151">Nella pagina **Parametri di commercio**, nella scheda **Codici a barre**, selezionare il codice a barre creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="320ed-151">On the **Commerce parameters** page, on the **Bar codes** tab, select the bar code that you created earlier.</span></span>
6. <span data-ttu-id="320ed-152">Nella pagina **Parametri condivisi di commercio**, nella scheda **Sequenze numeriche**, selezionare le sequenze numeriche create per il numero di buono sconto e ID codice buono sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-152">On the **Commerce shared parameters** page, on the **Number sequences** tab, select the number sequences that you created for the coupon number and coupon code ID.</span></span>
7. <span data-ttu-id="320ed-153">È ora possibile aprire la pagina **Buoni sconto** e creare nuovi buoni sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-153">You can now open the **Coupons** page and create new coupons.</span></span>

## <a name="the-effect-of-partial-updates-on-coupons"></a><span data-ttu-id="320ed-154">Effetto degli aggiornamenti parziali sui buoni sconto</span><span class="sxs-lookup"><span data-stu-id="320ed-154">The effect of partial updates on coupons</span></span>

<span data-ttu-id="320ed-155">La funzionalità Buono sconto include diverse funzionalità distinte.</span><span class="sxs-lookup"><span data-stu-id="320ed-155">Coupon functionality comprises multiple distinct features.</span></span> <span data-ttu-id="320ed-156">Commerce Headquarters (HQ) e il canale possono essere parzialmente aggiornati sui componenti.</span><span class="sxs-lookup"><span data-stu-id="320ed-156">Commerce Headquarters (HQ) and the channel can be partially updated across components.</span></span> <span data-ttu-id="320ed-157">Di conseguenza, è importante comprendere come gli aggiornamenti parziali influiscono complessivamente sulla funzionalità dei buoni sconto.</span><span class="sxs-lookup"><span data-stu-id="320ed-157">Therefore, it's important that you understand how partial updates affect coupon functionality as a whole.</span></span>

- <span data-ttu-id="320ed-158">**HQ è parzialmente aggiornato, ma Commerce Scale Unit e POS non vengono aggiornati.**</span><span class="sxs-lookup"><span data-stu-id="320ed-158">**HQ is partially updated, but Commerce Scale Unit and POS aren't updated.**</span></span> <span data-ttu-id="320ed-159">In un aggiornamento HQ, il buono sconto e le pagine di sconto vengono aggiornati e il motore dei prezzi di commercio viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="320ed-159">In an HQ update, the coupon and discount pages are updated, and the commerce price engine is also updated.</span></span> <span data-ttu-id="320ed-160">Se uno solo di questi due componenti viene aggiornato, alcune pagine in Commerce non corrisponderanno ai dati del calcolo dei prezzi.</span><span class="sxs-lookup"><span data-stu-id="320ed-160">If only one of those two components is updated, some pages in Commerce won't match the price calculation data.</span></span> <span data-ttu-id="320ed-161">Di conseguenza, calcoli degli sconti imprevisti o errori possono verificarsi durante i calcoli degli sconti.</span><span class="sxs-lookup"><span data-stu-id="320ed-161">Therefore, unexpected discount calculations or errors might occur during discount calculations.</span></span>
- <span data-ttu-id="320ed-162">**HQ è aggiornato, ma Commerce Scale Unit e POS non vengono aggiornati (N-1).**</span><span class="sxs-lookup"><span data-stu-id="320ed-162">**HQ is updated, but Commerce Scale Unit and POS aren't updated (N-1).**</span></span> <span data-ttu-id="320ed-163">Poiché non tutti i punti vendita possono essere aggiornati contemporaneamente, si consiglia di aggiornare HQ prima di aggiornare i punti vendita.</span><span class="sxs-lookup"><span data-stu-id="320ed-163">Because not all stores can be updated at the same time, we recommend that you update HQ before you update stores.</span></span> <span data-ttu-id="320ed-164">Nello scenario N-1, le nuove funzionalità correlate ai buoni sconto non saranno disponibili nei punti vendita che non sono stati ancora aggiornati.</span><span class="sxs-lookup"><span data-stu-id="320ed-164">In the N-1 scenario, new functionality that is related to coupons won't be available in stores that haven't been updated yet.</span></span> <span data-ttu-id="320ed-165">Ad esempio, la funzionalità dei buoni sconto introduce l'esclusione delle righe.</span><span class="sxs-lookup"><span data-stu-id="320ed-165">For example, the coupon functionality introduces "exclude" lines.</span></span> <span data-ttu-id="320ed-166">Se si utilizza l'esclusione delle righe in uno sconto, questo non verrà applicato in un punto vendita che esegue una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="320ed-166">If you use exclude lines on a discount, they won't be applied in a store that is running an earlier version.</span></span>
- <span data-ttu-id="320ed-167">**HQ non è aggiornato, ma Commerce Scale Unit e POS vengono aggiornati (N+1).**</span><span class="sxs-lookup"><span data-stu-id="320ed-167">**HQ isn't updated, but Commerce Scale Unit and POS are updated (N+1).**</span></span> <span data-ttu-id="320ed-168">Poiché il motore dei prezzi aggiornato in Commerce Scale Unit è in grado di gestire i codici sconto legacy durante i calcoli dei prezzi, l'aggiornamento non dovrebbe avere alcun impatto funzionale in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="320ed-168">Because the updated price engine in Commerce Scale Unit can handle legacy discount codes during price calculations, the update should have no functional impact in this scenario.</span></span>