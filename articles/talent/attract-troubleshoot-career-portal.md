---
title: Gli utenti di Attract non possono candidarsi per mansioni dal portale delle carriere
description: Questo argomento spiega come risolvere un problema a causa del quale gli utenti di Attract non possono candidarsi per lavori dal portale delle carriere.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: e1d72bef6d8bbe15e27326f66341915ba44a09b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461604"
---
# <a name="attract-users-cant-apply-for-jobs-from-career-portal"></a><span data-ttu-id="7e5d8-103">Gli utenti di Attract non possono candidarsi per mansioni dal portale delle carriere</span><span class="sxs-lookup"><span data-stu-id="7e5d8-103">Attract users can't apply for jobs from career portal</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="7e5d8-104">Uscita</span><span class="sxs-lookup"><span data-stu-id="7e5d8-104">Issue</span></span>

<span data-ttu-id="7e5d8-105">Gli utenti di Attract non possono candidarsi per mansioni dal portale delle carriere.</span><span class="sxs-lookup"><span data-stu-id="7e5d8-105">Attract users can't apply for jobs from the career portal.</span></span> <span data-ttu-id="7e5d8-106">Quando cercano di candidarsi per un lavoro creato in Dynamics 365 Talent: Attract, il browser carica la pagina continuamente e non completa l'azione.</span><span class="sxs-lookup"><span data-stu-id="7e5d8-106">When they try to apply for a job that was created in Dynamics 365 Talent: Attract, the browser loads the page continuously and doesn't complete the action.</span></span>

## <a name="cause"></a><span data-ttu-id="7e5d8-107">Causa</span><span class="sxs-lookup"><span data-stu-id="7e5d8-107">Cause</span></span>

<span data-ttu-id="7e5d8-108">Questo problema si verifica quando il team delle relazioni di Talent non ha il ruolo utente Talent.</span><span class="sxs-lookup"><span data-stu-id="7e5d8-108">This problem occurs when the Talent Relationship Team doesn't have the Talent user role.</span></span>

## <a name="resolution"></a><span data-ttu-id="7e5d8-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="7e5d8-109">Resolution</span></span>

<span data-ttu-id="7e5d8-110">Assegnare il ruolo utente Talent al team delle relazioni di Talent.</span><span class="sxs-lookup"><span data-stu-id="7e5d8-110">Assign the Talent user role to the Talent Relationship Team.</span></span>

1. <span data-ttu-id="7e5d8-111">Accedere all'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com) con una delle seguenti credenziali di amministratore:</span><span class="sxs-lookup"><span data-stu-id="7e5d8-111">Sign in to the [Power Platform admin center](https://admin.powerplatform.microsoft.com) with any of the following admin credentials:</span></span>

   - <span data-ttu-id="7e5d8-112">Amministratore di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7e5d8-112">Dynamics 365 admin</span></span>
   - <span data-ttu-id="7e5d8-113">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="7e5d8-113">Global admin</span></span>
   - <span data-ttu-id="7e5d8-114">Amministratore di Power Platform</span><span class="sxs-lookup"><span data-stu-id="7e5d8-114">Power Platform admin</span></span>

2. <span data-ttu-id="7e5d8-115">Nel riquadro di spostamento selezionare **Ambienti**, quindi selezionare l'ambiente in cui assegnare il ruolo utente Talent al team delle relazioni di Talent.</span><span class="sxs-lookup"><span data-stu-id="7e5d8-115">In the navigation pane, select **Environments**, and then select the environment in which to assign the Talent user role to the Talent Relationship Team.</span></span>

   ![Selezionare l'ambiente](./media/attract-troubleshoot-career-portal-select-environment.png)

3. <span data-ttu-id="7e5d8-117">Nel riquadro **Ambienti** selezionare l'**URL dell'ambiente** e accedere al portale di amministrazione dell'ambiente (ad esempio, https:<orgname>.crm.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="7e5d8-117">In the **Environments** pane, select the **Environment URL** and sign in to the environment's admin portal (for example, https:<orgname>.crm.dynamics.com).</span></span>

4. <span data-ttu-id="7e5d8-118">Selezionare **Impostazioni**, **Sistema** e quindi selezionare **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="7e5d8-118">Select **Settings**, select **System**, and then select **Security**.</span></span>

   ![Passare a Sicurezza](./media/attract-troubleshoot-career-portal-security.png)

5. <span data-ttu-id="7e5d8-120">Selezionare **Teams**.</span><span class="sxs-lookup"><span data-stu-id="7e5d8-120">Select **Teams**.</span></span>

   ![Selezionare Teams](./media/attract-troubleshoot-career-portal-security-teams.png)

6. <span data-ttu-id="7e5d8-122">Cercare **Team delle relazioni di Talent** nella casella di ricerca, quindi selezionare il team dai risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="7e5d8-122">Search for **Talent Relationship Team** in the search box, and then select the team from the search results.</span></span>

7. <span data-ttu-id="7e5d8-123">Selezionare **GESTISCI RUOLI** dalla barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="7e5d8-123">Select **MANAGE ROLES** from the ribbon.</span></span>

8. <span data-ttu-id="7e5d8-124">Nella finestra di dialogo **Gestisci i ruoli del team**, selezionare **Utente di Talent** dall'elenco dei ruoli disponibili, quindi selezionare **OK** per applicare il ruolo.</span><span class="sxs-lookup"><span data-stu-id="7e5d8-124">In the **Manage Team Roles** dialog, select **Talent user** from the list of available roles, and then select **OK** to apply the role.</span></span>

   ![Applicare il ruolo](./media/attract-troubleshoot-career-portal-apply-role.png)

9. <span data-ttu-id="7e5d8-126">Testare le modifiche:</span><span class="sxs-lookup"><span data-stu-id="7e5d8-126">Test your changes:</span></span>

   1. <span data-ttu-id="7e5d8-127">Accedere al portale delle carriere da una nuova finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="7e5d8-127">Sign in to the career portal from a new browser window.</span></span>
   2. <span data-ttu-id="7e5d8-128">Candidarsi per il lavoro dal portale delle carriere.</span><span class="sxs-lookup"><span data-stu-id="7e5d8-128">Apply for the job from the career portal.</span></span> 