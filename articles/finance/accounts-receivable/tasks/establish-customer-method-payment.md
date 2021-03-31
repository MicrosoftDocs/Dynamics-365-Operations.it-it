---
title: Definire il metodo di pagamento del cliente
description: In questo argomento viene illustrato come creare un metodo di pagamento per i pagamenti dei clienti.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7e60459c417c6018c4088009a323cf7f66616ef4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220205"
---
# <a name="establish-customer-method-of-payment"></a><span data-ttu-id="91250-103">Definire il metodo di pagamento del cliente</span><span class="sxs-lookup"><span data-stu-id="91250-103">Establish customer method of payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="91250-104">In questo argomento viene illustrato come creare un metodo di pagamento per i pagamenti dei clienti.</span><span class="sxs-lookup"><span data-stu-id="91250-104">This topic explains how to create a method of payment for customer payments.</span></span> <span data-ttu-id="91250-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="91250-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="91250-106">Nel pannello di navigazione andare a **Moduli > Crediti e riscossioni > Impostazione pagamenti > Metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="91250-106">In the navigation pane, go to **Modules > Accounts receivable > Payments setup > Methods of payment**.</span></span>
2. <span data-ttu-id="91250-107">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="91250-107">Select **New**.</span></span>
3. <span data-ttu-id="91250-108">Nel campo **Metodo di pagamento** immettere un ID per il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="91250-108">In the **Method of payment** field, enter an ID for the method of payment.</span></span> <span data-ttu-id="91250-109">L'ID relativo al metodo di pagamento viene visualizzato nelle fatture e nei pagamenti, quindi fare in modo che sia abbastanza descrittivo per comprendere il tipo di pagamento registrato e per quale conto bancario.</span><span class="sxs-lookup"><span data-stu-id="91250-109">The Method of payment ID is shown on invoices and payments, so make it descriptive enough to understand what type of payment is being recorded, and for what bank account.</span></span>  
4. <span data-ttu-id="91250-110">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="91250-110">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="91250-111">Selezionare lo stato del pagamento richiesto per la registrazione dei pagamenti.</span><span class="sxs-lookup"><span data-stu-id="91250-111">Select what payment status is required in order for payments to be posted.</span></span> <span data-ttu-id="91250-112">Quando si crea un pagamento cliente, può essere registrato solo quando lo stato di pagamento corrisponde allo stato di pagamento definito in questo campo.</span><span class="sxs-lookup"><span data-stu-id="91250-112">When creating a customer payment, it can only be posted when the payment status matches the payment status you define here.</span></span>  
6. <span data-ttu-id="91250-113">Selezionare la modalità di creazione dei pagamenti dei clienti per le fatture.</span><span class="sxs-lookup"><span data-stu-id="91250-113">Select how customers payments should be created for invoices.</span></span> <span data-ttu-id="91250-114">Questa opzione viene utilizzata solo quando si esegue una proposta di pagamento.</span><span class="sxs-lookup"><span data-stu-id="91250-114">This option is only used when running a payment proposal.</span></span> <span data-ttu-id="91250-115">Una proposta di pagamento potrebbe essere utilizzata per i pagamenti cliente quando si effettuano addebiti diretti e il pull dei fondi dai conti bancari dei clienti.</span><span class="sxs-lookup"><span data-stu-id="91250-115">A payment proposal could be used for customer payments when doing direct debits, and pulling the funds from the customers' bank accounts.</span></span>  
7. <span data-ttu-id="91250-116">Selezionare il tipo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="91250-116">Select the type of payment.</span></span> <span data-ttu-id="91250-117">Il tipo di pagamento contribuirà a determinare se verrà eseguita una certa convalida sul pagamento.</span><span class="sxs-lookup"><span data-stu-id="91250-117">The payment type will help determine whether some validation will occur or not on the payment.</span></span>  
8. <span data-ttu-id="91250-118">Selezionare il tipo di conto in cui verranno registrati i pagamenti.</span><span class="sxs-lookup"><span data-stu-id="91250-118">Select what account type payments will post to.</span></span> <span data-ttu-id="91250-119">In genere per questa opzione verrà selezionato il valore Banca.</span><span class="sxs-lookup"><span data-stu-id="91250-119">Typically, Bank would be selected for this option.</span></span>  
9. <span data-ttu-id="91250-120">Selezionare il conto bancario in cui il pagamento verrà registrato.</span><span class="sxs-lookup"><span data-stu-id="91250-120">Select the bank account into which this payment will be recorded.</span></span>
10. <span data-ttu-id="91250-121">Immettere il tipo di transazione bancaria per identificare il tipo di pagamento utilizzato dalla banca.</span><span class="sxs-lookup"><span data-stu-id="91250-121">Enter the Bank transaction type to identify the type of payment used by your bank.</span></span> <span data-ttu-id="91250-122">Il tipo di transazione bancaria viene utilizzato durante il processo di riconciliazione bancaria e può semplificare la riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="91250-122">The bank transaction type is used during the bank reconciliation process, and can make reconciliation easier.</span></span>  
11. <span data-ttu-id="91250-123">Selezionare se il pagamento verrà temporaneamente registrato in un conto provvisorio.</span><span class="sxs-lookup"><span data-stu-id="91250-123">Select whether this payment will temporarily post to a bridging account.</span></span> <span data-ttu-id="91250-124">Se si desidera provare il periodo fondo di cassa per un pagamento per cancellare la banca, utilizzare la funzionalità Registrazione compensativa.</span><span class="sxs-lookup"><span data-stu-id="91250-124">If you want to try the float time for a payment to clear the bank, use the Bridging functionality.</span></span> <span data-ttu-id="91250-125">Il pagamento verrà temporaneamente registrato in un conto CoGe finché non cancella la banca, momento in cui il pagamento verrà trasferito nel conto bancario definito in questo campo.</span><span class="sxs-lookup"><span data-stu-id="91250-125">The payment will temporarily post to a Ledger account until it clears the bank, at which time the payment will move to the bank account you defined here.</span></span>  
12. <span data-ttu-id="91250-126">Immettere il conto principale utilizzato per la registrazione provvisoria.</span><span class="sxs-lookup"><span data-stu-id="91250-126">Enter the main account used for the bridging posting.</span></span> <span data-ttu-id="91250-127">Si tratta del conto principale in cui il pagamento verrà temporaneamente registrato se si utilizza la registrazione compensativa.</span><span class="sxs-lookup"><span data-stu-id="91250-127">This is the main account to which the payment will temporarily post if using bridging.</span></span>  
13. <span data-ttu-id="91250-128">Utilizzare la scheda **Formato file** per definire l'impostazione dei pagamenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="91250-128">Use the **File format** tab to define setting for electronic payments.</span></span>
14. <span data-ttu-id="91250-129">Utilizzare la scheda **Controllo pagamenti** per definire i campi obbligatori.</span><span class="sxs-lookup"><span data-stu-id="91250-129">Use the **Payment control** tab to define fields that are mandatory.</span></span> <span data-ttu-id="91250-130">Ad esempio, se si richiede che tutti i pagamenti con questo metodo di pagamento vengano depositati, è possibile selezionare tale opzione nella scheda.</span><span class="sxs-lookup"><span data-stu-id="91250-130">For example, if you require all payments with this method of payment to be deposited, you can choose that option on this tab.</span></span>  
15. <span data-ttu-id="91250-131">Utilizzare la scheda **Attributi di pagamento** per definire gli attributi di pagamento che si desidera utilizzare per il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="91250-131">Use the **Payment attributes** tab to define which payment attributes you want to use for this method of payment.</span></span>
16. <span data-ttu-id="91250-132">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="91250-132">Select **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]