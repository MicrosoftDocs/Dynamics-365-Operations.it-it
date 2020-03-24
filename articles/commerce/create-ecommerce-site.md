---
title: Creare un sito di e-commerce
description: Questo argomento descrive i passaggi e le informazioni richiesti per creare un nuovo sito di e-commerce in Creazione di siti Web di Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 03/02/2020
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
ms.openlocfilehash: 7177bae911dfa91a645b40581bf23b3ed76562a3
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096776"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="3ab5b-103">Creare un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="3ab5b-103">Create an e-Commerce site</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3ab5b-104">Questo argomento descrive i passaggi e le informazioni richiesti per creare un nuovo sito di e-commerce in Creazione di siti Web di Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-104">This topic describes the steps and information required to create a new e-Commerce site in Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="3ab5b-105">Prima di iniziare a sviluppare il sito di e-Commerce, è innanzitutto necessario configurare un nuovo sito in Creazione di siti Web.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-105">Before you can start developing your e-Commerce site, you must first establish a new site in site builder.</span></span> 


<span data-ttu-id="3ab5b-106">Per iniziare a sviluppare il sito di e-Commerce, è innanzitutto necessario configurare un nuovo sito nell'ambiente di creazione di siti.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-106">To start to develop your e-Commerce site, you must first establish a new site in the site authoring environment.</span></span> <span data-ttu-id="3ab5b-107">Prima di poter creare un nuovo sito, almeno un punto vendita online deve essere creato in Commerce.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-107">Before you can create a new site, at least one online store must be created in Commerce.</span></span> 


## <a name="set-up-your-site"></a><span data-ttu-id="3ab5b-108">Configurare il sito</span><span class="sxs-lookup"><span data-stu-id="3ab5b-108">Set up your site</span></span>

<span data-ttu-id="3ab5b-109">Per configurare il sito, effettuare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-109">To set up your site, do the following.</span></span>

1. <span data-ttu-id="3ab5b-110">Aprire l'ambiente di Creazione di siti Web.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-110">Open the site builder environment.</span></span> <span data-ttu-id="3ab5b-111">È possibile trovare un collegamento a Creazione di siti Web in Microsoft Lifecycle Services (LCS) nella pagina Funzionalità ambiente per Commerce.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-111">You can find a link to site builder in Microsoft Lifecycle Services (LCS) in the environment features page for Commerce.</span></span>
1. <span data-ttu-id="3ab5b-112">Nella home page dell'ambiente di creazione di siti, selezionare **Nuovo sito**.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-112">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="3ab5b-113">Nella finestra di dialogo **Nuovo sito** immettere le informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-113">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="3ab5b-114">Campo</span><span class="sxs-lookup"><span data-stu-id="3ab5b-114">Field</span></span>                               | <span data-ttu-id="3ab5b-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ab5b-115">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="3ab5b-116">Nome sito</span><span class="sxs-lookup"><span data-stu-id="3ab5b-116">Site name</span></span>                           | <span data-ttu-id="3ab5b-117">Immettere il nome visualizzato da utilizzare per il sito nell'ambiente di creazione di siti.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-117">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="3ab5b-118">Questo nome è visibile solo nell'ambiente di creazione e non ai clienti.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-118">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="3ab5b-119">Gruppo di sicurezza dell'amministratore del sito</span><span class="sxs-lookup"><span data-stu-id="3ab5b-119">Site administrator's security group</span></span> | <span data-ttu-id="3ab5b-120">Specificare il gruppo di sicurezza di Microsoft Azure Active Directory (Azure AD) che gestisce gli utenti con il ruolo di amministratore sito nel sito.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-120">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="3ab5b-121">Canale predefinito (numero unità operativa)</span><span class="sxs-lookup"><span data-stu-id="3ab5b-121">Default channel (operating unit number)</span></span> | <span data-ttu-id="3ab5b-122">Selezionare il punto vendita online per il quale il sito viene utilizzato come vetrina virtuale Web.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-122">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="3ab5b-123">Se il sito di e-Commerce deve supportare più punti vendita online, è necessario associare i punti vendita al sito in **Impostazioni sito** dopo la configurazione del sito.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-123">If you want your e-Commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="3ab5b-124">Lingua predefinita</span><span class="sxs-lookup"><span data-stu-id="3ab5b-124">Default language</span></span>                            | <span data-ttu-id="3ab5b-125">Specificare la lingua predefinita per il mercato e il punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-125">Specify the default language for this online store and market.</span></span> <span data-ttu-id="3ab5b-126">Un punto vendita online può supportare più lingue.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-126">An online store can support multiple languages.</span></span> <span data-ttu-id="3ab5b-127">Se si desidera supportare più lingue per questo punto vendita online o un altro punto vendita online, è possibile configurare tale supporto in **Impostazioni sito** dopo la configurazione del sito.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-127">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="3ab5b-128">Dominio</span><span class="sxs-lookup"><span data-stu-id="3ab5b-128">Domain</span></span>                              | <span data-ttu-id="3ab5b-129">Selezionare un nome di dominio che sarà utilizzato come dominio per il punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-129">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="3ab5b-130">Se non è stato configurato alcun dominio in LCS, è possibile lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-130">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="3ab5b-131">Dopo che il dominio è configurato in LCS, è necessario aggiungerlo al punto vendita online in **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-131">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="3ab5b-132">Percorso</span><span class="sxs-lookup"><span data-stu-id="3ab5b-132">Path</span></span>                              | <span data-ttu-id="3ab5b-133">Quando il sito supporta più lingue per un nome di dominio specifico, utilizzare il campo del percorso per creare un URL di sito univoco per quella combinazione di dominio e lingua.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-133">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="3ab5b-134">Se la lingua specificata nel campo **Lingua predefinita** è l'unica lingua che verrà supportata per il dominio, o sarà sempre la lingua predefinita dopo aver localizzato il sito in altre lingue, è consigliabile lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-134">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="3ab5b-135">Dopo la creazione del sito, è possibile verificare che sia associato al punto vendita online selezionando la scheda **Prodotti**. Dovrebbe essere visualizzato l'assortimento di prodotti che è stato allocato al punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-135">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="3ab5b-136">È anche possibile utilizzare il menu a discesa nell'angolo in alto a sinistra della pagina per accedere ai prodotti allocati per categoria.</span><span class="sxs-lookup"><span data-stu-id="3ab5b-136">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3ab5b-137">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3ab5b-137">Additional resources</span></span>

[<span data-ttu-id="3ab5b-138">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="3ab5b-138">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="3ab5b-139">Distribuire un nuovo sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="3ab5b-139">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="3ab5b-140">Impostare un canale punto vendita online</span><span class="sxs-lookup"><span data-stu-id="3ab5b-140">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="3ab5b-141">Associare un sito online a un canale</span><span class="sxs-lookup"><span data-stu-id="3ab5b-141">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="3ab5b-142">Gestire i file robots.txt</span><span class="sxs-lookup"><span data-stu-id="3ab5b-142">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="3ab5b-143">Caricare reindirizzamenti di URL in blocco</span><span class="sxs-lookup"><span data-stu-id="3ab5b-143">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="3ab5b-144">Impostare un tenant B2C in Commerce</span><span class="sxs-lookup"><span data-stu-id="3ab5b-144">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="3ab5b-145">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="3ab5b-145">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="3ab5b-146">Configurare più tenant B2C in un ambiente Commerce</span><span class="sxs-lookup"><span data-stu-id="3ab5b-146">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="3ab5b-147">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="3ab5b-147">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="3ab5b-148">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="3ab5b-148">Enable location-based store detection</span></span>](enable-store-detection.md)
