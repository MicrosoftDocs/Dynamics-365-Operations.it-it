--- 
title: "Verificare le fatture e i dati principali nel sistema di contabilità fornitori"
description: "Quando si riceve una fattura da un fornitore per merci o servizi di un ordine fornitore, è possibile che per i processi aziendali sia necessario ricevere le merci o i servizi prima dell'approvazione della fattura per il pagamento."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 70a7a1f7d7a8221a72addfbee1d21f813df4eb46
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="audit-invoices-and-key-data-in-ap-system"></a><span data-ttu-id="b27b4-103">Verificare le fatture e i dati principali nel sistema di contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="b27b4-103">Audit invoices and key data in AP system</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b27b4-104">Quando si riceve una fattura da un fornitore per merci o servizi di un ordine fornitore, è possibile che per i processi aziendali sia necessario ricevere le merci o i servizi prima dell'approvazione della fattura per il pagamento.</span><span class="sxs-lookup"><span data-stu-id="b27b4-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="b27b4-105">Prima di iniziare, assicurarsi che sia selezionata la chiave di configurazione Abbinamento fatture.</span><span class="sxs-lookup"><span data-stu-id="b27b4-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="b27b4-106">Nella pagina Parametri di contabilità fornitori, assicurarsi che l'opzione Abilita convalida abbinamento fatture sia selezionata,che il campo Registra fatture con discrepanze sia impostato su Richiedi approvazione e che il campo Criteri di abbinamento riga sia impostato su Criteri di abbinamento a tre elementi di verifica.</span><span class="sxs-lookup"><span data-stu-id="b27b4-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="b27b4-107">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="b27b4-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="b27b4-108">Il ruolo di responsabile della contabilità fornitori o del responsabile della contabilità eseguirebbe le operazioni.</span><span class="sxs-lookup"><span data-stu-id="b27b4-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="b27b4-109">Creare un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="b27b4-109">Create a purchase order</span></span>
1. <span data-ttu-id="b27b4-110">Fare clic su Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="b27b4-110">Go to All purchase orders.</span></span>
2. <span data-ttu-id="b27b4-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b27b4-111">Click New.</span></span>
3. <span data-ttu-id="b27b4-112">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b27b4-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="b27b4-113">Digitare un valore nel campo Conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="b27b4-113">In the Vendor account field, type a value.</span></span>
5. <span data-ttu-id="b27b4-114">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b27b4-114">Click OK.</span></span>
6. <span data-ttu-id="b27b4-115">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="b27b4-115">Click Add line.</span></span>
7. <span data-ttu-id="b27b4-116">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="b27b4-116">In the Item number field, type a value.</span></span>
8. <span data-ttu-id="b27b4-117">Nel riquadro azioni fare clic su Acquisti.</span><span class="sxs-lookup"><span data-stu-id="b27b4-117">On the Action Pane, click Purchase.</span></span>
9. <span data-ttu-id="b27b4-118">Fare clic su Conferma.</span><span class="sxs-lookup"><span data-stu-id="b27b4-118">Click Confirm.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="b27b4-119">Registra un'entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="b27b4-119">Post a product receipt</span></span>
1. <span data-ttu-id="b27b4-120">Nel riquadro azioni fare clic su Ricevimento.</span><span class="sxs-lookup"><span data-stu-id="b27b4-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="b27b4-121">Fare clic su Entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="b27b4-121">Click Product receipt.</span></span>
3. <span data-ttu-id="b27b4-122">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b27b4-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="b27b4-123">Digitare un valore nel campo Entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="b27b4-123">In the Product receipt field, type a value.</span></span>
5. <span data-ttu-id="b27b4-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b27b4-124">Click OK.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="b27b4-125">Registrare e abbinare una fattura fornitore a un'entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="b27b4-125">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="b27b4-126">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="b27b4-126">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="b27b4-127">Fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="b27b4-127">Click Invoice.</span></span>
3. <span data-ttu-id="b27b4-128">Digitare un valore nel campo Numero.</span><span class="sxs-lookup"><span data-stu-id="b27b4-128">In the Number field, type a value.</span></span>
4. <span data-ttu-id="b27b4-129">Fare clic su Predefinito da: Quantità ordinata per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="b27b4-129">Click Default from: Ordered quantity to open the drop dialog.</span></span>
5. <span data-ttu-id="b27b4-130">Nel campo Quantità predefinita per le righe selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="b27b4-130">In the Default quantity for lines field, select an option.</span></span>
6. <span data-ttu-id="b27b4-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b27b4-131">Click OK.</span></span>
7. <span data-ttu-id="b27b4-132">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="b27b4-132">Click Yes.</span></span>
8. <span data-ttu-id="b27b4-133">Fare clic su Abbina entrate prodotti.</span><span class="sxs-lookup"><span data-stu-id="b27b4-133">Click Match product receipts.</span></span>
9. <span data-ttu-id="b27b4-134">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b27b4-134">Click OK.</span></span>
10. <span data-ttu-id="b27b4-135">Nel riquadro azioni fare clic su Revisione.</span><span class="sxs-lookup"><span data-stu-id="b27b4-135">On the Action Pane, click Review.</span></span>
11. <span data-ttu-id="b27b4-136">Fare clic su Dettagli abbinamento.</span><span class="sxs-lookup"><span data-stu-id="b27b4-136">Click Matching details.</span></span>


