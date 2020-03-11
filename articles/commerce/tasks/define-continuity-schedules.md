---
title: " Definire programmazioni di continuità"
description: In questo argomento si descrive l'impostazione di un programma di continuità (altrimenti detto ordini ricorrenti).
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRContinuitySchedule, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a438656730863f345080bc99fef24cfff724f528
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023032"
---
# <a name="define-continuity-schedules"></a><span data-ttu-id="8c288-103"> Definire programmazioni di continuità</span><span class="sxs-lookup"><span data-stu-id="8c288-103">Define continuity schedules</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="8c288-104">In questo argomento si descrive l'impostazione di un programma di continuità (altrimenti detto ordini ricorrenti).</span><span class="sxs-lookup"><span data-stu-id="8c288-104">This topic walks through setting up a continuity program (otherwise known as reoccurring orders).</span></span> <span data-ttu-id="8c288-105">Questo argomento utilizza la società USRT nei dati dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="8c288-105">This topic uses company USRT in the demo data.</span></span>


## <a name="create-continuity-program"></a><span data-ttu-id="8c288-106">Creare un programma di continuità</span><span class="sxs-lookup"><span data-stu-id="8c288-106">Create continuity program</span></span>
1. <span data-ttu-id="8c288-107">Passare a Retail e Commerce > Continuità > Programmi di continuità.</span><span class="sxs-lookup"><span data-stu-id="8c288-107">Go to Retail and Commerce > Continuity > Continuity programs.</span></span>
2. <span data-ttu-id="8c288-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8c288-108">Click New.</span></span>
3. <span data-ttu-id="8c288-109">Nel campo ID programmazione, digitare l'ID programmazione di continuità.</span><span class="sxs-lookup"><span data-stu-id="8c288-109">In the Schedule ID field, type the continuity schedule ID.</span></span>
4. <span data-ttu-id="8c288-110">Nel campo Inizio ordine selezionare 'Primo evento'.</span><span class="sxs-lookup"><span data-stu-id="8c288-110">In the Order start field, select 'First event'.</span></span>
    * <span data-ttu-id="8c288-111">Se un cliente effettua un nuovo ordine per il programma di continuità, sono disponibili due opzioni per cui il prodotto verrà spedito:  1</span><span class="sxs-lookup"><span data-stu-id="8c288-111">If a customer places a new order for the continuity program, there are two options for which product will be shipped:  1.</span></span> <span data-ttu-id="8c288-112">Primo evento: il primo prodotto nel programma di continuità verrà spedito.</span><span class="sxs-lookup"><span data-stu-id="8c288-112">First event: the first product in the continuity program will be shipped.</span></span>  <span data-ttu-id="8c288-113">2</span><span class="sxs-lookup"><span data-stu-id="8c288-113">2.</span></span> <span data-ttu-id="8c288-114">Evento esistente: il prodotto corrente verrà spedito.</span><span class="sxs-lookup"><span data-stu-id="8c288-114">Current event: the current product will be shipped.</span></span> <span data-ttu-id="8c288-115">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="8c288-115">For example.</span></span> <span data-ttu-id="8c288-116">tre mesi nel programma, il cliente riceverà il terzo nel programma.</span><span class="sxs-lookup"><span data-stu-id="8c288-116">three months into the program, the customer will receive the third in the program.</span></span>  
5. <span data-ttu-id="8c288-117">Selezionare 'Sì' per richiedere la data di inizio dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="8c288-117">Select 'Yes' to prompt for the order start date.</span></span>
6. <span data-ttu-id="8c288-118">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="8c288-118">Click Add line.</span></span>
7. <span data-ttu-id="8c288-119">Nel campo Numero articolo digitare il numero di articolo per il primo prodotto ('0013').</span><span class="sxs-lookup"><span data-stu-id="8c288-119">In the Item number field, type the item number for the first product ('0013').</span></span>
8. <span data-ttu-id="8c288-120">Digitare 'CP'.</span><span class="sxs-lookup"><span data-stu-id="8c288-120">Type 'CP'.</span></span>
9. <span data-ttu-id="8c288-121">Immettere la data in cui il primo prodotto sarà disponibile per l'ordine.</span><span class="sxs-lookup"><span data-stu-id="8c288-121">Enter the date when the first product will be available for order.</span></span>
10. <span data-ttu-id="8c288-122">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="8c288-122">Click Add line.</span></span>
11. <span data-ttu-id="8c288-123">Nel campo Numero articolo digitare '0014'.</span><span class="sxs-lookup"><span data-stu-id="8c288-123">In the Item number field, type '0014'.</span></span>
12. <span data-ttu-id="8c288-124">Nel campo Codice intervallo date, cancellare il valore in modo che il campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="8c288-124">In the Date interval code field, clear the value so the field is empty.</span></span>
    * <span data-ttu-id="8c288-125">Per questa procedura, deselezionare l'intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="8c288-125">For this procedure, clear the date interval.</span></span> <span data-ttu-id="8c288-126">Fisserete la data come incrementale dalla data di inizio del primo articolo.</span><span class="sxs-lookup"><span data-stu-id="8c288-126">You'll set the date as incremental from the start date of the first item.</span></span>  
13. <span data-ttu-id="8c288-127">Qui immettere l'intervallo a cui i prodotti sono spediti.</span><span class="sxs-lookup"><span data-stu-id="8c288-127">Here you'll enter the interval at which the products are shipped.</span></span> <span data-ttu-id="8c288-128">Digitare '30'.</span><span class="sxs-lookup"><span data-stu-id="8c288-128">Type '30'.</span></span>
    * <span data-ttu-id="8c288-129">Per un programma mensile, immettere 30 giorni per l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="8c288-129">For a monthly program, you'll enter 30 days for the interval.</span></span>  
14. <span data-ttu-id="8c288-130">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="8c288-130">Click Add line.</span></span>
15. <span data-ttu-id="8c288-131">Nel campo Numero articolo digitare '0015'.</span><span class="sxs-lookup"><span data-stu-id="8c288-131">In the Item number field, type '0015'.</span></span>
16. <span data-ttu-id="8c288-132">Digitare 'Fine'.</span><span class="sxs-lookup"><span data-stu-id="8c288-132">Type 'End'.</span></span>
17. <span data-ttu-id="8c288-133">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8c288-133">Click Save.</span></span>

## <a name="assign-to-continuity-item"></a><span data-ttu-id="8c288-134">Assegnare all'articolo di continuità</span><span class="sxs-lookup"><span data-stu-id="8c288-134">Assign to continuity item</span></span>
1. <span data-ttu-id="8c288-135">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="8c288-135">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="8c288-136">Selezionare l'articolo '0016'.</span><span class="sxs-lookup"><span data-stu-id="8c288-136">Select item '0016'.</span></span>
    * <span data-ttu-id="8c288-137">Per questa procedura, selezionerete il numero di articolo 0016.</span><span class="sxs-lookup"><span data-stu-id="8c288-137">For this procedure, you'll select item number 0016.</span></span> <span data-ttu-id="8c288-138">In genere, si sarà creato un prodotto rilasciato a cui è applicata la logica di business di continuità aggiuntiva quando viene inserito in un ordine cliente nel servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="8c288-138">Normally, you'll have created a released product that has additional continuity business logic applied when it's placed on a sales order in call center.</span></span>  
3. <span data-ttu-id="8c288-139">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8c288-139">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="8c288-140">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="8c288-140">Click Edit.</span></span>
5. <span data-ttu-id="8c288-141">Espandere o comprimere la sezione Vendi.</span><span class="sxs-lookup"><span data-stu-id="8c288-141">Expand or collapse the Sell section.</span></span>
6. <span data-ttu-id="8c288-142">Qui immettere il programma di continuità che l'articolo rappresenta.</span><span class="sxs-lookup"><span data-stu-id="8c288-142">Here you'll enter the continuity program that this item represents.</span></span> <span data-ttu-id="8c288-143">Immettere l'ID programmazione creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8c288-143">Type the Schedule ID you created earlier.</span></span>
    * <span data-ttu-id="8c288-144">Quando l'articolo viene venduto da un servizio clienti, la logica di business aggiuntiva viene applicata dal programma di continuità selezionato.</span><span class="sxs-lookup"><span data-stu-id="8c288-144">When this item is sold in a call center, additional business logic is applied from the selected continuity program.</span></span>  
7. <span data-ttu-id="8c288-145">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8c288-145">Click Save.</span></span>
