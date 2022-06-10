---
title: Registrazione dei costi indiretti
description: Questo argomento spiega come registrare i costi indiretti, creare gruppi di costi e aggiungere nodi alla scheda di determinazione costi per i costi indiretti.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CostSheetDesigner, BOMCostGroup, ProjCategory, CostingVersion, CostSheetCalculationFactor
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: d7f4753f69d83d172993e1c9b04be2220fdf253f
ms.sourcegitcommit: 1ea145dc606e243c7f51d91a5c0dd9e385bbda4a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "8804619"
---
# <a name="indirect-cost-posting"></a>Registrazione dei costi indiretti

I costi indiretti sono costi che non sono direttamente correlati a nessuna singola attività nel processo di produzione. Gli esempi includono i costi amministrativi come gli stipendi dei dipendenti, i costi del reparto contabilità e i costi generali come l'affitto, le utenze e i costi dei macchinari.

## <a name="calculating-indirect-costs"></a>Calcolo dei costi indiretti

Microsoft Dynamics 365 Finance non dispone di un modo automatizzato per calcolare la tariffa per i costi indiretti. È necessario determinare i costi indiretti, creare i codici di costo indiretto e mantenere la tariffa per ciascun costo indiretto nella scheda di determinazione dei costi.

Il processo esatto utilizzato per calcolare i costi indiretti potrebbe variare leggermente da società a società. Tuttavia, in generale, il processo consiste nei seguenti passaggi di base:

1. Crea un elenco di costi indiretti da riconoscere in produzione. Questo elenco potrebbe includere l'affitto, le spese amministrative, le spese contabili e le spese legali. Non deve includere i costi delle materie prime o del lavoro che sono rilevati nei cicli di lavorazione di produzione.
2. Somma tutti i costi indiretti. Puoi raggruppare tipi simili di costi indiretti o tenerli separati. Ciascun costo indiretto configurato può avere diversi conti principali utilizzati per la registrazione nella contabilità generale.
3. Confronta i costi indiretti con un fattore, denominato anche base di assorbimento. Il fattore può essere qualsiasi cosa tu scelga. Di seguito sono riportati alcuni esempi comuni:

    - Ricavi
    - Quantità totale prodotta
    - Tempo di attrezzaggio
    - Tempo di esecuzione

    È possibile selezionare il periodo per il quale vuoi calcolare i costi indiretti, ad esempio mensile, trimestrale o annuale. La somma dei tuoi costi indiretti e la somma del tuo fattore dovrebbero essere per la stessa quantità di tempo. La seguente formula viene utilizzata per calcolare il tasso di costo indiretto:

    *Tasso di costo indiretto* = *Totale spese indirette* &divide; *Fattore totale*

4. Crea i gruppi di costi indiretti.
5. Configura la scheda di determanzione costi con le tue tariffe.
6. Mantieni il costo per i tuoi costi indiretti nella versione di determinazione dei costi.

> [!NOTE]
> Puoi usare il modulo **Contabilità industriale** per accumulare costi e determinare le tue spese generali da diverse fonti, come produzione, progetti e contabilità generale. Per ulteriori informazioni, vedere [Contabilità industriale](/cost-accounting/cost-accounting-home-page.md).

> [!IMPORTANT]
> Diversi organismi di regolamentazione hanno pubblicato una guida sui tipi di costi che possono essere inclusi come costi indiretti o spese generali nel costo dei prodotti finiti. Prima di iniziare a configurare i costi indiretti, ti consigliamo di verificare con il tuo contabile e le normative locali per assicurarti di essere conforme.

## <a name="create-cost-groups-for-indirect-costs"></a>Creare i gruppi di costi per i costi indiretti

È necessario creare almeno un gruppo di costi da utilizzare per i costi indiretti. Non c'è limite al numero di gruppi di costi che puoi utilizzare. Considera come calcoli i tuoi costi e se ci sono tariffe diverse per diversi tipi di costi. Ad esempio, la tua organizzazione produce prodotti alimentari. Alcune materie prime e prodotti finiti sono prodotti secchi e hanno un costo indiretto per il magazzino. Altre materie prime e prodotti finiti sono refrigerati e hanno un costo indiretto maggiore. In questo caso, potresti voler creare due gruppi di costi: **Spese generali materiale secco** e **Spese generali materiale refrigerato**.

Per creare un gruppo di costi per i costi indiretti completa i passaggi seguenti.

1. Vai a **Controllo produzione &gt; Impostazioni &gt; Cicli di lavorazione &gt; Gruppi di costi**.
2. Seleziona **Nuovo** per creare un gruppo.
3. Nel campo **Gruppo di costi** immetti un nome univoco per il gruppo di costi, ad esempio **MATOVH**.
4. Nel campo **Nome** immetti una descrizione del gruppo di costi, ad esempio **Spese generali materiale**.
5. Nel campo **Tipo di gruppo di costi**, seleziona **Indiretto**.
6. Opzionale: nel campo **Comportamento** seleziona **Costo fisso** o **Costo variabile**.

## <a name="configure-the-costing-sheet-for-indirect-costs"></a>Configurare la scheda di determinazione costi per i costi indiretti

Dopo aver creato uno o più gruppi di costi, è possibile configurare la scheda di determinazione costi con i costi indiretti e definire il calcolo. Potresti voler raggruppare i costi indiretti nella scheda di determinazione costi. Per raggruppare i costi indiretti, puoi creare un'intestazione facoltativa nella scheda di determinazione costi. È necessario creare almeno un nodo per ciascun gruppo di costi nella scheda di determinazione costi. Per ogni gruppo di costi per i costi indiretti, puoi aggiungere un altro calcolo dei costi indiretti.

### <a name="indirect-cost-node-types"></a>Tipi di nodo costi indiretti

Questa sezione descrive i diversi tipi di nodi per i costi indiretti.

#### <a name="surcharge"></a>Supplemento

**Supplemento** è uno dei tipi più comuni di costi indiretti. Calcola una percentuale del costo da una base di assorbimento dei costi nell'ordine di produzione. È possibile definire la base di assorbimento selezionando i gruppi di costi collegati ai componenti del materiale o del tempo nella scheda di determinazione costi.

Ad esempio, un supplemento del 3% potrebbe essere aggiunto al costo di produzione per tutte le materie prime in un ordine di produzione.

#### <a name="rate"></a>Tasso

Un costo indiretto di tipo **Tariffa** viene utilizzato per aggiungere un importo fisso di costo all'ordine di produzione da una base di assorbimento dei costi nell'ordine di produzione. La tariffa può essere basata su uno dei tre sottotipi:

- **Elaborazione** – La tariffa si basa sul tempo di elaborazione del ciclo di lavorazione.
- **Attrezzaggio** – La tariffa si basa sul tempo di attrezzaggio del ciclo di lavorazione.
- **Quantità** – La tariffa si basa sulla quantità prodotta.

È possibile definire la base di assorbimento selezionando i gruppi di costi collegati ai componenti del materiale o del tempo nella scheda di determinazione costi.

Ad esempio, a ciascun ordine di produzione viene aggiunto un importo fisso di 2,00 dollari USA (USD), in base al tempo di esecuzione nel ciclo di lavorazione per il gruppo di costi di manodopera nella scheda di determinazione costi.

#### <a name="output-unit-based"></a>Basato su unità di output

Un costo indiretto di tipo **Basato sull'unità di output** viene calcolato moltiplicando l'importo specificato sulla Scheda dettaglio **Tariffa** della scheda di determinazione costi in base al sottotipo selezionato. Puoi selezionare la quantità, il peso o il volume del prodotto finito come moltiplicatore per il costo indiretto.

Ad esempio, si utilizza la quantità per calcolare 1,50 USD dell'ammortamento macchina per ciascuna quantità prodotta. Come altro esempio, usi il volume per calcolare 2,00 USD dei costi di refrigerazione per il volume di spazio che i prodotti finiti occupano nelle tue unità di refrigerazione.

#### <a name="input-unit-based"></a>Basato su unità di input

Un costo indiretto di tipo **Basato sull'unità di input** viene calcolato moltiplicando la quantità di materie prime consumate in un ordine di produzione per un importo. Puoi utilizzare il peso o il volume degli input nell'ordine di produzione per calcolare il totale. È possibile limitare il calcolo a un sottoinsieme di materiali selezionando uno o più gruppi di costi nella scheda dettaglio **Base di assorbimento** della scheda di determinazione costi.

Ad esempio, si utilizza il volume di input per un gruppo di costi specifico collegato a prodotti refrigerati per aggiungere 1,00 USD all'ordine di produzione.

### <a name="create-a-total-node-for-indirect-costs-in-the-costing-sheet"></a>Creare un nodo totale per i costi indiretti nella scheda di determinazione costi

Per creare un nodo totale per i costi indiretti nella scheda di determinazione costi, attieniti alla seguente procedura.

1. Passa a **Gestione costi &gt; Impostazioni criteri contabili costi indiretti &gt; Scheda di determinazione costi**.
2. Nell'albero, seleziona un nodo che rappresenta il costo dei beni che sono stati prodotti.
3. Seleziona **Nuovo** per creare un nodo.
4. Nel campo **Seleziona tipo di nodo** seleziona **Totale**.
5. Nel campo **Codice** immetti un ID univoco per il nodo, ad esempio **Costi generali produzione**.
6. Seleziona la casella di controllo **Intestazione**.
7. Seleziona la casella di controllo **Totale**.
8. Seleziona **OK**.

### <a name="create-an-indirect-cost-group-node-in-the-costing-sheet"></a>Creare un nodo di gruppo di costi indiretti nella scheda di determinazione costi

Per creare un nodo di gruppo di costi indiretti nella scheda di determinazione costi, attieniti alla seguente procedura.

1. Passa a **Gestione costi &gt; Impostazioni criteri contabili costi indiretti &gt; Scheda di determinazione costi**.
2. Nell'albero, seleziona il nodo in cui desideri creare il costo indiretto. Ad esempio, seleziona il nodo totale per **Costi generali produzione**.
3. Seleziona **Nuovo** per creare un nodo.
4. Nel campo **Seleziona tipo di nodo**, seleziona **Gruppo di costi**.
5. Nel campo **Codice** immetti un ID univoco per il nodo, ad esempio **TRANSP**.
6. Nel campo **Descrizione** immetti una breve descrizione, ad esempio **Costi generali trasporto**.
7. Seleziona **OK**.
8. Nel campo **Gruppo di costi** seleziona il gruppo di costi, ad esempio **OVH1: costi generali trasporto**.

### <a name="create-a-surcharge-indirect-cost"></a>Creare un costo indiretto di supplemento

Per creare un costo indiretto di supplemento nella scheda di determinazione costi, attieniti alla seguente procedura.

1. Passa a **Gestione costi &gt; Impostazioni criteri contabili costi indiretti &gt; Scheda di determinazione costi**.
2. Nell'albero, seleziona il nodo del gruppo di costi indiretti in cui desideri creare il costo indiretto. Ad esempio, seleziona il nodo totale per **TRASP - Costi generali trasporto**.
3. Seleziona **Nuovo** per creare un nodo.
4. Nel campo **Seleziona tipo di nodo** seleziona **Supplemento**.
5. Nel campo **Codice** immetti un ID univoco per il nodo, ad esempio **Supplemento trasporto**.
6. Seleziona **OK**.
7. Nel campo **Sottotipo** seleziona **Totale**.
8. Nella Scheda dettaglio **Base di assorbimento** seleziona **Nuovo** per creare un codice di costo.
9. Nel campo **Codice** seleziona un gruppo di costi da utilizzare per calcolare il supplemento.
10. Facoltativo: ripeti i passaggi da 8 a 9 per ogni gruppo di costi aggiuntivo che vuoi utilizzare per il calcolo.
11. Nella Scheda dettaglio **Supplemento** seleziona **Nuova** per creare una tariffa.
12. Nel campo **Versione** seleziona la versione di determinazione costi a cui aggiungere il supplemento.
13. Opzionale: nel campo **Sito** inserisci un sito a cui applicare il supplemento.
14. Nel campo **Percentuale** immetti la percentuale da calcolare sugli ordini di produzione dai gruppi di costi definiti nella scheda dettaglio **Base di assorbimento**.
15. Sulla Scheda dettaglio **Registrazioni contabili** seleziona il conto principale da utilizzare per i campi **Costi indiretti assorbiti stimati**, **Costo stimato dei costi indiretti consumati, WIP**, **Costi indiretti assorbiti**, e **Costo dei costi indiretti consumati, WIP**.
16. Opzionale: sulla Scheda dettaglio **Dimensioni finanziarie**, specifica le dimensioni finanziarie da inserire per impostazione predefinita nelle transazioni quando vengono registrate nella contabilità generale.

La procedura precedente mostra come creare un costo indiretto di tipo **Supplemento**. Passaggi simili vengono utilizzati per creare altri tipi di costi indiretti. Le sezioni seguenti descrivono le differenze per ciascun tipo.

#### <a name="rate"></a>Tasso

- Al passaggio 4, seleziona **Tariffa** invece di **Supplemento**.
- Al passaggio 7, seleziona **Elaborazione**, **Attrezzaggio**, o **Quantità** invece di **Totale**.
- Al passaggio 11, utilizza la Scheda dettaglio **Tariffa** invece di **Supplemento**.
- Nel passaggio 14, inserisci un importo nel campo **Importo** invece di una percentuale nel campo **Percentuale**.

#### <a name="output-unit-based"></a>Basato su unità di output

- Al passaggio 4, seleziona **Basato sull'unità di output** invece di **Supplemento**.
- Al passaggio 7, seleziona **Quantità**, **Peso**, o **Volume** invece di **Totale**.
- Ignora i passaggi da 8 a 10.
- Al passaggio 11, utilizza la Scheda dettaglio **Tariffa** invece di **Supplemento**.

#### <a name="input-unit-based"></a>Basato su unità di input

- Al passaggio 4, seleziona **Basato sull'unità di input** invece di **Supplemento**.
- Al passaggio 7, seleziona **Peso** o **Volume** invece di **Totale**.
- Al passaggio 11, utilizza la Scheda dettaglio **Tariffa** invece di **Supplemento**.
