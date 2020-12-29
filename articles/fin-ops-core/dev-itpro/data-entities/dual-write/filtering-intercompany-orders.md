---
title: Filtrare gli ordini interaziendali per evitare di sincronizzare ordini e righe ordine
description: Questo argomento descrive come filtrare gli ordini interaziendali per evitare di sincronizzare ordini e righe ordine.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: negudava
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 6c5e1e2467673badd20366d3bd8e1b93b8078b26
ms.sourcegitcommit: 0eb33909a419d526eb84b4e4b64d3595d01731ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "4701035"
---
# <a name="filter-intercompany-orders-to-avoid-synchronizing-orders-and-orderlines"></a><span data-ttu-id="3932a-103">Filtrare gli ordini interaziendali per evitare di sincronizzare ordini e righe ordine</span><span class="sxs-lookup"><span data-stu-id="3932a-103">Filter intercompany orders to avoid synchronizing Orders and OrderLines</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3932a-104">È possibile filtrare gli ordini interaziendali per evitare di sincronizzare le entità **Ordini** e **Righe ordine**.</span><span class="sxs-lookup"><span data-stu-id="3932a-104">You can filter intercompany orders to avoid synchronizing the **Orders** and **OrderLines** entities.</span></span> <span data-ttu-id="3932a-105">In alcuni scenari, i dettagli degli ordini interaziendali non sono necessari nell'app Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="3932a-105">In some scenarios, the intercompany order details are not necessary in customer engagement app.</span></span>

<span data-ttu-id="3932a-106">Ciascuna delle entità standard Common Data Service è estesa con riferimenti al campo **Ordine interaziendale** e le mappe a doppia scrittura vengono modificate per fare riferimento ai campi aggiuntivi nei filtri.</span><span class="sxs-lookup"><span data-stu-id="3932a-106">Each of the standard Common Data Service entities is extended with references to the **IntercompanyOrder** field, and the dual-write maps are modified to refer to the additional fields in the filters.</span></span> <span data-ttu-id="3932a-107">Il risultato è che gli ordini interaziendali non sono più sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="3932a-107">The result is that the intercompany orders are no longer synchronized.</span></span> <span data-ttu-id="3932a-108">Questo processo evita dati non necessari nell'app Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="3932a-108">This process avoids unnecessary data in the customer engagement app.</span></span>

1. <span data-ttu-id="3932a-109">Aggiungere un riferimento a **Ordine interaziendale** per **Intestazioni ordini di vendita CDS**.</span><span class="sxs-lookup"><span data-stu-id="3932a-109">Add a reference to **IntercompanyOrder** to **CDS Sales Order Headers**.</span></span> <span data-ttu-id="3932a-110">Viene popolato solo sugli ordini interaziendali.</span><span class="sxs-lookup"><span data-stu-id="3932a-110">It is populated on only intercompany orders.</span></span> <span data-ttu-id="3932a-111">Il campo **Ordine interaziendale** è disponibile in **SalesTable**.</span><span class="sxs-lookup"><span data-stu-id="3932a-111">The field **IntercompanyOrder** is available in **SalesTable**.</span></span>

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mappa gestione temporanea a destinazione, SalesOrderHeader":::
    
2. <span data-ttu-id="3932a-113">Dopo aver esteso le **Intestazioni ordini di vendita CDS**, il campo **Ordine interaziendale** è disponibile nella mappatura.</span><span class="sxs-lookup"><span data-stu-id="3932a-113">After **CDS Sales Order Headers** is extended, the **IntercompanyOrder** field is available in the mapping.</span></span> <span data-ttu-id="3932a-114">Applicare un filtro con `INTERCOMPANYORDER == ""` come stringa di query.</span><span class="sxs-lookup"><span data-stu-id="3932a-114">Apply a filter with `INTERCOMPANYORDER == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Intestazioni degli ordini di vendita, modifica query":::

3. <span data-ttu-id="3932a-116">Aggiungere un riferimento a **IntercompanyInventTransId** per **Righe ordine cliente CDS**.</span><span class="sxs-lookup"><span data-stu-id="3932a-116">Add a reference to **IntercompanyInventTransId** to **CDS Sales Order Lines**.</span></span>  <span data-ttu-id="3932a-117">Viene popolato solo sugli ordini interaziendali.</span><span class="sxs-lookup"><span data-stu-id="3932a-117">It is populated on only intercompany orders.</span></span> <span data-ttu-id="3932a-118">Il campo **IntercompanyInventTransId** è disponibile in **SalesLine**.</span><span class="sxs-lookup"><span data-stu-id="3932a-118">The field **InterCompanyInventTransID** is available in **SalesLine**.</span></span>

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mappa gestione temporanea a destinazione, SalesOrderLine":::

4. <span data-ttu-id="3932a-120">Dopo aver esteso le **Righe ordine cliente CDS**, il campo **IntercompanyInventTransId** è disponibile nella mappatura.</span><span class="sxs-lookup"><span data-stu-id="3932a-120">After **CDS Sales Order Lines** is extended, the **IntercompanyInventTransId** field is available in the mapping.</span></span> <span data-ttu-id="3932a-121">Applicare un filtro con `INTERCOMPANYINVENTTRANSID == ""` come stringa di query.</span><span class="sxs-lookup"><span data-stu-id="3932a-121">Apply a filter with `INTERCOMPANYINVENTTRANSID == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Righe ordine cliente, modifica query":::

5. <span data-ttu-id="3932a-123">Estendere **Intestazioni fattura di vendita V2** e **Righe fattura di vendita V2** nello stesso modo in cui sono state estese le entità Common Data Service nei passaggi 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="3932a-123">Extend **Sales Invoice Header V2** and **Sales Invoice Lines V2** in the same way you extended the Common Data Service entities in steps 1 and 2.</span></span> <span data-ttu-id="3932a-124">Quindi aggiungere le query di filtro.</span><span class="sxs-lookup"><span data-stu-id="3932a-124">Then add the filter queries.</span></span> <span data-ttu-id="3932a-125">La stringa del filtro per **Intestazioni fattura di vendita V2** è `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`.</span><span class="sxs-lookup"><span data-stu-id="3932a-125">The filter string for **Sales Invoice Header V2** is `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`.</span></span> <span data-ttu-id="3932a-126">La stringa del filtro per **Righe fattura di vendita V2** è `INTERCOMPANYINVENTTRANSID == ""`.</span><span class="sxs-lookup"><span data-stu-id="3932a-126">The filter string for **Sales Invoice Lines V2** is `INTERCOMPANYINVENTTRANSID == ""`.</span></span>

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mappa gestione temporanea a destinazione, Intestazioni fattura di vendita":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Intestazioni fattura di vendita, modifica query":::

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Righe fattura di vendita, modifica query":::

6. <span data-ttu-id="3932a-130">L'entità **Offerte** non ha una relazione interaziendale.</span><span class="sxs-lookup"><span data-stu-id="3932a-130">The **Quotations** entity doesn't have an intercompany relationship.</span></span> <span data-ttu-id="3932a-131">Se qualcuno crea un preventivo per uno dei tuoi clienti interaziendali, è possibile raggruppare tutti questi clienti in un unico gruppo di clienti utilizzando il campo **CustGroup**.</span><span class="sxs-lookup"><span data-stu-id="3932a-131">If someone creates a quote for one of your intercompany customers, you can put all of these customers in one customer group by using the **CustGroup** field.</span></span>  <span data-ttu-id="3932a-132">L'intestazione e le righe possono essere estese per aggiungere il campo **CustGroup** e quindi filtrare per non includere questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="3932a-132">Header and lines can be extended to add the **CustGroup** field and then filter to not include this group.</span></span>

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mappa gestione temporanea a destinazione, Intestazione offerta di vendita":::

7. <span data-ttu-id="3932a-134">Dopo aver esteso l'entità **Offerte**, applicare un filtro con `CUSTGROUP !=  "<company>"` come stringa di query.</span><span class="sxs-lookup"><span data-stu-id="3932a-134">After you extent the **Quotations** entity, apply a filter with `CUSTGROUP !=  "<company>"` as the query string.</span></span>

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Intestazione offerta di vendita, modifica query":::
