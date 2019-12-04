---
title: Assegnare gli utenti ai ruoli di sicurezza
description: Per accedere alle app Finance and Operations, è necessario assegnare utenti a ruoli di sicurezza.
author: ChrisGarty
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4f4ef4535de9e371829c2d86d4fdc1400510c7b
ms.sourcegitcommit: 6aa74f66f1abd3a7977050a5339b0b17e62ff053
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "2807998"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="5e0b5-103">Assegnare gli utenti ai ruoli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="5e0b5-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5e0b5-104">Per utilizzare altri elementi oltre alle capacità comuni, è necessario assegnare utenti a ruoli di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-104">To use anything other than common capabilities, users must be assigned to security roles.</span></span> <span data-ttu-id="5e0b5-105">In questa procedura viene illustrato come gli amministratori di sistema possono assegnare utenti ai ruoli automaticamente, in base ai dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-105">This procedure explains how system administrators can automatically assign users to roles, based on business data.</span></span> 

## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="5e0b5-106">Assegnare automaticamente utenti a ruoli</span><span class="sxs-lookup"><span data-stu-id="5e0b5-106">Automatically assign users to roles</span></span>
1. <span data-ttu-id="5e0b5-107">Passare **Pannello di navigazione > Moduli > Amministrazione sistema > Sicurezza > Assegna utenti a ruoli**.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-107">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="5e0b5-108">Nella struttura selezionare "Supervisore contabile".</span><span class="sxs-lookup"><span data-stu-id="5e0b5-108">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="5e0b5-109">Selezionare il ruolo per il quale si desidera configurare la regola.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-109">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="5e0b5-110">In questo esempio selezionare Supervisore contabile.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-110">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="5e0b5-111">Fare clic su **Aggiungi regola** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-111">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="5e0b5-112">Nell'elenco **Seleziona query**, trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-112">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="5e0b5-113">Selezionare la query da usare per questa regola.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-113">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="5e0b5-114">Nell'elenco **Nome regola di appartenenza**, fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-114">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="5e0b5-115">Fare clic su **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-115">Click **Edit query**.</span></span> <span data-ttu-id="5e0b5-116">Modificare la query, se necessario.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-116">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="5e0b5-117">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-117">Click **OK**.</span></span>
8. <span data-ttu-id="5e0b5-118">Fare clic su **Esegui assegnazione automatica ruoli**.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-118">Click **Run automatic role assignment**.</span></span>
9. <span data-ttu-id="5e0b5-119">Passare a **Pannello di navigazione > Moduli > Amministrazione sistema > Utenti > Utenti** (idealmente in una scheda separata del browser).</span><span class="sxs-lookup"><span data-stu-id="5e0b5-119">Go to **Navigation pane > Modules > System administration > Users > Users** (ideally in a separate browser tab).</span></span>
10. <span data-ttu-id="5e0b5-120">Esaminare i ruoli assegnati ai vari utenti per confermare che la query di assegnazione ruolo è corretta.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-120">Review the roles assigned to various users to confirm that the role assignment query was correct.</span></span> <span data-ttu-id="5e0b5-121">Modificare e rieseguire se necessario.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-121">Adjust and re-run if needed.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="5e0b5-122">Escludere gli utenti dall'assegnazione automatica dei ruoli</span><span class="sxs-lookup"><span data-stu-id="5e0b5-122">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="5e0b5-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-123">Close the page.</span></span>
2. <span data-ttu-id="5e0b5-124">Passare **Pannello di navigazione > Moduli > Amministrazione sistema > Sicurezza > Assegna utenti a ruoli**.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-124">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="5e0b5-125">Nella struttura selezionare "Supervisore contabile".</span><span class="sxs-lookup"><span data-stu-id="5e0b5-125">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="5e0b5-126">Selezionare un ruolo.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-126">Select a role.</span></span> <span data-ttu-id="5e0b5-127">In questo esempio selezionare Supervisore contabile.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-127">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="5e0b5-128">Nel menu **Utenti assegnati al ruolo**, selezionare **Assegna/escludi utenti manualmente**.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-128">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="5e0b5-129">Nell'elenco **Assegna o escludi utenti da ruolo**, contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-129">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="5e0b5-130">Selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-130">Select a user.</span></span>  
6. <span data-ttu-id="5e0b5-131">Nel **Riquadro azioni**, selezionare **Escludi da ruolo**.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-131">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="5e0b5-132">Fare clic su **Escludi da ruolo** per escludere gli utenti selezionati dal ruolo.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-132">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="5e0b5-133">Per rimuovere le esclusioni, selezionare gli utenti per i quali si desidera rimuovere le esclusioni, quindi fare clic su **Reimposta stato**.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-133">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="5e0b5-134">Quando si rimuove un'esclusione reimpostando lo stato dell'utente, il ruolo utente viene assegnato di nuovo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-134">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="5e0b5-135">Tuttavia, l'utente non viene assegnato immediatamente al ruolo o non viene escluso dal ruolo quando si reimposta lo stato.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-135">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="5e0b5-136">Invece, l'utente viene assegnato al ruolo o viene rimosso dal ruolo alla successiva esecuzione delle regole di assegnazione automatica dei ruoli.</span><span class="sxs-lookup"><span data-stu-id="5e0b5-136">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
