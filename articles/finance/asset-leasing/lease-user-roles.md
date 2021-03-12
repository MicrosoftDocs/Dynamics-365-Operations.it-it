---
title: Assegnare ruoli utente per il leasing
description: In questo argomento vengono descritti i ruoli di sicurezza utilizzati in Leasing cespiti. Spiega inoltre come assegnare gli utenti a quei ruoli.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: df23e219f5bd859b0072785dfd5f7a0ec63f540e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995395"
---
# <a name="assign-lease-user-roles"></a><span data-ttu-id="42bd2-104">Assegnare ruoli utente per il leasing</span><span class="sxs-lookup"><span data-stu-id="42bd2-104">Assign lease user roles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="42bd2-105">In questo argomento vengono descritti i ruoli di sicurezza utilizzati in Leasing cespiti.</span><span class="sxs-lookup"><span data-stu-id="42bd2-105">This topic describes the security roles that are used in Asset leasing.</span></span> <span data-ttu-id="42bd2-106">Spiega inoltre come assegnare gli utenti a quei ruoli.</span><span class="sxs-lookup"><span data-stu-id="42bd2-106">It also explains how to assign users to those roles.</span></span>

<span data-ttu-id="42bd2-107">Tre ruoli utente differenziano l'accesso in Leasing cespiti.</span><span class="sxs-lookup"><span data-stu-id="42bd2-107">Three user roles differentiate access in Asset leasing.</span></span> <span data-ttu-id="42bd2-108">Un ruolo è appropriato per mantenere i leasing, uno è appropriato per visualizzare i leasing e uno è appropriato per svolgere le funzioni di addetto al leasing.</span><span class="sxs-lookup"><span data-stu-id="42bd2-108">One role is appropriate for maintaining leases, one is appropriate for viewing leases, and one is appropriate for performing a lease clerk's duties.</span></span> <span data-ttu-id="42bd2-109">Ogni ruolo dispone di autorizzazioni specifiche per tutte le pagine di leasing e ciascuno consente agli utenti di visualizzare, creare, modificare o eliminare i leasing, in base alle loro mansioni lavorative.</span><span class="sxs-lookup"><span data-stu-id="42bd2-109">Each role has specific permissions for all lease pages, and each lets users view, create, edit, or delete leases, according to their job duties.</span></span>

| <span data-ttu-id="42bd2-110">Ruolo</span><span class="sxs-lookup"><span data-stu-id="42bd2-110">Role</span></span>           | <span data-ttu-id="42bd2-111">descrizione</span><span class="sxs-lookup"><span data-stu-id="42bd2-111">Description</span></span> |
|----------------|-------------|
| <span data-ttu-id="42bd2-112">Gestire leasing</span><span class="sxs-lookup"><span data-stu-id="42bd2-112">Maintain Lease</span></span> | <span data-ttu-id="42bd2-113">Gli utenti in questo ruolo possono aggiungere, modificare, eliminare e visualizzare i leasing.</span><span class="sxs-lookup"><span data-stu-id="42bd2-113">Users in this role can add, edit, delete, and view leases.</span></span> <span data-ttu-id="42bd2-114">Questo ruolo è progettato per gli utenti giornalieri le cui attività includono la creazione e la registrazione di voci di giornale mensili e l'aggiunta di nuovi leasing.</span><span class="sxs-lookup"><span data-stu-id="42bd2-114">This role is designed for daily users whose tasks include creating and posting monthly journal entries and adding new leases.</span></span> <span data-ttu-id="42bd2-115">Questo ruolo fornisce l'accesso a tutte le funzionalità di Leasing cespiti.</span><span class="sxs-lookup"><span data-stu-id="42bd2-115">This role gives access to all Asset leasing functionality.</span></span> |
| <span data-ttu-id="42bd2-116">Visualizzare leasing</span><span class="sxs-lookup"><span data-stu-id="42bd2-116">View Lease</span></span>     | <span data-ttu-id="42bd2-117">Gli utenti in questo ruolo possono solo visualizzare i record di leasing, gli scadenziari ed eseguire report.</span><span class="sxs-lookup"><span data-stu-id="42bd2-117">Users in this role can only view lease records, schedules, and run reports.</span></span> <span data-ttu-id="42bd2-118">Non possono creare nuovi leasing, modificare i leasing esistenti o creare scritture contabili a fronte di leasing.</span><span class="sxs-lookup"><span data-stu-id="42bd2-118">They can't create new leases, edit existing leases, or create journal entries against leases.</span></span> <span data-ttu-id="42bd2-119">Il ruolo è progettato per gli utenti che devono solo visualizzare i leasing, le pianificazioni dei leasing e le transazioni che si verificano a fronte di tali leasing.</span><span class="sxs-lookup"><span data-stu-id="42bd2-119">The role is designed for users who just have to view leases, lease schedules, and the transactions that occur against those leases.</span></span> |
| <span data-ttu-id="42bd2-120">Addetto al leasing</span><span class="sxs-lookup"><span data-stu-id="42bd2-120">Lease Clerk</span></span>    | <span data-ttu-id="42bd2-121">Gli utenti in questo ruolo possono solo creare nuovi leasing.</span><span class="sxs-lookup"><span data-stu-id="42bd2-121">Users in this role can only create new leases.</span></span> <span data-ttu-id="42bd2-122">Non possono modificare o eliminare leasing esistenti, visualizzare pianificazioni leasing o registrare scritture contabili di leasing.</span><span class="sxs-lookup"><span data-stu-id="42bd2-122">They can't edit or delete existing leases, view lease schedules, or post leasing journal entries.</span></span> <span data-ttu-id="42bd2-123">Questo ruolo è progettato per gli utenti che lavorano con capacità di immissione dati.</span><span class="sxs-lookup"><span data-stu-id="42bd2-123">This role is designed for users who work in a data entry capacity.</span></span> |

<span data-ttu-id="42bd2-124">Attieniti alla seguente procedura per assegnare gli utenti ai ruoli utilizzati in Leasing cespiti.</span><span class="sxs-lookup"><span data-stu-id="42bd2-124">Follow these steps to assign users to the roles that are used in Asset leasing.</span></span>

1. <span data-ttu-id="42bd2-125">Passa ad **Amministrazione sistema \> Sicurezza \> Assegna utenti a ruoli**.</span><span class="sxs-lookup"><span data-stu-id="42bd2-125">Go to **System administration \> Security \> Assign users to roles**.</span></span>
2. <span data-ttu-id="42bd2-126">Seleziona il ruolo **Mantenere il leasing**, **Addetto al leasing** o **Visualizzare il leasing**, quindi seleziona **Assegna/escludi utenti manualmente**.</span><span class="sxs-lookup"><span data-stu-id="42bd2-126">Select the **Maintain lease**, **Lease clerk**, or **View lease** role, and then select **Manually assign/exclude users**.</span></span>
3. <span data-ttu-id="42bd2-127">Seleziona l'utente a cui assegnare il ruolo, quindi seleziona **Assegna a ruolo**.</span><span class="sxs-lookup"><span data-stu-id="42bd2-127">Select the user to assign to the role, and then select **Assign to role**.</span></span>
