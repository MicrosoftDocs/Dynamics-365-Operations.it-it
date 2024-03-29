---
title: Tracciare un articolo o la materia prima
description: Questa procedura dimostra come utilizzare la tracciabilità articolo per identificare gli articoli o le materie prime che sono stati utilizzati o vengono utilizzati.
author: yufeihuang
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria, InventTrackingItemIdLookup, InventBatchIdLookup, CustTable, SalesLine
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c01cabf32542798f70720ab0db7d055fc54cf345
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575826"
---
# <a name="trace-an-item-or-raw-material"></a>Tracciare un articolo o la materia prima

[!include [banner](../../includes/banner.md)]

Questa procedura dimostra come utilizzare la tracciabilità articolo per identificare gli articoli o le materie prime che sono stati utilizzati o vengono utilizzati. Con questa procedura è possibile identificare un articolo, risalire all'origine, quindi tracciarlo in avanti attraverso la produzione e la vendita del prodotto finito. Il processo può essere utilizzato per esaminare i clienti interessati, gli ordini clienti interessati e altro. Questa procedura utilizza la società di dati dimostrativi USP2.


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a>Tracciare un articolo a ritroso utilizzando un numero batch noto
1. Nel **pannello di navigazione**, andare a **Moduli > Gestione articoli > Richieste di informazioni e report > Dimensioni di tracciabilità > Tracciabilità articolo**.
2. Nel campo **Numero articolo** selezionare "P9100".
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Nel campo **Avanti o indietro**, selezionare "Indietro".
5. Nel campo **Numero batch** selezionare "as-12-344-01".
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Fare clic su **OK**.

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a>Identificare un articolo, tracciarlo in avanti e fare un'analisi

Il nodo principale della struttura rappresenta la quantità disponibile dell'articolo e del batch selezionati. È necessario espandere i nodi della struttura per trovare l'articolo su cui deve essere eseguita la tracciabilità in avanti.   
1. Nella struttura espandere "i nodi descritti sotto, quindi selezionare l'ultimo nodo".
    
    Espandere: "P9100 / 1 / 10 / as-12-344-01 ● 2 keg ● 7,00 gal \P9100 ● Prelevato ● Ordine cliente 000072 ● 12/22/2015 ● -1 keg ● -4,00 gal ● Sito=1, Magazzino=10, Numero batch=as-12-344-01 \P9100 ● Produzione B-000050 ● 12/9/2015● 7 keg ● 27,00 gal ● Sito=1, Magazzino=10, Numero batch=as-12-344-01 ● Co-prodotti: P9101", quindi selezionare quel nodo.     
2. Nella struttura espandere "il nodo descritto sotto, quindi selezionare quel nodo".
    
    A partire dal nodo appena selezionato, espandere "M9103 ● Riga produzione B-000050 ● 12/9/2015 ● -160,00 lb ● Dimensione=70, Colore=OK, Sito=1, Magazzino=10, Numero batch=App01", quindi selezionare quel nodo.  
3. Fare clic su **Traccia da nodo**.
4. Fare clic su **Avanti**.
5. Nel **riquadro azioni** fare clic su **Tracciatura**.
    
    Sono disponibili più opzioni di tracciabilità che forniscono informazioni sui clienti interessati dall'articolo che si sta tracciando e sugli ordini cliente correlati all'articolo che sono stati sia spediti che non spediti.   
6. Fare clic su **Clienti**.
7. Chiudere la pagina.
8. Nel **riquadro azioni** fare clic su **Tracciatura**.
9. Fare clic su **Ordini cliente spediti**.
10. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]