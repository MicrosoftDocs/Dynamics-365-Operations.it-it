---
title: Miglioramenti POS per prodotti in serie
description: "Questo argomento elenca i miglioramenti apportati ai prodotti in serie per risparmiare tempo e migliorare la produttività."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-08-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 74a27761c065e475fa7c10c5812f0307df9f570e
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---

# <a name="pos-improvements-for-serialized-products"></a>Miglioramenti POS per prodotti in serie

[!include[banner](includes/banner.md)]

## <a name="overview"></a>Panoramica 
In base alle impostazioni in Retail Headquarters, i prodotti possono essere classificati come in serie o non in serie. Quando i prodotti sono in serie, a ogni articolo può essere assegnato un numero univoco che consente di tenere traccia delle garanzie, identificare gli articoli e confermare la proprietà. Sebbene la capacità di fornire numeri di serie per prodotti in serie fosse già presente in Modern POS (POS) e POS cloud, sono stati aggiunti alcuni miglioramenti per consentire ai cassieri di risparmiare tempo ed essere più produttivi.  

## <a name="pos-improvements"></a>Miglioramenti POS

- **I numeri di serie non sono necessari fino al check out**: in precedenza, un cassiere che aggiungeva un prodotto in serie alla transazione doveva immettere un numero di serie. Questa necessità era un problema negli scenari di fidelizzazione dei clienti, nel caso in cui cassieri e assistenti alle vendite avessero l'opportunità di eseguire l'upselling di prodotti. Fino alla fase di pagamento, i prodotti erano spesso aggiornati nel carrello. Di conseguenza, ogni volta che un cassiere aggiungeva un nuovo prodotto, il sistema richiedeva l'immissione del numero di serie. La finestra di dialogo del numero di serie ora include il pulsante **Aggiungi in seguito**. Di conseguenza, gli assistenti alle vendite possono aggiungere l'articolo alla transazione e immettere il numero di serie in seguito. Gli assistenti alle vendite possono aggiungere e sostituire rapidamente gli articoli in serie nel carrello e immettere il numero di serie appena prima del checkout. Se il numero di serie non viene indicato per qualsiasi prodotto in serie, un cassiere che cerca di completare la transazione riceve un messaggio di errore. Questo messaggio indica che il cassiere deve immettere i numeri di serie mancanti per poter continuare.

    Per ogni articolo in serie il cui numero di serie non è stato specificato, viene visualizzato un commento sotto la riga della transazione. Questo commento indica che il numero di serie non è stato specificato per l'articolo. Di conseguenza, il cassiere può trovare rapidamente gli articoli senza numero di serie.

    Una nuova operazione **Aggiungi numero di serie** fornisce il numero di serie per gli articoli senza numero di serie. Dopo l'immissione, il numero di serie non può essere modificato. Il cassiere deve annullare la riga e aggiungere nuovamente il prodotto. 
    
- **I numeri di serie non sono necessari per piazzare ordini cliente**: gli ordini cliente possono essere eseguiti in un punto vendita ed evasi in un altro. Un cassiere che piazza un ordine cliente non deve fornire il numero di serie. Il numero di serie verrà indicato durante la fase di prelievo. Tuttavia, un numero di serie deve essere specificato per tutti gli articoli per i quali è stato selezionato il tipo di consegna **Esegui**. In caso contrario, la transazione non può essere completata.    
- **I prodotti in serie non sono aggregati nella schermata della transazione**: l'impostazione **Aggrega prodotti** nel gruppo di campi **Terminale** della pagina **Profilo funzionalità** consente di aggregare gli stessi prodotti non in serie nella schermata della transazione. Quando gli stessi prodotti vengono aggregati, sono più facili da visualizzare nella griglia della transazione. Tuttavia, poiché i numeri di serie sono in genere univoci e gli assistenti alle vendite non devono immettere numeri di serie fino al checkout, l'impostazione **Aggrega prodotti** non viene applicata ai prodotti in serie. Di conseguenza, i prodotti in serie non verranno aggregati nella schermata della transazione se l'impostazione **Aggrega prodotti** è selezionata.
- **Possibilità di cercare i giornali di registrazione per numero di serie** - I giornali di registrazione possono ora essere ulteriormente ricercati per numero di serie. A tale scopo, aprire l'operazione "Giornali di registrazione" e premere il pulsante "Ricerca avanzata" nella barra delle applicazioni. Utilizzando il pulsante "Aggiungi filtro", è anche possibile applicare un filtro per cercare i numeri di serie.

