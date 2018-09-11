--- 
title: Registrare una fattura fornitore nel giornale di registrazione fatture
description: "Questa guida attività indicherà come registrare le fatture fornitore non associate a ordini fornitore."
author: abruer
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 9109144feee2cb5c813e00a04e78e4291d7f3bfd
ms.contentlocale: it-it
ms.lasthandoff: 09/11/2018

---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="98796-103">Registrare una fattura fornitore nel giornale di registrazione fatture</span><span class="sxs-lookup"><span data-stu-id="98796-103">Record a vendor invoice in the invoice journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="98796-104">Questa guida attività indicherà come registrare le fatture fornitore non associate a ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="98796-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="98796-105">Gli esempi di questo tipo di fattura includono le spese per le forniture o i servizi.</span><span class="sxs-lookup"><span data-stu-id="98796-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="98796-106">Questa registrazione utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="98796-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="98796-107">Andare a Contabilità fornitori > Aree di lavoro > Inserimento fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="98796-107">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="98796-108">Fare clic su Nuovo giornale di registrazione fatture.</span><span class="sxs-lookup"><span data-stu-id="98796-108">Click New invoice journal.</span></span>
3. <span data-ttu-id="98796-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="98796-109">Click New.</span></span>
4. <span data-ttu-id="98796-110">Nel campo Nome immettere il nome del giornale di registrazione o fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="98796-110">In the Name field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="98796-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="98796-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="98796-112">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="98796-112">Click Lines.</span></span>
    * <span data-ttu-id="98796-113">Nel campo Data, immettere la data di registrazione che aggiornerà la contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="98796-113">In the Date field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="98796-114">Nel campo Conto specificare il conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="98796-114">In the Account field, specify the Vendor account.</span></span>
8. <span data-ttu-id="98796-115">Nel campo Fattura immettere il numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="98796-115">In the Invoice field, enter the invoice number.</span></span>
9. <span data-ttu-id="98796-116">Digitare un valore nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="98796-116">In the Description field, type a value.</span></span>
10. <span data-ttu-id="98796-117">Nel campo Credito immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="98796-117">In the Credit field, enter a number.</span></span>
11. <span data-ttu-id="98796-118">Nel campo Conto di contropartita immettere il numero di conto o fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="98796-118">In the Offset account field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="98796-119">Come fascia IVA predefinita verrà impostata quella del conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="98796-119">The Sales tax group will default from the vendor account.</span></span>  
    * <span data-ttu-id="98796-120">Come fascia IVA articoli predefinita verrà impostata quella del conto principale specificata nel campo Conto di contropartita.</span><span class="sxs-lookup"><span data-stu-id="98796-120">The Item sales tax group will default from the main account specified in the Offset account field.</span></span>  
    * <span data-ttu-id="98796-121">La data di scadenza verrà calcolata in base ai Termini di pagamento.</span><span class="sxs-lookup"><span data-stu-id="98796-121">The Due date will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="98796-122">Come sconto di cassa predefinito verrà impostato quello del conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="98796-122">The Cash discount will default from the Vendor account.</span></span>  
12. <span data-ttu-id="98796-123">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="98796-123">Click Post.</span></span>
13. <span data-ttu-id="98796-124">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="98796-124">Close the page.</span></span>


