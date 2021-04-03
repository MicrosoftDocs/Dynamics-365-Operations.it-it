---
title: Rimborsare i clienti
description: In questo articolo viene illustrato come creare transazioni di rimborso per un gruppo di clienti. Se un cliente dispone di un saldo in Avere, è possibile rimborsare il cliente per l'importo del saldo.
author: JodiChristiansen
manager: AnnBe
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca087b5a39432eec6b2711cc4c4decf23932b611
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251122"
---
# <a name="reimburse-customers"></a><span data-ttu-id="a95df-104">Rimborsare i clienti</span><span class="sxs-lookup"><span data-stu-id="a95df-104">Reimburse customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a95df-105">In questo articolo viene illustrato come creare transazioni di rimborso per un gruppo di clienti.</span><span class="sxs-lookup"><span data-stu-id="a95df-105">This article explains how to create reimbursement transactions for a group of customers.</span></span> <span data-ttu-id="a95df-106">Se un cliente dispone di un saldo in Avere, è possibile rimborsare il cliente per l'importo del saldo.</span><span class="sxs-lookup"><span data-stu-id="a95df-106">If a customer has a credit balance, you can reimburse the customer for the amount of the balance.</span></span> 

<span data-ttu-id="a95df-107">Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="a95df-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="a95df-108">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="a95df-108">Prerequisite</span></span>                                                            | <span data-ttu-id="a95df-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a95df-109">Description</span></span> |
|-------------------------------------------------------------------------|-------------|
| <span data-ttu-id="a95df-110">Specificare l'importo minimo di rimborso per la persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="a95df-110">Specify the minimum reimbursement amount for the legal entity.</span></span>          | <span data-ttu-id="a95df-111">Nella pagina **Parametri contabilità clienti**, nell'area **Generale**, nel campo **Rimborso minimo**, immettere l'importo minimo rimborsabile per le eccedenze di pagamento del cliente.</span><span class="sxs-lookup"><span data-stu-id="a95df-111">On the **Accounts receivable parameters** page, in the **General** area, in the **Minimum reimbursement** field, enter the minimum amount that can be reimbursed for customer overpayments.</span></span> |
| <span data-ttu-id="a95df-112">Facoltativo: aggiungere un conto fornitore a ciascun cliente che può essere rimborsato.</span><span class="sxs-lookup"><span data-stu-id="a95df-112">Optional: Add a vendor account to each customer that can be reimbursed.</span></span> | <span data-ttu-id="a95df-113">Nella pagina **Clienti**, nella scheda dettaglio **Dettagli vari**, nel campo **Conto fornitore**, selezionare il conto fornitore per il cliente.</span><span class="sxs-lookup"><span data-stu-id="a95df-113">On the **Customers** page, on the **Miscellaneous details** FastTab, in the **Vendor account** field, select the vendor account for the customer.</span></span> |

<span data-ttu-id="a95df-114">Quando si creano le transazioni di rimborso, viene creata una fattura fornitore per l'importo del saldo in Avere.</span><span class="sxs-lookup"><span data-stu-id="a95df-114">When you create reimbursement transactions, a vendor invoice is created for the amount of the credit balance.</span></span> <span data-ttu-id="a95df-115">Il processo di rimborso rimuove il saldo in Avere per il conto cliente e crea un saldo esigibile per il conto fornitore corrispondente al cliente.</span><span class="sxs-lookup"><span data-stu-id="a95df-115">The reimbursement process removes the credit balance for the customer account and creates a balance due for the vendor account that corresponds to the customer.</span></span>

1. <span data-ttu-id="a95df-116">In Contabilità clienti, esegui il processo **Rimborso** (**Contabilità clienti \> Attività periodiche \> Rimborso**).</span><span class="sxs-lookup"><span data-stu-id="a95df-116">In Accounts receivable, run the **Reimbursement** process (**Accounts receivable \> Periodic tasks \> Reimbursement**).</span></span>
2. <span data-ttu-id="a95df-117">Per raggruppare tutte le transazioni, indipendentemente dalle dimensioni del libro mastro, imposta l'opzione **Riepiloga cliente** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a95df-117">To group all transactions, regardless of ledger dimensions, set the **Summarize customer** option to **Yes**.</span></span> <span data-ttu-id="a95df-118">Per raggruppare solo transazioni con dimensioni contabili simili, imposta l'opzione su **No**.</span><span class="sxs-lookup"><span data-stu-id="a95df-118">To group only transactions that have similar ledger dimensions, set the option to **No**.</span></span>
3. <span data-ttu-id="a95df-119">Seleziona **Includi clienti con transazioni di addebito in sospeso** per selezionare i clienti che hanno importi di addebito non liquidati.</span><span class="sxs-lookup"><span data-stu-id="a95df-119">Select **Include customers with outstanding debit transactions** to select customers who have unsettled debit amounts.</span></span>
4. <span data-ttu-id="a95df-120">Per rimborsare conti di clienti specifici, nella scheda dettaglio **Record da includere**, elezionare **Filtro** e quindi specificare i conti del cliente nella query.</span><span class="sxs-lookup"><span data-stu-id="a95df-120">To reimburse specific customer accounts, on the **Records to include** FastTab, select **Filter**, and then specify the customer accounts in the query.</span></span>

    <span data-ttu-id="a95df-121">Gli importi in Avere verranno trasferiti nei conti fornitore dei clienti ed elaborati come normali pagamenti.</span><span class="sxs-lookup"><span data-stu-id="a95df-121">The credit amounts are transferred to the vendor accounts of the customers and are processed as ordinary payments.</span></span> <span data-ttu-id="a95df-122">Se un cliente non dispone di conto fornitore, verrà creato automaticamente un conto fornitore occasionale per il cliente.</span><span class="sxs-lookup"><span data-stu-id="a95df-122">If a customer doesn't have a vendor account, a one-time vendor account is automatically created for the customer.</span></span>

5. <span data-ttu-id="a95df-123">Per visualizzare le transazioni di rimborso create, utilizza il report **Rimborso** (**Contabilità clienti \> Richieste di informazioni e report \> Report di rimborso**).</span><span class="sxs-lookup"><span data-stu-id="a95df-123">To view the reimbursement transactions that were created, use the **Reimbursement** report (**Accounts Receivable \> Inquiries and reports \> Reimbursement report**).</span></span>
6. <span data-ttu-id="a95df-124">In Contabilità fornitori, creare un pagamento per le fatture fornitore create dal processo di rimborso.</span><span class="sxs-lookup"><span data-stu-id="a95df-124">In Accounts payable, create a payment for the vendor invoices that were created by the reimbursement process.</span></span> <span data-ttu-id="a95df-125">Per informazioni su come pagare i fornitori, vedi [Panoramica dei pagamenti del fornitore](../accounts-payable/Vendor-payments-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="a95df-125">For information about how to pay vendors, see [Vendor payment overview](../accounts-payable/Vendor-payments-workspace.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]