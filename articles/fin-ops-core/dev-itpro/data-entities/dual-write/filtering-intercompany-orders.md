---
title: Filtrare gli ordini interaziendali per evitare di sincronizzare ordini e righe ordine
description: Questo argomento spiega come filtrare gli ordini interaziendali in modo che le entità Ordini e Righe ordini non siano sincronizzate.
author: negudava
manager: tfehr
ms.date: 11/09/2020
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
ms.author: negudava
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 342db8c1b4337145bfd61f5698ff6de25434a400
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796608"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a><span data-ttu-id="c9a29-103">Filtrare gli ordini interaziendali per evitare di sincronizzare ordini e righe ordine</span><span class="sxs-lookup"><span data-stu-id="c9a29-103">Filter intercompany orders to avoid syncing Orders and OrderLines</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c9a29-104">È possibile filtrare gli ordini interaziendali per evitare di sincronizzare le entità **Ordini** e **Righe ordine**.</span><span class="sxs-lookup"><span data-stu-id="c9a29-104">You can filter intercompany orders so that the **Orders** and **OrderLines** tables aren't synced.</span></span> <span data-ttu-id="c9a29-105">In alcuni scenari, i dettagli degli ordini interaziendali non sono obbligatori in un'app di interazione con i clienti.</span><span class="sxs-lookup"><span data-stu-id="c9a29-105">In some scenarios, the intercompany order details aren't required in a customer engagement app.</span></span>

<span data-ttu-id="c9a29-106">Ciascuna delle tabelle standard Dataverse è estesa tramite riferimenti alla colonna **Ordine interaziendale** e le mappe a doppia scrittura vengono modificate per fare riferimento alle colonne aggiuntive nei filtri.</span><span class="sxs-lookup"><span data-stu-id="c9a29-106">Each standard Dataverse table is extended through references to the **IntercompanyOrder** column, and the dual-write maps are modified so that they refer to the additional columns in the filters.</span></span> <span data-ttu-id="c9a29-107">Pertanto, gli ordini interaziendali non vengono più sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="c9a29-107">Therefore, the intercompany orders are no longer synced.</span></span> <span data-ttu-id="c9a29-108">Questo processo consente di evitare dati non necessari nell'app di interazione con i clienti.</span><span class="sxs-lookup"><span data-stu-id="c9a29-108">This process helps prevent unnecessary data in the customer engagement app.</span></span>

1. <span data-ttu-id="c9a29-109">Estendere la tabella **Intestazioni ordine cliente CDS** aggiungendo un riferimento alla colonna **Ordine interaziendale**.</span><span class="sxs-lookup"><span data-stu-id="c9a29-109">Extend the **CDS Sales Order Headers** table by adding a reference to the **IntercompanyOrder** column.</span></span> <span data-ttu-id="c9a29-110">Questa colonna viene compilata solo negli ordini interaziendali.</span><span class="sxs-lookup"><span data-stu-id="c9a29-110">This column is filled in only on intercompany orders.</span></span> <span data-ttu-id="c9a29-111">La colonna **Ordine interaziendale** è disponibile nella tabella **SalesTable**.</span><span class="sxs-lookup"><span data-stu-id="c9a29-111">The **IntercompanyOrder** column is available in the **SalesTable** table.</span></span>

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Eseguire il mapping dello staging alla pagina di destinazione per le intestazioni degli ordini di vendita CDS":::

2. <span data-ttu-id="c9a29-113">Dopo aver esteso le **Intestazioni ordini di vendita CDS**, la colonna **Ordine interaziendale** è disponibile nella mappatura.</span><span class="sxs-lookup"><span data-stu-id="c9a29-113">After **CDS Sales Order Headers** is extended, the **IntercompanyOrder** column is available in the mapping.</span></span> <span data-ttu-id="c9a29-114">Applicare un filtro con `INTERCOMPANYORDER == ""` come stringa di query.</span><span class="sxs-lookup"><span data-stu-id="c9a29-114">Apply a filter that has `INTERCOMPANYORDER == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Finestra di dialogo Modifica query per le intestazioni degli ordini di vendita CDS":::

3. <span data-ttu-id="c9a29-116">Estendere la tabella **Righe ordine cliente CDS** aggiungendo un riferimento alla colonna **IntercompanyInventTransId**.</span><span class="sxs-lookup"><span data-stu-id="c9a29-116">Extend the **CDS Sales Order Lines** table by adding a reference to the **IntercompanyInventTransId** column.</span></span> <span data-ttu-id="c9a29-117">Questa colonna viene compilata solo negli ordini interaziendali.</span><span class="sxs-lookup"><span data-stu-id="c9a29-117">This column is filled in only on intercompany orders.</span></span> <span data-ttu-id="c9a29-118">La colonna **IntercompanyInventTransId** è disponibile nella tabella **SalesLine**.</span><span class="sxs-lookup"><span data-stu-id="c9a29-118">The **InterCompanyInventTransId** column is available in the **SalesLine** table.</span></span>

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Eseguire il mapping dello staging alla pagina di destinazione per le righe degli ordini di vendita CDS":::

4. <span data-ttu-id="c9a29-120">Dopo aver esteso le **Righe ordine cliente CDS**, la colonna **IntercompanyInventTransId** è disponibile nella mappatura.</span><span class="sxs-lookup"><span data-stu-id="c9a29-120">After **CDS Sales Order Lines** is extended, the **IntercompanyInventTransId** column is available in the mapping.</span></span> <span data-ttu-id="c9a29-121">Applicare un filtro con `INTERCOMPANYINVENTTRANSID == ""` come stringa di query.</span><span class="sxs-lookup"><span data-stu-id="c9a29-121">Apply a filter that has `INTERCOMPANYINVENTTRANSID == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Finestra di dialogo Modifica query per le intestazioni delle righe degli ordini di vendita CDS":::

5. <span data-ttu-id="c9a29-123">Ripetere i passaggi 1 e 2 per estendere la tabella **Intestazione fattura di vendita V2** e aggiungere una query di filtro.</span><span class="sxs-lookup"><span data-stu-id="c9a29-123">Repeat steps 1 and 2 to extend the **Sales Invoice Header V2** table and add a filter query.</span></span> <span data-ttu-id="c9a29-124">In questo caso, utilizzare `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` come stringa di query per il filtro.</span><span class="sxs-lookup"><span data-stu-id="c9a29-124">In this case, use `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` as the query string for the filter.</span></span>

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Eseguire il mapping dello staging alla pagina di destinazione per l'intestazione fattura di vendita V2":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Finestra di dialogo Modifica query per l'intestazione fattura di vendita V2":::

6. <span data-ttu-id="c9a29-127">Ripetere i passaggi 3 e 4 per estendere la tabella **Righe fattura di vendita V2** e aggiungere una query di filtro.</span><span class="sxs-lookup"><span data-stu-id="c9a29-127">Repeat steps 3 and 4 to extend the **Sales Invoice Lines V2** table and add a filter query.</span></span> <span data-ttu-id="c9a29-128">In questo caso, utilizzare `INTERCOMPANYINVENTTRANSID == ""` come stringa di query per il filtro.</span><span class="sxs-lookup"><span data-stu-id="c9a29-128">In this case, use `INTERCOMPANYINVENTTRANSID == ""` as the query string for the filter.</span></span>

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Finestra di dialogo Modifica query per le righe fattura di vendita V2":::

7. <span data-ttu-id="c9a29-130">La tabella **Offerte** non ha una relazione interaziendale.</span><span class="sxs-lookup"><span data-stu-id="c9a29-130">The **Quotations** table doesn't have an intercompany relationship.</span></span> <span data-ttu-id="c9a29-131">Se qualcuno crea un'offerta per uno dei tuoi clienti interaziendali, è possibile utilizzare la colonna **CustGroup** per raggruppare tutti questi clienti in un unico gruppo di clienti.</span><span class="sxs-lookup"><span data-stu-id="c9a29-131">If someone creates a quotation for one of your intercompany customers, you can use the **CustGroup** column to put all those customers into one customer group.</span></span> <span data-ttu-id="c9a29-132">È possibile estendere l'intestazione e le righe aggiungendo la colonna **CustGroup**, quindi filtrare in modo che il gruppo non sia incluso.</span><span class="sxs-lookup"><span data-stu-id="c9a29-132">You can extend the header and lines by adding the **CustGroup** column, and then filter so that the group isn't included.</span></span>

    :::image type="content" source="media/filter-cust-group.png" alt-text="Eseguire il mapping dello staging all'intestazione dell'offerta di vendita CDS":::

8. <span data-ttu-id="c9a29-134">Dopo aver esteso l'entità **Offerte**, applicare un filtro con `CUSTGROUP != "<company>"` come stringa di query.</span><span class="sxs-lookup"><span data-stu-id="c9a29-134">After **Quotations** is extended, apply a filter that has `CUSTGROUP != "<company>"` as the query string.</span></span>

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Finestra di dialogo Modifica query per l'intestazione offerta di vendita CDS":::
