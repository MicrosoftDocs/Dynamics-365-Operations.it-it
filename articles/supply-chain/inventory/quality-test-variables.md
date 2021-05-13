---
title: Variabili di test di gestione qualità
description: Questo argomento descrive come creare variabili di test che possano essere utilizzati per i test qualitativi in ordini di controllo qualità in Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e94972b41baf3f59a633fa7bbc7434abfb90460
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956714"
---
# <a name="quality-management-test-variables"></a><span data-ttu-id="fa5b9-103">Variabili di test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="fa5b9-103">Quality management test variables</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fa5b9-104">Questo argomento descrive come creare variabili di test che possano essere utilizzati per i test qualitativi in ordini di controllo qualità in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-104">This topic describes how to create test variables that can be used for qualitative tests on quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="fa5b9-105">È necessario definire una variabile di test e i possibili relativi risultati per ogni test qualitativo definito nella pagina **Test**.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-105">For every qualitative test that is defined on the **Tests** page, you must define a test variable and its possible outcomes (results).</span></span> <span data-ttu-id="fa5b9-106">(Per i test qualitativi, il campo **Tipo** nella pagina **Test** è impostato su *Opzione*).</span><span class="sxs-lookup"><span data-stu-id="fa5b9-106">(For qualitative tests, the **Type** field on the **Tests** page is set to *Option*.)</span></span>

<span data-ttu-id="fa5b9-107">Utilizzare la pagina **Variabili di test** per impostare, modificare e visualizzare i possibili risultati di una variabile di test associata a un test qualitativo.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-107">You use the **Test variables** page to set up, edit, and view the possible outcomes for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="fa5b9-108">Per ogni risultato, si assegna uno stato di risultato tra *Superato* e *Non superato* per indicare se il test è superato o meno quando tale risultato viene selezionato come risultato del test.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-108">For each outcome, you assign an outcome status of either *Pass* or *Fail* to indicate whether the test is passed or failed when that outcome is selected as a test result.</span></span> <span data-ttu-id="fa5b9-109">Utilizzare la pagina **Gruppi di test** per assegnare una variabile di test e il risultato predefinito reletivo a un test qualitativo individuale.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-109">You use the **Test groups** page to assign a test variable and a default outcome for it to an individual qualitative test.</span></span>

<span data-ttu-id="fa5b9-110">Per ogni variabile di test, ti consigliamo di definire almeno due risultati: uno con stato di risultato *Superato* e uno che ha uno stato di risultato di *Non superato*.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-110">For every test variable, we recommend that you define at least two outcomes: one that has an outcome status of *Pass* and one that has an outcome status of *Fail*.</span></span> <span data-ttu-id="fa5b9-111">Non c'è limite al numero totale di variabili o risultati che possono essere definiti.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-111">There is no limit on the total number of variables or outcomes that can be defined.</span></span> <span data-ttu-id="fa5b9-112">Inoltre, più test possono utilizzare le stesse variabili di test per registrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-112">Additionally, multiple tests can use the same test variables to record results.</span></span>

## <a name="examples-of-test-variables"></a><span data-ttu-id="fa5b9-113">Esempi di variabili di test</span><span class="sxs-lookup"><span data-stu-id="fa5b9-113">Examples of test variables</span></span>

### <a name="example-1"></a><span data-ttu-id="fa5b9-114">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="fa5b9-114">Example 1</span></span>

<span data-ttu-id="fa5b9-115">Una società di produzione esegue due test sui materiali fabbricati.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-115">A manufacturing company performs two tests on manufactured materials.</span></span> <span data-ttu-id="fa5b9-116">In un test, il livello di pH è associato a una striscia colorata.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-116">In one test, the pH level is associated with a color strip.</span></span> <span data-ttu-id="fa5b9-117">I livelli di pH accettabili sono in colori più chiari e i livelli di pH inaccettabili sono in colori più scuri.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-117">Acceptable pH levels are in lighter colors, and unacceptable pH levels are in darker colors.</span></span> <span data-ttu-id="fa5b9-118">In un altro test, vengono eseguite più ispezioni visive e gli addetti alla qualità usano il loro giudizio per determinare se l'articolo supera o meno l'ispezione visiva.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-118">In another test, multiple visual inspections are performed, and quality workers use their judgement to determine whether the item passes or fails the visual inspection.</span></span>

### <a name="example-2"></a><span data-ttu-id="fa5b9-119">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="fa5b9-119">Example 2</span></span>

<span data-ttu-id="fa5b9-120">Una società produttrice di biscotti utilizza un test di ispezione per il prodotto finito.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-120">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="fa5b9-121">Il test di ispezione ha diverse variabili.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-121">This inspection test has several variables.</span></span> <span data-ttu-id="fa5b9-122">Una variabile si riferisce al gusto e i possibili risultati per questa variabile sono buono o cattivo.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-122">One variable is taste, and the possible outcomes for it are good and bad.</span></span> <span data-ttu-id="fa5b9-123">Una seconda variabile riguarda il colore e i risultati possibili troppo scuro, troppo chiaro e corretto.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-123">A second variable is color, and the possible outcomes for it are too dark, too light, and correct.</span></span>

## <a name="create-a-test-variable"></a><span data-ttu-id="fa5b9-124">Creare una variabile di test</span><span class="sxs-lookup"><span data-stu-id="fa5b9-124">Create a test variable</span></span>

<span data-ttu-id="fa5b9-125">Per creare una variabile di test, eseguire i passaggi indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="fa5b9-125">Follow these steps to create a test variable.</span></span>

1. <span data-ttu-id="fa5b9-126">Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Variabili di test**.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-126">Go to **Inventory management \> Setup \> Quality control \> Test variables**.</span></span>
1. <span data-ttu-id="fa5b9-127">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-127">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="fa5b9-128">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="fa5b9-128">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="fa5b9-129">**Variabile** – Immetti un ID o nome univoco per la variabile.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-129">**Variable** – Enter a unique ID or name for the variable.</span></span>
    - <span data-ttu-id="fa5b9-130">**Descrizione** - Immettere una descrizione dettagliata della variabile.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-130">**Description** – Enter a detailed description of the variable.</span></span>

1. <span data-ttu-id="fa5b9-131">Mentre la nuova riga è ancora selezionata, seleziona **Risultati** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-131">While the new row is still selected, select **Outcomes** on the Action Pane.</span></span>
1. <span data-ttu-id="fa5b9-132">Nella pagina **Risultati variabile di test**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-132">On the **Test variable outcomes** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="fa5b9-133">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="fa5b9-133">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="fa5b9-134">**Risultato** – Immetti un ID o nome univoco per il risultato.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-134">**Outcome** – Enter a unique ID or name for the outcome.</span></span>
    - <span data-ttu-id="fa5b9-135">**Descrizione** - Immettere una descrizione dettagliata del risultato.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-135">**Description** – Enter a detailed description of the outcome.</span></span>
    - <span data-ttu-id="fa5b9-136">**Stato risultato** – seleziona *Superato* o *Non superato* per indicare se il test è superato o meno quando tale risultato viene selezionato come risultato del test.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-136">**Outcome status** – Select either *Pass* or *Fail* to indicate whether the test is passed or failed when the outcome is selected as a test result.</span></span>

1. <span data-ttu-id="fa5b9-137">Ripeti il passaggio precedente per ogni risultato aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-137">Repeat the previous step for each additional outcome.</span></span> <span data-ttu-id="fa5b9-138">Assicurati che almeno un risultato abbia uno stato di risultato di *Superato* e almeno uno ha uno stato di risultato di *Non superato*.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-138">Make sure that at least one outcome has an outcome status of *Pass* and at least one has an outcome status of *Fail*.</span></span>
1. <span data-ttu-id="fa5b9-139">Chiudere le pagine.</span><span class="sxs-lookup"><span data-stu-id="fa5b9-139">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fa5b9-140">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fa5b9-140">Additional resources</span></span>

- [<span data-ttu-id="fa5b9-141">Strumenti di test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="fa5b9-141">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="fa5b9-142">Test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="fa5b9-142">Quality management tests</span></span>](quality-tests.md)
- [<span data-ttu-id="fa5b9-143">Gruppi di test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="fa5b9-143">Quality management test groups</span></span>](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
