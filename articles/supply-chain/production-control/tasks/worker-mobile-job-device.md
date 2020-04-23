---
title: Configurare un lavoratore tramite il dispositivo di processo mobile
description: Questa argomento spiega come assegnare i ruoli corretti all'account utente di un lavoratore e abilitare il lavoratore a effettuare le registrazioni del reparto produzione.
author: ShylaThompson
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1086a88c341b95d6af03adc81c4e3e5d76adc69
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210205"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="e0b9b-103">Configurare un lavoratore tramite il dispositivo di processo mobile</span><span class="sxs-lookup"><span data-stu-id="e0b9b-103">Configure a worker using the mobile job device</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e0b9b-104">Questa argomento spiega come assegnare i ruoli corretti all'account utente di un lavoratore e abilitare il lavoratore a effettuare le registrazioni del reparto produzione.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-104">This topic explains how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a><span data-ttu-id="e0b9b-105">Verificare che a un lavoratore è assegnato un determinato ruolo</span><span class="sxs-lookup"><span data-stu-id="e0b9b-105">Verify that a worker is assigned a certain role</span></span>

<span data-ttu-id="e0b9b-106">Per questo esempio, verificare che all'utente "SHANNON " sia assegnato il ruolo di operatore prima di configurare l'account del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-106">For this example, verify that user "SHANNON" is assigned the machine operator role before you configure the worker account.</span></span>

1. <span data-ttu-id="e0b9b-107">Andare a **Pannello di navigazione > Moduli > Amministrazione sistema > Utenti > Utenti**.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="e0b9b-108">Cercare un utente nel filtro rapido.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-108">Search for a user in the quick filter.</span></span> <span data-ttu-id="e0b9b-109">Per questo esempio, immettere `shannon`.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-109">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="e0b9b-110">Selezionare il collegamento nella colonna **ID utente** dell'account utente visualizzato.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-110">Select the link in the **User ID** column of the user account that appears.</span></span>
4. <span data-ttu-id="e0b9b-111">Nella struttura **Ruoli utente**, selezionare **Ruoli > Operatore macchina**.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-111">In the **User's roles** tree, select **Roles > Machine operator**.</span></span>
5. <span data-ttu-id="e0b9b-112">Chiudere le pagine **dettagli utente** e **utenti** per tornare alla home page.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-112">Close the **user details** and **users** pages to return to the home page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="e0b9b-113">Configurare l'account del lavoratore</span><span class="sxs-lookup"><span data-stu-id="e0b9b-113">Configure worker account</span></span>
1. <span data-ttu-id="e0b9b-114">Passare a **Pannello di navigazione > Moduli > Risorse umane > Lavoratori > Lavoratori**.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-114">Go to **Navigation pane > Modules > Human resources > Workers > Workers**.</span></span>
2. <span data-ttu-id="e0b9b-115">Cercare un utente nel filtro rapido.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-115">Search for a user in the quick filter.</span></span> <span data-ttu-id="e0b9b-116">Per questo esempio, immettere `shannon`.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-116">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="e0b9b-117">Selezionare il collegamento nella colonna **Nome** dell'account utente visualizzato.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-117">Select the link in the **Name** column of the user account that appears.</span></span>
4. <span data-ttu-id="e0b9b-118">Fare clic sulla scheda **Registrazione ore**.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-118">Select the **Time registration** tab.</span></span>
5. <span data-ttu-id="e0b9b-119">Selezionare **Attiva su terminali registrazioni**.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-119">Select **Activate on registration terminals**.</span></span>
6. <span data-ttu-id="e0b9b-120">Immettere o selezionare i valori nei seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="e0b9b-120">Enter or select values in the following fields:</span></span>  

    - <span data-ttu-id="e0b9b-121">**Gruppo di calcolo**</span><span class="sxs-lookup"><span data-stu-id="e0b9b-121">**Calculation group**</span></span>  
    - <span data-ttu-id="e0b9b-122">**Gruppo di calcolo predefinito**</span><span class="sxs-lookup"><span data-stu-id="e0b9b-122">**Default calculation group**</span></span>  
    - <span data-ttu-id="e0b9b-123">**Gruppo di approvazione**</span><span class="sxs-lookup"><span data-stu-id="e0b9b-123">**Approval group**</span></span>  
    - <span data-ttu-id="e0b9b-124">**Profilo standard**</span><span class="sxs-lookup"><span data-stu-id="e0b9b-124">**Standard profile**</span></span>  
    - <span data-ttu-id="e0b9b-125">**Gruppo profilo**</span><span class="sxs-lookup"><span data-stu-id="e0b9b-125">**Profile group**</span></span>  

7. <span data-ttu-id="e0b9b-126">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-126">Select **OK**.</span></span>
8. <span data-ttu-id="e0b9b-127">Fare clic su **Modifica** per immettere un numero di badge per il nuovo lavoratore per registrazione ore.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-127">Select **Edit** to enter a badge number for the new time registration worker.</span></span> <span data-ttu-id="e0b9b-128">Nel campo **ID badge** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-128">Enter a value in the **Badge ID** field.</span></span>
9. <span data-ttu-id="e0b9b-129">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-129">Select **Save**.</span></span>
10. <span data-ttu-id="e0b9b-130">Chiudere le pagine **Dettagli lavoratore** e **Lavoratori**.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-130">Close the **Worker details** and **Workers** pages.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="e0b9b-131">Assegnare il lavoratore a un gruppo di dispositivi</span><span class="sxs-lookup"><span data-stu-id="e0b9b-131">Assign worker to device group</span></span>
1. <span data-ttu-id="e0b9b-132">Andare a **Controllo produzione > Impostazioni > Esecuzione produzione > Configura scheda processo per dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-132">Go to **Production control > Setup > Manufacturing execution > Configure job card for devices**.</span></span>
2. <span data-ttu-id="e0b9b-133">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-133">Select **Add**.</span></span>
3. <span data-ttu-id="e0b9b-134">Selezionare il lavoratore desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-134">In the list, select the desired worker.</span></span> <span data-ttu-id="e0b9b-135">Per questo esempio, selezionare **SHANNON**.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-135">For this example, select **SHANNON**.</span></span>
4. <span data-ttu-id="e0b9b-136">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-136">Select **OK**.</span></span>
5. <span data-ttu-id="e0b9b-137">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-137">Select **Edit**.</span></span>
6. <span data-ttu-id="e0b9b-138">Nel campo **Unità di produzione**, è possibile impostare il filtro predefinito per il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-138">In the **Production unit** field, you can set the default filter for the worker.</span></span> <span data-ttu-id="e0b9b-139">In tal modo si assicura che solo i processi di produzione per l'unità di produzione selezionata vengano visualizzati quando il lavoratore accede al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-139">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span> <span data-ttu-id="e0b9b-140">Immettere il valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-140">Enter the desired value.</span></span>
7. <span data-ttu-id="e0b9b-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e0b9b-141">Close the page.</span></span>

