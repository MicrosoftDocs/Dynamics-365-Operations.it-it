---
title: Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams
description: In questo argomento vengono fornite risposte alle domande frequenti relative all'integrazione di Microsoft Dynamics 365 Commerce e Microsoft Teams.
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
ms.openlocfilehash: bf9aebb1c8ba7cf4fee3f0471a10872de1e23ce6
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908858"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a><span data-ttu-id="b0c3b-103">Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b0c3b-103">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b0c3b-104">In questo argomento vengono fornite risposte alle domande frequenti relative all'integrazione di Microsoft Dynamics 365 Commerce e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-104">This topic provides answers to frequently asked questions regarding Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a><span data-ttu-id="b0c3b-105">Chi nel negozio diventa proprietario di un team durante il provisioning di Teams da Commerce?</span><span class="sxs-lookup"><span data-stu-id="b0c3b-105">Who in the store becomes an owner of a team while provisioning Teams from Commerce?</span></span> 

<span data-ttu-id="b0c3b-106">Tutti i responsabili dei negozi vengono aggiunti automaticamente come proprietari al gruppo del team corrispondente in modo che possano eseguire operazioni come l'aggiunta di un canale privato e l'aggiunta o l'eliminazione di membri.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-106">All store managers are automatically added as owners to the corresponding team group so that they can perform operations such as adding a private channel and adding or deleting members.</span></span> 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a><span data-ttu-id="b0c3b-107">Come si assegna il ruolo di "responsabile delle comunicazioni" a un dipendente in Commerce headquarters?</span><span class="sxs-lookup"><span data-stu-id="b0c3b-107">How do I assign the "communications manager" role to an employee in Commerce headquarters?</span></span> 

<span data-ttu-id="b0c3b-108">I responsabili della comunicazione in Microsoft Teams hanno la capacità di creare e pubblicare elenchi di attività.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-108">Communication managers in Microsoft Teams have the ability to create and publish task lists.</span></span> <span data-ttu-id="b0c3b-109">I dipendenti dell'organizzazione che devono diventare responsabili della comunicazione devono avere il ruolo di "responsabile attività di vendita al dettaglio" assegnato loro in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-109">Organization employees who need to become communication managers must have the "retail task manager" role assigned to them in Commerce headquarters.</span></span>

<span data-ttu-id="b0c3b-110">Per assegnare il ruolo di responsabile dell'attività di vendita al dettaglio a un dipendente in Commerce headquarters, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-110">To assign the retail task manager role to an employee in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="b0c3b-111">Passare a **Retail e Commerce \> Dipendenti \> Utenti**.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-111">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="b0c3b-112">Selezionare un dipendente.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-112">Select an employee.</span></span>
1. <span data-ttu-id="b0c3b-113">Nella scheda dettaglio **Ruoli utente**, selezionare **Assegna ruoli**.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-113">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="b0c3b-114">Nella finestra di dialogo **Assegna ruoli all'utente** selezionare il ruolo **Responsabile attività vendita al dettaglio**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-114">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a><span data-ttu-id="b0c3b-115">Come faccio a rendere disponibile una gerarchia organizzativa specifica per il caricamento in Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="b0c3b-115">How do I make a specific organization hierarchy available to upload into Microsoft Teams?</span></span>

<span data-ttu-id="b0c3b-116">In Commerce headquarters, la gerarchia di ogni organizzazione è associata a uno o più scopi.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-116">In Commerce headquarters, every organization's hierarchy is associated with one or more purposes.</span></span> <span data-ttu-id="b0c3b-117">Assicurati che la gerarchia in cui desideri eseguire il provisioning in Microsoft Teams abbia lo scopo **Report per vendita al dettaglio** ad essa associato, come mostrato nella seguente immagine di esempio.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-117">Make sure the hierarchy that you want to provision into Microsoft Teams has the **Retail reporting** purpose associated with it, as shown in the following example image.</span></span> 

![Esempio di scopo della gerarchia organizzativa in Commerce headquarters](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a><span data-ttu-id="b0c3b-119">Come si consente ai lavoratori dei punti vendita al dettaglio di accedere al POS di Commerce utilizzando Azure Active Directory (Azure AD)?</span><span class="sxs-lookup"><span data-stu-id="b0c3b-119">How do I enable retail store workers to sign in to Commerce point of sale (POS) using Azure Active Directory (Azure AD)?</span></span>

<span data-ttu-id="b0c3b-120">Per informazioni su come configurare l'esperienza di accesso a Commerce POS per utilizzare l'autenticazione Azure AD, vedi [Abilitare l'autenticazione Azure Active Directory per l'accesso al POS](aad-pos-logon.md).</span><span class="sxs-lookup"><span data-stu-id="b0c3b-120">For information about how to configure the Commerce POS sign-in experience to use Azure AD authentication, see [Enable Azure Active Directory authentication for POS sign-in](aad-pos-logon.md).</span></span>

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a><span data-ttu-id="b0c3b-121">Come faccio a mappare i negozi e i team corrispondenti in Commerce headquarters se la mia organizzazione ha già creato team in Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="b0c3b-121">How do I map stores and corresponding teams in Commerce headquarters if my organization has already created teams in Microsoft Teams?</span></span>

<span data-ttu-id="b0c3b-122">Per informazioni su come mappare negozi e team se sono presenti team preesistenti, vedi [Mappare negozi e team corrispondenti se l'organizzazione ha team preesistenti in Microsoft Teams](map-stores-existing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b0c3b-122">For information on how to map stores and teams if there are pre-existing teams, see [Map stores and corresponding teams if your organization has pre-existing teams in Microsoft Teams](map-stores-existing-teams.md).</span></span>

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a><span data-ttu-id="b0c3b-123">Come si cancella il token dell'API Microsoft Graph archiviato nell'archiviazione della sessione?</span><span class="sxs-lookup"><span data-stu-id="b0c3b-123">How do I clear the Microsoft Graph API token stored in the session storage?</span></span>

<span data-ttu-id="b0c3b-124">Un utente che ha effettuato l'accesso al POS con un account Azure Active Directory (Azure AD) deve disconnettersi dal POS o chiudere l'applicazione per cancellare l'archiviazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-124">A user who has signed in to the point of sale (POS) with an Azure Active Directory (Azure AD) account should sign out from the POS or close the application to clear the session storage.</span></span> 

> [!TIP]
> <span data-ttu-id="b0c3b-125">Una procedura consigliata è quella di chiedere sempre ai dipendenti del negozio di bloccare il terminale POS o di disconnettersi da una sessione quando non utilizzano il terminale.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-125">A recommended best practice is to always have store workers lock the POS terminal or sign out from a session when not using the terminal.</span></span> 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a><span data-ttu-id="b0c3b-126">Cosa succede se un negozio non ha responsabili del negozio?</span><span class="sxs-lookup"><span data-stu-id="b0c3b-126">What happens if a store doesn't have store managers?</span></span>

<span data-ttu-id="b0c3b-127">Se un negozio non ha responsabili, non verrà creato un gruppo di team per il negozio o in Teams.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-127">If a store doesn't have managers, a team group will not be created for the store or in Teams.</span></span> 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a><span data-ttu-id="b0c3b-128">Cosa succede se un responsabile del negozio lascia l'azienda?</span><span class="sxs-lookup"><span data-stu-id="b0c3b-128">What happens if a store manager leaves the company?</span></span>

<span data-ttu-id="b0c3b-129">Chiunque abbia il ruolo di proprietario può aggiungere un nuovo responsabile del negozio in Commerce headquarters ed eseguire il reprovisioning dei team in modo che il nuovo responsabile disponga dei privilegi necessari in Teams per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="b0c3b-129">Anyone with the owner role can add a new store manager in Commerce headquarters and reprovision Teams so that the new manager will have the necessary privileges in Teams for the group.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="b0c3b-130">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b0c3b-130">Additional resources</span></span>

[<span data-ttu-id="b0c3b-131">Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b0c3b-131">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="b0c3b-132">Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b0c3b-132">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="b0c3b-133">Provisioning di Microsoft Teams da Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="b0c3b-133">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="b0c3b-134">Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="b0c3b-134">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="b0c3b-135">Gestire i ruoli utente in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b0c3b-135">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="b0c3b-136">Mappare negozi e team se ci sono team preesistenti in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b0c3b-136">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)
