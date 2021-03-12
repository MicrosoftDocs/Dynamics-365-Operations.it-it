---
title: Configurare il proprio nome di dominio
description: In questo argomento viene illustrato come configurare un nome di dominio per un sito di e-Commerce di Microsoft Dynamics 365.
author: psimolin
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d3df563b62b40970509340802a09bb36dda14777
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001002"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="e5753-103">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="e5753-103">Configure your domain name</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e5753-104">In questo argomento viene illustrato come configurare un nome di dominio per un sito di e-Commerce di Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e5753-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="e5753-105">Aggiungere domini durante l'inizializzazione di e-commerce</span><span class="sxs-lookup"><span data-stu-id="e5753-105">Add domains during e-commerce initialization</span></span>

<span data-ttu-id="e5753-106">Per associare domini all'ambiente di e-commerce Dynamics 365 Commerce, inizializzare e-commerce come descritto in [Distribuire un nuovo tenant di e-commerce](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="e5753-106">To associate domains with your Dynamics 365 Commerce e-commerce environment, initialize e-commerce as described in [Deploy a new e-commerce tenant](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="e5753-107">Durante l'inizializzazione, viene richiesto di immettere informazioni che verranno utilizzate per eseguire il provisioning dell'ambiente di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="e5753-107">During initialization, you're asked to provide information that will be used to provision your e-commerce environment.</span></span> <span data-ttu-id="e5753-108">Nel campo **Nomi host supportati**, aggiungere tutti i domini che si prevede di utilizzare con questo ambiente.</span><span class="sxs-lookup"><span data-stu-id="e5753-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="e5753-109">I domini devono essere separati con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="e5753-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="e5753-110">In questo modo, i domini vengono configurati in tutti i componenti di Commerce necessari e sono pronti per essere utilizzati quando si passa il traffico dalla rete per la distribuzione di contenuti (CDN) o dal server Web ai front-end di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="e5753-110">In this way, the domains are configured in all the required Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="e5753-111">Aggiungere domini dopo l'inizializzazione di e-commerce</span><span class="sxs-lookup"><span data-stu-id="e5753-111">Add domains after e-commerce initialization</span></span>

<span data-ttu-id="e5753-112">Per associare nuovi domini all'ambiente di e-commerce dopo l'inizializzazione di e-commerce, è necessario inviare una richiesta di assistenza.</span><span class="sxs-lookup"><span data-stu-id="e5753-112">To associate new domains with your e-commerce environment after e-commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e5753-113">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e5753-113">Additional resources</span></span>

[<span data-ttu-id="e5753-114">Distribuire un nuovo tenant di e-commerce</span><span class="sxs-lookup"><span data-stu-id="e5753-114">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="e5753-115">Creare un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="e5753-115">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="e5753-116">Associare un sito Dynamics 365 Commerce a un canale online</span><span class="sxs-lookup"><span data-stu-id="e5753-116">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="e5753-117">Gestire i file robots.txt</span><span class="sxs-lookup"><span data-stu-id="e5753-117">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="e5753-118">Caricare reindirizzamenti URL in blocco</span><span class="sxs-lookup"><span data-stu-id="e5753-118">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="e5753-119">Impostare un tenant B2C in Commerce</span><span class="sxs-lookup"><span data-stu-id="e5753-119">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="e5753-120">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="e5753-120">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="e5753-121">Configurare più tenant B2C in un ambiente Commerce</span><span class="sxs-lookup"><span data-stu-id="e5753-121">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="e5753-122">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="e5753-122">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="e5753-123">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="e5753-123">Enable location-based store detection</span></span>](enable-store-detection.md)
