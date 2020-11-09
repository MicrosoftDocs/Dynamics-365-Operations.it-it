---
title: Disponibilità delle scorte in doppia scrittura
description: Questo argomento fornisce informazioni su come controllare la disponibilità delle scorte in doppia scrittura.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 4d1022eec633bf0a9edb4d5b26982853cec836d7
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997894"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="c1a8a-103">Disponibilità delle scorte in doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="c1a8a-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c1a8a-104">Utilizzando la disponibilità delle scorte, puoi verificare le scorte prima di aggiungere un prodotto alla pagina **Offerte** , **Ordini** o **Fatture** in Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c1a8a-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations** , **Orders** , or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="c1a8a-105">Ad esempio, la verifica delle scorte e la determinazione di una data di evasione sono attività chiave nel processo [prospect-to-cash](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="c1a8a-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="c1a8a-106">Se non si dispone di scorte sufficienti, è possibile stimare una data di consegna in base a entrate e uscite da magazzino previste.</span><span class="sxs-lookup"><span data-stu-id="c1a8a-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="c1a8a-107">È anche possibile verificare le informazioni available-to-promise (ATP) del prodotto, che indicano la quantità ATP nell'intervallo temporale predefinito.</span><span class="sxs-lookup"><span data-stu-id="c1a8a-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="c1a8a-108">Scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="c1a8a-108">On-hand inventory</span></span>

<span data-ttu-id="c1a8a-109">In Dynamics 365 Sales, nell'intestazione delle pagine **Offerte** , **Ordini** e **Fatture** , viene aggiunto un nuovo pulsante **Scorte disponibili**.</span><span class="sxs-lookup"><span data-stu-id="c1a8a-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes** , **Orders** , and **Invoices** pages.</span></span> <span data-ttu-id="c1a8a-110">Quando selezioni questo pulsante, viene visualizzata una finestra di dialogo in cui è possibile specificare la società e il prodotto per i quali si desidera verificare le scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="c1a8a-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="c1a8a-111">Questa finestra di dialogo mostra le stesse informazioni di [Scorte disponibili](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="c1a8a-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="c1a8a-112">La finestra di dialogo restituisce le informazioni di inventario da Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c1a8a-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="c1a8a-113">Queste informazioni includono le seguenti quantità:</span><span class="sxs-lookup"><span data-stu-id="c1a8a-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="c1a8a-114">Quantità disponibile</span><span class="sxs-lookup"><span data-stu-id="c1a8a-114">On-hand quantity</span></span>
- <span data-ttu-id="c1a8a-115">Quantità disponibile prenotata</span><span class="sxs-lookup"><span data-stu-id="c1a8a-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="c1a8a-116">Quantità disponibile utilizzabile</span><span class="sxs-lookup"><span data-stu-id="c1a8a-116">Available on-hand quantity</span></span>
- <span data-ttu-id="c1a8a-117">Quantità ordinata</span><span class="sxs-lookup"><span data-stu-id="c1a8a-117">Ordered quantity</span></span>
- <span data-ttu-id="c1a8a-118">Quantità in ordinazione</span><span class="sxs-lookup"><span data-stu-id="c1a8a-118">On-order quantity</span></span>
- <span data-ttu-id="c1a8a-119">Quantità ordinata prenotata</span><span class="sxs-lookup"><span data-stu-id="c1a8a-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="c1a8a-120">Quantità totale disponibile</span><span class="sxs-lookup"><span data-stu-id="c1a8a-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="c1a8a-121">Informazioni ATP</span><span class="sxs-lookup"><span data-stu-id="c1a8a-121">ATP information</span></span>

<span data-ttu-id="c1a8a-122">Nelle Sales, è stato aggiunto alle voci un nuovo pulsante **Informazioni ATP** nelle pagine **Offerte** , **Ordini** e **Fatture**.</span><span class="sxs-lookup"><span data-stu-id="c1a8a-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes** , **Orders** , and **Invoices** pages.</span></span> <span data-ttu-id="c1a8a-123">Quando selezioni questo pulsante, viene visualizzata una finestra di dialogo in cui è possibile specificare la società, il prodotto, il sito magazzino, il magazzino scorte e la quantità dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c1a8a-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="c1a8a-124">Questa finestra di dialogo ha le stesse impostazioni descritte in [Promesse ordine](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="c1a8a-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="c1a8a-125">La finestra di dialogo restituisce le informazioni ATP da Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c1a8a-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="c1a8a-126">Queste informazioni includono le seguenti quantità:</span><span class="sxs-lookup"><span data-stu-id="c1a8a-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="c1a8a-127">Quantità ATP</span><span class="sxs-lookup"><span data-stu-id="c1a8a-127">ATP quantity</span></span>
- <span data-ttu-id="c1a8a-128">Quantità entrata</span><span class="sxs-lookup"><span data-stu-id="c1a8a-128">Receipt quantity</span></span>
- <span data-ttu-id="c1a8a-129">Quantità uscita</span><span class="sxs-lookup"><span data-stu-id="c1a8a-129">Issue quantity</span></span>
- <span data-ttu-id="c1a8a-130">Quantità disponibile</span><span class="sxs-lookup"><span data-stu-id="c1a8a-130">On-hand quantity</span></span>
