---
title: Creare gruppi di autorizzazioni POS
description: In questo argomento viene illustrato come creare un gruppo di autorizzazioni POS.
author: scott-tucker
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e6782c60aa659523775cc6c4eb1694430a4bf4f
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914808"
---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="31151-103">Creare gruppi di autorizzazioni POS</span><span class="sxs-lookup"><span data-stu-id="31151-103">Create POS permission groups</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="31151-104">In questo argomento viene illustrato come creare un gruppo di autorizzazioni POS.</span><span class="sxs-lookup"><span data-stu-id="31151-104">This topic explains how to create a POS permission group.</span></span> <span data-ttu-id="31151-105">La società di dati dimostrativi utilizzata per creare questa attività è USRT.</span><span class="sxs-lookup"><span data-stu-id="31151-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="31151-106">Questa attività è destinata al ruolo Responsabile operativo vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="31151-106">This task is intended for the Retail operations manager role.</span></span>

1. <span data-ttu-id="31151-107">Nel pannello di navigazione, andare a **Moduli > Vendita al dettaglio > Dipendenti > Gruppi di autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="31151-107">In the navigation pane, go to **Modules > Retail > Employees > Permission groups**.</span></span>
2. <span data-ttu-id="31151-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="31151-108">Select **New**.</span></span>
3. <span data-ttu-id="31151-109">Digitare un valore nel campo **ID gruppo di autorizzazioni POS**.</span><span class="sxs-lookup"><span data-stu-id="31151-109">In the **POS permission group ID** field, type a value.</span></span>
4. <span data-ttu-id="31151-110">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="31151-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="31151-111">Selezionare **Sì** nel campo **Visualizza voci orologio**.</span><span class="sxs-lookup"><span data-stu-id="31151-111">Select **Yes** in the **View time clock entries** field.</span></span> <span data-ttu-id="31151-112">È ora possibile abilitare o disabilitare le varie autorizzazioni per il gruppo di autorizzazioni POS.</span><span class="sxs-lookup"><span data-stu-id="31151-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="31151-113">Per alcune autorizzazioni è possibile impostare un valore che verrà utilizzato per valutare se l'utente POS può eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="31151-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span> <span data-ttu-id="31151-114">Questa guida attività abilita l'autorizzazione che può essere assegnata al cassiere.</span><span class="sxs-lookup"><span data-stu-id="31151-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="31151-115">Selezionare **Sì** nel campo **Consenti creazione ordine**.</span><span class="sxs-lookup"><span data-stu-id="31151-115">Select **Yes** in the **Allow create order** field.</span></span>
7. <span data-ttu-id="31151-116">Selezionare **Sì** nel campo **Consenti modifica ordine**.</span><span class="sxs-lookup"><span data-stu-id="31151-116">Select **Yes** in the **Allow edit order** field.</span></span>
8. <span data-ttu-id="31151-117">Selezionare **Sì** nel campo **Consenti recupero ordine**.</span><span class="sxs-lookup"><span data-stu-id="31151-117">Select **Yes** in the **Allow retrieve order** field.</span></span>
9. <span data-ttu-id="31151-118">Selezionare **Sì** nel campo **Consenti modifica password**.</span><span class="sxs-lookup"><span data-stu-id="31151-118">Select **Yes** in the **Allow password change** field.</span></span>
10. <span data-ttu-id="31151-119">Selezionare **Sì** nel campo **Consenti chiusura forzata**.</span><span class="sxs-lookup"><span data-stu-id="31151-119">Select **Yes** in the **Allow blind close** field.</span></span>
11. <span data-ttu-id="31151-120">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="31151-120">Select **Save**.</span></span> <span data-ttu-id="31151-121">Dopo aver salvato le modifiche, è necessario eseguire la programmazione di distribuzione del personale per applicare le modifiche ai canali di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="31151-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span> 
12. <span data-ttu-id="31151-122">Nel pannello di navigazione, andare a **Moduli > Risorse umane > Posizioni lavorative > Posizioni lavorative**.</span><span class="sxs-lookup"><span data-stu-id="31151-122">In the navigation pane, go to **Modules > Human resources > Jobs > Jobs**.</span></span>
13. <span data-ttu-id="31151-123">Quindi, verrà assegnato il gruppo di autorizzazioni POS a un processo.</span><span class="sxs-lookup"><span data-stu-id="31151-123">Next we will assign the POS permission group to a Job.</span></span> <span data-ttu-id="31151-124">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="31151-124">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="31151-125">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="31151-125">Select **Edit**.</span></span>
15. <span data-ttu-id="31151-126">Espandere la sezione **Classificazione mansione**.</span><span class="sxs-lookup"><span data-stu-id="31151-126">Expand the **Job classification** section.</span></span>
16. <span data-ttu-id="31151-127">Nel campo Gruppo di autorizzazioni POS immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="31151-127">In the POS permission group field, enter or select a value.</span></span> <span data-ttu-id="31151-128">Tutti i lavoratori nelle posizioni per questo processo utilizzeranno le impostazioni del gruppo di autorizzazioni POS a meno che le autorizzazioni POS del lavoratore siano state ignorate a livello di posizione.</span><span class="sxs-lookup"><span data-stu-id="31151-128">All Workers in Positions for this Job will use this POS permission group’s settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
17. <span data-ttu-id="31151-129">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="31151-129">Select **Save**.</span></span> <span data-ttu-id="31151-130">Dopo aver salvato le modifiche, è necessario eseguire la programmazione di distribuzione del personale per applicare le modifiche ai canali di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="31151-130">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  

