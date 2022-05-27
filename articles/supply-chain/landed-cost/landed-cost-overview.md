---
title: Modulo Costo sbarcato
description: Il modulo Costo sbarcato consente alle aziende di semplificare le operazioni di spedizione in entrata fornendo agli utenti un controllo finanziario e logistico completo sulle merci importate, dal produttore al magazzino.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: aa6f3baf6e6d980ac3c15e2045d1fcdef08ec296
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694629"
---
# <a name="landed-cost-module"></a>Modulo Costo sbarcato

[!include [banner](../../includes/banner.md)]

Il modulo **Costo sbarcato** consente alle aziende di semplificare le operazioni di spedizione in entrata fornendo agli utenti un controllo finanziario e logistico completo sulle merci importate, dal produttore al magazzino. Per le merci importate, i costi sbarcati possono rappresentare il 40% o più del costo totale di ogni articolo importato. Pertanto, la sfida è fornire stime accurate per i costi sbarcati.

Le aziende possono utilizzare Costo sbarcato per completare le seguenti attività:

- Stimare costi sbarcati al momento della creazione del viaggio.
- Ripartire costi sbarcati su più articoli e ordini fornitore o ordini di trasferimento in un unico viaggio.
- Supportare il trasferimento di merci tra luoghi fisici riconoscendo i costi sbarcati.
- Riconoscere gli accumuli per le merci in transito.

Il modulo Costo sbarcato fornisce stime accurate e tempestive dei costi sbarcati generali. Allo stesso tempo, fornisce una maggiore visibilità finanziaria e logistica nella supply chain estesa. Aiuta inoltre a ridurre le operazioni di gestione della determinazione dei costi e degli errori di determinazione dei costi.

## <a name="highlights"></a>Caratteristiche principali

### <a name="voyages"></a>Viaggi

In Costo sbarcato, un viaggio è un movimento distinto da un'ubicazione in uscita, attraverso un insieme specifico di destinazioni in un periodo specificato, a un'ubicazione di magazzino in entrata specificata. Gli ordini fornitore e le righe d'ordine possono essere aggiunti a un singolo contenitore o più contenitori per un viaggio e i costi verranno allocati correttamente alla riga articolo. 

### <a name="item-ownership"></a>Proprietà degli articoli

In Microsoft Dynamics 365 Supply Chain Management, le merci vengono generalmente ricevute al magazzino di destinazione e quindi fatturate. Tuttavia, la maggior parte degli accordi commerciali internazionali prevede che un'azienda assuma la proprietà delle merci dal momento in cui queste lasciano il porto originale, prima che siano state ricevute fisicamente. Costo sbarcato consente alle aziende di fatturare le merci prima che siano state ricevute fisicamente. Questo concetto è noto come ordine di merci in transito. Crea un nuovo tipo di ordine per gestire il ricevimento delle merci dopo che l'ordine fornitore originale è stato fatturato.

### <a name="costs"></a>Costi

Quando si crea un viaggio in Costo sbarcato, è possibile aggiungervi automaticamente i costi. Questi costi sono impostati in Costo sbarcato e sono disponibili varie basi di costo e opzioni relative ai costi. Ogni costo può essere impostato per diversi livelli di un viaggio e ripartito a livello di articolo tramite regole di ripartizione che supportano quantità, volume, peso, importo e divisori volumetrici definiti. Questi costi stimati forniscono una stima accurata di tutti i costi per un viaggio.

Costo sbarcato esegue quindi un accumulo/registrazione preliminare dei costi sbarcati stimati per garantire un calcolo accurato dei costi stimati al momento della creazione del viaggio. Poiché questi costi automatici vengono fatturati, i costi stimati vengono stornati e sostituiti dai costi effettivi, in base alle fatture di costi.

I costi effettivi sono costi stimati stornati che vengono registrati al momento della fatturazione dei costi utilizzando conti di compensazione impostati per ogni tipo di costo (ad esempio, dazi, trasporto e assicurazione). Queste registrazioni seguono il comportamento di registrazione associato all'articolo specifico. Aggiornano automaticamente la registrazione dell'inventario, indipendentemente dal fatto che il tipo di registrazione sia first in, first out (FIFO), last in, first out (LIFO), media ponderata mobile o media mobile. Sono supportati tutti i tipi di registrazione del gruppo di modelli inventariali. Per la registrazione della media mobile e dei costi standard, sono disponibili conti scostamento di prezzo di acquisto per registrare le differenze tra i costi stimati e quelli effettivi.

### <a name="item-and-order-tracking"></a>Tracciabilità di articoli e ordini

Quando un viaggio passa dall'ubicazione di partenza di origine al magazzino di destinazione finale, gli utenti possono aggiornare ogni fase, o *scalo*, del relativo percorso come necessario. Per ogni scalo, vengono identificati un lead time e uno stato della spedizione. Vengono inoltre identificate le date di consegna confermate per il passaggio allo scalo successivo del percorso. Insieme, queste date di consegna forniscono una data di consegna stimata delle merci al magazzino in entrata. Gli utenti possono modificare queste date di consegna. In questo caso, la data di consegna stimata delle merci viene quindi aggiornata automaticamente, in base ai lead time e agli scali del percorso. La visibilità delle merci in transito per viaggio e imbarcazione è disponibile per ogni contenitore prima del ricevimento della merce. Poiché le date vengono aggiornate su ogni riga dell'ordine fornitore, le aziende hanno un maggiore controllo sulla logistica e sulla pianificazione del magazzino.

## <a name="landed-cost-concepts"></a>Concetti di Costo sbarcato

La tabella seguente riassume alcuni concetti fondamentali di Costo sbarcato.

| Concetto | Descrizione |
|---|---|
| Viaggio | Tipicamente, un viaggio è un'imbarcazione. Tuttavia, a seconda delle pratiche e delle procedure, può essere un fornitore o un ordine fornitore. Non vi sono limitazioni all'uso di questo concetto. |
| Registrazione | Una registrazione è spesso determinata dalle normative doganali. Può essere costituita dalle merci di un fornitore per un'entità/azienda per spedizione. Le merci in una registrazione possono essere in un contenitore o distribuite tra più contenitori. |
| Contenitore di spedizione | I contenitori di spedizione memorizzano le righe dell'ordine fornitore. Sono un livello inferiore al livello di spedizione. In genere vengono utilizzati se i costi sono ripartiti per merci per contenitore o se la ricezione viene effettuata per contenitore. |
| Tipo di contenitore di spedizione | I tipi di contenitore di spedizione possono determinare il prezzo per un tipo di costo (ad esempio, trasporto). Forniscono anche informazioni utili sulla spedizione. |
| Tipo di costo | I tipi di costo identificano i costi associati alle importazioni, come dazi, trasporto e assicurazione. |
| Costo automatico | I costi automatici funzionano come accordi commerciali. Un costo automatico è collegato a un livello di viaggio. |
| Porto | I porti sono aree in cui le merci vengono ricevute e trasferite. |
| Imbarcazione | Un'imbarcazione è il mezzo utilizzato per il trasporto di merci, ad esempio una nave o un aeroplano. |
| Merci in transito | A seconda delle impostazioni, le merci vengono trasferite in un magazzino in transito dopo l'aggiornamento di una fattura. |
| Attività | Le attività possono essere utilizzate per memorizzare ogni fase significativa del percorso tra due porti. Possono essere utilizzate per aggiornare le date. |
| Modello di percorso | I modelli di percorso sono gli itinerari delle merci tra due porti. |

Per un confronto della terminologia e delle funzionalità dei moduli **Costo sbarcato** e **Gestione trasporto** (TMS), vedere [Costo sbarcato e Gestione trasporto](landed-cost-vs-tms.md).
