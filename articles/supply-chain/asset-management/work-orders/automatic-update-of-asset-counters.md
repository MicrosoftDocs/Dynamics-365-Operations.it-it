---
title: Aggiornamento automatico dei contatori di cespiti
description: In questo argomento viene descritto l'aggiornamento automatico dei contatori di cespiti in Gestione cespiti
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d51b9a7684e460d555632c3896e9dd8a4e10d92c
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626180"
---
# <a name="automatic-update-of-asset-counters"></a><span data-ttu-id="e9bc5-103">Aggiornamento automatico dei contatori di cespiti</span><span class="sxs-lookup"><span data-stu-id="e9bc5-103">Automatic update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e9bc5-104">Per informazioni sulla registrazione manuale dei contatori di cespiti, vedere [Aggiornamento manuale dei contatori di cespiti](../work-orders/manual-update-of-asset-counters.md).</span><span class="sxs-lookup"><span data-stu-id="e9bc5-104">For information about manual registration of asset counters, see [Manual update of asset counters](../work-orders/manual-update-of-asset-counters.md).</span></span> <span data-ttu-id="e9bc5-105">Per informazioni su come impostare i contatori di cespiti, vedere [Contatori](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="e9bc5-105">For information on how to set up asset counters, see [Counters](../setup-for-objects/counters.md).</span></span>

<span data-ttu-id="e9bc5-106">I valori dei contatori possono essere aggiornati automaticamente dalle registrazioni di produzione, basate sulle ore di produzione o sulla quantità di produzione (ossia la quantità prodotta).</span><span class="sxs-lookup"><span data-stu-id="e9bc5-106">Counter values can also be automatically updated from production registrations, based on the production hours or production quantity (that is, the quantity that is produced).</span></span> <span data-ttu-id="e9bc5-107">Questo aggiornamento viene eseguito nella pagina **Aggiornare i contatori di cespiti**.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-107">This update is done on the **Update asset counters** page.</span></span> <span data-ttu-id="e9bc5-108">È possibile aggiornare uno o più cespiti impostando il parametro **Dal**.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-108">You can update one or several assets by setting one parameter, **From date**.</span></span> <span data-ttu-id="e9bc5-109">Questo parametro specifica la data di inizio per le registrazioni di produzione (ore di produzione o quantità di produzione).</span><span class="sxs-lookup"><span data-stu-id="e9bc5-109">This parameter specifies the start date for production registrations (production hours or production quantities).</span></span> <span data-ttu-id="e9bc5-110">In altre parole, specifica la data di inizio dell'aggiornamento dei controvalori.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-110">In other words, it specifies the date that counter values should be updated from.</span></span>

<span data-ttu-id="e9bc5-111">Tutti i cespiti correlati a una risorsa *e* che hanno contatori di cespiti, i quali sono impostati per essere aggiornati in base alle ore di produzione o alla quantità di produzione, saranno inclusi in un aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-111">All assets that are related to a resource, *and* that have asset counters that are set up to be updated based on the production hours or production quantity, will be included in an automatic update.</span></span> <span data-ttu-id="e9bc5-112">I nuovi controvalori verranno creati.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-112">New counter values will be created.</span></span>

<span data-ttu-id="e9bc5-113">Per i contatori basati sulla quantità di produzione, il conteggio include la quantità idonea e la quantità difettosa registrate.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-113">For counters that are based on the production quantity, the count includes both the good quantity and the error quantity that are registered.</span></span> <span data-ttu-id="e9bc5-114">Se l'unità utilizzata per la registrazione della quantità di produzione è diversa dall'unità utilizzata per il contatore, la quantità viene convertita per corrispondere all'unità del contatore.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-114">If the unit that is used for production quantity registration differs from the unit that is used for the counter, the quantity is converted so that it corresponds to the counter unit.</span></span>

<span data-ttu-id="e9bc5-115">Come descritto in precedenza, i contatori automatici possono essere aggiornati dalle registrazioni di produzione.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-115">As mentioned above, automatic counters can be updated from production registrations.</span></span> <span data-ttu-id="e9bc5-116">Di conseguenza, il cespite per il quale si desidera aggiornare automaticamente i contatori deve essere associato a una risorsa (macchina).</span><span class="sxs-lookup"><span data-stu-id="e9bc5-116">Therefore, the asset for which you want to automatically update counters must be related to a resource (machine).</span></span> <span data-ttu-id="e9bc5-117">Quando le quantità prodotte o le ore di produzione sono state registrate nella risorsa, è possibile aggiornare i contatori di cespiti correlati.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-117">When produced quantities or production hours have been registered on the resource, you can update the related asset counters.</span></span>

1. <span data-ttu-id="e9bc5-118">Selezionare **Gestione cespiti** > **Periodico** > **Cespiti** > **Aggiorna contatori di cespiti**.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-118">Select **Asset management** > **Periodic** > **Assets** > **Update asset counters**.</span></span>

2. <span data-ttu-id="e9bc5-119">Selezionare la data di inizio dell'aggiornamento automatico nel campo **Dal**.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-119">In the **From date** field, select the start date of the automatic update.</span></span>

>[!NOTE]
><span data-ttu-id="e9bc5-120">La data in questo campo corrisponde alla data "WIP" in **Transazioni cicli di lavorazione** (**Controllo produzione** > **Richieste di informazioni e report** > **Produzione** > **Transazioni cicli di lavorazione** > **Data effettiva**).</span><span class="sxs-lookup"><span data-stu-id="e9bc5-120">The date in this field is the "work in progress" date from **Route transactions** (**Production control** > **Inquiries and reports** > **Production** > **Route transactions** > **Physical date** field).</span></span>

3. <span data-ttu-id="e9bc5-121">Nella Scheda dettaglio **Record da includere**, è possibile selezionare i cespiti, i tipi di cespite o le risorse per l'aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-121">On the **Records to include** FastTab, you can select specific assets, asset types, or resources for the automatic update.</span></span> <span data-ttu-id="e9bc5-122">Selezionare **Filtro** ed effettuare la selezione delle opzioni rilevanti.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-122">Select **Filter**, and make the relevant selections.</span></span>

4. <span data-ttu-id="e9bc5-123">Nella Scheda dettaglio **Esecuzione in background**, è possibile impostare l'aggiornamento automatico come processo batch, come necessario.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-123">On the **Run in the background** FastTab, you can set up the automatic update as a batch job, as you require.</span></span>

<span data-ttu-id="e9bc5-124">Nella figura seguente è illustrato un esempio della finestra di dialogo **Aggiornare i contatori di cespiti**.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-124">The illustration below shows an example of the **Update asset counters** dialog.</span></span>

![Figura 1](media/12-work-orders.png)

5. <span data-ttu-id="e9bc5-126">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-126">Select **OK**.</span></span> 

<span data-ttu-id="e9bc5-127">Dopo l'aggiornamento automatico del contatore di cespiti, è possibile visualizzare le registrazioni del contatore correlate al cespite nella pagina **Contatori cespiti**.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-127">After the automatic asset counter update is done, you can view the counter registrations that are related to the asset on the **Asset counters** page.</span></span> <span data-ttu-id="e9bc5-128">Selezionare **Gestione cespiti** > **Comune** > **Cespiti** > **Tutti i cespiti**, selezionare il cespite, quindi nel riquadro azioni, nella scheda **Cespite**, nel gruppo **Preventivo** selezionare **Contatori**.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-128">Select **Asset management** > **Common** > **Assets** > **All assets**, select the asset, and then, on the Action Pane, on the **Asset** tab, in the **Preventive** group, select **Counters**.</span></span>

<span data-ttu-id="e9bc5-129">Nella pagina **Valore aggregato cespiti**, è possibile ottenere una panoramica dell'ultima registrazione effettuata in tutti i cespiti di tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-129">On the **Asset aggregated value** page, you can get an overview of the latest registration that have been made on all counter types on all assets.</span></span> <span data-ttu-id="e9bc5-130">Selezionare **Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **Valore aggregato cespiti**.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-130">Select **Asset management** > **Inquiries** > **Assets** > **Asset aggregated value**.</span></span> <span data-ttu-id="e9bc5-131">Questa pagina è simile alla pagina **Contatori cespiti**, ma non è possibile aggiungere o modificare le registrazioni.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-131">This page resembles the **Asset counters** page, but you can't add or edit registrations.</span></span> <span data-ttu-id="e9bc5-132">La visualizzazione è disponibile solo a scopo informativo.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-132">It's for overview only.</span></span>

<span data-ttu-id="e9bc5-133">Nella figura seguente è illustrato un esempio della pagina **Valore aggregato cespiti**.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-133">The illustration below shows an example of the **Asset aggregated value** page.</span></span>

![Figura 2](media/13-work-orders.png)

<span data-ttu-id="e9bc5-135">Notare i punti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9bc5-135">Note the following points:</span></span>

- <span data-ttu-id="e9bc5-136">È comunque possibile creare registrazioni manuali dei valori di contatore per i tipi di contatori che vengono aggiornati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-136">You can still create manual counter value registrations for counter types that are automatically updated.</span></span> <span data-ttu-id="e9bc5-137">Per ulteriori informazioni, vedere [Aggiornamento manuale dei contatori di cespiti](../work-orders/manual-update-of-asset-counters.md).</span><span class="sxs-lookup"><span data-stu-id="e9bc5-137">For more information, see [Manual update of asset counters](../work-orders/manual-update-of-asset-counters.md).</span></span>

- <span data-ttu-id="e9bc5-138">È possibile impostare i contatori correlati a un altro contatore.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-138">You can set up counters that are related to another counter.</span></span> <span data-ttu-id="e9bc5-139">In questo caso, quando un contatore viene aggiornato, i contatori correlati vengono aggiornati automaticamente contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e9bc5-139">In this case, when a counter is updated, related counters are automatically updated at the same time.</span></span> <span data-ttu-id="e9bc5-140">Per ulteriori informazioni su come impostare i contatori correlati, vedere [Contatori](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="e9bc5-140">For more information about how to set up related counters, see [Counters](../setup-for-objects/counters.md).</span></span>

