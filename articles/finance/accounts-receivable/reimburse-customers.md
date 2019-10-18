---
title: Rimborsare i clienti
description: In questo articolo viene illustrato come creare transazioni di rimborso per un gruppo di clienti. Se un cliente dispone di un saldo in Avere, è possibile rimborsare il cliente per l'importo del saldo.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97982dec140ed440682ae507f40557670ebccd3e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178519"
---
# <a name="reimburse-customers"></a><span data-ttu-id="7ca45-104">Rimborsare i clienti</span><span class="sxs-lookup"><span data-stu-id="7ca45-104">Reimburse customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ca45-105">In questo articolo viene illustrato come creare transazioni di rimborso per un gruppo di clienti.</span><span class="sxs-lookup"><span data-stu-id="7ca45-105">This article explains how to create reimbursement transactions for a group of customers.</span></span> <span data-ttu-id="7ca45-106">Se un cliente dispone di un saldo in Avere, è possibile rimborsare il cliente per l'importo del saldo.</span><span class="sxs-lookup"><span data-stu-id="7ca45-106">If a customer has a credit balance, you can reimburse the customer for the amount of the balance.</span></span> 

<span data-ttu-id="7ca45-107">Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="7ca45-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="7ca45-108">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="7ca45-108">Prerequisite</span></span>                                                            | <span data-ttu-id="7ca45-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ca45-109">Description</span></span>                                                                                                                                                                                 |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7ca45-110">Specificare l'importo minimo di rimborso per la persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="7ca45-110">Specify the minimum reimbursement amount for the legal entity.</span></span>          | <span data-ttu-id="7ca45-111">Nella pagina **Parametri contabilità clienti**, nell'area **Generale**, nel campo **Rimborso minimo**, immettere l'importo minimo rimborsabile per le eccedenze di pagamento del cliente.</span><span class="sxs-lookup"><span data-stu-id="7ca45-111">On the **Accounts receivable parameters** page, in the **General** area, in the **Minimum reimbursement** field, enter the minimum amount that can be reimbursed for customer overpayments.</span></span> |
| <span data-ttu-id="7ca45-112">Facoltativo: aggiungere un conto fornitore a ciascun cliente che può essere rimborsato.</span><span class="sxs-lookup"><span data-stu-id="7ca45-112">Optional: Add a vendor account to each customer that can be reimbursed.</span></span> | <span data-ttu-id="7ca45-113">Nella pagina **Clienti**, nella scheda dettaglio **Dettagli vari**, nel campo **Conto fornitore**, selezionare il conto fornitore per il cliente.</span><span class="sxs-lookup"><span data-stu-id="7ca45-113">On the **Customers** page, on the **Miscellaneous details** FastTab, in the **Vendor account** field, select the vendor account for the customer.</span></span>                                           |

<span data-ttu-id="7ca45-114">Quando si creano le transazioni di rimborso, viene creata una fattura fornitore per l'importo del saldo in Avere.</span><span class="sxs-lookup"><span data-stu-id="7ca45-114">When you create reimbursement transactions, a vendor invoice is created for the amount of the credit balance.</span></span> <span data-ttu-id="7ca45-115">Il processo di rimborso rimuove il saldo in Avere per il conto cliente e crea un saldo esigibile per il conto fornitore corrispondente al cliente.</span><span class="sxs-lookup"><span data-stu-id="7ca45-115">The reimbursement process removes the credit balance for the customer account and creates a balance due for the vendor account that corresponds to the customer.</span></span>

1.  <span data-ttu-id="7ca45-116">In Contabilità clienti, eseguire il processo **Rimborso**.</span><span class="sxs-lookup"><span data-stu-id="7ca45-116">In Accounts receivable, run the **Reimbursement** process.</span></span>
2.  <span data-ttu-id="7ca45-117">Eseguire uno dei passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="7ca45-117">Follow one of these steps:</span></span>
    -   <span data-ttu-id="7ca45-118">Per effettuare il rimborso su specifici conti cliente, fare clic su **Seleziona**, quindi specificare i conti cliente nella query.</span><span class="sxs-lookup"><span data-stu-id="7ca45-118">To reimburse specific customer accounts, click **Select**, and specify the customer accounts in the query.</span></span>
    -   <span data-ttu-id="7ca45-119">Per effettuare il rimborso su tutti i conti cliente, scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ca45-119">To reimburse all customer accounts, click **OK**.</span></span>

    <span data-ttu-id="7ca45-120">Gli importi in Avere verranno trasferiti nei conti fornitore dei clienti ed elaborati come normali pagamenti.</span><span class="sxs-lookup"><span data-stu-id="7ca45-120">The credit amounts are transferred to the vendor accounts of the customers and are processed as ordinary payments.</span></span> <span data-ttu-id="7ca45-121">Se un cliente non dispone di conto fornitore, verrà creato automaticamente un conto fornitore occasionale per il cliente.</span><span class="sxs-lookup"><span data-stu-id="7ca45-121">If a customer doesn't have a vendor account, a one-time vendor account is automatically created for the customer.</span></span>
3.  <span data-ttu-id="7ca45-122">Per visualizzare le transazioni di rimborso create, utilizzare la pagina **Rimborso**.</span><span class="sxs-lookup"><span data-stu-id="7ca45-122">To view the reimbursement transactions that were created, use the **Reimbursement** page.</span></span>
4.  <span data-ttu-id="7ca45-123">In Contabilità fornitori, creare un pagamento per le fatture fornitore create dal processo di rimborso.</span><span class="sxs-lookup"><span data-stu-id="7ca45-123">In Accounts payable, create a payment for the vendor invoices that were created by the reimbursement process.</span></span>




