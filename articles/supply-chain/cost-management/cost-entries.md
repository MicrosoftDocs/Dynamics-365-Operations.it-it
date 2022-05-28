---
title: Voci di costo
description: Questo articolo fornisce informazioni sulle voci di costo e sul momento in cui vengono create. Una voce di costo è un record che registra la quantità e il costo di un evento specifico.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 07e0e5f2e579d81fc96e1e03a2c63aea4c5c956f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673272"
---
# <a name="cost-entries"></a>Voci di costo

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sulle voci di costo e sul momento in cui vengono create. Una voce di costo è un record che registra la quantità e il costo di un evento specifico.

Le voci di costo sono aggregazioni delle operazioni di magazzino registrate su dimensioni inventariali finanziarie attive.

## <a name="examples"></a>Esempi
### <a name="example-1-no-cost-entries-are-created"></a>Esempio 1: nessuna voce di costo viene creata

Un evento del giornale di registrazione trasferimenti viene registrato. L'evento trasferisce un pezzo di articolo A dall'ubicazione A all'ubicazione B. La dimensione inventariale dell'ubicazione non viene considerata parte dell'oggetto di costo. Di conseguenza, l'evento crea due operazioni di magazzino e nessuna voce di costo.

### <a name="example-2-cost-entries-are-created"></a>Esempio 2: vengono create voci di costo

Un evento del giornale di registrazione trasferimenti viene registrato. L'evento trasferisce un singolo pezzo dell'articolo A dal sito 1 al sito 2. La dimensione inventariale Sito viene considerata parte dell'oggetto di costo. Di conseguenza, l'evento crea due operazioni di magazzino e due voci di costo.

### <a name="example-3-one-cost-entry-is-created"></a>Esempio 3: viene creata una voce di costo

Un evento dell'entrata prodotti viene registrato per un ordine fornitore. L'evento immette 100 pezzi di un articolo A a un costo unitario di 10,00 euro (EUR). Poiché l'articolo A utilizza un numero di serie per tenere traccia dello scopo di gestione articoli, un numero di serie univoco viene creato per ciascun articolo ricevuto. Di conseguenza, l'evento crea 100 operazioni di magazzino e una voce di costo.

## <a name="cost-entries-page"></a>Pagina Voci di costo
La nuova pagina **Voci di costo** consente di visualizzare e controllare le registrazioni delle quantità e dei costi. Questa pagina fa da complemento alle pagine **Operazione di magazzino** e **Liquidazione magazzino**. I record vengono registrati in ordine storico di un evento. Di conseguenza, è possibile cercare e verificare rapidamente i costi accumulati di un evento specifico o di tutti gli eventi correlati a un documento. Ecco un esempio:

-   Un evento dell'entrata prodotti viene registrato per l'articolo A. Cento pezzi vengono ricevuti al costo unitario di 10,00 EUR.
-   Alcuni giorni dopo che l'evento di fatturazione è stato registrato, il costo aumenta a 11,00 EUR. Di conseguenza, l'importo totale è 1.100 EUR. Un secondo giustificativo viene creato per rappresentare la differenza di 100 EUR.
-   Alcuni giorni dopo spese varie di 15,00 EUR per coprire il costo di trasporto vengono registrate nell'ordine fornitore.

| Giustificativo | Data       | Riferimento      | Numero | ID lotto  | Quantità | Importo  |
|---------|------------|----------------|--------|---------|---------------|----|
| 00001   | 01/01/2015 | Ordine fornitore | 100001 | 0000101 | 100,00   | 1000,00 |
| 00002   | 20/01/2015 | Ordine acquisto | 100001 | 0000101 |          | 100,00  |
| 00003   | 31/01/2015 | Correzione     | 100001 | 0000101 |          | 15,00   |

La pagina **Voci di costo** abilita il filtro in base all'ID e alla data del documento. 

> [!NOTE]
> Le voci di costo sono disponibili solo per gli [oggetti di costo](cost-object.md) o i prodotti rilasciati.

## <a name="additional-resources"></a>Risorse aggiuntive

[Oggetti di costo](cost-object.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]