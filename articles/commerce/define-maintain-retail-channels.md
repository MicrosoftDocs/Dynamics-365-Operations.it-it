---
title: Definire e gestire canali di vendita al dettaglio
description: Questo argomento fornisce una panoramica del processo per l'impostazione di punti vendita fisici, denominati punti vendita in Dynamics 365 Commerce. Sono riportate informazioni sulle attività da completare prima e dopo la configurazione di un punto vendita.
author: mugunthanm
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 63639d69af90c6aa37bbf7af7868bca71942063f
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022996"
---
# <a name="define-and-maintain-retail-channels"></a><span data-ttu-id="a92b5-104">Definire e gestire canali di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="a92b5-104">Define and maintain retail channels</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a92b5-105">Questo argomento fornisce una panoramica del processo per l'impostazione di punti vendita fisici, denominati punti vendita in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a92b5-105">This topic provides an overview of the process for setting up brick-and-mortar stores, which are referred to as stores in Dynamics 365 Commerce.</span></span> <span data-ttu-id="a92b5-106">Sono riportate informazioni sulle attività da completare prima e dopo la configurazione di un punto vendita.</span><span class="sxs-lookup"><span data-stu-id="a92b5-106">It includes information about the tasks that you must complete both before and after you set up a store.</span></span>

<span data-ttu-id="a92b5-107">Commerce supporta più canali di vendita al dettaglio, ad esempio negozi online, servizi clienti e punti vendita fisici.</span><span class="sxs-lookup"><span data-stu-id="a92b5-107">Commerce supports multiple channels, such as online stores, call centers, and brick-and-mortar stores.</span></span> <span data-ttu-id="a92b5-108">Un punto vendita fisico è anche denominato punto vendita.</span><span class="sxs-lookup"><span data-stu-id="a92b5-108">A brick-and-mortar store is called a store.</span></span> <span data-ttu-id="a92b5-109">Ogni punto vendita può disporre dei propri metodi di pagamento, gruppi di prezzi, registratori di cassa POS, conti ricavi/spese e personale.</span><span class="sxs-lookup"><span data-stu-id="a92b5-109">Each store can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="a92b5-110">È necessario impostare tutti questi elementi per un punto vendita prima di crearlo.</span><span class="sxs-lookup"><span data-stu-id="a92b5-110">You must set up all these elements for a store before you create it.</span></span> <span data-ttu-id="a92b5-111">Dopo aver creato il punto vendita, assegnare i prodotti che si desidera siano presenti i esso.</span><span class="sxs-lookup"><span data-stu-id="a92b5-111">After you create the store, you assign the products that you want it to carry.</span></span> <span data-ttu-id="a92b5-112">Inoltre l'utente assegna dipendenti, registratori di cassa e clienti al punto vendita.</span><span class="sxs-lookup"><span data-stu-id="a92b5-112">You also assign employees, registers, and customers to the store.</span></span> <span data-ttu-id="a92b5-113">Infine, aggiungere il nuovo punto vendita a una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="a92b5-113">Finally, you add the new store to an organization hierarchy.</span></span>

## <a name="setting-up-stores"></a><span data-ttu-id="a92b5-114">Impostazione dei punti vendita</span><span class="sxs-lookup"><span data-stu-id="a92b5-114">Setting up stores</span></span>

<span data-ttu-id="a92b5-115">Prima di impostare un punto vendita al dettaglio in Commerce, è necessario completare alcune attività previste come prerequisito.</span><span class="sxs-lookup"><span data-stu-id="a92b5-115">Before you can set up a store in Commerce, you must complete some prerequisite tasks.</span></span> <span data-ttu-id="a92b5-116">È possibile quindi creare il punto vendita e aggiungere i dettagli.</span><span class="sxs-lookup"><span data-stu-id="a92b5-116">You can then create the store and add details.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="a92b5-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a92b5-117">Prerequisites</span></span>

<span data-ttu-id="a92b5-118">Prima di impostare un punto vendita, è necessario completare le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="a92b5-118">You must complete the following tasks before you can set up a store:</span></span>

1. <span data-ttu-id="a92b5-119">Configurare la struttura dell'organizzazione e impostare le gerarchie dell'organizzazione per gli assortimenti di articoli al dettaglio, il rifornimento e il reporting.</span><span class="sxs-lookup"><span data-stu-id="a92b5-119">Configure your organization structure, and set up organization hierarchies for retail assortments, replenishment, and reporting.</span></span>
2. <span data-ttu-id="a92b5-120">Impostare un magazzino che rappresenti il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="a92b5-120">Set up a warehouse that represents the store.</span></span>
3. <span data-ttu-id="a92b5-121">Impostare le sequenze numeriche per i punti vendita, i rendiconti per il punto vendita e i giustificativi dei rendiconti.</span><span class="sxs-lookup"><span data-stu-id="a92b5-121">Set up number sequences for stores, store statements, and statement vouchers.</span></span>
4. <span data-ttu-id="a92b5-122">Configurare i parametri per Commerce.</span><span class="sxs-lookup"><span data-stu-id="a92b5-122">Configure parameters for Commerce.</span></span>
5. <span data-ttu-id="a92b5-123">Impostare i metodi di pagamento accettati dal punto vendita.</span><span class="sxs-lookup"><span data-stu-id="a92b5-123">Set up the methods of payment that the store accepts.</span></span>
6. <span data-ttu-id="a92b5-124">Per elaborare le transazioni con carta di credito nei registratori di cassa Retail POS, è possibile impostare i servizi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="a92b5-124">To process credit card transactions at retail POS registers, you can also set up payment services.</span></span>
7. <span data-ttu-id="a92b5-125">Impostare le fasce IVA.</span><span class="sxs-lookup"><span data-stu-id="a92b5-125">Set up sales tax groups.</span></span>
8. <span data-ttu-id="a92b5-126">Impostare i prodotti di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="a92b5-126">Set up retail products.</span></span> <span data-ttu-id="a92b5-127">Come parte dell'attività, si impostano anche le gerarchie di prodotti, le varianti prodotto e gli assortimenti prodotto.</span><span class="sxs-lookup"><span data-stu-id="a92b5-127">As part of this task, you also set up product hierarchies, product variants, and product assortments.</span></span>
9. <span data-ttu-id="a92b5-128">Impostare i gruppi di prezzo dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="a92b5-128">Set up product price groups.</span></span>
10. <span data-ttu-id="a92b5-129">Impostare i prezzi dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="a92b5-129">Set up product pricing.</span></span> <span data-ttu-id="a92b5-130">Come parte dell'attività, si impostano anche le rettifiche prezzo, gli sconti e i periodi di sconto.</span><span class="sxs-lookup"><span data-stu-id="a92b5-130">As part of this task, you also set up price adjustments, discounts, and discount periods.</span></span>
11. <span data-ttu-id="a92b5-131">Impostare i membri del personale.</span><span class="sxs-lookup"><span data-stu-id="a92b5-131">Set up staff members.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a92b5-132">È inoltre necessario assegnare le autorizzazioni appropriate ai lavoratori, in modo che possano accedere ed eseguire le attività utilizzando il sistema POS.</span><span class="sxs-lookup"><span data-stu-id="a92b5-132">You must also assign appropriate permissions to the workers, so that they can sign in and perform tasks by using the POS system.</span></span>

12. <span data-ttu-id="a92b5-133">Configurare i profili POS da assegnare al punto vendita.</span><span class="sxs-lookup"><span data-stu-id="a92b5-133">Configure the POS profiles to assign to the store.</span></span> <span data-ttu-id="a92b5-134">Questa attività include molte altre attività, ad esempio, l'impostazione dei registratori, dei profili offline oltre che dei formati delle ricevute e dei profili.</span><span class="sxs-lookup"><span data-stu-id="a92b5-134">This task includes many other tasks, such as setting up registers, setting up offline profiles, and setting up receipt formats and profiles.</span></span>

<span data-ttu-id="a92b5-135">Verificare tutte le attività incluse tra i prerequisito e completare solo le attività applicabili alla propria situazione.</span><span class="sxs-lookup"><span data-stu-id="a92b5-135">Review all the tasks that are included in the prerequisites, and complete only the tasks that apply to you.</span></span>

### <a name="set-up-a-store"></a><span data-ttu-id="a92b5-136">Impostare un punto vendita</span><span class="sxs-lookup"><span data-stu-id="a92b5-136">Set up a store</span></span>

<span data-ttu-id="a92b5-137">Dopo aver completato le attività prerequisite, completare le attività seguenti per impostare i dettagli del punto vendita:</span><span class="sxs-lookup"><span data-stu-id="a92b5-137">After you complete the prerequisite tasks, complete these tasks to set up the details for the store:</span></span>

1. <span data-ttu-id="a92b5-138">Creare un punto vendita.</span><span class="sxs-lookup"><span data-stu-id="a92b5-138">Create a store.</span></span>
2. <span data-ttu-id="a92b5-139">Assegnare una fascia IVA al punto vendita.</span><span class="sxs-lookup"><span data-stu-id="a92b5-139">Assign a sales tax group to the store.</span></span>
3. <span data-ttu-id="a92b5-140">Assegnare i metodi di pagamento accettati al punto vendita.</span><span class="sxs-lookup"><span data-stu-id="a92b5-140">Assign the accepted payment methods to the store.</span></span>
4. <span data-ttu-id="a92b5-141">Aggiungere dettagli alle descrizioni di prodotto per i prodotti offerti che nei punti vendita.</span><span class="sxs-lookup"><span data-stu-id="a92b5-141">Add details to the product descriptions for products that you offer in your stores.</span></span> <span data-ttu-id="a92b5-142">Ad esempio, è possibile aggiungere il formato RTF e le immagini.</span><span class="sxs-lookup"><span data-stu-id="a92b5-142">For example, you can add rich text and images.</span></span> <span data-ttu-id="a92b5-143">Tali dettagli del prodotto vengono visualizzati in vari contesti, ad esempio sul registratore di cassa POS o nelle etichette stampate.</span><span class="sxs-lookup"><span data-stu-id="a92b5-143">These product details appear in various contexts, such as on the POS register or on printed labels.</span></span>
5. <span data-ttu-id="a92b5-144">Aggiungere il punto vendita alla gerarchia organizzativa predefinita assegnata a uno scopo di **Assortimento di articoli al dettaglio**, **Rifornimento per vendita al dettaglio** o **Report per vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="a92b5-144">Add the store to the default organization hierarchy that is assigned to a purpose of **Retail assortment**, **Retail replenishment**, or **Retail reporting**.</span></span>

### <a name="after-you-set-up-a-store"></a><span data-ttu-id="a92b5-145">Dopo aver impostato un punto vendita</span><span class="sxs-lookup"><span data-stu-id="a92b5-145">After you set up a store</span></span>

<span data-ttu-id="a92b5-146">Dopo aver immesso i dettagli relativi al punto vendita, completare queste attività per inviare i nuovi dati del punto di vendita a POS.</span><span class="sxs-lookup"><span data-stu-id="a92b5-146">After you enter the details for the store, complete these tasks to send the new store data to POS:</span></span>

1. <span data-ttu-id="a92b5-147">Configurare i registratori di cassa POS per il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="a92b5-147">Configure the POS registers for the store.</span></span>
2. <span data-ttu-id="a92b5-148">Assegnare gli assortimenti dei prodotti al punto vendita.</span><span class="sxs-lookup"><span data-stu-id="a92b5-148">Assign product assortments to the store.</span></span>
3. <span data-ttu-id="a92b5-149">Elaborare gli assortimenti per generare l'elenco di prodotti inclusi nell'assortimento e per rendere i prodotti disponibili nel punto vendita.</span><span class="sxs-lookup"><span data-stu-id="a92b5-149">Process assortments to generate the list of products that are included in the assortment and to make the products available in the store.</span></span>
4. <span data-ttu-id="a92b5-150">Inviare i dati quali sequenze numeriche, profili hardware e layout delle schermate POS ai registratori di cassa di POS.</span><span class="sxs-lookup"><span data-stu-id="a92b5-150">Send data such as number sequences, hardware profiles, and POS screen layouts to the POS registers.</span></span>
5. <span data-ttu-id="a92b5-151">Pubblicare il punto vendita per inviare i dati del punto vendita a POS.</span><span class="sxs-lookup"><span data-stu-id="a92b5-151">Publish the store to send store data to POS.</span></span>
6. <span data-ttu-id="a92b5-152">Eseguire i processi per inviare i dati del punto vendita a POS.</span><span class="sxs-lookup"><span data-stu-id="a92b5-152">Run the jobs to send the store data to POS.</span></span>

## <a name="organization-hierarchies"></a><span data-ttu-id="a92b5-153">Gerarchie organizzative</span><span class="sxs-lookup"><span data-stu-id="a92b5-153">Organization hierarchies</span></span>

<span data-ttu-id="a92b5-154">Commerce utilizza gerarchie organizzative per strutturare canali.</span><span class="sxs-lookup"><span data-stu-id="a92b5-154">Commerce uses organization hierarchies to structure channels.</span></span> <span data-ttu-id="a92b5-155">Le gerarchie organizzative rappresentano i rapporti tra le organizzazioni che fanno parte dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="a92b5-155">Organization hierarchies represent the relationships between the organizations that make up your business.</span></span> <span data-ttu-id="a92b5-156">Quando si impostano gli archivi, è possibile aggiungerli a una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="a92b5-156">When you set up stores, you can add them to an organization hierarchy.</span></span> <span data-ttu-id="a92b5-157">I punti vendita, quindi, condividono i dati utilizzati per assortimenti, rifornimento e reporting.</span><span class="sxs-lookup"><span data-stu-id="a92b5-157">The stores then share data that is used for assortments, replenishment, and reporting.</span></span>

> [!NOTE]
> <span data-ttu-id="a92b5-158">Per utilizzare la funzionalità di vendita al dettaglio, la chiave di configurazione per **Indirizzi di spedizione multipli**deve essere abilitata.</span><span class="sxs-lookup"><span data-stu-id="a92b5-158">To use Retail sales functionality, the configuration key for **Multiple ship-to** must be enabled.</span></span> <span data-ttu-id="a92b5-159">Questa chiave di configurazione è disponibile nelle chiavi **Configurazione commercio** sotto **Amministrazione di sistema**\>**Impostazioni**\>**Configurazione licenza**.</span><span class="sxs-lookup"><span data-stu-id="a92b5-159">This configuration key can be found in the **Trade configuration** keys under **System Administration**\> **Setup** \> **License Configuration**.</span></span> <span data-ttu-id="a92b5-160">Ciò è necessario a causa della funzionalità Retail che esegue varie convalide in base all'indirizzo di consegna configurato a livello di riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="a92b5-160">This is required due to Retail functionality that performs various validations based on the delivery address configured at the sales order line level.</span></span>

