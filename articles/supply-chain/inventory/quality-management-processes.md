---
title: Panoramica sulla gestione di qualità e non conformità
description: Questo articolo introduce le funzionalità di gestione della qualità e della non conformità in Microsoft Dynamics 365 Supply Chain Management e spiega come possono aiutare a migliorare la qualità del prodotto nella supply chain
author: yufeihuang
ms.date: 03/23/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling, InventNonConformanceHistory, InventNonConformanceTable, InventQualityOrderLineResults, InventQualityOrderTable, InventTestCorrection, InventTestDiagnosticType, InventTestInstrument, InventTestReportSetup, InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "11574"
- intro-internal
ms.assetid: 5ac8a059-5cb4-4cb5-ba14-b944bd08dae9
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 510dee78f6fed02e6511aedad00fcb1b15195470
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907495"
---
# <a name="quality-and-nonconformance-management-overview"></a>Panoramica sulla gestione di qualità e non conformità

[!include [banner](../includes/banner.md)]

Questo articolo introduce le funzionalità di gestione della qualità e della non conformità in Microsoft Dynamics 365 Supply Chain Management e spiega come possono aiutare a migliorare la qualità del prodotto nella supply chain

Il controllo qualità prevede l'esecuzione di test sui prodotti e la gestione di materiali non conformi. I processi di gestione della qualità consentono di garantire un alto livello di qualità del prodotto nella supply chain. Questi processi consentono inoltre di ottimizzare i processi della supply chain e aumentare la soddisfazione dei clienti. La gestione della qualità può favorire la gestione dei tempi di completamento quando ci si occupa di prodotti non conformi, indipendentemente dal punto di origine dei prodotti. È possibile collegare i risultati di diagnostica alle attività di correzione. È possibile programmare le attività per correggere i problemi e quindi impedire le ricorrenze di tali problemi in futuro. La gestione della qualità consente inoltre di tenere traccia dei problemi (inclusi i problemi interni) in base al tipo di problema e consente di identificare le soluzioni relative a breve o a lungo termine. Le statistiche relative agli indicatori di prestazioni chiave (KPI) forniscono un'analisi dei problemi di non conformità che si sono precedentemente verificati e le soluzioni applicate per correggerli. È possibile utilizzare i dati storici per analizzare l'efficienza delle misure di qualità che sono state adottate in precedenza e determinare le misure appropriate in futuro.

La gestione della qualità può favorire la gestione dei tempi di completamento quando ci si occupa di prodotti non conformi, indipendentemente dal punto di origine dei prodotti. Poiché i tipi di diagnostica sono collegati alla dichiarazione di correzione, Supply Chain Management consente di programmare le attività per correggere i problemi e impedire che si ripetano.

Oltre alla funzionalità per gestire la non conformità, la gestione della qualità include la funzionalità per tenere traccia dei problemi in base al tipo (anche i problemi interni) e per l'identificazione di soluzioni a breve termine o a lungo termine. Le statistiche relative agli indicatori di prestazioni chiave (KPI) forniscono un'analisi dei problemi di non conformità che si sono precedentemente verificati e le soluzioni applicate per correggerli. È possibile utilizzare i dati storici per analizzare l'efficienza delle misure di qualità che sono state adottate in precedenza e determinare le misure appropriate in futuro.

Quando si imposta un'associazione di controllo qualità, Supply Chain Management può generare ordini di controllo qualità per diversi processi aziendali, eventi e condizioni. L'associazione di controllo qualità può coprire un articolo specifico, un determinato gruppo di articoli oppure tutti gli articoli.

## <a name="examples-of-the-use-of-quality-management"></a>Esempi di utilizzo di gestione della qualità

La gestione della qualità è flessibile e può essere implementata in vari modi per soddisfare i requisiti di livelli specifici di operazioni della catena di fornitura. Nei seguenti esempi viene illustrato i possibili usi di queste funzionalità:

- Consente di avviare automaticamente un processo di controllo qualità in base a criteri predefiniti (ad esempio, al momento della registrazione in magazzino di un ordine fornitore di un fornitore specifico).
- Consente di bloccare l'inventario durante l'ispezione per impedire che venga utilizzato un magazzino non approvato (blocco completo di quantità degli ordini acquisto).
- Utilizzare il campionamento articoli come parte di un'associazione di qualità per definire l'importo di inventario fisico corrente che deve essere controllato. Il campionamento può essere basato su quantità fisse, una percentuale o una targa completa.
- Creare ordini di controllo qualità per le entrate parziali. Per creare un ordine di controllo qualità basato sulla quantità che viene fisicamente ricevuta con un ordine, è necessario selezionare la casella di controllo **Per quantità aggiornata** nella pagina **Campionamento articoli**.
- Consente di creare i tipi di test che includono i valori di test minimi, massimi e di destinazione e di eseguire il test qualitativo-contro-quantitativo con i risultati di convalida predefiniti.
- Specificare un livello di qualità accettabile (AQL) per controllare le tolleranze di misura di qualità.
- Specificare le risorse che un'operazione di ispezione richiede, ad esempio area di test e strumenti di test.

> [!NOTE]
> La funzionalità _Gestione della qualità per i processi di magazzino_ estende le capacità di gestione della qualità. Se si utilizza questa funzionalità, vedere [Gestione qualità per i processi di magazzino](quality-management-for-warehouses-processes.md) per esempi su come funziona la gestione della qualità quando è abilitata.

## <a name="controlling-the-quality-management-process"></a>Controllo del processo di gestione della qualità

Di seguito sono indicati alcuni modi che è possibile utilizzare per controllare il processo di gestione della qualità:

- Creare ordini di controllo qualità basati su punti di attivazione quali “in entrata prodotti" per le operazioni in entrata e "in prelievo prodotti" per le operazioni in uscita.
- Documentare i risultati dei test e determinare se i risultati soddisfano i criteri di test stabiliti e i livelli di qualità accettabili.
- Utilizzare la gestione documenti per le specifiche di prodotto dettagliate e le note specifiche dell'utente come parte del report durante il processo di ispezione.
- Gestire i prodotti non conformi e correlare tali prodotti a ulteriori informazioni di non conformità per tenere traccia della causa originale di un problema.
- Documentare il costo di gestione di una non conformità. Il costo può includere gli articoli (ad esempio i pezzi di ricambio), le spese varie e le ore del foglio presenze necessarie per correggere la non conformità.
- Programmare i processi di correzione degli errori utilizzando la gestione della correzione collegata agli ordini di controllo qualità.

[![Processo di gestione qualità.](media/quality-management-process-diagram.png)](media/quality-management-process-diagram.png)

## <a name="product-testing-and-quality-orders"></a>Test sui prodotti e ordini di controllo qualità

L'insieme dei test eseguiti sui prodotti è in genere definito come controllo qualità e prevede l'utilizzo di appositi ordini. La funzionalità di controllo qualità consente di effettuare le seguenti operazioni:

- Definire i test che devono essere eseguiti sui materiali. Questi test includono le specifiche di qualità, lo strumento di test applicabile, i documenti descrittivi del test, un piano di campionamento e i livelli di qualità accettabili.
- Creare un ordine di controllo qualità in base al quale individuare i test da eseguire per uno specifico ordine, ad esempio un ordine fornitore o di produzione, oppure per una determinata quantità di scorte. È possibile creare un ordine di controllo qualità manualmente generarlo automaticamente, in base a linee guida per il controllo qualità.
- Definire le linee guida per il controllo qualità relative a ordini fornitore o cliente oppure a ordini di produzione o di quarantena nell'ambito di ogni processo aziendale in modo da poter generare automaticamente un ordine di controllo qualità che consenta di identificare i requisiti dei test per i materiali in entrata o in uscita.
- Registrare i risultati dei test in un ordine di controllo qualità, convalidare i risultati dei test in base al livello di qualità accettabile e stampare un certificato di analisi che mostra i risultati dei test.

## <a name="nonconformance"></a>Non conformità

Con non conformità si intende un articolo con un problema di qualità. Il processo di non conformità consente di creare un ordine di non conformità in cui è descritta una quantità di materiale non conforme riguardo all'origine del problema, al tipo di problema e alle note esplicative. Per semplificare l'analisi del materiale non conforme, è possibile definire una classificazione dei tipi di problemi. È inoltre possibile stampare un tag di non conformità e un report di non conformità per facilitare lo smaltimento del materiale non conforme. Ad esempio, il tag e il report possono indicare una condizione **Inutilizzabile** o **Utilizzo limitato**.

Nella tabella di seguito sono elencati i sei tipi predefiniti di non conformità e vengono descritte le informazioni che devono essere registrate per ciascun tipo.

| Tipo di non conformità | Informazioni sorgente |
|---|---|
| Cliente | Numero del conto cliente, numero dell'ordine cliente o numero di lotto di una transazione di ordini cliente. La non conformità potrebbe riferirsi ad esempio a una spedizione specifica di un ordine cliente o a suggerimenti dei clienti sulla qualità dei prodotti. |
| Richiesta di assistenza | Numero del conto cliente, numero dell'ordine cliente o numero di lotto di una transazione di ordini cliente. La non conformità potrebbe riferirsi ad esempio a una spedizione specifica di un ordine cliente o al reclamo di un cliente sulla qualità degli articoli. |
| Fornitore | Numero del conto fornitore, numero dell'ordine fornitore o numero di lotto di una transazione di ordini fornitore. La non conformità potrebbe riferirsi ad esempio al ricevimento di un ordine fornitore o ai dubbi di un fornitore riguardo a una parte fornita. |
| Produzione | Numero dell'ordine di produzione o numero di lotto di una transazione di ordini di produzione. La non conformità potrebbe riferirsi ad esempio a uno specifico batch prodotto. |
| Interno | Numero dell'ordine di controllo qualità o numero di lotto di una transazione di ordini di controllo qualità. La non conformità potrebbe riferirsi ad esempio ai test eseguiti nell'ambito di un ordine di controllo qualità o ai dubbi di un dipendente riguardo alla qualità di un prodotto. |
| Produzione co-prodotti | Una non conformità di ordini di produzione co-prodotti che è correlata agli ordini di produzione batch. |

Le non conformità sono associate a un tipo di problema. I tipi di problema vengono definiti nella pagina **Tipi di problema**, in cui si specificano i tipi di problema che possono essere associati a ciascun tipo di non conformità. I tipi di problema relativi alle non conformità di tipo **Richiesta di assistenza** potrebbero ad esempio riflettere una classificazione di reclami dei clienti, mentre i tipi di problema relativi alle non conformità di tipo **Interno** potrebbero rappresentare una classificazione di codici di articoli difettosi.

Quando si crea una nuova non conformità, selezionare il tipo di non conformità e il tipo di problema. Lo stato di approvazione iniziale, **Nuovo**, che rappresenta una richiesta di azione. Il passaggio successivo è quello di modificare lo stato di approvazione in **Approvato** o **Respinto** per segnalare la decisione di intraprendere o meno le azioni necessarie a fronte della non conformità. È inoltre possibile chiudere una non conformità (selezionando una casella di controllo separata) per segnalare che il processo è completato oppure riaprire una non conformità per segnalare la necessità di ulteriori considerazioni.

È possibile immettere commenti per una non conformità allegando un documento. È buona idea definire un tipo di documento univoco per le non conformità utilizzando la pagina **Tipo di documento**. È quindi possibile utilizzare la pagina **Impostazione report** per definire se i commenti per il tipo di documento devono essere stampati nel tag e nel report di non conformità. Il report di conformità e il tag di non conformità possono essere utili per agevolare lo smaltimento dei materiali. È possibile generare in modo selettivo i report e i tag in base ai criteri di selezione associati a una non conformità. I criteri includono il numero, l'articolo, il cliente, il fornitore e lo stato di non conformità.

Il report di non conformità visualizza il numero di non conformità, l'articolo e il tipo di problema. In base ai criteri di impostazione del report, il report può inoltre visualizzare le note correlate alla non conformità. Il tag di non conformità visualizza informazioni simili e include anche l'area di quarantena e il tipo, ad esempio **Utilizzo limitato** o **Inutilizzabile**, assegnati alla non conformità per facilitare lo smaltimento del materiale difettoso.

## <a name="approved-nonconformance"></a>Non conformità approvata

Per ciascuna non conformità approvata è possibile definire una o più operazioni correlate. Un'operazione correlata descrive il lavoro che deve essere eseguito e contiene un elenco di operazioni di controllo qualità definite e testo descrittivo sul motivo del lavoro. Dopo aver definito un'operazione, è possibile definire le spese varie, gli articoli e le ore di manodopera del foglio presenze necessarie per eseguire il lavoro. Verranno visualizzati i costi calcolati per l'operazione correlata e il totale dei costi calcolati per la non conformità. I costi calcolati e i dettagli sottostanti (relativi ad articoli, ore di manodopera e spese varie) rappresentano informazioni di riferimento, utilizzate solo nella funzione di gestione della qualità.

È inoltre possibile creare un ordine di controllo qualità a partire da una non conformità, eseguendo innanzitutto una richiesta di informazioni sugli ordini di controllo qualità e quindi creando il nuovo ordine. Un ordine di controllo qualità, ad esempio, può identificare la necessità di eseguire (o rieseguire) il test del materiale difettoso. Nell'ordine di controllo qualità appena creato viene indicato il collegamento alla non conformità da cui deriva.

Eventualmente, è possibile collegare una non conformità a un'altra e creare una nuova non conformità a partire da una non conformità esistente. Il collegamento, ad esempio, può riflettere una interconnessione tra vari problemi di qualità.

## <a name="correction-handling"></a>Gestione delle correzioni

La pagina **Correzioni** consente di creare un elenco di non conformità che devono essere corrette. Ciascun articolo di correzione è associato al tipo di diagnostica che ha generato il problema da individuare. La pagina **Correzioni** contiene inoltre informazioni sull'utente che deve eseguire le azioni correttive e quando. È possibile descrivere i dettagli del problema e l'azione correttiva necessaria allegando un documento alla correzione. Dopo l'analisi e la correzione della non conformità stata, si “chiude" l'articolo di correzione selezionando l'opzione **Completato**. È inoltre possibile indicare che la soluzione è una soluzione a breve termine.

È buona idea definire un tipo di documento univoco per correzioni utilizzando la pagina **Tipo di documento**. È quindi possibile utilizzare la pagina **Impostazione report** per definire se i commenti per il tipo di documento devono essere stampati nel report di correzione. Un report di correzione stampato visualizza le informazioni sulla non conformità e le note di non conformità correlate. Il report include inoltre le informazioni di correzione, ad esempio il tipo di diagnostica e le note di correzione correlate.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Abilitare la gestione della qualità e della non conformità](enable-quality-management.md)
- [Blocco scorte](inventory-blocking.md)
- [Ordini di quarantena](quarantine-orders.md)
- [Verificare la qualità delle merci](tasks/inspect-quality-goods.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
