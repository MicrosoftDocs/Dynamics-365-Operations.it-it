---
title: Registrare un assegno postdatato per un fornitore
description: Utilizzare il giustificativo giornale di registrazione per registrare i dettagli di un assegno postdatato prima di emettere l'assegno a favore di un fornitore.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cb7f9935b20d042551b0ce77fd6bdbf55e9f9669
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834670"
---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a><span data-ttu-id="feb09-103">Registrare un assegno postdatato per un fornitore</span><span class="sxs-lookup"><span data-stu-id="feb09-103">Register and post a postdated check for a vendor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="feb09-104">Utilizzare il giustificativo giornale di registrazione per registrare i dettagli di un assegno postdatato prima di emettere l'assegno a favore di un fornitore.</span><span class="sxs-lookup"><span data-stu-id="feb09-104">You can register the details of a postdated check before you issue the check to a vendor by using the journal voucher.</span></span> <span data-ttu-id="feb09-105">È inoltre possibile registrare l'assegno postdatato e generare transazioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="feb09-105">You can also post the postdated check and generate financial transactions.</span></span> <span data-ttu-id="feb09-106">Prima di registrare un assegno postdatato ricevuto da un fornitore, completare le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="feb09-106">Before you register and post a postdated check from a vendor, complete the following task:</span></span> 

<span data-ttu-id="feb09-107">impostare gli assegni postdatati nella pagina Gestione banche e di cassa.</span><span class="sxs-lookup"><span data-stu-id="feb09-107">Set up postdated checks in the Cash and bank management page.</span></span> 



<span data-ttu-id="feb09-108">Il ruolo dell'attività è Tesoriere.</span><span class="sxs-lookup"><span data-stu-id="feb09-108">The role of this task guides is Treasurer.</span></span> <span data-ttu-id="feb09-109">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="feb09-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="feb09-110">Passare a Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti</span><span class="sxs-lookup"><span data-stu-id="feb09-110">Go to Acounts payable > Payments > Payment journal</span></span>
2. <span data-ttu-id="feb09-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="feb09-111">Click New.</span></span>
3. <span data-ttu-id="feb09-112">Digitare 'VendPay' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="feb09-112">In the Name field, type 'VendPay'.</span></span>
4. <span data-ttu-id="feb09-113">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="feb09-113">Click Lines.</span></span>
5. <span data-ttu-id="feb09-114">Nel campo Conto, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="feb09-114">In the Account field, specify the desired values.</span></span>
6. <span data-ttu-id="feb09-115">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="feb09-115">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="feb09-116">Nel campo Dare immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="feb09-116">In the Debit field, enter a number.</span></span>
8. <span data-ttu-id="feb09-117">Nel campo Metodo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="feb09-117">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="feb09-118">Selezionare il metodo di pagamento per l'assegno postdatato</span><span class="sxs-lookup"><span data-stu-id="feb09-118">Select the method of payment for the postdated check</span></span>  
9. <span data-ttu-id="feb09-119">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="feb09-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="feb09-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="feb09-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="feb09-121">Fare clic sulla scheda Assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="feb09-121">Click the Postdated checks tab.</span></span>
12. <span data-ttu-id="feb09-122">Digitare un valore nel campo Numero assegno.</span><span class="sxs-lookup"><span data-stu-id="feb09-122">In the Check number field, type a value.</span></span>
    * <span data-ttu-id="feb09-123">Immettere o modificare il numero dell'assegno postdatato.</span><span class="sxs-lookup"><span data-stu-id="feb09-123">Enter or modify the number of the postdated check.</span></span>  
13. <span data-ttu-id="feb09-124">Digitare un valore nel campo Nome banca emittente.</span><span class="sxs-lookup"><span data-stu-id="feb09-124">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="feb09-125">Immettere le informazioni sulla banca emittente.</span><span class="sxs-lookup"><span data-stu-id="feb09-125">enter the bank details for the issuing bank.</span></span>  
14. <span data-ttu-id="feb09-126">Fare clic sulla scheda Elenco.</span><span class="sxs-lookup"><span data-stu-id="feb09-126">Click the List tab.</span></span>
15. <span data-ttu-id="feb09-127">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="feb09-127">Click Post.</span></span>
16. <span data-ttu-id="feb09-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="feb09-128">Close the page.</span></span>
17. <span data-ttu-id="feb09-129">Fare clic sulla scheda Assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="feb09-129">Click the Postdated checks tab.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]