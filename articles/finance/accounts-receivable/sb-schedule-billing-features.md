---
title: Funzionalità del programma di fatturazione
description: In questo argomento vengono illustrate le funzionalità del programma di fatturazione, ad esempio metodi di determinazione del prezzo, escalation e sconti, date di allineamento, ripartizione proporzionale, fatturazione con storno e gruppi di articoli suddivisi.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 0ce323565a94e8e70d90a65b7a3143e984a1c159
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8700723"
---
# <a name="billing-schedule-features"></a>Funzionalità del programma di fatturazione

[!include [banner](../includes/banner.md)]

In questo argomento vengono illustrate le funzioni del programma di fatturazione e delle righe programma di fatturazione. Descrive i diversi metodi utilizzati per la determinazione del prezzo, come utilizzare le escalation e gli sconti e come stornare un periodo di fatturazione. Include anche esempi di calcoli proporzionali e gruppi di articoli divisi.

## <a name="pricing-methods"></a>Metodi di determinazione dei prezzi

È possibile utilizzare uno dei seguenti metodi di determinazione dei prezzi per calcolare il prezzo unitario di un articolo:

* Flat
* Standard
* Livello
* Livello forfettario

### <a name="flat-pricing"></a>Determinazione dei prezzi forfettari

Quando viene utilizzato il metodo di determinazione dei prezzi forfettari, il prezzo unitario per una voce del programma di fatturazione nella pagina **Tutti i programmi di fatturazione** può essere modificata in qualsiasi valore. Il valore **Unità di prezzo** è sempre **1**. Quindi, i valori **Prezzo unitario** e **Importo netto** per un articolo sono uguali.

### <a name="standard-pricing-without-a-trade-agreement"></a>Prezzo standard (senza accordo commerciale)

Quando si utilizza il metodo di determinazione dei prezzi standard senza un accordo commerciale, si imposta il prezzo unitario per una voce del programma di fatturazione selezionando **Gestione delle informazioni sui prodotti** nella pagina **Dettagli prodotto rilasciato**. Il prezzo unitario è indicato nella sezione **Prezzo vendita di base**. È calcolato come *Prezzo* &divide; *Quantità prezzo*.

### <a name="standard-pricing-with-a-trade-agreement"></a>Prezzo standard (con accordo commerciale)

Gli esempi seguenti mostrano i calcoli dei prezzi standard quando esiste un accordo commerciale. È possibile creare accordi commerciali dalla pagina **Dettagli prodotto rilasciato**.

Entrambi gli esempi utilizzano un articolo con le seguenti fasce di prezzo.

| Da qtà | A qtà | Unità di misura | Prezzo | Unità di prezzo |
|---|---|---|---|---|
| 0 | 100 | Ciascuno | 1,50 | 1 |
| 100 | 200 | Ciascuno | 1.25 | 1 |
| 200 | 999999 | Ciascuno | 1,00 | 1 |

**Esempio 1**

La quantità della fattura è 250 e viene utilizzato il metodo di determinazione dei prezzi standard. Poiché la quantità è compresa nell'intervallo di quantità prezzo tra 200 e 999.999, il prezzo unitario è 1,00. 

L'importo netto viene calcolato nel seguente modo:

*Importo netto* = (*Quantità* &times; *Prezzo*) &divide; *Prezzo unitario* = (250 &times; 1,00) &divide; 1 = 250

**Esempio 2**

La quantità della fattura è 100 e viene utilizzato il metodo di determinazione dei prezzi standard. Poiché la quantità in fattura è compresa nell'intervallo di quantità prezzo tra 0 e 100, il prezzo unitario è 1,50.

> [!NOTE]
> La quantità in fattura è compresa nell'intervallo 0-100 anziché nell'intervallo 100-200 perché, nel comportamento di corrispondenza quantità standard, una quantità corrisponde se è *maggiore o uguale* alla quantità "da" e *meno* della quantità "a".

L'importo netto viene calcolato nel seguente modo:

*Importo netto* = (100 &times; 1,50) &divide; 1 = 150

### <a name="tier-pricing"></a>Determinazione dei prezzi con livelli

Per entrambi gli esempi, un articolo ha le seguenti fasce di prezzo.

| Da qtà | A qtà | Unità di misura | Prezzo | Unità di prezzo |
|---|---|---|---|---|
| 0 | 100 | Ciascuno | 1,50 | 10 |
| 100 | 200 | Ciascuno | 1.25 | 10 |
| 200 | 999999 | Ciascuno | 1,00 | 10 |

Se la quantità della fattura è 250 e viene utilizzato il metodo di determinazione dei prezzi con livelli, i prezzi degli articoli vengono calcolati nel modo seguente, in base alle fasce di prezzo:

- **Primi 100 articoli:** 100 &times; 1,50 = 150,00
- **Secondi 100 articoli:** 100 &times; 1,25 = 125,00
- **Articoli rimanenti:** 50 &times; 1,00 = 50,00

L'importo netto viene calcolato nel seguente modo:

*Importo netto* = (150,00 &divide; 10) + (125,00 &divide; 10) + (50,00 &divide; 10) = 15,00 + 12,50 + 5,00 = 32,50

Dopo aver calcolato l'importo netto, il prezzo unitario viene calcolato dividendo l'importo netto per la quantità:

*Prezzo unitario* = 32,50 &divide; 250 = 0,13

### <a name="flat-tier-pricing"></a>Determinazione dei prezzi con livelli forfettari

Per entrambi gli esempi, un articolo ha le seguenti fasce di prezzo.

| Da qtà | A qtà | Unità di misura | Importo livello forfettario | Unità di prezzo |
|---|---|---|---|---|
| 0 | 50 | Ciascuno | 100,00 | 50 |
| 50 | 200 | Ciascuno | 150,00 | 200 |

La tabella seguente mostra le fatture e i prezzi unitari per le diverse quantità acquistate. Viene prima calcolato l'importo netto, quindi viene calcolato il prezzo unitario.

| Fattura | Quantità acquistata | Prezzo unitario | Importo netto |
|---|---|---|---|
| 1 | 25 | 2,00 &divide; 25 = 0,08 | 100 &divide; 50 = 2,00 |
| 2 | 20 | 2,00 &divide; 20 = 0,10 | 100 &divide; 50 = 2,00 |
| 3 | 50 | 2,00 &divide; 50 = 0,04 | 100 &divide; 50 = 2,00 |
| 4 | 60 | 0.75 &divide; 60 = 0,0125 = 0,01 | 150 &divide; 200 = 0,75 |

## <a name="escalations-and-discounts"></a>Escalation e sconti

Una *escalation* è un aumento di prezzo per un periodo di fatturazione futuro per il quale la fattura non è stata ancora creata. Uno *sconto* è una riduzione di prezzo per un periodo di fatturazione futuro per il quale la fattura non è stata ancora creata.

Nella fatturazione abbonamento, le escalation e gli sconti non possono essere applicati retroattivamente a un programma di fatturazione. Ad esempio, non puoi applicare un'escalation a un programma di fatturazione tre mesi prima ed elaborarla. In altre parole, non è possibile applicare un aumento di prezzo avvenuto tre mesi fa.

Puoi applicare un'escalation o uno sconto a un programma di fatturazione o a una riga del programma di fatturazione in una delle seguenti posizioni:

- La pagina elenco **Tutti i programmi di fatturazione o Programmi di fatturazione attivi**
- Un programma di fatturazione specifico
- Una riga programma di fatturazione specifica

### <a name="apply-an-escalation-or-discount"></a>Applicare un'escalation o uno sconto

Per applicare un'escalation o uno sconto a un programma di fatturazione, attieniti alla seguente procedura.

1. Seleziona un programma di fatturazione o una riga programma di fatturazione.
2. Seleziona **Escalation e sconto** nella scheda **Escalation e sconto** o nella riga del programma di fatturazione.
3. Se viene utilizzato un indice dei prezzi al consumo per calcolare l'escalation o lo sconto, seleziona un valore nel campo **Calcolo dell'indice dei prezzi al consumo**.
4. Seleziona **Nuovo** per aggiungere una riga di escalation o di sconto.
5. Per uno sconto, seleziona la casella di controllo **Sconto**. Per un'escalation, lasciare la casella di controllo **Sconto** deselezionata.
6. Imposta i campi **Data di inizio** e **Frequenza**.
7. Per le voci di differimento che utilizzano la funzione ricavi non fatturati, imposta il campo **Data di fine**.
8. Imposta il campo **Percentuale**, **Importo**, o **Programma dell'indice dei prezzi al consumo**.
9. Imposta il campo **Data di fine**.
10. Seleziona **OK**.
11. Ripeti i passaggi da 4 a 10 per ogni ulteriore riga di escalation o di sconto richiesta.

### <a name="fields-on-the-billing-schedule-lines-page"></a>Campi della pagina Righe programma di fatturazione

La pagina **Righe programma di fatturazione** contiene i seguenti campi.

| Campo | Description |
|---|---|
| Numero articolo | Il numero di articolo della riga di programma di fatturazione. Questo campo è disponibile solo quando la pagina viene aperta da una voce del programma di fatturazione. |
| Calcolo indice dei prezzi al consumo | <p>Seleziona il metodo utilizzato per calcolare l'escalation dell'indice dei prezzi al consumo:</p><ul><li>**Indice dei prezzi al consumo precedente** – Utilizza il valore dell'indice dei prezzi al consumo precedente per il calcolo dell'escalation.</li><li>**Indice dei prezzi al consumo di base** – Utilizza il valore dell'indice dei prezzi al consumo di base per il calcolo dell'escalation.</li></ul> |
| Griglia **Riga** | |
| Sconto | <p>Imposta la casella di controllo per specificare se la modifica dell'importo è un'escalation o uno sconto:</p><ul><li>**Selezionato** – La modifica applica uno sconto al programma di fatturazione o alla riga del programma di fatturazione.</li><li>**Deselezionato** – La modifica applica un'escalation a un programma di fatturazione o a una riga del programma.</li></ul><p>L'impostazione di questa casella di controllo non può essere modificata per gli articoli che utilizzano la funzione ricavi non fatturati. Inoltre, non è possibile applicare sconti agli articoli che utilizzano la suddivisione dei ricavi.</p> |
| Data di inizio | Seleziona la data di inizio dell'escalation o dello sconto. |
| Frequenza | Seleziona la frequenza dell'escalation o dello sconto: **Nessuna**, **Mensile**, **Trimestrale**, **Semestrale**, o **Annuale**. |
| Percentuale | Specifica la percentuale dell'escalation o dello sconto. |
| Importo | Specifica l'importo dell'escalation o dello sconto. |
| Programmazione indice dei prezzi al consumo | Seleziona il programma dell'indice dei prezzi al consumo utilizzato per i calcoli. |
| Data di fine | <p>Seleziona la data di fine dell'escalation o dello sconto.</p><p>**Nota:** Questo campo è obbligatorio per gli articoli che utilizzano la funzione ricavi non fatturati.</p> |
| Numero programmazione differimento | <p>Il numero del programma di differimento.</p><p>Questo campo è disponibile solo quando la pagina viene aperta da una riga del programma di fatturazione.</p> |
| Numero batch giornale di registrazione | <p>Numero batch del giornale di registrazione.</p><p>Questo campo è disponibile solo quando la pagina viene aperta da una riga del programma di fatturazione.</p> |
| Totale importo sconto | <p>La somma degli importi di sconto per tutte le righe della griglia.</p><p>Questo campo è disponibile solo quando la pagina viene aperta da una riga del programma di fatturazione.</p> |
| Importo corrente dei ricavi non fatturati a breve termine | <p>L'importo corrente dei ricavi non fatturati a breve termine.</p><p>Questo importo appare quando viene selezionato un metodo di differimento a breve termine nella pagina **Parametri di fatturazione ricorrente di contratti** e i conti per la voce vengono impostati nella pagina **Configurazione ricavi non fatturati**.</p> |
| Importo corrente dei ricavi non fatturati a lungo termine | <p>L'importo corrente dei ricavi non fatturati a lungo termine.</p><p>Questo importo appare quando viene selezionato un metodo di differimento a breve termine nella pagina **Parametri di fatturazione ricorrente di contratti** e i conti per la voce vengono impostati nella pagina **Configurazione ricavi non fatturati**.</p> |

## <a name="proration-examples"></a>Esempi di ripartizione

I calcoli per la ripartizione possono essere basati sul numero di giorni o sul numero di mesi. Il metodo utilizzato per il calcolo della ripartizione è impostato nella pagina **Parametri di fatturazione ricorrente di contratti**. Il metodo di ripartizione incide sul modo in cui gli importi vengono calcolati per un programma di fatturazione nelle seguenti situazioni:

- Creazione iniziale
- Applicazione di un'escalation o di uno sconto
- Fine
- Posizionamento o rimozione di una sospensione
- Aggiunta di supporto o rinnovo

Il metodo di ripartizione incide anche sui calcoli del report sui ricavi ricorrenti mensili (MRR).

### <a name="example-1"></a>Esempio 1

L'importo annuale di un programma di fatturazione è $ 5.000. La data di inizio è il 12 agosto 2019 e la data di fine è il 22 dicembre 2019. La frequenza di fatturazione è annuale. L'importo proporzionale viene calcolato con le seguenti modalità, a seconda che si utilizzi il metodo di calcolo giornaliero o mensile:

- **Giornaliero**

    - *Numero di giorni* = *Data di fine* – *Data d'inizio* + 1 = 133 giorni
    - *Numero di giorni dell'anno* = 11 agosto 2020 – 12 agosto 2019 + 1 = 366 giorni
    - *Importo proporzionale* = 5.000 &times; (133 &divide; 366) = 1816,94

- **Ogni mese**

    - *Parte del mese di inizio* = (31 – 12 + 1) &divide; 31 = 20 &divide; 31
    - *Mesi medi* = 3
    - *Parte del mese di fine* = 22 &divide; 31
    - Importo proporzionale = 5.000 &divide; 12 &times; \[(20 &divide; 31) + 3 + (22 &divide; 31)\] = 1814,52

### <a name="example-2"></a>Esempio 2

L'importo annuale di un programma di fatturazione è $ 12.000. La data di inizio è il 1 agosto 2019 e la data di fine è il 31 dicembre 2019. La frequenza di fatturazione è annuale. L'importo proporzionale viene calcolato con le seguenti modalità, a seconda del metodo di calcolo:

- **Giornaliero**

    - *Numero di giorni* = *Data di fine* – *Data d'inizio* + 1 = 153 giorni
    - *Numero di giorni dell'anno* = 31 luglio 2020 – 1 agosto 2019 + 1 = 366 giorni
    - *Importo proporzionale* = 12.000 &times; (153 &divide; 366) = 5016,39

- **Mensile (mese intero)**

    - *Numero di mesi* = 5
    - *Mesi totali* = 12
    - *Importo proporzionale* = (12.000 &times; 5) &divide; 12 = 5.000

## <a name="reversing-a-period-billing"></a>Storno di una fatturazione del periodo

Per questo esempio, un programma di fatturazione ha una sola riga:

- La fatturazione viene effettuata mensilmente per 12 mesi da gennaio a dicembre.
- Le fatture sono state create per tutti i periodi fino ad aprile.

Vuoi stornare la fattura per il periodo di fatturazione di aprile.

Se non è stata ancora creata una fattura di vendita per il periodo di fatturazione di aprile, è possibile eliminare l'ordine di vendita. In questo caso, lo stato **Fatturato** per il dettaglio verrebbe rimosso. Tuttavia, poiché è stata creata una fattura per il periodo di fatturazione, lo stato **Fatturato** per il dettaglio non può essere cancellato. Pertanto, per stornare la fatturazione di aprile, è necessario creare una nota di credito di compensazione per la riga.

1. Crea una riga del programma per lo stesso articolo nella pagina **Tutti i programmi di fatturazione**.
2. Cambia il valore **Quantità** per l'articolo sul valore negativo della quantità originale.
3. Imposta il campo **Frequenza di fatturazione** su **Una volta**.
4. Aggiorna le date di inizio e fine in modo che corrispondano alle date della riga dei dettagli di fatturazione per la quale desideri creare una nota di credito. Per questo esempio, imposta la data di inizio su 1 aprile 2019 e la data di fine su 30 aprile 2019.
5. Salvare le modifiche.
6. Apri la pagina **Genera fattura** e crea l'ordine cliente con la nota di credito per il periodo specificato.
7. Facoltativo: registra la fattura.

Quando esamini le righe per il programma di fatturazione, noterai che la nuova riga ha un collegamento alla nota di credito. La riga originale conterrà ancora un collegamento alla fattura originale di aprile.

## <a name="split-item-group-examples"></a>Esempi di gruppi di articoli suddivisi

Per questo esempio, c'è la seguente configurazione:

- Nella pagina **Parametri di fatturazione ricorrente di contratti**, **Dividi per gruppo di articoli** è selezionato e il campo **Tipo di programma univoco** è impostato su **Cliente**.
- Sono stati creati tre gruppi di articoli: **PREFIX**, **DATAHUB**, e **SPP**.
- Il cliente US-001 ha più programmi di fatturazione in cui il gruppo di articoli è PREFIX o DATAHUB.
- Il cliente US-002 ha più programmi di fatturazione in cui il gruppo di articoli è PREFIX o SPP.

| Numero programmazione fatturazione | Cliente | Gruppo di articoli |
|---|---|---|
| SCH001 | US-001 | PREFIX |
| SCH002 | US-001 | DATAHUB |
| SCH003 | US-002 | PREFIX |
| SCH004 | US-002 | SPP |

Il cliente US-001 acquista un articolo di rinnovo che appartiene al gruppo di articoli PREFIX. Questa transazione è un nuovo ordine cliente.

| Numero ordine cliente | Cliente | Articolo principale | Articolo rinnovo | Gruppo di articoli rinnovo | Numero programmazione fatturazione |
|---|---|---|---|---|---|
| SO0001 | US-001 | D0001 | D0002 | PREFIX | SCH001 |

Quando la fattura per l'ordine cliente viene registrata, l'articolo di rinnovo viene aggiunto al programma di fatturazione esistente (SCH001) per il cliente. Questo programma di fatturazione utilizza il gruppo di articoli PREFIX. Tutti gli articoli di rinnovo che appartengono allo stesso gruppo di articoli vengono inseriti nello stesso programma di fatturazione.

**Intestazione**
 
| Numero programmazione fatturazione | Cliente | Gruppo di articoli |
|---|---|---| 
| SCH001 | US-001 | PREFIX |

**Riga**

| Numero programmazione fatturazione | Cliente | Gruppo di articoli |
|---|---|---|
| SCH001 | US-001 | D0002 |

Il cliente US-001 ora acquista un articolo di rinnovo che appartiene al gruppo di articoli SPP. Questa transazione è un nuovo ordine cliente.

| Numero ordine cliente | Cliente | Articolo principale | Articolo rinnovo | Gruppo di articoli rinnovo | Numero programmazione fatturazione |
|---|---|---|---|---|---|
| SO0002 | US-001 | D0003 | D0004 | SPP | |

Attualmente, il cliente US-001 non dispone di un programma di fatturazione che utilizza il gruppo di articoli SPP. Pertanto, viene creato un nuovo programma di fatturazione.

**Intestazione**

| Numero programmazione fatturazione| Cliente | Gruppo di articoli |
|---|---|---|
| SCH005 | US-001 | SPP |

**Riga**

| Numero programmazione fatturazione | Cliente | Gruppo di articoli |
|---|---|---|
| SCH005 | US-001 | D0004 |

### <a name="multiple-billing-schedules-for-the-same-end-user-and-customer"></a>Più programmi di fatturazione per lo stesso utente finale e cliente

Per questo esempio, c'è la seguente configurazione:

- Nella pagina **Parametri di fatturazione ricorrente di contratti**, **Dividi per gruppo di articoli** è selezionato e il campo **Tipo di programma univoco** è impostato su **Utente finale**.
- Nella pagina **Utenti finali** viene impostata la seguente relazione tra cliente e utente finale.

    | Conto cliente | Account utente finale |
    |---|---|
    | US-001 | US-221 |

Più programmi di fatturazione sono creati per la combinazione utente finale e cliente. Perché **Dividi per gruppo di articoli** è selezionato nella pagina **Parametri di fatturazione ricorrente di contratti** è possibile creare più programmi di fatturazione per la stessa relazione cliente e utente finale.

| Numero programmazione fatturazione | Cliente | Account utente finale | Gruppo di articoli intestazione |
|---|---|---|---|
| SCH005 | US-001 | US-221 | IG1 |
| SCH006 | US-001 | US-221 | IG2 |
| SCH007 | US-001 | US-221 | IG3 |

Nella pagina **Configurazione articolo** crea le relazioni tra articoli di supporto e rinnovo.

| Codice articolo | Relazione articolo | Articolo supporto | Articolo rinnovo | Gruppo di articoli rinnovo |
|---|---|---|---|---|
| Tabella | D001 | ITEM27 | D007 | IG1 |
| Tabella | D002 | ITEM28 | D005 | IG2 |
| Tabella | D003 | ITEM29 | D006 | IG3 |

Ora crea un ordine cliente per il cliente US-001. Questo ordine cliente contiene articoli dalla pagina **Configurazione articolo**. Quando crei l'ordine cliente, apri la pagina **Supporto e processo di rinnovo** e imposta il campo **Conto utente finale** e qualsiasi altra informazione richiesta per l'articolo di rinnovo.

Quando la fattura per la transazione viene creata e registrata, vengono creati diversi programmi di fatturazione per la combinazione cliente/utente finale e gruppo di articoli. È possibile assegnare più righe dello stesso ordine cliente allo stesso programma di fatturazione.

| Numero ordine cliente | Cliente | Account utente finale | Articolo principale | Articolo supporto | Articolo rinnovo | Numero programmazione fatturazione |
|---|---|---|---|---|---|---|
| SO0001 | US-001 | US-221 | D001 | ITEM27 | D007 | SCH005 |
| SO0001 | US-001 | US-221 | D002 | ITEM28 | D005 | SCH006 |
| SO0001 | US-001 | US-221 | D003 | ITEM29 | D006 | SCH005 |
