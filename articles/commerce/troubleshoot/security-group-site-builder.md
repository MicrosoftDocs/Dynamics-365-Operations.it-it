---
title: Impossibile configurare un gruppo di sicurezza per Creazione di siti di Commerce durante la distribuzione iniziale
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando il gruppo di sicurezza Microsoft Azure Active Directory (Azure AD) per Creazione di siti di Commerce non appare come opzione quando si creano componenti di e-commerce in Microsoft Dynamics Lifecycle Services (LCS) durante la distribuzione iniziale di un nuovo tenant di e-commerce.
author: Reza-Assadi
manager: AnnBe
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
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 36ea43e19f395e3914d3eda1a9b8f5487b0926c5
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585396"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a><span data-ttu-id="76b06-103">Impossibile configurare un gruppo di sicurezza per Creazione di siti di Commerce durante la distribuzione iniziale</span><span class="sxs-lookup"><span data-stu-id="76b06-103">Can't configure a security group for Commerce site builder during initial deployment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="76b06-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando il gruppo di sicurezza Microsoft Azure Active Directory (Azure AD) per Creazione di siti di Commerce non appare come opzione quando si creano componenti di e-commerce in Microsoft Dynamics Lifecycle Services (LCS) durante la distribuzione iniziale di un nuovo tenant di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="76b06-104">This topic provides troubleshooting guidance that can help when the Microsoft Azure Active Directory (Azure AD) security group for Commerce site builder doesn't appear as an option when you create e-commerce components in Microsoft Dynamics Lifecycle Services (LCS) during initial deployment of a new e-commerce tenant.</span></span>

## <a name="description"></a><span data-ttu-id="76b06-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76b06-105">Description</span></span>

<span data-ttu-id="76b06-106">Quando si creano i componenti di e-commerce come parte del processo di distribuzione di un nuovo tenant di e-commerce che include il componente Creazione di siti di Commerce, il gruppo di sicurezza Azure AD non viene visualizzato come opzione nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="76b06-106">When you create the e-commerce components as part of the process of deploying a new e-commerce tenant that includes the Commerce site builder component, the Azure AD security group doesn't appear as an option in the dialog box.</span></span>

## <a name="resolution"></a><span data-ttu-id="76b06-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="76b06-107">Resolution</span></span>

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a><span data-ttu-id="76b06-108">Effettuare il provisioning del sito di e-commerce con un utente nel tenant corretto</span><span class="sxs-lookup"><span data-stu-id="76b06-108">Provision the e-commerce site with a user in the correct tenant</span></span>

1. <span data-ttu-id="76b06-109">Accedi al [portale di Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="76b06-109">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="76b06-110">Sotto il tenant per cui è stato eseguito il provisioning del progetto LCS per il sito di e-commerce, seguire le istruzioni in [Creare un gruppo di base e aggiungere membri utilizzando Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="76b06-110">Under the tenant that the LCS project for your e-commerce site was provisioned for, follow the instructions in [Create a basic group and add members using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span>
1. <span data-ttu-id="76b06-111">Accedere a [LCS](https://lcs.dynamics.com/) utilizzando un account che condivide lo stesso tenant del gruppo di sicurezza Azure AD appena creato.</span><span class="sxs-lookup"><span data-stu-id="76b06-111">Go to [LCS](https://lcs.dynamics.com/), and sign in by using an account that shares the same tenant as the Azure AD security group that you just created.</span></span> <span data-ttu-id="76b06-112">L'account deve avere accesso per visualizzare il gruppo di sicurezza Azure AD.</span><span class="sxs-lookup"><span data-stu-id="76b06-112">The account must have access to view the Azure AD security group.</span></span>
1. <span data-ttu-id="76b06-113">Completa i passaggi di configurazione per configurare il sito di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="76b06-113">Complete the setup steps to configure the e-commerce site.</span></span> <span data-ttu-id="76b06-114">Quando si esegue il provisioning dei componenti di e-commerce, il gruppo di sicurezza deve apparire come opzione nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="76b06-114">When you provision the e-commerce components, the security group should now appear as an option in the dialog box.</span></span>

> [!NOTE]
> <span data-ttu-id="76b06-115">Per assicurarsi che il campo nella finestra di dialogo sia riempito con l'elenco di gruppi di sicurezza, è necessario selezionare **Immetti** dopo aver inserito il nome del gruppo di sicurezza Azure AD creato.</span><span class="sxs-lookup"><span data-stu-id="76b06-115">To ensure that the field in the dialog box is filled with the list of security groups, you must select **Enter** after you enter the name of the Azure AD security group that you created.</span></span> <span data-ttu-id="76b06-116">I risultati della ricerca elencheranno tutti i gruppi di sicurezza Azure AD che iniziano con il testo di ricerca e a cui l'utente ha accesso.</span><span class="sxs-lookup"><span data-stu-id="76b06-116">The search results will list all the Azure AD security groups that start with the search text, and that the user has access to.</span></span> <span data-ttu-id="76b06-117">È possibile utilizzare un termine di ricerca più breve per consentire risultati di ricerca più ampi.</span><span class="sxs-lookup"><span data-stu-id="76b06-117">You can use a shorter search term to allow for broader search results.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="76b06-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="76b06-118">Additional resources</span></span>

[<span data-ttu-id="76b06-119">Creare un gruppo di base e aggiungere membri utilizzando Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="76b06-119">Create a basic group and add members using Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[<span data-ttu-id="76b06-120">Distribuire un nuovo tenant di e-commerce</span><span class="sxs-lookup"><span data-stu-id="76b06-120">Deploy a new e-commerce tenant</span></span>](../deploy-ecommerce-site.md)
