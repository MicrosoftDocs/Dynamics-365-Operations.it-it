---
title: Impostazione guidata della pianificazione generale (video)
description: In questo articolo viene descritto come eseguire l'impostazione guidata della pianificazione generale per configurare la pianificazione generale.
author: t-benebo
ms.date: 10/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: a53dfd02ac2f42fd680eb71509dbd41214160f19
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066020"
---
# <a name="master-planning-setup-wizard"></a>Impostazione guidata della pianificazione generale

[!include [banner](../includes/banner.md)]

Questo articolo fornisce una guida per la **Impostazione guidata della pianificazione generale**. Descrive come suggerimenti dei parametri vengono calcolati e fornisce inoltre alcuni esempi che mostrano come diverse società configurano la pianificazione generale, in base alle esigenze aziendali.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3YnSB]

Il video relativo all'[impostazione guidata della pianificazione generale in Dynamics 365 Supply Chain Management](https://youtu.be/c-e6n-8rZb4) (mostrato sopra) è incluso nella [playlist delle app per la finanza e le operazioni](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponibile in YouTube.


## <a name="specific-requirements-of-your-company"></a>Requisiti specifici della società

La prima pagina della procedura guidata chiede dei requisiti specifici della società. Le risposte a queste domande non devono essere esatte, ma dovrebbe essere possibile fornire un'approssimazione del numero di articoli e degli ordini pianificati che ci saranno per la persona giuridica. Le risposte verranno utilizzate per configurare i parametri che vengono applicati alla persona giuridica, non solo al piano generale selezionato. Nelle seguenti sezioni vengono descritti i parametri che vengono calcolati e le formule utilizzate.

### <a name="number-of-threads"></a>Numero di thread

- **Se si produce qualcuno degli articoli:** Numero di thread = Numero di ordini pianificati ÷ 1.000
- **Se non si producono gli articoli:** Numero di thread = Numero di articoli ÷ 1.000

Se il numero di thread calcolato supera il 75% del numero di thread disponibile, viene limitato al 75% del numero di thread disponibile per ogni cliente. Il numero di thread disponibili verrà determinato per ogni cliente.

Per ulteriori informazioni, vedere [Numero di thread](/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-threads).

### <a name="bundle-size"></a>Dimensioni aggregazione

Le dimensioni di aggregazione verranno impostate su **1**. Questo valore è spesso il migliore valore, poiché consente di migliorare le prestazioni della pianificazione generale.

Per ulteriori informazioni, vedere [Numero di attività nell'aggregazione helper](/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-tasks-in-helper-task-bundle).

### <a name="firming-bundle-size"></a>Dimensioni aggregazione di stabilizzazione

- **Se si produce qualcuno degli articoli:** Le dimensioni di aggregazione di stabilizzazione verranno impostato sul valore maggiore tra di questi due valori: **10** e il calcolo di aggregazione
- **Se non si producono gli articoli:** Le dimensioni di aggregazione di stabilizzazione verranno impostato sul valore maggiore tra questi due valori: **50** e il calcolo di aggregazione

Calcolo di aggregazione = (numero degli ordini pianificati × (Intervallo temporale di stabilizzazione ÷ Intervallo temporale di copertura) ÷ Numero di thread) ÷ 10

### <a name="cache-size"></a>Dimensioni cache

Le dimensioni della cache verranno impostate su **Massimo**. Questo valore è spesso il migliore valore, poiché consente di migliorare le prestazioni della pianificazione generale.

Per ulteriori informazioni, vedere [Allocare tempo ai processi in un'aggregazione di processi](/dynamics365/unified-operations/supply-chain/production-control/allocate-time-jobs-job-bundle).

### <a name="manufacturing-setup"></a>Impostazione della produzione

Se si producono articoli, una pagina **Impostazione della produzione** sarà visualizzata successivamente nella procedura guidata.

## <a name="scope-of-the-current-plan"></a>Ambito del piano corrente

Nella pagina **Ambito del piano corrente** della procedura guidata, si risponde a domande correlate a quanto avanti nel futuro i vari fabbisogni verranno considerati e calcolati nella Pianificazione generale. Ciascuna domanda chiede se si desidera utilizzare una funzionalità e la modalità di configurazione.

Ad esempio, per la funzionalità di piano previsionale, la procedura guidata chiede se si desidera usare un piano previsionale in Pianificazione generale in modo che gli ordini pianificati vengano suggeriti per soddisfare la domanda prevista.

Sono disponibili le opzioni seguenti:

- **No** - La pianificazione generale non suggerirà gli ordini pianificati per soddisfare una previsione. Nella scheda **Intervalli temporali** della pagina **Piani generali** (**Pianificazione generale \> Impostazione \> Piani \> Piani generali**), la procedura guidata imposterà l'opzione **Intervallo temporale di piano previsionale** su **Sì** e il numero di giorni su **0** (zero). Questa impostazione sostituirà l'intervallo temporale specificato nel gruppo di copertura. Poiché il numero di giorni è  **0** (zero), la funzionalità non verrà utilizzata.
- **Sì, come definito nel piano generale** - Un campo diventa disponibile, in cui è possibile immettere il numero di giorni che la pianificazione generale suggerirà gli ordini pianificati per soddisfare la domanda prevista. La procedura guidata imposterà l'opzione **Intervallo temporale di piano previsionale** su **Sì** e il numero di giorni sul numero di giorni immesso nel campo **Piano previsionale** della scheda **Intervalli temporali** della pagina **Piani generali**. Questa impostazione sovrascriverà i valori impostati nei gruppi di copertura.
- **Sì, come definito nella copertura** - La procedura guidata imposterà l'opzione **Intervallo temporale di piano previsionale** su **No**. Gli intervalli temporali specificati nel gruppo di copertura verranno utilizzati per specificare il periodo di pianificazione per la previsione.

Le domande rimanenti in questa pagina e le relative risposte seguono lo stesso schema:

- **No** - L'opzione **Intervallo temporale di piano previsionale** è impostata su **Sì** e il numero di giorni su **0** (zero).
- **Sì, come definito nel piano generale** - L'opzione **Intervallo temporale di piano previsionale** verrà impostata su **Sì**. Numero di giorni immesso verrà utilizzato e sovrascriverà i valori impostati nei gruppi di copertura.
- **Sì, come definito nel gruppo di copertura** - L'opzione **Intervallo temporale di piano previsionale** verrà impostata su **No**.

Per ulteriori informazioni, vedere [Programmazione processo](/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="scheduling-options"></a>Opzioni di programmazione

La pagina **Opzioni di programmazione** appare solo se si è risposto **Sì** alla domanda se si produce qualcuno degli articoli pianificati nella prima pagina della procedura guidata.

La risposta alla prima domanda di questa pagina ("È necessario programmare operazioni suddivise in singoli processi?") determina il metodo di programmazione nella scheda **Generale** della pagina **Piani generali**.

- **Sì** - La programmazione dei processi verrà utilizzata.
- **No** - La programmazione delle operazioni verrà utilizzata.

Per ulteriori informazioni, vedere [Programmazione operazioni](/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling) e [Programmazione processo](/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="updates-of-demand-and-supply"></a>Aggiornamenti di domanda e offerta

Le domande nella pagina **Aggiornamenti di domanda e offerta** sono correlate alla stabilizzazione, i messaggi d'azione e ai ritardi.

L'impostazione di pianificazione generale verrà aggiornata in base alle risposte, in base allo stesso schema che viene descritto nella sezione precedente:

- **No** - L'opzione **Intervallo temporale** nella pagina **Piani generali** verrà impostata su **Sì** e il numero di giorni su **0** (zero).
- **Sì, come definito nel piano generale** - L'opzione **Intervallo temporale** verrà impostata su **Sì**. Numero di giorni immesso verrà utilizzato e sovrascriverà i valori impostati nei gruppi di copertura.
- **Sì, come definito nel gruppo di copertura** - L'opzione **Intervallo temporale** verrà impostata su **No**.

Per i ritardi calcolati, le risposte alle domande della procedura guidata aggiorneranno i parametri corrispondenti nella scheda **Ritardi calcolati** della pagina **Piani generali**.

## <a name="summary-of-your-changes"></a>Riepilogo delle modifiche

Ultima pagina della procedura guidata mostra le modifiche consigliate in base alle risposte. Mostra sia il valore nell'impostazione attuale (**Impostazione corrente**) che il valore consigliato dalla procedura guidata si (**Nuova configurazione**).

È inoltre possibile modificare i parametri nella nuova configurazione. I parametri sono separati in parametri che vengono applicati alla persona giuridica e parametri che vengono applicati solo al piano generale selezionato. Per visualizzare tutti i parametri di impostazione che possono essere modificati utilizzando la procedura guidata, selezionare **Mostra tutti i parametri** nell'area inferiore. È quindi possibile modificare i parametri.

Infine, quando si seleziona **Fine**, la nuova configurazione viene applicata. Se si seleziona **Annulla**, nessuna delle modifiche vengono applicate.

## <a name="examples"></a>Esempi

In questa sezione viene descritta l'impostazione di due società fittizie per mostrare come impostazione può variare in base alle esigenze di ciascuna azienda.

### <a name="example-1-contoso-manufacturer"></a>Esempio 1: Contoso Manufacturer

Contoso Manufacturer è una società che produce altoparlanti. Acquista le varie materie prime e componenti che verranno utilizzate per gli altoparlanti finiti da diversi fornitori. Di seguito sono alcune caratteristiche della fornitura e produzione:

- Gli articoli finiti che la società produce hanno una struttura di distinte base (DBA).
- Tutti gli articoli finiti e i componenti vengono pianificati nella pianificazione generale. La pianificazione manuale non viene applicata.
- Un ciclo di operazioni viene definito per la produzione di ciascun articolo finito.
- L'impianto di produzione produce gli articoli finiti. Ha un numero definito di macchine per la fresatura e la perforazione utilizzate per elaborare i componenti. I vari componenti devono essere elaborate da questi macchine.
- Sono presenti molti fornitori. Il lead time medio degli articoli corrisponde a una settimana. Un gruppo di articoli dello stesso fornitore avrà un lead time di sette settimane.

Nella procedura guidata, i seguenti valori vengono immessi per Contoso Manufacturer:

- **Copertura:**

    - **Domanda:** "Si desidera specificare il numero di giorni dell'orizzonte di pianificazione"?
    - **Risposta:** "Sì, come definito nei gruppi di copertura."

    Poiché il lead time per gli articoli è molto diverso, Contoso non deve pianificare tutti gli articoli per lo stesso periodo futuro. I gruppi di copertura per gli articoli vengono creati. Gli articoli con un lead time simile vengono allocati allo stesso gruppo di copertura. L'orizzonte di pianificazione per ciascun gruppo di copertura (ovvero l'intervallo temporale di copertura) corrisponde approssimativamente al lead time più un margine di una settimana. La pianificazione generale quindi assicura che gli articoli siano pianificati in anticipo, in base al lead time.

    Di conseguenza, due gruppi di copertura verranno creati per questo esempio. Un gruppo di copertura avrà un intervallo temporale di due settimane e l'altro avrà un intervallo temporale di otto settimane.

    Se si seleziona **Sì, come definito nel piano generale** come risposta, il numero di giorni immesso deve superare il lead time massimo di tutti gli articoli. Tuttavia, poiché molti articoli non devono essere pianificati con tanto anticipo, numerosi ordini pianificati verranno calcolati ma mai utilizzati. Di conseguenza, il runtime della pianificazione generale aumenterà.

- **Programmazione:**

    - **Domanda:** "È necessario programmare operazioni suddivise in singoli processi"?
    - **Risposta:** "Sì".

    Contoso Manufacturing deve pianificare e programmare singoli processi che verranno eseguiti nello shop floor. Di conseguenza, utilizzerà la programmazione processi.

- **Capacità:**

    - **Domanda:** "Si desidera eseguire la programmazione usando la capacità delle risorse"?
    - **Risposta:** "Sì, come definito nel piano generale". **10 giorni** viene immesso.

    Il numero di macchina per la fresatura e la perforazione è limitato. La pianificazione della produzione deve tenere conto di questa limitazione e organizzare i processi in tempo in base alla capacità delle risorse. Ovvero i processi programmati verranno ripianificati in base alle limitazioni delle risorse. La pianificazione userà il lead time in aggiunta al periodo definito. (Ordini di produzione pianificati possono sovrapporsi.) Poiché il lead time di produzione per gli articoli è di sette giorni, la capacità delle risorse per la pianificazione generale verrà presa in considerazione per 10 giorni.

- **Sequenziamento:**

    - **Domanda:** "Si desidera ordinare gli ordini pianificati utilizzando i valori della sequenza dei prodotti"?
    - **Risposta:** "Sì, come definito nei gruppi di copertura."

    Un ciclo di lavorazione viene definito per la produzione di ciascun articolo finito. Di conseguenza, la pianificazione generale programmerà gli ordini in tempo in base ai cicli di lavorazione definiti.

- **Esplosione:**

    - **Domanda:** "Si desidera pianificare gli ordini per tutti gli elementi in una distinta base (pianificare per l'articolo padre e tutti gli articoli figlio")?
    - **Risposta:** "Sì, come definito nei gruppi di copertura."

    Tutti gli articoli utilizzati per la produzione devono essere pianificati. Poiché gli articoli hanno lead time molto diversi, la pianificazione generale avrà prestazioni migliori quando vengono utilizzati i gruppi di copertura. Anche in questo caso, un margine di una settimana può essere inserito e l'esplosione può essere effettuata per lo stesso tempo come copertura.

### <a name="example-2-contoso-retailer"></a>Esempio 2: Contoso Retailer

Contoso Retailer è una società di distribuzione nel settore della moda. Utilizza la pianificazione generale per calcolare quando gli ordini fornitore devono essere effettuati, in base alle vendite previste. Ecco alcune delle sue caratteristiche:

- Contoso Retailer utilizza una previsione della domanda per prevedere le vendite. Gli ordini fornitore verranno pianificati in base alla previsione.
- I punti vendita usano richieste di rifornimento.
- Il lead time dal magazzino principale a ogni punto vendita è di due settimane circa per tutti gli articoli.

Nella procedura guidata, i seguenti valori vengono immessi per Contoso Retailer:

- **Previsione della domanda:**

    - **Domanda:** "Si desidera utilizzare un piano previsionale nella pianificazione generale in modo che gli ordini pianificati vengano suggeriti per soddisfare la domanda prevista"?
    - **Risposta:** "Sì, come definito nel piano generale".

    Contoso ha incluso una previsione della domanda per prevedere le vendite. Di conseguenza, la pianificazione generale deve consigliare gli ordini pianificati per soddisfare la previsione.

- **Stabilizzazione:**

    - **Domanda:** "Si desidera che la pianificazione generale automaticamente stabilizzi gli ordini pianificati in documenti di ordine, ad esempio ordini di produzione o ordini fornitore"?
    - **Risposta:** "Sì, come definito nel piano generale". **1 giorno** viene immesso.

    Poiché Contoso Retailer creerà ordini fornitore direttamente da ordini fornitore pianificati, è utile se gli ordini fornitore pianificati vengono stabilizzati automaticamente. Poiché la società esegue la pianificazione generale ogni giorno, un intervallo temporale di stabilizzazione di un giorno stabilizzerà automaticamente tutti gli ordini necessari per il giorno successivo.

- **Richieste approvate:**

    - **Domanda:** "Si desidera includere la domanda dalle richieste approvate per rifornire i punti vendita al dettaglio"?
    - **Risposta:** "Sì, come definito nel piano generale". **1 giorno** viene immesso.

    Contoso utilizza le richieste approvate dei punti vendita per creare ordini fornitore pianificati per rifornire questi punti vendita. Poiché la pianificazione generale viene eseguita ogni giorno, le richieste dall'ultimo giorno verranno incluse nella programmazione.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
