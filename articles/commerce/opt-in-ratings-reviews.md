---
title: Consentire l'utilizzo di valutazioni e recensioni
description: In questo argomento viene descritto come consentire l'utilizzo di valutazioni e recensioni sul sito di Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: 10e3c33af232fa46df09a103b2e73eae09a909eb
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697982"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="c5411-103">Consentire l'utilizzo di valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="c5411-103">Opt in to use ratings and reviews</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="c5411-104">In questo argomento viene descritto come consentire l'utilizzo di valutazioni e recensioni sul sito di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c5411-104">This topic explains how to opt in to use ratings and reviews on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="c5411-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="c5411-105">Overview</span></span>

<span data-ttu-id="c5411-106">La soluzione con valutazioni e recensioni è una soluzione multicanale che è possibile rendere disponibile in Dynamics 365 Commerce mediante Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c5411-106">The ratings and reviews solution is an omnichannel solution that you can make available in Dynamics 365 Commerce by using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="c5411-107">LCS è un portale di amministrazione che i rivenditori utilizzano per gestire i loro ambienti dal provisioning alla rimozione.</span><span class="sxs-lookup"><span data-stu-id="c5411-107">LCS is an administration portal that retailers use to manage their environments from provisioning to decommissioning.</span></span>

<span data-ttu-id="c5411-108">Se si desidera utilizzare la soluzione con valutazioni e recensioni sul sito Web di Commerce, è necessario dapprima consentirne l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="c5411-108">If you want to use the ratings and reviews solution on your Commerce website, you must first opt in.</span></span>

## <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="c5411-109">Consentire l'utilizzo di valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="c5411-109">Opt in to use ratings and reviews</span></span>

<span data-ttu-id="c5411-110">Per consentire l'utilizzo di valutazioni e recensioni sul sito, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="c5411-110">To opt in to use ratings and reviews on your site, follow these steps.</span></span>

1. <span data-ttu-id="c5411-111">Seguire i passaggi in [Distribuire un nuovo sito di e-Commerce](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="c5411-111">Follow the steps in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span>
1. <span data-ttu-id="c5411-112">Quando si è ancora in LCS, andare a **Configurazione distribuzione Retail \> Altre impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="c5411-112">While you're still in LCS, go to **Retail deployment setup \> Other settings**.</span></span>
1. <span data-ttu-id="c5411-113">Impostare l'opzione **Abilita servizio Valutazioni e recensioni** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="c5411-113">Set the **Enable ratings and reviews service** option to **Yes**.</span></span>
1. <span data-ttu-id="c5411-114">Nel campo **Gruppo di sicurezza ADD per moderatore di valutazioni e recensioni (ID oggetto gruppo di sicurezza)**, immettere l'ID gruppo di sicurezza di Microsoft Azure Active Directory (Azure AD) che include moderatori di valutazioni e recensioni.</span><span class="sxs-lookup"><span data-stu-id="c5411-114">In the **AAD security group for ratings and review moderator (security group object id)** field, enter the ID of the Microsoft Azure Active Directory (Azure AD) security group that includes the ratings and reviews moderators.</span></span>

    ![Consentire l'utilizzo di valutazioni e recensioni](media/LCS_RnR_Preference.png)

1. <span data-ttu-id="c5411-116">Completare il processo di inizializzazione di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="c5411-116">Complete the e-Commerce initialization process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c5411-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c5411-117">Additional resources</span></span>

[<span data-ttu-id="c5411-118">Panoramica valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="c5411-118">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="c5411-119">Gestire valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="c5411-119">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="c5411-120">Configurare valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="c5411-120">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="c5411-121">Sincronizzare valutazioni sul prodotto in Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="c5411-121">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)