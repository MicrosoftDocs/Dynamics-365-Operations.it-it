---
title: Pianificazione della produzione
description: Questo argomento descrive la pianificazione della produzione e spiega come modificare gli ordini di produzione pianificati utilizzando Ottimizzazione pianificazione.
author: ChristianRytt
ms.date: 06/01/2021
ms.topic: article
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: d0e2a730743a7921578278f23d0d2272b8e052174620c8a6c86c3e1809cdae7c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739013"
---
# <a name="production-planning"></a>Pianificazione della produzione

Ottimizzazione pianificazione supporta diversi scenari di produzione. Se si esegue la migrazione dal motore di pianificazione generale integrato esistente, è importante essere a conoscenza di alcuni comportamenti modificati.

Il video seguente offre una breve introduzione ad alcuni dei concetti discussi in questo argomento:[Dynamics 365 Supply Chain Management: miglioramenti di Ottimizzazione pianificazione](https://youtu.be/u1pcmZuZBTw).

## <a name="turn-on-this-feature-for-your-system"></a>Attivare questa funzionalità per il sistema

Se il sistema in uso non include già le funzionalità descritte in questo argomento, vedere [Gestione funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e attivare la funzionalità *Ordini di produzione pianificati per Ottimizzazione pianificazione*.

## <a name="planned-production-orders"></a>Ordini di produzione pianificati

Quando la pianificazione generale crea ordini pianificati per soddisfare i requisiti, il tipo di ordine è determinato dal valore del campo **Tipo di ordine pianificato**. Se il campo **Tipo di ordine pianificato** è impostato su *Produzione*, vengono creati gli ordini di produzione pianificati. Questi ordini di produzione pianificati includono informazioni sulla distinta base (BOM) attiva e l'ID ciclo di lavorazione dalla relativa configurazione di produzione.

## <a name="requirements-from-boms"></a>Requisiti delle distinte base

Le informazioni sulla distinta base vengono rispettate durante la pianificazione generale. L'output del piano include l'offerta di materiale per coprire la domanda di materiale correlata per la produzione.

Durante la pianificazione generale, la distinta base attiva corrente viene utilizzata per determinare i materiali necessari per la produzione. Questo passaggio viene eseguito attraverso tutti i livelli della struttura della distinta base correlata all'ordine di produzione richiesto. Il fabbisogno di materiale viene soddisfatto utilizzando le scorte disponibili, la fornitura su ordinazione esistente e gli ordini pianificati approvati. Se in un qualsiasi punto è necessario materiale aggiuntivo, viene creato un ordine pianificato per coprire la domanda.

## <a name="scheduling-during-firming"></a>Pianificazione durante la stabilizzazione

Gli ordini di produzione pianificati includono l'ID ciclo di lavorazione richiesto per la pianificazione della produzione. Tuttavia, il supporto della pianificazione durante l'esecuzione della pianificazione per gli ordini pianificati è in sospeso. L'ID ciclo di lavorazione viene utilizzato per programmare gli ordini di produzione pianificati durante la stabilizzazione. Pertanto, il lead time sugli ordini di produzione pianificati può differire dal lead time sugli ordini di produzione stabilizzati programmati correlati generati da essi, come descritto di seguito:

- **Ordine di produzione pianificato** - Il lead time si basa sul lead time statico dal prodotto rilasciato.
- **Ordine di produzione stabilizzato** - Il lead time si basa sulla pianificazione che utilizza le informazioni sul percorso e i relativi vincoli di risorse.

Per ulteriori informazioni sulla disponibilità delle funzionalità previste, vedere [Analisi di adattamento dell'ottimizzazione della pianificazione](planning-optimization-fit-analysis.md).

Se dipendi dalla funzionalità di produzione che non è ancora disponibile per Ottimizzazione pianificazione, puoi continuare a utilizzare il motore di pianificazione generale integrato. Non è richiesta alcuna eccezione.

## <a name="delays"></a>Ritardi

Se il lead time per il materiale richiesto è più lungo del periodo compreso tra la data odierna e la data del fabbisogno di materiale, l'ordine pianificato per il materiale richiesto e il relativo ordine di produzione verranno ritardati. Per gli ordini pianificati, il ritardo (in giorni) viene calcolato in base al lead time dal prodotto rilasciato. Le informazioni sul ritardo vengono quindi propagate a tutti i livelli della struttura della distinta componenti. Pertanto, è possibile seguire l'impatto del ritardo delle materie prime fino all'ordine cliente del cliente.

## <a name="modifying-planned-orders"></a>Modifica degli ordini pianificati

Quando si modificano le informazioni su un ordine pianificato, viene visualizzato il messaggio seguente: "Notare che l'impatto delle modifiche manuali sugli ordini pianificati non si rifletterà nel resto del piano fino alla successiva esecuzione della pianificazione generale".

Se desideri modificare le informazioni su un ordine pianificato e vedere l'impatto sui relativi requisiti di materiale, segui questi passaggi.

1. Aggiorna l'ordine pianificato.
2. Approva l'ordine pianificato.
3. Esegui la pianificazione generale.

Quando si esegue la pianificazione generale, non è consigliabile utilizzare filtri se sono inclusi gli ordini di produzione pianificati. Per ulteriori informazioni, vedi la sezione [Filgtri](#filters) più avanti in questo argomento.

> [!NOTE]
> Se la data di consegna dell'ordine pianificato viene modificata in una data successiva, la domanda potrebbe essere ancorata a un nuovo ordine pianificato. Questo comportamento si verifica quando la nuova data di fornitura causa un ritardo per la domanda con pegging ma, in base alle impostazioni del lead time, è possibile evitare il ritardo.

## <a name="explosion-page"></a>Pagina di esplosione

Puoi utilizzare la pagina **Esplosione** per analizzare la domanda richiesta per uno specifico ordine di produzione o ordine di produzione pianificato, la relativa copertura e le informazioni sul pegging. Le informazioni sulla pagina **Esplosione** vengono aggiornate durante la pianificazione generale. Non è possibile aggiornare le informazioni direttamente dalla pagina **Esplosione**.

## <a name="filters"></a><a name="filters"></a>Filtri

Per garantire che Ottimizzazione pianificazione disponga delle informazioni necessarie per calcolare il risultato corretto, è necessario includere tutti i prodotti che hanno una relazione con i prodotti nell'intera struttura DBA dell'ordine pianificato. Per gli scenari di pianificazione che includono la produzione, si consiglia pertanto di evitare esecuzioni di pianificazione generale filtrate.

Sebbene gli elementi figlio dipendenti vengano rilevati automaticamente e inclusi nelle esecuzioni della pianificazione generale quando viene utilizzato il motore di pianificazione generale integrato, Ottimizzazione pianificazione attualmente non esegue questa azione.

Ad esempio, se un singolo bullone dalla struttura DBA del prodotto A viene utilizzato anche per produrre il prodotto B, tutti i prodotti nella struttura DBA dei prodotti A e B devono essere inclusi nel filtro. Poiché può essere complesso garantire che tutti i prodotti facciano parte del filtro, si consiglia di evitare esecuzioni di pianificazione generale filtrate quando sono coinvolti ordini di produzione. In caso contrario, la pianificazione generale fornirà risultati indesiderati.

### <a name="reasons-to-avoid-filtered-master-planning-runs"></a>Motivi per evitare le esecuzioni di pianificazione generale filtrate

Quando si esegue la pianificazione generale filtrata per un prodotto, Ottimizzazione pianificazione (a differenza del motore di pianificazione generale integrato) non rileva tutti i sottoprodotti e le materie prime nella struttura della distinta base di quel prodotto e quindi non li include nell'esecuzione della pianificazione generale. Anche Ottimizzazione pianificazione identifica il primo livello nella struttura della distinta base del prodotto, non carica alcuna impostazione del prodotto (come il tipo di ordine predefinito o la copertura dell'articolo) dal database.

In Pianificazione ottimizzazione, i dati per l'esecuzione vengono caricati in anticipo e vengono applicati i filtri. Ciò significa che se un sottoprodotto o una materia prima inclusa in un prodotto specifico non fa parte del filtro, le informazioni su di esso non verranno acquisite per l'esecuzione. Inoltre, se il sottoprodotto o la materia prima è incluso anche in un altro prodotto, un'esecuzione filtrata che includa solo il prodotto originale e i suoi componenti eliminerebbe la domanda pianificata esistente creata per l'altro prodotto.

Questa logica può far sì che le esecuzioni di pianificazione principale filtrate producano risultati imprevisti. Le sezioni seguenti forniscono esempi che illustrano i risultati imprevisti che potrebbero verificarsi.

### <a name="example-1"></a>Esempio 1

Il prodotto finito *FG* è formato dai seguenti componenti:

- Materia prima *R*
- Sottoprodotto *S1*, composto dal sottoprodotto *S2*

Sono disponibili scorte per la materia prima *R*, mentre il sottoprodotto *S1* non è presente nell'inventario.

Quando si esegue un'esecuzione di pianificazione generale filtrata per il prodotto finito *FG*, si riceverà un ordine di produzione pianificato per il prodotto finito *FG*, un ordine di acquisto pianificato per la materia prima *R* e un ordine di acquisto pianificato per il sottoprodotto *S1*. Questo è un risultato indesiderabile perché Ottimizzazione pianificazione ha ignorato la fornitura esistente per la materia prima *R* e il sottoprodotto *S1* deve essere prodotto utilizzando *S2* anziché ordinato direttamente. Questo è successo perché Ottimizzazione pianificazione ha solo l'elenco dei componenti per il prodotto finito *FG* senza alcuna informazione correlata, come la fornitura esistente dei componenti o le impostazioni dell'ordine predefinite.

### <a name="example-2"></a>Esempio 2

Basandosi sull'esempio precedente, un ulteriore prodotto finito, *FG2*, utilizza anche il sottoprodotto *S1*. Esiste un ordine pianificato per il prodotto finito *FG2* ed esiste una domanda pianificata per tutti i suoi componenti, incluso *S1*.

Si decide di ovviare ai risultati indesiderati dell'esecuzione della pianificazione generale filtrata dall'esempio precedente aggiungendo tutti i sottoprodotti e le materie prime dalla struttura DBA del prodotto finito *FG* al filtro ed eseguendo quindi la rigenerazione completa.

Quando si esegue la rigenerazione completa, il sistema elimina tutti i risultati esistenti per tutti i prodotti inclusi e quindi ricrea i risultati in base ai nuovi calcoli. Ciò significa che la domanda pianificata esistente per il prodotto *S1* viene cancellata e poi ricreata tenendo conto solo dei requisiti del prodotto finito *FG*, mentre i requisiti del prodotto finito *FG2* vengono ignorati. Ciò accade perché quando si esegue Ottimizzazione pianificazione non viene inclusa la domanda pianificata di altri ordini di produzione pianificati: viene utilizzata solo la domanda pianificata generata durante l'esecuzione.

> [!NOTE]
> Se l'ordine pianificato esistente per il prodotto finito *FG2* è nello stato *Approvato*, verrà inclusa la domanda pianificata approvata, anche quando il prodotto padre non viene aggiunto al filtro.

Quindi, a meno che non si aggiungano tutti i componenti del prodotto finito *FG*, il prodotto finito *FG2* e tutti gli altri prodotti di cui questi componenti fanno parte (insieme ai relativi componenti), l'esecuzione della pianificazione generale filtrata fornirà risultati indesiderati.

Poiché può essere complesso garantire che tutti i prodotti facciano parte del filtro, si consiglia di evitare esecuzioni di pianificazione generale filtrate quando sono coinvolti ordini di produzione.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
