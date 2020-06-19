---
title: Disponibilità delle scorte in doppia scrittura
description: Questo argomento fornisce informazioni sulla verifica della disponibilità delle scorte in doppia scrittura.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: dd0995eb8c70ed06cdc3c0f6a28b13b117297533
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426984"
---
# <a name="inventory-availability"></a><span data-ttu-id="77705-103">Disponibilità delle scorte</span><span class="sxs-lookup"><span data-stu-id="77705-103">Inventory availability</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="77705-104">Utilizzando la disponibilità delle scorte, è possibile verificare le scorte prima di aggiungere un prodotto nei moduli **Offerte**, **Ordini** o **Fatture** in app basate su modello in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="77705-104">Using inventory availability, you can check your inventory before you add a product into the **Quotes**, **Orders**, or **Invoices** forms in model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="77705-105">Ad esempio, la verifica delle scorte e la determinazione di una data di evasione sono attività chiave nel processo [prospect-to-cash](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="77705-105">For example, checking inventory and determining a fulfullment date is a key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span> <span data-ttu-id="77705-106">Se non si dispone di scorte sufficienti, è possibile stimare una data di consegna in base a entrate e uscite da magazzino previste.</span><span class="sxs-lookup"><span data-stu-id="77705-106">If you don't have enough inventory, you can estimate a delivery date based on projected inventory receipts and issues.</span></span> <span data-ttu-id="77705-107">È anche possibile verificare le informazioni available-to-promise (ATP) del prodotto, che indicano la quantità ATP nell'intervallo temporale predefinito.</span><span class="sxs-lookup"><span data-stu-id="77705-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the pre-defined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="77705-108">Scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="77705-108">On-hand Inventory</span></span> 

<span data-ttu-id="77705-109">Nell'intestazione dei moduli **Offerte**, **Ordini** o **Fatture** in Dynamics 365 Sales, viene aggiunto un nuovo pulsante **Scorte disponibili**.</span><span class="sxs-lookup"><span data-stu-id="77705-109">In the header of the **Quotes**, **Orders**, or **Invoices** forms in Dynamics 365 Sales, a new button **On-hand Inventory** is added.</span></span> <span data-ttu-id="77705-110">Quando si fa clic sul pulsante, viene visualizzata una finestra di dialogo in cui è possibile specificare la società e il prodotto per i quali si desidera verificare le scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="77705-110">When you click the button, a dialog box appears and you can specify the company and the product for which you want to check the on-hand inventory.</span></span> <span data-ttu-id="77705-111">Vengono restituite le informazioni sulle scorte presenti in Dynamics 365 Supply Chain Management e queste informazioni sono visualizzate come [Scorte disponibili](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="77705-111">It returns the inventory information from Dynamics 365 Supply Chain Management, and shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span> <span data-ttu-id="77705-112">Le informazioni includono queste quantità:</span><span class="sxs-lookup"><span data-stu-id="77705-112">The information includes these quantities:</span></span>

- <span data-ttu-id="77705-113">**Quantità disponibile**</span><span class="sxs-lookup"><span data-stu-id="77705-113">**On-hand Quantity**</span></span>
- <span data-ttu-id="77705-114">**Quantità disponibile prenotata**</span><span class="sxs-lookup"><span data-stu-id="77705-114">**Reserved On-hand Quantity**</span></span>
- <span data-ttu-id="77705-115">**Quantità disponibile utilizzabile**</span><span class="sxs-lookup"><span data-stu-id="77705-115">**Available On-hand Quantity**</span></span>
- <span data-ttu-id="77705-116">**Quantità ordinata**</span><span class="sxs-lookup"><span data-stu-id="77705-116">**Orderd Quantity**</span></span>
- <span data-ttu-id="77705-117">**Quantità in ordinazione**</span><span class="sxs-lookup"><span data-stu-id="77705-117">**On-order Quantity**</span></span>
- <span data-ttu-id="77705-118">**Quantità ordinata prenotata**</span><span class="sxs-lookup"><span data-stu-id="77705-118">**Reserved Ordered Quantity**</span></span>
- <span data-ttu-id="77705-119">**Quantità totale disponibile**</span><span class="sxs-lookup"><span data-stu-id="77705-119">**Total Available Quantity**</span></span>

## <a name="atp-information"></a><span data-ttu-id="77705-120">Informazioni ATP</span><span class="sxs-lookup"><span data-stu-id="77705-120">ATP information</span></span>

<span data-ttu-id="77705-121">Nelle voci dei moduli **Offerte**, **Ordini** o **Fatture** in Dynamics 365 Sales, viene aggiunto un nuovo pulsante **Informazioni ATP**.</span><span class="sxs-lookup"><span data-stu-id="77705-121">On line items of the **Quotes**, **Orders**, or **Invoices** forms in Dynamics 365 Sales, a new button **ATP Information** is added.</span></span> <span data-ttu-id="77705-122">Quando si fa clic sul pulsante, viene visualizzata una finestra di dialogo in cui è possibile specificare la società, il prodotto, il sito magazzino, il magazzino scorte e la quantità dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="77705-122">When you click the button, a dialog box appears and you can specify the company, product, inventory Site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="77705-123">Vengono restituite le **Informazioni ATP** da Supply Chain Management e vengono visualizzate le impostazioni descritte in [Promesse ordine](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="77705-123">It returns the **ATP Information** from Supply Chain Management and shows the settings descrbed in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span> <span data-ttu-id="77705-124">Le informazioni includono **Quantità ATP**, **Quantità entrata**, **Quantità uscita** e **Quantità disponibile**.</span><span class="sxs-lookup"><span data-stu-id="77705-124">The information includes **ATP quantity**, **Receipt quantity**, **Issue quantity**, and **On-hand quantity**.</span></span>
