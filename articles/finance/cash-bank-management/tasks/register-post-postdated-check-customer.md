---
title: Registrare un assegno postdatato per un cliente
description: È possibile registrare i dettagli di un assegno postdatato ricevuto da un cliente.
author: kweekley
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f27675a2aa2160619bf78eea33bba2ce0b7bd81
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188098"
---
# <a name="register-and-post-a-postdated-check-for-a-customer"></a><span data-ttu-id="e2ca4-103">Registrare un assegno postdatato per un cliente</span><span class="sxs-lookup"><span data-stu-id="e2ca4-103">Register and post a postdated check for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e2ca4-104">È possibile registrare i dettagli di un assegno postdatato ricevuto da un cliente.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-104">You can register details of a postdated check received from a customer.</span></span> <span data-ttu-id="e2ca4-105">È inoltre possibile registrare l'assegno postdatato e generare transazioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-105">You can also post the postdated check and generate financial transactions.</span></span>   <span data-ttu-id="e2ca4-106">Completare le seguenti attività prima di registrare un assegno postdatato ricevuto da un cliente: • Impostare gli assegni postdatati nella pagina Gestione cassa e banche • Impostare un metodo di pagamento per gli assegni postdatati. Il ruolo per questa procedura è tesoriere.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-106">Complete the following tasks before you register and post a postdated check received from a customer:   • Set up postdated check in the Cash and bank management page • Set up a method of payment for postdated checks   The role for this procedure is Treasurer.</span></span> <span data-ttu-id="e2ca4-107">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-107">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="e2ca4-108">Andare a Contabilità clienti > Pagamenti > Giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-108">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="e2ca4-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-109">Click New.</span></span>
3. <span data-ttu-id="e2ca4-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="e2ca4-111">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-111">Click Lines.</span></span>
5. <span data-ttu-id="e2ca4-112">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="e2ca4-113">Nel campo Conto, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-113">In the Account field, specify the desired values.</span></span>
7. <span data-ttu-id="e2ca4-114">Nel campo Credito immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-114">In the Credit field, enter a number.</span></span>
    * <span data-ttu-id="e2ca4-115">Immettere l'importo specificato nell'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-115">Enter the amount specified in the postdated check.</span></span>  
8. <span data-ttu-id="e2ca4-116">Fare clic sulla scheda Pagamento.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-116">Click the Payment tab.</span></span>
9. <span data-ttu-id="e2ca4-117">Digitare un valore nel campo Metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-117">In the Method of payment field, type a value.</span></span>
    * <span data-ttu-id="e2ca4-118">Selezionare il metodo di pagamento per l'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-118">Select the method of payment for the postdated check.</span></span>  
10. <span data-ttu-id="e2ca4-119">Fare clic sulla scheda Assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-119">Click the Postdated checks tab.</span></span>
11. <span data-ttu-id="e2ca4-120">Immettere una data nel campo Data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-120">In the Maturity date field, enter a date.</span></span>
    * <span data-ttu-id="e2ca4-121">Immettere la data in cui è possibile esigere il pagamento dell'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-121">Enter the date when the postdated check is due for payment.</span></span>  
12. <span data-ttu-id="e2ca4-122">Digitare un valore nel campo Nome filiale emittente.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-122">In the Issuing bank branch field, type a value.</span></span>
    * <span data-ttu-id="e2ca4-123">Immettere i dettagli bancari dell'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-123">Enter the bank details of the postdated check.</span></span>  
13. <span data-ttu-id="e2ca4-124">Digitare un valore nel campo Numero assegno.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-124">In the check number field, type a value.</span></span>
14. <span data-ttu-id="e2ca4-125">Digitare un valore nel campo Nome banca emittente.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-125">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="e2ca4-126">Immettere i dettagli bancari dell'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-126">Enter the bank details of the postdated check.</span></span>  
15. <span data-ttu-id="e2ca4-127">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-127">Click Post.</span></span>
16. <span data-ttu-id="e2ca4-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e2ca4-128">Close the page.</span></span>

