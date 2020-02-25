---
title: Consentire l'utilizzo di valutazioni e recensioni
description: In questo argomento viene descritto come consentire l'utilizzo di valutazioni e recensioni sul sito di Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: eda7fbaeea8d3c1a07f7b43cafe44886d149a211
ms.sourcegitcommit: 1e6c8163da5818196769eb278afb3a2335d0cbe3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027267"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="97326-103">Consentire l'utilizzo di valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="97326-103">Opt in to use ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="97326-104">In questo argomento viene descritto come consentire l'utilizzo di valutazioni e recensioni sul sito di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="97326-104">This topic explains how to opt in to use ratings and reviews on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="97326-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="97326-105">Overview</span></span>

<span data-ttu-id="97326-106">La soluzione con valutazioni e recensioni è una soluzione multicanale che è possibile rendere disponibile in Dynamics 365 Commerce mediante Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="97326-106">The ratings and reviews solution is an omni-channel solution that you can make available in Dynamics 365 Commerce by using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="97326-107">LCS è un portale di amministrazione che i rivenditori utilizzano per gestire i loro ambienti dal provisioning alla rimozione.</span><span class="sxs-lookup"><span data-stu-id="97326-107">LCS is an administration portal that retailers use to manage their environments from provisioning to decommissioning.</span></span>

<span data-ttu-id="97326-108">Se si desidera utilizzare la soluzione con valutazioni e recensioni sul sito Web di Commerce, è necessario consentire l'utilizzo di valutazioni e recensioni durante la distribuzione del sito di e-commerce in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="97326-108">If you want to use the ratings and reviews solution on your Commerce website, you must opt in for ratings and reviews during deployment of your e-Commerce site on Dynamics 365 Commerce.</span></span>

## <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="97326-109">Consentire utilizzo di valutazioni e sulle revisioni</span><span class="sxs-lookup"><span data-stu-id="97326-109">Opt in to use ratings and reviews</span></span>

<span data-ttu-id="97326-110">Per consentire l'utilizzo di valutazioni e recensioni sul sito, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="97326-110">To opt in to use ratings and reviews on your site, follow these steps.</span></span>

1. <span data-ttu-id="97326-111">Seguire i passaggi in [Distribuire un nuovo sito di e-Commerce](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="97326-111">Follow the steps in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span>
1. <span data-ttu-id="97326-112">Quando si è ancora in LCS, andare a **Configurazione distribuzione Retail \> Altre impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="97326-112">While you're still in LCS, go to **Retail deployment setup \> Other settings**.</span></span>
1. <span data-ttu-id="97326-113">Impostare l'opzione **Abilita servizio Valutazioni e recensioni** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="97326-113">Set the **Enable ratings and reviews service** option to **Yes**.</span></span>
1. <span data-ttu-id="97326-114">Nel campo **Gruppo di sicurezza ADD per moderatore di valutazioni e recensioni (ID oggetto gruppo di sicurezza)**, immettere l'ID gruppo di sicurezza di Microsoft Azure Active Directory (Azure AD) che include moderatori di valutazioni e recensioni.</span><span class="sxs-lookup"><span data-stu-id="97326-114">In the **AAD security group for ratings and review moderator (security group object id)** field, enter the ID of the Microsoft Azure Active Directory (Azure AD) security group that includes the ratings and reviews moderators.</span></span>

    ![Consentire utilizzo di valutazioni e sulle revisioni](media/LCS_RnR_Preference.png)

1. <span data-ttu-id="97326-116">Completare il processo di inizializzazione di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="97326-116">Complete the e-Commerce initialization process.</span></span>

> [!NOTE] 
> <span data-ttu-id="97326-117">Se si è un cliente Dynamics 365 Commerce esistente che ha già distribuito un sito di e-commerce senza aver fornito il consenso per l'utilizzo di valutazioni e recensioni e ora si desidera utilizzare valutazioni e recensioni del pacchetto Dynamics 365 Commerce, inviare una richiesta di assistenza.</span><span class="sxs-lookup"><span data-stu-id="97326-117">If you are an existing Dynamics 365 Commerce customer who has already deployed an e-Commerce site without having opted in for ratings and reviews and now want to use ratings and reviews from the Dynamics 365 Commerce package, please submit a service request.</span></span> <span data-ttu-id="97326-118">Per informazioni su come inviare una richiesta di assistenza, vedere [Processo per inviare richieste di servizio](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="97326-118">For information about how to submit a service request, see [Submit service requests process](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json).</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="97326-119">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="97326-119">Additional resources</span></span>

[<span data-ttu-id="97326-120">Panoramica valutazioni e revisioni</span><span class="sxs-lookup"><span data-stu-id="97326-120">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="97326-121">Gestire valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="97326-121">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="97326-122">Configurare valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="97326-122">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="97326-123">Sincronizzare valutazioni sul prodotto in Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="97326-123">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)


