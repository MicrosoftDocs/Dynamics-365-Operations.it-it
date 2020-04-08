---
title: Utilizzare il giornale di registrazione delle scorte di sicurezza per aggiornare la copertura minima
description: Questa procedura mostra come calcolare le proposte di copertura minima basate sulle transazioni storiche e poi aggiornare la copertura articoli con le proposte.
author: ChristianRytt
manager: AnnBe
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1624f84db10ea7cc80bb94757f19484b8c403c5c
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148770"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a><span data-ttu-id="5028c-103">Utilizzare il giornale di registrazione delle scorte di sicurezza per aggiornare la copertura minima</span><span class="sxs-lookup"><span data-stu-id="5028c-103">Use the safety stock journal to update minimum coverage</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5028c-104">Questa procedura mostra come calcolare le proposte di copertura minima basate sulle transazioni storiche e poi aggiornare la copertura articoli con le proposte.</span><span class="sxs-lookup"><span data-stu-id="5028c-104">This procedure shows how to calculate minimum coverage proposals based on historical transactions and then update the item coverage with the proposals.</span></span> <span data-ttu-id="5028c-105">Ciò viene effettuato facendo uso del giornale di registrazione delle scorte di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5028c-105">This is done using the safety stock journal.</span></span> <span data-ttu-id="5028c-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="5028c-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="5028c-107">Questa attività è destinata al responsabile pianificazione della produzione, per facilitare il mantenimento della copertura minima.</span><span class="sxs-lookup"><span data-stu-id="5028c-107">This task is intended for the production planner, to help maintain minimum coverage.</span></span>


## <a name="create-a-new-safety-stock-journal-name"></a><span data-ttu-id="5028c-108">Creare un nuovo nome per il giornale di registrazione delle scorte di sicurezza</span><span class="sxs-lookup"><span data-stu-id="5028c-108">Create a new safety stock journal name</span></span>
1. <span data-ttu-id="5028c-109">Nel **pannello di navigazione**, andare a **Pianificazione generale > Impostazioni > Nomi giornali di registrazione scorte di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="5028c-109">In the **Navigation pane**, go to **Master planning > Setup > Safety stock journal names**.</span></span>
2. <span data-ttu-id="5028c-110">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5028c-110">Click **New**.</span></span>
3. <span data-ttu-id="5028c-111">Nel campo **Nome** digitare "Materiale".</span><span class="sxs-lookup"><span data-stu-id="5028c-111">In the **Name** field, type 'Material'.</span></span>
4. <span data-ttu-id="5028c-112">Digitare "Materiale" nel campo **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="5028c-112">In the **Description** field, type 'Material'.</span></span>
5. <span data-ttu-id="5028c-113">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5028c-113">Close the page.</span></span>

## <a name="create-a-safety-stock-journal"></a><span data-ttu-id="5028c-114">Creare un giornale di registrazione delle scorte di sicurezza</span><span class="sxs-lookup"><span data-stu-id="5028c-114">Create a safety stock journal</span></span>
1. <span data-ttu-id="5028c-115">Nel **pannello di navigazione**,andare a **Pianificazione generale > Pianificazione generale > Esegui Calcolo scorte di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="5028c-115">In the **Navigation pane**, go to **Master planning > Master planning > Run > Safety stock calculation**.</span></span>
2. <span data-ttu-id="5028c-116">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5028c-116">Click **New**.</span></span>
3. <span data-ttu-id="5028c-117">Nel campo **Nome** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5028c-117">In the **Name** field, enter or select a value.</span></span> <span data-ttu-id="5028c-118">Selezionare il nome del giornale di registrazione delle scorte di sicurezza creato, ad esempio, Materiale.</span><span class="sxs-lookup"><span data-stu-id="5028c-118">Select the safety stock journal name that you created, for example, Material.</span></span>  
4. <span data-ttu-id="5028c-119">Fare clic su **Crea righe**.</span><span class="sxs-lookup"><span data-stu-id="5028c-119">Click **Create lines**.</span></span>
5. <span data-ttu-id="5028c-120">Immettere una data nel campo **Dal**.</span><span class="sxs-lookup"><span data-stu-id="5028c-120">In the **From date** field, enter a date.</span></span>  
6. <span data-ttu-id="5028c-121">Nel campo **Al** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="5028c-121">In the **To date** field, enter a date.</span></span>
7. <span data-ttu-id="5028c-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5028c-122">Click **OK**.</span></span> <span data-ttu-id="5028c-123">Ciò creerà le righe per le dimensioni che hanno operazioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="5028c-123">This will create lines for the dimensions that have inventory transactions.</span></span>  

## <a name="calculate-proposal"></a><span data-ttu-id="5028c-124">Calcola proposta</span><span class="sxs-lookup"><span data-stu-id="5028c-124">Calculate proposal</span></span>
1. <span data-ttu-id="5028c-125">Fare clic su **Calcola proposta**.</span><span class="sxs-lookup"><span data-stu-id="5028c-125">Click **Calculate proposal**.</span></span>
2. <span data-ttu-id="5028c-126">Selezionare l'opzione **Utilizza uscita media durante il lead time**.</span><span class="sxs-lookup"><span data-stu-id="5028c-126">Select the **Use average issue during lead time** option.</span></span>
3. <span data-ttu-id="5028c-127">Impostare **Fattore di moltiplicazione** su "10".</span><span class="sxs-lookup"><span data-stu-id="5028c-127">Set **Multiplication factor** to '10'.</span></span> <span data-ttu-id="5028c-128">Il fattore di moltiplicazione è usato per rettificare la proposta.</span><span class="sxs-lookup"><span data-stu-id="5028c-128">The Multiply factor is used to adjust the proposal.</span></span> <span data-ttu-id="5028c-129">Poiché i dati dimostrativi hanno soltanto alcune transazioni, dovrete impostare il fattore in modo da ottenere una proposta realistica.</span><span class="sxs-lookup"><span data-stu-id="5028c-129">Because demo data only has a few transactions, you will need to set the factor to get a realistic proposal.</span></span>  
4. <span data-ttu-id="5028c-130">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5028c-130">Click **OK**.</span></span> <span data-ttu-id="5028c-131">Scorrere in basso fino a trovare M0002 e M0003.</span><span class="sxs-lookup"><span data-stu-id="5028c-131">Scroll down to find M0002 and M0003.</span></span> <span data-ttu-id="5028c-132">Visualizzare la colonna **Quantità minima calcolata**.</span><span class="sxs-lookup"><span data-stu-id="5028c-132">View the **Calculated minimum** quantity column.</span></span>   

## <a name="update-minimum-quantity"></a><span data-ttu-id="5028c-133">Aggiornare la quantità minima</span><span class="sxs-lookup"><span data-stu-id="5028c-133">Update minimum quantity</span></span>
1. <span data-ttu-id="5028c-134">Nel campo **Nuova quantità minima** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="5028c-134">In the **New minimum quantity** field, enter a number.</span></span> <span data-ttu-id="5028c-135">Aggiornare la Nuova quantità minima in modo che corrisponda al valore della Quantità minima calcolata.</span><span class="sxs-lookup"><span data-stu-id="5028c-135">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="5028c-136">Se il minimo calcolato è zero, potete immettere il valore futuro desiderato.</span><span class="sxs-lookup"><span data-stu-id="5028c-136">If the Calculated minimum is zero,  you can enter the desired future value.</span></span> <span data-ttu-id="5028c-137">Ad esempio, potete immettere la quantità minima calcolata in questo campo per M0002 che ha magazzino 12.</span><span class="sxs-lookup"><span data-stu-id="5028c-137">For example, you can enter the Calculated minimum quantity in this field for M0002 that has warehouse 12.</span></span>  
2. <span data-ttu-id="5028c-138">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="5028c-138">In the list, find and select the desired record.</span></span> <span data-ttu-id="5028c-139">Ad esempio, potete selezionare M0002 che ha magazzino 12.</span><span class="sxs-lookup"><span data-stu-id="5028c-139">For example, you can select M0002 that has warehouse 12.</span></span>  
3. <span data-ttu-id="5028c-140">Nel campo **Nuova quantità minima** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="5028c-140">In the **New minimum quantity** field, enter a number.</span></span> <span data-ttu-id="5028c-141">Aggiornare la Nuova quantità minima in modo che corrisponda al valore della Quantità minima calcolata.</span><span class="sxs-lookup"><span data-stu-id="5028c-141">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="5028c-142">Se il minimo calcolato è zero, potete immettere il valore futuro desiderato.</span><span class="sxs-lookup"><span data-stu-id="5028c-142">If the Calculated minimum is zero you can enter the desired future value.</span></span>  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a><span data-ttu-id="5028c-143">Inviare la nuova quantità minima e convalidare il risultato</span><span class="sxs-lookup"><span data-stu-id="5028c-143">Post the new minimum quantity and validate the result</span></span>
1. <span data-ttu-id="5028c-144">Fare clic su **Registra**.</span><span class="sxs-lookup"><span data-stu-id="5028c-144">Click **Post**.</span></span>
2. <span data-ttu-id="5028c-145">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5028c-145">Click **OK**.</span></span>
3. <span data-ttu-id="5028c-146">Fare clic per seguire il collegamento nel campo **Numero articolo**.</span><span class="sxs-lookup"><span data-stu-id="5028c-146">Click to follow the link in the **Item number** field.</span></span>
4. <span data-ttu-id="5028c-147">Fare clic per seguire il collegamento nel campo **Numero articolo**.</span><span class="sxs-lookup"><span data-stu-id="5028c-147">Click to follow the link in the **Item number** field.</span></span>
5. <span data-ttu-id="5028c-148">Nel **riquadro azioni**, fare clic su Piano.</span><span class="sxs-lookup"><span data-stu-id="5028c-148">On the **Action Pane**, click Plan.</span></span>
6. <span data-ttu-id="5028c-149">Fare clic su **Copertura articoli**.</span><span class="sxs-lookup"><span data-stu-id="5028c-149">Click **Item coverage**.</span></span> <span data-ttu-id="5028c-150">Notare che la **quantità minima** è stata aggiornata con la nuova quantità minima dal giornale di registrazione delle scorte di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5028c-150">Notice that the **Minimum quantity** has been updated with the new minimum quantity from the safety stock journal.</span></span>  

