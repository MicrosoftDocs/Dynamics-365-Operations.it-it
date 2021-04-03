---
title: Disponibilità delle scorte in doppia scrittura
description: Questo argomento fornisce informazioni su come controllare la disponibilità delle scorte in doppia scrittura.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 48e54c043967ea5db15938857bd8f020dd4dfc64
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566741"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="58e89-103">Disponibilità delle scorte in doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="58e89-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="58e89-104">Utilizzando la disponibilità delle scorte, puoi verificare le scorte prima di aggiungere un prodotto alla pagina **Offerte**, **Ordini** o **Fatture** in Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="58e89-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations**, **Orders**, or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="58e89-105">Ad esempio, la verifica delle scorte e la determinazione di una data di evasione sono attività chiave nel processo [prospect-to-cash](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="58e89-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="58e89-106">Se non si dispone di scorte sufficienti, è possibile stimare una data di consegna in base a entrate e uscite da magazzino previste.</span><span class="sxs-lookup"><span data-stu-id="58e89-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="58e89-107">È anche possibile verificare le informazioni available-to-promise (ATP) del prodotto, che indicano la quantità ATP nell'intervallo temporale predefinito.</span><span class="sxs-lookup"><span data-stu-id="58e89-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="58e89-108">Scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="58e89-108">On-hand inventory</span></span>

<span data-ttu-id="58e89-109">In Dynamics 365 Sales, nell'intestazione delle pagine **Offerte**, **Ordini** e **Fatture**, viene aggiunto un nuovo pulsante **Scorte disponibili**.</span><span class="sxs-lookup"><span data-stu-id="58e89-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="58e89-110">Quando selezioni questo pulsante, viene visualizzata una finestra di dialogo in cui è possibile specificare la società e il prodotto per i quali si desidera verificare le scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="58e89-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="58e89-111">Questa finestra di dialogo mostra le stesse informazioni di [Scorte disponibili](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="58e89-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="58e89-112">La finestra di dialogo restituisce le informazioni di inventario da Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="58e89-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="58e89-113">Queste informazioni includono le seguenti quantità:</span><span class="sxs-lookup"><span data-stu-id="58e89-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="58e89-114">Quantità disponibile</span><span class="sxs-lookup"><span data-stu-id="58e89-114">On-hand quantity</span></span>
- <span data-ttu-id="58e89-115">Quantità disponibile prenotata</span><span class="sxs-lookup"><span data-stu-id="58e89-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="58e89-116">Quantità disponibile utilizzabile</span><span class="sxs-lookup"><span data-stu-id="58e89-116">Available on-hand quantity</span></span>
- <span data-ttu-id="58e89-117">Quantità ordinata</span><span class="sxs-lookup"><span data-stu-id="58e89-117">Ordered quantity</span></span>
- <span data-ttu-id="58e89-118">Quantità in ordinazione</span><span class="sxs-lookup"><span data-stu-id="58e89-118">On-order quantity</span></span>
- <span data-ttu-id="58e89-119">Quantità ordinata prenotata</span><span class="sxs-lookup"><span data-stu-id="58e89-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="58e89-120">Quantità totale disponibile</span><span class="sxs-lookup"><span data-stu-id="58e89-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="58e89-121">Informazioni ATP</span><span class="sxs-lookup"><span data-stu-id="58e89-121">ATP information</span></span>

<span data-ttu-id="58e89-122">Nelle Sales, è stato aggiunto alle voci un nuovo pulsante **Informazioni ATP** nelle pagine **Offerte**, **Ordini** e **Fatture**.</span><span class="sxs-lookup"><span data-stu-id="58e89-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="58e89-123">Quando selezioni questo pulsante, viene visualizzata una finestra di dialogo in cui è possibile specificare la società, il prodotto, il sito magazzino, il magazzino scorte e la quantità dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="58e89-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="58e89-124">Questa finestra di dialogo ha le stesse impostazioni descritte in [Promesse ordine](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="58e89-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="58e89-125">La finestra di dialogo restituisce le informazioni ATP da Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="58e89-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="58e89-126">Queste informazioni includono le seguenti quantità:</span><span class="sxs-lookup"><span data-stu-id="58e89-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="58e89-127">Quantità ATP</span><span class="sxs-lookup"><span data-stu-id="58e89-127">ATP quantity</span></span>
- <span data-ttu-id="58e89-128">Quantità entrata</span><span class="sxs-lookup"><span data-stu-id="58e89-128">Receipt quantity</span></span>
- <span data-ttu-id="58e89-129">Quantità uscita</span><span class="sxs-lookup"><span data-stu-id="58e89-129">Issue quantity</span></span>
- <span data-ttu-id="58e89-130">Quantità disponibile</span><span class="sxs-lookup"><span data-stu-id="58e89-130">On-hand quantity</span></span>

## <a name="how-it-works"></a><span data-ttu-id="58e89-131">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="58e89-131">How it works</span></span>

<span data-ttu-id="58e89-132">Quando selezioni il pulsante **Scorte disponibili** nella pagina **Offerte**, **Ordini** o **Fatture**, viene effettuata una chiamata live a doppia scrittura all'API **Scorte disponibili**.</span><span class="sxs-lookup"><span data-stu-id="58e89-132">When you select the **On-hand Inventory** button on the **Quotes**, **Orders**, or **Invoices** page, a live dual-write call is made to the **Onhand inventory** API.</span></span> <span data-ttu-id="58e89-133">L'API calcola le scorte disponibili per il prodotto specificato.</span><span class="sxs-lookup"><span data-stu-id="58e89-133">The API calculates the on-hand inventory for the given product.</span></span> <span data-ttu-id="58e89-134">Il risultato viene memorizzato nelle tabelle **InventCDSInventoryOnHandRequestEntity** e **InventCDSInventoryOnHandEntryEntity**, quindi viene scritto in Dataverse con doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="58e89-134">The result is stored in the **InventCDSInventoryOnHandRequestEntity** and **InventCDSInventoryOnHandEntryEntity** tables, and then is written to Dataverse by dual-write.</span></span> <span data-ttu-id="58e89-135">Per utilizzare questa funzionalità, è necessario eseguire i seguenti mapping di doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="58e89-135">To use this functionality, you need to run the following dual-write maps.</span></span> <span data-ttu-id="58e89-136">Salta la sincronizzazione iniziale quando esegui i mapping.</span><span class="sxs-lookup"><span data-stu-id="58e89-136">Skip initial synchronization when you run the maps.</span></span>

- <span data-ttu-id="58e89-137">Voci di scorte disponibili CDS (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="58e89-137">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>
- <span data-ttu-id="58e89-138">Richieste di disponibilità di scorte CDS (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="58e89-138">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

## <a name="templates"></a><span data-ttu-id="58e89-139">Modelli</span><span class="sxs-lookup"><span data-stu-id="58e89-139">Templates</span></span>
<span data-ttu-id="58e89-140">I seguenti modelli sono disponibili per l'esposizione dei dati sulle scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="58e89-140">The following templates are available for the exposing the onhand inventory data.</span></span>

<span data-ttu-id="58e89-141">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="58e89-141">Finance and Operations apps</span></span> | <span data-ttu-id="58e89-142">App di interazione con i clienti</span><span class="sxs-lookup"><span data-stu-id="58e89-142">Customer engagement app</span></span> | <span data-ttu-id="58e89-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58e89-143">Description</span></span> 
---|---|---
[<span data-ttu-id="58e89-144">Movimenti scorte disponibili inventario CDS</span><span class="sxs-lookup"><span data-stu-id="58e89-144">CDS inventory on-hand entries</span></span>](#145) | <span data-ttu-id="58e89-145">msdyn_inventoryonhandentries</span><span class="sxs-lookup"><span data-stu-id="58e89-145">msdyn_inventoryonhandentries</span></span> |
[<span data-ttu-id="58e89-146">Richieste scorte disponibili inventario CDS</span><span class="sxs-lookup"><span data-stu-id="58e89-146">CDS inventory on-hand requests</span></span>](#147) | <span data-ttu-id="58e89-147">msdyn_inventoryonhandrequests</span><span class="sxs-lookup"><span data-stu-id="58e89-147">msdyn_inventoryonhandrequests</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

###  <a name="cds-inventory-on-hand-entries-msdyn_inventoryonhandentries"></a><a name="145"></a><span data-ttu-id="58e89-148">Voci di scorte disponibili CDS (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="58e89-148">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>

<span data-ttu-id="58e89-149">Questo modello sincronizza i dati tra le app Finance and Operations e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="58e89-149">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="58e89-150">Campo di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="58e89-150">Finance and Operations field</span></span> | <span data-ttu-id="58e89-151">Tipo di mappa</span><span class="sxs-lookup"><span data-stu-id="58e89-151">Map type</span></span> | <span data-ttu-id="58e89-152">Campo Interazione con i clienti</span><span class="sxs-lookup"><span data-stu-id="58e89-152">Customer engagement field</span></span> | <span data-ttu-id="58e89-153">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="58e89-153">Default value</span></span>
---|---|---|---
`REQUESTID` | = | `msdyn_request.msdyn_requestid` |
`INVENTORYSITEID` | = | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | = | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`AVAILABLEONHANDQUANTITY` | > | `msdyn_availableonhandquantity` |
`AVAILABLEORDEREDQUANTITY` | > | `msdyn_availableorderedquantity` |
`ONHANDQUANTITY` | > | `msdyn_onhandquantity` |
`ONORDERQUANTITY` | > | `msdyn_onorderquantity` |
`ORDEREDQUANTITY` | > | `msdyn_orderedquantity` |
`RESERVEDONHANDQUANTITY` | > | `msdyn_reservedonhandquantity` |
`RESERVEDORDEREDQUANTITY` | > | `msdyn_reservedorderedquantity` |
`TOTALAVAILABLEQUANTITY` | > | `msdyn_totalavailablequantity` |
`ATPDATE` | = | `msdyn_atpdate` |
`ATPQUANTITY` | > | `msdyn_atpquantity` |
`PROJECTEDISSUEQUANTITY` | > | `msdyn_projectedissuequantity` |
`PROJECTEDONHANDQUANTITY` | > | `msdyn_projectedonhandquantity` |
`PROJECTEDRECEIPTQUANTITY` | > | `msdyn_projectedreceiptquantity` |
`ORDERQUANTITY` | > | `msdyn_orderquantity` |
`UNAVAILABLEONHANDQUANTITY` | > | `msdyn_unavailableonhandquantity` |

###  <a name="cds-inventory-on-hand-requests-msdyn_inventoryonhandrequests"></a><a name="147"></a><span data-ttu-id="58e89-154">Richieste di disponibilità di scorte CDS (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="58e89-154">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

<span data-ttu-id="58e89-155">Questo modello sincronizza i dati tra le app Finance and Operations e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="58e89-155">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="58e89-156">Campo di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="58e89-156">Finance and Operations field</span></span> | <span data-ttu-id="58e89-157">Tipo di mappa</span><span class="sxs-lookup"><span data-stu-id="58e89-157">Map type</span></span> | <span data-ttu-id="58e89-158">Campo Interazione con i clienti</span><span class="sxs-lookup"><span data-stu-id="58e89-158">Customer engagement field</span></span> | <span data-ttu-id="58e89-159">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="58e89-159">Default value</span></span>
---|---|---|---
`REQUESTID` | = | `msdyn_requestid` |
`PRODUCTNUMBER` | < | `msdyn_product.msdyn_productnumber` |
`ISATPCALCULATION` | << | `msdyn_isatpcalculation` |
`ORDERQUANTITY` | < | `msdyn_orderquantity` |
`INVENTORYSITEID` | < | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | < | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`REFERENCENUMBER` | < | `msdyn_referencenumber` |
`LINECREATIONSEQUENCENUMBER` | < | `msdyn_linecreationsequencenumber` |






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]