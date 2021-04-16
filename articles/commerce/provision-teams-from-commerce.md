---
title: Provisioning di Microsoft Teams da Dynamics 365 Commerce
description: Questo argomento descrive come eseguire il provisioning di Microsoft Teams utilizzando i dati dell'organizzazione da Dynamics 365 Commerce.
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
ms.openlocfilehash: 96382c072e03506294d72899072a358091bda8ab
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842694"
---
# <a name="provision-microsoft-teams-from-dynamics-365-commerce"></a><span data-ttu-id="321cf-103">Provisioning di Microsoft Teams da Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="321cf-103">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="321cf-104">Questo argomento descrive come eseguire il provisioning di Microsoft Teams utilizzando i dati dell'organizzazione da Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="321cf-104">This topic describes how to provision Microsoft Teams by using organizational data from Dynamics 365 Commerce.</span></span>

<span data-ttu-id="321cf-105">Dynamics 365 Commerce offre un modo semplice per eseguire il provisioning di Teams se non hai ancora impostato i team per i tuoi punti vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="321cf-105">Dynamics 365 Commerce offers an easy way to provision Teams if you haven't yet set up teams for your retail stores there.</span></span> <span data-ttu-id="321cf-106">Utilizzando le informazioni ben definite di Commerce in Teams, puoi aiutare i dipendenti del tuo negozio a iniziare a usare Teams.</span><span class="sxs-lookup"><span data-stu-id="321cf-106">By taking advantage of well-defined information from Commerce that you want to use in Teams, you can help your store employees get started in Teams.</span></span> <span data-ttu-id="321cf-107">Queste informazioni includono la gerarchia organizzativa, i nomi dei negozi, le informazioni sui dipendenti e gli account Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="321cf-107">This information includes the organizational hierarchy, store names, employee information, and Azure Active Directory (Azure AD) accounts.</span></span> 

<span data-ttu-id="321cf-108">Il processo di provisioning di Teams prevede due passaggi principali:</span><span class="sxs-lookup"><span data-stu-id="321cf-108">The process of provisioning Teams has two main steps:</span></span>

1. <span data-ttu-id="321cf-109">In Teams crea un team per ogni punto vendita al dettaglio e aggiungi i lavoratori del negozio come membri del team appropriato.</span><span class="sxs-lookup"><span data-stu-id="321cf-109">In Teams, create a team for each retail store, and add store workers as members of the appropriate team.</span></span> <span data-ttu-id="321cf-110">Se un dipendente è associato a più di un punto vendita al dettaglio, l'appartenenza al team rifletterà le associazioni.</span><span class="sxs-lookup"><span data-stu-id="321cf-110">If an employee is associated with more than one retail store, team membership will reflect that fact.</span></span> <span data-ttu-id="321cf-111">Verrà creato un team di comunicazione che include i manager regionali come membri per aiutare a pubblicare attività da Teams.</span><span class="sxs-lookup"><span data-stu-id="321cf-111">A communications team that includes regional managers as members will be created to help publish tasks from Teams.</span></span>
1. <span data-ttu-id="321cf-112">Carica la tua gerarchia organizzativa da Commerce a Teams.</span><span class="sxs-lookup"><span data-stu-id="321cf-112">Upload your organizational hierarchy from Commerce to Teams.</span></span>

## <a name="provision-teams-in-commerce-headquarters"></a><span data-ttu-id="321cf-113">Provisioning di Teams in Commerce headquarters</span><span class="sxs-lookup"><span data-stu-id="321cf-113">Provision Teams in Commerce headquarters</span></span>

<span data-ttu-id="321cf-114">Prima di eseguire il provisioning di Microsoft Teams, completa queste attività:</span><span class="sxs-lookup"><span data-stu-id="321cf-114">Before you provision Microsoft Teams, complete these tasks:</span></span>

- <span data-ttu-id="321cf-115">Verifica che tutti i responsabili regionali siano stati nominati responsabili delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="321cf-115">Confirm that all regional managers have been made communications managers.</span></span>
- <span data-ttu-id="321cf-116">Verifica che l'account Azure di ogni responsabile del negozio e lavoratore sia stato associato al record del responsabile o del lavoratore in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="321cf-116">Confirm that the Azure account of every store manager and worker has been associated with that manager's or worker's worker record in Commerce headquarters.</span></span>

<span data-ttu-id="321cf-117">Per eseguire il provisioning di Teams in Commerce Headquarters, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="321cf-117">To provision Teams in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="321cf-118">Vai a **Retail e Commerce \> Impostazione canale \> Configurazione dell'integrazione di Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="321cf-118">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="321cf-119">Nel riquadro azioni, seleziona **Provisioning di Team**.</span><span class="sxs-lookup"><span data-stu-id="321cf-119">On the Action Pane, select **Provision teams**.</span></span> <span data-ttu-id="321cf-120">Un processo batch denominato **Provisioning di Team** viene creato.</span><span class="sxs-lookup"><span data-stu-id="321cf-120">A batch job that is named **Teams provision** is created.</span></span>
1. <span data-ttu-id="321cf-121">Vai a **Amministrazione sistema \> Richieste di informazioni \> Processi batch** e trova il processo più recente con la descrizione **Provisioning di Team**.</span><span class="sxs-lookup"><span data-stu-id="321cf-121">Go to **System administration \> Inquiries \> Batch jobs**, and find the most recent job that has the description **Teams provision**.</span></span> <span data-ttu-id="321cf-122">Attendi fino al termine dell'esecuzione di questo processo.</span><span class="sxs-lookup"><span data-stu-id="321cf-122">Wait until this job has finished running.</span></span>

> [!TIP]
> <span data-ttu-id="321cf-123">Se nessuno dei tuoi responsabili regionali, responsabili del negozio e dipendenti del negozio è stato associato a una licenza di Teams, potresti ricevere il seguente messaggio di errore: "Impossibile recuperare le categorie Sku applicabili per l'utente".</span><span class="sxs-lookup"><span data-stu-id="321cf-123">If none of your regional managers, store managers, and store workers have been associated with a Teams license, you might receive the following error message: "Failed to retrieve appliable Sku categories for the user."</span></span> <span data-ttu-id="321cf-124">Per correggere il problema, seleziona **Sincronizza team e membri** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="321cf-124">To correct the issue, select **Sync teams and members** on the Action Pane.</span></span>

<!-- ![Dynamics 365 Commerce - Teams integration configuration](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)-->

## <a name="validate-teams-provisioning-in-the-teams-admin-center"></a><span data-ttu-id="321cf-125">Convalidare il provisioning di Teams nell'interfaccia di amministrazione di Teams</span><span class="sxs-lookup"><span data-stu-id="321cf-125">Validate Teams provisioning in the Teams admin center</span></span>

<span data-ttu-id="321cf-126">Per convalidare il provisioning di Microsoft Teams nell'interfaccia di amministrazione di Microsoft Teams, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="321cf-126">To validate Microsoft Teams provisioning in the Microsoft Teams admin center, follow these steps.</span></span>
    
1. <span data-ttu-id="321cf-127">Vai all'[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com/) e accedi come amministratore del tuo tenant e-commerce.</span><span class="sxs-lookup"><span data-stu-id="321cf-127">Go to the [Teams admin center](https://admin.teams.microsoft.com/), and sign in as the administrator of your e-commerce tenant.</span></span>
1. <span data-ttu-id="321cf-128">Nel riquadro di spostamento a sinistra, seleziona **Teams** per espanderlo, quindi seleziona **Gestisci team**.</span><span class="sxs-lookup"><span data-stu-id="321cf-128">In the left navigation pane, select **Teams** to expand it, and then select **Manage teams**.</span></span>
1. <span data-ttu-id="321cf-129">Verifica che sia stato creato un team per ogni punto vendita al dettaglio di Commerce.</span><span class="sxs-lookup"><span data-stu-id="321cf-129">Confirm that one team has been created for each Commerce retail store.</span></span>
1. <span data-ttu-id="321cf-130">Seleziona un team e verifica che i lavoratori del negozio siano stati aggiunti come membri.</span><span class="sxs-lookup"><span data-stu-id="321cf-130">Select a team, and confirm that store workers have been added to it as members.</span></span>
1. <span data-ttu-id="321cf-131">Nel riquadro di spostamento a sinistra, seleziona **Utenti** e verifica che tutti i dipendenti del negozio in tutti i negozi siano stati aggiunti come utenti.</span><span class="sxs-lookup"><span data-stu-id="321cf-131">In the left navigation pane, select **Users**, and confirm that all store employees in all stores have been added as users.</span></span>

<span data-ttu-id="321cf-132">La figura seguente mostra un esempio della pagina **Gestisci team** nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="321cf-132">The following illustration shows an example of the **Manage teams** page in the Teams admin center.</span></span>

![Esempio della pagina Gestisci team nell'interfaccia di amministrazione di Teams](media/Teams-FLW-Admin-Teams.png)

## <a name="upload-a-commerce-organizational-hierarchy-to-teams"></a><span data-ttu-id="321cf-134">Caricare una gerarchia organizzativa di Commerce in Teams</span><span class="sxs-lookup"><span data-stu-id="321cf-134">Upload a Commerce organizational hierarchy to Teams</span></span>
    
<span data-ttu-id="321cf-135">La gerarchia organizzativa di Commerce può essere utilizzata in Microsoft Teams per pubblicare le attività in tutti i negozi o in quelli selezionati che utilizzano la stessa struttura gerarchica.</span><span class="sxs-lookup"><span data-stu-id="321cf-135">The Commerce organizational hierarchy can be used in Microsoft Teams to publish tasks to all or selected stores that use the same hierarchy structure.</span></span>

<span data-ttu-id="321cf-136">Per caricare una gerarchia organizzativa di Commerce in Teams effettua le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="321cf-136">To upload a Commerce organizational hierarchy to Teams, follow these steps.</span></span>
    
1. <span data-ttu-id="321cf-137">In Commerce headquarters vai a **Retail e Commerce \> Impostazione canale \> Configurazione dell'integrazione di Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="321cf-137">In Commerce headquarters, go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="321cf-138">Seleziona **Scarica gerarchia di destinazione** e quindi seleziona **Punti vendita per regione** per scaricare un file CSV (valori delimitati da virgole) della gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="321cf-138">Select **Download targeting hierarchy**, and then select **Retail Stores by Region** to download a comma-separated values (CSV) file of the organizational hierarchy.</span></span>
1. <span data-ttu-id="321cf-139">Installa il modulo Microsoft Teams PowerShell seguendo i passaggi in [Installare Microsoft Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="321cf-139">Install the Microsoft Teams PowerShell module by following the steps in [Install Microsoft Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
1. <span data-ttu-id="321cf-140">Quando ti viene richiesto nella finestra Teams PowerShell, accedi utilizzando l'account amministratore per il tuo tenant Azure AD.</span><span class="sxs-lookup"><span data-stu-id="321cf-140">When you're prompted in the Teams PowerShell window, sign in by using the administrator account for your Azure AD tenant.</span></span>
1. <span data-ttu-id="321cf-141">Segui i passaggi in [Impostare la gerarchia di destinazione del tuo team](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy) per caricare il file CSV per la gerarchia di destinazione.</span><span class="sxs-lookup"><span data-stu-id="321cf-141">Follow the steps in [Set up your team targeting hierarchy](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy) to upload the CSV file for the targeting hierarchy.</span></span>

## <a name="verify-that-the-organizational-hierarchy-was-uploaded-to-teams"></a><span data-ttu-id="321cf-142">Verificare che la gerarchia organizzativa sia stata caricata in Teams</span><span class="sxs-lookup"><span data-stu-id="321cf-142">Verify that the organizational hierarchy was uploaded to Teams</span></span>

<span data-ttu-id="321cf-143">Per verificare che la gerarchia organizzativa sia stata caricata in Microsoft Teams, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="321cf-143">To verify that the organizational hierarchy was uploaded to Microsoft Teams, follow these steps.</span></span>

1. <span data-ttu-id="321cf-144">Accedi a Teams come responsabile delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="321cf-144">Sign in to Teams as a communications manager.</span></span>
1. <span data-ttu-id="321cf-145">Nel riquadro di spostamento a sinistra, seleziona **Attività di Planner**.</span><span class="sxs-lookup"><span data-stu-id="321cf-145">In the left navigation pane, select **Tasks by Planner**.</span></span>
1. <span data-ttu-id="321cf-146">Nella scheda **Elenchi pubblicati** crea un nuovo elenco con un'attività fittizia.</span><span class="sxs-lookup"><span data-stu-id="321cf-146">On the **Published lists** tab, create a new list that has a dummy task.</span></span>
1. <span data-ttu-id="321cf-147">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="321cf-147">Select **Publish**.</span></span> <span data-ttu-id="321cf-148">La gerarchia organizzativa deve apparire nella finestra di dialogo **Seleziona per chi pubblicare** come mostrato nell'esempio della figura seguente.</span><span class="sxs-lookup"><span data-stu-id="321cf-148">The organizational hierarchy should appear in the **Select who to publish to** dialog box, as shown in the example in the following illustration.</span></span>

![Esempio di una gerarchia organizzativa nella finestra di dialogo Seleziona per chi pubblicare](media/Microsoft-teams-verify-org-hierarchy.png)

## <a name="additional-resources"></a><span data-ttu-id="321cf-150">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="321cf-150">Additional resources</span></span>

[<span data-ttu-id="321cf-151">Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="321cf-151">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="321cf-152">Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="321cf-152">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="321cf-153">Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="321cf-153">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="321cf-154">Gestire i ruoli utente in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="321cf-154">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="321cf-155">Mappare negozi e team se ci sono team preesistenti in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="321cf-155">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="321cf-156">Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="321cf-156">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
