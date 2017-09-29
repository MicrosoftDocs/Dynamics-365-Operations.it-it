---
title: "Impostare la funzionalità di accesso esteso per POS cloud e MPOS"
description: Questo argomento illustra le opzioni per l'impostazione dell'accesso esteso per POS cloud e Retail Modern POS (MPOS).
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e29aea4509dd323c295b02f289fbcfa46fab3392
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---

# <a name="set-up-extended-logon-functionality-for-cloud-pos-and-mpos"></a><span data-ttu-id="62059-103">Impostare la funzionalità di accesso esteso per POS cloud e MPOS</span><span class="sxs-lookup"><span data-stu-id="62059-103">Set up extended logon functionality for Cloud POS and MPOS</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="62059-104">Questo argomento illustra le opzioni per l'impostazione dell'accesso esteso per POS cloud e Retail Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="62059-104">This topic covers your options for setting up extended logon for Cloud POS and Retail Modern POS (MPOS).</span></span>

<a name="setting-up-extended-logon"></a><span data-ttu-id="62059-105">Impostazione dell'accesso esteso</span><span class="sxs-lookup"><span data-stu-id="62059-105">Setting up extended logon</span></span>
=========================

<span data-ttu-id="62059-106">Le impostazioni per le maschere dei codici a barre sono disponibili in **Vendita al dettaglio** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Profili POS** &gt; **Profili funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="62059-106">You can find the setup for bar code masks at **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profiles** &gt; **Functionality profiles**.</span></span> <span data-ttu-id="62059-107">La scheda Dettaglio **Funzioni** include le seguenti opzioni correlate all'accesso esteso.</span><span class="sxs-lookup"><span data-stu-id="62059-107">The **Functions** FastTab includes the following options that are related to extended logon.</span></span>

### <a name="staff-bar-code-logon"></a><span data-ttu-id="62059-108">Accesso personale con codice a barre</span><span class="sxs-lookup"><span data-stu-id="62059-108">Staff bar code logon</span></span>

<span data-ttu-id="62059-109">Se l'opzione **Accesso personale con codice a barre** è attivata, i lavoratori con accesso esteso assegnato alle credenziali del POS possono collegarsi mediante un codice a barre.</span><span class="sxs-lookup"><span data-stu-id="62059-109">When the **Staff bar code logon** option is enabled, workers who have an extended logon assigned to their point of sale (POS) credentials can log on by using a bar code.</span></span>

### <a name="staff-bar-code-logon-requires-password"></a><span data-ttu-id="62059-110">L'accesso personale con codice a barre richiede la password</span><span class="sxs-lookup"><span data-stu-id="62059-110">Staff bar code logon requires password</span></span>

<span data-ttu-id="62059-111">Se l'opzione **L'accesso personale con codice a barre richiede la password** è attivata, l'accesso personale con codice a barre seleziona solo il lavoratore assegnato all'accesso esteso che viene presentato.</span><span class="sxs-lookup"><span data-stu-id="62059-111">When the **Staff bar code logon requires password** option is enabled, the staff bar code logon selects only the worker who is assigned to the extended logon that is presented.</span></span> <span data-ttu-id="62059-112">I lavoratori devono comunque immettere la propria password se questa opzione è abilitata.</span><span class="sxs-lookup"><span data-stu-id="62059-112">Workers must still enter their password when this option is enabled.</span></span>

### <a name="staff-card-logon"></a><span data-ttu-id="62059-113">Accesso personale con badge</span><span class="sxs-lookup"><span data-stu-id="62059-113">Staff card logon</span></span>

<span data-ttu-id="62059-114">Se l'opzione **Accesso personale con badge** è attivata, i lavoratori con accesso esteso assegnato alle credenziali del POS possono collegarsi mediante una banda magnetica.</span><span class="sxs-lookup"><span data-stu-id="62059-114">When the **Staff card logon** option is enabled, workers who have an extended logon assigned to their POS credentials can log on by using a magnetic stripe.</span></span>

### <a name="staff-card-logon-requires-password"></a><span data-ttu-id="62059-115">L'accesso personale con badge richiede la password</span><span class="sxs-lookup"><span data-stu-id="62059-115">Staff card logon requires password</span></span>

<span data-ttu-id="62059-116">Se l'opzione **L'accesso personale con badge richiede la password** è attivata, l'accesso personale con badge seleziona solo il lavoratore assegnato all'accesso esteso che viene presentato.</span><span class="sxs-lookup"><span data-stu-id="62059-116">When the **Staff card logon requires password** option is enabled, the staff card logon selects only the worker who is assigned to the extended logon that is presented.</span></span> <span data-ttu-id="62059-117">I lavoratori devono comunque immettere la propria password se questa opzione è abilitata.</span><span class="sxs-lookup"><span data-stu-id="62059-117">Workers must still enter their password when this option is enabled.</span></span>

<a name="assigning-an-extended-logon"></a><span data-ttu-id="62059-118">Assegnazione di un accesso esteso</span><span class="sxs-lookup"><span data-stu-id="62059-118">Assigning an extended logon</span></span>
===========================

<span data-ttu-id="62059-119">Per impostazione predefinita, solo i responsabili possono assegnare l'accesso esteso lavoratori.</span><span class="sxs-lookup"><span data-stu-id="62059-119">By default, only managers can assign extended logon to workers.</span></span> <span data-ttu-id="62059-120">Per assegnare l'accesso esteso, passare a ** **Accesso esteso** ** nel POS.</span><span class="sxs-lookup"><span data-stu-id="62059-120">To assign extended logon, go to **Extended log on** in POS.</span></span> <span data-ttu-id="62059-121">Quindi cercare un lavoratore immettendo il relativo ID operatore nel campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="62059-121">Then search for a worker by entering his or her operator ID in the search field.</span></span> <span data-ttu-id="62059-122">Selezionare il lavoratore e quindi fare clic su **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="62059-122">Select the worker, and then click **Assign**.</span></span> <span data-ttu-id="62059-123">Nella pagina successiva, passare o leggere con lo scanner l'accesso esteso per assegnarlo al lavoratore.</span><span class="sxs-lookup"><span data-stu-id="62059-123">On the next page, swipe or scan the extended logon to assign to the worker.</span></span> <span data-ttu-id="62059-124">Se il passaggio o la scansione ha esito positivo, il pulsante **OK** diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="62059-124">If the swipe or scan is successfully read, the **OK** button becomes available.</span></span> <span data-ttu-id="62059-125">Fare clic su **OK** per salvare l'accesso esteso per il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="62059-125">Click **OK** to save the extended logon for that worker.</span></span>

<a name="deleting-an-extended-logon"></a><span data-ttu-id="62059-126">Eliminazione di un accesso esteso</span><span class="sxs-lookup"><span data-stu-id="62059-126">Deleting an extended logon</span></span>
==========================

<span data-ttu-id="62059-127">Per eliminare l'accesso esteso assegnato a un lavoratore, individuare il lavoratore utilizzando l'operazione **Accesso esteso**.</span><span class="sxs-lookup"><span data-stu-id="62059-127">To delete the extended logon that is assigned to a worker, search for the worker by using the **Extended log on** operation.</span></span> <span data-ttu-id="62059-128">Selezionare il lavoratore e fare clic sulla scheda **Annulla assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="62059-128">Select the worker, and then click **Unassign**.</span></span> <span data-ttu-id="62059-129">Tutte le credenziali di accesso esteso associate al lavoratore verranno rimosse.</span><span class="sxs-lookup"><span data-stu-id="62059-129">All extended logon credentials that are associated with that worker are removed.</span></span>

<a name="extending-extended-logon"></a><span data-ttu-id="62059-130">Estensione dell'accesso esteso</span><span class="sxs-lookup"><span data-stu-id="62059-130">Extending extended logon</span></span>
========================

<span data-ttu-id="62059-131">Il servizio di accesso può essere esteso per supportare dispositivi di accesso estesi aggiuntivi, ad esempio scanner palmari.</span><span class="sxs-lookup"><span data-stu-id="62059-131">The logon service can be extended to support additional extended logon devices, such as palm scanners.</span></span> <span data-ttu-id="62059-132">Per ulteriori informazioni, vedere la documentazione di POS sull'estendibilità.</span><span class="sxs-lookup"><span data-stu-id="62059-132">For more information, see the POS extensibility documentation.</span></span>

<a name="using-extended-logon"></a><span data-ttu-id="62059-133">Utilizzo dell'accesso esteso</span><span class="sxs-lookup"><span data-stu-id="62059-133">Using extended logon</span></span>
====================

<span data-ttu-id="62059-134">Se l'accesso esteso è configurato e un lavoratore è stato assegnato a un codice a barre o una banda magnetica, il lavoratore dovrà semplicemente passare o eseguire la scansione della scheda durante la visualizzazione della pagina di accesso del POS.</span><span class="sxs-lookup"><span data-stu-id="62059-134">When extended logon is configured, and a worker has been assigned a bar code or magnetic stripe, the worker just has to swipe or scan his or her card while the POS logon page is displayed.</span></span> <span data-ttu-id="62059-135">Se è necessaria anche una password prima che l'accesso possa continuare, al lavoratore viene richiesto di immettere la relativa password.</span><span class="sxs-lookup"><span data-stu-id="62059-135">If a password is also required before logon can proceed, the worker is prompted to enter his or her password.</span></span>




