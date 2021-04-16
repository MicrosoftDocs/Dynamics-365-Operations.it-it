---
title: Impostare un profilo di panoramica arrivo articoli
description: In questo argomento viene descritta l'impostazione del profilo della panoramica arrivi.
author: ShylaThompson
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0394d1b4288dac0ff913b125017571a8c0bc95a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829838"
---
# <a name="set-up-an-item-arrival-overview-profile"></a><span data-ttu-id="8857b-103">Impostare un profilo di panoramica arrivo articoli</span><span class="sxs-lookup"><span data-stu-id="8857b-103">Set up an item arrival overview profile</span></span>

<span data-ttu-id="8857b-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="8857b-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="8857b-105">In questo argomento viene descritta l'impostazione del profilo della panoramica arrivi.</span><span class="sxs-lookup"><span data-stu-id="8857b-105">This topic focuses on the setup of an arrival overview profile.</span></span> <span data-ttu-id="8857b-106">Il profilo della panoramica arrivi è una raccolta di regole da applicare alla pagina della panoramica arrivi viene aperta da un utente.</span><span class="sxs-lookup"><span data-stu-id="8857b-106">The arrival overview profile is a collection of rules that will be applied when the Arrival overview page is opened by a user.</span></span> <span data-ttu-id="8857b-107">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="8857b-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="8857b-108">In genere questa procedura verrebbe eseguita da un addetto al ricevimento.</span><span class="sxs-lookup"><span data-stu-id="8857b-108">This procedure would typically be carried out by a receiving clerk.</span></span>

1. <span data-ttu-id="8857b-109">Nel pannello di navigazione andare a **Moduli > Gestione articoli > Impostazione > Distribuzione > Profili panoramica arrivi**.</span><span class="sxs-lookup"><span data-stu-id="8857b-109">In the navigation pane, go to **Modules > Inventory management > Setup > Distribution > Arrival overview profiles**.</span></span>
2. <span data-ttu-id="8857b-110">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8857b-110">Select **New**.</span></span> <span data-ttu-id="8857b-111">Poiché verrà utilizzato quasi sempre lo stesso magazzino in cui vengono scaricati camion carichi, è necessario creare un profilo della panoramica arrivi per semplificare il processo di registrazione degli articoli ricevuti.</span><span class="sxs-lookup"><span data-stu-id="8857b-111">Because you will almost always work in the same warehouse offloading full truck loads, you should create an arrival overview profile to simplify the process of registering received items.</span></span>  
3. <span data-ttu-id="8857b-112">Nel campo **Nome profilo panoramica arrivi** digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="8857b-112">In the **Arrival overview profile name** field, type a value.</span></span>
4. <span data-ttu-id="8857b-113">Selezionare un'opzione nel campo **Mostra righe**.</span><span class="sxs-lookup"><span data-stu-id="8857b-113">In the **Show lines** field, select an option.</span></span> <span data-ttu-id="8857b-114">Selezionare le righe da visualizzare per le entrate:</span><span class="sxs-lookup"><span data-stu-id="8857b-114">Select which lines to show for the receipts:</span></span>  

    - <span data-ttu-id="8857b-115">**Tutto**: mostra tutte le righe, indipendentemente dal loro stato.</span><span class="sxs-lookup"><span data-stu-id="8857b-115">**All** – Show all lines, regardless of status.</span></span>   
    - <span data-ttu-id="8857b-116">**In corso**: mostra solo le righe per le entrate con stato di avanzamento Completa o Parzialmente.</span><span class="sxs-lookup"><span data-stu-id="8857b-116">**In progress** – Show lines for receipts in which the progress is Complete or Partly.</span></span> <span data-ttu-id="8857b-117">Ciò significa che, per ogni riga, nel giornale di registrazione arrivi è stata registrata la quantità completa o una quantità parziale.</span><span class="sxs-lookup"><span data-stu-id="8857b-117">This means that for each line, either the full quantity or part of the quantity has been registered in an arrival journal.</span></span>   
    - <span data-ttu-id="8857b-118">**Non completato**: mostra solo le righe per le entrate con stato di avanzamento Nessuno o Parzialmente.</span><span class="sxs-lookup"><span data-stu-id="8857b-118">**Not complete** – Show lines for receipts in which the progress is None or Partly.</span></span> <span data-ttu-id="8857b-119">Ciò significa che, per ogni riga, nel giornale di registrazione arrivi non è stata registrata alcuna quantità o è stata registrata solo una quantità parziale.</span><span class="sxs-lookup"><span data-stu-id="8857b-119">This means that for each line, nothing or only part of the quantity has been registered in an arrival journal.</span></span>  

5. <span data-ttu-id="8857b-120">Espandere o comprimere la sezione **Opzioni arrivi**.</span><span class="sxs-lookup"><span data-stu-id="8857b-120">Expand or collapse the **Arrival options** section.</span></span>
6. <span data-ttu-id="8857b-121">Digitare un valore nel campo **Giorni successivi**.</span><span class="sxs-lookup"><span data-stu-id="8857b-121">In the **Days forward** field, type a value.</span></span> <span data-ttu-id="8857b-122">Viene impostato un filtro per visualizzare le righe di entrata previste per il ricevimento nei prossimi giorni (in base al numero impostato).</span><span class="sxs-lookup"><span data-stu-id="8857b-122">This sets a filter to show the receipt lines expected to be received within the next few days (depending on the number you set).</span></span>  
7. <span data-ttu-id="8857b-123">Digitare un valore nel campo **Giorni precedenti**.</span><span class="sxs-lookup"><span data-stu-id="8857b-123">In the **Days back** field, type a value.</span></span> <span data-ttu-id="8857b-124">Viene impostato un filtro per visualizzare le righe di entrata previste per il ricevimento un numero di giorni prima della data odierna.</span><span class="sxs-lookup"><span data-stu-id="8857b-124">This sets a filter to show the receipt lines expected to be received a number of days before today.</span></span>  
8. <span data-ttu-id="8857b-125">Digitare un valore nel campo **Magazzini**.</span><span class="sxs-lookup"><span data-stu-id="8857b-125">In the **Warehouses** field, type a value.</span></span> <span data-ttu-id="8857b-126">Viene applicato un filtro su uno o più magazzini.</span><span class="sxs-lookup"><span data-stu-id="8857b-126">Filter on one or more warehouses.</span></span>  
9. <span data-ttu-id="8857b-127">Selezionare un valore nel campo **Modalità di consegna**.</span><span class="sxs-lookup"><span data-stu-id="8857b-127">In the **Mode of delivery** field, select a value.</span></span> <span data-ttu-id="8857b-128">Viene impostato un filtro per visualizzare solo le righe entrata con questa modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="8857b-128">This sets a filter to show only the receipt lines with this Mode of delivery.</span></span>  
10. <span data-ttu-id="8857b-129">Selezionare Gestione magazzino nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="8857b-129">In the **Name** field, select WHS.</span></span>
11. <span data-ttu-id="8857b-130">Nel campo **Magazzino** selezionare il magazzino 24.</span><span class="sxs-lookup"><span data-stu-id="8857b-130">In the **Warehouse** field, select warehouse 24.</span></span> <span data-ttu-id="8857b-131">Si tratta del magazzino predefinito da utilizzare per le righe entrata registrate che utilizzano il profilo.</span><span class="sxs-lookup"><span data-stu-id="8857b-131">This is the default warehouse that will be used for registered receipt lines that use this profile.</span></span>  
12. <span data-ttu-id="8857b-132">Nel campo **Ubicazione** selezionare **Baydoor**.</span><span class="sxs-lookup"><span data-stu-id="8857b-132">In the **Location** field, select **Baydoor**.</span></span> <span data-ttu-id="8857b-133">Si tratta dell'ubicazione predefinita da utilizzare per le righe entrata registrate che utilizzano il profilo.</span><span class="sxs-lookup"><span data-stu-id="8857b-133">This is the default location that will be used for registered receipt lines that use this profile.</span></span>  
13. <span data-ttu-id="8857b-134">Espandere o comprimere la sezione **Dettagli query arrivi**.</span><span class="sxs-lookup"><span data-stu-id="8857b-134">Expand or collapse the **Arrival query details** section.</span></span>
14. <span data-ttu-id="8857b-135">Nel campo **Limita al sito** selezionare il sito 2.</span><span class="sxs-lookup"><span data-stu-id="8857b-135">In the **Restrict to site** field, select site 2.</span></span> <span data-ttu-id="8857b-136">Viene impostato un filtro per visualizzare solo le righe entrata con questo sito.</span><span class="sxs-lookup"><span data-stu-id="8857b-136">This sets a filter to show only the receipt lines with this site.</span></span>  
15. <span data-ttu-id="8857b-137">Impostare l'opzione **Ordini fornitore** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8857b-137">Set the **Purchase orders** option to **Yes**.</span></span> <span data-ttu-id="8857b-138">Consente di selezionare righe entrata dagli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="8857b-138">Select receipt lines from purchase orders.</span></span>  
16. <span data-ttu-id="8857b-139">Impostare l'opzione **Ordini di trasferimento** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8857b-139">Set the **Transfer** orders option to **Yes**.</span></span> <span data-ttu-id="8857b-140">Consente di selezionare righe entrata dagli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="8857b-140">Select receipt lines from transfer orders.</span></span>  
17. <span data-ttu-id="8857b-141">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8857b-141">Select **Save**.</span></span>
18. <span data-ttu-id="8857b-142">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8857b-142">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]