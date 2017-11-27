---
title: Inizializzare i dati iniziali in un nuovo ambiente di vendita al dettaglio
description: In questo articolo viene descritto i dati creati durante il processo di inizializzazione di Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7388324fe8a9abc8fc3d723b7c8df2c73d76a2ae
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a><span data-ttu-id="58c62-103">Inizializzare i dati iniziali in un nuovo ambiente di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="58c62-103">Initialize seed data in a new Retail environment</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="58c62-104">In questo articolo viene descritto i dati creati durante il processo di inizializzazione di Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="58c62-104">This article describes the data that's created as part of the initialization process for Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="58c62-105">Dopo la distribuzione della soluzione di vendita al dettaglio tramite Microsoft Dynamics Lifecycle Services (LCS), è necessario inizializzare la configurazione della soluzione per creare i dati di configurazione di base.</span><span class="sxs-lookup"><span data-stu-id="58c62-105">After the Retail solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the retail configuration to create the basic configuration data.</span></span> <span data-ttu-id="58c62-106">**Importante:** prima di inizializzare la configurazione di vendita al dettaglio, assicurarsi che sia specificata una lingua e un indirizzo postale per ogni persona giuridica per cui si desidera impostare i punti vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="58c62-106">**Important:** Before you initialize the retail configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up retail stores.</span></span> <span data-ttu-id="58c62-107">Questo passaggio deve essere completato per ogni persona giuridica che utilizza la funzionalità di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="58c62-107">This step must be completed for each legal entity that you use for retail.</span></span> <span data-ttu-id="58c62-108">Per inizializzare la configurazione della funzionalità di vendita al dettaglio, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="58c62-108">To initialize the retail configuration, follow these steps.</span></span>

1.  <span data-ttu-id="58c62-109">Avviare il client Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="58c62-109">Start the Dynamics 365 for Retail client.</span></span>
2.  <span data-ttu-id="58c62-110">Fare clic su **Vendita al dettaglio** &gt; **Impostazione sedi centrali** &gt; **Parametri** &gt; **Parametri di vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="58c62-110">Click **Retail** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Retail parameters**.</span></span>
3.  <span data-ttu-id="58c62-111">Fare clic su **Inizializza**.</span><span class="sxs-lookup"><span data-stu-id="58c62-111">Click **Initialize**.</span></span>

<span data-ttu-id="58c62-112">L'inizializzazione crea i seguenti dati di configurazione predefiniti:</span><span class="sxs-lookup"><span data-stu-id="58c62-112">Initialization creates the following default configuration data:</span></span>

-   <span data-ttu-id="58c62-113">Processi e processi secondari di Retail Scheduler</span><span class="sxs-lookup"><span data-stu-id="58c62-113">Retail scheduler jobs and subjobs</span></span>
-   <span data-ttu-id="58c62-114">Schema del canale di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="58c62-114">Retail channel schema</span></span>
-   <span data-ttu-id="58c62-115">Programmazioni della distribuzione di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="58c62-115">Retail distribution schedules</span></span>
-   <span data-ttu-id="58c62-116">Layout della schermata predefiniti, che includono griglie dei pulsanti, immagini e temi</span><span class="sxs-lookup"><span data-stu-id="58c62-116">Default screen layouts, which include button grids, images, and themes</span></span>
-   <span data-ttu-id="58c62-117">Informazioni fuso orario</span><span class="sxs-lookup"><span data-stu-id="58c62-117">Time zone information</span></span>
-   <span data-ttu-id="58c62-118">Operazioni POS</span><span class="sxs-lookup"><span data-stu-id="58c62-118">Point-of-sale (POS) operations</span></span>
-   <span data-ttu-id="58c62-119">Autorizzazioni POS</span><span class="sxs-lookup"><span data-stu-id="58c62-119">POS permissions</span></span>
-   <span data-ttu-id="58c62-120">Report canale</span><span class="sxs-lookup"><span data-stu-id="58c62-120">Channel reports</span></span>
-   <span data-ttu-id="58c62-121">Metadati di attributi</span><span class="sxs-lookup"><span data-stu-id="58c62-121">Attribute metadata</span></span>
-   <span data-ttu-id="58c62-122">Modelli di convalida entità</span><span class="sxs-lookup"><span data-stu-id="58c62-122">Entity validation templates</span></span>
-   <span data-ttu-id="58c62-123">Processo batch per l'eliminazione dello storico della sessione di scambio dei dati commerciali</span><span class="sxs-lookup"><span data-stu-id="58c62-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="58c62-124">Inoltre, la registrazione correlata a PCI (Payment Card Industry) è abilitata per il database di Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="58c62-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Dynamics 365 for Retail database.</span></span> <span data-ttu-id="58c62-125">**Nota:** è disponibile un'opzione per configurare separatamente Retail scheduler.</span><span class="sxs-lookup"><span data-stu-id="58c62-125">**Note:** There is an option to separately configure the Retail scheduler.</span></span> <span data-ttu-id="58c62-126">Questa opzione consente di reimpostare la configurazione il dettaglio dell'utilità di pianificazione con le relative impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="58c62-126">This option lets you reset the Retail scheduler configuration to its default settings.</span></span> <span data-ttu-id="58c62-127">Dopo il completamento dell'inizializzazione, è necessario configurare i dati aggiuntivi per la dati vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="58c62-127">After initialization is completed, you must configure additional retail data.</span></span> <span data-ttu-id="58c62-128">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="58c62-128">Here are some examples:</span></span>

-   <span data-ttu-id="58c62-129">Parametri di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="58c62-129">Retail parameters</span></span>
-   <span data-ttu-id="58c62-130">Parametri Retail Scheduler</span><span class="sxs-lookup"><span data-stu-id="58c62-130">Retail scheduler parameters</span></span>
-   <span data-ttu-id="58c62-131">Canali di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="58c62-131">Retail channels</span></span>
-   <span data-ttu-id="58c62-132">Registri e dispositivi</span><span class="sxs-lookup"><span data-stu-id="58c62-132">Registers and devices</span></span>
-   <span data-ttu-id="58c62-133">Assortimenti</span><span class="sxs-lookup"><span data-stu-id="58c62-133">Assortments</span></span>





