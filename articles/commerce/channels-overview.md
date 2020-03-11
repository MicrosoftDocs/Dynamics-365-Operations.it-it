---
title: Panoramica dei canali
description: Questo argomento fornisce una panoramica dei canali di Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 099ccd9f769ea5c431c1a82532d8654cbbd082b1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002360"
---
# <a name="channels-overview"></a><span data-ttu-id="edf2d-103">Panoramica dei canali</span><span class="sxs-lookup"><span data-stu-id="edf2d-103">Channels overview</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="edf2d-104">Questo argomento fornisce una panoramica dei canali di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="edf2d-104">This topic presents an overview of channels in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="edf2d-105">Sono riportate informazioni sulle attività da completare prima e dopo la configurazione di ciascun canale.</span><span class="sxs-lookup"><span data-stu-id="edf2d-105">It includes information about the tasks that you must complete both before and after you set up each channel.</span></span>

## <a name="types-of-channels"></a><span data-ttu-id="edf2d-106">Tipi di canali</span><span class="sxs-lookup"><span data-stu-id="edf2d-106">Types of Channels</span></span>

<span data-ttu-id="edf2d-107">Dynamics 365 Commerce supporta tre diversi tipi di canali: vendita al dettaglio, servizio clienti e online.</span><span class="sxs-lookup"><span data-stu-id="edf2d-107">Dynamics 365 Commerce supports three different channel types: retail, call center, and online channels.</span></span>

### <a name="retail-channels"></a><span data-ttu-id="edf2d-108">Canali di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="edf2d-108">Retail channels</span></span>

<span data-ttu-id="edf2d-109">I canali di vendita al dettaglio rappresentano i punti vendita fisici.</span><span class="sxs-lookup"><span data-stu-id="edf2d-109">Retail channels represent standard brick-and-mortar stores.</span></span> <span data-ttu-id="edf2d-110">Ogni punto vendita può disporre dei propri registratori di cassa POS, conti ricavi/spese e personale.</span><span class="sxs-lookup"><span data-stu-id="edf2d-110">Each store can have its own point of sale (POS) registers, income and expense accounts, and staff.</span></span> 

### <a name="call-center-channels"></a><span data-ttu-id="edf2d-111">Canale servizio clienti</span><span class="sxs-lookup"><span data-stu-id="edf2d-111">Call center channels</span></span>

<span data-ttu-id="edf2d-112">I canali servizio clienti rappresentano la gestione degli ordini e dei clienti del servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="edf2d-112">Call center channels represent call center order and customer management.</span></span>

### <a name="online-channels"></a><span data-ttu-id="edf2d-113">Canale online</span><span class="sxs-lookup"><span data-stu-id="edf2d-113">Online channels</span></span>

<span data-ttu-id="edf2d-114">I canali online rappresentano i punti vendita di e-commerce online.</span><span class="sxs-lookup"><span data-stu-id="edf2d-114">Online channels represent online e-Commerce storefronts.</span></span> <span data-ttu-id="edf2d-115">Dopo la creazione di un canale online, è necessario creare un sito utilizzando lo strumento Creazione di siti Web di Microsoft Dynamics 365 Commerce o un'altra soluzione di e-commerce di terze parti.</span><span class="sxs-lookup"><span data-stu-id="edf2d-115">Once an online channel is created, a site must be created using the Microsoft Dynamics 365 Commerce Site Builder tool or other third-party e-Commerce solution.</span></span>

## <a name="channel-setup-basics"></a><span data-ttu-id="edf2d-116">Nozioni di base sull'impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="edf2d-116">Channel setup basics</span></span>

<span data-ttu-id="edf2d-117">L'impostazione dei canali viene eseguita nello strumento Commerce.</span><span class="sxs-lookup"><span data-stu-id="edf2d-117">Channel set up is performed in the Commerce tool.</span></span> <span data-ttu-id="edf2d-118">Ogni canale può avere i propri metodi di pagamento, gruppi di prezzi, gerarchie di prodotti, assortimenti e set di prodotti.</span><span class="sxs-lookup"><span data-stu-id="edf2d-118">Each channel can have its own payment methods, price groups, product hierarchies, assortments, and set of products.</span></span> <span data-ttu-id="edf2d-119">Dopo aver creato un canale, assegnare i prodotti che il canale deve presentare e vendere.</span><span class="sxs-lookup"><span data-stu-id="edf2d-119">After you create a channel, you assign the products that you want it to carry and sell.</span></span> <span data-ttu-id="edf2d-120">Ogni tipo di canale ha un set univoco di funzionalità che potrebbero dover essere configurate.</span><span class="sxs-lookup"><span data-stu-id="edf2d-120">Each channel type has a unique set of features that may need to be configured.</span></span> <span data-ttu-id="edf2d-121">Ad esempio, un canale di vendita al dettaglio necessita di registratori di cassa, clienti e dipendenti assegnati.</span><span class="sxs-lookup"><span data-stu-id="edf2d-121">For example, a retail channel needs assigned employees, registers, and customers.</span></span> <span data-ttu-id="edf2d-122">Una volta creato un nuovo canale, deve essere assegnato a una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="edf2d-122">Once a new channel is created, it needs to be assigned to an organization hierarchy.</span></span>

## <a name="channel-setup-prerequisites"></a><span data-ttu-id="edf2d-123">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="edf2d-123">Channel setup prerequisites</span></span>

<span data-ttu-id="edf2d-124">Prima di poter impostare un canale, è necessario completare alcune attività preliminari in base al tipo di canale.</span><span class="sxs-lookup"><span data-stu-id="edf2d-124">Before you can set up a channel, you must complete some prerequisite tasks based on the channel type.</span></span> <span data-ttu-id="edf2d-125">Per ulteriori informazioni, vedere [Prerequisiti di impostazione dei canali](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="edf2d-125">For more information, see [Channel setup prerequisites](channels-prerequisites.md).</span></span>

## <a name="set-up-a-channel"></a><span data-ttu-id="edf2d-126">Impostare un canale</span><span class="sxs-lookup"><span data-stu-id="edf2d-126">Set up a channel</span></span>

<span data-ttu-id="edf2d-127">Dopo aver completato le attività preliminari, per ulteriori istruzioni sull'impostazione, utilizzare i seguenti collegamenti.</span><span class="sxs-lookup"><span data-stu-id="edf2d-127">After you complete the prerequisite tasks, for further setup instructions, use the following links.</span></span>

- [<span data-ttu-id="edf2d-128">Impostare un canale di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="edf2d-128">Set up a retail channel</span></span>](channel-setup-retail.md)
- [<span data-ttu-id="edf2d-129">Impostare un canale servizio clienti</span><span class="sxs-lookup"><span data-stu-id="edf2d-129">Set up a call center channel</span></span>](channel-setup-callcenter.md)
- [<span data-ttu-id="edf2d-130">Impostare un canale online</span><span class="sxs-lookup"><span data-stu-id="edf2d-130">Set up an online channel</span></span>](channel-setup-online.md)

<!--
## Post-channel configuration

After you create a channel, you may need to complete some of the below tasks:

- [Add channel to an organizational hierarchy](add-channel-org-hierarchy.md)
- Set up fulfillment groups. (LINK TBD)
- Configure the POS registers for the store. (LINK TBD)
- Assign product assortments to the store. (LINK TBD)
- Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store. (LINK TBD)
- Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.(LINK TBD)
- Publish the retail store to send store data to Retail POS. (LINK TBD)
- Run the jobs to send the store data to Retail POS. (LINK TBD)
-->

## <a name="additional-resources"></a><span data-ttu-id="edf2d-131">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="edf2d-131">Additional resources</span></span>

[<span data-ttu-id="edf2d-132">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="edf2d-132">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="edf2d-133">Impostare un canale di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="edf2d-133">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="edf2d-134">Impostare un canale online</span><span class="sxs-lookup"><span data-stu-id="edf2d-134">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="edf2d-135">Impostare un canale servizio clienti</span><span class="sxs-lookup"><span data-stu-id="edf2d-135">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="edf2d-136">Impostare gerarchie organizzative</span><span class="sxs-lookup"><span data-stu-id="edf2d-136">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)