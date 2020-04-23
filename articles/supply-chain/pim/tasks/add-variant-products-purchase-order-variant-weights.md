---
title: Aggiungere prodotti varianti agli ordini fornitore tramite pesi varianti
description: In questa procedura vengono descritti i passaggi per utilizzare i pesi varianti per popolare automaticamente le righe ordine fornitore per ogni variante di un prodotto.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0199f4b05c23eec5c03c770c37111a6ee6d13efe
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208388"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a><span data-ttu-id="926d9-103">Aggiungere prodotti varianti agli ordini fornitore tramite pesi varianti</span><span class="sxs-lookup"><span data-stu-id="926d9-103">Add variant products to purchase orders using variant weights</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="926d9-104">In questa procedura vengono descritti i passaggi per utilizzare i pesi varianti per popolare automaticamente le righe ordine fornitore per ogni variante di un prodotto.</span><span class="sxs-lookup"><span data-stu-id="926d9-104">This procedure walks through the steps for using variant weights to auto populate purchase order lines for each variant of a product.</span></span> <span data-ttu-id="926d9-105">Quando si seleziona la quantità del prodotto che si desidera acquistare, le righe ordine fornitore vengono create per tutte le varianti del prodotto con le quantità suggerite in base ai pesi configurati nelle varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="926d9-105">When you select the quantity of the product you want to purchase, purchase order lines are created for all the variants of the product with suggested quantities based on the weights configured on the product variants.</span></span> <span data-ttu-id="926d9-106">Questa procedura non include i passaggi per configurare i valori di peso nelle dimensioni prodotto e nelle varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="926d9-106">This procedure doesn't include steps to configure weight values on product dimensions and product variants.</span></span> <span data-ttu-id="926d9-107">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="926d9-107">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="926d9-108">Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="926d9-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="926d9-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="926d9-109">Click New.</span></span>
3. <span data-ttu-id="926d9-110">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="926d9-110">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="926d9-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="926d9-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="926d9-112">Attivare/disattivare l'espansione della sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="926d9-112">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="926d9-113">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="926d9-113">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="926d9-114">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="926d9-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="926d9-115">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="926d9-115">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="926d9-116">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="926d9-116">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="926d9-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="926d9-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="926d9-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="926d9-118">Click OK.</span></span>
12. <span data-ttu-id="926d9-119">Attivare/disattivare l'espansione della sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="926d9-119">Toggle the expansion of the Line details section.</span></span>
13. <span data-ttu-id="926d9-120">Fare clic sulla scheda Varianti.</span><span class="sxs-lookup"><span data-stu-id="926d9-120">Click the Variants tab.</span></span>
14. <span data-ttu-id="926d9-121">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="926d9-121">Click Add line.</span></span>
15. <span data-ttu-id="926d9-122">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="926d9-122">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="926d9-123">Nel campo Numero articolo digitare '0140'.</span><span class="sxs-lookup"><span data-stu-id="926d9-123">In the Item number field, type '0140'.</span></span>
17. <span data-ttu-id="926d9-124">Impostare la quantità su "1000".</span><span class="sxs-lookup"><span data-stu-id="926d9-124">Set Quantity to '1000'.</span></span>
18. <span data-ttu-id="926d9-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="926d9-125">Click Save.</span></span>

