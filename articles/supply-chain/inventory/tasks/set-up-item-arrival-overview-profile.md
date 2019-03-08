---
title: Impostare un profilo di panoramica arrivo articoli
description: Questa attività riguarda l'impostazione del profilo della panoramica arrivi.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b61d77072358083a35de28003176cb88e53453e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "338017"
---
# <a name="set-up-an-item-arrival-overview-profile"></a><span data-ttu-id="99427-103">Impostare un profilo di panoramica arrivo articoli</span><span class="sxs-lookup"><span data-stu-id="99427-103">Set up an item arrival overview profile</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="99427-104">Questa attività riguarda l'impostazione del profilo della panoramica arrivi.</span><span class="sxs-lookup"><span data-stu-id="99427-104">This task focuses on the setup of an arrival overview profile.</span></span> <span data-ttu-id="99427-105">Il profilo della panoramica arrivi è una raccolta di regole da applicare alla pagina della panoramica arrivi viene aperta da un utente.</span><span class="sxs-lookup"><span data-stu-id="99427-105">The arrival overview profile is a collection of rules that will be applied when the Arrival overview page is opened by a user.</span></span> <span data-ttu-id="99427-106">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="99427-106">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="99427-107">In genere questa procedura verrebbe eseguita da un addetto al ricevimento.</span><span class="sxs-lookup"><span data-stu-id="99427-107">This procedure would typically be carried out by a receiving clerk.</span></span>





1. <span data-ttu-id="99427-108">Andare a Gestione articoli > Impostazioni > Distribuzione > Profili panoramica arrivi.</span><span class="sxs-lookup"><span data-stu-id="99427-108">Go to Inventory management > Setup > Distribution > Arrival overview profiles.</span></span>
2. <span data-ttu-id="99427-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="99427-109">Click New.</span></span>
    * <span data-ttu-id="99427-110">Poiché verrà utilizzato quasi sempre lo stesso magazzino in cui vengono scaricati camion carichi, è necessario creare un profilo della panoramica arrivi per semplificare il processo di registrazione degli articoli ricevuti.</span><span class="sxs-lookup"><span data-stu-id="99427-110">Because you will almost always work in the same warehouse offloading full truck loads, you should create an arrival overview profile to simplify the process of registering received items.</span></span>  
3. <span data-ttu-id="99427-111">Nel campo Nome profilo panoramica arrivi digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="99427-111">In the Arrival overview profile name field, type a value.</span></span>
4. <span data-ttu-id="99427-112">Selezionare un'opzione nel campo Mostra righe.</span><span class="sxs-lookup"><span data-stu-id="99427-112">In the Show lines field, select an option.</span></span>
    * <span data-ttu-id="99427-113">Selezionare le righe da visualizzare per le entrate. Tutte: indica tutte le righe, indipendentemente dallo stato.</span><span class="sxs-lookup"><span data-stu-id="99427-113">Select which lines to show for the receipts:   All – Show all lines, regardless of status.</span></span>   <span data-ttu-id="99427-114">In corso: mostra solo le righe per le entrate con stato di avanzamento Completa o Parzialmente.</span><span class="sxs-lookup"><span data-stu-id="99427-114">In progress – Show lines for receipts in which the progress is Complete or Partly.</span></span> <span data-ttu-id="99427-115">Ciò significa che, per ogni riga, nel giornale di registrazione arrivi è stata registrata la quantità completa o una quantità parziale.</span><span class="sxs-lookup"><span data-stu-id="99427-115">This means that for each line, either the full quantity or part of the quantity has been registered in an arrival journal.</span></span>   <span data-ttu-id="99427-116">Non completato: mostra solo le righe per le entrate con stato di avanzamento Nessuno o Parzialmente.</span><span class="sxs-lookup"><span data-stu-id="99427-116">Not complete – Show lines for receipts in which the progress is None or Partly.</span></span> <span data-ttu-id="99427-117">Ciò significa che, per ogni riga, nel giornale di registrazione arrivi non è stata registrata alcuna quantità o è stata registrata solo una quantità parziale.</span><span class="sxs-lookup"><span data-stu-id="99427-117">This means that for each line, nothing or only part of the quantity has been registered in an arrival journal.</span></span>  
5. <span data-ttu-id="99427-118">Espandere o comprimere la sezione Opzioni arrivi.</span><span class="sxs-lookup"><span data-stu-id="99427-118">Expand or collapse the Arrival options section.</span></span>
6. <span data-ttu-id="99427-119">Digitare un valore nel campo Giorni successivi.</span><span class="sxs-lookup"><span data-stu-id="99427-119">In the Days forward field, type a value.</span></span>
    * <span data-ttu-id="99427-120">Viene impostato un filtro per visualizzare le righe di entrata previste per il ricevimento nei prossimi giorni (in base al numero impostato).</span><span class="sxs-lookup"><span data-stu-id="99427-120">This sets a filter to show the receipt lines expected to be received within the next few days (depending on the number you set).</span></span>  
7. <span data-ttu-id="99427-121">Digitare un valore nel campo Giorni precedenti.</span><span class="sxs-lookup"><span data-stu-id="99427-121">In the Days back field, type a value.</span></span>
    * <span data-ttu-id="99427-122">Viene impostato un filtro per visualizzare le righe di entrata previste per il ricevimento un numero di giorni prima della data odierna.</span><span class="sxs-lookup"><span data-stu-id="99427-122">This sets a filter to show the receipt lines expected to be received a number of days before today.</span></span>  
8. <span data-ttu-id="99427-123">Digitare un valore nel campo Magazzini.</span><span class="sxs-lookup"><span data-stu-id="99427-123">In the Warehouses field, type a value.</span></span>
    * <span data-ttu-id="99427-124">Viene applicato un filtro su uno o più magazzini.</span><span class="sxs-lookup"><span data-stu-id="99427-124">Filter on one or more warehouses.</span></span>  
9. <span data-ttu-id="99427-125">Selezionare un valore nel campo Modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="99427-125">In the Mode of delivery field, select a value.</span></span>
    * <span data-ttu-id="99427-126">Viene impostato un filtro per visualizzare solo le righe entrata con questa modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="99427-126">This sets a filter to show only the receipt lines with this Mode of delivery.</span></span>  
10. <span data-ttu-id="99427-127">Selezionare Gestione magazzino nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="99427-127">In the Name field, select WHS.</span></span>
11. <span data-ttu-id="99427-128">Nel campo Magazzino selezionare il magazzino 24.</span><span class="sxs-lookup"><span data-stu-id="99427-128">In the Warehouse field, select warehouse 24.</span></span>
    * <span data-ttu-id="99427-129">Si tratta del magazzino predefinito da utilizzare per le righe entrata registrate che utilizzano il profilo.</span><span class="sxs-lookup"><span data-stu-id="99427-129">This is the default warehouse that will be used for registered receipt lines that use this profile.</span></span>  
12. <span data-ttu-id="99427-130">Nel campo Ubicazione selezionare Baydoor.</span><span class="sxs-lookup"><span data-stu-id="99427-130">In the Location field, select Baydoor.</span></span>
    * <span data-ttu-id="99427-131">Si tratta dell'ubicazione predefinita da utilizzare per le righe entrata registrate che utilizzano il profilo.</span><span class="sxs-lookup"><span data-stu-id="99427-131">This is the default location that will be used for registered receipt lines that use this profile.</span></span>  
13. <span data-ttu-id="99427-132">Espandere o comprimere la sezione Dettagli query arrivi.</span><span class="sxs-lookup"><span data-stu-id="99427-132">Expand or collapse the Arrival query details section.</span></span>
14. <span data-ttu-id="99427-133">Nel campo Limita al sito selezionare il sito 2.</span><span class="sxs-lookup"><span data-stu-id="99427-133">In the Restrict to site field, select site 2.</span></span>
    * <span data-ttu-id="99427-134">Viene impostato un filtro per visualizzare solo le righe entrata con questo sito.</span><span class="sxs-lookup"><span data-stu-id="99427-134">This sets a filter to show only the receipt lines with this site.</span></span>  
15. <span data-ttu-id="99427-135">Impostare l'opzione Ordini fornitore su Sì.</span><span class="sxs-lookup"><span data-stu-id="99427-135">Set the Purchase orders option to Yes.</span></span>
    * <span data-ttu-id="99427-136">Consente di selezionare righe entrata dagli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="99427-136">Select receipt lines from purchase orders.</span></span>  
16. <span data-ttu-id="99427-137">Impostare l'opzione Ordini di trasferimento su Sì.</span><span class="sxs-lookup"><span data-stu-id="99427-137">Set the Transfer orders option to Yes.</span></span>
    * <span data-ttu-id="99427-138">Consente di selezionare righe entrata dagli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="99427-138">Select receipt lines from transfer orders.</span></span>  
17. <span data-ttu-id="99427-139">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="99427-139">Click Save.</span></span>
18. <span data-ttu-id="99427-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="99427-140">Close the page.</span></span>

