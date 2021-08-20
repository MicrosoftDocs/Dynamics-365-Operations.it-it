---
title: Calcoli BOM
description: I calcoli relativi al rollup dei costi e ai prezzi di vendita sono chiamati calcoli DBA o calcoli della distinta base (DBA) perché è possibile avviarli dalla pagina Calcoli. Vengono fornite le informazioni sui calcoli BOM.
author: AndersGirke
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion, InventItemPrice, ProdSetupCostEstimation
audience: Application User
ms.reviewer: kamaybac
ms.custom: 273763
ms.assetid: c6fa3348-eafa-4847-9132-e65c5f55cbf4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: b4c79115dbe3a38cf4e772f9025f52bbf3b5b350bea4d55dd32e9ad6b01d2cfd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779640"
---
# <a name="bom-calculations"></a>Calcoli BOM

[!include [banner](../includes/banner.md)]

I calcoli relativi al rollup dei costi e ai prezzi di vendita sono chiamati calcoli DBA o calcoli della distinta base (DBA) perché è possibile avviarli dalla pagina Calcoli. Vengono fornite le informazioni sui calcoli BOM.

I calcoli relativi al rollup dei costi e ai prezzi di vendita sono chiamati calcoli DBA o calcoli della distinta base (DBA) perché è possibile avviarli dalla pagina **Calcoli**. Usare la pagina **Calcoli** per eseguire le seguenti attività:

-   Calcolare il costo di un articolo prodotto e generare un apposito record associato all'interno di una versione di determinazione costi.
-   Calcolare il prezzo di vendita di un articolo prodotto e generare un apposito record associato all'interno di una versione di determinazione costi.

La modalità di utilizzo della pagina **Calcoli** varia leggermente in base alla modalità di avvio dei calcoli DBA. La modalità di utilizzo della pagina **Calcoli** dipendono anche dal fatto che tali calcoli interessino una versione di determinazione costi per costi standard o pianificati e a numerosi criteri definiti all'interno della versione di determinazione costi in uso nei calcoli DBA. **Nota**: una variante della pagina **Calcoli** viene utilizzata nel contesto di una voce di un ordine cliente, di un'offerta di vendita o di un ordine di assistenza. Questi calcoli sono noti come calcoli specifici della DBA. Un calcolo DBA specifico di un ordine non genera un record di costo in una versione di determinazione costi. Genera invece un record di calcolo che viene visualizzato nella pagina **Dettagli calcolo DBA**. Nel record di calcolo sono inclusi un costo calcolato e un prezzo di vendita calcolato. La pagina **Calcoli** può essere aperta per un singolo articolo prodotto o per una versione di determinazione costi.

-   Per calcolare i costi per un singolo articolo prodotto, avviare i calcoli DBA dalla pagina **Prezzo articolo**. La pagina **Calcoli** deriverà l'identificatore dell'articolo. Devono essere specificati la versione di determinazione costi, la versione DBA, la versione del ciclo di lavorazione, la quantità di calcolo, la data di calcolo e il sito.
    -   Per impostazione predefinita, la versione DBA e la versione del ciclo di lavorazione sono impostate sulle versioni attive per l'articolo, il sito, la data e la quantità di calcolo. Tuttavia, è possibile sostituire i valori predefiniti con le versioni approvate.
    -   Per impostazione predefinita, la quantità di calcolo è impostata sulle quantità ordine standard dell'articolo. Tuttavia, è possibile sostituire il valore predefinito.
    -   La data di calcolo o il sito può dipendere dalla versione di determinazione costi oppure, in caso non siano definiti nella versione, è possibile utilizzare valori specificati dall'utente. Una data di calcolo futura determina le modalità di utilizzo di record di costo in sospeso. Per i calcoli DBA utilizza un record di questo tipo con la data 'Dal' più prossima lo stesso giorno o prima della data di calcolo.
-   Per calcolare i costi di tutti gli articoli prodotti o articoli selezionati o per aggiornare gli articoli in base dove-usato, è possibile avviare i calcoli DBA dalla pagina **Impostazione versione di determinazione costi** o **Gestione versione di determinazione costi**. La pagina **Calcoli** deriverà l'identificatore la versione di determinazione costi.
    -   Per i calcoli si presuppone l'utilizzo della versione della DBA e della versione del ciclo di lavorazione attive per un articolo prodotto, con il sito, la data e la quantità correlati, a meno che per un componente prodotto non si sia provveduto a specificare una DBA secondaria o un ciclo di lavorazione secondario.
    -   Per i calcoli, si presuppone l'utilizzo della quantità ordine standard per gli articoli prodotti. La quantità ordine standard costituisce la base per calcolare le quantità dei componenti, per determinare le versioni di DBA e cicli di lavorazione pertinenti (quando si applicano DBA e cicli di lavorazione che variano secondo la quantità) e per ammortizzare i costi costanti. Tale presupposto non è valido quando per un componente prodotto presenta una riga DBA è di tipo **Produzione** o **Fornitore** oppure quando si utilizza la modalità di esplosione Produzione su ordine per i calcoli DBA, dal momento che le quantità rifletteranno la quantità di calcolo specificata.
    -   La data di calcolo o il sito può dipendere dalla versione di determinazione costi oppure, in caso non siano definiti nella versione, è possibile utilizzare valori specificati dall'utente.

Altre differenze nei calcoli DBA riflettono il tipo di determinazione costi e le restrizioni della versione di determinazione costi:

-   I calcoli DBA che utilizzano costi standard devono essere limitati da criteri relativi alla versione di determinazione costi perché queste restrizioni garantiscono il rispetto dei principi di determinazione dei costi. Secondo tali principi, sono richieste l'applicazione di restrizioni sull'utilizzo dei costi standard per gli articoli acquistati, la modalità di esplosione a livello singolo e l'inclusione delle spese varie nei costi unitari.
-   Per i calcoli DBA che utilizzano costi pianificati non è necessario rispettare i principi di determinazione dei costi standard. In tali calcoli DBA è pertanto possibile utilizzare modalità di esplosione diverse e origini dei dati di costo alternative per gli articoli acquistati, nonché applicare facoltativamente restrizioni all'interno della versione di determinazione costi.

### <a name="bom-calculations-that-use-standard-costs"></a>Calcoli DBA che utilizzano costi standard

I criteri all'interno della versione di determinazione costi (per i costi standard) possono definire l'applicazione di cinque criteri di calcolo DBA. L'opzione **Restrizione registrazione** all'interno della versione di determinazione costi dipende uno di questi criteri, ovvero l'obbligo di includere le spese varie nel prezzo unitario. Le spese varie per gli articoli acquistati possono essere immesse manualmente, mentre gli articoli prodotti riflettono l'ammortamento calcolato dei costi costanti. L'opzione relativa alla **restrizione calcolo** all'interno della versione di determinazione costi dipendono invece gli altri quattro criteri di calcolo DBA:

-   L'origine dei contributi costi per gli articoli acquistati deve essere basata sui costi standard. In altri termini, per i calcoli DBA devono essere utilizzati i record di costo articolo all'interno della versione di determinazione costi specificata o del fallback contenente i costi standard.
-   Per garantire un calcolo accurato e coerente dei costi standard, la modalità di esplosione deve essere a livello singolo.
-   Per ottenere risultati coerenti nel calcolo del prezzo di vendita dell'articolo, l'impostazione di profitto deve essere definita. L'impostazione di profitto può essere utilizzata e i record di prezzo di vendita degli articoli possono essere generati solo se nella versione di determinazione costi sia consentito il contenuto dei prezzi di vendita.
-   Il principio di fallback deve essere definito e può essere impostato su **Nessuno**, **Attivo** per record di costo attivi o su **Versione determinazione costi** per una particolare versione di determinazione costi.

### <a name="bom-calculations-that-use-planned-costs"></a>Calcoli DBA che utilizzano costi pianificati

I criteri all'interno della versione di determinazione costi (per i costi pianificati) possono facoltativamente definire l'applicazione di cinque criteri di calcolo DBA. In alternativa, possono fornire semplicemente valori predefiniti. L'opzione **Restrizione registrazione** nella versione di determinazione costi dipende il fatto che il criterio di calcolo DBA sulle spese varie debba essere definito o utilizzato come valore predefinito. Le spese varie possono essere facoltativamente incluse nel prezzo unitario. L'opzione relativa alla **restrizione calcolo** nella versione di determinazione costi dipende invece il fatto che gli altri quattro criteri di calcolo DBA debbano essere definiti o utilizzati come valori predefiniti.

-   L'origine dei contributi costi di un articolo acquistato può corrispondere ai record di costo articolo all'interno di una versione di determinazione costi. oppure può essere definita dal gruppo di calcolo DBA assegnato all'articolo. Tale gruppo ad esempio può definire gli accordi commerciali sui prezzi di acquisto come origine dei dati sui contributi costi.
-   La modalità di esplosione può essere a livello singolo, multilivello, Produzione su ordine o può essere basata sulla voce DBA. La modalità di esplosione per il tipo di riga DBA replica la logica di calcolo dei costi per le stime degli ordini di produzione.
-   L'impostazione di profitto può essere definita o può essere un valore predefinito. L'impostazione di profitto può essere utilizzata e i record di prezzo di vendita degli articoli possono essere generati solo se nella versione di determinazione costi sia consentito il contenuto dei prezzi di vendita.
-   Il principio di fallback può essere definito o essere un valore predefinito. Il principio di fallback può essere impostato su **Nessuno**, **Attivo** per record di costo attivi o su **Versione determinazione costi** per una particolare versione di determinazione costi.

A seguito dei calcoli DBA, vengono generati messaggi di avviso e di altro tipo. I tipi di messaggi sono determinati da diversi criteri di calcolo DBA. Le condizioni di avviso applicabili definite nel gruppo di calcolo DBA assegnato agli articoli. Tuttavia, questi avvisi possono essere sovrascritti quando si avvia un calcolo DBA. Quando si applica il principio di fallback, spesso è utile visualizzare le relative informazioni come messaggi di informazioni. Quando si tenta di aggiornare i costi calcolati per articoli con record di costo mancanti, è utile anche identificare gli articoli non aggiornati come messaggi di informazioni.

## <a name="bom-calculations-that-use-the-fallback-principle"></a>Calcoli DBA basati sul principio di fallback
Nelle seguenti situazioni vengono illustrati due utilizzi di tale principio:

-   **Approccio basato su due versioni per gli aggiornamenti dei costi standard**: una versione di determinazione costi può contenere le modifiche incrementali relative ai costi standard, ad esempio record dei costi in sospeso che rappresentano nuovi articoli o modifiche costo. In tal caso, il principio di fallback può identificare l'utilizzo dei costi standard attivi contenuti in altre versioni di determinazione costi.
-   **Simulazione dell'effetto delle modifiche costo con costi pianificati**: una versione di determinazione costi per costi pianificati può contenere modifiche incrementali a scopo di simulazione. In questa versione di determinazione costi verranno inclusi record dei costi in sospeso che rappresentano le modifiche costo simulate per articoli, categorie di costi e formule di calcolo per i costi indiretti. In tal caso, il principio di fallback può identificare l'utilizzo dei costi standard attivi contenuti in altre versioni di determinazione costi.

## <a name="bom-calculation-of-a-suggested-sales-price"></a>Calcolo DBA di un prezzo di vendita suggerito
Quando si utilizza questo tipo di approccio, il prezzo di vendita calcolato per un articolo riflette l'insieme di percentuali di impostazione del profitto specificato per il calcolo DBA e i costi associati agli articoli componente, alle operazioni di cicli di lavorazione e ai costi generali di produzione applicabili. Il ricarico riflette le percentuali di impostazione del profitto assegnate a gruppi di costi e i gruppi di costi assegnati agli articoli, le categorie di costi per le operazioni dei cicli di lavorazione e le formule di calcolo dei costi indiretti per i costi generali di produzione. Gli insiemi di percentuali di impostazione del profitto sono denominati **Standard**, **Profitto 1**, **Profitto 2** e **Profitto 3**. Nell'insieme Profitto 1 ad esempio è possibile definire una percentuale di impostazione del profitto del 50% per un gruppo di costi assegnato al materiale acquistato e una percentuale di impostazione del profitto dell'80% per un gruppo di costi assegnato alle categorie di costi per le operazioni dei cicli di lavorazione. Il contesto del calcolo DBA determina la modalità di gestione dei risultati di un prezzo di vendita calcolato:

-   **Calcolo DBA per un articolo e una versione di determinazione costi specificata**: il calcolo DBA genera un record di prezzo di vendita in sospeso nella versione di determinazione costi. Questo record del prezzo di vendita rappresenta il punto di partenza per la visualizzazione dei dettagli relativi al calcolo, ad esempio la visualizzazione della pagina **Calcola costo articolo**. Il record del prezzo di vendita è principalmente un dato di riferimento e non viene utilizzato come base per un prezzo di vendita negli ordini cliente.
-   **Calcolo DBA specifico dell'ordine**: una variazione della pagina **Calcolo DBA** viene utilizzata nel contesto di un ordine cliente, un'offerta di vendita o una voce di ordine di assistenza. Un calcolo DBA specifico di un ordine non genera un record nella versione di determinazione costi. Genera invece un record di calcolo che viene visualizzato nella pagina **Risultati calcolo DBA**. Questo record di calcolo rappresenta il punto di partenza per la visualizzazione dei dettagli relativi al calcolo, ad esempio la visualizzazione della pagina **Calcola costo articolo**. Le informazioni relative al record di calcolo selezionato possono essere trasferite nella voce di origine. Ad esempio, il prezzo di vendita calcolato può essere trasferito in una voce di ordine cliente.

## <a name="order-specific-bom-calculations"></a>Calcoli DBA specifici dell'ordine
Un calcolo della distinta base specifico dell'ordine rappresenta una variazione di un calcolo DBA per un articolo prodotto e viene eseguito nel contesto di una voce di un ordine cliente, un'offerta di vendita o un ordine di assistenza. Un calcolo DBA specifico di un ordine genera un record di calcolo che viene visualizzato nella pagina **Risultati di calcolo DBA**. che include un peso calcolato, un costo calcolato basato sui record dei costi attivi e un prezzo di vendita calcolato. IL record di calcolo generato da ciascun calcolo della formula specifico di un ordine nella pagina **Risultati calcolo DBA** viene identificato in modo univoco da un numero di calcolo. I risultati di un record di calcolo possono eventualmente essere trasferiti alla voce di origine. Un calcolo DBA specifico di un ordine è diverso da un calcolo DBA per un articolo prodotto in due modi:

-   Un calcolo DBA specifico di un ordine non genera un record di costo in una versione di determinazione costi. Di conseguenza, i criteri di calcolo DBA non vengono applicati quando un record di costo articolo viene creato oppure quando un record di costo viene sovrascritto.
-   Un calcolo DBA specifico di un ordine utilizza sempre i record dei costi attivi per i componenti, le categorie di costi e le formule di calcolo dei costi indiretti.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]