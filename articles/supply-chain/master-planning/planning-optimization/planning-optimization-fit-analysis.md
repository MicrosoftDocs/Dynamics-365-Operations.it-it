---
title: Analisi corrispondenza Ottimizzazione pianificazione
description: Questo articolo spiega come verificare la configurazione e i dati correnti rispetto alle funzionalità della funzionalità di ottimizzazione di pianificazione.
author: t-benebo
ms.date: 08/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsFitAnalysis, MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 15ec53c1f13b3017fb6e829bd1c8e99fbb938ce3
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689996"
---
# <a name="planning-optimization-fit-analysis"></a>Analisi di adeguatezza dell'ottimizzazione di pianificazione

[!include [banner](../../includes/banner.md)]

Devi analizzare il risultato dell'analisi di adeguatezza dell'ottimizzazione di pianificazione come parte del processo di migrazione. Nota che l'ambito dell'ottimizzazione di pianificazione non è uguale alla funzionalità di pianificazione generale incorporata corrente. Ti consigliamo di collaborare con il tuo partner e di leggere la documentazione per prepararti alla migrazione. 

L'analisi di adeguatezza dell'ottimizzazione di pianificazione ti aiuta a identificare dove il risultato potrebbe differire tra il motore di pianificazione generale integrato e l'ottimizzazione di pianificazione. Questa analisi viene eseguita in base alla configurazione e ai dati correnti. 

Per vedere il risultato dell'analisi di adeguatezza dell'ottimizzazione di pianificazione, vai a **Pianificazione generale** \> **Impostazione** \> **Analisi di adeguatezza dell'ottimizzazione di pianificazione** e quindi seleziona **Esegui analisi**. Se l'analisi rileva delle incoerenze, vengono elencate nella stessa pagina. L'esecuzione dell'analisi può richiedere alcuni minuti.

> [!NOTE]
>
> - Alcune incongruenze non possono essere identificate dall'analisi di adattamento di Planning Optimization. Per maggiori informazioni, vedere [Differenze tra la pianificazione generale classica e l'ottimizzazione della pianificazione](planning-optimization-differences-with-built-in.md).
>
> - In caso di incongruenze, sarà comunque possibile utilizzare l'ottimizzazione di pianificazione. I risultati dell'analisi di adeguatezza indicano le posizioni in cui il servizio di pianificazione non onorerà la configurazione corrente. Ciò significa che indicano le posizioni in cui i processi potrebbero essere ignorati o non essere supportati.

## <a name="analysis-results-example-1"></a>Risultati dell'analisi: Esempio 1

- **Funzionalità:** Produzione
- **Problema:** Articoli con un livello distinta base (BOM) maggiore di zero: 56
- **Spiegazione:** l'analisi di adeguatezza ha rilevato 56 articoli con l' impostazione della distinta base per la produzione. Poiché l'attuale versione di ottimizzazione di pianificazione non supporta la produzione, ottimizzazione di pianificazione genera ordini fornitore pianificati anziché ordini di produzione pianificati. Mostra anche un avviso che elenca gli articoli interessati.

## <a name="analysis-results-example-2"></a>Risultati dell'analisi: Esempio 2

- **Funzionalità:** Azioni
- **Problema:** Gruppi di copertura con calcolo delle azioni abilitato: 6
- **Descrizione:** L'analisi di adeguatezza ha rilevato sei gruppi di copertura in cui il calcolo dell'azione è abilitato. Poiché la versione corrente dell'ottimizzazione di pianificazione non supporta le azioni, non viene generata alcuna azione durante la pianificazione generale.

## <a name="overview-of-possible-results-from-the-fit-analysis"></a>Panoramica dei possibili risultati dell'analisi di adeguatezza

La tabella seguente mostra i vari risultati che possono essere mostrati dopo un'analisi di adeguatezza. Il segno di cancelletto (*\#*) verrà sostituito con un numero che indica il numero di record che presentano il problema elencato.

> [!IMPORTANT]
> Per le funzionalità che non sono ancora supportate, la tabella seguente fornisce informazioni sulla disponibilità prevista stimate in base alla nostra roadmap corrente. Queste stime sono soggette a modifiche senza preavviso.

| Funzionalità | Problema elencato | Spiegazione | Disponibilità prevista |
| --- | --- | --- | --- |
| Azioni | Gruppi di copertura con il calcolo delle azioni abilitato: *\#* | Questa funzionalità è ora supportata. | Supportata |
| Calendari di base | Calendari che utilizzano il calendario di base: *\#* | Questa funzionalità è ora supportata. | Supportata | 
| Codici smaltimento batch | Smaltimenti batch generali non nettificabili: *\#* | Questa funzionalità è ora supportata. Per informazioni aggiuntive, vedi [Utilizzare i codici smaltimento batch per contrassegnare i batch come disponibili o non disponibili](../../inventory/batch-disposition-codes.md) | Supportata |
| Capable-to-promise (CTP) | Impostazioni predefinite ordine con controllo data di consegna impostato su CTP: *\#* | In Supply Chain Management 10.0.28 e versioni successive, un processo denominato *CTP per Ottimizzazione pianificazione* rende disponibili le date di spedizione e di ricezione dopo l'esecuzione del piano dinamico. Per le versioni precedenti di Supply Chain Management, l'impostazione CTP legacy viene ignorata quando Pianificazione ottimizzazione è abilitata. | Supportata |
| Copia piano statico in piano dinamico | La copia del piano statico in quello dinamico è abilitata nei parametri di pianificazione generale. | L'ottimizzazione della pianificazione non copia il piano statico nel piano dinamico, indipendentemente da questa impostazione. In generale, questo concetto è meno rilevante a causa della velocità e della rigenerazione completa fornita dall'ottimizzazione della pianificazione. Se vengono utilizzati due o più piani, è necessario attivare la pianificazione generale per ciascun piano. | N/D |
| Stabilizzazione | Gruppi di copertura con intervallo temporale di stabilizzazione automatica impostato: *\#* | Nella versione 10.0.7 e successive, la stabilizzazione è supportata come processo di stabilizzazione batch separato al termine della pianificazione generale (a condizione che la funzionalità *Stabilizzazione automatica per l'ottimizzazione della pianificazione* sia stata abilitata in [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Si noti che la stabilizzazione automatica per l'ottimizzazione della pianificazione si basa sulla data dell'ordine di lavoro (data di inizio) e non sulla data del fabbisogno (data di fine). Questo comportamento garantisce che la stabilizzazione degli ordini pianificati si verifichi alla scadenza, senza dover includere i tempi di consegna nel tempo di risposta. | Supportata |
| Stabilizzazione | Record di copertura articoli con stabilizzazione automatica impostata: *\#* | Nella versione 10.0.7 e successive, la stabilizzazione automatica è supportata come processo di stabilizzazione batch separato al termine della pianificazione generale (a condizione che la funzionalità *Stabilizzazione automatica per l'ottimizzazione della pianificazione* è stata abilitata in [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Si noti che la stabilizzazione automatica per l'ottimizzazione della pianificazione si basa sulla data dell'ordine di lavoro (data di inizio) e non sulla data del fabbisogno (data di fine). Questo comportamento garantisce che la stabilizzazione degli ordini pianificati si verifichi alla scadenza, senza dover includere i tempi di consegna nel tempo di risposta. | Supportata |
| Stabilizzazione | Piani generali con stabilizzazione automatica impostata: *\#* | Nella versione 10.0.7 e successive, la stabilizzazione automatica è supportata come processo di stabilizzazione batch separato al termine della pianificazione generale (a condizione che la funzionalità *Stabilizzazione automatica per l'ottimizzazione della pianificazione* è stata abilitata in [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Si noti che la stabilizzazione automatica per l'ottimizzazione della pianificazione si basa sulla data dell'ordine di lavoro (data di inizio) e non sulla data del fabbisogno (data di fine). Questo comportamento garantisce che la stabilizzazione degli ordini pianificati si verifichi alla scadenza, senza dover includere i tempi di consegna nel tempo di risposta. | Supportata |
| FitAnalysisPlanningItems | Articoli di pianificazione: *\#* | Questa funzione è in sospeso. Attualmente, gli articoli di pianificazione vengono gestiti come gli articoli normali quando è abilitata l'ottimizzazione della pianificazione. | Ciclo di rilascio 2 o successivo del 2022 |
| Prevista | Gruppi di copertura con "Includi ordini interaziendali" abilitati: *\#* | Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Pianificazione interaziendale](Intercompany-planning.md) | Supportata |
| Prevista | Gruppi di copertura con impostazione "Riduci previsione per" impostata su un valore diverso rispetto a "Ordini": *\#* | Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Pianificazione generale con previsioni della domanda](demand-forecast.md) | Supportata |
| Prevista | Modelli previsionali con sottomodelli: *\#* |  Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Pianificazione generale con previsioni della domanda](demand-forecast.md) | Supportata |
| Prevista | Piani generali con "Includi previsione offerta" abilitati: *\#* | Questa funzione è in sospeso. Attualmente, le previsioni offerta non sono supportate quando è abilitata l'ottimizzazione della pianificazione. Saranno ignorati, indipendentemente da questa impostazione. | Ciclo di rilascio 2 o successivo del 2022 |
| Intervallo temporale blocco | Gruppi di copertura con intervallo temporale blocco impostato: *\#* | Questa funzione è in sospeso. Attualmente, l'impostazione dell'intervallo temporale blocco viene ignorata quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | Ciclo di rilascio 2 del 2022 |
| Intervallo temporale blocco | Record di copertura articoli con intervallo temporale blocco impostato: *\#* | Questa funzione è in sospeso. Attualmente, l'impostazione dell'intervallo temporale blocco viene ignorata quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | Ciclo di rilascio 2 del 2022 |
| Intervallo temporale blocco | Piani generali con intervallo temporale blocco impostato: *\#* | Questa funzione è in sospeso. Attualmente, l'impostazione dell'intervallo temporale blocco viene ignorata quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | Ciclo di rilascio 2 del 2022 |
| Interaziendale | Piani generali che includono la domanda downstream pianificata: *\#* | Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Pianificazione interaziendale](Intercompany-planning.md) | Supportata |
| Kanban | Record di copertura articoli con kanban di tipo di ordine pianificato: *\#* | Questa funzione è in sospeso. Attualmente, la copertura degli articoli impostata su kanban verrà ignorata quando è abilitata l'ottimizzazione della pianificazione. Il tipo di ordine pianificato kanban creerà un avviso durante la pianificazione generale e verranno creati ordini fornitore pianificati per coprire la domanda relativa. | Ciclo futuro |
| Kanban | Articoli con ordine di tipo kanban predefinito: *\#* | Attualmente, un tipo di ordine predefinito impostato su kanban verrà ignorato quando è abilitata l'ottimizzazione della pianificazione. Il tipo di ordine predefinito kanban creerà un avviso durante la pianificazione generale e verranno creati ordini fornitore pianificati per coprire la domanda relativa. | Ciclo futuro |
| Stato del ciclo di vita prodotto | Stati del ciclo di vita prodotto non attivi per la pianificazione: *\#* | Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Escludere i prodotti con stati del ciclo di vita prodotto specifici](product-lifecycle-state.md) | Supportata |
| Produzione | Righe DBA con arrotondamento o impostazione multipla *\#* | Questa funzione è in sospeso. Attualmente, l'arrotondamento e le impostazioni multiple vengono ignorate sulle righe DBA quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | Ciclo futuro|
| Produzione | Righe DBA/formula con misura formula: *\#* | Questa funzione è in sospeso. Attualmente, la misura della formula viene ignorata in DBA e nelle righe della formula quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | Ciclo di rilascio 2 del 2022 |
| Produzione | Righe DBA/formula con sostituzione articolo (gruppi di piani): *\#* | Questa funzione è in sospeso. Attualmente, la sostituzione degli articoli (gruppi di pianificazione) viene ignorata in DBA e nelle righe formula quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | Ciclo di rilascio 2 del 2022 |
| Produzione | Righe DBA/formula con quantità negativa: *\#* | Questa funzione è in sospeso. Le DBA e le righe formula con una quantità negativa verranno incluse con una quantità pari a 0 (zero) e verrà emesso un avviso quando l'ottimizzazione della pianificazione è abilitata. Aggiorna i dati master per evitare avvisi. | Ciclo di rilascio 2 del 2022 |
| Produzione | Righe DBA/formula con consumo risorsa: *\#* | Questa funzione è in sospeso. Attualmente, le DBA e righe formula con consumo di risorse sono ignorate quando è abilitata l'ottimizzazione della pianificazione. Quando questa funzionalità è supportata, il fabbisogno di materiale verrà impostato sulla data di inizio della produzione. Fino a quando questa funzionalità non sarà supportata, i requisiti non verranno generati per i materiali contrassegnati con un flag di consumo di risorse. | Ciclo di rilascio 2 del 2022 |
| Produzione | Righe DBA/formula con consumo fase: *\#* | Questa funzione è in sospeso. Attualmente, le DBA e righe formula con consumo per fasi sono ignorate quando è abilitata l'ottimizzazione della pianificazione. | Ciclo di rilascio 2 del 2022 |
| Produzione | DBA con scarto costante o variabile definito: *\#* | Questa funzione è in sospeso. Attualmente, gli scarti costanti e gli scarti variabili definiti in DBA vengono ignorati quando è abilitata l'ottimizzazione della pianificazione. | Ciclo di rilascio 2 del 2022 |
| Produzione | DBA con conto lavoro: *\#* | Questa funzionalità è ora supportata. | Supportata |
| Produzione | DBA senza un sito: *\#* | Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Pianificazione della produzione](production-planning.md) | Supportata |
| Produzione | Richiesta con distinta DBA specifica o requisiti di percorso definiti: *\#* | Questa funzione è in sospeso. Attualmente, i requisiti delle DBA o dei percorsi specifici definiti sulla domanda (come una distinta base secondaria o un ciclo di lavorazione secondario su un ordine cliente) vengono ignorati quando è abilitata l'ottimizzazione della pianificazione. Verrà utilizzata la distinta base o il ciclo di lavorazione standard, indipendentemente da questa impostazione. | Ciclo di rilascio 2 del 2022 |
| Produzione | Versioni formula con sotto/co-prodotti: *\#* | Questa funzione è in sospeso. Attualmente, i coprodotti e i sottoprodotti associati alla versione della formula vengono ignorati quando è abilitata l'ottimizzazione della pianificazione. | Ciclo di rilascio 2 del 2022 |
| Produzione | Versioni formula con resa: *\#* | Questa funzione è in sospeso. Attualmente, il rendimento associato alla versione della formula viene ignorato quando è abilitata l'ottimizzazione della pianificazione. | Ciclo di rilascio 2 del 2022 |
| Produzione | Piani che includono la sequenza: *\#* | Questa funzione è in sospeso. Attualmente, la sequenza viene ignorata quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | Ciclo di rilascio 2 del 2022 |
| Produzione | Ordini di produzione rilasciati non avviati, il cui avvio programmato è precedente alla data odierna: *\#* | Questa funzione è in sospeso. Attualmente, se un ordine di produzione viene ritardato, la pianificazione generale presumerà che sarà completato oggi. Ciò è rilevante per gli ordini di produzione rilasciati in cui una data di consegna è nel passato, ma non è stata ancora completata. | Ciclo futuro |
| Produzione | Risorse programmate con capacità limitata: *\#* | Questa funzionalità è ora supportata.| Supportata |
| Produzione | Cicli di lavorazione utilizzati nella pianificazione: *\#* | Questa funzionalità è supportata. | Supportata |
| Produzione | Prenotazione riga vendite mediante esplosione: *\#* | La prenotazione della riga di vendita che utilizza l'esplosione non è supportata quando l'ottimizzazione della pianificazione è abilitata. | Ciclo futuro |
| Produzione | Programmazione con esplosione degli ordini di produzione: *\#* | La programmazione che utilizza l'esplosione degli ordini di produzione non è supportata quando l'ottimizzazione della pianificazione è abilitata. Gli ordini di produzione possono essere programmati singolarmente. | Ciclo futuro |
| Richieste di offerta | Piani generali con richieste di offerte abilitate: *\#* | Questa funzione è in sospeso. Al momento, le richieste di offerta (RdO) non sono considerate richieste quando è abilitata l'ottimizzazione della pianificazione. Saranno ignorati, indipendentemente da questa impostazione. | Ciclo di rilascio 2 del 2022 |
| Richieste | Piani generali con richieste abilitate: *\#* | Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Richieste di acquisto](purchase-requisitions.md) | Supportata |
| Margini di sicurezza | Gruppi di copertura con margine di sicurezza: *\#* | Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Margini di sicurezza](safety-margins.md) | Supportata |
| Margini di sicurezza | Piani generali con margine di sicurezza: *\#* | Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Margini di sicurezza](safety-margins.md) |  Supportata |
| Garanzia scorte di sicurezza | Record di copertura articoli con "Soddisfa minimo" diverso da "Data odierna + tempo di approvvigionamento": *\#* | L'ottimizzazione della pianificazione utilizza sempre *Data odierna + tempo di approvvigionamento*. Questa modifica viene apportata per preparare una configurazione di pianificazione semplificata in futuro e per fornire un risultato utile. Se il tempo di approvvigionamento non è incluso per la scorta di sicurezza, gli ordini pianificati creati per le scorte a disponibilità ridotta saranno sempre posticipati a causa dei tempi di consegna. Questo comportamento può causare disturbi significativi e ordini pianificati indesiderati. Come procedura consigliata cambiare l'impostazione in modo che venga usato *Data odierna + tempo di approvvigionamento*. Aggiorna i dati master per evitare avvisi. | N/D |
| Offerte di vendita | Piani generali con offerte di vendita abilitate: *\#* | Questa funzione è in sospeso. Attualmente, le offerte non sono considerate quando è abilitata l'ottimizzazione della pianificazione. Saranno ignorati, indipendentemente da questa impostazione. | Ciclo di rilascio 2 o successivo del 2022 |
| Durata a scaffale | Piani generali con durata a scaffale abilitata: *\#* | Questa funzione è in sospeso. | Ciclo di rilascio 2 del 2022 |

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sull'ottimizzazione della pianificazione](planning-optimization-overview.md)

[Introduzione a Ottimizzazione pianificazione](get-started.md)

[Differenze tra la pianificazione classica e l'ottimizzazione della pianificazione](planning-optimization-differences-with-built-in.md)

[Parametri non utilizzati da Ottimizzazione pianificazione](not-used-parameters.md)

[Visualizzare i registri di pianificazione e dello storico del piano](plan-history-logs.md)

[Applicare i filtri a un piano](plan-filters.md)

[Annullare un processo di pianificazione](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
