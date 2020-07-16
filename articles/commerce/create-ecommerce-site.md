---
title: Creare un sito di e-commerce
description: Questo argomento descrive i passaggi e le informazioni richiesti per creare un nuovo sito di e-commerce in Creazione di siti Web di Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 07/02/2020
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
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ea3517a4f2b84db8a87a97d2f644bb4436f8693f
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533438"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="63eb1-103">Creare un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="63eb1-103">Create an e-Commerce site</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="63eb1-104">Questo argomento descrive i passaggi e le informazioni richiesti per creare un nuovo sito di e-commerce in Creazione di siti Web di Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="63eb1-104">This topic describes the steps and information required to create a new e-Commerce site in Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="63eb1-105">Quando si concedono in licenza le funzionalità di e-commerce, all'autore del sito verrà fornito un sito di partenza che è possibile utilizzare come base per il proprio sito.</span><span class="sxs-lookup"><span data-stu-id="63eb1-105">When you license the e-Commerce capabilities, site builder will be provisioned with a starter site that you can use as a basis for your own site.</span></span> <span data-ttu-id="63eb1-106">Tuttavia, se si desidera iniziare da zero o se si desidera creare un secondo sito, sarà necessario stabilire un nuovo sito nell'ambiente di creazione del sito.</span><span class="sxs-lookup"><span data-stu-id="63eb1-106">However, if you want to start from scratch or if you want to establish a second site, you will need to establish a new site in the site authoring environment.</span></span> 

## <a name="set-up-your-site"></a><span data-ttu-id="63eb1-107">Configurare il sito</span><span class="sxs-lookup"><span data-stu-id="63eb1-107">Set up your site</span></span>

<span data-ttu-id="63eb1-108">Per configurare il sito, effettuare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="63eb1-108">To set up your site, do the following.</span></span>

1. <span data-ttu-id="63eb1-109">Aprire l'ambiente di Creazione di siti Web.</span><span class="sxs-lookup"><span data-stu-id="63eb1-109">Open the site builder environment.</span></span> <span data-ttu-id="63eb1-110">È possibile trovare un collegamento a Creazione di siti Web in Microsoft Lifecycle Services (LCS) nella pagina Funzionalità ambiente per Commerce.</span><span class="sxs-lookup"><span data-stu-id="63eb1-110">You can find a link to site builder in Microsoft Lifecycle Services (LCS) in the environment features page for Commerce.</span></span>
1. <span data-ttu-id="63eb1-111">Nella home page dell'ambiente di creazione di siti, selezionare **Nuovo sito**.</span><span class="sxs-lookup"><span data-stu-id="63eb1-111">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="63eb1-112">Nella finestra di dialogo **Nuovo sito** immettere le informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="63eb1-112">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="63eb1-113">Campo</span><span class="sxs-lookup"><span data-stu-id="63eb1-113">Field</span></span>                               | <span data-ttu-id="63eb1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63eb1-114">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="63eb1-115">Nome sito</span><span class="sxs-lookup"><span data-stu-id="63eb1-115">Site name</span></span>                           | <span data-ttu-id="63eb1-116">Immettere il nome visualizzato da utilizzare per il sito nell'ambiente di creazione di siti.</span><span class="sxs-lookup"><span data-stu-id="63eb1-116">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="63eb1-117">Questo nome è visibile solo nell'ambiente di creazione e non ai clienti.</span><span class="sxs-lookup"><span data-stu-id="63eb1-117">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="63eb1-118">Gruppo di sicurezza dell'amministratore del sito</span><span class="sxs-lookup"><span data-stu-id="63eb1-118">Site administrator's security group</span></span> | <span data-ttu-id="63eb1-119">Specificare il gruppo di sicurezza di Microsoft Azure Active Directory (Azure AD) che gestisce gli utenti con il ruolo di amministratore sito nel sito.</span><span class="sxs-lookup"><span data-stu-id="63eb1-119">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="63eb1-120">Canale predefinito (numero unità operativa)</span><span class="sxs-lookup"><span data-stu-id="63eb1-120">Default channel (operating unit number)</span></span> | <span data-ttu-id="63eb1-121">Selezionare il punto vendita online per il quale il sito viene utilizzato come vetrina virtuale Web.</span><span class="sxs-lookup"><span data-stu-id="63eb1-121">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="63eb1-122">Se il sito di e-Commerce deve supportare più punti vendita online, è necessario associare i punti vendita al sito in **Impostazioni sito** dopo la configurazione del sito.</span><span class="sxs-lookup"><span data-stu-id="63eb1-122">If you want your e-Commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="63eb1-123">Lingua predefinita</span><span class="sxs-lookup"><span data-stu-id="63eb1-123">Default language</span></span>                            | <span data-ttu-id="63eb1-124">Specificare la lingua predefinita per il mercato e il punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="63eb1-124">Specify the default language for this online store and market.</span></span> <span data-ttu-id="63eb1-125">Un punto vendita online può supportare più lingue.</span><span class="sxs-lookup"><span data-stu-id="63eb1-125">An online store can support multiple languages.</span></span> <span data-ttu-id="63eb1-126">Se si desidera supportare più lingue per questo punto vendita online o un altro punto vendita online, è possibile configurare tale supporto in **Impostazioni sito** dopo la configurazione del sito.</span><span class="sxs-lookup"><span data-stu-id="63eb1-126">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="63eb1-127">Dominio</span><span class="sxs-lookup"><span data-stu-id="63eb1-127">Domain</span></span>                              | <span data-ttu-id="63eb1-128">Selezionare un nome di dominio che sarà utilizzato come dominio per il punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="63eb1-128">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="63eb1-129">Se non è stato configurato alcun dominio in LCS, è possibile lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="63eb1-129">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="63eb1-130">Dopo che il dominio è configurato in LCS, è necessario aggiungerlo al punto vendita online in **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="63eb1-130">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="63eb1-131">Percorso</span><span class="sxs-lookup"><span data-stu-id="63eb1-131">Path</span></span>                              | <span data-ttu-id="63eb1-132">Quando il sito supporta più lingue per un nome di dominio specifico, utilizzare il campo del percorso per creare un URL di sito univoco per quella combinazione di dominio e lingua.</span><span class="sxs-lookup"><span data-stu-id="63eb1-132">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="63eb1-133">Se la lingua specificata nel campo **Lingua predefinita** è l'unica lingua che verrà supportata per il dominio, o sarà sempre la lingua predefinita dopo aver localizzato il sito in altre lingue, è consigliabile lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="63eb1-133">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="63eb1-134">Dopo la creazione del sito, è possibile verificare che sia associato al punto vendita online selezionando la scheda **Prodotti**. Dovrebbe essere visualizzato l'assortimento di prodotti che è stato allocato al punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="63eb1-134">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="63eb1-135">È anche possibile utilizzare il menu a discesa nell'angolo in alto a sinistra della pagina per accedere ai prodotti allocati per categoria.</span><span class="sxs-lookup"><span data-stu-id="63eb1-135">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="63eb1-136">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="63eb1-136">Additional resources</span></span>

[<span data-ttu-id="63eb1-137">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="63eb1-137">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="63eb1-138">Distribuire un nuovo sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="63eb1-138">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="63eb1-139">Associare un sito online a un canale</span><span class="sxs-lookup"><span data-stu-id="63eb1-139">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="63eb1-140">Gestire i file robots.txt</span><span class="sxs-lookup"><span data-stu-id="63eb1-140">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="63eb1-141">Caricare reindirizzamenti di URL in blocco</span><span class="sxs-lookup"><span data-stu-id="63eb1-141">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="63eb1-142">Impostare un tenant B2C in Commerce</span><span class="sxs-lookup"><span data-stu-id="63eb1-142">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="63eb1-143">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="63eb1-143">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="63eb1-144">Configurare più tenant B2C in un ambiente Commerce</span><span class="sxs-lookup"><span data-stu-id="63eb1-144">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="63eb1-145">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="63eb1-145">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="63eb1-146">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="63eb1-146">Enable location-based store detection</span></span>](enable-store-detection.md)
