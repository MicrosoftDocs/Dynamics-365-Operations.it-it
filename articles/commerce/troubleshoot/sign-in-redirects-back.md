---
title: Il collegamento di accesso reindirizza a un sito di e-commerce
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un collegamento di accesso reindirizza al sito di e-commerce anziché alla pagina di accesso.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: ee2ac8636dad8d31719971b2cc17c8b923f07959
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801461"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a><span data-ttu-id="2b6e7-103">Il collegamento di accesso reindirizza a un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="2b6e7-103">Sign-in link redirects back to an e-commerce site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2b6e7-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un collegamento di accesso reindirizza al sito di e-commerce anziché alla pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="2b6e7-104">This topic provides troubleshooting guidance that can help when a sign-in link redirects back to the e-commerce site instead of going to the sign-in page.</span></span>

## <a name="description"></a><span data-ttu-id="2b6e7-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b6e7-105">Description</span></span>

<span data-ttu-id="2b6e7-106">Dopo aver configurato un nuovo tenant di Microsoft Azure Active Directory B2C (Azure AD B2C) in Creazione di siti di Commerce, gli utenti che selezionano il collegamento di **accesso** vengono reindirizzati alla pagina di destinazione di e-commerce principale senza passare alla pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="2b6e7-106">After you configure a new Microsoft Azure Active Directory B2C (Azure AD B2C) tenant in Commerce site builder, users who select the **Sign in** link are redirected back to the main e-commerce landing page without going to the sign-in page.</span></span>

## <a name="resolution"></a><span data-ttu-id="2b6e7-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="2b6e7-107">Resolution</span></span>

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a><span data-ttu-id="2b6e7-108">Verificare che l'URL di risposta sia configurato correttamente nell'applicazione Azure AD B2C</span><span class="sxs-lookup"><span data-stu-id="2b6e7-108">Confirm that the reply URL is correctly configured in the Azure AD B2C application</span></span>

<span data-ttu-id="2b6e7-109">Per confermare che l'URL di risposta sia configurato correttamente nell'applicazione Azure AD B2C, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="2b6e7-109">To confirm that the reply URL is correctly configured in the Azure AD B2C application, follow these steps.</span></span>

1. <span data-ttu-id="2b6e7-110">Accedi al [portale di Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="2b6e7-110">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="2b6e7-111">Selezionare l'applicazione Azure AD B2C creata per l'accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="2b6e7-111">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="2b6e7-112">Selezionare l'applicazione creata durante la configurazione di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2b6e7-112">Select the application that you created during the Azure AD B2C setup.</span></span>
1. <span data-ttu-id="2b6e7-113">Sotto **URL di risposta**, assicurarsi che l'elenco includa voci per l'URL del dominio del sito e per l'URL generato dall'e-commerce, come mostrato nell'esempio nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="2b6e7-113">Under **Reply URL**, make sure that the list includes entries for both the site domain URL and the e-commerce-generated URL, as shown in the example in the following illustration.</span></span>

    ![Voci dell'URL di risposta Azure AD B2C](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> <span data-ttu-id="2b6e7-115">L'URL del dominio del sito e l'URL generato dall'e-commerce devono essere in un formato URL valido che non include barre iniziali o finali.</span><span class="sxs-lookup"><span data-stu-id="2b6e7-115">Both the site domain URL and the e-commerce-generated URL must be in a valid URL format that doesn't include leading or trailing slashes.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2b6e7-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2b6e7-116">Additional resources</span></span>

[<span data-ttu-id="2b6e7-117">Registrare un'applicazione Web in Azure Active Directory B2C</span><span class="sxs-lookup"><span data-stu-id="2b6e7-117">Register a web application in Azure Active Directory B2C</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[<span data-ttu-id="2b6e7-118">Impostare un tenant B2C in Commerce</span><span class="sxs-lookup"><span data-stu-id="2b6e7-118">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)
