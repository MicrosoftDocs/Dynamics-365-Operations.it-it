---
title: Gestire utenti e ruoli di e-Commerce
description: In questo argomento viene descritto come concedere agli utenti l'accesso all'ambiente di creazione del sito di Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23977ddc8ef67389d088ca52c1a1bc6a9b2f7fb4
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697683"
---
# <a name="manage-e-commerce-users-and-roles"></a><span data-ttu-id="9b04a-103">Gestire utenti e ruoli di e-Commerce</span><span class="sxs-lookup"><span data-stu-id="9b04a-103">Manage e-Commerce users and roles</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="9b04a-104">In questo argomento viene descritto come concedere agli utenti l'accesso all'ambiente di creazione del sito di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9b04a-104">This topic explains how to grant users access to the authoring environment for your Microsoft Dynamics 365 Commerce site.</span></span>

<span data-ttu-id="9b04a-105">Per consentire il controllo dell'accesso utente e concedere agli utenti l'autorizzazione di eseguire specifiche attività, l'ambiente di creazione di siti utilizza gruppi di sicurezza creati in Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="9b04a-105">To help control user access and grant users permission to perform specific tasks, the site authoring environment uses security groups that you create in Microsoft Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="9b04a-106">Innanzitutto si assegna un gruppo di sicurezza nuovo o esistente da Azure AD a ogni ruolo nell'ambiente di creazione.</span><span class="sxs-lookup"><span data-stu-id="9b04a-106">You first assign a new or existing security group from Azure AD to each role in the authoring environment.</span></span> <span data-ttu-id="9b04a-107">Quindi si concedono o si revocano le autorizzazioni per singoli utenti aggiungendo quegli utenti a un gruppo di sicurezza appropriato o rimuovendoli da un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9b04a-107">You then grant or revoke permissions for individual users by either adding those users to an appropriate security group or removing them from a security group.</span></span>

## <a name="overview-of-roles-in-the-authoring-environment"></a><span data-ttu-id="9b04a-108">Panoramica dei ruoli nell'ambiente di creazione</span><span class="sxs-lookup"><span data-stu-id="9b04a-108">Overview of roles in the authoring environment</span></span>

<span data-ttu-id="9b04a-109">L'ambiente di creazione di Dynamics 365 for Commerce supporta i ruoli seguenti.</span><span class="sxs-lookup"><span data-stu-id="9b04a-109">The Dynamics 365 for Commerce authoring environment supports the following roles.</span></span>

| <span data-ttu-id="9b04a-110">Ruolo</span><span class="sxs-lookup"><span data-stu-id="9b04a-110">Role</span></span>                 | <span data-ttu-id="9b04a-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b04a-111">Description</span></span> |
|----------------------|-------------|
| <span data-ttu-id="9b04a-112">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="9b04a-112">System Administrator</span></span> | <span data-ttu-id="9b04a-113">Gli utenti con questo ruolo hanno tutti i privilegi per tutti gli strumenti e tutte le valutazioni e recensioni.</span><span class="sxs-lookup"><span data-stu-id="9b04a-113">Users who have this role have all privileges for all tools, and for all ratings and reviews.</span></span> <span data-ttu-id="9b04a-114">Possono inoltre creare siti.</span><span class="sxs-lookup"><span data-stu-id="9b04a-114">They can also create sites.</span></span> |
| <span data-ttu-id="9b04a-115">Amministratore</span><span class="sxs-lookup"><span data-stu-id="9b04a-115">Administrator</span></span>   | <span data-ttu-id="9b04a-116">Gli utenti con questo ruolo hanno tutti i privilegi per tutti gli strumenti e per il servizio Valutazioni e recensioni in una determinata struttura del sito.</span><span class="sxs-lookup"><span data-stu-id="9b04a-116">Users who have this role have all privileges for all tools and RnR in a given site structure.</span></span> |
| <span data-ttu-id="9b04a-117">Produttore Web</span><span class="sxs-lookup"><span data-stu-id="9b04a-117">Web Producer</span></span>         | <span data-ttu-id="9b04a-118">Gli utenti con questo ruolo possono creare pagine, frammenti e modelli, caricare e gestire asset e arricchire prodotti e categorie.</span><span class="sxs-lookup"><span data-stu-id="9b04a-118">Users who have this role can create pages, fragments and templates, upload and manage assets, and enrich products and categories.</span></span> |
| <span data-ttu-id="9b04a-119">Lettore</span><span class="sxs-lookup"><span data-stu-id="9b04a-119">Reader</span></span>               | <span data-ttu-id="9b04a-120">Gli utenti con questo ruolo possono visualizzare pagine, modelli, asset, frammenti, layout e impostazioni, ma non apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="9b04a-120">Users who have this role can view pages, templates, assets, fragments, layouts and settings, but may not make changes.</span></span> |
| <span data-ttu-id="9b04a-121">Moderatore valutazioni e recensioni</span><span class="sxs-lookup"><span data-stu-id="9b04a-121">RnR Moderator</span></span>        | <span data-ttu-id="9b04a-122">Gli utenti con questo ruolo possono moderare le recensioni sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="9b04a-122">Users who have this role can moderate product reviews.</span></span> |

## <a name="system-administrator-role"></a><span data-ttu-id="9b04a-123">Ruolo Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="9b04a-123">System Administrator role</span></span>

<span data-ttu-id="9b04a-124">Quando si esegue il provisioning di Dynamics 365 Commerce nell'ambiente di Microsoft Dynamics Lifecycle Services (LCS), viene richiesto di fornire un gruppo di sicurezza per il ruolo **Amministratore di sistema**.</span><span class="sxs-lookup"><span data-stu-id="9b04a-124">When you provision Dynamics 365 Commerce in the Microsoft Dynamics Lifecycle Services (LCS) environment, you're asked to provide a security group for the **System Administrator** role.</span></span> <span data-ttu-id="9b04a-125">Questo ruolo viene applicato automaticamente a tutti i siti creati nell'ambiente che si sta configurando.</span><span class="sxs-lookup"><span data-stu-id="9b04a-125">This role is then automatically applied to all sites that you create in the environment that you're configuring.</span></span> <span data-ttu-id="9b04a-126">Il gruppo di sicurezza per questo ruolo può essere aggiornato solo in LCS.</span><span class="sxs-lookup"><span data-stu-id="9b04a-126">The security group for this role can be updated only in LCS.</span></span> <span data-ttu-id="9b04a-127">Nella pagina **Amministrazione sito** di tutti i siti, viene visualizzato come di sola lettura e solo a scopo informativo.</span><span class="sxs-lookup"><span data-stu-id="9b04a-127">On the **Site Administration** page for all sites, it appears as read-only and is for informational purposes only.</span></span>

## <a name="administrator-role"></a><span data-ttu-id="9b04a-128">Ruolo Amministratore</span><span class="sxs-lookup"><span data-stu-id="9b04a-128">Administrator role</span></span>

<span data-ttu-id="9b04a-129">Quando si crea un nuovo sito in Commerce, viene richiesto di fornire un gruppo di sicurezza per il ruolo **Amministratore**.</span><span class="sxs-lookup"><span data-stu-id="9b04a-129">When you create a new site in Commerce, you're asked to provide a security group for the **Administrator** role.</span></span> <span data-ttu-id="9b04a-130">Vedere la tabella precedente in questo argomento per una panoramica delle autorizzazioni concesse da questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="9b04a-130">See the table earlier in this topic for an overview of the permissions that this role grants.</span></span>

## <a name="add-or-update-security-groups"></a><span data-ttu-id="9b04a-131">Aggiungere o aggiornare gruppi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="9b04a-131">Add or update security groups</span></span>

<span data-ttu-id="9b04a-132">Dopo la creazione del sito, solo gli utenti nei gruppi di sicurezza associati ai ruoli **Amministratore** e **Amministratore di sistema** possono accedere all'ambiente di creazione per quel sito.</span><span class="sxs-lookup"><span data-stu-id="9b04a-132">After your site is created, only users who are in the security groups that are associated with the **System Administrator** and **Administrator** roles can access the authoring environment for that site.</span></span> <span data-ttu-id="9b04a-133">Per assegnare utenti ai ruoli **Produttore Web**, **Moderatore valutazioni e recensioni** e **Lettore**, è necessario assegnare gruppi di sicurezza a tali ruoli.</span><span class="sxs-lookup"><span data-stu-id="9b04a-133">To assign users to the **Web Producer**, **RnR Moderator**, and **Reader** roles, you must assign security groups to those roles.</span></span> <span data-ttu-id="9b04a-134">Per aggiungere un gruppo di sicurezza a un ruolo o per aggiornare un gruppo di sicurezza correntemente assegnato a un ruolo, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="9b04a-134">To add a security group to a role, or to update a security group that is currently assigned to a role, follow these steps.</span></span>

1. <span data-ttu-id="9b04a-135">Accedere al sito che si intende aggiornare.</span><span class="sxs-lookup"><span data-stu-id="9b04a-135">Go to the site that you want to update.</span></span>
1. <span data-ttu-id="9b04a-136">In **Gestione sito**, aprire la pagina **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="9b04a-136">In **Site management**, open the **Security** page.</span></span>
1. <span data-ttu-id="9b04a-137">Selezionare il ruolo da modificare.</span><span class="sxs-lookup"><span data-stu-id="9b04a-137">Select the role to modify.</span></span>
1. <span data-ttu-id="9b04a-138">Aggiungere gruppi di sicurezza a ruoli o rimuovere gruppi di sicurezza da ruoli.</span><span class="sxs-lookup"><span data-stu-id="9b04a-138">Add security groups to roles, or remove security groups from roles.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9b04a-139">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9b04a-139">Additional resources</span></span>

[<span data-ttu-id="9b04a-140">Aggiungere codice script nelle pagine del sito per supportare la telemetria</span><span class="sxs-lookup"><span data-stu-id="9b04a-140">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="9b04a-141">Considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito</span><span class="sxs-lookup"><span data-stu-id="9b04a-141">Search engine optimization (SEO) considerations for your site</span></span>](search-engine-optimization-considerations.md)

[<span data-ttu-id="9b04a-142">Gestire i criteri di sicurezza del contenuto (CSP)</span><span class="sxs-lookup"><span data-stu-id="9b04a-142">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
