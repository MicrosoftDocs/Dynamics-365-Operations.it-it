---
title: Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams
description: Questo argomento descrive come abilitare l'integrazione di Microsoft Dynamics 365 Commerce e Microsoft Teams.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eb0b8b419b302fbd0bc107bca22f8b26774ba3c7
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019837"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a><span data-ttu-id="6b2b5-103">Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6b2b5-103">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6b2b5-104">Questo argomento descrive come abilitare l'integrazione di Microsoft Dynamics 365 Commerce e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-104">This topic describes how to enable Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="6b2b5-105">Per fornire a Teams informazioni da Dynamics 365 Commerce e sincronizzare le funzionalità di gestione delle attività tra Teams e l'applicazione del punto vendita (POS), è necessario abilitare le funzionalità di integrazione in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-105">To provision Teams with information from Dynamics 365 Commerce and synchronize the task management features between Teams and the point of sale (POS) application, you must enable the integration features in Commerce headquarters.</span></span>

> [!NOTE]
> <span data-ttu-id="6b2b5-106">Quando abiliti l'integrazione di Teams, acconsenti a condividere i tuoi dati con Teams.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-106">When you enable Teams integration, you consent to share your data with Teams.</span></span> <span data-ttu-id="6b2b5-107">I dati condivisi con Teams potrebbero risiedere in un paese diverso rispetto ai dati di Commerce e potrebbero essere soggetti a standard di conformità diversi.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-107">Data that is shared with Teams might reside in a different country than your Commerce data, and it might be subject to different compliance standards.</span></span> <span data-ttu-id="6b2b5-108">Per ulteriori informazioni, vedi il [Centro protezione Microsoft](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="6b2b5-108">For more information, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="6b2b5-109">Per informazioni sui criteri della privacy di Microsoft, vedi l'[Informativa sulla privacy di Microsoft](https://aka.ms/privacy).</span><span class="sxs-lookup"><span data-stu-id="6b2b5-109">For information about Microsoft privacy policies, see the [Microsoft Privacy Statement](https://aka.ms/privacy).</span></span>

## <a name="enable-teams-integration"></a><span data-ttu-id="6b2b5-110">Abilitare l'integrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="6b2b5-110">Enable Teams integration</span></span>

<span data-ttu-id="6b2b5-111">Prima di poter abilitare l'integrazione di Microsoft Teams con Commerce, è necessario registrare l'applicazione Teams con il tenant nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-111">Before you can enable Microsoft Teams integration with Commerce, you must register the Teams application with your tenant in the Azure portal.</span></span>

<span data-ttu-id="6b2b5-112">Per registrare l'applicazione Teams con il tuo tenant nel portale di Azure, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-112">To register the Teams application with your tenant in the Azure portal, follow these steps.</span></span>

1. <span data-ttu-id="6b2b5-113">Segui i passaggi in [Guida introduttiva: Registrare un'applicazione con Microsoft Identity Platform](/azure/active-directory/develop/quickstart-register-app) per registrare l'applicazione Teams con il tenant nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-113">Follow the steps in [Quickstart: Register an app in the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app) to register the Teams application with your tenant in the Azure portal.</span></span>
1. <span data-ttu-id="6b2b5-114">Copia il valore **ID applicazione (client)** dalla pagina **Panoramica** per l'app registrata.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-114">Copy the **Application (client) ID** value from the **Overview** page for the registered app.</span></span> <span data-ttu-id="6b2b5-115">Utilizzerai questo valore per abilitare l'integrazione di Teams in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-115">You will use this value to enable Teams integration in Commerce headquarters.</span></span>
1. <span data-ttu-id="6b2b5-116">Copia il valore del certificato che hai immesso quando hai [aggiunto un certificato](/azure/active-directory/develop/quickstart-register-app#add-a-certificate) al passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-116">Copy the certificate value that was entered when you [added a certificate](/azure/active-directory/develop/quickstart-register-app#add-a-certificate) in step 1.</span></span> <span data-ttu-id="6b2b5-117">Il certificato è anche noto come chiave pubblica o chiave dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-117">The certificate is also known as the public key or application key.</span></span> <span data-ttu-id="6b2b5-118">Utilizzerai questo valore per abilitare l'integrazione di Teams in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-118">You will use this value to enable Teams integration in Commerce headquarters.</span></span>

<span data-ttu-id="6b2b5-119">Per abilitare l'integrazione di Teams in Commerce headquarters, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-119">To enable Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="6b2b5-120">Vai a **Retail e Commerce \> Impostazione canale \> Configurazione dell'integrazione di Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-120">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams integration configuration**.</span></span>
1. <span data-ttu-id="6b2b5-121">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-121">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="6b2b5-122">Imposta l'opzione **Abilita integrazione di Microsoft Teams** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-122">Set the **Enable Microsoft Teams integration** option to **Yes**.</span></span>
1. <span data-ttu-id="6b2b5-123">Nei campi **ID applicazione** e **Chiave dell'applicazione** immetti i valori ottenuti durante la registrazione dell'applicazione Teams nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-123">In the **Application ID** and **Application key** fields, enter the values you obtained when you registered the Teams application in the Azure portal.</span></span>
1. <span data-ttu-id="6b2b5-124">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-124">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="6b2b5-125">La figura seguente mostra un esempio di configurazione dell'integrazione di Teams in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-125">The following illustration shows an example of the configuration of Teams integration in Commerce headquarters.</span></span>

![Configurazione dell'integrazione di Teams in Commerce headquarters](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a><span data-ttu-id="6b2b5-127">Disabilitare l'integrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="6b2b5-127">Disable Teams integration</span></span>

<span data-ttu-id="6b2b5-128">Per disabilitare l'integrazione di Microsoft Teams in Commerce headquarters, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-128">To disable Microsoft Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="6b2b5-129">Vai a **Retail e Commerce \> Impostazione canale \> Configurazione dell'integrazione di Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-129">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="6b2b5-130">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-130">On the Action Pane, select **Edit**.</span></span>
3. <span data-ttu-id="6b2b5-131">Imposta l'opzione **Abilita integrazione di Microsoft Teams** su **No**.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-131">Set the **Enable Microsoft Teams integration** option to **No**.</span></span>
4. <span data-ttu-id="6b2b5-132">Cancella i valori dai campi **ID applicazione** e **Chiave applicazione**.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-132">Clear the values from the **Application ID** and **Application Key** fields.</span></span>
1. <span data-ttu-id="6b2b5-133">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-133">On the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="6b2b5-134">Dopo aver disabilitato l'integrazione di Teams con Commerce, i terminali POS non mostreranno più le attività pubblicate dall'applicazione Teams.</span><span class="sxs-lookup"><span data-stu-id="6b2b5-134">After you disable Teams integration with Commerce, POS terminals will no longer show tasks that are published from the Teams application.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6b2b5-135">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="6b2b5-135">Additional resources</span></span>

[<span data-ttu-id="6b2b5-136">Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6b2b5-136">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="6b2b5-137">Provisioning di Microsoft Teams da Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6b2b5-137">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="6b2b5-138">Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6b2b5-138">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="6b2b5-139">Gestire i ruoli utente in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6b2b5-139">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="6b2b5-140">Mappare negozi e team se ci sono team preesistenti in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6b2b5-140">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="6b2b5-141">Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6b2b5-141">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)