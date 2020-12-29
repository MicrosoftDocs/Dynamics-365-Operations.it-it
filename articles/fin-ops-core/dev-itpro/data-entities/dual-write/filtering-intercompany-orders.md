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
# <a name="filter-intercompany-orders-to-avoid-synchronizing-orders-and-orderlines"></a>Filtrare gli ordini interaziendali per evitare di sincronizzare ordini e righe ordine

[!include [banner](../../includes/banner.md)]

È possibile filtrare gli ordini interaziendali per evitare di sincronizzare le entità **Ordini** e **Righe ordine**. In alcuni scenari, i dettagli degli ordini interaziendali non sono necessari nell'app Customer Engagement.

Ciascuna delle entità standard Common Data Service è estesa con riferimenti al campo **Ordine interaziendale** e le mappe a doppia scrittura vengono modificate per fare riferimento ai campi aggiuntivi nei filtri. Il risultato è che gli ordini interaziendali non sono più sincronizzati. Questo processo evita dati non necessari nell'app Customer Engagement.

1. Aggiungere un riferimento a **Ordine interaziendale** per **Intestazioni ordini di vendita CDS**. Viene popolato solo sugli ordini interaziendali. Il campo **Ordine interaziendale** è disponibile in **SalesTable**.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mappa gestione temporanea a destinazione, SalesOrderHeader":::
    
2. Dopo aver esteso le **Intestazioni ordini di vendita CDS**, il campo **Ordine interaziendale** è disponibile nella mappatura. Applicare un filtro con `INTERCOMPANYORDER == ""` come stringa di query.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Intestazioni degli ordini di vendita, modifica query":::

3. Aggiungere un riferimento a **IntercompanyInventTransId** per **Righe ordine cliente CDS**.  Viene popolato solo sugli ordini interaziendali. Il campo **IntercompanyInventTransId** è disponibile in **SalesLine**.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mappa gestione temporanea a destinazione, SalesOrderLine":::

4. Dopo aver esteso le **Righe ordine cliente CDS**, il campo **IntercompanyInventTransId** è disponibile nella mappatura. Applicare un filtro con `INTERCOMPANYINVENTTRANSID == ""` come stringa di query.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Righe ordine cliente, modifica query":::

5. Estendere **Intestazioni fattura di vendita V2** e **Righe fattura di vendita V2** nello stesso modo in cui sono state estese le entità Common Data Service nei passaggi 1 e 2. Quindi aggiungere le query di filtro. La stringa del filtro per **Intestazioni fattura di vendita V2** è `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`. La stringa del filtro per **Righe fattura di vendita V2** è `INTERCOMPANYINVENTTRANSID == ""`.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mappa gestione temporanea a destinazione, Intestazioni fattura di vendita":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Intestazioni fattura di vendita, modifica query":::

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Righe fattura di vendita, modifica query":::

6. L'entità **Offerte** non ha una relazione interaziendale. Se qualcuno crea un preventivo per uno dei tuoi clienti interaziendali, è possibile raggruppare tutti questi clienti in un unico gruppo di clienti utilizzando il campo **CustGroup**.  L'intestazione e le righe possono essere estese per aggiungere il campo **CustGroup** e quindi filtrare per non includere questo gruppo.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mappa gestione temporanea a destinazione, Intestazione offerta di vendita":::

7. Dopo aver esteso l'entità **Offerte**, applicare un filtro con `CUSTGROUP !=  "<company>"` come stringa di query.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Intestazione offerta di vendita, modifica query":::
