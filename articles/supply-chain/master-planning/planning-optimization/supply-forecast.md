---
title: Pianificazione generale con previsioni dell'offerta
description: Questo articolo descrive come vengono considerate le previsioni dell'offerta durante la pianificazione generale.
author: t-benebo
ms.date: 09/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-21
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: dc83d10851958ec67166cb7e40cfd84dceae6651
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690084"
---
# <a name="master-planning-with-supply-forecasts"></a>Pianificazione generale con previsioni dell'offerta

[!include [banner](../../includes/banner.md)]

Le previsioni dell'offerta consentono di specificare la fornitura di cui prevedi di aver bisogno in un periodo futuro. In genere, la stima si baserà sulla cronologia delle vendite dell'anno precedente e quindi si utilizzerà la previsione a fini di budget. Puoi anche configurare i tuoi piani generali in modo da considerare le previsioni durante la pianificazione.

## <a name="set-up-a-master-plan-to-consider-supply-forecasts"></a>Configurare un piano generale per considerare le previsione dell'offerta

È possibile specificare se ogni piano generale deve considerare le previsioni durante l'esecuzione. Utilizzare la procedura seguente per impostare le opzioni di previsione per ciascun piano.

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.
1. Selezionare un piano generale esistente nel riquadro elenco oppure selezionare **Nuovo** nel riquadro Azioni per crearne uno.
1. Nella scheda dettaglio **Generale**, impostare i seguenti campi:

    - **Modello di previsione** – Selezionare il modello che contiene le previsioni dell'offerta e/o della domanda che dovrebbero essere considerate dal piano generale.
    - **Includi previsione dell'offerta** - Impostare questa opzione su *Sì* se il piano generale deve considerare le previsioni dell'offerta.
    - **Includi previsione della domanda** - Impostare questa opzione su *Sì* se il piano generale deve considerare le previsioni della domanda. Sebbene questa impostazione sia indipendente dall'impostazione **Includi previsione dell'offerta**, alcune delle altre impostazioni nella pagina si applicano sia alle previsioni dell'offerta che alle previsioni della domanda. Per ulteriori informazioni sulla pianificazione che tiene conto delle previsioni della domanda, vedere [Pianificazione generale con previsioni della domanda](demand-forecast.md).
    - **Metodo utilizzato per ridurre i requisiti di previsione** - Selezionare il metodo da utilizzare per ridurre i requisiti di previsione durante la pianificazione generale:

        - *Nessuno* – I requisiti di previsione non verranno ridotti durante la pianificazione generale.
        - *Percentuale - chiave di riduzione* – I requisiti di previsione verranno ridotti in base alle percentuali e ai periodi di tempo definiti nella chiave di riduzione.
        - *Transazioni - chiave di riduzione* – I requisiti di previsione verranno ridotti in base alle transazioni effettuate durante i periodi di tempo definiti nella chiave di riduzione.
        - *Transazioni - periodo dinamico* – I requisiti di previsione verranno ridotti in base alle transazioni di ordine effettive effettuate durante il periodo dinamico. Il periodo dinamico copre le date di previsione correnti e termina all'inizio della previsione successiva. Il metodo *Transazioni – periodo dinamico* non utilizza o richiede una chiave di riduzione e, quando utilizzato, si applicano le seguenti condizioni:

            - Se la previsione viene ridotta completamente, i requisiti per la previsione corrente diventano 0 (zero).
            - Se non vi è alcuna previsione futura, vengono ridotti i requisiti di previsione dall'ultima previsione immessa.
            - Gli intervalli temporali vengono inclusi nel calcolo della riduzione previsionale.
            - I giorni di positività vengono inclusi nel calcolo della riduzione previsionale.
            - Se le transazioni di ordini effettivi superano i requisiti previsti, le transazioni rimanenti non vengono inoltrate al periodo previsionale successivo.

        > [!NOTE]
        > L'impostazione **Metodo utilizzato per ridurre i requisiti di previsione** si applica anche alle previsioni della domanda se le hai abilitate per il piano generale e ha un impatto simile su di esse. Per ulteriori informazioni, vedere [Pianificazione generale con previsioni della domanda](demand-forecast.md).

## <a name="set-reduction-options-for-coverage-groups"></a>Impostare le opzioni di riduzione per i gruppi di copertura

Per impostare le opzioni che controllano il modo in cui un gruppo di copertura ridurrà i propri requisiti di previsione per i piani generali che utilizzano la riduzione basata sulle transazioni, attenersi alla seguente procedura.

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Gruppi di copertura**.
1. Selezionare un gruppo di copertura esistente nel riquadro dell'elenco oppure selezionare **Nuovo** nel riquadro azioni per crearne uno nuovo.
1. Nella Scheda dettagli **Altro**, nel campo **Riduci previsione per**, specificare la modalità di riduzione dei requisiti di previsione della domanda per gli elementi nel gruppo di copertura, per i piani generali in cui il campo **Metodo utilizzato per ridurre i requisiti di previsione** è impostato su *Transazioni - chiave di riduzione* o *Transazioni - periodo dinamico*. Selezionare uno dei seguenti valori:

    - *Tutte le transazioni* - Tutte le transazioni devono ridurre la previsione.
    - *Ordini* - Solo gli ordini dello stesso tipo devono ridurre la previsione.

    Ad esempio, le impostazioni dell'ordine predefinite per un articolo indicano che deve essere prodotto. È presente una riga di previsione dell'offerta per una quantità di 50 ed è presente un ordine fornitore esistente per una quantità di 20. Se il campo **Riduci previsione per** è impostato su *Ordini*, verrà creato un ordine di produzione pianificato per una quantità di 50. Se è impostato su *Tutte le transazioni*, l'ordine di produzione pianificato verrà ridotto a una quantità di 30.

    Questa impostazione si applica anche alla riduzione delle previsioni della domanda. Per ulteriori informazioni, vedere [Pianificazione generale con previsioni della domanda](demand-forecast.md).

## <a name="enter-a-supply-forecast-for-a-product"></a>Immettere una previsione dell'offerta per un prodotto

Per immettere una previsione dell'offerta , seguire questi passaggi.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Selezionare il prodotto per cui si desidera immettere una previsione.
1. Nella scheda **Piano** del riquadro Azioni selezionare **Previsione dell'offerta**.
1. Nel riquadro Azione della pagina **Previsione dell'offerta**, selezionare **Nuovo** per aggiungere una previsione alla griglia.
1. Immettere le informazioni sulla nuova riga come richiesto per specificare la previsione.

## <a name="plan-for-an-item-with-supply-forecast-lines"></a>Pianificare un articolo con righe di previsione dell'offerta

Quando si esegue un piano generale che include un articolo per il quale esiste una previsione dell'offerta, il sistema crea un ordine fornitore per le righe di offerta che sono state immesse. Le impostazioni dell'ordine predefinite per l'articolo vengono rispettate. Se tali impostazioni dell'ordine predefinite specificano un valore **Tipo di ordine predefinito** di *Ordine fornitore* e nessun conto fornitore è specificato nella riga di previsione dell'offerta, il sistema utilizzerà il fornitore predefinito per l'articolo.

## <a name="check-whether-a-planned-order-is-a-supply-forecast-order"></a>Verificare se un ordine pianificato è un ordine di previsione dell'offerta

Utilizzare la procedura seguente per sapere se un ordine pianificato è stato creato a seguito di una previsione dell'offerta.

1. Andare a **Pianificazione generale \> Pianificazione generale \> Ordini pianificati**.
1. Aprire l'ordine pianificato che si desidera ispezionare.
1. Nella Scheda dettaglio **Generale**, osservare il valore del campo **Previsione dell'offerta**. Se l'ordine è stato creato per coprire una previsione dell'offerta, questo campo sarà impostato su *Sì*.

## <a name="examples-of-master-planning-with-supply-forecasts"></a>Esempi di pianificazione generale con previsioni dell'offerta

Questa sezione fornisce diversi esempi che mostrano come la previsione dell'offerta influisca sulla pianificazione generale.

### <a name="example-1-supply-forecast-for-an-item"></a>Esempio 1: previsione dell'offerta per un articolo

Hai un articolo in cui il tipo di ordine predefinito è *Ordine fornitore* e il fornitore predefinito è *US-002*. Ha la seguente riga di previsione dell'offerta.

| Modello    | Data     | Account fornitore | Gruppo di fornitori | Quantity | Unità | Sito | Magazzino |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                |              | 35       | Cadauno   | 1    | 11        |

Quando si esegue la pianificazione generale, verrà creato un ordine fornitore pianificato per *35 ea* dal fornitore *US-002*.

### <a name="example-2-several-supply-forecast-lines-with-and-without-a-vendor"></a>Esempio 2: diverse righe di previsione dell'offerta, con e senza un fornitore

Hai un articolo in cui il tipo di ordine predefinito è *Ordine fornitore* e il fornitore predefinito è *US-002*. Ha le seguenti righe di previsione dell'offerta.

| Modello    | Data     | Account fornitore | Gruppo di fornitori | Quantity | Unità | Sito | Magazzino |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                |              | 35       | Cadauno   | 1    | 11        |
| CurrentF | 10/10/22 | US-101         |              | 25       | Cadauno   | 1    | 11        |

In questo caso, il sistema tratta la riga che non specifica un fornitore come previsione generica e presume che la riga che specifica un fornitore debba essere sottratta dalla previsione generica. Pertanto, la pianificazione generale crea i seguenti ordini fornitore pianificati per l'articolo:

- Un ordine fornitore pianificato per una quantità di *25 ea* dal fornitore *US-101* (vengono utilizzati il fornitore e la quantità specificati nella riga di previsione).
- Un ordine fornitore pianificato per una quantità di *10 ea* dal fornitore *US-002* (poiché non è stato specificato alcun fornitore nell'altra riga di previsione, viene utilizzato il fornitore predefinito e la quantità di questa riga di previsione viene ridotta della quantità della riga di previsione specifica del fornitore).

### <a name="example-3-plans-that-use-the-transactions---dynamic-period-reduction-method-in-a-single-forecast-period"></a>Esempio 3: piani che utilizzano il metodo di riduzione Transazioni - periodo dinamico in un unico periodo di previsione

Per i piani generali che utilizzano *Transazioni - periodo dinamico* come metodo di riduzione delle previsioni, la pianificazione generale ridurrà le quantità previste se esistono transazioni esistenti che corrispondono a tali caratteristiche dell'offerta.

Ad esempio, hai un articolo in cui il tipo di ordine predefinito è *Ordine fornitore*. Ha la seguente riga di previsione dell'offerta.

| Modello    | Data     | Account fornitore | Gruppo di fornitori | Quantity | Unità | Sito | Magazzino |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | Cadauno   | 1    | 11        |

Poiché esiste una sola riga di previsione dell'offerta, esiste un solo periodo di previsione.

Quando si esegue un piano generale configurato per utilizzare *Transazioni – periodo dinamico* come metodo di riduzione, può verificarsi uno dei seguenti risultati:

- Se esiste un ordine fornitore per il fornitore *US-101* e una quantità di *10 ea* e il campo **Previsione dell'offerta** è impostato su *Sì*, la pianificazione generale crea un nuovo ordine fornitore pianificato per la quantità rimanente di *10 ea*. La riga di previsione viene ridotta, poiché il fornitore corrisponde all'ordine fornitore esistente.
- Se esiste un ordine fornitore per il fornitore *US-102*, sito *1*, magazzino *11* e una quantità di *10 ea* e il campo **Previsione dell'offerta** è impostato su *Sì*, la pianificazione generale crea un nuovo ordine fornitore pianificato per la quantità intera di *25 ea*. La riga di previsione non può essere ridotta perché ha un fornitore diverso dall'ordine fornitore esistente.

> [!NOTE]
> Questa situazione può verificarsi per gli ordini fornitore pianificati, perché ad essi è associato un fornitore. Tuttavia, per gli ordini di trasferimento e gli ordini di produzione, gli importi della previsione dell'offerta verranno sempre ridotti degli ordini esistenti, poiché per questi tipi di ordini non è specificato alcun fornitore.

### <a name="example-4-plans-that-use-the-transactions---dynamic-period-reduction-method-over-several-forecast-periods"></a>Esempio 4: piani che utilizzano il metodo di riduzione Transazioni - periodo dinamico per diversi periodi di previsione

Hai un articolo in cui il tipo di ordine predefinito è *Ordine fornitore*. Ha le seguenti righe di previsione dell'offerta.

| Modello    | Data     | Account fornitore | Gruppo di fornitori | Quantity | Unità | Sito | Magazzino |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | Cadauno   | 1    | 11        |
| CurrentF | 10/15/22 | US-101         |              | 25       | Cadauno   | 1    | 11        |

In questo esempio sono presenti due righe di previsione, ognuna delle quali ha una data diversa. Pertanto, le date stabiliscono i confini dei periodi di previsione. Il primo periodo va dal 10 ottobre al 14 ottobre 2022 (10/10/22–14/10/22). Il secondo è dal 15 ottobre 2022 (15/10/22) in poi.

Esiste un ordine fornitore esistente per il fornitore *US-101*, una quantità di *10 ea*, e la data *12/10/22* (12 ottobre 2022). Quando si esegue un piano generale configurato per utilizzare *Transazioni – periodo dinamico* come metodo di riduzione, verranno creati gli ordini seguenti:

- Un ordine pianificato per una quantità di *15 ea* e la data *10/10/22* (la quantità viene ridotta dell'ordine fornitore esistente datato durante lo stesso periodo di previsione).
- Un ordine pianificato per una quantità di *25 ea* e la data *15/10/22* (la quantità è la quantità intera della previsione).

### <a name="example-5-plans-that-use-no-reduction"></a>Esempio 5: piani che non utilizzano riduzioni

Quando si esegue un piano in cui il metodo di riduzione delle previsioni è *Nessuno*, la pianificazione generale crea sempre l'offerta pianificata per tutte le righe di previsione dell'offerta. Dopo che l'offerta pianificata è stata approvata, ridurrà gli ordini pianificati futuri. Tuttavia, gli ordini fornitore non ridurranno le righe di previsione dell'offerta.

Ad esempio, hai un articolo in cui il tipo di ordine predefinito è *Ordine fornitore*. Ha la seguente riga di previsione dell'offerta.

| Modello    | Data     | Account fornitore | Gruppo di fornitori | Quantity | Unità | Sito | Magazzino |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | Cadauno   | 1    | 11        |

Esiste un ordine fornitore esistente per il fornitore *US-101*, sito *1*, magazzino *11*, una quantità di *25 ea*, e la data *10/10/22*. 

Quando si esegue un piano generale configurato per utilizzare *Nessuno* come metodo di riduzione, verrà creato un ordine fornitore pianificato per il fornitore *US-101*, sito *1*, magazzino *11*, una quantità di *25 ea* e la data *10/10/22*. In altre parole, l'ordine fornitore esistente non verrà ridotto, poiché il metodo di riduzione della previsione è *Nessuno*.

È ora possibile modificare l'ordine fornitore pianificato creato dopo l'ultima esecuzione di pianificazione e modificare la quantità in *15 ea*. È possibile quindi approvare l'ordine. La volta successiva che si esegue il piano generale, verrà creato un ordine fornitore pianificato per il fornitore *US-101*, sito *1*, magazzino *11*, una quantità di *10 ea* e la data *10/10/22*. Questa volta, la quantità verrà ridotta per riflettere la quantità dell'ordine approvato esistente dall'esecuzione della pianificazione precedente.

## <a name="differences-between-planning-optimization-and-the-built-in-planning-engine"></a>Differenze tra Ottimizzazione pianificazione e il motore di pianificazione integrato

Le previsioni dell'offerta funzionano in modo leggermente differente, a seconda del motore di pianificazione in uso (pianificazione generale integrata o Ottimizzazione pianificazione). Questa sezione descrive le differenze.

### <a name="vendor-groups"></a>Gruppi di fornitori

Quando si aggiunge una riga di previsione, è possibile specificare un fornitore e un gruppo di fornitori. Nel motore di pianificazione integrato, gli ordini pianificati creati vengono raggruppati in base alla combinazione dei valori del fornitore e del gruppo di fornitori. In Ottimizzazione pianificazione, gli ordini pianificati sono raggruppati per fornitore.

La tabella seguente fornisce alcuni esempi di righe di previsione dell'offerta per un articolo.

| Modello    | Data     | Account fornitore | Gruppo di fornitori | Quantity | Unità | Sito | Magazzino |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                | VendorGroupA | 5        | Cadauno   | 1    | 11        |
| CurrentF | 10/10/22 |                | VendorGroupA | 6        | Cadauno   | 1    | 11        |
| CurrentF | 10/10/22 |                |              | 7        | Cadauno   | 1    | 11        |

Il fornitore *VendorA* è il fornitore predefinito per il gruppo di fornitori *VendorGroupA*. È inoltre il fornitore predefinito per l'articolo.

Il motore di pianificazione integrato crea i seguenti ordini:

- Un ordine fornitore pianificato per il fornitore *VendorA*, gruppo di fornitori *VendorGroupA* e una quantità di *11*
- Un ordine fornitore pianificato per il fornitore *VendorA* e una quantità di *7*

Ottimizzazione pianificazione crea un solo ordine:

- Un ordine fornitore pianificato per il fornitore *VendorA*, gruppo di fornitori *VendorGroupA* e una quantità di *18*

### <a name="reduction-of-general-forecasts-by-more-specific-forecasts"></a>Riduzione delle previsioni generali in previsioni più specifiche

Nel motore di pianificazione generale integrato, il risultato è imprevedibile se alcune previsioni hanno un fornitore ma altre no.

In Ottimizzazione pianificazione, le previsioni generali vengono sempre ridotte di previsioni più specifiche, come mostra l'esempio seguente.

La tabella seguente fornisce alcuni esempi di righe di previsione dell'offerta per un articolo.

| Data       | Quantity | Fornitore   | Gruppo di fornitori  |
|------------|----------|----------|---------------|
| 11/02/2022 | 5.00     | Vendor-A | VendorGroup-A |
| 11/02/2022 | 6,00     | Vendor-A | VendorGroup-A |
| 11/02/2022 | 15.00    |          |               |

La previsione generale (per 15,00 pezzi) è ridotta delle previsioni più specifiche (per 5,00 + 6,00 = 11,00 pezzi). Il resto è assegnato al fornitore predefinito. Nella seguente tabella vengono illustrati gli ordini pianificati.

| Data       | Quantity | Fornitore   | Gruppo di fornitori  |
|------------|----------|----------|---------------|
| 11/02/2022 | 11.00    | Vendor-A | VendorGroup-A |
| 11/02/2022 | 4.00     | Vendor-A | VendorGroup-A |

### <a name="respect-for-default-order-settings-when-planned-orders-are-generated"></a>Rispettare le impostazioni dell'ordine predefinite quando vengono generati gli ordini pianificati

Ciascun articolo può avere impostazioni dell'ordine predefinite, ad esempio una quantità minima dell'ordine fornitore. Il motore di pianificazione integrato ignora queste impostazioni e quindi converte le previsioni in ordini pianificati con la stessa quantità. Ottimizzazione pianificazione rispetta queste impostazioni quando gli ordini pianificati vengono generati dalle previsioni dell'offerta. 

### <a name="aggregation-of-planned-orders-as-a-result-of-reduction-by-approved-orders"></a>Aggregazione degli ordini pianificati a seguito della riduzione degli ordini approvati

Il motore di pianificazione generale integrato presuppone che un solo ordine ridurrà la previsione dell'offerta esistente. Pertanto, se più ordini corrispondono a una riga di previsione dell'offerta, solo il primo ordine la ridurrà. In Ottimizzazione pianificazione, tutti gli ordini che corrispondono alla riga di previsione dell'offerta la ridurranno.

### <a name="reduction-of-forecasts-by-matching-vendors-only"></a>Riduzione delle previsioni con corrispondenza solo tra fornitori

Quando il motore di pianificazione generale integrato riduce una previsione in base agli ordini fornitore rilasciati esistenti, non garantisce che il fornitore nell'ordine fornitore corrisponda al fornitore della previsione. Ottimizzazione pianificazione riduce le previsioni solo in base agli ordini fornitore che hanno un valore corrispondente nel campo fornitore.

Per gli ordini di trasferimento e di produzione, il campo fornitore viene sempre ignorato, poiché non è rilevante per quei tipi di ordine.

### <a name="reduction-of-forecasts-by-transfer-orders"></a>Riduzione delle previsioni per ordini di trasferimento

Se il tipo di ordine predefinito per un articolo è *Trasferimento*, le previsioni possono essere ridotte solo in base a ordini di trasferimento pianificati esistenti. Tuttavia, per gli ordini di produzione e gli ordini fornitore, solo gli ordini rilasciati riducono la previsione dell'offerta.

Il motore di pianificazione integrato riduce per tutti gli stati degli ordini di trasferimento, mentre Ottimizzazione pianificazione riduce le previsioni solo in base agli ordini di trasferimento che si trovano nello stato *Rilasciato*.
