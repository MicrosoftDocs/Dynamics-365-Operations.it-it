---
title: Contratti di progetto
description: "Vengono forniti esempi di contratti che è possibile creare per diversi tipi di progetto e fonti di finanziamento e viene illustrato il modo in cui è possibile gestire i contratti e le fatture dei clienti di progetto in Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: e46393b9ac8797bf12cca12099d177980b75ba38
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="project-contracts"></a>Contratti di progetto

[!include [banner](../includes/banner.md)]

Vengono forniti esempi e descrizioni di contratti creabili per diversi tipi di progetto e fonti di finanziamento e viene illustrato il modo in cui è possibile gestire i contratti e fatturare i progetti ai clienti in Microsoft Dynamics 365 for Finance and Operations.

Il tipo di progetto creato per un contratto di progetto determina il metodo utilizzato per rilasciare fatture ai clienti del progetto. È possibile modificare un contratto di progetto e il relativo progetto, ma non è possibile modificare il tipo di progetto. 

Un contratto di progetto consente di fatturare contemporaneamente uno o più progetti Il contratto di progetto consente inoltre di garantire che una procedura di fatturazione coerente venga utilizzata per ogni sottoprogetto in una struttura di progetto. 

Ogni progetto fatturato deve essere associato a un contratto di progetto. Le impostazioni per un contratto di progetto vengono applicate a tutti i progetti e sottoprogetti associati al contratto di progetto. 

Un contratto di progetto può specificare una o più fonti di finanziamento. È pertanto possibile suddividere la fatturazione tra più finanziatori, impostare limiti di finanziamento per impedire che alle fonti di finanziamento vengano fatturati importi superiori a quello specificato e configurare regole di finanziamento per il carico delle spese.

## <a name="funding-for-project-contracts"></a>Finanziamento dei contratti di progetto
In alcuni contratti di progetto viene specificato che più parti condividono la responsabilità del finanziamento dei costi di progetto. Di seguito sono riportati alcuni esempi.

-   Un cliente di grandi dimensioni con più divisioni richiede che il finanziamento di un progetto sia suddiviso per divisione.
-   La società condivide i costi di un progetto di grandi dimensioni con un'organizzazione esterna.
-   Un progetto per una strada è cofinanziato da due comuni.
-   Un progetto per un ponte è finanziato da una sovvenzione di governo e da una società privata.

In Finance and Operations, è possibile suddividere la fatturazione per una singola transazione o un intero progetto tra più clienti, sovvenzioni o organizzazioni. 

In progetti con più finanziatori, tutte le parti che contribuiscono a un progetto di finanziamento avanzato sono denominate fonti di finanziamento. Quando un cliente, organizzazione, o sovvenzione viene definito come fonte di finanziamento, potrà essere assegnato a una o più regole di finanziamento. Le regole di finanziamento contengono i criteri che determinano come le spese sono allocate a diverse fonti di finanziamento per un progetto. 

Poiché gli articoli stoccati, ad esempio quelli visualizzati nelle richieste di acquisto e ordini fornitore, non possono essere suddivisi, l'importo costi non può essere suddiviso tra più fonti di finanziamento al momento della distribuzione. Il valore relativo alla fonte di finanziamento rimane quindi pari a zero fino al momento della registrazione dell'uscita da magazzino. Quando l'uscita da magazzino viene registrata, l'importo dei costi viene distribuito in base alle regole di distribuzione contabile del progetto.

Di seguito sono riportati alcuni passaggi che è possibile eseguire per rendere più facile suddividere la fatturazione tra più fonti di finanziamento:

-   Specificare che tutte le transazioni registrate per un progetto utilizzino la stessa valuta di vendita presente nel contratto del progetto stesso.
-   Impostare i limiti di finanziamento in modo che a una fonte di finanziamento non sia possibile fatturare per un progetto importi superiori a un limite specificato.
-   Configurare le regole di finanziamento e i limiti di finanziamento per ciascun lavoratore, articolo, categoria, gruppo di categorie e tipo di transazione (o per tutti i tipi di transazione).
-   Selezionare facoltativamente le date di inizio e di fine per definire il periodo di validità di ciascuna regola di finanziamento.
-   Specificare la percentuale di cui è responsabile ciascuna fonte di finanziamento.
-   Specificare la fonte di finanziamento responsabile delle differenze di arrotondamento derivanti dai calcoli per l'allocazione del finanziamento.
-   Impostare le regole che determinano le modalità di fatturazione dei costi di progetto ai clienti esterni e per le modalità di addebito alle organizzazioni interne.
-   Registrare le transazioni in un conto di finanziamento in sospeso fino all'ottenimento di un finanziamento aggiuntivo o fino alla decisione di farsi carico dei costi internamente.

Per determinare la fascia IVA da associare a una transazione, viene effettuata la ricerca di un'assegnazione di fascia IVA all'interno del progetto. Se non è stata effettuata alcuna assegnazione di fascia IVA a livello di progetto, viene effettuata la ricerca nel contratto di progetto.

### <a name="example-multiple-funding-sources-simple"></a>Esempi: più fonti di finanziamento (semplice)

Nella tabella riportata di seguito vengono illustrati gli scenari per la gestione dell'allocazione del finanziamento tra più fonti di finanziamento. Questi scenari si basano sui seguenti presupposti:

-   Le impostazioni di priorità vengono considerate fattori importanti per l'allocazione di fondi prima dell'applicazione di altri criteri della regola di finanziamento.
-   Alcun intervallo di date è stato specificato per definire il periodo d in cui la regola di finanziamento è valida.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Scenario</strong></td>
<td><strong>Fonte di finanziamento</strong></td>
<td><strong>Percentuale di allocazione </strong></td>
<td><strong>Priorità di allocazione</strong></td>
</tr>
<tr class="even">
<td>Si desidera allocare i costi a una fonte di finanziamento fino a esaurire i relativi fondi, allocare i costi a una seconda fonte di finanziamento fino a esaurire i fondi e infine allocare i costi rimanenti a una terza fonte di finanziamento.</td>
<td><ul>
<li>Fonte di finanziamento 1</li>
<li>Fonte di finanziamento 2</li>
<li>Fonte di finanziamento 3</li>
</ul></td>
<td><ul>
<li>100%</li>
<li>100%</li>
<li>100%</li>
</ul></td>
<td><ul>
<li>1</li>
<li>2</li>
<li>3</li>
</ul></td>
</tr>
<tr class="odd">
<td>Si desidera allocare il 75 percento dei costi a una fonte di finanziamento e il 25 percento a una seconda fonte. Quando una delle fonti di finanziamento è esaurita, si desidera pagare i costi rimanenti da una terza fonte di finanziamento.</td>
<td><ul>
<li>Fonte di finanziamento 1</li>
<li>Fonte di finanziamento 2</li>
<li>Fonte di finanziamento 3</li>
</ul></td>
<td><ul>
<li>75%</li>
<li>25%</li>
<li>100%</li>
</ul></td>
<td><ul>
<li>1</li>
<li>1</li>
<li>2</li>
</ul></td>
</tr>
<tr class="even">
<td>Si desidera allocare il 75 percento dei costi a una fonte di finanziamento e il 25 percento a una seconda fonte. Quando una delle fonti di finanziamento è esaurita, si desidera dividere i costi rimanenti tra una terza e una quarta fonte di finanziamento.</td>
<td><ul>
<li>Fonte di finanziamento 1</li>
<li>Fonte di finanziamento 2</li>
<li>Fonte di finanziamento 3</li>
<li>Fonte di finanziamento 4</li>
</ul></td>
<td><ul>
<li>75%</li>
<li>25%</li>
<li>50%</li>
<li>50%</li>
</ul></td>
<td><ul>
<li>1</li>
<li>1</li>
<li>2</li>
<li>2</li>
</ul></td>
</tr>
<tr class="odd">
<td>Si desidera allocare il primo 25 percento dei costi a una fonte di finanziamento e il resto a una seconda fonte di finanziamento.</td>
<td><ul>
<li>Fonte di finanziamento 1</li>
<li>Fonte di finanziamento 2</li>
</ul></td>
<td><ul>
<li>25%</li>
<li>100%</li>
</ul></td>
<td><ul>
<li>1</li>
<li>2</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="example-multiple-funding-sources-complex"></a>Esempio: più fonti di finanziamento (complesso)

Sono disponibili tre fonti di finanziamento che si desidera utilizzare nel seguente ordine:

1.  Utilizzare equamente la fonte di finanziamento 2 e la fonte di finanziamento 3 fino a esaurire la fonte di finanziamento 2.
2.  Continuare a utilizzare la fonte di finanziamento 3 fino a esaurimento.
3.  Utilizzare la fonte di finanziamento 1 quando la fonte di finanziamento 3 viene esaurita.

Per realizzare l'obiettivo in questione, è necessario eseguire le seguenti operazioni:

-   Impostare limiti di finanziamento per le fonti di finanziamento 2 e 3 per i rispettivi importi.
-   Creare le seguenti regole di finanziamento:
    -   Regola 1: (priorità 1) allocare il 50 percento delle transazioni alla fonte di finanziamento 2 e il 50 percento alla fonte di finanziamento 3.
    -   Regola 2: (priorità 2) allocare il 100 percento delle transazioni alla fonte di finanziamento 3.
    -   Regola 3: (priorità 3) allocare il 100 percento delle transazioni alla fonte di finanziamento 1.

Questa impostazione funziona poiché le transazioni vengono confrontate con le regole e i limiti per determinare se una qualsiasi si applica alla transazione. Se alla transazione non si applica alcun limite o regola specifico, si applicherà la regola Tutte le transazioni. La regola Tutte le transazioni corrisponde a tutte le transazioni. 

Se viene trovata una regola che corrisponde a una transazione, in primo luogo si applica la percentuale che è stata allocata nella regola, ma solo dopo che le corrispondenze vengono confrontate con tutti i limiti impostati. Se un limite è stato raggiunto e i fondi di una fonte di finanziamento vengono esauriti, la regola di finanziamento associata al limite di finanziamento viene ignorata e il programma verifica la presenta della regola successiva applicabile. 

In alcuni casi, solo parte di una transazione può essere allocata in base a una regola. Ciò potrebbe verificarsi poiché un limite viene raggiunto quando la transazione viene allocata. In questo caso, solo un certo importo viene allocato in base alla regola, ad esempio il 50 percento a ciascuna fonte di finanziamento. Questo si verifica nella regola 1, descritta in precedenza in questa sezione. Il resto viene allocato in base alla regola successiva nella sequenza. 

Nella tabella seguente questo scenario viene esaminato in modo più dettagliato.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Elemento attivo</strong></td>
<td><strong>Dettagli</strong></td>
</tr>
<tr class="even">
<td>Regole di finanziamento</td>
<td><ul>
<li>Regola 1 (priorità 1): tutte le transazioni. Allocare la fonte di finanziamento 2 per il 50% e la fonte di finanziamento 3 per il 50%.</li>
<li>Regola 2 (priorità 2): tutte le transazioni. Allocare la fonte di finanziamento 3 per il 100%.</li>
<li>Regola 3 (priorità 2): tutte le transazioni. Allocare la fonte di finanziamento 1 per il 100%.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Limiti di finanziamento</td>
<td><ul>
<li>Limite della fonte di finanziamento 1 = 10.000,00</li>
<li>Limite della fonte di finanziamento 2 = 500,00</li>
<li>Limite della fonte di finanziamento 3 = 750,00</li>
</ul></td>
</tr>
<tr class="even">
<td>Transazione 1</td>
<td><strong>Importo della transazione:</strong> 100.00<strong>Finanziamento:</strong> La transazione viene pagata solo in base alla regola 1, poiché la transazione è interamente pagata dopo l'applicazione della regola 1. La transazione è finanziata equamente tra la fonte di finanziamento 2 e la fonte di finanziamento 3.
<ul>
<li>Fonte di finanziamento 2: 50,00</li>
<li>Fonte di finanziamento 3: 50,00</li>
</ul></td>
</tr>
<tr class="odd">
<td>Transazione 2</td>
<td><strong>Importo della transazione:</strong> 5.000,00<strong>Finanziamento:</strong> la transazione viene pagata in base a tutte e tre le regole. <strong>Regola 1</strong>
<ul>
<li>Fonte di finanziamento 2: 450,00</li>
<li>Fonte di finanziamento 3: 450,00</li>
</ul>
<strong>Regola 2</strong>
<ul>
<li>Fonte di finanziamento 3: 250,00 (= 750,00 – 50,00 – 450,00)</li>
</ul>
<strong>Regola 3</strong>
<ul>
<li>Fonte di finanziamento 1: 3.850,00 (= 5.000,00 – 450,00 – 450,00 – 250,00)</li>
</ul></td>
</tr>
<tr class="even">
<td>Fondi totali distribuiti per ciascuna fonte di finanziamento</td>
<td><ul>
<li>Fonte di finanziamento 1: 3.850,00</li>
<li>Fonte di finanziamento 2: 500,00</li>
<li>Fonte di finanziamento 3: 750,00</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="billing-rules"></a>Regole di fatturazione
Nel contratto di progetto negoziato con il cliente vengono definiti tempi e modalità per poter fatturare al cliente un lavoro nell'ambito di un progetto. Dopo aver impostato il progetto e il relativo contratto, è possibile stabilire le regole di fatturazione del progetto stesso. Tali regole si basano sui termini specificati nel contratto di progetto. Le regole di fatturazione che è possibile creare dipendono dai termini del contratto di progetto e dal tipo di progetto, ad esempio Tempistica e materiali o A prezzi fissi, associato alla regola di fatturazione. È possibile creare più di una regola di fatturazione per un contratto di progetto. È inoltre possibile assegnare una regola di fatturazione a più progetti associati allo stesso contratto di progetto e applicare termini di fatturazione simili. 

Si possono impostare i seguenti tipi di regole di fatturazione:

-   **Unità di consegna** – Fatturazione al cliente dopo il completamento di un'unità di consegna. L'utente definisce le unità di consegna all'interno del contratto.
-   **Stato** – Fatturazione al cliente dopo il completamento di una percentuale di progetto specificata. È possibile impostare una regola di fatturazione per calcolare automaticamente la percentuale di lavoro completato, oppure è possibile calcolare manualmente la percentuale di lavoro completato e l'importo da fatturare al cliente.
-   **Punto cardine** – Fatturazione a un cliente per l'intero importo relativo a un punto cardine di un progetto quando viene raggiunto tale punto cardine.
-   **Commissioni** - Fatturazione a un cliente per i servizi forniti più una commissione di gestione, in genere costituita da una percentuale del costo dei servizi.
-   **Tempistica e materiali** - Fatturazione a un cliente per il valore di tempo e i materiali utilizzati per un progetto.

Per tutti i tipi di regole di fatturazione, è possibile specificare una percentuale di ritenuta detratta dalle fatture cliente finché un progetto non raggiunge una fase concordata. La percentuale di ritenuta pagamento è specificata nel contratto di progetto. L'importo viene calcolato in base al, e sottratto dal, valore totale delle righe di una fattura cliente. 

Per le regole di fatturazione **Tempistica e materiali** e **Progressiva** è possibile assegnare le categorie addebitabili. Tali categorie indicano le transazioni da includere nelle fatture cliente. 

Quando si desidera fatturare al cliente, l'importo da fatturare per il progetto viene calcolato in base alle regole di fatturazione e viene generata una proposta di fattura di progetto. 

Nelle sezioni seguenti vengono forniti alcuni esempi che illustrano come impostare e gestire le regole di fatturazione per un progetto.

### <a name="example-create-a-billing-rule-that-is-based-on-the-number-of-units-delivered"></a>Esempio: Creare una regola di fatturazione in base al numero di unità consegnate

L'organizzazione stipula un contratto fornire a un totale di cinque sessioni di formazione ai dipendenti di un cliente al costo di 10.000 per sessione. La fatturazione al cliente verrà eseguita dopo ogni sessione di formazione. 

Quando si impostano le regole di fatturazione per il contratto, si utilizzano i valori seguenti:

-   L'unità di consegna è la singola sessione di formazione.
-   Il prezzo unitario è di 10.000 per sessione di formazione.
-   Il numero totale di unità è di cinque sessioni di formazione.

Dopo aver completato una sessione di formazione, è possibile creare una fattura per l'importo di 10.000 per la prima unità consegnata e inviare la fattura al cliente.

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-manual-calculation"></a>Esempio: Creare una regola di fatturazione basata su una percentuale di completamento del progetto specificata (calcolo manuale)

L'organizzazione dell'utente (una società di consulenza software) stipula un contratto con un cliente per sviluppare una parte di un prodotto che il cliente sta realizzando. L'organizzazione accetta di consegnare il codice software in un periodo di sei mesi, mentre il cliente accetta di corrispondere all'organizzazione un totale di 100.000 per questo lavoro. Viene creata una regola di fatturazione per fatturare al cliente in base alla percentuale di lavoro completata nel progetto come specificato nel contratto.

-   Al termine del primo mese, l'utente incontra il cliente per stabilire la percentuale di lavoro completata e in seguito alla revisione del progetto, insieme al cliente, decide che la percentuale di completamento è pari al 15%.
-   Viene pertanto creata una fattura per l'importo di 15.000 (15% di $100.000), successivamente inviata al cliente.

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-automatic-calculation"></a>Esempio: Creare una regola di fatturazione basata su una percentuale di completamento del progetto specificata (calcolo automatico)

L'organizzazione, una società di sviluppo software, accetta di sviluppare un pacchetto per la contabilità delle retribuzioni per un cliente al costo di 30.000. Il cliente accetta di effettuare i pagamenti all'organizzazione in base alla percentuale di lavoro completato. L'utente stima che i costi di progetto ammontano a 20.000. Nel contratto di progetto vengono specificate le categorie di lavoro da utilizzare nel processo di fatturazione. Vengono quindi impostate le regole di fatturazione che calcolano automaticamente gli importi della fattura per la percentuale di lavoro completato per ogni categoria. e viene impostato un budget per ogni categoria:

-   **Sviluppo**: costo di 15.000 e ricavi per 20.000
-   **Installazione**: costo di 5.000 e ricavi per 10.000

Quando si crea una fattura cliente per la prima volta, l'importo della fattura viene calcolato automaticamente in base alle informazioni seguenti:

-   Dopo un mese, il dipendente impegnato nel progetto invia una scheda attività relativa al progetto. Il costo per le ore di lavoro è di 5.000 per lo sviluppo e di 1.000 per l'installazione. Il lavoro di sviluppo è completo al 33% (5.000 in costi effettivi /15.000 in costi di budget), mentre il lavoro di installazione è completo al 20% (1.000 in costi effettivi /5.000 in costi di budget).
-   L'importo della fattura, pari a 8.667, verrà calcolato automaticamente (il 33% di 20.000 + il 20% di 10.000).
-   Viene pertanto creata una fattura per l'importo di 8.667 successivamente inviata al cliente.

### <a name="example-create-a-billing-rule-that-is-based-on-agreed-upon-milestones"></a>Esempio: Creare una regola di fatturazione basata su punti cardine stabiliti

L'organizzazione dell'utente, una società di consulenza gestionale, acconsente di condurre una ricerca di mercato su un prodotto consumer che il cliente prevede di vendere. Il cliente accetta di utilizzare i servizi dell'utente per un periodo di tre mesi, a partire da marzo, e acconsente al pagamento di 50.000 all'organizzazione dell'utente. Il progetto è costituito da tre punti cardine:

-   Punto cardine 1: raccolta dei dati sui consumatori (31 marzo)
-   Punto cardine 2: analisi dei dati sui consumatori (30 aprile)
-   Punto cardine 3: presentazione di una proposta di fattibilità per il prodotto (31 maggio).

Il cliente accetta di pagare all'organizzazione 10.000 per il primo punto cardine, 20.000 per il secondo punto cardine e 20.000 per il terzo punto cardine. 

Quando imposta il contratto di progetto, l'organizzazione accetta di fatturare al cliente in base al punto cardine completato. L'impostazione delle regole di fatturazione è costituita dai passaggi seguenti:

-   Definizione delle fasi di progetto.
-   Definire l'importo da fatturare al cliente quando viene ogni punto cardine è completato.

Quando si completa il primo punto cardine, il 31 marzo, si contrassegna il punto cardine come completato, quindi si crea una fattura per l'importo di 10.000 e si invia al cliente. Non è possibile creare una fattura per un punto cardine finché il punto cardine non è contrassegnato come completo.

### <a name="example-create-a-billing-rule-that-is-based-on-services-plus-a-management-fee"></a>Esempio: Creare una regola di fatturazione basata sui servizi forniti più una commissione di gestione

L'organizzazione dell'utente, una società di consulenza gestionale, accetta di condurre una ricerca di mercato per valutare la fattibilità di un prodotto che il cliente, un società di vendita al dettaglio, sta sviluppando. Le condizioni del contratto indicano che l'organizzazione dovrà fornire i servizi di tre consulenti gestionali principali che condurranno la ricerca su basi di tempistica e di materiali. Il cliente accetta di corrispondere 100 per ciascuna ora, oltre a una commissione di gestione pari al 10% per le ore di consulenza attribuite al progetto. 

Durante l'impostazione del contratto di progetto viene creata una regola di fatturazione che consente di aggiungere una commissione di gestione del 10% alle ore di consulenza attribuite al progetto. 

Quando si crea una fattura per il cliente, a quest'ultimo vengono addebitati una commissione di gestione del 10% insieme al costo delle ore di consulenza. Se ad esempio il totale delle ore di lavoro sul progetto dei tre consulenti è di 200 ore, viene creata una fattura per l'importo di 22.000 in base al calcolo seguente:

-   200 ore al costo di 100 all'ora = 20.000
-   commissione di gestione del 10% = 2.000
-   Importo totale fattura = 22.000

Se le commissioni sono tassabili per un cliente e si seleziona una fascia IVA nel contratto di progetto, la fascia IVA verrà immessa automaticamente in una regola di fatturazione per le commissioni.

### <a name="example-create-a-billing-rule-for-the-value-of-time-and-materials"></a>Esempio: Creazione di una regola di fatturazione per il valore delle ore di lavoro e dei materiali

L'organizzazione, una società di consulenza software, ha stipulato un contratto in base al quale cinque consulenti tecnici lavoreranno su un progetto di sviluppo software per un cliente per i sei mesi successivi. Il cliente accetta di pagare 150 per ogni ora di consulenza, più il costo della cancelleria. L'organizzazione invierà una fattura al cliente alla fine di ogni mese. 

Al momento di impostare il contratto di progetto, l'utente accetta di fatturare ogni mese al cliente le ore di lavoro e i materiali per il progetto. L'utente crea una regola di fatturazione che include le informazioni seguenti:

-   Il periodo del contratto è di sei mesi.
-   Il tempo di consulenza viene calcolato alla tariffa di 150 all'ora.
-   La cancelleria viene fatturata in base al costo e il costo totale del progetto non deve superare 10.000.
-   L'utente crea una fattura cliente alla fine di ogni mese di calendario per tutta la durata del progetto.

Durante il primo mese, i consulenti registrano 800 ore di lavoro totali nell'ambito del progetto. Il costo della cancelleria addebitato al progetto è di 2.000. Alla fine del mese, l'utente crea quindi una fattura per un importo di 122.000, calcolato nel modo seguente: 800 ore al costo di 150 all'ora più 2.000 per gli articoli di cancelleria.




