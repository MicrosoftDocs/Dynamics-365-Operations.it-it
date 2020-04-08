---
title: Definire commissioni pagamento fornitore
description: Impostare commissione pagamento fornitore.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 404bd1e22caa8098f114a2dcc67dd420509cce2b
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140469"
---
# <a name="define-vendor-payment-fees"></a><span data-ttu-id="f76ec-103">Definire commissioni pagamento fornitore</span><span class="sxs-lookup"><span data-stu-id="f76ec-103">Define vendor payment fees</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f76ec-104">Impostare commissione pagamento fornitore.</span><span class="sxs-lookup"><span data-stu-id="f76ec-104">Set up vendor payment fees.</span></span> <span data-ttu-id="f76ec-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="f76ec-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="f76ec-106">Andare a Contabilità fornitori > Impostazione pagamenti > Commissione di pagamento.</span><span class="sxs-lookup"><span data-stu-id="f76ec-106">Go to Accounts payable > Payment setup > Payment fee.</span></span>
2. <span data-ttu-id="f76ec-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="f76ec-107">Click New.</span></span>
3. <span data-ttu-id="f76ec-108">Digitare un valore nel campo ID commissione.</span><span class="sxs-lookup"><span data-stu-id="f76ec-108">In the Fee ID field, type a value.</span></span>
    * <span data-ttu-id="f76ec-109">L'ID della commissione deve descrivere quando la commissione verrà utilizzata, ad esempio "EFT_Fee.</span><span class="sxs-lookup"><span data-stu-id="f76ec-109">The Fee ID should describe when this fee will be used, such as "EFT_Fee".</span></span>  
4. <span data-ttu-id="f76ec-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f76ec-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="f76ec-111">Digitare un valore nel campo Descrizione commissione.</span><span class="sxs-lookup"><span data-stu-id="f76ec-111">In the Fee description field, type a value.</span></span>
    * <span data-ttu-id="f76ec-112">Aggiungere una descrizione per fornire più dettagli riguardo a quando la commissione viene imposta.</span><span class="sxs-lookup"><span data-stu-id="f76ec-112">Add a description to provide more detail on when the fee is assessed.</span></span>  
6. <span data-ttu-id="f76ec-113">Nel campo di Spesa, selezionare Fornitore o Contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="f76ec-113">In the Charge field, select either Vendor or Ledger.</span></span>
    * <span data-ttu-id="f76ec-114">Contabilità generale viene utilizzata quando la commissione verrà considerata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f76ec-114">Ledger is used when the fee will be expensed to your organization.</span></span>  <span data-ttu-id="f76ec-115">Fornitore viene utilizzato quando la commissione verrà imposta al fornitore.</span><span class="sxs-lookup"><span data-stu-id="f76ec-115">Vendor is used when the fee will be assessed to the vendor.</span></span>  
7. <span data-ttu-id="f76ec-116">Immettere un conto principale per dove la commissione verrà considerata come spesa.</span><span class="sxs-lookup"><span data-stu-id="f76ec-116">Enter a main account for where the fee will be expensed.</span></span>
    * <span data-ttu-id="f76ec-117">Questa opzione è disponibile solo quando si seleziona Contabilità generale come opzione di addebito.</span><span class="sxs-lookup"><span data-stu-id="f76ec-117">This option is only available when selecting Ledger as the Charge option.</span></span>  
8. <span data-ttu-id="f76ec-118">Selezionare il giornale di registrazione in cui la commissione può essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="f76ec-118">Select the journal on which this fee can be used.</span></span> 
    * <span data-ttu-id="f76ec-119">Per una commissione di pagamento fornitore, verrà selezionato il giornale di registrazione "Esborso fornitore".</span><span class="sxs-lookup"><span data-stu-id="f76ec-119">For a vendor payment fee, you would select the journal 'Vendor disbursement.'</span></span>  
9. <span data-ttu-id="f76ec-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="f76ec-120">Click Save.</span></span>
10. <span data-ttu-id="f76ec-121">Fare clic su Impostazione commissione pagamento.</span><span class="sxs-lookup"><span data-stu-id="f76ec-121">Click Payment fee setup.</span></span>
    * <span data-ttu-id="f76ec-122">Procedere all'impostazione della commissione di pagamento per definire quando la commissione dovrà essere impostata come valore predefinito nel giornale di registrazione selezionato.</span><span class="sxs-lookup"><span data-stu-id="f76ec-122">Continue to the Payment fee setup to define when the fee should default onto the journal you selected.</span></span>  
11. <span data-ttu-id="f76ec-123">Selezionare Tabella, Gruppo o Tutti.</span><span class="sxs-lookup"><span data-stu-id="f76ec-123">Select either Table, Group or All.</span></span>
    * <span data-ttu-id="f76ec-124">Tabella viene utilizzata per selezionare un singolo conto bancario, Gruppo viene utilizzato per selezionare un gruppo bancario e Tutti per utilizzare l'impostazione della commissione per tutti i conti bancari</span><span class="sxs-lookup"><span data-stu-id="f76ec-124">Table is used to select a single bank account, Group is used to select a bank group, and All is to use this fee setup for all bank accounts</span></span>  
12. <span data-ttu-id="f76ec-125">Selezionare un gruppo bancario o un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="f76ec-125">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="f76ec-126">La ricerca indicherà il gruppo bancario se è stato selezionato Gruppo e indicherà i conti bancari se è stato selezionato Tabella.</span><span class="sxs-lookup"><span data-stu-id="f76ec-126">The lookup will show bank group if you selected Group, and will show bank accounts if you selected Table.</span></span>  
13. <span data-ttu-id="f76ec-127">Selezionare il metodo di pagamento per quando verrà imposta la commissione.</span><span class="sxs-lookup"><span data-stu-id="f76ec-127">Select the method of payment for when this fee will be assessed.</span></span>
14. <span data-ttu-id="f76ec-128">Selezionare la specifica di pagamento per il metodo di pagamento selezionato.</span><span class="sxs-lookup"><span data-stu-id="f76ec-128">Select the Payment specification for the selected method of payment.</span></span>
    * <span data-ttu-id="f76ec-129">La specifica di pagamento viene utilizzata con i metodi di trasferimento fondi attraverso sistemi di pagamento elettronici.</span><span class="sxs-lookup"><span data-stu-id="f76ec-129">The Payment specification is used with electronic fund transfer methods of payment.</span></span>  
15. <span data-ttu-id="f76ec-130">Selezionare se la commissione è una percentuale, un importo o un intervallo.</span><span class="sxs-lookup"><span data-stu-id="f76ec-130">Select whether the fee is a percentage, amount or interval.</span></span>
16. <span data-ttu-id="f76ec-131">Immettere la percentuale o l'importo della commissione.</span><span class="sxs-lookup"><span data-stu-id="f76ec-131">Enter the percentage or amount of the fee.</span></span>
    * <span data-ttu-id="f76ec-132">Se la commissione è una percentuale, immettere la percentuale.</span><span class="sxs-lookup"><span data-stu-id="f76ec-132">If the Fee is a percentage, enter the percentage.</span></span> <span data-ttu-id="f76ec-133">Se la commissione è un importo, immettere l'importo della commissione.</span><span class="sxs-lookup"><span data-stu-id="f76ec-133">If the Fee is an amount, enter the amount of the fee.</span></span> <span data-ttu-id="f76ec-134">Se la commissione è un intervallo, utilizzare la scheda Intervallo per definire le commissioni a livelli.</span><span class="sxs-lookup"><span data-stu-id="f76ec-134">If the Fee is an interval, use the Interval tab to defined the tiered fees.</span></span>  
17. <span data-ttu-id="f76ec-135">Nel campo Valuta commissioni selezionare la valuta in cui verrà imposta la commissione.</span><span class="sxs-lookup"><span data-stu-id="f76ec-135">In the Fee currency field, select the currency in which the fee will be assessed.</span></span>
    * <span data-ttu-id="f76ec-136">Questa valuta è per la commissione.</span><span class="sxs-lookup"><span data-stu-id="f76ec-136">This currency is for the fee.</span></span> <span data-ttu-id="f76ec-137">La valuta di pagamento viene utilizzata per definire quando la regola della commissione deve essere imposta in base alla valuta del pagamento.</span><span class="sxs-lookup"><span data-stu-id="f76ec-137">The payment currency is used to define when the fee rule should be assessed based on the payment's currency.</span></span> <span data-ttu-id="f76ec-138">Ad esempio, la banca può addebitare una commissione quando un pagamento viene effettuato in euro, ma a tutti gli altri pagamenti non viene imposta una commissione.</span><span class="sxs-lookup"><span data-stu-id="f76ec-138">For example, your bank may charge a fee when a payment is made in EUR, but all other payments aren't assessed a fee.</span></span>  
18. <span data-ttu-id="f76ec-139">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="f76ec-139">Click Save.</span></span>

