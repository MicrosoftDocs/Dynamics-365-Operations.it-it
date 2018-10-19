--- 
title: Impostare un metodo di pagamento per addebito diretto ISO20022
description: In questa procedura viene illustrato come impostare il metodo di pagamento del cliente per addebito diretto ISO20022 o qualsiasi altro tipo di pagamento mediante la creazione di report elettronici.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 953a3cffc356ab44163944318e7e7d542a113112
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a><span data-ttu-id="849d7-103">Impostare un metodo di pagamento per addebito diretto ISO20022</span><span class="sxs-lookup"><span data-stu-id="849d7-103">Setup method of payment for ISO20022 direct debit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="849d7-104">In questa procedura viene illustrato come impostare il metodo di pagamento del cliente per addebito diretto ISO20022 o qualsiasi altro tipo di pagamento mediante la creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="849d7-104">This procedure shows how to set up the customer method of payment for ISO20022 direct debit or any other payment type using electronic reporting.</span></span> 



<span data-ttu-id="849d7-105">Prima di completare l'attività, è necessario impostare le configurazioni del formato di esportazione e i conti di pagamento.</span><span class="sxs-lookup"><span data-stu-id="849d7-105">Before you complete this task, you must set up export format configurations and payment accounts.</span></span>



<span data-ttu-id="849d7-106">Questa procedura è stata creata utilizzando la società di dati dimostrativi DEMF.</span><span class="sxs-lookup"><span data-stu-id="849d7-106">This procedure was created using the demo data company DEMF.</span></span>



<span data-ttu-id="849d7-107">Si tratta della terza di cinque procedure che illustrano il processo di pagamento cliente utilizzando le configurazioni di creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="849d7-107">This is the third of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="849d7-108">Andare a Contabilità clienti > Impostazione pagamenti > Metodi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="849d7-108">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="849d7-109">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="849d7-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="849d7-110">Ad esempio, applicare un filtro al campo Metodo di pagamento in base al valore di pagamento elettronico.</span><span class="sxs-lookup"><span data-stu-id="849d7-110">For example, filter on the Method of payment field with a value of 'ELECTRONIC'.</span></span>
3. <span data-ttu-id="849d7-111">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="849d7-111">Click Edit.</span></span>
4. <span data-ttu-id="849d7-112">Nel campo Conto pagamenti specificare i valori "DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="849d7-112">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
5. <span data-ttu-id="849d7-113">Espandere la sezione Formati file.</span><span class="sxs-lookup"><span data-stu-id="849d7-113">Expand the File formats section.</span></span>
6. <span data-ttu-id="849d7-114">Selezionare Sì nel campo Report elettronici generici.</span><span class="sxs-lookup"><span data-stu-id="849d7-114">Select Yes in the Generic electronic reporting field.</span></span>
7. <span data-ttu-id="849d7-115">Nel campo Esporta configurazione formato immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="849d7-115">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="849d7-116">Nell'elenco selezionare Addebito diretto ISO20022 (DE).</span><span class="sxs-lookup"><span data-stu-id="849d7-116">In the list, select ISO20022 Direct debit (DE).</span></span>  <span data-ttu-id="849d7-117">Se l'elenco è vuoto, significa che la configurazione del formato di esportazione dei pagamenti cliente non è importata e attiva.</span><span class="sxs-lookup"><span data-stu-id="849d7-117">If the list is empty, the customer payment export format configuration has not been imported and active.</span></span>  
8. <span data-ttu-id="849d7-118">Selezionare Sì nel campo Richiedi mandato.</span><span class="sxs-lookup"><span data-stu-id="849d7-118">Select Yes in the Require mandate field.</span></span>
    * <span data-ttu-id="849d7-119">Selezionare il parametro Richiedi mandato per i formati di pagamento cliente, che richiedono di includere le informazioni sul mandato nel messaggio di pagamento, come addebito diretto SEPA.</span><span class="sxs-lookup"><span data-stu-id="849d7-119">Select the Require mandate parameter for customer payment formats, which require including mandate information in the payment message, like SEPA direct debit.</span></span>  
9. <span data-ttu-id="849d7-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="849d7-120">Click Save.</span></span>


