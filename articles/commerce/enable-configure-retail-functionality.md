---
title: Inizializzare i dati iniziali nei nuovi ambienti Commerce
description: In questo articolo viene descritto i dati creati durante il processo di inizializzazione di Dynamics 365 Commerce.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 9f534410b21fd97554f4e038bb14eebd5f887130
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792585"
---
# <a name="initialize-seed-data-in-new-commerce-environments"></a><span data-ttu-id="b3289-103">Inizializzare i dati iniziali nei nuovi ambienti Commerce</span><span class="sxs-lookup"><span data-stu-id="b3289-103">Initialize seed data in new Commerce environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b3289-104">In questo articolo viene descritto i dati creati durante il processo di inizializzazione di Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3289-104">This article describes the data that's created as part of the initialization process for Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b3289-105">Dopo la distribuzione della soluzione Commerce tramite Microsoft Dynamics Lifecycle Services (LCS), è necessario inizializzare la configurazione della soluzione per creare i dati di configurazione di base.</span><span class="sxs-lookup"><span data-stu-id="b3289-105">After the Commerce solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the Commerce configuration to create the basic configuration data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3289-106">Prima di inizializzare la configurazione di Commerce, assicurarsi che sia specificata una lingua e un indirizzo postale per ogni persona giuridica per cui si desidera impostare i punti vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="b3289-106">Before you initialize the commerce configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up stores.</span></span> <span data-ttu-id="b3289-107">Questo passaggio deve essere completato per ogni persona giuridica utilizzata per Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3289-107">This step must be completed for each legal entity that you use for commerce.</span></span>

<span data-ttu-id="b3289-108">Per inizializzare la configurazione procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="b3289-108">To initialize the configuration, follow these steps.</span></span>

1. <span data-ttu-id="b3289-109">Avviare il client Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3289-109">Start the Commerce client.</span></span>
2. <span data-ttu-id="b3289-110">Fare clic su **Retail e Commerce** &gt; **Impostazione sedi centrali** &gt; **Parametri** &gt; **Parametri di commercio**.</span><span class="sxs-lookup"><span data-stu-id="b3289-110">Click **Retail and Commerce** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Commerce parameters**.</span></span>
3. <span data-ttu-id="b3289-111">Fare clic su **Inizializza**.</span><span class="sxs-lookup"><span data-stu-id="b3289-111">Click **Initialize**.</span></span>

<span data-ttu-id="b3289-112">L'inizializzazione crea i seguenti dati di configurazione predefiniti:</span><span class="sxs-lookup"><span data-stu-id="b3289-112">Initialization creates the following default configuration data:</span></span>

- <span data-ttu-id="b3289-113">Processi e processi secondari dell'utilità di pianificazione di commercio</span><span class="sxs-lookup"><span data-stu-id="b3289-113">Commerce scheduler jobs and subjobs</span></span>
- <span data-ttu-id="b3289-114">Schema del canale di commercio</span><span class="sxs-lookup"><span data-stu-id="b3289-114">Commerce channel schema</span></span>
- <span data-ttu-id="b3289-115">Programmazioni di distribuzione di commercio</span><span class="sxs-lookup"><span data-stu-id="b3289-115">Commerce distribution schedules</span></span>
- <span data-ttu-id="b3289-116">Layout della schermata predefiniti, che includono griglie dei pulsanti, immagini e temi</span><span class="sxs-lookup"><span data-stu-id="b3289-116">Default screen layouts, which include button grids, images, and themes</span></span>
- <span data-ttu-id="b3289-117">Informazioni fuso orario</span><span class="sxs-lookup"><span data-stu-id="b3289-117">Time zone information</span></span>
- <span data-ttu-id="b3289-118">Operazioni POS</span><span class="sxs-lookup"><span data-stu-id="b3289-118">Point-of-sale (POS) operations</span></span>
- <span data-ttu-id="b3289-119">Autorizzazioni POS</span><span class="sxs-lookup"><span data-stu-id="b3289-119">POS permissions</span></span>
- <span data-ttu-id="b3289-120">Report canale</span><span class="sxs-lookup"><span data-stu-id="b3289-120">Channel reports</span></span>
- <span data-ttu-id="b3289-121">Metadati di attributi</span><span class="sxs-lookup"><span data-stu-id="b3289-121">Attribute metadata</span></span>
- <span data-ttu-id="b3289-122">Modelli di convalida entità</span><span class="sxs-lookup"><span data-stu-id="b3289-122">Entity validation templates</span></span>
- <span data-ttu-id="b3289-123">Processo batch per l'eliminazione dello storico della sessione di Commerce Data Exchange</span><span class="sxs-lookup"><span data-stu-id="b3289-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="b3289-124">Inoltre, la registrazione correlata a PCI (Payment Cad Industry) è abilitata per il database di Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3289-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Commerce database.</span></span>

> [!NOTE]
> <span data-ttu-id="b3289-125">È disponibile un'opzione per configurare separatamente l'utilità di pianificazione di commercio.</span><span class="sxs-lookup"><span data-stu-id="b3289-125">There is an option to separately configure the Commerce scheduler.</span></span> <span data-ttu-id="b3289-126">Questa opzione consente di reimpostare la configurazione dell'utilità di pianificazione di commercio con le relative impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="b3289-126">This option lets you reset the Commerce scheduler configuration to its default settings.</span></span>

<span data-ttu-id="b3289-127">Dopo il completamento dell'inizializzazione, è necessario configurare i dati di commercio aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="b3289-127">After initialization is completed, you must configure additional commerce data.</span></span> <span data-ttu-id="b3289-128">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="b3289-128">Here are some examples:</span></span>

- <span data-ttu-id="b3289-129">Parametri di commercio</span><span class="sxs-lookup"><span data-stu-id="b3289-129">Commerce parameters</span></span>
- <span data-ttu-id="b3289-130">Parametri utilità di pianificazione commercio</span><span class="sxs-lookup"><span data-stu-id="b3289-130">Commerce scheduler parameters</span></span>
- <span data-ttu-id="b3289-131">Canali di commercio</span><span class="sxs-lookup"><span data-stu-id="b3289-131">Commerce channels</span></span>
- <span data-ttu-id="b3289-132">Registri e dispositivi</span><span class="sxs-lookup"><span data-stu-id="b3289-132">Registers and devices</span></span>
- <span data-ttu-id="b3289-133">Assortimenti</span><span class="sxs-lookup"><span data-stu-id="b3289-133">Assortments</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]