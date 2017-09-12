--- 
title: Impostare i clienti e i conti bancari dei clienti per gli addebiti diretti ISO20022
description: "Questa attività descrive l'impostazione di un conto bancario cliente e un mandato di addebito diretto cliente necessari per generare il file di pagamento cliente come addebito diretto ISO20022."
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 52970c54849e91c5052ad61ffc6458e646cbb262
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a><span data-ttu-id="1adb2-103">Impostare i clienti e i conti bancari dei clienti per gli addebiti diretti ISO20022</span><span class="sxs-lookup"><span data-stu-id="1adb2-103">Set up customers and customer bank accounts for ISO20022 direct debits</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1adb2-104">Questa attività descrive l'impostazione di un conto bancario cliente e un mandato di addebito diretto cliente necessari per generare il file di pagamento cliente come addebito diretto ISO20022.</span><span class="sxs-lookup"><span data-stu-id="1adb2-104">This task walks you through setting up a customer bank account and a customer direct debit mandate which are required to generate the customer payment file like ISO20022 direct debit.</span></span> <span data-ttu-id="1adb2-105">A seconda dei formati di pagamento del cliente impostati, informazioni aggiuntive, non coperte in questa procedura, possono essere necessarie per un cliente o conto bancario cliente.</span><span class="sxs-lookup"><span data-stu-id="1adb2-105">Depending on the customer payment formats tha are set up, additional information, not covered in this procedure, might be required for a customer or a customer bank account.</span></span> 

<span data-ttu-id="1adb2-106">Questa attività è stata creata utilizzando la società di dati dimostrativi DEMF con l'indirizzo principale della persona giuridica in Germania.</span><span class="sxs-lookup"><span data-stu-id="1adb2-106">This task was created using the demo data company DEMF with a legal entity primary address in Germany.</span></span>



<span data-ttu-id="1adb2-107">Si tratta della quarta di cinque procedure che illustrano il processo di pagamento cliente utilizzando le configurazioni di creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="1adb2-107">This is the fourth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>


## <a name="set-up-a-customer-bank-account"></a><span data-ttu-id="1adb2-108">Impostare un conto bancario cliente</span><span class="sxs-lookup"><span data-stu-id="1adb2-108">Set up a customer bank account</span></span>
1. <span data-ttu-id="1adb2-109">Andare a Contabilità clienti > Clienti > Tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="1adb2-109">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="1adb2-110">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="1adb2-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="1adb2-111">Ad esempio, applicare un filtro al campo Conto in base al valore "DE-010".</span><span class="sxs-lookup"><span data-stu-id="1adb2-111">For example, filter on the Account field with a value of 'DE-010 '.</span></span>
3. <span data-ttu-id="1adb2-112">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1adb2-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="1adb2-113">Nel riquadro azioni fare clic su Cliente.</span><span class="sxs-lookup"><span data-stu-id="1adb2-113">On the Action Pane, click Customer.</span></span>
5. <span data-ttu-id="1adb2-114">Fare clic su Conti bancari.</span><span class="sxs-lookup"><span data-stu-id="1adb2-114">Click Bank accounts.</span></span>
6. <span data-ttu-id="1adb2-115">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="1adb2-115">Click New.</span></span>
7. <span data-ttu-id="1adb2-116">Digitare un valore nel campo Conto bancario.</span><span class="sxs-lookup"><span data-stu-id="1adb2-116">In the Bank account field, type a value.</span></span>
8. <span data-ttu-id="1adb2-117">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="1adb2-117">In the Name field, type a value.</span></span>
    * <span data-ttu-id="1adb2-118">Immettere ad esempio 'EUR bank'.</span><span class="sxs-lookup"><span data-stu-id="1adb2-118">For example, enter 'EUR bank'.</span></span>  
9. <span data-ttu-id="1adb2-119">Nel campo gruppi bancari immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1adb2-119">In the Bank groups field, enter or select a value.</span></span>
10. <span data-ttu-id="1adb2-120">Digitare un valore nel campo IBAN.</span><span class="sxs-lookup"><span data-stu-id="1adb2-120">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="1adb2-121">Ad esempio, immettere 'DE36200400000628808808'.</span><span class="sxs-lookup"><span data-stu-id="1adb2-121">For example, enter 'DE36200400000628808808'.</span></span>  
11. <span data-ttu-id="1adb2-122">Digitare un valore nel campo Codice SWIFT.</span><span class="sxs-lookup"><span data-stu-id="1adb2-122">In the SWIFT code field, type a value.</span></span>
    * <span data-ttu-id="1adb2-123">Ad esempio, immettere "COBADEFFXXX".</span><span class="sxs-lookup"><span data-stu-id="1adb2-123">For example: Enter 'COBADEFFXXX'.</span></span>  <span data-ttu-id="1adb2-124">Si noti che SWIFT\BIC non è obbligatorio per numerosi formati di pagamento, tuttavia è consigliabile registrarlo per un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="1adb2-124">Please note that SWIFT \ BIC is not mandatory for many payment formats however it is recommended to have it registered for a bank account.</span></span>  
12. <span data-ttu-id="1adb2-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="1adb2-125">Click Save.</span></span>
13. <span data-ttu-id="1adb2-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1adb2-126">Close the page.</span></span>
14. <span data-ttu-id="1adb2-127">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="1adb2-127">Click Edit.</span></span>
15. <span data-ttu-id="1adb2-128">Espandere la sezione Impostazioni predefinite pagamento.</span><span class="sxs-lookup"><span data-stu-id="1adb2-128">Expand the Payment defaults section.</span></span>
16. <span data-ttu-id="1adb2-129">Nel campo Conto bancario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1adb2-129">In the Bank account field, enter or select a value.</span></span>

## <a name="add-a-direct-debit-mandate"></a><span data-ttu-id="1adb2-130">Aggiungere un mandato di addebito diretto</span><span class="sxs-lookup"><span data-stu-id="1adb2-130">Add a direct debit mandate</span></span>
1. <span data-ttu-id="1adb2-131">Espandere la sezione Mandati di addebito diretto.</span><span class="sxs-lookup"><span data-stu-id="1adb2-131">Expand the Direct debit mandates section.</span></span>
2. <span data-ttu-id="1adb2-132">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="1adb2-132">Click Add.</span></span>
3. <span data-ttu-id="1adb2-133">Nel campo Conto bancario del creditore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1adb2-133">In the Creditor bank account field, enter or select a value.</span></span>
    * <span data-ttu-id="1adb2-134">Selezionare, ad esempio DEMF OPER.</span><span class="sxs-lookup"><span data-stu-id="1adb2-134">For example, select DEMF OPER.</span></span>  
4. <span data-ttu-id="1adb2-135">Immettere una data nel campo Data di firma.</span><span class="sxs-lookup"><span data-stu-id="1adb2-135">In the Signature date field, enter a date.</span></span>
5. <span data-ttu-id="1adb2-136">Fare clic su Sì per confermare l'aggiornamento della data.</span><span class="sxs-lookup"><span data-stu-id="1adb2-136">Click Yes to confirm the date update.</span></span>
6. <span data-ttu-id="1adb2-137">Nel campo Luogo di firma immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1adb2-137">In the Signature location field, enter or select a value.</span></span>
7. <span data-ttu-id="1adb2-138">Nel campo Numero di pagamenti previsto immettere un numero</span><span class="sxs-lookup"><span data-stu-id="1adb2-138">In the Expected number of payments field, enter a number.</span></span>
8. <span data-ttu-id="1adb2-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="1adb2-139">Click OK.</span></span>
9. <span data-ttu-id="1adb2-140">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="1adb2-140">Click Save.</span></span>

