--- 
title: " Creare gruppi di autorizzazioni POS"
description: In questa procedura vengono descritti i passaggi per creare un gruppo di autorizzazioni POS.
author: scott-tucker
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 985cce1f1848408517ce71b36575162960c3d84e
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="879c0-103"> Creare gruppi di autorizzazioni POS</span><span class="sxs-lookup"><span data-stu-id="879c0-103">Create POS permission groups</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="879c0-104">In questa procedura vengono descritti i passaggi per creare un gruppo di autorizzazioni POS.</span><span class="sxs-lookup"><span data-stu-id="879c0-104">This procedure will show how to create a POS permission group.</span></span> <span data-ttu-id="879c0-105">La società di dati dimostrativi utilizzata per creare questa attività è USRT.</span><span class="sxs-lookup"><span data-stu-id="879c0-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="879c0-106">Questa attività è destinata al ruolo Responsabile operativo vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="879c0-106">This task is intended for the Retail operations manager role.</span></span>

1. <span data-ttu-id="879c0-107">Passare a Gruppi di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="879c0-107">Go to Permission groups.</span></span>
2. <span data-ttu-id="879c0-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="879c0-108">Click New.</span></span>
3. <span data-ttu-id="879c0-109">Digitare un valore nel campo ID gruppo di autorizzazioni POS.</span><span class="sxs-lookup"><span data-stu-id="879c0-109">In the POS permission group ID field, type a value.</span></span>
4. <span data-ttu-id="879c0-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="879c0-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="879c0-111">Selezionare Sì nel campo Visualizza voci orologio.</span><span class="sxs-lookup"><span data-stu-id="879c0-111">Select Yes in the View time clock entries field.</span></span>
    * <span data-ttu-id="879c0-112">È ora possibile abilitare o disabilitare le varie autorizzazioni per il gruppo di autorizzazioni POS.</span><span class="sxs-lookup"><span data-stu-id="879c0-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="879c0-113">Per alcune autorizzazioni è possibile impostare un valore che verrà utilizzato per valutare se l'utente POS può eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="879c0-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span>  <span data-ttu-id="879c0-114">Questa guida attività abilita l'autorizzazione che può essere assegnata al cassiere.</span><span class="sxs-lookup"><span data-stu-id="879c0-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="879c0-115">Selezionare Sì nel campo Consenti creazione ordine.</span><span class="sxs-lookup"><span data-stu-id="879c0-115">Select Yes in the Allow create order field.</span></span>
7. <span data-ttu-id="879c0-116">Selezionare Sì nel campo Consenti modifica ordine.</span><span class="sxs-lookup"><span data-stu-id="879c0-116">Select Yes in the Allow edit order field.</span></span>
8. <span data-ttu-id="879c0-117">Selezionare Sì nel campo Consenti recupero ordine.</span><span class="sxs-lookup"><span data-stu-id="879c0-117">Select Yes in the Allow retrieve order field.</span></span>
9. <span data-ttu-id="879c0-118">Selezionare Sì nel campo Consenti modifica password.</span><span class="sxs-lookup"><span data-stu-id="879c0-118">Select Yes in the Allow password change field.</span></span>
10. <span data-ttu-id="879c0-119">Selezionare Sì nel campo Consenti chiusura forzata.</span><span class="sxs-lookup"><span data-stu-id="879c0-119">Select Yes in the Allow blind close field.</span></span>
11. <span data-ttu-id="879c0-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="879c0-120">Click Save.</span></span>
    * <span data-ttu-id="879c0-121">Dopo aver salvato le modifiche, è necessario eseguire la programmazione di distribuzione del personale per applicare le modifiche ai canali di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="879c0-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  
12. <span data-ttu-id="879c0-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="879c0-122">Close the page.</span></span>
13. <span data-ttu-id="879c0-123">Passare a Processi.</span><span class="sxs-lookup"><span data-stu-id="879c0-123">Go to Jobs.</span></span>
    * <span data-ttu-id="879c0-124">Quindi, verrà assegnato il gruppo di autorizzazioni POS a un processo.</span><span class="sxs-lookup"><span data-stu-id="879c0-124">Next we will assign the POS permission group to a Job.</span></span>  
14. <span data-ttu-id="879c0-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="879c0-125">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="879c0-126">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="879c0-126">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="879c0-127">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="879c0-127">Click Edit.</span></span>
17. <span data-ttu-id="879c0-128">Espandere la sezione Classificazione mansione.</span><span class="sxs-lookup"><span data-stu-id="879c0-128">Expand the Job classification section.</span></span>
18. <span data-ttu-id="879c0-129">Nel campo Gruppo di autorizzazioni POS immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="879c0-129">In the POS permission group field, enter or select a value.</span></span>
    * <span data-ttu-id="879c0-130">Tutti i lavoratori nelle posizioni per questo processo utilizzeranno le impostazioni del gruppo di autorizzazioni POS a meno che le autorizzazioni POS del lavoratore siano state ignorate a livello di posizione.</span><span class="sxs-lookup"><span data-stu-id="879c0-130">All Workers in Positions for this Job will use this POS permission group’s settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
19. <span data-ttu-id="879c0-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="879c0-131">Click Save.</span></span>
    * <span data-ttu-id="879c0-132">Dopo aver salvato le modifiche, è necessario eseguire la programmazione di distribuzione del personale per applicare le modifiche ai canali di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="879c0-132">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  


