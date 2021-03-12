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
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ac03e1bfb7a2463b31feca0a4303c182a00ad259
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964822"
---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="fb6d7-103">Creare gruppi di autorizzazioni POS</span><span class="sxs-lookup"><span data-stu-id="fb6d7-103">Create POS permission groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb6d7-104">In questo argomento viene illustrato come creare un gruppo di autorizzazioni POS.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-104">This topic explains how to create a POS permission group.</span></span> <span data-ttu-id="fb6d7-105">La società di dati dimostrativi utilizzata per creare questa attività è USRT.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="fb6d7-106">Questa attività è destinata al ruolo Responsabile operativo commercio.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-106">This task is intended for the Commerce operations manager role.</span></span>

1. <span data-ttu-id="fb6d7-107">Nel pannello di navigazione, andare a **Moduli > Retail e Commerce > Dipendenti > Gruppi di autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-107">In the navigation pane, go to **Modules > Retail and Commerce > Employees > Permission groups**.</span></span>
2. <span data-ttu-id="fb6d7-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-108">Select **New**.</span></span>
3. <span data-ttu-id="fb6d7-109">Digitare un valore nel campo **ID gruppo di autorizzazioni POS**.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-109">In the **POS permission group ID** field, type a value.</span></span>
4. <span data-ttu-id="fb6d7-110">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fb6d7-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="fb6d7-111">Selezionare **Sì** nel campo **Visualizza voci orologio**.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-111">Select **Yes** in the **View time clock entries** field.</span></span> <span data-ttu-id="fb6d7-112">È ora possibile abilitare o disabilitare le varie autorizzazioni per il gruppo di autorizzazioni POS.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="fb6d7-113">Per alcune autorizzazioni è possibile impostare un valore che verrà utilizzato per valutare se l'utente POS può eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span> <span data-ttu-id="fb6d7-114">Questa guida attività abilita l'autorizzazione che può essere assegnata al cassiere.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="fb6d7-115">Selezionare **Sì** nel campo **Consenti creazione ordine**.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-115">Select **Yes** in the **Allow create order** field.</span></span>
7. <span data-ttu-id="fb6d7-116">Selezionare **Sì** nel campo **Consenti modifica ordine**.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-116">Select **Yes** in the **Allow edit order** field.</span></span>
8. <span data-ttu-id="fb6d7-117">Selezionare **Sì** nel campo **Consenti recupero ordine**.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-117">Select **Yes** in the **Allow retrieve order** field.</span></span>
9. <span data-ttu-id="fb6d7-118">Selezionare **Sì** nel campo **Consenti modifica password**.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-118">Select **Yes** in the **Allow password change** field.</span></span>
10. <span data-ttu-id="fb6d7-119">Selezionare **Sì** nel campo **Consenti chiusura forzata**.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-119">Select **Yes** in the **Allow blind close** field.</span></span>
11. <span data-ttu-id="fb6d7-120">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-120">Select **Save**.</span></span> <span data-ttu-id="fb6d7-121">Dopo aver salvato le modifiche, è necessario eseguire la programmazione di distribuzione del personale per applicare le modifiche ai canali di commercio.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to commerce channels.</span></span> 
12. <span data-ttu-id="fb6d7-122">Nel pannello di navigazione, andare a **Moduli > Risorse umane > Posizioni lavorative > Posizioni lavorative**.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-122">In the navigation pane, go to **Modules > Human resources > Jobs > Jobs**.</span></span>
13. <span data-ttu-id="fb6d7-123">Quindi, verrà assegnato il gruppo di autorizzazioni POS a un processo.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-123">Next we will assign the POS permission group to a Job.</span></span> <span data-ttu-id="fb6d7-124">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-124">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="fb6d7-125">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-125">Select **Edit**.</span></span>
15. <span data-ttu-id="fb6d7-126">Espandere la sezione **Classificazione mansione**.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-126">Expand the **Job classification** section.</span></span>
16. <span data-ttu-id="fb6d7-127">Nel campo Gruppo di autorizzazioni POS immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-127">In the POS permission group field, enter or select a value.</span></span> <span data-ttu-id="fb6d7-128">Tutti i lavoratori nelle posizioni per questo processo utilizzeranno le impostazioni del gruppo di autorizzazioni POS a meno che le autorizzazioni POS del lavoratore siano state ignorate a livello di posizione.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-128">All Workers in Positions for this Job will use this POS permission group's settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
17. <span data-ttu-id="fb6d7-129">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-129">Select **Save**.</span></span> <span data-ttu-id="fb6d7-130">Dopo aver salvato le modifiche, è necessario eseguire la programmazione di distribuzione del personale per applicare le modifiche ai canali.</span><span class="sxs-lookup"><span data-stu-id="fb6d7-130">After your changes are saved you need to run the Staff distribution schedule to push the changes to channels.</span></span>  

