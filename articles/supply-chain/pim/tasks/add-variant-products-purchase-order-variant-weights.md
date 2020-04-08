---
title: Aggiungere prodotti varianti agli ordini fornitore tramite pesi varianti
description: In questa procedura vengono descritti i passaggi per utilizzare i pesi varianti per popolare automaticamente le righe ordine fornitore per ogni variante di un prodotto.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae45dc0ed5332242a12efbb7f8ca37f97a244cce
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147988"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a><span data-ttu-id="bbf35-103">Aggiungere prodotti varianti agli ordini fornitore tramite pesi varianti</span><span class="sxs-lookup"><span data-stu-id="bbf35-103">Add variant products to purchase orders using variant weights</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bbf35-104">In questa procedura vengono descritti i passaggi per utilizzare i pesi varianti per popolare automaticamente le righe ordine fornitore per ogni variante di un prodotto.</span><span class="sxs-lookup"><span data-stu-id="bbf35-104">This procedure walks through the steps for using variant weights to auto populate purchase order lines for each variant of a product.</span></span> <span data-ttu-id="bbf35-105">Quando si seleziona la quantità del prodotto che si desidera acquistare, le righe ordine fornitore vengono create per tutte le varianti del prodotto con le quantità suggerite in base ai pesi configurati nelle varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="bbf35-105">When you select the quantity of the product you want to purchase, purchase order lines are created for all the variants of the product with suggested quantities based on the weights configured on the product variants.</span></span> <span data-ttu-id="bbf35-106">Questa procedura non include i passaggi per configurare i valori di peso nelle dimensioni prodotto e nelle varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="bbf35-106">This procedure doesn't include steps to configure weight values on product dimensions and product variants.</span></span> <span data-ttu-id="bbf35-107">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="bbf35-107">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="bbf35-108">Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="bbf35-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="bbf35-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="bbf35-109">Click New.</span></span>
3. <span data-ttu-id="bbf35-110">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbf35-110">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="bbf35-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bbf35-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="bbf35-112">Attivare/disattivare l'espansione della sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="bbf35-112">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="bbf35-113">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbf35-113">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="bbf35-114">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bbf35-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="bbf35-115">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbf35-115">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="bbf35-116">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="bbf35-116">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="bbf35-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bbf35-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="bbf35-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="bbf35-118">Click OK.</span></span>
12. <span data-ttu-id="bbf35-119">Attivare/disattivare l'espansione della sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="bbf35-119">Toggle the expansion of the Line details section.</span></span>
13. <span data-ttu-id="bbf35-120">Fare clic sulla scheda Varianti.</span><span class="sxs-lookup"><span data-stu-id="bbf35-120">Click the Variants tab.</span></span>
14. <span data-ttu-id="bbf35-121">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="bbf35-121">Click Add line.</span></span>
15. <span data-ttu-id="bbf35-122">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bbf35-122">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="bbf35-123">Nel campo Numero articolo digitare '0140'.</span><span class="sxs-lookup"><span data-stu-id="bbf35-123">In the Item number field, type '0140'.</span></span>
17. <span data-ttu-id="bbf35-124">Impostare la quantità su "1000".</span><span class="sxs-lookup"><span data-stu-id="bbf35-124">Set Quantity to '1000'.</span></span>
18. <span data-ttu-id="bbf35-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="bbf35-125">Click Save.</span></span>

