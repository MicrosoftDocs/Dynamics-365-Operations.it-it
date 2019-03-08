---
title: Registrare giornali periodici
description: I giornali di registrazione periodici vengono talvolta denominati giornali ricorrenti poiché l'importo, il testo e altre informazioni vengono ripetuti ogni volta che il giornale di registrazione periodico viene recuperato.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransPeriodic, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: deae523d922e1d6a4f7bb05433e9b1568c9c1ee9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "351311"
---
# <a name="post-periodic-journals"></a><span data-ttu-id="911e5-103">Registrare giornali periodici</span><span class="sxs-lookup"><span data-stu-id="911e5-103">Post periodic journals</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="911e5-104">I giornali di registrazione periodici vengono talvolta denominati giornali ricorrenti poiché l'importo, il testo e altre informazioni vengono ripetuti ogni volta che il giornale di registrazione periodico viene recuperato.</span><span class="sxs-lookup"><span data-stu-id="911e5-104">Periodic journals are sometimes called recurring journals because the amount, text, and other information are repeated each time that the periodic journal is retrieved.</span></span> <span data-ttu-id="911e5-105">Quando si crea il giornale di registrazione periodico si specifica l'intervallo periodico per la ricorrenza, ad esempio giorni o mesi.</span><span class="sxs-lookup"><span data-stu-id="911e5-105">When you create the periodic journal, you specify the period interval for the recurrence, such as days or months.</span></span> <span data-ttu-id="911e5-106">Questa guida attività consentirà di creare un giornale di registrazione periodico con una ricorrenza mensile.</span><span class="sxs-lookup"><span data-stu-id="911e5-106">This task guide will create a periodic journal with a monthly recurrence.</span></span>



1. <span data-ttu-id="911e5-107">Fare clic su Contabilità generale > Attività periodiche > Giornali di registrazione periodici.</span><span class="sxs-lookup"><span data-stu-id="911e5-107">Go to General ledger > Periodic tasks > Periodic journals.</span></span>
2. <span data-ttu-id="911e5-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="911e5-108">Click New.</span></span>
3. <span data-ttu-id="911e5-109">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="911e5-109">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="911e5-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="911e5-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="911e5-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="911e5-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="911e5-112">La descrizione consisterà nel nome del giornale di registrazione periodico quando viene recuperato in un momento successivo, quindi assicurarsi di scegliere un nome pertinente.</span><span class="sxs-lookup"><span data-stu-id="911e5-112">The description will be the name of the Periodic journal when retrieved later so make sure to give it a relevant name.</span></span>  
6. <span data-ttu-id="911e5-113">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="911e5-113">Click Lines.</span></span>
    * <span data-ttu-id="911e5-114">Un giornale di registrazione periodico in genere includerà più righe giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="911e5-114">A periodic journal will typically include several journal lines.</span></span> <span data-ttu-id="911e5-115">questa guida attività tuttavia consentirà di aggiungere una sola riga.</span><span class="sxs-lookup"><span data-stu-id="911e5-115">this task guide will however only add one line.</span></span>  
7. <span data-ttu-id="911e5-116">Nel campo Data immettere una data.</span><span class="sxs-lookup"><span data-stu-id="911e5-116">In the Date field, enter a date.</span></span>
    * <span data-ttu-id="911e5-117">Il campo Data contiene la data di registrazione per il successivo trasferimento nel giornale di registrazione giornaliero.</span><span class="sxs-lookup"><span data-stu-id="911e5-117">The Date field contains the posting date for the next transfer to the daily journal.</span></span> <span data-ttu-id="911e5-118">Per i giornali di registrazione che verranno recuperati ogni mese si consiglia di utilizzare la data del mese in cui verranno registrati, in genere la prima o l'ultima data del periodo.</span><span class="sxs-lookup"><span data-stu-id="911e5-118">For journals that will be retrieved each month it is recommended to use the date in the month when it will be posted, typically the first or last date in the period.</span></span> <span data-ttu-id="911e5-119">È possibile lasciare vuoto il campo Data e immettere una data in cui il giornale di registrazione viene recuperato, utilizzando il campo data Vuoto.</span><span class="sxs-lookup"><span data-stu-id="911e5-119">It is possible to leave the Date field blank and to give a date when the journal is retrieved, using the Empty date field.</span></span>    <span data-ttu-id="911e5-120">Il campo viene aggiornato automaticamente alla data ricorrente successiva in cui le transazioni vengono recuperate.</span><span class="sxs-lookup"><span data-stu-id="911e5-120">The field is automatically updated to the next recurring date when transactions are retrieved.</span></span>  
8. <span data-ttu-id="911e5-121">Nel campo Conto, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="911e5-121">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="911e5-122">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="911e5-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="911e5-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="911e5-123">Close the page.</span></span>
11. <span data-ttu-id="911e5-124">Nel campo Dare immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="911e5-124">In the Debit field, enter a number.</span></span>
12. <span data-ttu-id="911e5-125">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="911e5-125">In the Offset account field, specify the desired values.</span></span>
13. <span data-ttu-id="911e5-126">Nel campo Unità selezionare "Mesi".</span><span class="sxs-lookup"><span data-stu-id="911e5-126">In the Unit field, select 'Months'.</span></span>
14. <span data-ttu-id="911e5-127">Nel campo Numero di unità immettere "1".</span><span class="sxs-lookup"><span data-stu-id="911e5-127">In the Number of units field, enter '1'.</span></span>
15. <span data-ttu-id="911e5-128">Nel campo Ultima data immettere una data.</span><span class="sxs-lookup"><span data-stu-id="911e5-128">In the Last date field, enter a date.</span></span>
    * <span data-ttu-id="911e5-129">L'immissione dell'ultima data nel periodo precedente impedirà che il giornale di registrazione ricorrente venga per errore creato nel periodo iniziale sbagliato.</span><span class="sxs-lookup"><span data-stu-id="911e5-129">Entering last date in the preceding period will prevent that the recurring journal by mistake is created in the wrong starting period.</span></span> <span data-ttu-id="911e5-130">L'ultima data verrà successivamente aggiornata ogni volta che il giornale di registrazione periodico viene recuperato.</span><span class="sxs-lookup"><span data-stu-id="911e5-130">Last date will later on be updated each time the periodic journal is retrieved.</span></span>  
16. <span data-ttu-id="911e5-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="911e5-131">Click Save.</span></span>
17. <span data-ttu-id="911e5-132">Fare clic su Dashboard predefinito.</span><span class="sxs-lookup"><span data-stu-id="911e5-132">Go to Default dashboard.</span></span>
18. <span data-ttu-id="911e5-133">Fare clic su Contabilità generale > Scritture contabili > Giornali di registrazione generali.</span><span class="sxs-lookup"><span data-stu-id="911e5-133">Go to General ledger > Journal entries > General journals.</span></span>
19. <span data-ttu-id="911e5-134">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="911e5-134">Click New.</span></span>
20. <span data-ttu-id="911e5-135">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="911e5-135">In the Name field, enter or select a value.</span></span>
21. <span data-ttu-id="911e5-136">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="911e5-136">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="911e5-137">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="911e5-137">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="911e5-138">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="911e5-138">In the Description field, type a value.</span></span>
24. <span data-ttu-id="911e5-139">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="911e5-139">Click Lines.</span></span>
25. <span data-ttu-id="911e5-140">Fare clic su Giornale di registrazione periodico.</span><span class="sxs-lookup"><span data-stu-id="911e5-140">Click Period journal.</span></span>
26. <span data-ttu-id="911e5-141">Fare clic su Recupera giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="911e5-141">Click Retrieve journal.</span></span>
27. <span data-ttu-id="911e5-142">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="911e5-142">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="911e5-143">La data finale funge da data limite per le righe periodiche di giustificativo.</span><span class="sxs-lookup"><span data-stu-id="911e5-143">The To date serves as the cutoff date for the periodic voucher lines.</span></span> <span data-ttu-id="911e5-144">In base all'impostazione della ricorrenza, l'ultima data e la data finale, la stessa riga può essere inclusa più volte nel giornale di registrazione risultante.</span><span class="sxs-lookup"><span data-stu-id="911e5-144">Based on the recurrence setting, the Last date and To date the same line might be included more than once in the resulting journal.</span></span> <span data-ttu-id="911e5-145">La data finale viene automaticamente aggiornata in base alla data della sessione in cui è stato effettuato l'ultimo trasferimento della riga del giornale di registrazione periodico in un giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="911e5-145">To date is automatically updated based on  session date of the last time the periodic line was transferred to a journal.</span></span>  
28. <span data-ttu-id="911e5-146">Nel campo Numero giornale di registrazione periodico immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="911e5-146">In the Periodic journal number field, enter or select a value.</span></span>
29. <span data-ttu-id="911e5-147">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="911e5-147">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="911e5-148">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="911e5-148">Click OK.</span></span>
    * <span data-ttu-id="911e5-149">Il giornale di registrazione periodico può ora essere rivisto, approvato o registrato a seconda del fabbisogno e dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="911e5-149">The period journal can now be reviewed, approved or posted depending on requirement and setup.</span></span>  

