---
title: Configurare il proprio nome di dominio
description: In questo argomento viene illustrato come configurare un nome di dominio per un sito di e-Commerce di Microsoft Dynamics 365.
author: psimolin
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4db774783dba4b1cea9552da3cff29a9528bd496
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002176"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="4b358-103">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="4b358-103">Configure your domain name</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="4b358-104">In questo argomento viene illustrato come configurare un nome di dominio per un sito di e-Commerce di Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="4b358-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="4b358-105">Aggiungere domini durante l'inizializzazione di e-Commerce</span><span class="sxs-lookup"><span data-stu-id="4b358-105">Add domains during e-Commerce initialization</span></span>

<span data-ttu-id="4b358-106">Per associare domini all'ambiente di e-Commerce, inizializzare e-Commerce come descritto in [Distribuire un nuovo sito di e-Commerce](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="4b358-106">To associate domains with your e-commerce environment, initialize e-Commerce as described in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="4b358-107">Durante l'inizializzazione, viene richiesto di immettere informazioni che verranno utilizzate per eseguire il provisioning dell'ambiente di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="4b358-107">During initialization, you're asked to provide information that will be used to provision your e-Commerce environment.</span></span> <span data-ttu-id="4b358-108">Nel campo **Nomi host supportati**, aggiungere tutti i domini che si prevede di utilizzare con questo ambiente.</span><span class="sxs-lookup"><span data-stu-id="4b358-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="4b358-109">I domini devono essere separati con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="4b358-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="4b358-110">In questo modo, i domini vengono configurati in tutti i componenti di e-Commerce necessari e sono pronti per essere utilizzati quando si passa il traffico dalla rete per la distribuzione di contenuti (CDN) o dal server Web ai front-end di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="4b358-110">In this way, the domains are configured in all the required e-Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-Commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="4b358-111">Aggiungere domini dopo l'inizializzazione di e-Commerce</span><span class="sxs-lookup"><span data-stu-id="4b358-111">Add domains after e-Commerce initialization</span></span>

<span data-ttu-id="4b358-112">Per associare nuovi domini all'ambiente di e-Commerce dopo l'inizializzazione di e-Commerce, è necessario inviare una richiesta di assistenza.</span><span class="sxs-lookup"><span data-stu-id="4b358-112">To associate new domains with your e-Commerce environment after e-Commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4b358-113">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4b358-113">Additional resources</span></span>

[<span data-ttu-id="4b358-114">Distribuire un nuovo sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="4b358-114">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="4b358-115">Creare un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="4b358-115">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="4b358-116">Associare un sito online a un canale</span><span class="sxs-lookup"><span data-stu-id="4b358-116">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="4b358-117">Gestire i file robots.txt</span><span class="sxs-lookup"><span data-stu-id="4b358-117">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="4b358-118">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="4b358-118">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="4b358-119">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="4b358-119">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="4b358-120">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="4b358-120">Enable location-based store detection</span></span>](enable-store-detection.md)
