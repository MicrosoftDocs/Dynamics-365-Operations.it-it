--- 
title: Registrare un assegno postdatato per un cliente
description: "È possibile registrare i dettagli di un assegno postdatato ricevuto da un cliente."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1610036815349f625a67d5dd67260114d42fff97
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="register-and-post-a-postdated-check-for-a-customer"></a><span data-ttu-id="32b88-103">Registrare un assegno postdatato per un cliente</span><span class="sxs-lookup"><span data-stu-id="32b88-103">Register and post a postdated check for a customer</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="32b88-104">È possibile registrare i dettagli di un assegno postdatato ricevuto da un cliente.</span><span class="sxs-lookup"><span data-stu-id="32b88-104">You can register details of a postdated cheque received from a customer.</span></span> <span data-ttu-id="32b88-105">È inoltre possibile registrare l'assegno postdatato e generare transazioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="32b88-105">You can also post the postdated cheque and generate financial transactions.</span></span>   <span data-ttu-id="32b88-106">Completare le seguenti attività prima di registrare un assegno postdatato ricevuto da un cliente: • Impostare gli assegni postdatati nella pagina Gestione cassa e banche • Impostare un metodo di pagamento per gli assegni postdatati. Il ruolo per questa procedura è tesoriere.</span><span class="sxs-lookup"><span data-stu-id="32b88-106">Complete the following tasks before you register and post a postdated cheque received from a customer:   • Set up postdated Cheques in the Cash and bank management page • Set up a method of payment for postdated Cheques   The role for this procedure is Treasurer.</span></span> <span data-ttu-id="32b88-107">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="32b88-107">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="32b88-108">Andare a Contabilità clienti > Pagamenti > Giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="32b88-108">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="32b88-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="32b88-109">Click New.</span></span>
3. <span data-ttu-id="32b88-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="32b88-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="32b88-111">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="32b88-111">Click Lines.</span></span>
5. <span data-ttu-id="32b88-112">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="32b88-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="32b88-113">Nel campo Conto, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="32b88-113">In the Account field, specify the desired values.</span></span>
7. <span data-ttu-id="32b88-114">Nel campo Credito immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="32b88-114">In the Credit field, enter a number.</span></span>
    * <span data-ttu-id="32b88-115">Immettere l'importo specificato nell'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="32b88-115">Enter the amount specified in the postdated cheque.</span></span>  
8. <span data-ttu-id="32b88-116">Fare clic sulla scheda Pagamento.</span><span class="sxs-lookup"><span data-stu-id="32b88-116">Click the Payment tab.</span></span>
9. <span data-ttu-id="32b88-117">Digitare un valore nel campo Metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="32b88-117">In the Method of payment field, type a value.</span></span>
    * <span data-ttu-id="32b88-118">Selezionare il metodo di pagamento per l'assegno postdatato</span><span class="sxs-lookup"><span data-stu-id="32b88-118">Select the method of payment for the postdated cheque</span></span>  
10. <span data-ttu-id="32b88-119">Fare clic sulla scheda Assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="32b88-119">Click the Postdated checks tab.</span></span>
11. <span data-ttu-id="32b88-120">Immettere una data nel campo Data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="32b88-120">In the Maturity date field, enter a date.</span></span>
    * <span data-ttu-id="32b88-121">Immettere la data in cui è possibile esigere il pagamento dell'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="32b88-121">Enter the date when the postdated cheque is due for payment.</span></span>  
12. <span data-ttu-id="32b88-122">Digitare un valore nel campo Nome filiale emittente.</span><span class="sxs-lookup"><span data-stu-id="32b88-122">In the Issuing bank branch field, type a value.</span></span>
    * <span data-ttu-id="32b88-123">Immettere i dettagli bancari dell'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="32b88-123">Enter the bank details of the postdated cheque.</span></span>  
13. <span data-ttu-id="32b88-124">Digitare un valore nel campo Numero assegno.</span><span class="sxs-lookup"><span data-stu-id="32b88-124">In the cheque number field, type a value.</span></span>
14. <span data-ttu-id="32b88-125">Digitare un valore nel campo Nome banca emittente.</span><span class="sxs-lookup"><span data-stu-id="32b88-125">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="32b88-126">Immettere i dettagli bancari dell'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="32b88-126">Enter the bank details of the postdated check.</span></span>  
15. <span data-ttu-id="32b88-127">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="32b88-127">Click Post.</span></span>
16. <span data-ttu-id="32b88-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="32b88-128">Close the page.</span></span>


