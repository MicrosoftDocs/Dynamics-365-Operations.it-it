---
title: Creare una sequenza di lettere di sollecito
description: Utilizzare la guida attività per creare una sequenza delle lettere di sollecito.
author: mikefalkner
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CollectionLetterCourse
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db5264f6d8d7723ff01d13e99728c2bfebcb4515
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "311567"
---
# <a name="create-a-collection-letter-sequence"></a><span data-ttu-id="24607-103">Creare una sequenza di lettere di sollecito</span><span class="sxs-lookup"><span data-stu-id="24607-103">Create a collection letter sequence</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="24607-104">Utilizzare la guida attività per creare una sequenza delle lettere di sollecito.</span><span class="sxs-lookup"><span data-stu-id="24607-104">Use this task guide to create a collection letter sequence.</span></span> <span data-ttu-id="24607-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="24607-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="24607-106">Andare a Crediti e riscossioni > Impostazioni > Imposta la sequenza lettere di sollecito.</span><span class="sxs-lookup"><span data-stu-id="24607-106">Go to Credit and collections > Setup > Set up collection letter sequence.</span></span>
2. <span data-ttu-id="24607-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="24607-107">Click New.</span></span>
3. <span data-ttu-id="24607-108">Nel campo Sequenza lettere di sollecito, immettere un ID sequenza che rappresenterà la sequenza.</span><span class="sxs-lookup"><span data-stu-id="24607-108">In the Collection letter sequence field, enter a sequence ID that will represent the sequence.</span></span> <span data-ttu-id="24607-109">Verrà utilizzato quando si imposta un profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="24607-109">It will be used when you set up a posting profile.</span></span>
4. <span data-ttu-id="24607-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="24607-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="24607-111">I termini di pagamento sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="24607-111">The terms of payment is optional.</span></span> <span data-ttu-id="24607-112">Se si immette un valore in questo campo, la fattura di addebito lettera di sollecito utilizzerà questi termini di pagamento anziché i termini di pagamento archiviati con il cliente.</span><span class="sxs-lookup"><span data-stu-id="24607-112">If you enter a value here, the collection letter fee invoice will use these terms of payment instead of the terms of payment stored with the customer.</span></span>  
5. <span data-ttu-id="24607-113">Nel campo Codice lettera di sollecito selezionare il codice per la prima lettera di sollecito che si desidera inviare.</span><span class="sxs-lookup"><span data-stu-id="24607-113">In the collection letter code field, select the code for the first collection letter that you want to send.</span></span>
    * <span data-ttu-id="24607-114">La prima nota d'interesse viene creata in base alla data di scadenza riportata sulla fattura, al valore specificato per il periodo di tolleranza nel campo Giorni e alle altre informazioni immesse in questa riga.</span><span class="sxs-lookup"><span data-stu-id="24607-114">The first collection letter is created according to the due date on the invoice, the value that you enter for the grace period in the Days field on this line, and other information that you enter on this line.</span></span>  
6. <span data-ttu-id="24607-115">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="24607-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="24607-116">La valuta per le impostazioni predefinite della commissione nella valuta del cliente.</span><span class="sxs-lookup"><span data-stu-id="24607-116">The currency for the fee defaults to the customer currency.</span></span> <span data-ttu-id="24607-117">Questo codice valuta può essere diverso dalla valuta della fattura.</span><span class="sxs-lookup"><span data-stu-id="24607-117">This currency code can be different than the invoice currency.</span></span>  
7. <span data-ttu-id="24607-118">Fare clic su Aggiungi per aggiungere la lettera di sollecito successiva che verrà inviata nella sequenza</span><span class="sxs-lookup"><span data-stu-id="24607-118">Click Add to add the next collection letter that will be sent in the sequence</span></span>
    * <span data-ttu-id="24607-119">In molti casi, la prima lettera di sollecito è soltanto un avviso.</span><span class="sxs-lookup"><span data-stu-id="24607-119">In many cases, the first collection letter is just a warning.</span></span> <span data-ttu-id="24607-120">È possibile aggiungere le commissioni se necessario.</span><span class="sxs-lookup"><span data-stu-id="24607-120">You can add fees if needed.</span></span>  
8. <span data-ttu-id="24607-121">Nel campo Codice lettera di sollecito selezionare la lettera di sollecito successiva che verrà inviata nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="24607-121">In the collection letter code field, select the next collection letter that will be sent in the sequence.</span></span>
9. <span data-ttu-id="24607-122">Digitare un valore nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="24607-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="24607-123">Nel campo Conto principale, selezionare il conto ricavi che verrà utilizzato per le commissioni.</span><span class="sxs-lookup"><span data-stu-id="24607-123">In the main account field, select the revenue account that will be used for fees.</span></span>
11. <span data-ttu-id="24607-124">Immettere la commissione che verrà addebitata quando la lettera di sollecito viene registrata.</span><span class="sxs-lookup"><span data-stu-id="24607-124">Enter the fee that will be charged when this collection letter is posted.</span></span>
12. <span data-ttu-id="24607-125">Nel campo Fascia IVA articoli fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="24607-125">In the Item sales tax group field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="24607-126">Selezionare una fascia IVA articoli se l'IVA deve essere calcolata sulla commissione.</span><span class="sxs-lookup"><span data-stu-id="24607-126">Select an item sales tax group if sales taxes must be calculated on the fee.</span></span>  
13. <span data-ttu-id="24607-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="24607-127">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="24607-128">Immettere il saldo scaduto minimo necessario prima che venga inviata una lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="24607-128">Enter the minimum overdue balance required before a collection letter is sent.</span></span>
15. <span data-ttu-id="24607-129">Immettere il numero di giorni di tolleranza da consentire.</span><span class="sxs-lookup"><span data-stu-id="24607-129">Enter the number of grace days that you will allow.</span></span>
    * <span data-ttu-id="24607-130">Questo è il numero di giorni dopo la data di scadenza in cui una lettera di sollecito può essere generata.</span><span class="sxs-lookup"><span data-stu-id="24607-130">This is the number of days after the due date that a collection letter can be generated.</span></span> <span data-ttu-id="24607-131">La data di scadenza utilizzata per il calcolo dipende dalla posizione della lettera di sollecito nella sequenza delle lettere di sollecito: ⦁ Il periodo di tolleranza della lettera di sollecito 1 è relativo alla data di scadenza della fattura.</span><span class="sxs-lookup"><span data-stu-id="24607-131">The due date that is used for the calculation depends on the position of the collection letter in the collection letter sequence:   ⦁    The grace period for collection letter 1 is relative to the due date on the invoice.</span></span>  <span data-ttu-id="24607-132">⦁ Il periodo di tolleranza per le lettere di sollecito 2 e superiori è in relazione alla data di registrazione e stampa della lettera di sollecito precedente, a seconda della selezione nel campo Aggiorna codice lettera di sollecito nella pagina Parametri contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="24607-132">⦁ The grace period for collection letters 2 and higher is relative to the date that the previous collection letter is posted or printed, depending on the selection in the Update collection letter code field in the Accounts receivable parameters page.</span></span>  
16. <span data-ttu-id="24607-133">Fare clic su Aggiungi per aggiungere l'ultima lettera di sollecito nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="24607-133">Click Add to add the last collection letter in the sequence.</span></span>
    * <span data-ttu-id="24607-134">Per una sequenza di lettere di sollecito è possibile aggiungere fino a cinque codici lettera di sollecito.</span><span class="sxs-lookup"><span data-stu-id="24607-134">You can add up to five collection letter codes for a collection letter sequence.</span></span>  
17. <span data-ttu-id="24607-135">Nel campo Codice lettera di sollecito selezionare la lettera di sollecito successiva che verrà inviata nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="24607-135">In the collection letter code field, select the next collection letter that will be sent in the sequence.</span></span>
18. <span data-ttu-id="24607-136">Digitare un valore nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="24607-136">In the Description field, type a value.</span></span>
19. <span data-ttu-id="24607-137">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="24607-137">In the Main account field, specify the desired values.</span></span>
20. <span data-ttu-id="24607-138">Nel campo Addebito in valuta immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="24607-138">In the Fee in currency field, enter a number.</span></span>
21. <span data-ttu-id="24607-139">Nel campo Fascia IVA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="24607-139">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="24607-140">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="24607-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="24607-141">Nel campo Saldo scaduto minimo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="24607-141">In the Minimum overdue balance field, enter a number.</span></span>
24. <span data-ttu-id="24607-142">Nel campo Giorni immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="24607-142">In the Days field, enter a number.</span></span>
25. <span data-ttu-id="24607-143">Selezionare la casella di controllo per impedire al cliente di effettuare operazioni di consegna e fatturazione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="24607-143">Select this check box to stop the customer from additional deliveries and invoicing.</span></span>
    * <span data-ttu-id="24607-144">Per sbloccare il conto, selezionare No nel campo Fatturazione e consegna in attesa della pagina Clienti.</span><span class="sxs-lookup"><span data-stu-id="24607-144">To unblock the account, select No in the Invoicing and delivery on hold field in the Customers page.</span></span>  
26. <span data-ttu-id="24607-145">Espandere la Scheda dettaglio Nota.</span><span class="sxs-lookup"><span data-stu-id="24607-145">Expand the Note fasttab.</span></span>
27. <span data-ttu-id="24607-146">Immettere il testo da visualizzare sulla lettera di sollecito per il codice lettera di sollecito selezionato.</span><span class="sxs-lookup"><span data-stu-id="24607-146">Enter the text to appear on the collection letter for the selected collection letter code.</span></span>
    * <span data-ttu-id="24607-147">È possibile tradurre il testo in più lingue utilizzando il menu Traduzioni sopra la casella della nota.</span><span class="sxs-lookup"><span data-stu-id="24607-147">You can translate this text in to multiple languages using the Translations menu above the note box.</span></span>  

