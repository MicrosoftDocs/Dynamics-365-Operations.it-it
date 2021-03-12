---
title: Codici del passaggio ondata
description: Questo argomento fornisce una panoramica dei codici passaggio ondata e del modo in cui vengono utilizzati.
author: josaw1
manager: tfehr
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveStepCode, WHSReplenishmentTemplates, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 08b40c076e288592f6a4cd628b9acd8a2eaedb7e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4998405"
---
# <a name="wave-step-codes"></a><span data-ttu-id="9e411-103">Codici del passaggio ondata</span><span class="sxs-lookup"><span data-stu-id="9e411-103">Wave step codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9e411-104">I codici passaggio ondata sono codici che gli utenti possono impostare e utilizzare per collegare istanze specifiche di metodi ondata a un modello corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9e411-104">Wave step codes are codes that users can set up and use to link specific instances of wave methods to a corresponding template.</span></span> <span data-ttu-id="9e411-105">I modelli includono modelli per rifornimento, containerizzazione, stampa di etichette, creazione di carichi e ordinamento.</span><span class="sxs-lookup"><span data-stu-id="9e411-105">The templates include templates for replenishment, containerization, label printing, load building, and sorting.</span></span>

<span data-ttu-id="9e411-106">Quando non vengono utilizzati i codici passaggio ondata, gli utenti devono inserire il testo libero per fare riferimento a un modello specifico dall'istanza del metodo ondata.</span><span class="sxs-lookup"><span data-stu-id="9e411-106">When wave step codes aren't used, users must enter free text to reference a specific template from the wave method instance.</span></span> <span data-ttu-id="9e411-107">Il testo libero è soggetto a errori, poiché gli utenti devono assicurarsi che il testo del passaggio ondata che aggiungono per un metodo di passaggio ondata specifico in un modello ondata corrisponda esattamente al testo del passaggio ondata nel modello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9e411-107">Free text is prone to errors because users must make sure that the wave step text that they add for a specific wave step method in a wave template exactly matches the wave step text in the target template.</span></span>

<span data-ttu-id="9e411-108">I codici passaggio ondata per uno specifico tipo di passaggio ondata vengono impostati in una pagina separata.</span><span class="sxs-lookup"><span data-stu-id="9e411-108">Wave step codes for a specific wave step type are set up on a separate page.</span></span> <span data-ttu-id="9e411-109">Per ogni istanza del metodo del passaggio ondata in un modello di ondata che richiede un codice passaggio ondata, il codice passaggio ondata deve essere selezionato in un elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="9e411-109">For every wave step method instance in a wave template that requires a wave step code, the wave step code must be selected in a drop-down list.</span></span> <span data-ttu-id="9e411-110">La selezione in un elenco a discesa sostituisce l'immissione di testo libero e aiuta a ridurre il rischio e l'impatto dell'errore umano.</span><span class="sxs-lookup"><span data-stu-id="9e411-110">Selection in a drop-down list replaces free text entry and helps reduce the risk and impact of human error.</span></span> <span data-ttu-id="9e411-111">I codici di impostazione vengono utilizzati per collegare un metodo del passaggio ondata in un modello ondata a un modello di destinazione per il metodo.</span><span class="sxs-lookup"><span data-stu-id="9e411-111">Setup codes are used to link a wave step method in a wave template to a target template for the method.</span></span>

> [!NOTE]
> <span data-ttu-id="9e411-112">L'uso della funzionalità dei codici del passaggio di ondata è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9e411-112">Use of the wave step codes feature is optional.</span></span> <span data-ttu-id="9e411-113">È abilitato a livello di organizzazione per tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="9e411-113">It is enabled organization-wide for all legal entities.</span></span>

## <a name="setup-demo"></a><span data-ttu-id="9e411-114">Demo di impostazione</span><span class="sxs-lookup"><span data-stu-id="9e411-114">Setup demo</span></span> 

<span data-ttu-id="9e411-115">Per questa demo, i dati dimostrativi devono essere installati ed è necessario utilizzare la società di dati dimostrativi **USMF**.</span><span class="sxs-lookup"><span data-stu-id="9e411-115">For this demo, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="enable-wave-step-codes"></a><span data-ttu-id="9e411-116">Abilita codici del passaggio ondata</span><span class="sxs-lookup"><span data-stu-id="9e411-116">Enable wave step codes</span></span>

<span data-ttu-id="9e411-117">Seguire questi passaggi per attivare la funzionalità di codici passaggio ondata.</span><span class="sxs-lookup"><span data-stu-id="9e411-117">Follow these steps to turn on the wave step codes feature.</span></span>

1. <span data-ttu-id="9e411-118">Accedere a **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="9e411-118">Go to **Feature Management**.</span></span>
2. <span data-ttu-id="9e411-119">Selezionare per abilitare la funzionalità chiamata **Codice di passaggio di ondata a livello di organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="9e411-119">Select to enable the feature called **Organization-wide Wave Step Code**.</span></span>

<span data-ttu-id="9e411-120">Tutti i testi liberi del passaggio ondata esistenti in tutte le persone giuridiche vengono aggiornati alla nuova struttura.</span><span class="sxs-lookup"><span data-stu-id="9e411-120">All existing wave step free texts in all legal entities are upgraded to the new structure.</span></span> <span data-ttu-id="9e411-121">Dopo aver completato questo aggiornamento per tutte le persone giuridiche, la funzionalità è abilitata.</span><span class="sxs-lookup"><span data-stu-id="9e411-121">After this upgrade is completed for all legal entities, then the feature is enabled.</span></span> <span data-ttu-id="9e411-122">Se la funzionalità non può essere abilitata per una o più persone giuridiche, non è abilitata per nessuna persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="9e411-122">If the feature cannot be enabled for one or more legal entities, then the feature is not enabled for any legal entities.</span></span>

<span data-ttu-id="9e411-123">Durante l'abilitazione, le convalide vengono eseguite durante l'aggiornamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="9e411-123">During the enablement, validations are done during the data upgrade.</span></span> <span data-ttu-id="9e411-124">Se l'aggiornamento non riesce, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="9e411-124">If the upgrade fails, you receive an error message.</span></span> <span data-ttu-id="9e411-125">Un aggiornamento potrebbe non riuscire a causa dei seguenti conflitti:</span><span class="sxs-lookup"><span data-stu-id="9e411-125">An upgrade might fail because of the following conflicts:</span></span>

- <span data-ttu-id="9e411-126">Esistono testi liberi con passaggi ondata duplicati.</span><span class="sxs-lookup"><span data-stu-id="9e411-126">Duplicate wave step free texts exist.</span></span>
- <span data-ttu-id="9e411-127">Esistono personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="9e411-127">Customizations exist.</span></span>
- <span data-ttu-id="9e411-128">Un testo libero del passaggio ondata associato a un'istanza del metodo del passaggio ondata non corrisponde al tipo di modello previsto.</span><span class="sxs-lookup"><span data-stu-id="9e411-128">A wave step free text that is associated with a wave step method instance doesn't match the expected template type.</span></span>

<span data-ttu-id="9e411-129">Dopo aver risolto eventuali conflitti identificati durante le convalide, è possibile riprovare ad abilitare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9e411-129">After you've resolved any conflicts that are identified during the validations, you can retry to enable the feature.</span></span>

<span data-ttu-id="9e411-130">Quando la funzionalità è stata abilitata , la pagina **Codici passaggio ondata** (**Gestione magazzino \> Impostazione \> Ondate \> Codici passaggio ondata**) diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="9e411-130">When the feature has been enabled, the **Wave step codes** page (**Warehouse management \> Setup \> Waves \> Wave step codes**) becomes available.</span></span> <span data-ttu-id="9e411-131">Questa pagina elenca i codici dei passaggi ondata che sono stati aggiornati quando è stata attivata la funzionalità Codici passaggi ondata a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9e411-131">This page lists the wave step codes that were upgraded when the Organization-wide Wave Step Code feature was enabled.</span></span>

### <a name="create-new-wave-step-codes"></a><span data-ttu-id="9e411-132">Creare nuovi codici passaggio ondata</span><span class="sxs-lookup"><span data-stu-id="9e411-132">Create new wave step codes</span></span>

<span data-ttu-id="9e411-133">È possibile utilizzare la pagina **Codici passaggio ondata** per creare ed eliminare i codici passaggio ondata.</span><span class="sxs-lookup"><span data-stu-id="9e411-133">You can use the **Wave step codes** page to create and delete wave step codes.</span></span>

<span data-ttu-id="9e411-134">Ogni nuovo codice passaggio ondata e il relativo ID associato devono essere univoci per tutti i tipi di passaggio ondata e devono essere definiti per un tipo di passaggio ondata specifico.</span><span class="sxs-lookup"><span data-stu-id="9e411-134">Every new wave step code and its associated ID must be unique across all wave step types, and they must be defined for a specific wave step type.</span></span>

### <a name="apply-wave-step-codes"></a><span data-ttu-id="9e411-135">Applicare i codici passaggio ondata</span><span class="sxs-lookup"><span data-stu-id="9e411-135">Apply wave step codes</span></span>

<span data-ttu-id="9e411-136">Dopo aver definito i codici passaggio ondata appropriati, possono essere applicati ai metodi di processo ondata.</span><span class="sxs-lookup"><span data-stu-id="9e411-136">After you've defined the appropriate wave step codes, they can be applied to the wave process methods.</span></span>

<span data-ttu-id="9e411-137">Per applicare i codici passaggio ondata, andare al modello di destinazione appropriato.</span><span class="sxs-lookup"><span data-stu-id="9e411-137">To apply wave step codes, go to the appropriate target template.</span></span> <span data-ttu-id="9e411-138">Di seguito vengono riportati i modelli di destinazione a cui sono designati i codici passaggio ondata:</span><span class="sxs-lookup"><span data-stu-id="9e411-138">Here are the target templates that the wave step codes are designated to point to:</span></span>

- <span data-ttu-id="9e411-139">**Modelli rifornimento:** Gestione magazzino \> Impostazioni \> Rifornimento \> Modelli rifornimento</span><span class="sxs-lookup"><span data-stu-id="9e411-139">**Replenishment templates:** Warehouse management \> Setup \> Replenishment \> Replenishment templates</span></span>
- <span data-ttu-id="9e411-140">**Modelli di allestimento del carico:** Gestione magazzino \> Impostazioni \> Carico \> Modelli di allestimento del carico</span><span class="sxs-lookup"><span data-stu-id="9e411-140">**Load build templates:** Warehouse management \> Setup \> Load \> Load build templates</span></span>
- <span data-ttu-id="9e411-141">**Modelli di ordinamento:** Gestione magazzino \> Impostazioni \> Imballaggio \> Modelli di ordinamento in uscita</span><span class="sxs-lookup"><span data-stu-id="9e411-141">**Sort templates:** Warehouse management \> Setup \> Packing \> Outbound sorting templates</span></span>
- <span data-ttu-id="9e411-142">**Modelli di containerizzazione:** Gestione magazzino \> Impostazioni \> Contenitori \> Modelli di build contenitore</span><span class="sxs-lookup"><span data-stu-id="9e411-142">**Containerization templates:** Warehouse management \> Setup \> Containers \> Container build templates</span></span>
- <span data-ttu-id="9e411-143">**Modelli di stampa di etichette:** Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Modelli di etichette ondata</span><span class="sxs-lookup"><span data-stu-id="9e411-143">**Label printing templates:** Warehouse management \> Setup \> Document routing \> Wave label templates</span></span>

<span data-ttu-id="9e411-144">I modelli in questo elenco vengono applicati quando fanno riferimento a un metodo di processo ondata selezionato in un modello ondata.</span><span class="sxs-lookup"><span data-stu-id="9e411-144">The templates in this list are applied when they are referenced from a wave process method that is selected in a wave template.</span></span> <span data-ttu-id="9e411-145">Quando il codice passaggio ondata su un metodo del processo ondata in un modello ondata onda corrisponde al codice passaggio ondata in uno dei tipi di modelli, il modello viene applicato.</span><span class="sxs-lookup"><span data-stu-id="9e411-145">When the wave step code on a wave process method in a wave template matches the wave step code in one of the templates types, the template is applied.</span></span>

### <a name="sample-scenario"></a><span data-ttu-id="9e411-146">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="9e411-146">Sample scenario</span></span>

<span data-ttu-id="9e411-147">Le seguenti procedura consente di garantire che il modello di rifornimento create verrà applicato per il modello ondata.</span><span class="sxs-lookup"><span data-stu-id="9e411-147">The following procedure helps guarantee that the replenishment template that you created will be applied for the wave template.</span></span>

1. <span data-ttu-id="9e411-148">Passare a **Gestione magazzino \> Impostazioni \> Ondate \> Codici passaggio ondata** e creare un codice passaggio ondata per il tipo **Rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="9e411-148">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**, and create a wave step code for the **Replenishment** type.</span></span>
2. <span data-ttu-id="9e411-149">Andare a **Gestione magazzino \> Impostazioni \> Rifornimento \> Modelli rifornimento** e creare un modello rifornimento.</span><span class="sxs-lookup"><span data-stu-id="9e411-149">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**, and create a replenishment template.</span></span>
3. <span data-ttu-id="9e411-150">Nel modello di rifornimento, selezionare il codice passaggio ondata creato per il tipo **Rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="9e411-150">In the replenishment template, select the wave step code that you created for the **Replenishment** type.</span></span>
4. <span data-ttu-id="9e411-151">Passare a **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata** e selezionare il modello ondata che si intende utilizzare.</span><span class="sxs-lookup"><span data-stu-id="9e411-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**, and select the wave template that you intend to use.</span></span>
5. <span data-ttu-id="9e411-152">Nel modello, nella Scheda dettaglio **Metodi**, selezionare il metodo **Rifornimento**.</span><span class="sxs-lookup"><span data-stu-id="9e411-152">In the template, on the **Methods** FastTab, select the **Replenishment** method.</span></span>
6. <span data-ttu-id="9e411-153">Nel campo **Codice passaggio ondata**, selezionare il codice passaggio ondata selezionato nel modello rifornimento.</span><span class="sxs-lookup"><span data-stu-id="9e411-153">In the **Wave step code** field, select the wave step code that you selected in the replenishment template.</span></span>

<span data-ttu-id="9e411-154">Eseguire questi passaggi per ciascuna persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="9e411-154">You perform these steps for each legal entity.</span></span>
