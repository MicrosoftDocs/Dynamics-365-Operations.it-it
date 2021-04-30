---
title: Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams
description: Questo argomento descrive come abilitare l'integrazione di Microsoft Dynamics 365 Commerce e Microsoft Teams.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c4d596f27ffe15a97dc04e2ce7e85d21f8e7161f
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908397"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a><span data-ttu-id="f271e-103">Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f271e-103">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f271e-104">Questo argomento descrive come abilitare l'integrazione di Microsoft Dynamics 365 Commerce e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f271e-104">This topic describes how to enable Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="f271e-105">Per fornire a Teams informazioni da Dynamics 365 Commerce e sincronizzare le funzionalità di gestione delle attività tra Teams e l'applicazione del punto vendita (POS), è necessario abilitare le funzionalità di integrazione in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="f271e-105">To provision Teams with information from Dynamics 365 Commerce and synchronize the task management features between Teams and the point of sale (POS) application, you must enable the integration features in Commerce headquarters.</span></span>

> [!NOTE]
> <span data-ttu-id="f271e-106">Quando abiliti l'integrazione di Teams, acconsenti a condividere i tuoi dati con Teams.</span><span class="sxs-lookup"><span data-stu-id="f271e-106">When you enable Teams integration, you consent to share your data with Teams.</span></span> <span data-ttu-id="f271e-107">I dati condivisi con Teams potrebbero risiedere in un paese diverso rispetto ai dati di Commerce e potrebbero essere soggetti a standard di conformità diversi.</span><span class="sxs-lookup"><span data-stu-id="f271e-107">Data that is shared with Teams might reside in a different country than your Commerce data, and it might be subject to different compliance standards.</span></span> <span data-ttu-id="f271e-108">Per ulteriori informazioni, vedi il [Centro protezione Microsoft](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="f271e-108">For more information, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="f271e-109">Per informazioni sui criteri della privacy di Microsoft, vedi l'[Informativa sulla privacy di Microsoft](https://aka.ms/privacy).</span><span class="sxs-lookup"><span data-stu-id="f271e-109">For information about Microsoft privacy policies, see the [Microsoft Privacy Statement](https://aka.ms/privacy).</span></span>

## <a name="enable-teams-integration"></a><span data-ttu-id="f271e-110">Abilitare l'integrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="f271e-110">Enable Teams integration</span></span>

<span data-ttu-id="f271e-111">Prima di poter abilitare l'integrazione di Microsoft Teams con Commerce, è necessario registrare l'applicazione Teams con il tenant nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="f271e-111">Before you can enable Microsoft Teams integration with Commerce, you must register the Teams application with your tenant in the Azure portal.</span></span>

<span data-ttu-id="f271e-112">Per registrare l'applicazione Teams con il tuo tenant nel portale di Azure, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="f271e-112">To register the Teams application with your tenant in the Azure portal, follow these steps.</span></span>

1. <span data-ttu-id="f271e-113">Segui i passaggi in [Guida introduttiva: Registrare un'applicazione con Microsoft Identity Platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app) per registrare l'applicazione Teams con il tenant nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="f271e-113">Follow the steps in [Quickstart: Register an app in the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app) to register the Teams application with your tenant in the Azure portal.</span></span>
1. <span data-ttu-id="f271e-114">Copia il valore **ID applicazione (client)** dalla pagina **Panoramica** per l'app registrata.</span><span class="sxs-lookup"><span data-stu-id="f271e-114">Copy the **Application (client) ID** value from the **Overview** page for the registered app.</span></span> <span data-ttu-id="f271e-115">Utilizzerai questo valore per abilitare l'integrazione di Teams in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="f271e-115">You will use this value to enable Teams integration in Commerce headquarters.</span></span>
1. <span data-ttu-id="f271e-116">Copia il valore del certificato che hai immesso quando hai [aggiunto un certificato](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) al passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="f271e-116">Copy the certificate value that was entered when you [added a certificate](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) in step 1.</span></span> <span data-ttu-id="f271e-117">Il certificato è anche noto come chiave pubblica o chiave dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f271e-117">The certificate is also known as the public key or application key.</span></span> <span data-ttu-id="f271e-118">Utilizzerai questo valore per abilitare l'integrazione di Teams in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="f271e-118">You will use this value to enable Teams integration in Commerce headquarters.</span></span>

<span data-ttu-id="f271e-119">Per abilitare l'integrazione di Teams in Commerce headquarters, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="f271e-119">To enable Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="f271e-120">Vai a **Retail e Commerce \> Impostazione canale \> Configurazione dell'integrazione di Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f271e-120">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams integration configuration**.</span></span>
1. <span data-ttu-id="f271e-121">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f271e-121">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="f271e-122">Imposta l'opzione **Abilita integrazione di Microsoft Teams** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="f271e-122">Set the **Enable Microsoft Teams integration** option to **Yes**.</span></span>
1. <span data-ttu-id="f271e-123">Nei campi **ID applicazione** e **Chiave dell'applicazione** immetti i valori ottenuti durante la registrazione dell'applicazione Teams nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="f271e-123">In the **Application ID** and **Application key** fields, enter the values you obtained when you registered the Teams application in the Azure portal.</span></span>
1. <span data-ttu-id="f271e-124">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f271e-124">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="f271e-125">La figura seguente mostra un esempio di configurazione dell'integrazione di Teams in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="f271e-125">The following illustration shows an example of the configuration of Teams integration in Commerce headquarters.</span></span>

![Configurazione dell'integrazione di Teams in Commerce headquarters](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a><span data-ttu-id="f271e-127">Disabilitare l'integrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="f271e-127">Disable Teams integration</span></span>

<span data-ttu-id="f271e-128">Per disabilitare l'integrazione di Microsoft Teams in Commerce headquarters, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="f271e-128">To disable Microsoft Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="f271e-129">Vai a **Retail e Commerce \> Impostazione canale \> Configurazione dell'integrazione di Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f271e-129">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="f271e-130">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f271e-130">On the Action Pane, select **Edit**.</span></span>
3. <span data-ttu-id="f271e-131">Imposta l'opzione **Abilita integrazione di Microsoft Teams** su **No**.</span><span class="sxs-lookup"><span data-stu-id="f271e-131">Set the **Enable Microsoft Teams integration** option to **No**.</span></span>
4. <span data-ttu-id="f271e-132">Cancella i valori dai campi **ID applicazione** e **Chiave applicazione**.</span><span class="sxs-lookup"><span data-stu-id="f271e-132">Clear the values from the **Application ID** and **Application Key** fields.</span></span>
1. <span data-ttu-id="f271e-133">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f271e-133">On the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="f271e-134">Dopo aver disabilitato l'integrazione di Teams con Commerce, i terminali POS non mostreranno più le attività pubblicate dall'applicazione Teams.</span><span class="sxs-lookup"><span data-stu-id="f271e-134">After you disable Teams integration with Commerce, POS terminals will no longer show tasks that are published from the Teams application.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f271e-135">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f271e-135">Additional resources</span></span>

[<span data-ttu-id="f271e-136">Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f271e-136">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="f271e-137">Provisioning di Microsoft Teams da Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f271e-137">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="f271e-138">Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f271e-138">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="f271e-139">Gestire i ruoli utente in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f271e-139">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="f271e-140">Mappare negozi e team se ci sono team preesistenti in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f271e-140">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="f271e-141">Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f271e-141">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
