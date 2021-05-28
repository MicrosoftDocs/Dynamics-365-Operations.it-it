---
title: Limitare l'accesso a una vetrina durante il processo di test o sviluppo
description: In questo argomento viene descritto come limitare l'accesso a una vetrina di Microsoft Dynamics 365 Commerce durante il processo di test o sviluppo.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: cdc9b6af55bcba98f5ea7607bb1847f61a707778
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018340"
---
# <a name="restrict-access-to-a-storefront-during-testing-or-development"></a><span data-ttu-id="4b84e-103">Limitare l'accesso a una vetrina durante il processo di test o sviluppo</span><span class="sxs-lookup"><span data-stu-id="4b84e-103">Restrict access to a storefront during testing or development</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4b84e-104">In questo argomento viene descritto come limitare l'accesso a una vetrina di Microsoft Dynamics 365 Commerce durante il processo di test o sviluppo.</span><span class="sxs-lookup"><span data-stu-id="4b84e-104">This topic explains how to restrict access to a Microsoft Dynamics 365 Commerce storefront while internal testing or development is occurring.</span></span>

## <a name="description"></a><span data-ttu-id="4b84e-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b84e-105">Description</span></span>

<span data-ttu-id="4b84e-106">Durante il processo di test o sviluppo attivo interno, è possibile che si intenda limitare l'accesso al sito per impedire agli utenti esterni di accedere alle pagine della vetrina pubblicate.</span><span class="sxs-lookup"><span data-stu-id="4b84e-106">During internal testing or active development, you might want to restrict access to your site to prevent external users from accessing the published storefront pages.</span></span>

## <a name="resolution"></a><span data-ttu-id="4b84e-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="4b84e-107">Resolution</span></span>

### <a name="set-up-azure-ad-b2c-by-using-standard-user-flows"></a><span data-ttu-id="4b84e-108">Impostare Azure AD B2C utilizzando flussi utente standard</span><span class="sxs-lookup"><span data-stu-id="4b84e-108">Set up Azure AD B2C by using standard user flows</span></span>

<span data-ttu-id="4b84e-109">Per informazioni su come configurare Azure Active Directory B2C (Azure AD B2C) per il sito di e-commerce, vedere [Impostare un tenant B2C in Commerce](../set-up-b2c-tenant.md).</span><span class="sxs-lookup"><span data-stu-id="4b84e-109">For information about how to configure Azure Active Directory B2C (Azure AD B2C) for your e-commerce site, see [Set up a B2C tenant in Commerce](../set-up-b2c-tenant.md).</span></span>

### <a name="restrict-user-access-to-storefront-pages-and-block-the-creation-of-new-users"></a><span data-ttu-id="4b84e-110">Limitare l'accesso degli utenti alle pagine della vetrina e bloccare la creazione di nuovi utenti</span><span class="sxs-lookup"><span data-stu-id="4b84e-110">Restrict user access to storefront pages and block the creation of new users</span></span>

<span data-ttu-id="4b84e-111">Per limitare l'accesso degli utenti alle pagine della vetrina in Creazione di siti di Commerce, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="4b84e-111">To restrict user access to storefront pages in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="4b84e-112">Accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="4b84e-112">Go to your site.</span></span>
1. <span data-ttu-id="4b84e-113">Selezionare **Pagine**, quindi selezionare la pagina per la quale limitare l'accesso utente.</span><span class="sxs-lookup"><span data-stu-id="4b84e-113">Select **Pages**, and then select the page to restrict user access for.</span></span>
1. <span data-ttu-id="4b84e-114">Selezionare lo slot del modulo o del frammento, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="4b84e-114">Select the module or fragment slot, and then select **Edit**.</span></span>
1. <span data-ttu-id="4b84e-115">Nel riquadro delle proprietà selezionare **È necessario l'accesso?**, quindi selezionare **Fine la modifica**.</span><span class="sxs-lookup"><span data-stu-id="4b84e-115">In the properties pane, select **Requires sign-in?**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="4b84e-116">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="4b84e-116">Select **Publish**.</span></span>

<span data-ttu-id="4b84e-117">Per bloccare la creazione di nuovi utenti in Azure AD, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="4b84e-117">To block the creation of new users in Azure AD, follow these steps.</span></span>

1. <span data-ttu-id="4b84e-118">Accedi al [portale di Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="4b84e-118">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="4b84e-119">Selezionare l'applicazione Azure AD B2C creata per l'accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="4b84e-119">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="4b84e-120">Nel pannello di navigazione a sinistra, selezionare **Flussi utente**.</span><span class="sxs-lookup"><span data-stu-id="4b84e-120">In the left navigation, select **User flows**.</span></span>
1. <span data-ttu-id="4b84e-121">Nella parte superiore della pagina **Flussi utente**, selezionare **Nuovo flusso utente**.</span><span class="sxs-lookup"><span data-stu-id="4b84e-121">At the top of the **User Flows** page, select **New user flow**.</span></span>
1. <span data-ttu-id="4b84e-122">Nella pagina **Seleziona un tipo di flusso utente**, selezionare **Anteprima**.</span><span class="sxs-lookup"><span data-stu-id="4b84e-122">On the **Select a user flow type** page, select **Preview**.</span></span>
1. <span data-ttu-id="4b84e-123">Al centro della pagina, selezionare **Accedi v2**.</span><span class="sxs-lookup"><span data-stu-id="4b84e-123">In the middle of the page, select **Sign in v2**.</span></span> <span data-ttu-id="4b84e-124">Quindi seguire i passaggi in [Impostare un tenant B2C in Commerce](../set-up-b2c-tenant.md) per configurare il flusso come flusso utente standard del sito per Azure AD B2C durante il processo di test o sviluppo.</span><span class="sxs-lookup"><span data-stu-id="4b84e-124">Then follow the steps in [Set up a B2C tenant in Commerce](../set-up-b2c-tenant.md) to configure the flow as your site's standard user flow for Azure AD B2C during testing or development.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4b84e-125">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4b84e-125">Additional resources</span></span>

[<span data-ttu-id="4b84e-126">Impostare un tenant B2C in Commerce</span><span class="sxs-lookup"><span data-stu-id="4b84e-126">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)

[<span data-ttu-id="4b84e-127">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="4b84e-127">Set up custom pages for user sign-ins</span></span>](../custom-pages-user-logins.md)
