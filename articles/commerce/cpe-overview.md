---
title: Panoramica dell'ambiente di valutazione Dynamics 365 Commerce
description: In questo argomento viene fornita una panoramica dell'ambiente di valutazione Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 25c0574e8d4502bcb846fba0ddf913d81eded87b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413350"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a><span data-ttu-id="a614f-103">Panoramica dell'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a614f-103">Dynamics 365 Commerce evaluation environment overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a614f-104">In questo argomento viene fornita una panoramica dell'ambiente di valutazione Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a614f-104">This topic gives an overview of the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

> [!NOTE]
> <span data-ttu-id="a614f-105">Gli ambienti di valutazione di Commerce non sono generalmente disponibili e sono concessi a partner e clienti in base alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="a614f-105">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="a614f-106">Per ulteriori informazioni, contattare il partner Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a614f-106">For more information, reach out to your Microsoft partner contact.</span></span>

## <a name="overview"></a><span data-ttu-id="a614f-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a614f-107">Overview</span></span>

<span data-ttu-id="a614f-108">L'ambiente di valutazione Commerce è un ambiente di anteprima completo facoltativo di Dynamics 365 Commerce che consente ai partner e ai potenziali clienti di provare il prodotto Commerce.</span><span class="sxs-lookup"><span data-stu-id="a614f-108">The Commerce evaluation environment is an optional end-to-end environment of Dynamics 365 Commerce that lets partners and potential customers try out the Commerce product.</span></span>

<span data-ttu-id="a614f-109">Gli ambienti di valutazione sono parzialmente preconfigurati per ridurre le fasi di post-provisioning necessarie.</span><span class="sxs-lookup"><span data-stu-id="a614f-109">Evaluation environments are partially preconfigured to reduce the required post-provisioning steps.</span></span>

<span data-ttu-id="a614f-110">A parte alcune limitazioni minori che non influiscono su caratteristiche o funzionalità, l'ambiente di valutazione Commerce offre l'esperienza Commerce completa e può essere utilizzato da clienti e partner di implementazione per valutare il prodotto, fornire feedback e fare analisi di corrispondenza/scarto.</span><span class="sxs-lookup"><span data-stu-id="a614f-110">Aside from some minor limitations that don't affect features or functionality, the Commerce evaluation environment provides the complete Commerce experience, and can be used by customers and implementation partners to evaluate the product, provide feedback, and do fit/gap analysis.</span></span>

## <a name="limitations-of-the-commerce-evaluation-environment"></a><span data-ttu-id="a614f-111">Limiti dell'ambiente di valutazione Commerce</span><span class="sxs-lookup"><span data-stu-id="a614f-111">Limitations of the Commerce evaluation environment</span></span>

<span data-ttu-id="a614f-112">Sebbene l'ambiente di valutazione Commerce fornisca il set completo di caratteristiche e funzionalità di Commerce, ci sono alcune limitazioni minori:</span><span class="sxs-lookup"><span data-stu-id="a614f-112">Although the Commerce evaluation environment provides the full set of Commerce features and functionality, there are some minor limitations:</span></span>

- <span data-ttu-id="a614f-113">Sebbene lo stesso ambiente di valutazione Commerce non abbia limiti geografici, il provisioning di componenti dell'ambiente, come Retail Cloud Scale Unit (RCSU) e le applicazioni di e-commerce, deve essere eseguito solo negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="a614f-113">Although the Commerce evaluation environment itself has no geographical limitations, components of the environment, such as the Retail Cloud Scale Unit (RCSU) and e-Commerce applications, should be provisioned only in the United States.</span></span>
- <span data-ttu-id="a614f-114">L'utilizzo dell'ambiente di valutazione Commerce ha un limite di 30 giorni dalla data dell'effettuazione del provisioning di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="a614f-114">Use of the Commerce evaluation environment is limited to 30 days from the date when e-Commerce is provisioned.</span></span>
- <span data-ttu-id="a614f-115">L'ambiente di valutazione Commerce può essere distribuito e inizializzato correttamente solo in un ambiente che utilizza la topologia dimostrativa, in cui tutti i componenti di un ambiente sono distribuiti su una singola macchina virtuale (VM) ospitata sul cloud</span><span class="sxs-lookup"><span data-stu-id="a614f-115">The Commerce evaluation environment can be successfully deployed and initialized only in an environment that uses the demo topology, where all components of an environment are deployed on a single cloud-hosted virtual machine (VM).</span></span> <span data-ttu-id="a614f-116">Il limite principale di questa topologia è il numero di utenti simultanei che può supportare l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a614f-116">The main limitation of this topology is the number of concurrent users that the environment can support.</span></span>

## <a name="get-started"></a><span data-ttu-id="a614f-117">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="a614f-117">Get started</span></span>

<span data-ttu-id="a614f-118">Per effettuare il provisioning dell'ambiente di valutazione Commerce, consultare [Provisioning di un ambiente di valutazione Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="a614f-118">To provision the Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a614f-119">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a614f-119">Additional resources</span></span>

[<span data-ttu-id="a614f-120">Provisioning di un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a614f-120">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="a614f-121">Configurare un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a614f-121">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="a614f-122">Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a614f-122">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="a614f-123">Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a614f-123">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="a614f-124">Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a614f-124">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)
