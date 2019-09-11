---
title: Creare nuovi utenti
description: Gli utenti sono dipendenti interni dell'organizzazione o clienti e fornitori esterni, che richiedono l'accesso al sistema per l'esecuzione dei processi.
author: maertenm
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a542ece226750330262e0c44427e5654fa4f6369
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916486"
---
# <a name="create-new-users"></a><span data-ttu-id="eb778-103">Creare nuovi utenti</span><span class="sxs-lookup"><span data-stu-id="eb778-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="eb778-104">Gli utenti sono dipendenti interni dell'organizzazione o clienti e fornitori esterni, che richiedono l'accesso al sistema per l'esecuzione dei processi.</span><span class="sxs-lookup"><span data-stu-id="eb778-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="eb778-105">Gli amministratori di sistema possono completare questa procedura per aggiungere gli utenti al sistema.</span><span class="sxs-lookup"><span data-stu-id="eb778-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="eb778-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="eb778-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="eb778-107">Aggiungere un nuovo utente</span><span class="sxs-lookup"><span data-stu-id="eb778-107">Add a new user</span></span>
1. <span data-ttu-id="eb778-108">Andare a **Pannello di navigazione > Moduli > Amministrazione sistema > Utenti > Utenti**.</span><span class="sxs-lookup"><span data-stu-id="eb778-108">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="eb778-109">Fare clic su **Nuova** nel **riquadro azioni**.</span><span class="sxs-lookup"><span data-stu-id="eb778-109">On the **Action pane**, click **New**.</span></span>
3. <span data-ttu-id="eb778-110">Digitare un valore nel campo **ID utente**.</span><span class="sxs-lookup"><span data-stu-id="eb778-110">In the **User ID** field, type a value.</span></span> <span data-ttu-id="eb778-111">Immettere un identificatore univoco per l'utente.</span><span class="sxs-lookup"><span data-stu-id="eb778-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="eb778-112">È necessario un ID utente.</span><span class="sxs-lookup"><span data-stu-id="eb778-112">A user ID is required.</span></span>  
4. <span data-ttu-id="eb778-113">Digitare un valore nel campo **Utente**.</span><span class="sxs-lookup"><span data-stu-id="eb778-113">In the **User name** field, type a value.</span></span> <span data-ttu-id="eb778-114">Immettere il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="eb778-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="eb778-115">Digitare un valore nel campo **Dominio**.</span><span class="sxs-lookup"><span data-stu-id="eb778-115">In the **Domain** field, type a value.</span></span> <span data-ttu-id="eb778-116">Immettere il dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="eb778-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="eb778-117">Digitare un valore nel campo **Alias**.</span><span class="sxs-lookup"><span data-stu-id="eb778-117">In the **Alias** field, type a value.</span></span> <span data-ttu-id="eb778-118">Immettere l'alias dell'utente.</span><span class="sxs-lookup"><span data-stu-id="eb778-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="eb778-119">Nel campo **Società** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="eb778-119">In the **Company** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="eb778-120">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="eb778-120">In the list, find and select the desired record.</span></span> 
9. <span data-ttu-id="eb778-121">Nella sezione **Ruoli utente**, fare clic su **Assegna ruoli**.</span><span class="sxs-lookup"><span data-stu-id="eb778-121">In the **User's roles** section, click **Assign roles**.</span></span>
10. <span data-ttu-id="eb778-122">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="eb778-122">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="eb778-123">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb778-123">Click **OK**.</span></span>
12. <span data-ttu-id="eb778-124">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="eb778-124">Click **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="eb778-125">Importa utenti</span><span class="sxs-lookup"><span data-stu-id="eb778-125">Import users</span></span>
1. <span data-ttu-id="eb778-126">Nel **riquadro azioni** fare clic su **Importa utenti**.</span><span class="sxs-lookup"><span data-stu-id="eb778-126">On the **Action pane**, click **Import users**.</span></span>
2. <span data-ttu-id="eb778-127">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="eb778-127">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="eb778-128">Fare clic su **Importa utenti**.</span><span class="sxs-lookup"><span data-stu-id="eb778-128">Click **Import users**.</span></span>
4. <span data-ttu-id="eb778-129">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="eb778-129">Click **Close**.</span></span>

