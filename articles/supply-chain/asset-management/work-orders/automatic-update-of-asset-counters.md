---
title: Aggiornamento automatico dei contatori di cespiti
description: In questo argomento viene descritto l'aggiornamento automatico dei contatori di cespiti in Gestione cespiti
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97e6912cd37d6f82d8bf022141f04645a3364ee1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875742"
---
# <a name="automatic-update-of-asset-counters"></a><span data-ttu-id="bfdda-103">Aggiornamento automatico dei contatori di cespiti</span><span class="sxs-lookup"><span data-stu-id="bfdda-103">Automatic update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="bfdda-104">Nella sezione precedente, è stata descritta la registrazione manuale dei contatori di cespiti.</span><span class="sxs-lookup"><span data-stu-id="bfdda-104">In the previous section, manual registration of asset counters is described.</span></span> <span data-ttu-id="bfdda-105">L'impostazione dei contatori di cespiti è descritta in [Contatori](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="bfdda-105">Setup of asset counters is described in [Counters](../setup-for-objects/counters.md).</span></span>

<span data-ttu-id="bfdda-106">I valori dei contatori possono essere aggiornati automaticamente dalle registrazioni di produzione, basate sulle ore di produzione o sulla quantità prodotta.</span><span class="sxs-lookup"><span data-stu-id="bfdda-106">Counter values can also be automatically updated from production registrations, based on production hours or production quantity.</span></span> <span data-ttu-id="bfdda-107">A questo proposito, si utilizza **Aggiorna contatori di cespiti**.</span><span class="sxs-lookup"><span data-stu-id="bfdda-107">This is done in **Update asset counters**.</span></span> <span data-ttu-id="bfdda-108">È possibile aggiornare uno o più cespiti inserendo il parametro **Dal**.</span><span class="sxs-lookup"><span data-stu-id="bfdda-108">You can update one or several assets by inserting one parameter, **From date**.</span></span> <span data-ttu-id="bfdda-109">Questo parametro specifica la data di inizio delle registrazioni di produzione (ore o quantità prodotte), ovvero la data a partire dalla quale i valori dei contatori devono essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="bfdda-109">This parameter specifies the start date for production registrations (hours or quantity produced), meaning the start date from which counter values should be updated.</span></span>

<span data-ttu-id="bfdda-110">Tutti i cespiti correlati a una risorsa *e* che hanno contatori di cespiti, i quali sono impostati per essere aggiornati in base alle ore di produzione o alla quantità prodotta, saranno inclusi in un aggiornamento automatico e verranno creati nuovi valori dei contatori.</span><span class="sxs-lookup"><span data-stu-id="bfdda-110">All assets that are related to a resource *and* have asset counters, which are set up to be updated based on produced quantity or production hours, will be included in an automatic update, and new counter values will be created.</span></span>

<span data-ttu-id="bfdda-111">I contatori basati sulla quantità di produzione, la quantità idonea e la quantità difettosa registrate sono inclusi nel conteggio.</span><span class="sxs-lookup"><span data-stu-id="bfdda-111">Regarding counters based on production quantity, good quantity as well as error quantity registered are included in the count.</span></span> <span data-ttu-id="bfdda-112">Se l'unità utilizzata per la registrazione della quantità prodotta è diversa dall'unità utilizzata nel contatore, la quantità viene convertita per corrispondere all'unità del contatore.</span><span class="sxs-lookup"><span data-stu-id="bfdda-112">If the unit used for produced quantity registration is different from the unit used on the counter, quantity is converted to correspond with the counter unit.</span></span>

<span data-ttu-id="bfdda-113">Come descritto in precedenza, i contatori automatici possono essere aggiornati dalle registrazioni di produzione.</span><span class="sxs-lookup"><span data-stu-id="bfdda-113">As mentioned above, automatic counters can be updated from production registrations.</span></span> <span data-ttu-id="bfdda-114">Di conseguenza, il cespite per il quale si desidera aggiornare automaticamente i contatori deve essere associato a una risorsa (macchina).</span><span class="sxs-lookup"><span data-stu-id="bfdda-114">Therefore, the asset for which you want to automatically update counters must be related to a resource (machine).</span></span> <span data-ttu-id="bfdda-115">Le descrizioni riportate di seguito forniscono una panoramica dell'impostazione e dell'elaborazione degli ordini di produzione (nel modulo **Controllo produzione**), utilizzata come base per l'aggiornamento automatico dei contatori in un cespite nel modulo **Gestione cespiti**.</span><span class="sxs-lookup"><span data-stu-id="bfdda-115">The following descriptions provide an overview of the setup and processing of production orders (in the **Production control** module), which is used as a basis for automatic update of counters on an asset in the **Asset management** module.</span></span>

<span data-ttu-id="bfdda-116">Quando le quantità prodotte o le ore di produzione sono state registrate nella risorsa, è possibile aggiornare i contatori di cespiti correlati.</span><span class="sxs-lookup"><span data-stu-id="bfdda-116">When produced quantities or production hours have been registered on the resource, you can update the related asset counters.</span></span>

1. <span data-ttu-id="bfdda-117">Fare clic su **Gestione cespiti** > **Periodico** > **Cespiti** > **Aggiorna contatori di cespiti**.</span><span class="sxs-lookup"><span data-stu-id="bfdda-117">Click **Asset management** > **Periodic** > **Assets** > **Update asset counters**.</span></span>

2. <span data-ttu-id="bfdda-118">Selezionare la data di inizio dell'aggiornamento automatico nel campo **Dal**.</span><span class="sxs-lookup"><span data-stu-id="bfdda-118">Select the start date of the automatic update in the **From date** field.</span></span>

>[!NOTE]
><span data-ttu-id="bfdda-119">La data in questo campo corrisponde alla data "WIP" in **Transazioni cicli di lavorazione** (**Controllo produzione** > **Richieste di informazioni e report** > **Produzione** > **Transazioni cicli di lavorazione** > **Data effettiva**).</span><span class="sxs-lookup"><span data-stu-id="bfdda-119">The date in this field is the "work in progress" date from **Route transactions** (**Production control** > **Inquiries and reports** > **Production** > **Route transactions** > **Physical date** field).</span></span>

3. <span data-ttu-id="bfdda-120">Se si desidera selezionare specifici cespiti, tipi di cespite o risorse per l'aggiornamento automatico, fare clic su **Filtro** nella Scheda dettaglio **Record da includere** ed effettuare le selezioni pertinenti.</span><span class="sxs-lookup"><span data-stu-id="bfdda-120">If you want to select specific assets, asset types, or resources for the automatic update, click **Filter** on the **Records to include** FastTab, and make the relevant selections.</span></span>

4. <span data-ttu-id="bfdda-121">Se necessario, è possibile impostare l'aggiornamento automatico come processo batch nella Scheda dettaglio **Esecuzione in background**.</span><span class="sxs-lookup"><span data-stu-id="bfdda-121">If required, you can set up the automatic update as a batch job on the **Run in the background** FastTab.</span></span>

![Figura 1](media/12-work-orders.png)

5. <span data-ttu-id="bfdda-123">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfdda-123">Click **OK**.</span></span> <span data-ttu-id="bfdda-124">Dopo l'aggiornamento automatico dei contatori di cespiti, è possibile visualizzare le registrazioni contatore relative al cespite in **Contatori cespiti** (**Gestione cespiti** > **Comune** > **Cespiti** > **Tutti i cespiti** > selezionare il cespite > pulsante **Contatori** ).</span><span class="sxs-lookup"><span data-stu-id="bfdda-124">When the automatic asset counter update is done, you can see the counter registrations related to the asset in **Asset counters** (**Asset management** > **Common** > **Assets** > **All assets** > select asset > **Counters** button).</span></span>

<span data-ttu-id="bfdda-125">In **totali contatori cespiti**, è possibile ottenere una panoramica dell'ultima registrazione effettuata in tutti i cespiti di tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="bfdda-125">In **Asset counter totals**, you can get an overview of the latest registration made on all counter types on all assets.</span></span> <span data-ttu-id="bfdda-126">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **Valore aggregato cespiti**.</span><span class="sxs-lookup"><span data-stu-id="bfdda-126">Click **Asset management** > **Inquiries** > **Assets** > **Asset aggregated value**.</span></span> <span data-ttu-id="bfdda-127">La visualizzazione è molto simile a **Contatori cespiti**, ma non è possibile aggiungere o modificare le registrazioni in **Valore aggregato cespiti**.</span><span class="sxs-lookup"><span data-stu-id="bfdda-127">The view is very similar to **Asset counters**, but you cannot add or edit registrations in **Asset aggregated value**.</span></span> <span data-ttu-id="bfdda-128">La visualizzazione è disponibile solo a scopo informativo.</span><span class="sxs-lookup"><span data-stu-id="bfdda-128">It is for overview only.</span></span>

![Figura 2](media/13-work-orders.png)


- <span data-ttu-id="bfdda-130">È sempre possibile creare registrazioni manuali dei valori di contatore per i tipi di contatori che vengono aggiornati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bfdda-130">It is still possible to create manual counter value registrations for counter types that are automatically updated.</span></span> <span data-ttu-id="bfdda-131">Per ulteriori informazioni, fare riferimento alla sezione "Aggiornamento manuale dei contatori di cespiti".</span><span class="sxs-lookup"><span data-stu-id="bfdda-131">Refer to the "Manual update of asset counters" section for more information.</span></span>
- <span data-ttu-id="bfdda-132">È possibile impostare contatori correlati a un altro contatore, ovvero quando un contatore viene aggiornato, anche i contatori associati vengono aggiornati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bfdda-132">You can set up counters related to another counter, which means that when a counter is updated, related counters are automatically updated at the same time.</span></span> <span data-ttu-id="bfdda-133">Leggere l'argomento [Contatori](../setup-for-objects/counters.md) per informazioni sull'impostazione di contatori associati.</span><span class="sxs-lookup"><span data-stu-id="bfdda-133">Refer to [Counters](../setup-for-objects/counters.md) regarding setup of related counters.</span></span>
