--- 
title: "Creare e acquisire cespiti dalla contabilità fornitori"
description: "In questa guida attività verrà illustrata la creazione e l'acquisizione di un cespite con il processo di acquisto."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: e6c36338cc67855c79ec97d88bb8b633417b85c7
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="create-and-acquire-assets-from-accounts-payable"></a><span data-ttu-id="aeb62-103">Creare e acquisire cespiti dalla contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="aeb62-103">Create and acquire assets from Accounts payable</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="aeb62-104">In questa guida attività verrà illustrata la creazione e l'acquisizione di un cespite con il processo di acquisto.</span><span class="sxs-lookup"><span data-stu-id="aeb62-104">This task guide will walk through creation and acquisition of a fixed asset with the purchasing process.</span></span>  <span data-ttu-id="aeb62-105">Vengono utilizzati l'addetto alla contabilità fornitori e il contabile e la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="aeb62-105">It uses the Accountant and Accounts payable clerks and the demo company USMF .</span></span>


## <a name="set-fixed-assets-parameters"></a><span data-ttu-id="aeb62-106">Impostare i parametri per i cespiti</span><span class="sxs-lookup"><span data-stu-id="aeb62-106">Set Fixed assets parameters</span></span>
1. <span data-ttu-id="aeb62-107">Passare a Cespiti > Impostazione > Parametri cespiti.</span><span class="sxs-lookup"><span data-stu-id="aeb62-107">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="aeb62-108">Espandere o comprimere la sezione Ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="aeb62-108">Expand or collapse the Purchase orders section.</span></span>
3. <span data-ttu-id="aeb62-109">Selezionare la casella di controllo Consenti acquisizione cespiti da Acquisto.</span><span class="sxs-lookup"><span data-stu-id="aeb62-109">Check the Allow asset acquisition from Purchasing checkbox.</span></span>
4. <span data-ttu-id="aeb62-110">Selezionare la casella di controllo Crea cespite durante la registrazione entrata prodotti o fattura.</span><span class="sxs-lookup"><span data-stu-id="aeb62-110">Check the Create asset during product receipt or invoice posting checkbox.</span></span>

## <a name="create-a-new-vendor-invoice"></a><span data-ttu-id="aeb62-111">Crea una nuova fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="aeb62-111">Create a new vendor invoice</span></span>
1. <span data-ttu-id="aeb62-112">Andare a Contabilità fornitori > Aree di lavoro > Inserimento fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="aeb62-112">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="aeb62-113">Fare clic su Nuova fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="aeb62-113">Click New vendor invoice.</span></span>
3. <span data-ttu-id="aeb62-114">Nel campo Conto fattura fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="aeb62-114">In the Invoice account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="aeb62-115">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="aeb62-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="aeb62-116">Digitare un valore nel campo Numero.</span><span class="sxs-lookup"><span data-stu-id="aeb62-116">In the Number field, type a value.</span></span>
6. <span data-ttu-id="aeb62-117">Immettere una data nel campo Data registrazione.</span><span class="sxs-lookup"><span data-stu-id="aeb62-117">In the Posting date field, enter a date.</span></span>
7. <span data-ttu-id="aeb62-118">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="aeb62-118">Click Add line.</span></span>
8. <span data-ttu-id="aeb62-119">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="aeb62-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="aeb62-120">Gli articoli non stoccati o le categorie di approvvigionamento possono essere utilizzati per l'acquisizione dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="aeb62-120">Either non-stocked items or procurement categories can be used for fixed asset acquisition.</span></span>  
9. <span data-ttu-id="aeb62-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="aeb62-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="aeb62-122">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="aeb62-122">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="aeb62-123">Una riga della fattura creerà solo un cespite, indipendentemente dalla quantità.</span><span class="sxs-lookup"><span data-stu-id="aeb62-123">One invoice line will only create one fixed asset, regardless of quantity.</span></span>  <span data-ttu-id="aeb62-124">Il valore del campo Quantità in fattura verrà trasferito in Quantità cespite.</span><span class="sxs-lookup"><span data-stu-id="aeb62-124">The invoice quantity field value will be transferred to the fixed asset quantity.</span></span>  
11. <span data-ttu-id="aeb62-125">Nel campo Prezzo unitario immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="aeb62-125">In the Unit price field, enter a number.</span></span>
12. <span data-ttu-id="aeb62-126">Espandere o comprimere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="aeb62-126">Expand or collapse the Line details section.</span></span>
13. <span data-ttu-id="aeb62-127">Fare clic sulla scheda Cespiti.</span><span class="sxs-lookup"><span data-stu-id="aeb62-127">Click the Fixed assets tab.</span></span>
14. <span data-ttu-id="aeb62-128">Selezionare la casella di controllo Crea un nuovo cespite.</span><span class="sxs-lookup"><span data-stu-id="aeb62-128">Check the Create a new fixed asset checkbox.</span></span>
15. <span data-ttu-id="aeb62-129">Nel campo Gruppo cespite fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="aeb62-129">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="aeb62-130">In questo elenco selezionare il gruppo cespite da utilizzare quando si crea il nuovo cespite.</span><span class="sxs-lookup"><span data-stu-id="aeb62-130">In the list, select the fixed asset group to be used when creating the new fixed asset.</span></span>
17. <span data-ttu-id="aeb62-131">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="aeb62-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="aeb62-132">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="aeb62-132">Click Post.</span></span>
    * <span data-ttu-id="aeb62-133">Il cespite verrà creato e acquisito quando viene registrata la fattura.</span><span class="sxs-lookup"><span data-stu-id="aeb62-133">The fixed asset will be created and acquired when the invoice is posted.</span></span>  


