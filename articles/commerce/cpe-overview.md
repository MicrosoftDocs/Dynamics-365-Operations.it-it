---
title: Panoramica dell'ambiente di anteprima Commerce
description: In questo argomento viene fornita una panoramica dell'ambiente di anteprima Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/10/2019
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
ms.openlocfilehash: 901583afde4739be5313fa129ff0e52f11326881
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906072"
---
# <a name="commerce-preview-environment-overview"></a><span data-ttu-id="60510-103">Panoramica dell'ambiente di anteprima Commerce</span><span class="sxs-lookup"><span data-stu-id="60510-103">Commerce preview environment overview</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="60510-104">In questo argomento viene fornita una panoramica dell'ambiente di anteprima Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="60510-104">This topic gives an overview of the Microsoft Dynamics 365 Commerce preview environment.</span></span>

## <a name="overview"></a><span data-ttu-id="60510-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="60510-105">Overview</span></span>

<span data-ttu-id="60510-106">L'ambiente di anteprima di Commerce è un ambiente di anteprima completo facoltativo di Dynamics 365 Commerce che consente ai potenziali clienti di provare il prodotto Commerce prima del rilascio generale al pubblico.</span><span class="sxs-lookup"><span data-stu-id="60510-106">The Commerce preview environment is an optional end-to-end preview environment of Dynamics 365 Commerce that lets potential customers try out the Commerce product before its general release to the public.</span></span>

<span data-ttu-id="60510-107">A parte alcune limitazioni minori che non influiscono su caratteristiche o funzionalità, l'ambiente di anteprima Commerce offre l'esperienza Commerce completa e può essere utilizzato da clienti e partner di implementazione per valutare il prodotto, fornire feedback e fare analisi di corrispondenza/scarto.</span><span class="sxs-lookup"><span data-stu-id="60510-107">Aside from some minor limitations that don't affect features or functionality, the Commerce preview environment provides the complete Commerce experience, and can be used by customers and implementation partners to evaluate the product, provide feedback, and do fit/gap analysis.</span></span>

## <a name="limitations-of-the-commerce-preview-environment"></a><span data-ttu-id="60510-108">Limiti dell'ambiente di anteprima di Commerce</span><span class="sxs-lookup"><span data-stu-id="60510-108">Limitations of the Commerce preview environment</span></span>

<span data-ttu-id="60510-109">Sebbene l'ambiente di anteprima di Commerce fornisca il set completo di caratteristiche e funzionalità di Commerce, ci sono alcune limitazioni minori:</span><span class="sxs-lookup"><span data-stu-id="60510-109">Although the Commerce preview environment provides the full set of Commerce features and functionality, there are some minor limitations:</span></span>

- <span data-ttu-id="60510-110">Sebbene lo stesso ambiente di anteprima di Commerce non abbia limiti geografici, il provisioning di componenti dell'ambiente, come Retail Cloud Scale Unit (RCSU) e le applicazioni di e-commerce, può essere eseguito solo negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="60510-110">Although the Commerce preview environment itself has no geographical limitations, components of the environment, such as the Retail Cloud Scale Unit (RCSU) and e-Commerce applications, can be provisioned only in the United States.</span></span>
- <span data-ttu-id="60510-111">L'utilizzo dell'ambiente di anteprima di Commerce ha un limite di 30 giorni dalla data dell'effettuazione del provisioning di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="60510-111">Use of the Commerce preview environment is limited to 30 days from the date when e-Commerce is provisioned.</span></span>
- <span data-ttu-id="60510-112">L'ambiente di anteprima di Commerce può essere distribuito e inizializzato correttamente solo in un ambiente che utilizza la topologia dimostrativa, in cui tutti i componenti di un ambiente sono distribuiti in una singola macchina virtuale (VM).</span><span class="sxs-lookup"><span data-stu-id="60510-112">The Commerce preview environment can be successfully deployed and initialized only in an environment that uses the demo topology, where all components of an environment are deployed in a single virtual machine (VM).</span></span> <span data-ttu-id="60510-113">Il limite principale di questa topologia della macchina virtuale (VM) OneBox è il numero di utenti simultanei che può supportare l'ambiente di anteprima.</span><span class="sxs-lookup"><span data-stu-id="60510-113">The main limitation of this OneBox VM topology is the number of concurrent users that the preview environment can support.</span></span>
- <span data-ttu-id="60510-114">L'ambiente di anteprima di Commerce può essere valutato solo fino alla disponibilità generale (GA) del prodotto Commerce.</span><span class="sxs-lookup"><span data-stu-id="60510-114">The Commerce preview environment can be evaluated only until the general availability (GA) of the Commerce product.</span></span> <span data-ttu-id="60510-115">I nuovi ambienti dimostrativi saranno disponibili dopo la versione GA.</span><span class="sxs-lookup"><span data-stu-id="60510-115">New demo environments will be available after GA.</span></span>

## <a name="get-started"></a><span data-ttu-id="60510-116">Inizia subito</span><span class="sxs-lookup"><span data-stu-id="60510-116">Get started</span></span>

<span data-ttu-id="60510-117">Per effettuare il provisioning dell'ambiente di anteprima di Commerce, consultare [Provisioning di un ambiente di anteprima Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="60510-117">To provision the Commerce preview environment, see [Provision a Commerce preview environment](provisioning-guide.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="60510-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="60510-118">Additional resources</span></span>

[<span data-ttu-id="60510-119">Provisioning di un ambiente di anteprima Commerce</span><span class="sxs-lookup"><span data-stu-id="60510-119">Provision a Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="60510-120">Configurare un ambiente di anteprima Commerce</span><span class="sxs-lookup"><span data-stu-id="60510-120">Configure a Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="60510-121">Configurare le funzioni facoltative per un ambiente di anteprima Commerce</span><span class="sxs-lookup"><span data-stu-id="60510-121">Configure optional features for a Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="60510-122">Domande frequenti sull'ambiente di anteprima Commerce</span><span class="sxs-lookup"><span data-stu-id="60510-122">Commerce preview environment FAQ</span></span>](cpe-faq.md)
