---
title: Posizione di cassa (anteprima)
description: Questo argomento descrive in che modo la funzionalità Previsione di cassa prevede la posizione di cassa di un'organizzazione per orari specifici. Descrive inoltre le opzioni disponibili per mostrare le previsioni per periodi diversi.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 64b8dcd43024e5c26d33bf12c5fe198711adde56
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645892"
---
# <a name="cash-position-preview"></a>Posizione di cassa (anteprima)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

La posizione di cassa è la proiezione del flusso di cassa previsto per il breve termine. Si basa sulla proiezione di incassi da clienti che pagano fatture e ordini in sospeso e anche sulla proiezione di esborsi in contanti pagati ai fornitori per fatture e ordini di acquisto.

Quando il sistema prevede i pagamenti dei clienti, utilizza le previsioni di pagamento dalla funzionalità di previsione dei pagamenti dei clienti. Senza previsioni di pagamento, per calcolare una data di pagamento viene utilizzato il tempo medio necessario per convertire una fattura cliente in un pagamento per ciascun cliente. Per gli ordini cliente aperti, il sistema calcola la data della fattura utilizzando il numero medio di giorni per la fatturazione delle righe ordine per cliente. Quindi utilizza la data della fattura come input per la funzionalità di previsione del pagamento. La funzionalità di previsione del pagamento del cliente calcola una data di pagamento per ciascuna riga dell'ordine. 

<*Ho bisogno di testo da Jarek o Dave su come le previsioni di pagamento vengono convertite in una data* > La data di pagamento per le fatture in sospeso è calcolata in modo approssimativo [*stimata*] a partitre dalle previsioni di pagamento selezionando una data che corrisponde al cinquantesimo percentile della funzione di distribuzione cumulativa ottenuta dalle probabilità del bucket previsto.

Un approccio simile viene utilizzato per prevedere i pagamenti ai fornitori. Per ogni fornitore, il sistema calcola il tempo medio necessario per convertire una fattura fornitore in un pagamento. Tale numero di giorni viene quindi utilizzato per calcolare la data di pagamento. Per gli ordini fornitore aperti, il sistema calcola la data della fattura considerando il numero medio di giorni necessari per convertire le righe ordine in una fattura per ogni fornitore. Per ogni fornitore, il sistema calcola quindi la data di pagamento mediante il tempo medio necessario per convertire una fattura fornitore in un pagamento.

La sezione superiore della scheda **Posizione di cassa** include un grafico della posizione di cassa. Questo grafico mostra i flussi di cassa in entrata e in uscita e il loro impatto sul saldo di liquidità totale. I dettagli nel grafico della posizione di cassa possono essere visualizzati in periodi giornalieri, settimanali, mensili o trimestrali. Quando selezioni **Giornaliero**, puoi visualizzare le previsioni per i prossimi 21 giorni. Quando selezioni **Settimanale**, puoi visualizzare le previsioni per le prossime 20 settimane. Quando selezioni **Mensile**, puoi visualizzare le previsioni per i prossimi 12 mesi. Quando selezioni **Trimestrale**, puoi visualizzare le previsioni per i prossimi 12 trimestri. Puoi nascondere il grafico se è necessario spazio aggiuntivo sullo schermo per visualizzare il contenuto della scheda **Posizione di cassa**.

La sezione inferiore della scheda **Posizione di cassa** mostra i dettagli per la posizione, il flusso di cassa, i pagamenti previsti e il conto bancario.

- Le informazioni nella griglia **Dettagli posizioni** vengono presentate in tre sezioni: un elenco di conti di liquidità, un elenco di documenti che costituiscono i flussi di cassa in entrata e un elenco di documenti che costituiscono i flussi di cassa in uscita. La griglia mostra anche i saldi delle posizioni di cassa. Per il primo periodo visualizzato, il saldo per i conti di liquidità è il saldo iniziale. Per i periodi successivi, i saldi per i conti di liquidità sono calcolati sulla base della somma dei flussi di cassa in entrata e della sottrazione dei flussi di cassa in uscita dai periodi precedenti. Per visualizzare i dettagli delle transazioni che compongono il saldo, seleziona il collegamento **Saldo**.
- La griglia **Flusso di cassa** mostra i flussi di cassa in entrata, i flussi di cassa in uscita aggregati per periodo e il loro impatto sui saldi dei conti di liquidità. Per il primo periodo, il saldo per i conti di liquidità è il saldo iniziale. Per i periodi successivi, i saldi per i conti di liquidità sono calcolati sulla base della somma dei flussi di cassa in entrata e della sottrazione dei flussi di cassa in uscita dai periodi precedenti.
- La griglia **Saldo bancario previsto** mostra i flussi di cassa in uscita previsti e il loro impatto sui conti di liquidità.
- La griglia **Conto bancario** mostra l'impatto dei flussi di cassa in entrata e in uscita previsti sul saldo bancario.

Per salvare e modificare la posizione di cassa, crea uno snapshot. Per ulteriori informazioni su come utilizzare gli snapshot, vedi [Panoramica degli snapshot](payment-snapshots.md).

#### <a name="privacy-notice"></a>Informativa sulla privacy
Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]