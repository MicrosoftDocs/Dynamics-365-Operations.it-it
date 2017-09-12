--- 
title: Configurare un lavoratore tramite il dispositivo di lavoro mobile
description: Questa procedura consente di assegnare i ruoli corretti all'account utente di un lavoratore e quindi consente al lavoratore di effettuare le registrazioni del reparto produzione.
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d56f861dbbf579e44fcd3fc4d8b45c24029acecc
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="8e3f2-103">Configurare un lavoratore tramite il dispositivo di lavoro mobile</span><span class="sxs-lookup"><span data-stu-id="8e3f2-103">Configure a worker using the mobile job device</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8e3f2-104">Questa procedura consente di assegnare i ruoli corretti all'account utente di un lavoratore e quindi consente al lavoratore di effettuare le registrazioni del reparto produzione.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-104">This procedure shows you how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>


## <a name="assign-roles-to-user-account"></a><span data-ttu-id="8e3f2-105">Assegnare ruoli all'account utente</span><span class="sxs-lookup"><span data-stu-id="8e3f2-105">Assign roles to user account</span></span>
1. <span data-ttu-id="8e3f2-106">Andare a Amministrazione sistema > Utenti > Utenti.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-106">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="8e3f2-107">Utilizzare il filtro rapido per filtrare il nome di un lavoratore nell'account utente associato al ruolo operatore macchina.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-107">Use the Quick Filter to filter on the name of a worker where the user account is associated with the machine operator role.</span></span> <span data-ttu-id="8e3f2-108">Nei dati di esempio, il nome sarà Shannon.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-108">In the sample data, the name would be Shannon.</span></span>
3. <span data-ttu-id="8e3f2-109">Evidenziare il record dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-109">Highlight the user account record.</span></span>
4. <span data-ttu-id="8e3f2-110">Nell'elenco, fare clic sul collegamento 'Nome' nella riga selezionata per visualizzare i dettagli dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-110">In the list, click the "Name" link in the selected row to view the details of the user account.</span></span>
5. <span data-ttu-id="8e3f2-111">Nella struttura, selezionare 'Ruoli\Operatore macchina'.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-111">In the tree, select 'Roles\Machine operator'.</span></span>
6. <span data-ttu-id="8e3f2-112">Chiudere la pagina dei dettagli dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-112">Close the user account details page.</span></span>
7. <span data-ttu-id="8e3f2-113">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-113">Close the page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="8e3f2-114">Configurare l'account del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-114">Configure worker account.</span></span>
1. <span data-ttu-id="8e3f2-115">Andare a Risorse umane > Lavoratori > Lavoratori.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-115">Go to Human resources > Workers > Workers.</span></span>
2. <span data-ttu-id="8e3f2-116">Utilizzare il filtro rapido per filtrare il nome di un lavoratore nell'account utente associato al ruolo operatore macchina.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-116">Use the Quick Filter to filter on the name of a worker where the user account is associated with the machine operator role.</span></span> <span data-ttu-id="8e3f2-117">Nei dati di esempio, il nome sarà Shannon.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-117">In the sample data, the name would be Shannon.</span></span>
3. <span data-ttu-id="8e3f2-118">Evidenziare il record dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-118">Highlight the user account record.</span></span>
4. <span data-ttu-id="8e3f2-119">Nell'elenco, fare clic sul collegamento 'Nome' nella riga selezionata per visualizzare i dettagli dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-119">In the list, click the "Name" link in the selected row to view the details of the user account.</span></span>
5. <span data-ttu-id="8e3f2-120">Fare clic sulla scheda Impiego.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-120">Click the Employment tab.</span></span>
6. <span data-ttu-id="8e3f2-121">Espandere la scheda dettaglio Registrazione ore e fare clic su Attiva su terminali registrazioni.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-121">Expand the Time registration FastTab and click Activate on registration terminals.</span></span>
7. <span data-ttu-id="8e3f2-122">Fare clic su Attiva su terminali registrazioni.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-122">Click Activate on registration terminals.</span></span>
8. <span data-ttu-id="8e3f2-123">Nel campo Gruppo di calcolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-123">In the Calculation group field, enter or select a value.</span></span>
9. <span data-ttu-id="8e3f2-124">Nel campo Gruppo di calcolo predefinito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-124">In the Default calculation group field, enter or select a value.</span></span>
10. <span data-ttu-id="8e3f2-125">Nel campo Gruppo di approvazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-125">In the Approval group field, enter or select a value.</span></span>
11. <span data-ttu-id="8e3f2-126">Nel campo Profilo standard immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-126">In the Standard profile field, enter or select a value.</span></span>
12. <span data-ttu-id="8e3f2-127">Nel campo Gruppo di profili immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-127">In the Profile group field, enter or select a value.</span></span>
13. <span data-ttu-id="8e3f2-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-128">Click OK.</span></span>
14. <span data-ttu-id="8e3f2-129">Fare clic su Modifica per immettere un numero di badge per il nuovo lavoratore per registrazione ore.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-129">Click Edit to enter a badge number for the new time registration worker.</span></span>
15. <span data-ttu-id="8e3f2-130">Digitare un valore nel campo ID badge.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-130">In the Badge ID field, type a value.</span></span>
16. <span data-ttu-id="8e3f2-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-131">Click Save.</span></span>
17. <span data-ttu-id="8e3f2-132">Utilizzare il collegamento SaveRecord.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-132">Use the SaveRecord shortcut.</span></span>
18. <span data-ttu-id="8e3f2-133">Chiudere la pagina del dettagli del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-133">Close the worker details page.</span></span>
19. <span data-ttu-id="8e3f2-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-134">Close the page.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="8e3f2-135">Assegnare il lavoratore al gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-135">Assign worker to device group.</span></span>
1. <span data-ttu-id="8e3f2-136">Andare a Controllo produzione > Impostazioni > Esecuzione produzione > Configura scheda processo per dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-136">Go to Production control > Setup > Manufacturing execution > Configure job card for devices.</span></span>
2. <span data-ttu-id="8e3f2-137">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-137">Click Add.</span></span>
3. <span data-ttu-id="8e3f2-138">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="8e3f2-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-139">Click OK.</span></span>
5. <span data-ttu-id="8e3f2-140">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-140">Click Edit.</span></span>
6. <span data-ttu-id="8e3f2-141">Nel campo Unità di produzione, è possibile impostare il filtro predefinito per il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-141">In the Production unit field, you can set the default filter for the worker.</span></span> <span data-ttu-id="8e3f2-142">In tal modo si assicura che solo i processi di produzione per l'unità di produzione selezionata vengano visualizzati quando il lavoratore accede al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-142">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span>
7. <span data-ttu-id="8e3f2-143">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8e3f2-143">Close the page.</span></span>

