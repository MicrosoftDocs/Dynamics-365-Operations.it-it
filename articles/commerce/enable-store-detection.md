---
title: Abilitare il rilevamento del punto vendita basato sull'ubicazione
description: In questo argomento viene descritto come attivare il rilevamento del punto vendita basato sull'ubicazione per il sito Dynamics 365 Commerce.
author: brianshook
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 71e523cab20281d5db7efff40b5ef4f7293a4765
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799133"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="c7505-103">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="c7505-103">Enable location-based store detection</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c7505-104">In questo argomento viene descritto come attivare il rilevamento del punto vendita basato sull'ubicazione per il sito Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c7505-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

<span data-ttu-id="c7505-105">Il rilevamento del punto vendita basato sull'ubicazione in Commerce consente di fornire contenuto del sito ai clienti, in base all'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="c7505-105">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="c7505-106">Quando il rilevamento del punto vendita basato sull'ubicazione è attivato il servizio di rendering di Commerce utilizza le informazioni sul paese dell'indirizzo IP del Web browser del cliente per indirizzare il cliente alla migliore configurazione geografica del sito che è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c7505-106">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="c7505-107">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="c7505-107">Privacy notice</span></span>

<span data-ttu-id="c7505-108">Se si attiva la funzionalità di rilevamento del punto vendita basato sull'ubicazione, le informazioni del browser del cliente vengono inviate a un servizio di ubicazione di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7505-108">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="c7505-109">Queste informazioni vengono quindi utilizzate per fornire contenuto del cliente relativo alla sua ubicazione.</span><span class="sxs-lookup"><span data-stu-id="c7505-109">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="c7505-110">Le informazioni inviate dal browser del cliente e le informazioni basate sull'ubicazione restituite al cliente sono soggette a criteri di conformità relativi a privacy e cookie.</span><span class="sxs-lookup"><span data-stu-id="c7505-110">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="c7505-111">Attivare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="c7505-111">Turn on location-based store detection</span></span>

<span data-ttu-id="c7505-112">Per attivare il rilevamento del punto vendita basato sull'ubicazione in Commerce, procedere come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="c7505-112">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="c7505-113">Nello strumento di creazione, accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="c7505-113">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="c7505-114">Selezionare **Gestione sito** nel pannello di navigazione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="c7505-114">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="c7505-115">Selezionare **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="c7505-115">Select **Site Settings**.</span></span>
1. <span data-ttu-id="c7505-116">Impostare l'opzione **Abilita rilevamento del punto vendita basato sull'ubicazione** su **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="c7505-116">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c7505-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c7505-117">Additional resources</span></span>

[<span data-ttu-id="c7505-118">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="c7505-118">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="c7505-119">Distribuire un nuovo tenant di e-commerce</span><span class="sxs-lookup"><span data-stu-id="c7505-119">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="c7505-120">Creare un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="c7505-120">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="c7505-121">Associare un sito Dynamics 365 Commerce a un canale online</span><span class="sxs-lookup"><span data-stu-id="c7505-121">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="c7505-122">Gestire i file robots.txt</span><span class="sxs-lookup"><span data-stu-id="c7505-122">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="c7505-123">Caricare reindirizzamenti URL in blocco</span><span class="sxs-lookup"><span data-stu-id="c7505-123">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="c7505-124">Impostare un tenant B2C in Commerce</span><span class="sxs-lookup"><span data-stu-id="c7505-124">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="c7505-125">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="c7505-125">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="c7505-126">Configurare più tenant B2C in un ambiente Commerce</span><span class="sxs-lookup"><span data-stu-id="c7505-126">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="c7505-127">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="c7505-127">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
