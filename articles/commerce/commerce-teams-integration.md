---
title: Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams
description: Questo argomento presenta una panoramica dell'integrazione di Microsoft Dynamics 365 Commerce e Microsoft Teams.
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
ms.openlocfilehash: c22af9bf76818dd682b4147c3677cd1715e4cbf8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021991"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-overview"></a><span data-ttu-id="55bba-103">Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55bba-103">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="55bba-104">Questo argomento presenta una panoramica dell'integrazione di Microsoft Dynamics 365 Commerce e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="55bba-104">This topic presents an overview of Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="55bba-105">Dynamics 365 Commerce si integra con Teams per aiutare i clienti e i loro dipendenti a migliorare la produttività sincronizzando la gestione delle attività tra le due applicazioni.</span><span class="sxs-lookup"><span data-stu-id="55bba-105">Dynamics 365 Commerce is integrating with Teams to help customers and their employees improve productivity by synchronizing task management between the two applications.</span></span> <span data-ttu-id="55bba-106">La gestione delle attività semplice offerta dall'integrazione di Commerce e Teams consente ai responsabili dei negozi e ai dipendenti di creare elenchi di attività, assegnare attività a più negozi e tenere traccia dello stato delle attività nei negozi, da entrambe le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="55bba-106">The seamless task management that Commerce and Teams integration provides lets store managers and employees create task lists, assign tasks to multiple stores, and track the status of tasks across stores, from either application.</span></span>

<span data-ttu-id="55bba-107">L'integrazione di Commerce e Teams è disponibile a partire dalla versione 10.0.18 di Commerce.</span><span class="sxs-lookup"><span data-stu-id="55bba-107">Commerce and Teams integration is available as of the Commerce version 10.0.18 release.</span></span>

## <a name="key-features"></a><span data-ttu-id="55bba-108">Funzionalità principali</span><span class="sxs-lookup"><span data-stu-id="55bba-108">Key features</span></span>

<span data-ttu-id="55bba-109">Ecco alcune delle funzionalità principali fornite dall'integrazione di Commerce e Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="55bba-109">Here are some of the key features that the Commerce and Microsoft Teams integration provides:</span></span>

- <span data-ttu-id="55bba-110">Provisioning di Teams utilizzando le informazioni ben definite di Commerce, come la struttura organizzativa e le informazioni su negozi, lavoratori, autorizzazioni e contesto aziendale.</span><span class="sxs-lookup"><span data-stu-id="55bba-110">Provision Teams by taking advantage of well-defined information from Commerce, such as the organizational structure and information about stores, workers, permissions, and business context.</span></span>
- <span data-ttu-id="55bba-111">Sincronizzazione facile delle modifiche in corso (ad esempio, l'aggiunta di nuovi negozi o l'assunzione di nuovi dipendenti) tra Commerce e Teams, ma mantenendo Commerce come fonte principale dei dati della struttura organizzativa.</span><span class="sxs-lookup"><span data-stu-id="55bba-111">Easily synchronize ongoing changes (for example, the addition of new stores or hiring of new employees) between Commerce and Teams, but keep Commerce as the master source of organizational structure data.</span></span>
- <span data-ttu-id="55bba-112">Integrazione della gestione delle attività tra Commerce e Teams per aiutare i dipendenti del negozio, i gestori del negozio, i responsabili di area e i responsabili delle comunicazioni a gestire le attività da entrambe le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="55bba-112">Integrate task management between Commerce and Teams to help store workers, store managers, regional managers, and communications managers handle task management from either application.</span></span>

## <a name="prerequisites-for-using-integration-features"></a><span data-ttu-id="55bba-113">Prerequisiti per l'utilizzo delle funzionalità di integrazione</span><span class="sxs-lookup"><span data-stu-id="55bba-113">Prerequisites for using integration features</span></span>

<span data-ttu-id="55bba-114">I seguenti prerequisiti devono essere soddisfatti prima di poter iniziare a utilizzare le funzionalità di integrazione di Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="55bba-114">The following prerequisites must be in place before you can start to use Microsoft Teams integration features:</span></span>

- <span data-ttu-id="55bba-115">Licenza Microsoft 365 Business Standard (questa licenza include Teams).</span><span class="sxs-lookup"><span data-stu-id="55bba-115">Microsoft 365 Business Standard License (This license includes Teams.)</span></span>
- <span data-ttu-id="55bba-116">Account Azure Active Directory (Azure AD) per tutti i responsabili e i lavoratori del negozio</span><span class="sxs-lookup"><span data-stu-id="55bba-116">Azure Active Directory (Azure AD) accounts for all store managers and workers</span></span>
- <span data-ttu-id="55bba-117">Sistemi POS configurati con l'autenticazione Azure AD</span><span class="sxs-lookup"><span data-stu-id="55bba-117">Point of sale (POS) systems that are configured with Azure AD authentication</span></span>

## <a name="conceptual-architecture"></a><span data-ttu-id="55bba-118">Architettura concettuale</span><span class="sxs-lookup"><span data-stu-id="55bba-118">Conceptual architecture</span></span>

<span data-ttu-id="55bba-119">La figura seguente mostra l'architettura concettuale dell'integrazione di Dynamics 365 Commerce e Microsoft Teams, utilizzando un negozio di San Francisco come esempio.</span><span class="sxs-lookup"><span data-stu-id="55bba-119">The following illustration shows the conceptual architecture of Dynamics 365 Commerce and Microsoft Teams integration, using a San Francisco store as an example.</span></span> <span data-ttu-id="55bba-120">L'applicazione POS di Teams e Commerce utilizza Microsoft Planner come repository in modo che le attività pubblicate da Teams vengano visualizzate nell'applicazione POS e le attività ad hoc create dai responsabili del negozio nell'applicazione POS vengano visualizzate in Teams, garantendo un'esperienza di gestione delle attività fluida tra le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="55bba-120">Both Teams and the Commerce POS application use Microsoft Planner as a repository so that tasks published from Teams appear in the POS application and ad hoc tasks created by store managers in the POS application appear in Teams, resulting in a seamless task management experience between the applications.</span></span>    

![Architettura dell'integrazione di Commerce e Teams](media/d365-commerce-teams-integration-conceptual-architecture.png)

## <a name="additional-resources"></a><span data-ttu-id="55bba-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="55bba-122">Additional resources</span></span>

[<span data-ttu-id="55bba-123">Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55bba-123">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="55bba-124">Provisioning di Microsoft Teams da Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="55bba-124">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="55bba-125">Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="55bba-125">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="55bba-126">Gestire i ruoli utente in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55bba-126">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="55bba-127">Mappare negozi e team se ci sono team preesistenti in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55bba-127">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="55bba-128">Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55bba-128">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
