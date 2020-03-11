---
title: Reimpostare numeri di ricevuta
description: Questo argomento descrive come reimpostare i numeri di ricevuta utilizzati per varie azioni a una determinata data (ad esempio, l'anno fiscale o l'anno di calendario).
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-Commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail, Commerce
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Application update 10.0.9
ms.openlocfilehash: e81ff86a8b8a4dca6b14a21d6e982b03a928d29e
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020080"
---
# <a name="reset-receipt-numbers"></a><span data-ttu-id="22108-103">Reimpostare numeri di ricevuta</span><span class="sxs-lookup"><span data-stu-id="22108-103">Reset receipt numbers</span></span> 

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="22108-104">I rivenditori generano numeri di ricevuta per varie azioni nel punto vendita, come ad esempio transazioni cash-and-carry, transazioni di reso, ordini cliente, offerte e pagamenti.</span><span class="sxs-lookup"><span data-stu-id="22108-104">Retailers generate receipt numbers for various actions in the store, such as cash and carry transactions, return transactions, customer orders, quotations, and payments.</span></span> <span data-ttu-id="22108-105">Sebbene i rivenditori definiscano i propri formati di ricevuta, alcuni paesi o aree geografiche hanno normative che impongono restrizioni a questi formati di ricevute.</span><span class="sxs-lookup"><span data-stu-id="22108-105">Although retailers define their own receipt formats, some countries or regions have regulations that put restrictions on these receipt formats.</span></span> <span data-ttu-id="22108-106">Ad esempio, queste normative potrebbero limitare il numero di caratteri sulla ricevuta, richiedere numeri di ricevuta consecutivi, limitare alcuni caratteri speciali o richiedere un azzeramento dei numeri di ricevuta all'inizio dell'anno.</span><span class="sxs-lookup"><span data-stu-id="22108-106">For example, these regulations might limit the number of characters on the receipt, require consecutive receipt numbers, restrict some special characters, or require a reset of receipt numbers at the beginning of the year.</span></span> <span data-ttu-id="22108-107">Microsoft Dynamics 365 Commerce rende estremamente flessibile il processo di gestione dei numeri di ricevuta, per aiutare i rivenditori a soddisfare i requisiti normativi.</span><span class="sxs-lookup"><span data-stu-id="22108-107">Microsoft Dynamics 365 Commerce makes the process of managing receipt numbers very flexible, to help retailers meet regulatory requirements.</span></span> <span data-ttu-id="22108-108">Questo argomento descrive come utilizzare la funzionalità di reimpostazioni dei numeri di ricevuta.</span><span class="sxs-lookup"><span data-stu-id="22108-108">This topic explains how to use the functionality for resetting receipt numbers.</span></span>

<span data-ttu-id="22108-109">In Commerce, i formati delle ricevute possono essere alfanumerici.</span><span class="sxs-lookup"><span data-stu-id="22108-109">In Commerce, receipt formats can be alphanumeric.</span></span> <span data-ttu-id="22108-110">È possibile inserire sia contenuto statico che contenuto dinamico.</span><span class="sxs-lookup"><span data-stu-id="22108-110">You can put both static content and dynamic content in them.</span></span> <span data-ttu-id="22108-111">Il contenuto statico include caratteri alfabetici, numeri e caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="22108-111">Static content includes alphabetic character, numbers, and special characters.</span></span> <span data-ttu-id="22108-112">Il contenuto dinamico include uno o più caratteri che rappresentano informazioni come il numero di punto vendita, il numero di terminale, la data, il mese, l'anno e le sequenze numeriche che vengono incrementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="22108-112">Dynamic content includes one or more characters that represent information such as the store number, terminal number, date, month, year, and number sequences that are automatically incremented.</span></span> <span data-ttu-id="22108-113">I formati sono definiti nella sezione **Numerazione ricevute** del profilo della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="22108-113">The formats are defined in the **Receipt numbering** section of the functionality profile.</span></span> <span data-ttu-id="22108-114">La tabella seguente descrive i caratteri che rappresentano il contenuto dinamico.</span><span class="sxs-lookup"><span data-stu-id="22108-114">The following table describes the characters that represent the dynamic content.</span></span>

| <span data-ttu-id="22108-115">Caratteri</span><span class="sxs-lookup"><span data-stu-id="22108-115">Characters</span></span> | <span data-ttu-id="22108-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22108-116">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="22108-117">S</span><span class="sxs-lookup"><span data-stu-id="22108-117">S</span></span>          | <span data-ttu-id="22108-118">Il carattere **S** viene utilizzato per il numero di punto vendita.</span><span class="sxs-lookup"><span data-stu-id="22108-118">The character **S** is used for the store number.</span></span> <span data-ttu-id="22108-119">Ad esempio, se il numero di un punto vendita è HOUSTON1, il formato **SSS** mostra "ON1" sulla ricevuta.</span><span class="sxs-lookup"><span data-stu-id="22108-119">For example, if a store is numbered HOUSTON1, the format **SSS** shows "ON1" on the receipt.</span></span> <span data-ttu-id="22108-120">Il formato **SSSSS** mostra "STON1" sulla ricevuta.</span><span class="sxs-lookup"><span data-stu-id="22108-120">The format **SSSSS** shows "STON1" on the receipt.</span></span> |
| <span data-ttu-id="22108-121">T</span><span class="sxs-lookup"><span data-stu-id="22108-121">T</span></span>          | <span data-ttu-id="22108-122">Il carattere **T** viene utilizzato per il numero di terminale.</span><span class="sxs-lookup"><span data-stu-id="22108-122">The character **T** is used for the terminal number.</span></span> <span data-ttu-id="22108-123">Ad esempio, se il numero di un terminale è 0001, il formato **TTTT** mostra "0001" sulla ricevuta.</span><span class="sxs-lookup"><span data-stu-id="22108-123">For example, if a terminal is numbered 0001, the format **TTTT** shows "0001" on the receipt.</span></span> |
| <span data-ttu-id="22108-124">C</span><span class="sxs-lookup"><span data-stu-id="22108-124">C</span></span>          | <span data-ttu-id="22108-125">Il carattere **C** viene utilizzato per il numero di ID personale.</span><span class="sxs-lookup"><span data-stu-id="22108-125">The character **C** is used for the staff ID number.</span></span> <span data-ttu-id="22108-126">Ad esempio, se l'ID di un membro del personale è 000160, il formato **CCCC** mostra "0160" sulla ricevuta.</span><span class="sxs-lookup"><span data-stu-id="22108-126">For example, if a staff member has an ID of 000160, the format **CCCC** shows "0160" on the receipt.</span></span> |
| <span data-ttu-id="22108-127">ggg</span><span class="sxs-lookup"><span data-stu-id="22108-127">ddd</span></span>        | <span data-ttu-id="22108-128">I caratteri **ggg** corrispondono al giorno dell'anno, dall'1 al 366.</span><span class="sxs-lookup"><span data-stu-id="22108-128">The characters **ddd** correspond to the day of the year, from 1 through 366.</span></span> <span data-ttu-id="22108-129">Ad esempio, il 15 gennaio, il formato **ggg** mostra "015" sulla ricevuta.</span><span class="sxs-lookup"><span data-stu-id="22108-129">For example, on January 15, the format **ddd** shows "015" on the receipt.</span></span> |
| <span data-ttu-id="22108-130">MM</span><span class="sxs-lookup"><span data-stu-id="22108-130">MM</span></span>         | <span data-ttu-id="22108-131">I caratteri **MM** vengono utilizzati per il mese a due cifre.</span><span class="sxs-lookup"><span data-stu-id="22108-131">The characters **MM** are used for the two-digit month.</span></span> <span data-ttu-id="22108-132">Ad esempio, in gennaio, il formato **MM** mostra "01" sulla ricevuta.</span><span class="sxs-lookup"><span data-stu-id="22108-132">For example, in January, the format **MM** show "01" on the receipt.</span></span> |
| <span data-ttu-id="22108-133">GG</span><span class="sxs-lookup"><span data-stu-id="22108-133">DD</span></span>         | <span data-ttu-id="22108-134">I caratteri **GG** vengono utilizzati per il giorno del mese a due cifre.</span><span class="sxs-lookup"><span data-stu-id="22108-134">The characters **DD** are used for the two-digit day of the month.</span></span> <span data-ttu-id="22108-135">Ad esempio, il 15 gennaio, il formato **GG** mostra "15" sulla ricevuta.</span><span class="sxs-lookup"><span data-stu-id="22108-135">For example, on January 15, the format **DD** shows "15" on the receipt.</span></span> |
| <span data-ttu-id="22108-136">AA</span><span class="sxs-lookup"><span data-stu-id="22108-136">YY</span></span>         | <span data-ttu-id="22108-137">I caratteri **AA** vengono utilizzati per l'anno a due cifre.</span><span class="sxs-lookup"><span data-stu-id="22108-137">The characters **YY** are used for the two-digit year.</span></span> <span data-ttu-id="22108-138">Ad esempio, in qualsiasi mese dell'anno 2020, il formato **AA** mostra "20" sulla ricevuta.</span><span class="sxs-lookup"><span data-stu-id="22108-138">For example, in any month during the year 2020, the format **YY** shows "20" on the receipt.</span></span> |
| \#         | <span data-ttu-id="22108-139">Un segno numerico ( **\#**) viene utilizzato per la numerazione sequenziale.</span><span class="sxs-lookup"><span data-stu-id="22108-139">A number sign (**\#**) is used for sequential numbering.</span></span> <span data-ttu-id="22108-140">Ad esempio, il formato **####** mostra "0001", "0002", "0003" e così via sulla ricevuta.</span><span class="sxs-lookup"><span data-stu-id="22108-140">For example, the format **####** shows "0001," "0002," "0003," and so on, on the receipt.</span></span> |

<span data-ttu-id="22108-141">È possibile reimpostare la numerazione sequenziale della ricevuta a una data specifica.</span><span class="sxs-lookup"><span data-stu-id="22108-141">You can reset the sequential numbering of the receipt on a specific date.</span></span> <span data-ttu-id="22108-142">Quindi, per la prima transazione che si verifica dopo le 00:00 alla data di azzeramento selezionata, il sistema reimposta la sequenza numerica della ricevuta su 1.</span><span class="sxs-lookup"><span data-stu-id="22108-142">Then, for the first transaction that occurs after 12:00 AM on the selected reset date, the system resets the receipt's number sequence to 1.</span></span> <span data-ttu-id="22108-143">È inoltre possibile specificare se la reimpostazione si verifica una sola volta o se si ripete ogni anno.</span><span class="sxs-lookup"><span data-stu-id="22108-143">You can also specify whether the reset occurs only one time, or whether it recurs every year.</span></span> <span data-ttu-id="22108-144">Se viene specificata la ricorrenza annuale, la reimpostazione si verifica automaticamente ogni anno fino a quando il rivenditore non decide di interromperla.</span><span class="sxs-lookup"><span data-stu-id="22108-144">If yearly recurrence is specified, the reset automatically occurs every year until the retailer chooses to stop it.</span></span> 

<span data-ttu-id="22108-145">Per attivare la reimpostazione, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="22108-145">To turn on the reset, follow these steps.</span></span>

1. <span data-ttu-id="22108-146">Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Profili POS \> Profili funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="22108-146">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="22108-147">Nella Scheda dettaglio **Numerazione ricevute**, selezionare **Reimposta data di azzeramento numero**.</span><span class="sxs-lookup"><span data-stu-id="22108-147">On the **Receipt numbering** FastTab, select **Reset number reset date**.</span></span>
1. <span data-ttu-id="22108-148">Nella finestra di dialogo a discesa, in **Data di azzeramento**, selezionare la data futura alla quale dovrebbe avvenire la reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="22108-148">In the drop-down dialog box, in the **Reset date** field, select a future date when the reset should occur.</span></span>
1. <span data-ttu-id="22108-149">Nel campo **Reimposta tipo di ricevuta**, selezionare **Una sola volta** o **Ogni anno**.</span><span class="sxs-lookup"><span data-stu-id="22108-149">In the **Reset receipt type** field, select **One time only** or **Yearly**.</span></span>
1. <span data-ttu-id="22108-150">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="22108-150">Select **OK**.</span></span>

<span data-ttu-id="22108-151">![Selezionare la data di azzeramento delle ricevute](media/Enable_receipt_reset.png "Selezionare la data di azzeramento delle ricevute")</span><span class="sxs-lookup"><span data-stu-id="22108-151">![Selecting a receipt reset date](media/Enable_receipt_reset.png "Selecting a receipt reset date")</span></span>

<span data-ttu-id="22108-152">Dopo aver selezionato una data, questa appare nella colonna **Data di azzeramento numero di ricevuta successiva**.</span><span class="sxs-lookup"><span data-stu-id="22108-152">After you select a date, it appears in the **Next receipt number reset date** column.</span></span> <span data-ttu-id="22108-153">La data di azzeramento è applicabile a tutti i tipi di transazioni di ricevuta.</span><span class="sxs-lookup"><span data-stu-id="22108-153">The reset date is applicable to all receipt transaction types.</span></span> <span data-ttu-id="22108-154">Pertanto, la sequenza del numero di ricevuta verrà reimpostata per tutti i tipi di ricevuta.</span><span class="sxs-lookup"><span data-stu-id="22108-154">Therefore, the receipt number sequence will be reset for all receipt types.</span></span>

<span data-ttu-id="22108-155">Alla data di azzeramento, il numero di ricevuta viene reimpostato per la prima transazione di ogni tipo.</span><span class="sxs-lookup"><span data-stu-id="22108-155">When the reset date arrives, the receipt number is reset for the first transaction of each type.</span></span> <span data-ttu-id="22108-156">Inoltre, nel profilo delle funzionalità, la data di azzeramento viene spostata dalla colonna **Data di azzeramento numero di ricevuta successiva** alla colonna **Data di azzeramento numero di ricevuta corrente**.</span><span class="sxs-lookup"><span data-stu-id="22108-156">In addition, in the functionality profile, the reset date is moved from the **Next receipt number reset date** column to the **Current receipt number reset date** column.</span></span> <span data-ttu-id="22108-157">Questa modifica indica che se un registro non viene utilizzato alla data di azzeramento, il numero di ricevuta verrà reimpostato la volta successiva che il registro *è* utilizzato.</span><span class="sxs-lookup"><span data-stu-id="22108-157">This change indicates that if a register isn't used on the reset date, the receipt number will be reset the next time that the register *is* used.</span></span> <span data-ttu-id="22108-158">Ad esempio, il 3 dicembre 2019, si seleziona **1 gennaio 2020**, come data di azzeramento.</span><span class="sxs-lookup"><span data-stu-id="22108-158">For example, on December 3, 2019, you select **January 1, 2020**, as the reset date.</span></span> <span data-ttu-id="22108-159">Il 1° gennaio, quando i registri effettuano la prima transazione, il numero di ricevuta viene reimpostato.</span><span class="sxs-lookup"><span data-stu-id="22108-159">On January 1, when the registers make their first transaction, the receipt number are reset.</span></span> <span data-ttu-id="22108-160">Tuttavia, un registro non viene utilizzato affatto a dicembre e gennaio, ma inizia a essere utilizzato a febbraio.</span><span class="sxs-lookup"><span data-stu-id="22108-160">However, one register isn't used at all during December and January, but then starts to be used in February.</span></span> <span data-ttu-id="22108-161">In questo caso, poiché è stata definita un'azione di reimpostazione, il numero di ricevuta per quel registro verrà reimpostato quando il registro effettua la prima transazione a febbraio.</span><span class="sxs-lookup"><span data-stu-id="22108-161">In this case, because a reset action was defined, the receipt number for that register will be reset when the register makes its first transaction in February.</span></span>

<span data-ttu-id="22108-162">È possibile utilizzare la funzionalità **Annulla data di azzeramento** per annullare le date di azzeramento future.</span><span class="sxs-lookup"><span data-stu-id="22108-162">You can use the **Clear reset date** functionality to clear future reset dates.</span></span> <span data-ttu-id="22108-163">Tuttavia, se la data di azzeramento si è verificata in passato, non può essere annullata.</span><span class="sxs-lookup"><span data-stu-id="22108-163">However, if the reset date occurred in the past, it can't be undone.</span></span> <span data-ttu-id="22108-164">Pertanto, la reimpostazione verrà comunque eseguita per tutti i registri in cui la reimpostazione non è ancora stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="22108-164">Therefore, the reset will still occur for all registers where the reset hasn't yet occurred.</span></span>

> [!NOTE]
> <span data-ttu-id="22108-165">A seconda della data di azzeramento selezionata e del formato della ricevuta, è possibile che si abbiano numeri di ricevuta duplicati.</span><span class="sxs-lookup"><span data-stu-id="22108-165">Depending on the reset date that you select, and the receipt format, you might have duplicate receipt numbers.</span></span> <span data-ttu-id="22108-166">Sebbene il sistema POS sia in grado di gestire queste situazioni, queste aumentano la quantità di tempo necessaria per elaborare i resi poiché gli addetti alle vendite devono scegliere tra le ricevute duplicate.</span><span class="sxs-lookup"><span data-stu-id="22108-166">Although the point of sale (POS) system can handle these situations, they increase the amount of time that is required to process returns, because sales associates must select among the duplicate receipts.</span></span> <span data-ttu-id="22108-167">Altre complicazioni legate alla pulizia dei dati possono verificarsi se le ricevute duplicate non erano una conseguenza pianificata.</span><span class="sxs-lookup"><span data-stu-id="22108-167">Other complications that are related to data cleanup can occur if the duplicate receipts weren't a planned consequence.</span></span> <span data-ttu-id="22108-168">Pertanto, si consiglia di utilizzare caratteri di data dinamici (ad esempio, **ggg**, **MM**, **DD** e **AA**) per evitare numeri di ricevuta duplicati dopo una reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="22108-168">Therefore, we recommend that you use dynamic date characters (for example, **ddd**, **MM**, **DD**, and **YY**) to help prevent duplicate receipt numbers after a reset.</span></span>