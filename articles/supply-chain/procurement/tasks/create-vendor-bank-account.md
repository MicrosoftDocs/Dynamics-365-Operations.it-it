--- 
title: Creare un nuovo conto bancario fornitore
description: Questa procedura mostra come creare un conto bancario per un fornitore.
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: adb759c59d7275e7323dbb760de56acdef2e3cff
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-vendor-bank-account"></a><span data-ttu-id="3db7d-103">Creare un nuovo conto bancario fornitore</span><span class="sxs-lookup"><span data-stu-id="3db7d-103">Create a vendor bank account</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3db7d-104">Questa procedura mostra come creare un conto bancario per un fornitore.</span><span class="sxs-lookup"><span data-stu-id="3db7d-104">This procedure shows you how to create a bank account for a vendor.</span></span> <span data-ttu-id="3db7d-105">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="3db7d-105">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="3db7d-106">Andare ad Approvvigionamento > Fornitori > Tutti i fornitori.</span><span class="sxs-lookup"><span data-stu-id="3db7d-106">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="3db7d-107">Selezionare il fornitore per cui volete creare un conto bancario e poi fate clic sul collegamento nell'ID conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="3db7d-107">Select the vendor that you want to create a bank account for, and then click the link on the Vendor account ID.</span></span>
3. <span data-ttu-id="3db7d-108">Nel riquadro azioni, fare clic su Fornitore.</span><span class="sxs-lookup"><span data-stu-id="3db7d-108">On the Action Pane, click Vendor.</span></span>
4. <span data-ttu-id="3db7d-109">Fare clic su Conti bancari.</span><span class="sxs-lookup"><span data-stu-id="3db7d-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="3db7d-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3db7d-110">Click New.</span></span>
6. <span data-ttu-id="3db7d-111">Digitare un valore nel campo Conto bancario.</span><span class="sxs-lookup"><span data-stu-id="3db7d-111">In the Bank account field, type a value.</span></span>
    * <span data-ttu-id="3db7d-112">Questo ID sarà usato per identificare il conto bancario nel record fornitore.</span><span class="sxs-lookup"><span data-stu-id="3db7d-112">This ID will be used to identify the bank account on the vendor record.</span></span>  
7. <span data-ttu-id="3db7d-113">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="3db7d-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="3db7d-114">Nel campo gruppi bancari immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3db7d-114">In the Bank groups field, enter or select a value.</span></span>
9. <span data-ttu-id="3db7d-115">Nel campo Tipo di numero di registrazione selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="3db7d-115">In the Routing number type field, select an option.</span></span>
    * <span data-ttu-id="3db7d-116">Questo è il tipo di numero di registrazione utilizzato per i pagamenti internazionali.</span><span class="sxs-lookup"><span data-stu-id="3db7d-116">This is the type of routing number that’s used for international payments.</span></span>  
10. <span data-ttu-id="3db7d-117">Digitare un valore nel campo Numero conto bancario.</span><span class="sxs-lookup"><span data-stu-id="3db7d-117">In the Bank account number field, type a value.</span></span>
11. <span data-ttu-id="3db7d-118">Digitare un valore nel campo Codice SWIFT.</span><span class="sxs-lookup"><span data-stu-id="3db7d-118">In the SWIFT code field, type a value.</span></span>
12. <span data-ttu-id="3db7d-119">Digitare un valore nel campo IBAN.</span><span class="sxs-lookup"><span data-stu-id="3db7d-119">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="3db7d-120">Il numero IBAN deve essere nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="3db7d-120">The IBAN number must be in the correct format.</span></span> <span data-ttu-id="3db7d-121">È ad esempio possibile utilizzare DE89370400440532013000.</span><span class="sxs-lookup"><span data-stu-id="3db7d-121">For example, you could use DE89370400440532013000.</span></span>  
    * <span data-ttu-id="3db7d-122">Lo stato del conto bancario è attivo se la data di attivazione è stata raggiunta e la data di scadenza non è stata oltrepassata.</span><span class="sxs-lookup"><span data-stu-id="3db7d-122">The status of the bank account is Active if the Active date has been reached, and the Expiration date has not been exceeded.</span></span> <span data-ttu-id="3db7d-123">È inoltre attivo se entrambi i campi Data di attivazione e Data di scadenza sono vuoti.</span><span class="sxs-lookup"><span data-stu-id="3db7d-123">It’s also active if both the Active date and Expiration date fields are blank.</span></span> <span data-ttu-id="3db7d-124">Se le date incluse nei campi Data di attivazione e Data di scadenza sono entrambe successive alla data corrente, non è possibile effettuare pagamenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="3db7d-124">If the dates in both the Active date and Expiration date fields are in the future electronic payments are not available.</span></span> <span data-ttu-id="3db7d-125">Sono disponibili altri tipi di pagamento e il conto bancario è attivo.</span><span class="sxs-lookup"><span data-stu-id="3db7d-125">Other payment types are available and the bank account is active.</span></span>  
13. <span data-ttu-id="3db7d-126">Espandere la sezione Impostazione.</span><span class="sxs-lookup"><span data-stu-id="3db7d-126">Expand the Setup section.</span></span>
14. <span data-ttu-id="3db7d-127">Digitare un valore nel campo Codice di testo.</span><span class="sxs-lookup"><span data-stu-id="3db7d-127">In the Text code field, type a value.</span></span>
    * <span data-ttu-id="3db7d-128">Questo campo specifica un codice che comparirà sul rendiconto bancario del destinatario.</span><span class="sxs-lookup"><span data-stu-id="3db7d-128">This field specifies a code that will appear on the bank statement of the recipient.</span></span>  
15. <span data-ttu-id="3db7d-129">Digitare un valore nel campo Messaggio alla banca.</span><span class="sxs-lookup"><span data-stu-id="3db7d-129">In the Message to bank field, type a value.</span></span>
16. <span data-ttu-id="3db7d-130">Digitare un valore nel campo Riferimento cambio.</span><span class="sxs-lookup"><span data-stu-id="3db7d-130">In the Exchange reference field, type a value.</span></span>
    * <span data-ttu-id="3db7d-131">Questo è il numero di riferimento dell'eventuale tasso di cambio a termine o fisso.</span><span class="sxs-lookup"><span data-stu-id="3db7d-131">This is the reference number for any forward-term or fixed-term rate of exchange.</span></span>  
17. <span data-ttu-id="3db7d-132">Nel campo Valuta immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3db7d-132">In the Currency field, enter or select a value.</span></span>
    * <span data-ttu-id="3db7d-133">Quando le notifiche anticipate sono pubblicate, questa sezione fornisce una panoramica del loro stato (in sospeso o approvato).</span><span class="sxs-lookup"><span data-stu-id="3db7d-133">When prenotes are issued, this section provides an overview of their status (pending or approved).</span></span>  
18. <span data-ttu-id="3db7d-134">Espandere la sezione Indirizzo.</span><span class="sxs-lookup"><span data-stu-id="3db7d-134">Expand the Address section.</span></span>
19. <span data-ttu-id="3db7d-135">Espandere la sezione Notifiche anticipate.</span><span class="sxs-lookup"><span data-stu-id="3db7d-135">Expand the Prenotes section.</span></span>
20. <span data-ttu-id="3db7d-136">Espandere la sezione Informazioni sul contatto.</span><span class="sxs-lookup"><span data-stu-id="3db7d-136">Expand the Contact information section.</span></span>
21. <span data-ttu-id="3db7d-137">Digitare un valore nel campo Telefono.</span><span class="sxs-lookup"><span data-stu-id="3db7d-137">In the Telephone field, type a value.</span></span>
22. <span data-ttu-id="3db7d-138">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3db7d-138">Close the page.</span></span>
23. <span data-ttu-id="3db7d-139">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="3db7d-139">Click Edit.</span></span>
24. <span data-ttu-id="3db7d-140">Espandere la sezione Pagamento.</span><span class="sxs-lookup"><span data-stu-id="3db7d-140">Expand the Payment section.</span></span>
25. <span data-ttu-id="3db7d-141">Nel campo Conto bancario, selezionare il conto che avete creato appena.</span><span class="sxs-lookup"><span data-stu-id="3db7d-141">In the Bank  account field, select the account that you’ve just created.</span></span>
26. <span data-ttu-id="3db7d-142">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3db7d-142">Click Save.</span></span>
    * <span data-ttu-id="3db7d-143">L'indirizzo può essere ereditato dal gruppo di banche, se è specificato, o potete aggiungerlo qui.</span><span class="sxs-lookup"><span data-stu-id="3db7d-143">The address may be inherited from the bank group, if one is specified, or you can add it here.</span></span>  


