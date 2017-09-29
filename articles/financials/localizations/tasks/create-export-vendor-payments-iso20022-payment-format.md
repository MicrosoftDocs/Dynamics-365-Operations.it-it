--- 
title: Creare ed esportare i pagamenti fornitore usando il formato di pagamento ISO20022
description: Questa procedura descrive come creare righe di pagamento nel giornale di registrazione pagamenti fornitore e come generare un file di pagamento fornitore usando l'esempio di bonifico ISO2022.
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7cc90bc86cd489b124a806c480632dd53ba47f3f
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="695e0-103">Creare ed esportare i pagamenti fornitore usando il formato di pagamento ISO20022</span><span class="sxs-lookup"><span data-stu-id="695e0-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="695e0-104">Questa procedura descrive come creare righe di pagamento nel giornale di registrazione pagamenti fornitore e come generare un file di pagamento fornitore usando l'esempio di bonifico ISO2022.</span><span class="sxs-lookup"><span data-stu-id="695e0-104">This procedure shows how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span> 

<span data-ttu-id="695e0-105">La società di dati dimostrativi utilizzata per creare questa procedura è DEMF.</span><span class="sxs-lookup"><span data-stu-id="695e0-105">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="695e0-106">Si tratta della quinta procedura di cinque, che illustra il processo di pagamento fornitore utilizzando le configurazioni di creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="695e0-106">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="695e0-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="695e0-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-payment-lines"></a><span data-ttu-id="695e0-108">Creare righe pagamento</span><span class="sxs-lookup"><span data-stu-id="695e0-108">Create payment lines</span></span>
1. <span data-ttu-id="695e0-109">Andare a Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="695e0-109">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="695e0-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="695e0-110">Click New.</span></span>
3. <span data-ttu-id="695e0-111">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="695e0-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="695e0-112">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="695e0-112">In the Name field, enter or select a value.</span></span>
5. <span data-ttu-id="695e0-113">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="695e0-113">Click Lines.</span></span>
6. <span data-ttu-id="695e0-114">Fare clic su Proposta di pagamento.</span><span class="sxs-lookup"><span data-stu-id="695e0-114">Click Payment proposal.</span></span>
7. <span data-ttu-id="695e0-115">Fare clic su Crea proposta di pagamento.</span><span class="sxs-lookup"><span data-stu-id="695e0-115">Click Create payment proposal.</span></span>
8. <span data-ttu-id="695e0-116">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="695e0-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="695e0-117">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="695e0-117">Click Filter.</span></span>
10. <span data-ttu-id="695e0-118">Nell'elenco, selezionare la riga per la tabella Fornitori e il campo Conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="695e0-118">In the list, select the row for Vendors table and Vendor account field.</span></span>
11. <span data-ttu-id="695e0-119">Nel campo Criteri immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="695e0-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="695e0-120">È possibile applicare qualsiasi criterio per la selezione delle transazioni fornitore da pagare, per questo esempio utilizzare DE-001 come conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="695e0-120">You can apply any criteria for selecting vendor transactions to pay, for this example use DE-001 as a vendor account.</span></span>  
12. <span data-ttu-id="695e0-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="695e0-121">Click OK.</span></span>
13. <span data-ttu-id="695e0-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="695e0-122">Click OK.</span></span>
14. <span data-ttu-id="695e0-123">Fare clic su Crea pagamenti.</span><span class="sxs-lookup"><span data-stu-id="695e0-123">Click Create payments.</span></span>

## <a name="generate-an-iso20022-payment-file"></a><span data-ttu-id="695e0-124">Generare un file di pagamento ISO20022</span><span class="sxs-lookup"><span data-stu-id="695e0-124">Generate an ISO20022 payment file</span></span>


