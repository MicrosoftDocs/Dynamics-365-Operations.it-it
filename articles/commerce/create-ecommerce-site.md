---
title: Creare un sito di e-Commerce
description: In questo argomento vengono descritte le attività associate alla creazione di un nuovo sito di e-Commerce in Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 10/31/2019
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
ms.openlocfilehash: 54259d3f5dfd8c8e1ff2caaadfac497cc0e133e0
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945837"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="1061d-103">Creare un sito di e-Commerce</span><span class="sxs-lookup"><span data-stu-id="1061d-103">Create an e-Commerce site</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="1061d-104">In questo argomento vengono descritte le attività associate alla creazione di un nuovo sito di e-Commerce in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1061d-104">This topic describes the tasks that are associated with the creation of a new e-Commerce site in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1061d-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="1061d-105">Overview</span></span>

<span data-ttu-id="1061d-106">Per iniziare a sviluppare il sito di e-Commerce, è innanzitutto necessario configurare un nuovo sito nell'ambiente di creazione di siti.</span><span class="sxs-lookup"><span data-stu-id="1061d-106">To start to develop your e-Commerce site, you must first establish a new site in the site authoring environment.</span></span> <span data-ttu-id="1061d-107">Prima di poter creare un nuovo sito, almeno un punto vendita online deve essere creato in Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="1061d-107">Before you can create a new site, at least one online store must be created in Dynamics 365 Retail.</span></span> 

## <a name="set-up-your-site"></a><span data-ttu-id="1061d-108">Configurare il sito</span><span class="sxs-lookup"><span data-stu-id="1061d-108">Set up your site</span></span>

<span data-ttu-id="1061d-109">Per configurare il sito, effettuare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="1061d-109">To set up your site, do the following.</span></span>

1. <span data-ttu-id="1061d-110">In Microsoft Lifecycle Services (LCS), selezionare il collegamento per l'ambiente di creazione di siti.</span><span class="sxs-lookup"><span data-stu-id="1061d-110">In Microsoft Lifecycle Services (LCS), select the link for the site authoring environment.</span></span> 
1. <span data-ttu-id="1061d-111">Nella home page dell'ambiente di creazione di siti, selezionare **Nuovo sito**.</span><span class="sxs-lookup"><span data-stu-id="1061d-111">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="1061d-112">Nella finestra di dialogo **Nuovo sito** immettere le informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1061d-112">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="1061d-113">Campo</span><span class="sxs-lookup"><span data-stu-id="1061d-113">Field</span></span>                               | <span data-ttu-id="1061d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1061d-114">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="1061d-115">Nome sito</span><span class="sxs-lookup"><span data-stu-id="1061d-115">Site name</span></span>                           | <span data-ttu-id="1061d-116">Immettere il nome visualizzato da utilizzare per il sito nell'ambiente di creazione di siti.</span><span class="sxs-lookup"><span data-stu-id="1061d-116">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="1061d-117">Questo nome è visibile solo nell'ambiente di creazione e non ai clienti.</span><span class="sxs-lookup"><span data-stu-id="1061d-117">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="1061d-118">Gruppo di sicurezza dell'amministratore del sito</span><span class="sxs-lookup"><span data-stu-id="1061d-118">Site administrator's security group</span></span> | <span data-ttu-id="1061d-119">Specificare il gruppo di sicurezza di Microsoft Azure Active Directory (Azure AD) che gestisce gli utenti con il ruolo di amministratore sito nel sito.</span><span class="sxs-lookup"><span data-stu-id="1061d-119">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="1061d-120">Canale predefinito (numero unità operativa)</span><span class="sxs-lookup"><span data-stu-id="1061d-120">Default channel (operating unit number)</span></span> | <span data-ttu-id="1061d-121">Selezionare il punto vendita online per il quale il sito viene utilizzato come vetrina virtuale Web.</span><span class="sxs-lookup"><span data-stu-id="1061d-121">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="1061d-122">Se il sito di e-Commerce deve supportare più punti vendita online, è necessario associare i punti vendita al sito in **Impostazioni sito** dopo la configurazione del sito.</span><span class="sxs-lookup"><span data-stu-id="1061d-122">If you want your e-Commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="1061d-123">Lingua predefinita</span><span class="sxs-lookup"><span data-stu-id="1061d-123">Default language</span></span>                            | <span data-ttu-id="1061d-124">Specificare la lingua predefinita per il mercato e il punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="1061d-124">Specify the default language for this online store and market.</span></span> <span data-ttu-id="1061d-125">Un punto vendita online può supportare più lingue.</span><span class="sxs-lookup"><span data-stu-id="1061d-125">An online store can support multiple languages.</span></span> <span data-ttu-id="1061d-126">Se si desidera supportare più lingue per questo punto vendita online o un altro punto vendita online, è possibile configurare tale supporto in **Impostazioni sito** dopo la configurazione del sito.</span><span class="sxs-lookup"><span data-stu-id="1061d-126">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="1061d-127">Dominio</span><span class="sxs-lookup"><span data-stu-id="1061d-127">Domain</span></span>                              | <span data-ttu-id="1061d-128">Selezionare un nome di dominio che sarà utilizzato come dominio per il punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="1061d-128">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="1061d-129">Se non è stato configurato alcun dominio in LCS, è possibile lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="1061d-129">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="1061d-130">Dopo che il dominio è configurato in LCS, è necessario aggiungerlo al punto vendita online in **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="1061d-130">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="1061d-131">Percorso</span><span class="sxs-lookup"><span data-stu-id="1061d-131">Path</span></span>                              | <span data-ttu-id="1061d-132">Quando il sito supporta più lingue per un nome di dominio specifico, utilizzare il campo del percorso per creare un URL di sito univoco per quella combinazione di dominio e lingua.</span><span class="sxs-lookup"><span data-stu-id="1061d-132">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="1061d-133">Se la lingua specificata nel campo **Lingua predefinita** è l'unica lingua che verrà supportata per il dominio, o sarà sempre la lingua predefinita dopo aver localizzato il sito in altre lingue, è consigliabile lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="1061d-133">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="1061d-134">Dopo la creazione del sito, è possibile verificare che sia associato al punto vendita online selezionando la scheda **Prodotti**. Dovrebbe essere visualizzato l'assortimento di prodotti che è stato allocato al punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="1061d-134">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="1061d-135">È anche possibile utilizzare il menu a discesa nell'angolo in alto a sinistra della pagina per accedere ai prodotti allocati per categoria.</span><span class="sxs-lookup"><span data-stu-id="1061d-135">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1061d-136">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1061d-136">Additional resources</span></span>

[<span data-ttu-id="1061d-137">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="1061d-137">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="1061d-138">Distribuire un nuovo sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="1061d-138">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="1061d-139">Associare un sito online a un canale</span><span class="sxs-lookup"><span data-stu-id="1061d-139">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="1061d-140">Gestire i file robots.txt</span><span class="sxs-lookup"><span data-stu-id="1061d-140">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="1061d-141">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="1061d-141">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="1061d-142">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="1061d-142">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="1061d-143">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="1061d-143">Enable location-based store detection</span></span>](enable-store-detection.md)
