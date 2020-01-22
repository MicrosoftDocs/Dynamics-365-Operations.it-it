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
ms.openlocfilehash: c5fb59a9798e2cddfb75b71235ee7754e54b0e28
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945774"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="d5a0f-103">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="d5a0f-103">Enable location-based store detection</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="d5a0f-104">In questo argomento viene descritto come attivare il rilevamento del punto vendita basato sull'ubicazione per il sito Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d5a0f-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="d5a0f-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d5a0f-105">Overview</span></span>

<span data-ttu-id="d5a0f-106">Il rilevamento del punto vendita basato sull'ubicazione in Commerce consente di fornire contenuto del sito ai clienti, in base all'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="d5a0f-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="d5a0f-107">Quando il rilevamento del punto vendita basato sull'ubicazione è attivato il servizio di rendering di Commerce utilizza le informazioni sul paese dell'indirizzo IP del Web browser del cliente per indirizzare il cliente alla migliore configurazione geografica del sito che è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d5a0f-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="d5a0f-108">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="d5a0f-108">Privacy notice</span></span>

<span data-ttu-id="d5a0f-109">Se si attiva la funzionalità di rilevamento del punto vendita basato sull'ubicazione, le informazioni del browser del cliente vengono inviate a un servizio di ubicazione di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5a0f-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="d5a0f-110">Queste informazioni vengono quindi utilizzate per fornire contenuto del cliente relativo alla sua ubicazione.</span><span class="sxs-lookup"><span data-stu-id="d5a0f-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="d5a0f-111">Le informazioni inviate dal browser del cliente e le informazioni basate sull'ubicazione restituite al cliente sono soggette a criteri di conformità relativi a privacy e cookie.</span><span class="sxs-lookup"><span data-stu-id="d5a0f-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="d5a0f-112">Attivare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="d5a0f-112">Turn on location-based store detection</span></span>

<span data-ttu-id="d5a0f-113">Per attivare il rilevamento del punto vendita basato sull'ubicazione in Commerce, procedere come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="d5a0f-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="d5a0f-114">Nello strumento di creazione, accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="d5a0f-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="d5a0f-115">Selezionare **Gestione sito** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="d5a0f-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="d5a0f-116">Selezionare **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="d5a0f-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="d5a0f-117">Impostare l'opzione **Abilita rilevamento del punto vendita basato sull'ubicazione** su **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="d5a0f-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d5a0f-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d5a0f-118">Additional resources</span></span>

[<span data-ttu-id="d5a0f-119">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="d5a0f-119">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="d5a0f-120">Distribuire un nuovo sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="d5a0f-120">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="d5a0f-121">Creare un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="d5a0f-121">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="d5a0f-122">Associare un sito online a un canale</span><span class="sxs-lookup"><span data-stu-id="d5a0f-122">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="d5a0f-123">Gestire i file robots.txt</span><span class="sxs-lookup"><span data-stu-id="d5a0f-123">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="d5a0f-124">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="d5a0f-124">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="d5a0f-125">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="d5a0f-125">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)
