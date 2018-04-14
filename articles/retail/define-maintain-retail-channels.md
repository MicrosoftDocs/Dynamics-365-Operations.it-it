---
title: Definire e gestire canali di vendita al dettaglio
description: "Questo argomento fornisce una panoramica del processo per l'impostazione di punti vendita fisici, denominati punti vendita al dettaglio in Microsoft Dynamics 365 for Retail. Sono riportate informazioni sulle attività da completare prima e dopo la configurazione di un punto vendita al dettaglio."
author: mugunthanm
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 055ff18b16fa2680c73564b7a7ef0c087c55e701
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="define-and-maintain-retail-channels"></a><span data-ttu-id="caa1f-104">Definire e gestire canali di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="caa1f-104">Define and maintain retail channels</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="caa1f-105">Questo argomento fornisce una panoramica del processo per l'impostazione di punti vendita fisici, denominati punti vendita al dettaglio in Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="caa1f-105">This topic provides an overview of the process for setting up brick-and-mortar stores, which are referred to as retail stores in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="caa1f-106">Sono riportate informazioni sulle attività da completare prima e dopo la configurazione di un punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="caa1f-106">It includes information about the tasks that you must complete both before and after you set up a retail store.</span></span>

<span data-ttu-id="caa1f-107">Dynamics 365 for Retail supporta più canali di vendita al dettaglio, ad esempio negozi online, servizi clienti e punti vendita fisici.</span><span class="sxs-lookup"><span data-stu-id="caa1f-107">Dynamics 365 for Retail supports multiple retail channels, such as online stores, call centers, and brick-and-mortar stores.</span></span> <span data-ttu-id="caa1f-108">Un punto vendita fisico è anche denominato punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="caa1f-108">A brick-and-mortar store is called a retail store.</span></span> <span data-ttu-id="caa1f-109">Ogni punto vendita al dettaglio può disporre dei propri metodi di pagamento, gruppi di prezzi, registratori di cassa POS, conti ricavi/spese e personale.</span><span class="sxs-lookup"><span data-stu-id="caa1f-109">Each retail store can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="caa1f-110">È necessario impostare tutti questi elementi per un punto vendita al dettaglio prima di crearlo.</span><span class="sxs-lookup"><span data-stu-id="caa1f-110">You must set up all these elements for a retail store before you create it.</span></span> <span data-ttu-id="caa1f-111">Dopo aver creato il punto vendita al dettaglio, assegnare i prodotti che si desidera siano presenti i esso.</span><span class="sxs-lookup"><span data-stu-id="caa1f-111">After you create the retail store, you assign the products that you want it to carry.</span></span> <span data-ttu-id="caa1f-112">Inoltre l'utente assegna dipendenti, registratori di cassa e clienti al punto vendita.</span><span class="sxs-lookup"><span data-stu-id="caa1f-112">You also assign employees, registers, and customers to the store.</span></span> <span data-ttu-id="caa1f-113">Infine, aggiungere il nuovo punto vendita a una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="caa1f-113">Finally, you add the new store to an organization hierarchy.</span></span>

## <a name="setting-up-retail-stores"></a><span data-ttu-id="caa1f-114">Impostazione dei punti vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="caa1f-114">Setting up retail stores</span></span>
<span data-ttu-id="caa1f-115">Prima di impostare un punto vendita al dettaglio in Dynamics 365 for Retail, è necessario completare alcune attività previste come prerequisito.</span><span class="sxs-lookup"><span data-stu-id="caa1f-115">Before you can set up a retail store in Dynamics 365 for Retail, you must complete some prerequisite tasks.</span></span> <span data-ttu-id="caa1f-116">È possibile quindi creare il punto vendita al dettaglio e aggiungere i dettagli.</span><span class="sxs-lookup"><span data-stu-id="caa1f-116">You can then create the retail store and add details.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="caa1f-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="caa1f-117">Prerequisites</span></span>

<span data-ttu-id="caa1f-118">Prima di impostare un punto vendita al dettaglio, è necessario completare le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="caa1f-118">You must complete the following tasks before you can set up a retail store:</span></span>

1.  <span data-ttu-id="caa1f-119">Configurare la struttura dell'organizzazione e impostare le gerarchie dell'organizzazione per gli assortimenti di articoli al dettaglio, il rifornimento e il reporting.</span><span class="sxs-lookup"><span data-stu-id="caa1f-119">Configure your organization structure, and set up organization hierarchies for retail assortments, replenishment, and reporting.</span></span>
2.  <span data-ttu-id="caa1f-120">Impostare un magazzino che rappresenti il punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="caa1f-120">Set up a warehouse that represents the retail store.</span></span>
3.  <span data-ttu-id="caa1f-121">Impostare le sequenze numeriche per i punti vendita al dettaglio, i rendiconti per il punto vendita e i giustificativi dei rendiconti.</span><span class="sxs-lookup"><span data-stu-id="caa1f-121">Set up number sequences for retail stores, store statements, and statement vouchers.</span></span>
4.  <span data-ttu-id="caa1f-122">Configurare i parametri per la vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="caa1f-122">Configure parameters for Retail.</span></span>
5.  <span data-ttu-id="caa1f-123">Impostare i metodi di pagamento accettati dal punto vendita.</span><span class="sxs-lookup"><span data-stu-id="caa1f-123">Set up the methods of payment that the store accepts.</span></span>
6.  <span data-ttu-id="caa1f-124">Per elaborare le transazioni con carta di credito nei registratori di cassa Retail POS, è possibile impostare i servizi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="caa1f-124">To process credit card transactions at retail POS registers, you can also set up payment services.</span></span>
7.  <span data-ttu-id="caa1f-125">Impostare le fasce IVA.</span><span class="sxs-lookup"><span data-stu-id="caa1f-125">Set up sales tax groups.</span></span>
8.  <span data-ttu-id="caa1f-126">Impostare i prodotti di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="caa1f-126">Set up retail products.</span></span> <span data-ttu-id="caa1f-127">Come parte dell'attività, si impostano anche le gerarchie di prodotti al dettaglio, le varianti prodotto e gli assortimenti prodotto.</span><span class="sxs-lookup"><span data-stu-id="caa1f-127">As part of this task, you also set up retail product hierarchies, product variants, and product assortments.</span></span>
9.  <span data-ttu-id="caa1f-128">Impostare i gruppi di prezzo dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="caa1f-128">Set up product price groups.</span></span>
10. <span data-ttu-id="caa1f-129">Impostare i prezzi dei prodotti di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="caa1f-129">Set up retail product pricing.</span></span> <span data-ttu-id="caa1f-130">Come parte dell'attività, si impostano anche le rettifiche prezzo, gli sconti e i periodi di sconto.</span><span class="sxs-lookup"><span data-stu-id="caa1f-130">As part of this task, you also set up price adjustments, discounts, and discount periods.</span></span>
11. <span data-ttu-id="caa1f-131">Impostare i membri del personale.</span><span class="sxs-lookup"><span data-stu-id="caa1f-131">Set up staff members.</span></span> <span data-ttu-id="caa1f-132">**Nota:** È inoltre necessario assegnare le autorizzazioni appropriate ai lavoratori, in modo che possano accedere ed eseguire le attività utilizzando il sistema Dynamics 365 for Retail for Retail POS.</span><span class="sxs-lookup"><span data-stu-id="caa1f-132">**Note:** You must also assign appropriate permissions to the workers, so that they can sign in and perform tasks by using the Dynamics 365 for Retail for Retail POS system.</span></span>
12. <span data-ttu-id="caa1f-133">Configurare i profili di Retail POS da assegnare al punto vendita.</span><span class="sxs-lookup"><span data-stu-id="caa1f-133">Configure the Retail POS profiles to assign to the store.</span></span> <span data-ttu-id="caa1f-134">Questa attività include molte altre attività, ad esempio, l'impostazione dei registratori, dei profili offline oltre che dei formati delle ricevute e dei profili.</span><span class="sxs-lookup"><span data-stu-id="caa1f-134">This task includes many other tasks, such as setting up registers, setting up offline profiles, and setting up receipt formats and profiles.</span></span>

<span data-ttu-id="caa1f-135">Verificare tutte le attività incluse tra i prerequisito e completare solo le attività applicabili alla propria situazione.</span><span class="sxs-lookup"><span data-stu-id="caa1f-135">Review all the tasks that are included in the prerequisite, and complete only the tasks that apply to you.</span></span>

### <a name="set-up-a-retail-store"></a><span data-ttu-id="caa1f-136">Impostare un punto vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="caa1f-136">Set up a retail store</span></span>

<span data-ttu-id="caa1f-137">Dopo aver completato le attività prerequisite, completare le attività seguenti per impostare i dettagli del punto vendita al dettaglio:</span><span class="sxs-lookup"><span data-stu-id="caa1f-137">After you complete the prerequisite tasks, complete these tasks to set up the details for the retail store:</span></span>

1.  <span data-ttu-id="caa1f-138">Creare un punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="caa1f-138">Create a retail store.</span></span>
2.  <span data-ttu-id="caa1f-139">Assegnare una fascia IVA al punto vendita.</span><span class="sxs-lookup"><span data-stu-id="caa1f-139">Assign a sales tax group to the store.</span></span>
3.  <span data-ttu-id="caa1f-140">Assegnare i metodi di pagamento accettati al punto vendita.</span><span class="sxs-lookup"><span data-stu-id="caa1f-140">Assign the accepted payment methods to the store.</span></span>
4.  <span data-ttu-id="caa1f-141">Aggiungere dettagli alle descrizioni di prodotto per i prodotti offerti che nei punti vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="caa1f-141">Add details to the product descriptions for products that you offer in your retail stores.</span></span> <span data-ttu-id="caa1f-142">Ad esempio, è possibile aggiungere il formato RTF e le immagini.</span><span class="sxs-lookup"><span data-stu-id="caa1f-142">For example, you can add rich text and images.</span></span> <span data-ttu-id="caa1f-143">Tali dettagli del prodotto vengono visualizzati in vari contesti, ad esempio sul registratore di cassa POS o nelle etichette stampate.</span><span class="sxs-lookup"><span data-stu-id="caa1f-143">These product details appear in various contexts, such as on the POS register or on printed labels.</span></span>
5.  <span data-ttu-id="caa1f-144">Aggiungere il punto vendita alla gerarchia organizzativa predefinita assegnata a uno scopo di **Assortimento di articoli al dettaglio**, **Rifornimento per vendita al dettaglio** o **Report per vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="caa1f-144">Add the store to the default organization hierarchy that is assigned to a purpose of **Retail assortment**, **Retail replenishment**, or **Retail reporting**.</span></span>

### <a name="after-you-set-up-a-retail-store"></a><span data-ttu-id="caa1f-145">Dopo aver impostato un punto vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="caa1f-145">After you set up a retail store</span></span>

<span data-ttu-id="caa1f-146">Dopo aver immesso i dettagli relativi al punto vendita al dettaglio, completare queste attività per inviare i nuovi dati del punto di vendita al dettaglio a Retail POS.</span><span class="sxs-lookup"><span data-stu-id="caa1f-146">After you enter the details for the retail store, complete these tasks to send the new retail store data to Retail POS:</span></span>

1.  <span data-ttu-id="caa1f-147">Configurare i registratori di cassa POS per il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="caa1f-147">Configure the POS registers for the store.</span></span>
2.  <span data-ttu-id="caa1f-148">Assegnare gli assortimenti dei prodotti al punto vendita.</span><span class="sxs-lookup"><span data-stu-id="caa1f-148">Assign product assortments to the store.</span></span>
3.  <span data-ttu-id="caa1f-149">Elaborare gli assortimenti per generare l'elenco di prodotti inclusi nell'assortimento e per rendere i prodotti disponibili nel punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="caa1f-149">Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store.</span></span>
4.  <span data-ttu-id="caa1f-150">Inviare i dati quali sequenze numeriche, profili hardware e layout delle schermate POS ai registratori di cassa di Retail POS.</span><span class="sxs-lookup"><span data-stu-id="caa1f-150">Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.</span></span>
5.  <span data-ttu-id="caa1f-151">Pubblicare il punto vendita al dettaglio per inviare i dati del punto vendita a Retail POS.</span><span class="sxs-lookup"><span data-stu-id="caa1f-151">Publish the retail store to send store data to Retail POS.</span></span>
6.  <span data-ttu-id="caa1f-152">Eseguire i processi per inviare i dati del punto vendita a Retail POS.</span><span class="sxs-lookup"><span data-stu-id="caa1f-152">Run the jobs to send the store data to Retail POS.</span></span>

## <a name="organization-hierarchies"></a><span data-ttu-id="caa1f-153">Gerarchie organizzative</span><span class="sxs-lookup"><span data-stu-id="caa1f-153">Organization hierarchies</span></span>
<span data-ttu-id="caa1f-154">Retail utilizza gerarchie organizzative per strutturare canali di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="caa1f-154">Retail uses organization hierarchies to structure retail channels.</span></span> <span data-ttu-id="caa1f-155">Le gerarchie organizzative rappresentano i rapporti tra le organizzazioni che fanno parte dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="caa1f-155">Organization hierarchies represent the relationships between the organizations that make up your business.</span></span> <span data-ttu-id="caa1f-156">Quando si impostano gli archivi, è possibile aggiungerli a una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="caa1f-156">When you set up stores, you can add them to an organization hierarchy.</span></span> <span data-ttu-id="caa1f-157">I punti vendita, quindi, condividono i dati utilizzati per assortimenti, rifornimento e reporting.</span><span class="sxs-lookup"><span data-stu-id="caa1f-157">The stores then share data that is used for assortments, replenishment, and reporting.</span></span>




