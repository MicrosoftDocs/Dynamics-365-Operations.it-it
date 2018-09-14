--- 
title: "Impostare i conti bancari della società per gli addebiti diretti ISO20022"
description: "Questa attività descrive l'impostazione delle informazioni sui conti bancari specifici della società necessarie per la creazione dei file di pagamento cliente."
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 290d0eeb383dc3808935809e21b1bf6c99a8550a
ms.contentlocale: it-it
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a><span data-ttu-id="2784a-103">Impostare i conti bancari della società per gli addebiti diretti ISO20022</span><span class="sxs-lookup"><span data-stu-id="2784a-103">Set up company bank accounts for ISO20022 direct debits</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2784a-104">Questa attività descrive l'impostazione delle informazioni sui conti bancari specifici della società necessarie per la creazione dei file di pagamento cliente.</span><span class="sxs-lookup"><span data-stu-id="2784a-104">This task walks you through setting up the company specific bank account information that is required for generating customer payment files.</span></span> <span data-ttu-id="2784a-105">In questa procedura viene utilizzato il formato di pagamento in addebito diretto ISO 20022 come esempio.</span><span class="sxs-lookup"><span data-stu-id="2784a-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> <span data-ttu-id="2784a-106">Altri formati possono richiedere informazioni di impostazione aggiuntive come l'ID società o il Codice di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="2784a-106">Other formats might require additional setup information like the Company ID or the Sort code.</span></span>



<span data-ttu-id="2784a-107">Questa attività è stata creata utilizzando la società di dati dimostrativi DEMF.</span><span class="sxs-lookup"><span data-stu-id="2784a-107">This task was created using the demo data company DEMF.</span></span>



<span data-ttu-id="2784a-108">Si tratta della seconda di cinque procedure che illustrano il processo di pagamento cliente utilizzando le configurazioni di creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="2784a-108">This is the second of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>


## <a name="set-up-the-iban-and-swift-codes"></a><span data-ttu-id="2784a-109">Impostare i codici IBAN e SWIFT</span><span class="sxs-lookup"><span data-stu-id="2784a-109">Set up the IBAN and SWIFT codes</span></span>
1. <span data-ttu-id="2784a-110">Andare a Gestione banche e di cassa > Conti bancari.</span><span class="sxs-lookup"><span data-stu-id="2784a-110">Go to Cash and bank management > Bank accounts.</span></span>
2. <span data-ttu-id="2784a-111">Utilizzare il filtro rapido per applicare un filtro al campo Conto bancario in base al valore "DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="2784a-111">Use the Quick Filter to filter on the Bank account field with a value of 'DEMF OPER'.</span></span>
3. <span data-ttu-id="2784a-112">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2784a-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2784a-113">Ad esempio fare clic su 'DEMF OPER' per aprire i dettagli del conto bancario.</span><span class="sxs-lookup"><span data-stu-id="2784a-113">For example, click 'DEMF OPER' to open the bank account details.</span></span>  
4. <span data-ttu-id="2784a-114">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="2784a-114">Click Edit.</span></span>
5. <span data-ttu-id="2784a-115">Espandere o comprimere la sezione Identificazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="2784a-115">Expand or collapse the Additional identification section.</span></span>
6. <span data-ttu-id="2784a-116">Digitare un valore nel campo IBAN.</span><span class="sxs-lookup"><span data-stu-id="2784a-116">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="2784a-117">Ad esempio, immettere 'DE89370400440532013000'.</span><span class="sxs-lookup"><span data-stu-id="2784a-117">For example, enter 'DE89370400440532013000'.</span></span>  
7. <span data-ttu-id="2784a-118">Digitare un valore nel campo Codice SWIFT.</span><span class="sxs-lookup"><span data-stu-id="2784a-118">In the SWIFT code field, type a value.</span></span>
    * <span data-ttu-id="2784a-119">Ad esempio, immettere 'DEUTDEFF'.</span><span class="sxs-lookup"><span data-stu-id="2784a-119">For example, enter 'DEUTDEFF'.</span></span>    <span data-ttu-id="2784a-120">Si noti che SWIFT\BIC non è obbligatorio per numerosi formati di pagamento, tuttavia è consigliabile registrarlo per un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="2784a-120">Please note that SWIFT \ BIC is not mandatory for many payment formats however it is recommended to have it registered for a bank account.</span></span>  
8. <span data-ttu-id="2784a-121">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2784a-121">Click Save.</span></span>

## <a name="set-up-a-bank-account-for-the-legal-entity"></a><span data-ttu-id="2784a-122">Impostare un conto bancario per la persona giuridica</span><span class="sxs-lookup"><span data-stu-id="2784a-122">Set up a bank account for the legal entity</span></span>
1. <span data-ttu-id="2784a-123">Andare ad Amministrazione organizzazione > Organizzazioni > Persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="2784a-123">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="2784a-124">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="2784a-124">Click Edit.</span></span>
3. <span data-ttu-id="2784a-125">Espandere o comprimere la sezione Informazioni conto bancario.</span><span class="sxs-lookup"><span data-stu-id="2784a-125">Expand or collapse the Bank account information section.</span></span>
4. <span data-ttu-id="2784a-126">Nel campo Conto bancario fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2784a-126">In the Bank account field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="2784a-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2784a-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2784a-128">Ad esempio selezionare il conto bancario "DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="2784a-128">For example, select the "DEMF OPER" bank account.</span></span>  
6. <span data-ttu-id="2784a-129">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2784a-129">Click Save.</span></span>


