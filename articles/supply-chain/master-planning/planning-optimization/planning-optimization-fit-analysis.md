---
title: Analisi di adeguatezza dell'ottimizzazione di pianificazione
description: Questo argomento spiega come verificare la configurazione e i dati correnti rispetto alle funzionalità della funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
ms.date: 07/07/2021
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
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 308b5132056be5bc8591fdd91f6495d1811e5cd0
ms.sourcegitcommit: 73d320d2103f2b0c6ecbb2b9df746469bc544ea2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "6433696"
---
# <a name="planning-optimization-fit-analysis"></a>Analisi di adeguatezza dell'ottimizzazione di pianificazione

[!include [banner](../../includes/banner.md)]

Devi analizzare il risultato dell'analisi di adeguatezza dell'ottimizzazione di pianificazione come parte del processo di migrazione. Nota che l'ambito dell'ottimizzazione di pianificazione non è uguale alla funzionalità di pianificazione generale incorporata corrente. Ti consigliamo di collaborare con il tuo partner e di leggere la documentazione per prepararti alla migrazione. 

L'analisi di adeguatezza dell'ottimizzazione di pianificazione ti aiuta a identificare dove il risultato potrebbe differire tra il motore di pianificazione generale integrato e l'ottimizzazione di pianificazione. Questa analisi viene eseguita in base alla configurazione e ai dati correnti. 

Per vedere il risultato dell'analisi di adeguatezza dell'ottimizzazione di pianificazione, vai a **Pianificazione generale** \> **Impostazione** \> **Analisi di adeguatezza dell'ottimizzazione di pianificazione** e quindi seleziona **Esegui analisi**. Se l'analisi rileva delle incoerenze, vengono elencate nella stessa pagina. L'esecuzione dell'analisi può richiedere alcuni minuti.

> [!NOTE]
> In caso di incongruenze, sarà comunque possibile utilizzare l'ottimizzazione di pianificazione. I risultati dell'analisi di adeguatezza indicano le posizioni in cui il servizio di pianificazione non onorerà la configurazione corrente. Ciò significa che indicano le posizioni in cui i processi potrebbero essere ignorati o non essere supportati.

## <a name="analysis-results-example-1"></a>Risultati dell'analisi: Esempio 1

- **Funzionalità:** Produzione
- **Problema:** Articoli con un livello distinta base (BOM) maggiore di zero: 56
- **Spiegazione:** l'analisi di adeguatezza ha rilevato 56 articoli con l' impostazione della distinta base per la produzione. Poiché l'attuale versione di ottimizzazione di pianificazione non supporta la produzione, ottimizzazione di pianificazione genera ordini fornitore pianificati anziché ordini di produzione pianificati. Mostra anche un avviso che elenca gli articoli interessati.

## <a name="analysis-results-example-2"></a>Risultati dell'analisi: Esempio 2

- **Funzionalità:** Azioni
- **Problema:** Gruppi di copertura con calcolo delle azioni abilitato: 6
- **Descrizione:** L'analisi di adeguatezza ha rilevato sei gruppi di copertura in cui il calcolo dell'azione è abilitato. Poiché la versione corrente dell'ottimizzazione di pianificazione non supporta le azioni, non viene generata alcuna azione durante la pianificazione generale.

## <a name="overview-of-possible-results-from-the-fit-analysis"></a>Panoramica dei possibili risultati dell'analisi di adeguatezza

La tabella seguente mostra i vari risultati che possono essere mostrati dopo un'analisi di adeguatezza. Il segno di cancelletto (_\#_) verrà sostituito con un numero che indica il numero di record che presentano il problema elencato. Le funzionalità supportate o in anteprima sono disponibili con la versione 10.0.9 o successiva (a meno che un numero di versione superiore non sia elencato nella colonna "Disponibilità prevista").

| Funzionalità | Problema elencato | Spiegazione | Disponibilità prevista |
| --- | --- | --- | --- |
| Azioni | Gruppi di copertura con il calcolo delle azioni abilitato: _\#_ | Questa funzione è in sospeso. Attualmente, le azioni non vengono generate durante la pianificazione generale se è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. Lo scopo principale delle azioni è suggerire modifiche agli ordini esistenti. Valuta se le azioni vengono applicate attivamente come parte dei processi aziendali o se le informazioni sui ritardi relative agli ordini sono sufficienti. | 2022 aprile |
| Calendari di base | Calendari che utilizzano il calendario di base: _\#_ | Questa funzione è in sospeso. Attualmente, il calendario di base viene ignorato quando è abilitata l'ottimizzazione della pianificazione. Valuta se il calendario di base è necessario per i tuoi processi aziendali o se la configurazione diretta nei calendari è sufficiente. | 2022 aprile | 
| Codici smaltimento batch | Smaltimenti batch generali non nettificabili: _\#_ | Questa funzione è in sospeso. Attualmente, i codici di disposizione batch vengono ignorati quando è abilitata l'ottimizzazione della pianificazione. | Ottobre 2022 o in seguito |
| Capable-to-promise (CTP) | Impostazioni ordine predefinite con il controllo data di consegna impostato su CTP: _\#_ | Questa funzione è in sospeso. Attualmente, CTP viene ignorato quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | 2022 ottobre |
| Copia piano statico in piano dinamico | La copia del piano statico in quello dinamico è abilitata nei parametri di pianificazione generale. | L'ottimizzazione della pianificazione non copia il piano statico nel piano dinamico, indipendentemente da questa impostazione. In generale, questo concetto è meno rilevante a causa della velocità e della rigenerazione completa fornita dall'ottimizzazione della pianificazione. Se vengono utilizzati due o più piani, è necessario attivare la pianificazione generale per ciascun piano. | 2022 ottobre |
| Stabilizzazione | Gruppi di copertura con intervallo temporale di stabilizzazione automatica impostato: _\#_ | Nella versione 10.0.7 e successive, la stabilizzazione è supportata come processo di stabilizzazione batch separato al termine della pianificazione generale (a condizione che la funzionalità _Stabilizzazione automatica per l'ottimizzazione della pianificazione_ sia stata abilitata in [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Si noti che la stabilizzazione automatica per l'ottimizzazione della pianificazione si basa sulla data dell'ordine di lavoro (data di inizio) e non sulla data del fabbisogno (data di fine). Questo comportamento garantisce che la stabilizzazione degli ordini pianificati si verifichi alla scadenza, senza dover includere i tempi di consegna nel tempo di risposta. | Supportata |
| Stabilizzazione | Record di copertura articoli con stabilizzazione automatica impostata: _\#_ | Nella versione 10.0.7 e successive, la stabilizzazione automatica è supportata come processo di stabilizzazione batch separato al termine della pianificazione generale (a condizione che la funzionalità _Stabilizzazione automatica per l'ottimizzazione della pianificazione_ è stata abilitata in [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Si noti che la stabilizzazione automatica per l'ottimizzazione della pianificazione si basa sulla data dell'ordine di lavoro (data di inizio) e non sulla data del fabbisogno (data di fine). Questo comportamento garantisce che la stabilizzazione degli ordini pianificati si verifichi alla scadenza, senza dover includere i tempi di consegna nel tempo di risposta. | Supportata |
| Stabilizzazione | Piani generali con stabilizzazione automatica impostata: _\#_ | Nella versione 10.0.7 e successive, la stabilizzazione automatica è supportata come processo di stabilizzazione batch separato al termine della pianificazione generale (a condizione che la funzionalità _Stabilizzazione automatica per l'ottimizzazione della pianificazione_ è stata abilitata in [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Si noti che la stabilizzazione automatica per l'ottimizzazione della pianificazione si basa sulla data dell'ordine di lavoro (data di inizio) e non sulla data del fabbisogno (data di fine). Questo comportamento garantisce che la stabilizzazione degli ordini pianificati si verifichi alla scadenza, senza dover includere i tempi di consegna nel tempo di risposta. | Supportata |
| FitAnalysisPlanningItems | Articoli di pianificazione: _\#_ | Questa funzione è in sospeso. Attualmente, gli articoli di pianificazione vengono gestiti come gli articoli normali quando è abilitata l'ottimizzazione della pianificazione. | Ottobre 2022 o in seguito |
| Prevista | Gruppi di copertura con "Includi ordini interaziendali" abilitati: _\#_ | Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Pianificazione interaziendale](Intercompany-planning.md) | Supportata |
| Prevista | Gruppi di copertura con impostazione "Riduci previsione per" impostata su un valore diverso rispetto a "Ordini": _\#_ | Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Pianificazione generale con previsioni della domanda](demand-forecast.md) | Supportata |
| Prevista | Modelli previsionali con sottomodelli: _\#_ |  Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Pianificazione generale con previsioni della domanda](demand-forecast.md) | Supportata |
| Prevista | Piani generali con "Includi previsione offerta" abilitati: _\#_ | Questa funzione è in sospeso. Attualmente, le previsioni offerta non sono supportate quando è abilitata l'ottimizzazione della pianificazione. Saranno ignorati, indipendentemente da questa impostazione. | Ottobre 2022 o in seguito |
| Intervallo temporale blocco | Gruppi di copertura con intervallo temporale di blocco impostato: _\#_ | L'intervallo temporale di blocco non viene spesso utilizzato e al momento non è previsto di includerlo per l'ottimizzazione della pianificazione. Attualmente, l'impostazione dell'intervallo temporale di blocco viene ignorata quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | N/D |
| Intervallo temporale blocco | Record di copertura articoli con intervallo temporale di blocco impostato: _\#_ | L'intervallo temporale di blocco non viene spesso utilizzato e al momento non è previsto di includerlo per l'ottimizzazione della pianificazione. Attualmente, l'impostazione dell'intervallo temporale di blocco viene ignorata quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | N/D |
| Intervallo temporale blocco | Piani generali con intervallo temporale di blocco impostato: _\#_ | L'intervallo temporale di blocco non viene spesso utilizzato e al momento non è previsto di includerlo per l'ottimizzazione della pianificazione. Attualmente, l'impostazione dell'intervallo temporale di blocco viene ignorata quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | N/D |
| Interaziendale | Piani generali che includono la domanda downstream pianificata: _\#_ | Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Pianificazione interaziendale](Intercompany-planning.md) | Supportata |
| Kanban | Record di copertura articoli con kanban di tipo di ordine pianificato: _\#_ | Questa funzione è in sospeso. Attualmente, la copertura degli articoli impostata su kanban verrà ignorata quando è abilitata l'ottimizzazione della pianificazione. Il tipo di ordine pianificato kanban creerà un avviso durante la pianificazione generale e verranno creati ordini fornitore pianificati per coprire la domanda relativa. | Ottobre 2022 o in seguito |
| Kanban | Articoli con ordine di tipo kanban predefinito: _\#_ | Attualmente, un tipo di ordine predefinito impostato su kanban verrà ignorato quando è abilitata l'ottimizzazione della pianificazione. Il tipo di ordine predefinito kanban creerà un avviso durante la pianificazione generale e verranno creati ordini fornitore pianificati per coprire la domanda relativa. | Ottobre 2022 o in seguito |
| Stato del ciclo di vita prodotto | Stati del ciclo di vita del prodotto non attivi per la pianificazione: _\#_ | Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Escludere i prodotti con stati del ciclo di vita del prodotto specifici](product-lifecycle-state.md) | Supportata |
| Produzione | Righe DBA con arrotondamento o impostazione multipla _\#_ | Questa funzione è in sospeso. Attualmente, l'arrotondamento e le impostazioni multiple vengono ignorate sulle righe DBA quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | 2021 ottobre |
| Produzione | Righe DBA/formula con misura formula: _\#_ | Questa funzione è in sospeso. Attualmente, la misura della formula viene ignorata in DBA e nelle righe della formula quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | 2022 ottobre |
| Produzione | Righe DBA / formula con sostituzione articolo (gruppi di piani): _\#_ | Questa funzione è in sospeso. Attualmente, la sostituzione degli articoli (gruppi di pianificazione) viene ignorata in DBA e nelle righe formula quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | 2022 ottobre |
| Produzione | Righe DBA/formula con quantità negativa: _\#_ | Questa funzione è in sospeso. Le DBA e le righe formula con una quantità negativa verranno incluse con una quantità pari a 0 (zero) e verrà emesso un avviso quando l'ottimizzazione della pianificazione è abilitata. Aggiorna i dati master per evitare avvisi. | 2022 ottobre |
| Produzione | Righe DBA/formula con consumo risorse: _\#_ | Questa funzione è in sospeso. Attualmente, le DBA e righe formula con consumo di risorse sono ignorate quando è abilitata l'ottimizzazione della pianificazione. Quando questa funzionalità è supportata, il fabbisogno di materiale verrà impostato sulla data di inizio della produzione. Fino a quando questa funzionalità non sarà supportata, i requisiti non verranno generati per i materiali contrassegnati con un flag di consumo di risorse. | 2022 ottobre |
| Produzione | Righe DBA/formula con consumo per fasi: _\#_ | Questa funzione è in sospeso. Attualmente, le DBA e righe formula con consumo per fasi sono ignorate quando è abilitata l'ottimizzazione della pianificazione. | 2022 ottobre |
| Produzione | DBA con scarto costante o variabile definito: _\#_ | Questa funzione è in sospeso. Attualmente, gli scarti costanti e gli scarti variabili definiti in DBA vengono ignorati quando è abilitata l'ottimizzazione della pianificazione. | 2022 ottobre |
| Produzione | DBA con conto lavoro: _\#_ | Questa funzione è in sospeso. Attualmente, le DBA con conto di lavoro vengono ignorate quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | 2022 aprile |
| Produzione | DBA senza un sito: _\#_ | Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Pianificazione della produzione](production-planning.md) | Supportata |
| Produzione | Richiesta con distinta DBA specifica o requisiti di percorso definiti: _\#_ | Questa funzione è in sospeso. Attualmente, i requisiti delle DBA o dei percorsi specifici definiti sulla domanda (come una distinta base secondaria o un ciclo di lavorazione secondario su un ordine cliente) vengono ignorati quando è abilitata l'ottimizzazione della pianificazione. Verrà utilizzata la distinta base o il ciclo di lavorazione standard, indipendentemente da questa impostazione. | 2022 ottobre |
| Produzione | Versioni formula con sotto/co-prodotti: _\#_ | Questa funzione è in sospeso. Attualmente, i coprodotti e i sottoprodotti associati alla versione della formula vengono ignorati quando è abilitata l'ottimizzazione della pianificazione. | 2022 ottobre |
| Produzione | Versioni formula con rendimento: _\#_ | Questa funzione è in sospeso. Attualmente, il rendimento associato alla versione della formula viene ignorato quando è abilitata l'ottimizzazione della pianificazione. | 2022 ottobre |
| Produzione | Piani che includono la sequenza: _\#_ | Questa funzione è in sospeso. Attualmente, la sequenza viene ignorata quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | 2022 ottobre |
| Produzione | Ordini di produzione rilasciati non ancora avviati, il cui avvio programmato è precedente alla data odierna: _\#_ | Questa funzione è in sospeso. Attualmente, se un ordine di produzione viene ritardato, la pianificazione generale presumerà che sarà completato oggi. Ciò è rilevante per gli ordini di produzione rilasciati in cui una data di consegna è nel passato, ma non è stata ancora completata. | 2022 ottobre |
| Produzione | Risorse programmate con capacità limitata: _\#_ | Questa funzione è in sospeso. Attualmente, le risorse programmate con capacità limitata vengono ignorate quando è abilitata l'ottimizzazione della pianificazione. La programmazione viene eseguita in base al tempo di consegna predefinito dal prodotto. | 2022 ottobre |
| Produzione | Cicli di lavorazione utilizzati nella pianificazione: _\#_ | Questa funzione è in sospeso. Attualmente, i cicli di lavorazione vengono ignorati quando è abilitata l'ottimizzazione della pianificazione. Viene utilizzato il lead time predefinito dal prodotto. | Anteprima: supportato (10.0.20), GA: ottobre 2021 |
| Produzione | Prenotazione riga vendite mediante esplosione: _\#_ | La prenotazione della riga di vendita che utilizza l'esplosione non è supportata quando l'ottimizzazione della pianificazione è abilitata. | 2022 ottobre |
| Produzione | Programmazione con esplosione degli ordini di produzione: _\#_ | La programmazione che utilizza l'esplosione degli ordini di produzione non è supportata quando l'ottimizzazione della pianificazione è abilitata. Gli ordini di produzione possono essere programmati singolarmente. | 2022 ottobre |
| Richieste di offerta | Piani generali con richieste di offerte abilitate: _\#_ | Questa funzione è in sospeso. Al momento, le richieste di offerta (RdO) non sono considerate richieste quando è abilitata l'ottimizzazione della pianificazione. Saranno ignorati, indipendentemente da questa impostazione. | 2022 ottobre |
| Richieste | Piani generali con richieste abilitate: _\#_ | Questa funzionalità è ora supportata. Per ulteriori informazioni, vedi [Richieste di acquisto](purchase-requisitions.md) | Supportata |
| Margini di sicurezza | Gruppi di copertura con margine di sicurezza: _\#_ | Questa funzionalità è ora parzialmente supportata. Per ulteriori informazioni, vedi [Margini di sicurezza](safety-margins.md) | Margine di ricevimento: supportato. Margine di riordino e margine di emissione: gennaio 2022 |
| Margini di sicurezza | Piani generali con margine di sicurezza: _\#_ | Questa funzionalità è ora parzialmente supportata. Per ulteriori informazioni, vedi [Margini di sicurezza](safety-margins.md) | Margine di ricevimento: supportato. Margine di riordino e margine di emissione: gennaio 2022 |
| Garanzia scorte di sicurezza | Record di copertura articoli con "Soddisfa minimo" diverso da "Data odierna + tempo di approvvigionamento": _\#_ | L'ottimizzazione della pianificazione utilizza sempre *Data odierna + tempo di approvvigionamento*. Questa modifica viene apportata per preparare una configurazione di pianificazione semplificata in futuro e per fornire un risultato utile. Se il tempo di approvvigionamento non è incluso per la scorta di sicurezza, gli ordini pianificati creati per le scorte a disponibilità ridotta saranno sempre posticipati a causa dei tempi di consegna. Questo comportamento può causare disturbi significativi e ordini pianificati indesiderati. Come procedura consigliata cambiare l'impostazione in modo che venga usato *Data odierna + tempo di approvvigionamento*. Aggiorna i dati master per evitare avvisi. | N/D |
| Offerte di vendita | Piani generali con offerte di vendita abilitate: _\#_ | Questa funzione è in sospeso. Attualmente, le offerte non sono considerate quando è abilitata l'ottimizzazione della pianificazione. Saranno ignorati, indipendentemente da questa impostazione. | Ottobre 2022 o in seguito |
| Durata a scaffale | Piani generali con durata a scaffale abilitata: _\#_ | Questa funzione è in sospeso. Attualmente, la durata a scaffale non viene considerata quando è abilitata l'ottimizzazione della pianificazione, indipendentemente da questa impostazione. | 2022 aprile |

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sull'ottimizzazione della pianificazione](planning-optimization-overview.md)

[Introduzione all'ottimizzazione della pianificazione](get-started.md)

[Visualizzare la cronologia del piano e i log di pianificazione](plan-history-logs.md)

[Applicare i filtri a un piano](plan-filters.md)

[Annullare un processo di pianificazione](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
