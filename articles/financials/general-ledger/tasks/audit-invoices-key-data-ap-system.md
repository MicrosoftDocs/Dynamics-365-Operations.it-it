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
ms.sourcegitcommit: cc995b474e86272b49629f97e1b4d4b4fb597b9d
ms.openlocfilehash: 946076d682a10becdc2c4a8baff7f52de7893119
ms.contentlocale: it-it
ms.lasthandoff: 12/04/2018

---
# <a name="audit-invoices-and-key-data-in-ap-system"></a><span data-ttu-id="1525a-103">Verificare le fatture e i dati principali nel sistema di contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="1525a-103">Audit invoices and key data in AP system</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1525a-104">Quando si riceve una fattura da un fornitore per merci o servizi di un ordine fornitore, è possibile che per i processi aziendali sia necessario ricevere le merci o i servizi prima dell'approvazione della fattura per il pagamento.</span><span class="sxs-lookup"><span data-stu-id="1525a-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="1525a-105">Prima di iniziare, assicurarsi che sia selezionata la chiave di configurazione Abbinamento fatture.</span><span class="sxs-lookup"><span data-stu-id="1525a-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="1525a-106">Nella pagina Parametri di contabilità fornitori, assicurarsi che l'opzione Abilita convalida abbinamento fatture sia selezionata,che il campo Registra fatture con discrepanze sia impostato su Richiedi approvazione e che il campo Criteri di abbinamento riga sia impostato su Criteri di abbinamento a tre elementi di verifica.</span><span class="sxs-lookup"><span data-stu-id="1525a-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="1525a-107">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="1525a-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="1525a-108">Il ruolo di responsabile della contabilità fornitori o del responsabile della contabilità eseguirebbe le operazioni.</span><span class="sxs-lookup"><span data-stu-id="1525a-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="1525a-109">Creare un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="1525a-109">Create a purchase order</span></span>
1. <span data-ttu-id="1525a-110">Accedere a **Tutti gli ordini fornitore**.</span><span class="sxs-lookup"><span data-stu-id="1525a-110">Go to **All purchase orders**.</span></span>
2. <span data-ttu-id="1525a-111">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1525a-111">Click **New**.</span></span>
3. <span data-ttu-id="1525a-112">Nel campo **Conto fornitore**, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="1525a-112">In the **Vendor account** field, type a value.</span></span>
4. <span data-ttu-id="1525a-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1525a-113">Click **OK**.</span></span>
5. <span data-ttu-id="1525a-114">Fare clic su **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="1525a-114">Click **Add line**.</span></span>
6. <span data-ttu-id="1525a-115">Nel campo **Numero articolo**, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="1525a-115">In the **Item number** field, type a value.</span></span>
7. <span data-ttu-id="1525a-116">Nel riquadro azioni, fare clic su **Acquisti**.</span><span class="sxs-lookup"><span data-stu-id="1525a-116">On the Action Pane, click **Purchase**.</span></span>
8. <span data-ttu-id="1525a-117">Fare clic su **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="1525a-117">Click **Confirm**.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="1525a-118">Registra un'entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="1525a-118">Post a product receipt</span></span>
1. <span data-ttu-id="1525a-119">Nel riquadro azioni, fare clic su **Ricevimento**.</span><span class="sxs-lookup"><span data-stu-id="1525a-119">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="1525a-120">Fare clic su **Entrata prodotti**.</span><span class="sxs-lookup"><span data-stu-id="1525a-120">Click **Product receipt**.</span></span>
3. <span data-ttu-id="1525a-121">Nel campo **Entrata prodotti**, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="1525a-121">In the **Product receipt** field, type a value.</span></span>
4. <span data-ttu-id="1525a-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1525a-122">Click **OK**.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="1525a-123">Registrare e abbinare una fattura fornitore a un'entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="1525a-123">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="1525a-124">Nel riquadro azioni, fare clic su **Fattura > Fattura**.</span><span class="sxs-lookup"><span data-stu-id="1525a-124">On the Action Pane, click **Invoice > Invoice**.</span></span>
2. <span data-ttu-id="1525a-125">Nel campo **Numero**, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="1525a-125">In the **Number** field, type a value.</span></span>
3. <span data-ttu-id="1525a-126">Fare clic su **Predefinito da: Quantità ordinata** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="1525a-126">Click **Default from: Ordered quantity** to open the drop dialog.</span></span>
4. <span data-ttu-id="1525a-127">Nel campo **Quantità predefinita per le righe**, selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="1525a-127">In the **Default quantity for lines** field, select an option.</span></span>
5. <span data-ttu-id="1525a-128">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1525a-128">Click **OK**.</span></span>
6. <span data-ttu-id="1525a-129">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="1525a-129">Click **Yes**.</span></span>
7. <span data-ttu-id="1525a-130">Fare clic su **Abbina entrate prodotti**.</span><span class="sxs-lookup"><span data-stu-id="1525a-130">Click **Match product receipts**.</span></span>
8. <span data-ttu-id="1525a-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1525a-131">Click **OK**.</span></span>
9. <span data-ttu-id="1525a-132">Nel riquadro azioni fare clic su **Revisione**.</span><span class="sxs-lookup"><span data-stu-id="1525a-132">On the Action Pane, click **Review**.</span></span>
10. <span data-ttu-id="1525a-133">Fare clic su **Dettagli abbinamento**.</span><span class="sxs-lookup"><span data-stu-id="1525a-133">Click **Matching details**.</span></span>


