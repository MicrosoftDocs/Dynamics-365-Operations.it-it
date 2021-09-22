---
title: Il numero massimo di decimali per l'unità di stockkeeping è 0
description: "Quando si tenta di registrare una transazione di magazzino o una prenotazione di magazzino, viene visualizzato il seguente messaggio di errore: \"Il numero massimo di decimali per l'unità di stockkeeping è 0\"."
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9dec198e2d77efd2253c80e14d15791cc37f88e1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476807"
---
# <a name="maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a>Il numero massimo di decimali per l'unità di stockkeeping è 0


## <a name="symptoms"></a>Sintomi

Quando si tenta di registrare una transazione di inventario o una prenotazione di inventario, viene visualizzato il seguente messaggio di errore:

> Il numero massimo di decimali per l'unità di stockkeeping è 0.

Questo problema si verifica quando la quantità della transazione di magazzino viene specificata come valore decimale inferiore al livello di precisione supportato dal campo. Ad esempio, una quantità di *0,5* è stata specificato per una transazione di magazzino, ma sono supportate solo quantità intere. Pertanto, il valore dovrebbe essere *1* invece di *0,5*.

## <a name="resolution"></a>Risoluzione

1. Esegui il seguente script sull'istanza di SQL Server per arrotondare le quantità nelle transazioni di magazzino. Questo script correggerà i valori nella tabella **inventTrans**.

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. Esegui un controllo di coerenza delle scorte disponibili dove l'opzione **correggi l'errore** è attivata. Questo controllo correggerà i valori nella tabella **inventSum**.

> [!IMPORTANT]
> Si consiglia vivamente di modificare con attenzione lo script come richiesto per il proprio ambiente, di testarlo in un ambiente di test e quindi di controllare i dati ottenuti prima di eseguire lo script in un ambiente di produzione.
