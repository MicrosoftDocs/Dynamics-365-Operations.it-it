--- 
title: Assegnare utenti a ruoli di sicurezza
description: Per accedere a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, agli utenti devono essere assegnati ruoli di sicurezza.
author: maertenm
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: c08c9ee27bef3ec8c51df558766f55d3ea4ac48a
ms.contentlocale: it-it
ms.lasthandoff: 09/11/2018

---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="d6303-103">Assegnare utenti a ruoli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d6303-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d6303-104">Per accedere a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, agli utenti devono essere assegnati ruoli di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d6303-104">To access Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, users must be assigned to security roles.</span></span> <span data-ttu-id="d6303-105">In questa procedura viene illustrato come gli amministratori di sistema possono assegnare utenti ai ruoli automaticamente, in base ai dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="d6303-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="d6303-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="d6303-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="d6303-107">Assegnare automaticamente utenti a ruoli</span><span class="sxs-lookup"><span data-stu-id="d6303-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="d6303-108">Passare ad Amministrazione sistema > Sicurezza > Assegna utenti a ruoli.</span><span class="sxs-lookup"><span data-stu-id="d6303-108">Go to System administration > Security > Assign users to roles.</span></span>
2. <span data-ttu-id="d6303-109">Nella struttura selezionare "Supervisore contabile".</span><span class="sxs-lookup"><span data-stu-id="d6303-109">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="d6303-110">Selezionare il ruolo per il quale si desidera configurare la regola.</span><span class="sxs-lookup"><span data-stu-id="d6303-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="d6303-111">In questo esempio selezionare Supervisore contabile.</span><span class="sxs-lookup"><span data-stu-id="d6303-111">In this example, select Accounting supervisor.</span></span>  
3. <span data-ttu-id="d6303-112">Fare clic su Aggiungi regola per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="d6303-112">Click Add rule to open the drop dialog.</span></span>
4. <span data-ttu-id="d6303-113">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="d6303-113">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d6303-114">Selezionare la query da usare per questa regola.</span><span class="sxs-lookup"><span data-stu-id="d6303-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="d6303-115">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d6303-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="d6303-116">Fare clic su Modifica query.</span><span class="sxs-lookup"><span data-stu-id="d6303-116">Click Edit query.</span></span>
    * <span data-ttu-id="d6303-117">Modificare la query, se necessario.</span><span class="sxs-lookup"><span data-stu-id="d6303-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="d6303-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d6303-118">Click OK.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="d6303-119">Escludere gli utenti dall'assegnazione automatica dei ruoli</span><span class="sxs-lookup"><span data-stu-id="d6303-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="d6303-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d6303-120">Close the page.</span></span>
2. <span data-ttu-id="d6303-121">Passare ad Amministrazione sistema > Sicurezza > Assegna utenti a ruoli.</span><span class="sxs-lookup"><span data-stu-id="d6303-121">Go to System administration > Security > Assign users to roles.</span></span>
3. <span data-ttu-id="d6303-122">Nella struttura selezionare "Supervisore contabile".</span><span class="sxs-lookup"><span data-stu-id="d6303-122">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="d6303-123">Selezionare un ruolo.</span><span class="sxs-lookup"><span data-stu-id="d6303-123">Select a role.</span></span> <span data-ttu-id="d6303-124">In questo esempio selezionare Supervisore contabile.</span><span class="sxs-lookup"><span data-stu-id="d6303-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="d6303-125">Fare clic su Assegna/escludi utenti manualmente.</span><span class="sxs-lookup"><span data-stu-id="d6303-125">Click Manually assign / exclude users.</span></span>
5. <span data-ttu-id="d6303-126">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d6303-126">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="d6303-127">Selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="d6303-127">Select a user.</span></span>  
6. <span data-ttu-id="d6303-128">Fare clic su Escludi da ruolo.</span><span class="sxs-lookup"><span data-stu-id="d6303-128">Click Exclude from role.</span></span>
    * <span data-ttu-id="d6303-129">Fare clic su Escludi da ruolo per escludere gli utenti selezionati dal ruolo.</span><span class="sxs-lookup"><span data-stu-id="d6303-129">Click Exclude from role to exclude the selected users from the role.</span></span> <span data-ttu-id="d6303-130">Per rimuovere le esclusioni, selezionare gli utenti per i quali si desidera rimuovere le esclusioni, quindi fare clic su Reimposta stato.</span><span class="sxs-lookup"><span data-stu-id="d6303-130">To remove exclusions, select the users that you want to remove exclusions for, and then click Reset status.</span></span> <span data-ttu-id="d6303-131">Quando si rimuove un'esclusione reimpostando lo stato dell'utente, il ruolo utente viene assegnato di nuovo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d6303-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="d6303-132">Tuttavia, l'utente non viene assegnato immediatamente al ruolo o non viene escluso dal ruolo quando si reimposta lo stato.</span><span class="sxs-lookup"><span data-stu-id="d6303-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="d6303-133">Invece, l'utente viene assegnato al ruolo o viene rimosso dal ruolo alla successiva esecuzione delle regole di assegnazione automatica dei ruoli.</span><span class="sxs-lookup"><span data-stu-id="d6303-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  


