---
title: Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce
description: Questo argomento fornisce risposte alle domande frequenti sull'ambiente di valutazione Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 637714e28b9f8f4aa66e251e709d8f78bff2739d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413354"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a><span data-ttu-id="f768a-103">Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f768a-103">Dynamics 365 Commerce evaluation environment FAQ</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f768a-104">Questo argomento fornisce risposte alle domande frequenti sull'ambiente di valutazione Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f768a-104">This topic provides answers to frequently asked questions about the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="f768a-105">**Possiamo usare l'ambiente di valutazione Commerce come vetrina di e-commerce per i clienti che attualmente implementano Retail?**</span><span class="sxs-lookup"><span data-stu-id="f768a-105">**Can we use the Commerce evaluation environment as an e-Commerce storefront for customers that currently implement Retail?**</span></span>

<span data-ttu-id="f768a-106">N.</span><span class="sxs-lookup"><span data-stu-id="f768a-106">No.</span></span> <span data-ttu-id="f768a-107">L'ambiente di valutazione Commerce è solo per scopi di valutazione.</span><span class="sxs-lookup"><span data-stu-id="f768a-107">The Commerce evaluation environment is only for evaluation.</span></span> <span data-ttu-id="f768a-108">Se è necessario un ambiente per un cliente che implementa Retail, contattare Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f768a-108">If you require an environment for a customer that implements Retail, contact Microsoft.</span></span>

<span data-ttu-id="f768a-109">**È possibile utilizzare l'ambiente di valutazione Commerce per eseguire il provisioning delle funzionalità di e-commerce su un'applicazione/ambiente esistente che implementa Retail?**</span><span class="sxs-lookup"><span data-stu-id="f768a-109">**Can the Commerce evaluation environment be used to provision the e-Commerce features on top of an existing application/environment that implements Retail?**</span></span>

<span data-ttu-id="f768a-110">No (nella maggior parte dei casi).</span><span class="sxs-lookup"><span data-stu-id="f768a-110">No (mostly).</span></span> <span data-ttu-id="f768a-111">I componenti di valutazione di Commerce sono disponibili solo per gli ambienti che corrispondono alle configurazioni specificate nei prerequisiti e nella guida di provisioning.</span><span class="sxs-lookup"><span data-stu-id="f768a-111">The Commerce evaluation components are available only to environments that match the configurations that are specified in the prerequisites and provisioning guide.</span></span> <span data-ttu-id="f768a-112">Inoltre, i dati demo di base necessari non saranno disponibili negli ambienti distribuiti con una versione iniziale precedente alla versione 10.0.8.</span><span class="sxs-lookup"><span data-stu-id="f768a-112">Additionally, the required base demo data won't be available in environments that were deployed with an initial release that is earlier than 10.0.8.</span></span> 

<span data-ttu-id="f768a-113">**Quali sono i costi associati alla distribuzione dell'ambiente di valutazione Commerce su Microsoft Azure mediante Microsoft Dynamics Lifecycle Services (LCS)?**</span><span class="sxs-lookup"><span data-stu-id="f768a-113">**What costs are involved in deploying the Commerce evaluation environment on Microsoft Azure via Microsoft Dynamics Lifecycle Services (LCS)?**</span></span>

<span data-ttu-id="f768a-114">Un ambiente di dimostrazione di Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce Headquarters (macchina virtuale \[VM\]) sarà ospitato nella sottoscrizione Azure.</span><span class="sxs-lookup"><span data-stu-id="f768a-114">A traditional Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce headquarters demo environment (virtual machine \[VM\]) will be hosted in your Azure subscription.</span></span> <span data-ttu-id="f768a-115">Puoi usare il [Calcolatore prezzi di Azure ](https://azure.microsoft.com/pricing/calculator/) per stimare questo costo.</span><span class="sxs-lookup"><span data-stu-id="f768a-115">You can use the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/) to estimate this cost.</span></span>

<span data-ttu-id="f768a-116">Altri componenti come Commerce Scale Unit, Creazione di siti Web di Commerce e il proprio sito di e-Commerce saranno disponibili come software come un servizio (SaaS) e ospitati da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f768a-116">Other components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site will be available as software as a service (SaaS) and hosted by Microsoft.</span></span>

<span data-ttu-id="f768a-117">**Quali aree geografiche di Azure sono attualmente supportate per l'ambiente di valutazione Commerce?**</span><span class="sxs-lookup"><span data-stu-id="f768a-117">**Which Azure geographies are currently supported for the Commerce evaluation environment?**</span></span>

<span data-ttu-id="f768a-118">L'ambiente di valutazione Commerce può essere distribuito solo nell'area geografica del Nord America.</span><span class="sxs-lookup"><span data-stu-id="f768a-118">The Commerce evaluation environment can be deployed only in the North America geography.</span></span>

<span data-ttu-id="f768a-119">**Esiste un disco rigido virtuale scaricabile (VHD) con l'opzione completa della macchina virtuale (VM) OneBox?**</span><span class="sxs-lookup"><span data-stu-id="f768a-119">**Is there a downloadable virtual hard disk (VHD) that has the complete OneBox virtual machine (VM) option?**</span></span>

<span data-ttu-id="f768a-120">Dynamics 365 Commerce ed Commerce Scale Unit sono totalmente SaaS (software as a service, software come un servizio) e devono essere ospitati sul cloud.</span><span class="sxs-lookup"><span data-stu-id="f768a-120">Dynamics 365 Commerce and Commerce Scale Unit are completely software as a service (SaaS) and must be cloud-hosted.</span></span>

<span data-ttu-id="f768a-121">**Per quanto tempo può essere utilizzato l'ambiente di valutazione Commerce?**</span><span class="sxs-lookup"><span data-stu-id="f768a-121">**How long can the Commerce evaluation environment be used?**</span></span>

<span data-ttu-id="f768a-122">L'ambiente di valutazione Commerce ha un limite di tempo di 30 giorni dalla data in cui viene eseguito il provisioning dei componenti SaaS come Commerce Scale Unit, Creazione di siti Web di Commerce e il proprio sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="f768a-122">The Commerce evaluation environment has a 30-day time limit from the date when SaaS components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site are provisioned.</span></span>

<span data-ttu-id="f768a-123">**Posso estendere il limite di tempo per il mio ambiente di valutazione Commerce?**</span><span class="sxs-lookup"><span data-stu-id="f768a-123">**Can I extend the time limit for my Commerce evaluation environment?**</span></span>

<span data-ttu-id="f768a-124">L'estensione del limite di tempo è un'eccezione alla norma e viene considerata caso per caso.</span><span class="sxs-lookup"><span data-stu-id="f768a-124">Extension of the time limit is an exception to the norm and is considered on a case-by-case basis.</span></span> <span data-ttu-id="f768a-125">Per assistenza, contattare il partner Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f768a-125">You should reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f768a-126">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f768a-126">Additional resources</span></span>

[<span data-ttu-id="f768a-127">Panoramica dell'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f768a-127">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="f768a-128">Provisioning di un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f768a-128">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="f768a-129">Configurare un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f768a-129">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="f768a-130">Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f768a-130">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="f768a-131">Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f768a-131">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)
