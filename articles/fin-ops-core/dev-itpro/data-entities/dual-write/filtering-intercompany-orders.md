---
title: Filtrare gli ordini interaziendali per evitare di sincronizzare ordini e righe ordine
description: Questo argomento spiega come filtrare gli ordini interaziendali in modo che le entità Ordini e Righe ordini non siano sincronizzate.
author: negudava
ms.date: 11/09/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: negudava
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 8575f38ca23ef245947a41c35846983604662ef2
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782555"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a>Filtrare gli ordini interaziendali per evitare di sincronizzare ordini e righe ordine

[!include [banner](../../includes/banner.md)]

È possibile filtrare gli ordini interaziendali per evitare di sincronizzare le entità **Ordini** e **Righe ordine**. In alcuni scenari, i dettagli degli ordini interaziendali non sono obbligatori in un'app di interazione con i clienti.

Ciascuna delle tabelle standard Dataverse è estesa tramite riferimenti alla colonna **Ordine interaziendale** e le mappe a doppia scrittura vengono modificate per fare riferimento alle colonne aggiuntive nei filtri. Pertanto, gli ordini interaziendali non vengono più sincronizzati. Questo processo consente di evitare dati non necessari nell'app di interazione con i clienti.

1. Estendere la tabella **Intestazioni ordine cliente CDS** aggiungendo un riferimento alla colonna **Ordine interaziendale**. Questa colonna viene compilata solo negli ordini interaziendali. La colonna **Ordine interaziendale** è disponibile nella tabella **SalesTable**.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Eseguire il mapping dello staging alla pagina di destinazione per le intestazioni degli ordini di vendita CDS.":::

2. Dopo aver esteso le **Intestazioni ordini di vendita CDS**, la colonna **Ordine interaziendale** è disponibile nella mappatura. Applicare un filtro con `INTERCOMPANYORDER == ""` come stringa di query.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Finestra di dialogo Modifica query per le intestazioni degli ordini di vendita CDS.":::

3. Estendere la tabella **Righe ordine cliente CDS** aggiungendo un riferimento alla colonna **IntercompanyInventTransId**. Questa colonna viene compilata solo negli ordini interaziendali. La colonna **IntercompanyInventTransId** è disponibile nella tabella **SalesLine**.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Eseguire il mapping dello staging alla pagina di destinazione per le righe degli ordini di vendita CDS.":::

4. Dopo aver esteso le **Righe ordine cliente CDS**, la colonna **IntercompanyInventTransId** è disponibile nella mappatura. Applicare un filtro con `INTERCOMPANYINVENTTRANSID == ""` come stringa di query.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Finestra di dialogo Modifica query per le intestazioni delle righe degli ordini di vendita CDS.":::

5. Ripetere i passaggi 1 e 2 per estendere la tabella **Intestazione fattura di vendita V2** e aggiungere una query di filtro. In questo caso, utilizzare `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` come stringa di query per il filtro.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Eseguire il mapping dello staging alla pagina di destinazione per l'intestazione fattura di vendita V2.":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Finestra di dialogo Modifica query per l'intestazione fattura di vendita V2.":::

6. Ripetere i passaggi 3 e 4 per estendere la tabella **Righe fattura di vendita V2** e aggiungere una query di filtro. In questo caso, utilizzare `INTERCOMPANYINVENTTRANSID == ""` come stringa di query per il filtro.

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Finestra di dialogo Modifica query per le righe fattura di vendita V2.":::

7. La tabella **Offerte** non ha una relazione interaziendale. Se qualcuno crea un'offerta per uno dei tuoi clienti interaziendali, è possibile utilizzare la colonna **CustGroup** per raggruppare tutti questi clienti in un unico gruppo di clienti. È possibile estendere l'intestazione e le righe aggiungendo la colonna **CustGroup**, quindi filtrare in modo che il gruppo non sia incluso.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Eseguire il mapping dello staging all'intestazione dell'offerta di vendita CDS.":::

8. Dopo aver esteso l'entità **Offerte**, applicare un filtro con `CUSTGROUP != "<company>"` come stringa di query.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Finestra di dialogo Modifica query per l'intestazione offerta di vendita CDS.":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]