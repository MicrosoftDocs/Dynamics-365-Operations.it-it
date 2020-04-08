---
title: Registrare una fattura fornitore nel giornale di registrazione fatture
description: Questa guida attività indicherà come registrare le fatture fornitore non associate a ordini fornitore.
author: abruer
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5277081d9f7adcc43c30d30208d13c7e39d76118
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140377"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="dcfe0-103">Registrare una fattura fornitore nel giornale di registrazione fatture</span><span class="sxs-lookup"><span data-stu-id="dcfe0-103">Record a vendor invoice in the invoice journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dcfe0-104">Questa guida attività indicherà come registrare le fatture fornitore non associate a ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="dcfe0-105">Gli esempi di questo tipo di fattura includono le spese per le forniture o i servizi.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="dcfe0-106">Questa registrazione utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="dcfe0-107">Andare a **Pannello di navigazione > Moduli > Contabilità fornitori > Aree di lavoro > Inserimento fatture fornitore**.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-107">Go to **Navigation pane > Modules > Accounts payable > Workspaces > Vendor invoice entry**.</span></span>
2. <span data-ttu-id="dcfe0-108">Fare clic su **Nuovo giornale di registrazione fatture** nel **riquadro azioni**.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-108">On the **Action pane**, click **New invoice journal**.</span></span>
3. <span data-ttu-id="dcfe0-109">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-109">Click **New**.</span></span>
4. <span data-ttu-id="dcfe0-110">Nel campo **Nome** immettere il nome del giornale di registrazione o fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-110">In the **Name** field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="dcfe0-111">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dcfe0-111">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="dcfe0-112">Nel **riquadro azioni** fare clic su **Righe**.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-112">On the **Action pane**, click **Lines**.</span></span> <span data-ttu-id="dcfe0-113">Nel campo **Data**, immettere la data di registrazione che aggiornerà la contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-113">In the **Date** field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="dcfe0-114">Nel campo **Conto** specificare il **conto fornitore**.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-114">In the **Account** field, specify the **Vendor account**.</span></span>
8. <span data-ttu-id="dcfe0-115">Nel campo **Fattura** immettere il numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-115">In the **Invoice** field, enter the invoice number.</span></span>
9. <span data-ttu-id="dcfe0-116">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dcfe0-116">In the **Description** field, type a value.</span></span>
10. <span data-ttu-id="dcfe0-117">Nel campo **Credito** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-117">In the **Credit** field, enter a number.</span></span>
11. <span data-ttu-id="dcfe0-118">Nel campo **Conto di contropartita** immettere il numero di conto o fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-118">In the **Offset account** field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="dcfe0-119">Come **Fascia IVA** predefinita verrà impostata quella del conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-119">The **Sales tax group** will be default from the vendor account.</span></span>  
    * <span data-ttu-id="dcfe0-120">Come **fascia IVA articoli** predefinita verrà impostata quella del conto principale specificata nel campo **Conto di contropartita**.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-120">The **Item sales tax group** will be default from the main account specified in the **Offset account** field.</span></span>  
    * <span data-ttu-id="dcfe0-121">La **data di scadenza** verrà calcolata in base ai Termini di pagamento.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-121">The **Due date** will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="dcfe0-122">Come **sconto di cassa** predefinito verrà impostato quello del conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-122">The **Cash discount** will default from the Vendor account.</span></span>  
12. <span data-ttu-id="dcfe0-123">Fare clic su **Registra**.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-123">Click **Post**.</span></span>
13. <span data-ttu-id="dcfe0-124">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dcfe0-124">Close the page.</span></span>

