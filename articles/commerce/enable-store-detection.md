---
title: Abilitare il rilevamento del punto vendita basato sull'ubicazione
description: In questo argomento viene descritto come attivare il rilevamento del punto vendita basato sull'ubicazione per il sito Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 10/01/2019
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
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a542d6987280451910b4ff3bcfb3a109a0e028c6
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697614"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="95119-103">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="95119-103">Enable location-based store detection</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="95119-104">In questo argomento viene descritto come attivare il rilevamento del punto vendita basato sull'ubicazione per il sito Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="95119-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="95119-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="95119-105">Overview</span></span>

<span data-ttu-id="95119-106">Il rilevamento del punto vendita basato sull'ubicazione in Commerce consente di fornire contenuto del sito ai clienti, in base all'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="95119-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="95119-107">Quando il rilevamento del punto vendita basato sull'ubicazione è attivato il servizio di rendering di Commerce utilizza le informazioni sul paese dell'indirizzo IP del Web browser del cliente per indirizzare il cliente alla migliore configurazione geografica del sito che è disponibile.</span><span class="sxs-lookup"><span data-stu-id="95119-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="95119-108">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="95119-108">Privacy notice</span></span>

<span data-ttu-id="95119-109">Se si attiva la funzionalità di rilevamento del punto vendita basato sull'ubicazione, le informazioni del browser del cliente vengono inviate a un servizio di ubicazione di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="95119-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="95119-110">Queste informazioni vengono quindi utilizzate per fornire contenuto del cliente relativo alla sua ubicazione.</span><span class="sxs-lookup"><span data-stu-id="95119-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="95119-111">Le informazioni inviate dal browser del cliente e le informazioni basate sull'ubicazione restituite al cliente sono soggette a criteri di conformità relativi a privacy e cookie.</span><span class="sxs-lookup"><span data-stu-id="95119-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="95119-112">Attivare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="95119-112">Turn on location-based store detection</span></span>

<span data-ttu-id="95119-113">Per attivare il rilevamento del punto vendita basato sull'ubicazione in Commerce, procedere come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="95119-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="95119-114">Nello strumento di creazione, accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="95119-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="95119-115">Selezionare **Gestione sito** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="95119-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="95119-116">Selezionare **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="95119-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="95119-117">Impostare l'opzione **Abilita rilevamento del punto vendita basato sull'ubicazione** su **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="95119-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="95119-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="95119-118">Additional resources</span></span>

[<span data-ttu-id="95119-119">Panoramica dei negozi online</span><span class="sxs-lookup"><span data-stu-id="95119-119">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="95119-120">Creare un sito di e-Commerce</span><span class="sxs-lookup"><span data-stu-id="95119-120">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="95119-121">Distribuire un nuovo sito di e-Commerce</span><span class="sxs-lookup"><span data-stu-id="95119-121">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="95119-122">Associare un sito online a un canale</span><span class="sxs-lookup"><span data-stu-id="95119-122">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="95119-123">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="95119-123">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="95119-124">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="95119-124">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="95119-125">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="95119-125">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)
