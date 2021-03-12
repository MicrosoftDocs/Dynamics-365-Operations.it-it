---
title: Creare ed esportare i pagamenti fornitore usando il formato di pagamento ISO20022
description: Questa procedura descrive come creare righe di pagamento nel giornale di registrazione pagamenti fornitore e come generare un file di pagamento fornitore usando l'esempio di bonifico ISO2022.
author: mrolecki
manager: AnnBe
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1df738e3925dc23e7723d93f33acf6a9d811b113
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964543"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="fd094-103">Creare ed esportare pagamenti fornitore usando il formato di pagamento ISO20022</span><span class="sxs-lookup"><span data-stu-id="fd094-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fd094-104">Questo argomento descrive come creare righe di pagamento nel giornale di registrazione pagamenti fornitore e come generare un file di pagamento fornitore usando l'esempio di bonifico ISO2022.</span><span class="sxs-lookup"><span data-stu-id="fd094-104">This topic explains how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span>

<span data-ttu-id="fd094-105">Si tratta della quinta procedura di cinque, che illustra il processo di pagamento fornitore utilizzando le configurazioni di creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="fd094-105">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="fd094-106">Per completare questo esempio utilizzare i dati dimostrativi DEMF.</span><span class="sxs-lookup"><span data-stu-id="fd094-106">Use the DEMF demo data to complete this example.</span></span>

## <a name="example"></a><span data-ttu-id="fd094-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd094-107">Example</span></span>

1.    <span data-ttu-id="fd094-108">Passare a **Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti.**</span><span class="sxs-lookup"><span data-stu-id="fd094-108">Go to **Accounts payable > Payments > Payment journal**.</span></span>
2.    <span data-ttu-id="fd094-109">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fd094-109">Click **New**.</span></span>
3.    <span data-ttu-id="fd094-110">Nel campo **Nome** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fd094-110">In the **Name** field, enter or select a value.</span></span>
4.    <span data-ttu-id="fd094-111">Fare clic su **Righe > Proposta di pagamento > Crea proposta di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="fd094-111">Click **Lines > Payment proposal > Create payment proposal**.</span></span>
5.    <span data-ttu-id="fd094-112">Espandere la sezione **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="fd094-112">Expand the **Records to include** section.</span></span>
6.    <span data-ttu-id="fd094-113">Fare clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="fd094-113">Click **Filter**.</span></span>
7.    <span data-ttu-id="fd094-114">Nell'elenco, selezionare la riga per la **tabella Fornitori** e il **campo Conto fornitore**.</span><span class="sxs-lookup"><span data-stu-id="fd094-114">In the list, select the row for **Vendors table** and **Vendor account field**.</span></span>
8.    <span data-ttu-id="fd094-115">Nel campo **Criteri** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fd094-115">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="fd094-116">È possibile applicare qualsiasi criterio per la selezione delle transazioni fornitore da pagare, per questo esempio utilizzare DE-001 come conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="fd094-116">You can apply any criteria for selecting vendor transactions to pay, for this example, use DE-001 as a vendor account.</span></span>
12.    <span data-ttu-id="fd094-117">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd094-117">Click **OK**.</span></span>
13.    <span data-ttu-id="fd094-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd094-118">Click **OK**.</span></span>
14.    <span data-ttu-id="fd094-119">Fare clic su **Crea pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="fd094-119">Click **Create payments**.</span></span>
15. <span data-ttu-id="fd094-120">Generare un file di pagamento ISO20022.</span><span class="sxs-lookup"><span data-stu-id="fd094-120">Generate an ISO20022 payment file.</span></span>
    1.    <span data-ttu-id="fd094-121">Fare clic su **Genera pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="fd094-121">Click **Generate payments**.</span></span>
    2.    <span data-ttu-id="fd094-122">Nel campo **Metodo di pagamento** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fd094-122">In the **Method of payment** field, enter or select a value.</span></span>
    3.    <span data-ttu-id="fd094-123">Digitare un valore nel campo **Nome file**.</span><span class="sxs-lookup"><span data-stu-id="fd094-123">In the **File name** field, type a value.</span></span> <span data-ttu-id="fd094-124">Per questo esempio, in seguito al pagamento EUR, il file generato sarà conforme a SEPA.</span><span class="sxs-lookup"><span data-stu-id="fd094-124">For this example, because of the EUR payment, the generated file will be SEPA compliant.</span></span> <span data-ttu-id="fd094-125">Il bonifico ISO20022 nonché altri formati di pagamento fornitore possono essere utilizzati per generare pagamenti in altre valute.</span><span class="sxs-lookup"><span data-stu-id="fd094-125">ISO20022 credit transfer as well as other vendor payment formats can also be used for generating payments in other currencies.</span></span>
    4.    <span data-ttu-id="fd094-126">Nel campo **Conto bancario** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fd094-126">In the **Bank account** field, enter or select a value.</span></span>

