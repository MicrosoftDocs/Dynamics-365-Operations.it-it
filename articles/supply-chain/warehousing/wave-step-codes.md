---
title: Codici del passaggio ondata
description: Questo argomento fornisce una panoramica dei codici passaggio ondata e del modo in cui vengono utilizzati.
author: josaw1
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0f89c6098db9e2e3a9aa4ee3666e4b9ae608f054
ms.sourcegitcommit: d8f1135cdbc2deca70bc4b2805a0519253c9a31f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "1992359"
---
# <a name="wave-step-codes"></a><span data-ttu-id="e781d-103">Codici del passaggio ondata</span><span class="sxs-lookup"><span data-stu-id="e781d-103">Wave step codes</span></span>

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

## <a name="about-wave-step-codes"></a><span data-ttu-id="e781d-104">Informazioni sui codici passaggio ondata</span><span class="sxs-lookup"><span data-stu-id="e781d-104">About wave step codes</span></span>

<span data-ttu-id="e781d-105">I codici passaggio ondata sono codici che gli utenti possono impostare e utilizzare per collegare istanze specifiche di metodi ondata a un modello corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e781d-105">Wave step codes are codes that users can set up and use to link specific instances of wave methods to a corresponding template.</span></span> <span data-ttu-id="e781d-106">I modelli includono modelli per rifornimento, containerizzazione, stampa di etichette, creazione di carichi e ordinamento.</span><span class="sxs-lookup"><span data-stu-id="e781d-106">The templates include templates for replenishment, containerization, label printing, load building, and sorting.</span></span>

<span data-ttu-id="e781d-107">Quando non vengono utilizzati i codici passaggio ondata, gli utenti devono inserire il testo libero per fare riferimento a un modello specifico dall'istanza del metodo ondata.</span><span class="sxs-lookup"><span data-stu-id="e781d-107">When wave step codes aren't used, users must enter free text to reference a specific template from the wave method instance.</span></span> <span data-ttu-id="e781d-108">Il testo libero è soggetto a errori, poiché gli utenti devono assicurarsi che il testo del passaggio ondata che aggiungono per un metodo di passaggio ondata specifico in un modello ondata corrisponda esattamente al testo del passaggio ondata nel modello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e781d-108">Free text is prone to error, because users must make sure that the wave step text that they add for a specific wave step method in a wave template exactly matches the wave step text in the target template.</span></span>

<span data-ttu-id="e781d-109">I codici passaggio ondata per uno specifico tipo di passaggio ondata vengono impostati in una pagina separata.</span><span class="sxs-lookup"><span data-stu-id="e781d-109">Wave step codes for a specific wave step type are set up on a separate page.</span></span> <span data-ttu-id="e781d-110">Per ogni istanza del metodo del passaggio ondata in un modello di ondata che richiede un codice passaggio ondata, il codice passaggio ondata deve essere selezionato in un elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e781d-110">For every wave step method instance in a wave template that requires a wave step code, the wave step code must be selected in a drop-down list.</span></span> <span data-ttu-id="e781d-111">La selezione in un elenco a discesa sostituisce l'immissione di testo libero e aiuta a ridurre il rischio e l'impatto dell'errore umano.</span><span class="sxs-lookup"><span data-stu-id="e781d-111">Selection in a drop-down list replaces free text entry and helps reduce the risk and impact of human error.</span></span> <span data-ttu-id="e781d-112">I codici di impostazione vengono utilizzati per collegare un metodo del passaggio ondata in un modello ondata a un modello di destinazione per il metodo.</span><span class="sxs-lookup"><span data-stu-id="e781d-112">Setup codes are used to link a wave step method in a wave template to a target template for the method.</span></span>

> [!NOTE]
> <span data-ttu-id="e781d-113">L'uso della funzione dei codici passaggio ondata è facoltativo e l'utilizzo è per entità legale.</span><span class="sxs-lookup"><span data-stu-id="e781d-113">Use of the wave step codes feature is optional, and uptake is per legal entity.</span></span> <span data-ttu-id="e781d-114">Pertanto, se una specifica entità legale utilizza la funzione, tutti i codici passaggio ondata esistenti in tale entità legale vengono aggiornati alla nuova struttura.</span><span class="sxs-lookup"><span data-stu-id="e781d-114">Therefore, if a specific legal entity uses the feature, all existing wave step codes in that legal entity are upgraded to the new structure.</span></span>

## <a name="setup-demo"></a><span data-ttu-id="e781d-115">Demo di impostazione</span><span class="sxs-lookup"><span data-stu-id="e781d-115">Setup demo</span></span> 

<span data-ttu-id="e781d-116">Per questa demo, i dati dimostrativi devono essere installati ed è necessario utilizzare la società di dati dimostrativi **USMF**.</span><span class="sxs-lookup"><span data-stu-id="e781d-116">For this demo, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="enable-wave-step-codes"></a><span data-ttu-id="e781d-117">Abilita codici del passaggio ondata</span><span class="sxs-lookup"><span data-stu-id="e781d-117">Enable wave step codes</span></span>

<span data-ttu-id="e781d-118">Seguire questi passaggi per attivare la funzionalità di codici passaggio ondata.</span><span class="sxs-lookup"><span data-stu-id="e781d-118">Follow these steps to turn on the wave step codes feature.</span></span>

1. <span data-ttu-id="e781d-119">Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="e781d-119">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
2. <span data-ttu-id="e781d-120">Nella scheda **Generale**, nella Scheda dettaglio **Elaborazione ondata**, impostare l'opzione **Abilita codici passaggio ondata** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e781d-120">On the **General** tab, on the **Wave processing** FastTab, set the **Enable wave step codes** option to **Yes**.</span></span>

<span data-ttu-id="e781d-121">Tutti i testi liberi del passaggio ondata esistenti vengono aggiornati alla nuova struttura.</span><span class="sxs-lookup"><span data-stu-id="e781d-121">All existing wave step free texts are upgraded to the new structure.</span></span> <span data-ttu-id="e781d-122">Dopo che questo aggiornamento è stato completato per una persona giuridica, l'opzione **Abilita codici passaggio ondata** non è più disponibile nella pagina **Parametri di gestione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="e781d-122">After this upgrade is completed for a legal entity, the **Enable wave step codes** option is no longer available on the **Warehouse management parameters** page.</span></span>

<span data-ttu-id="e781d-123">Le convalide vengono eseguite durante l'aggiornamento e, se l'aggiornamento ha esito negativo, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="e781d-123">Validations are done during the upgrade, and if the upgrade fails, you receive an error message.</span></span> <span data-ttu-id="e781d-124">Un aggiornamento potrebbe non riuscire a causa dei seguenti conflitti:</span><span class="sxs-lookup"><span data-stu-id="e781d-124">An upgrade might fail because of the following conflicts:</span></span>

- <span data-ttu-id="e781d-125">Esistono testi liberi con passaggi ondata duplicati.</span><span class="sxs-lookup"><span data-stu-id="e781d-125">Duplicate wave step free texts exist.</span></span>
- <span data-ttu-id="e781d-126">Esistono personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="e781d-126">Customizations exist.</span></span>
- <span data-ttu-id="e781d-127">Un testo libero del passaggio ondata associato a un'istanza del metodo del passaggio ondata non corrisponde al tipo di modello previsto.</span><span class="sxs-lookup"><span data-stu-id="e781d-127">A wave step free text that is associated with a wave step method instance doesn't match the expected template type.</span></span>

<span data-ttu-id="e781d-128">Dopo aver risolto eventuali conflitti identificati durante le convalide, è possibile rieseguire il processo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="e781d-128">After you've resolved any conflicts that are identified during the validations, you can rerun the upgrade process.</span></span>

<span data-ttu-id="e781d-129">Quando l'aggiornamento viene completato, la pagina **Codici passaggio ondata** (**Gestione magazzino \> Impostazione \> Ondate \> Codici passaggio ondata**) diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="e781d-129">When the upgrade succeeds, the **Wave step codes** page (**Warehouse management \> Setup \> Waves \> Wave step codes**) becomes available.</span></span> <span data-ttu-id="e781d-130">Questa pagina elenca i codici dei passaggi ondata che sono stati aggiornati quando è stata attivata la funzione Codici passaggi ondata.</span><span class="sxs-lookup"><span data-stu-id="e781d-130">This page lists the wave step codes that were upgraded when the wave step codes feature was turned on.</span></span>

### <a name="create-new-wave-step-codes"></a><span data-ttu-id="e781d-131">Creare nuovi codici passaggio ondata</span><span class="sxs-lookup"><span data-stu-id="e781d-131">Create new wave step codes</span></span>

<span data-ttu-id="e781d-132">È possibile utilizzare la pagina **Codici passaggio ondata** per creare ed eliminare i codici passaggio ondata.</span><span class="sxs-lookup"><span data-stu-id="e781d-132">You can use the **Wave step codes** page to create and delete wave step codes.</span></span>

<span data-ttu-id="e781d-133">Ogni nuovo codice passaggio ondata e il relativo ID associato devono essere univoci per tutti i tipi di passaggio ondata e devono essere definiti per un tipo di passaggio ondata specifico.</span><span class="sxs-lookup"><span data-stu-id="e781d-133">Every new wave step code and its associated ID must be unique across all wave step types, and they must be defined for a specific wave step type.</span></span>

### <a name="apply-wave-step-codes"></a><span data-ttu-id="e781d-134">Applicare i codici passaggio ondata</span><span class="sxs-lookup"><span data-stu-id="e781d-134">Apply wave step codes</span></span>

<span data-ttu-id="e781d-135">Dopo aver definito i codici passaggio ondata appropriati, possono essere applicati ai metodi di processo ondata.</span><span class="sxs-lookup"><span data-stu-id="e781d-135">After you've defined the appropriate wave step codes, they can be applied to the wave process methods.</span></span>

<span data-ttu-id="e781d-136">Per applicare i codici passaggio ondata, andare al modello di destinazione appropriato.</span><span class="sxs-lookup"><span data-stu-id="e781d-136">To apply wave step codes, go to the appropriate target template.</span></span> <span data-ttu-id="e781d-137">Di seguito vengono riportati i modelli di destinazione a cui sono designati i codici passaggio ondata:</span><span class="sxs-lookup"><span data-stu-id="e781d-137">Here are the target templates that the wave step codes are designated to point to:</span></span>

- <span data-ttu-id="e781d-138">**Modelli rifornimento:** Gestione magazzino \> Impostazioni \> Rifornimento \> Modelli rifornimento</span><span class="sxs-lookup"><span data-stu-id="e781d-138">**Replenishment templates:** Warehouse management \> Setup \> Replenishment \> Replenishment templates</span></span>
- <span data-ttu-id="e781d-139">**Modelli di allestimento del carico:** Gestione magazzino \> Impostazioni \> Carico \> Modelli di allestimento del carico</span><span class="sxs-lookup"><span data-stu-id="e781d-139">**Load build templates:** Warehouse management \> Setup \> Load \> Load build templates</span></span>
- <span data-ttu-id="e781d-140">**Modelli di ordinamento:** Gestione magazzino \> Impostazioni \> Imballaggio \> Modelli di ordinamento in uscita</span><span class="sxs-lookup"><span data-stu-id="e781d-140">**Sort templates:** Warehouse management \> Setup \> Packing \> Outbound sorting templates</span></span>
- <span data-ttu-id="e781d-141">**Modelli di containerizzazione:** Gestione magazzino \> Impostazioni \> Contenitori \> Modelli di build contenitore</span><span class="sxs-lookup"><span data-stu-id="e781d-141">**Containerization templates:** Warehouse management \> Setup \> Containers \> Container build templates</span></span>
- <span data-ttu-id="e781d-142">**Modelli di stampa di etichette:** Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Modelli di etichette ondata</span><span class="sxs-lookup"><span data-stu-id="e781d-142">**Label printing templates:** Warehouse management \> Setup \> Document routing \> Wave label templates</span></span>

<span data-ttu-id="e781d-143">I modelli in questo elenco vengono applicati quando fanno riferimento a un metodo di processo ondata selezionato in un modello ondata.</span><span class="sxs-lookup"><span data-stu-id="e781d-143">The templates in this list are applied when they are referenced from a wave process method that is selected in a wave template.</span></span> <span data-ttu-id="e781d-144">Quando il codice passaggio ondata su un metodo del processo ondata in un modello ondata onda corrisponde al codice passaggio ondata in uno dei tipi di modelli, il modello viene applicato.</span><span class="sxs-lookup"><span data-stu-id="e781d-144">When the wave step code on a wave process method in a wave template matches the wave step code in one of the templates types, the template is applied.</span></span>

### <a name="sample-scenario"></a><span data-ttu-id="e781d-145">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="e781d-145">Sample scenario</span></span>

<span data-ttu-id="e781d-146">Le seguenti procedura consente di garantire che il modello di rifornimento create verrà applicato per il modello ondata.</span><span class="sxs-lookup"><span data-stu-id="e781d-146">The following procedure helps guarantee that the replenishment template that you created will be applied for the wave template.</span></span>

1. <span data-ttu-id="e781d-147">Passare a **Gestione magazzino \> Impostazioni \> Ondate \> Codici passaggio ondata** e creare un codice passaggio ondata per il tipo **Rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="e781d-147">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**, and create a wave step code for the **Replenishment** type.</span></span>
2. <span data-ttu-id="e781d-148">Andare a **Gestione magazzino \> Impostazioni \> Rifornimento \> Modelli rifornimento** e creare un modello rifornimento.</span><span class="sxs-lookup"><span data-stu-id="e781d-148">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**, and create a replenishment template.</span></span>
3. <span data-ttu-id="e781d-149">Nel modello di rifornimento, selezionare il codice passaggio ondata creato per il tipo **Rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="e781d-149">In the replenishment template, select the wave step code that you created for the **Replenishment** type.</span></span>
4. <span data-ttu-id="e781d-150">Passare a **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata** e selezionare il modello ondata che si intende utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e781d-150">Go to **Warehouse management \> Setup \> Waves \> Wave templates**, and select the wave template that you intend to use.</span></span>
5. <span data-ttu-id="e781d-151">Nel modello, nella Scheda dettaglio **Metodi**, selezionare il metodo **Rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="e781d-151">In the template, on the **Methods** FastTab, select the **Replenishment** method.</span></span>
6. <span data-ttu-id="e781d-152">Nel campo **Codice passaggio ondata**, selezionare il codice passaggio ondata selezionato nel modello rifornimento.</span><span class="sxs-lookup"><span data-stu-id="e781d-152">In the **Wave step code** field, select the wave step code that you selected in the replenishment template.</span></span>
