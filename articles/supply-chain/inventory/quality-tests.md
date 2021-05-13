---
title: Test di gestione qualità
description: Questo argomento descrive come creare test che possano essere utilizzati per gli ordini di controllo qualità in Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: b88011f486b6582db4727b85d021868899c6abe1
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956713"
---
# <a name="quality-management-tests"></a><span data-ttu-id="f8f4a-103">Test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="f8f4a-103">Quality management tests</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f8f4a-104">Questo argomento descrive come creare test che possano essere utilizzati per gli ordini di controllo qualità in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-104">This topic describes how to create tests that can be used for quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="f8f4a-105">Utilizzare la pagina **Test** per definire e visualizzare i singoli test che determinano se i prodotti sono conformi alle specifiche di qualità.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-105">You use the **Tests** page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="f8f4a-106">È possibile assegnare uno o più test singoli a un gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-106">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="f8f4a-107">In questo caso, è inoltre necessario specificare le informazioni specifiche del test, ad esempio i valori di misura accettabili.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-107">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="f8f4a-108">I valori di misurazione vengono utilizzati per i test quantitativi.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-108">Measurement values are used for quantitative tests.</span></span> <span data-ttu-id="f8f4a-109">Per i test qualitativi, vengono utilizzate le variabili di test.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-109">For qualitative tests, test variables are used.</span></span>

- <span data-ttu-id="f8f4a-110">Per test quantitativi, il campo **Tipo** è impostato su *Frazione* o *Intero*.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-110">For quantitative tests, the **Type** field is set to *Integer* or *Fraction*.</span></span> <span data-ttu-id="f8f4a-111">È anche specificata un'unità di misura.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-111">A unit of measure is also specified.</span></span> <span data-ttu-id="f8f4a-112">Le specifiche di qualità e i risultati del test vengono espressi sotto forma di numeri.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-112">Quality specifications and test results are expressed as numbers.</span></span>
- <span data-ttu-id="f8f4a-113">Per i test qualitativi, il campo **Tipo** è impostato su *Opzione*.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-113">For qualitative tests, the **Type** field is set to *Option*.</span></span> <span data-ttu-id="f8f4a-114">I test qualitativi richiedono informazioni aggiuntive sulla variabile di test misurata e sulle relative opzioni enumerate.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-114">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="f8f4a-115">Le specifiche di qualità e i risultati del test vengono espressi in base a un esito.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-115">Quality specifications and test results are expressed according to an outcome.</span></span>

<span data-ttu-id="f8f4a-116">È possibile assegnare facoltativamente uno strumento di test a un test.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-116">You can optionally assign a test instrument to a test.</span></span> <span data-ttu-id="f8f4a-117">Tuttavia, gli strumenti di test non sono obbligatori per creare e utilizzare i test con gli ordini di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-117">However, test instruments aren't required to create and use tests with quality orders.</span></span> <span data-ttu-id="f8f4a-118">Per ulteriori informazioni, vedere [Strumenti di test di gestione qualità](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="f8f4a-118">For more information, see [Quality management test instruments](quality-test-instruments.md).</span></span>

<span data-ttu-id="f8f4a-119">È anche possibile specificare facoltativamente un'unità per un test, per indicare l'unità di misura in cui vengono registrati i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-119">You can also optionally specify a unit for a test, to indicate the unit of measure that test results are recorded in.</span></span> <span data-ttu-id="f8f4a-120">Ad esempio, un test per la temperatura potrebbe includere un'unità di gradi Fahrenheit o gradi Celsius.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-120">For example, a test for temperature might include a unit of either degrees Fahrenheit or degrees Celsius.</span></span>

## <a name="example-of-a-test"></a><span data-ttu-id="f8f4a-121">Esempio di un test</span><span class="sxs-lookup"><span data-stu-id="f8f4a-121">Example of a test</span></span>

<span data-ttu-id="f8f4a-122">Una società di produzione esegue due test sul materiale acquistato, ovvero un test quantitativo sulla qualità del materiale e un test qualitativo sul danno all'imballaggio.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-122">A manufacturing company performs two tests on purchased material: a quantitative test for material quality and a qualitative test for packaging damage.</span></span> <span data-ttu-id="f8f4a-123">La società specifica informazioni aggiuntive sul test qualitativo per definire la variabile di test (ad esempio, per l'imballaggio danneggiato), e i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-123">The company specifies additional information about the qualitative test to define the test variable (for example, damaged packaging) and its outcomes.</span></span> <span data-ttu-id="f8f4a-124">La società utilizza la pagina **Gruppi di test** per assegnare i due test a un gruppo di test e per specificare le informazioni specifiche del test.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-124">The company uses the **Test groups** page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="f8f4a-125">Il gruppo di test viene assegnato a un ordine di controllo qualità, in modo che la società possa creare un report per i risultati dei due test.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-125">The test group is assigned to a quality order so that the company can report test results for the two tests.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="f8f4a-126">Creare un test</span><span class="sxs-lookup"><span data-stu-id="f8f4a-126">Create a test</span></span>

<span data-ttu-id="f8f4a-127">Per creare un test, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-127">Follow these steps to create a test.</span></span>

1. <span data-ttu-id="f8f4a-128">Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Test**.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-128">Go to **Inventory management \> Setup \> Quality control \> Tests**.</span></span>
1. <span data-ttu-id="f8f4a-129">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-129">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="f8f4a-130">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="f8f4a-130">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="f8f4a-131">**Test** – Immetti un ID o nome univoco per il test.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-131">**Test** – Enter a unique ID or name for the test.</span></span>
    - <span data-ttu-id="f8f4a-132">**Descrizione** - Immettere una descrizione dettagliata del test.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-132">**Description** – Enter a detailed description of the test.</span></span>
    - <span data-ttu-id="f8f4a-133">**Tipo** - Seleziona il tipo di risultati che il test produce.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-133">**Type** – Select the type of results that the test produces.</span></span> <span data-ttu-id="f8f4a-134">Per i test quantitativi, selezionare *Frazione* o *Intero*.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-134">For quantitative tests, select *Fraction* or *Integer*.</span></span> <span data-ttu-id="f8f4a-135">Per i test qualitativi, selezionare *Opzione*.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-135">For qualitative tests, select *Option*.</span></span>
    - <span data-ttu-id="f8f4a-136">**Strumento di test** - Selezionare uno [strumento di test](quality-test-instruments.md) da utilizzare per il test.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-136">**Test instrument** – Select a [test instrument](quality-test-instruments.md) that should be used for the test.</span></span>
    - <span data-ttu-id="f8f4a-137">**Unità** - Se hai selezionato *Frazione* o *Intero* nel campo **Tipo** (ovvero, se il test è un test quantitativo), selezionare l'unità di misura in cui devono essere registrati i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-137">**Unit** – If you selected *Fraction* or *Integer* in the **Type** field (that is, if the test is a quantitative test), select the unit of measure that test results should be recorded in.</span></span>

1. <span data-ttu-id="f8f4a-138">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-138">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="f8f4a-139">Dopo aver salvato un test, non è più possibile modificare il campo **Tipo** nella griglia.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-139">After you save a test, you can no longer edit the **Type** field in the grid.</span></span> <span data-ttu-id="f8f4a-140">Se è necessario modificare il tipo di risultati del test che verranno registrati per un test, selezionare **Cambia tipo di test qualità** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-140">If you must change the type of test results that will be recorded for a test, select **Change quality test type** on the Action Pane.</span></span> <span data-ttu-id="f8f4a-141">Nella finestra di dialogo **Cambia tipo di test qualità**, impostare il campo **Nuovo tipo** sul tipo desiderato, quindi selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="f8f4a-141">In the **Change quality test type** dialog box, set the **New type** field to the desired type, and then select **OK** to close the dialog box.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f8f4a-142">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f8f4a-142">Additional resources</span></span>

- [<span data-ttu-id="f8f4a-143">Strumenti di test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="f8f4a-143">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="f8f4a-144">Gruppi di test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="f8f4a-144">Quality management test groups</span></span>](quality-test-groups.md)
- [<span data-ttu-id="f8f4a-145">Variabili di test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="f8f4a-145">Quality management test variables</span></span>](quality-test-variables.md)
- [<span data-ttu-id="f8f4a-146">Associazioni di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="f8f4a-146">Quality associations</span></span>](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
