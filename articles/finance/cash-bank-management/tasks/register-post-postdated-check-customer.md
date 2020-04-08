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
ms.openlocfilehash: 11089584e150a1a302eb969a5fb61cb9d1900901
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141743"
---
# <a name="register-and-post-a-postdated-check-for-a-customer"></a><span data-ttu-id="f2eac-103">Registrare un assegno postdatato per un cliente</span><span class="sxs-lookup"><span data-stu-id="f2eac-103">Register and post a postdated check for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f2eac-104">È possibile registrare i dettagli di un assegno postdatato ricevuto da un cliente.</span><span class="sxs-lookup"><span data-stu-id="f2eac-104">You can register details of a postdated check received from a customer.</span></span> <span data-ttu-id="f2eac-105">È inoltre possibile registrare l'assegno postdatato e generare transazioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="f2eac-105">You can also post the postdated check and generate financial transactions.</span></span>   <span data-ttu-id="f2eac-106">Completare le seguenti attività prima di registrare un assegno postdatato ricevuto da un cliente: \* Impostare gli assegni postdatati nella pagina Gestione cassa e banche \* Impostare un metodo di pagamento per gli assegni postdatati. Il ruolo per questa procedura è tesoriere.</span><span class="sxs-lookup"><span data-stu-id="f2eac-106">Complete the following tasks before you register and post a postdated check received from a customer:   \* Set up postdated check in the Cash and bank management page \* Set up a method of payment for postdated checks   The role for this procedure is Treasurer.</span></span> <span data-ttu-id="f2eac-107">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="f2eac-107">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="f2eac-108">Andare a Contabilità clienti > Pagamenti > Giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="f2eac-108">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="f2eac-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="f2eac-109">Click New.</span></span>
3. <span data-ttu-id="f2eac-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f2eac-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="f2eac-111">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="f2eac-111">Click Lines.</span></span>
5. <span data-ttu-id="f2eac-112">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f2eac-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="f2eac-113">Nel campo Conto, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="f2eac-113">In the Account field, specify the desired values.</span></span>
7. <span data-ttu-id="f2eac-114">Nel campo Credito immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="f2eac-114">In the Credit field, enter a number.</span></span>
    * <span data-ttu-id="f2eac-115">Immettere l'importo specificato nell'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="f2eac-115">Enter the amount specified in the postdated check.</span></span>  
8. <span data-ttu-id="f2eac-116">Fare clic sulla scheda Pagamento.</span><span class="sxs-lookup"><span data-stu-id="f2eac-116">Click the Payment tab.</span></span>
9. <span data-ttu-id="f2eac-117">Digitare un valore nel campo Metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="f2eac-117">In the Method of payment field, type a value.</span></span>
    * <span data-ttu-id="f2eac-118">Selezionare il metodo di pagamento per l'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="f2eac-118">Select the method of payment for the postdated check.</span></span>  
10. <span data-ttu-id="f2eac-119">Fare clic sulla scheda Assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="f2eac-119">Click the Postdated checks tab.</span></span>
11. <span data-ttu-id="f2eac-120">Immettere una data nel campo Data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="f2eac-120">In the Maturity date field, enter a date.</span></span>
    * <span data-ttu-id="f2eac-121">Immettere la data in cui è possibile esigere il pagamento dell'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="f2eac-121">Enter the date when the postdated check is due for payment.</span></span>  
12. <span data-ttu-id="f2eac-122">Digitare un valore nel campo Nome filiale emittente.</span><span class="sxs-lookup"><span data-stu-id="f2eac-122">In the Issuing bank branch field, type a value.</span></span>
    * <span data-ttu-id="f2eac-123">Immettere i dettagli bancari dell'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="f2eac-123">Enter the bank details of the postdated check.</span></span>  
13. <span data-ttu-id="f2eac-124">Digitare un valore nel campo Numero assegno.</span><span class="sxs-lookup"><span data-stu-id="f2eac-124">In the check number field, type a value.</span></span>
14. <span data-ttu-id="f2eac-125">Digitare un valore nel campo Nome banca emittente.</span><span class="sxs-lookup"><span data-stu-id="f2eac-125">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="f2eac-126">Immettere i dettagli bancari dell'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="f2eac-126">Enter the bank details of the postdated check.</span></span>  
15. <span data-ttu-id="f2eac-127">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="f2eac-127">Click Post.</span></span>
16. <span data-ttu-id="f2eac-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f2eac-128">Close the page.</span></span>

