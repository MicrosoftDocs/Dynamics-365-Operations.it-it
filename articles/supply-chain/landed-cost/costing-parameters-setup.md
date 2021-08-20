---
title: Impostazione dei valori dei parametri di determinazione dei costi
description: Quando si imposta il modulo Costo sbarcato, è possibile definire diversi set di valori comuni che saranno disponibili quando si selezionano tipi specifici di valori dei parametri di determinazione dei costi in altre parti dell'app. In questo argomento viene descritto come impostare questi set di valori.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostTypeTable, ITMCostTypeGroup, ITMCostTransferGroup, ITMCostTemplateTable, ITMVolumetricDivisorTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: dada2f9a3ae13f41b7f63d1f0907002860d0717ff9d8c2453fc6f3ad123cbf78
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736745"
---
# <a name="costing-parameter-values-setup"></a>Impostazione dei valori dei parametri di determinazione dei costi

[!include [banner](../../includes/banner.md)]

Quando si imposta il modulo **Costo sbarcato**, è possibile definire diversi set di valori comuni e impostazioni correlate per valore. Questi valori saranno quindi disponibili quando si selezionano tipi specifici di valori dei parametri di determinazione dei costi in altre parti dell'app. In questo argomento viene descritto come impostare questi set di valori.

## <a name="set-up-cost-type-codes"></a>Impostare codici di tipo di costo

I codici di tipo di costo determinano il tipo di costo sostenuto quando le merci vengono sbarcate nel magazzino o i costi sbarcati del viaggio. Sebbene di solito aumentino il valore delle merci, possono anche essere utilizzati per accumulare importi nel libro mastro. Le rettifiche contabili vengono utilizzate quando un costo viene maturato nel tempo o durante una serie di viaggi e viene compensato in una singola transazione.

> [!NOTE]
> Se la tabella dei tipi di costo è condivisa tra persone giuridiche, il piano dei conti deve essere condiviso anche tra le persone giuridiche. In caso contrario, le transazioni di registrazione non funzioneranno correttamente.

Per impostare codici di tipo di costo, selezionare **Costo sbarcato \> Configurazione dei costi \> Codici tipo di costo**. È possibile utilizzare i pulsanti nel riquadro Azioni per creare nuovi codici di tipo di costo, modificare codici esistenti o eliminare un tipo di costo selezionato.

Nella seguente tabella sono descritti i campi disponibili per ogni codice di tipo di costo.

| Campo | Descrizione |
|---|---|
| Codice tipo di costo | Immettere un nome per il codice di tipo di costo. |
| Descrizione | Immettere una descrizione per il codice di tipo di costo. |
| Usa tasso spedizione | Imposta questa opzione su *Sì* se il tasso di cambio del viaggio (a volte indicato come tasso di gestione) deve essere utilizzato per calcolare il valore di questi costi. In questo caso, per convertire le fatture in valuta estera verrà utilizzato il tasso di spedizione al posto del tasso di cambio spot o definito standard. |
| Categoria di reporting | Questo campo stabilisce una categoria di report per il tipo di costo. I report possono essere stampati sia per categorie di report che per tipo di costo. |
| Tipo di addebito | Selezionare se il tipo di costo deve addebitare l'articolo, il conto CoGe o il fornitore. |
| Addebito | Se il campo **Tipo di addebito** è impostato su *Conto CoGe*, selezionare la descrizione della registrazione. |
| Conto in Dare | Se il campo **Tipo di addebito** è impostato su *Conto CoGe*, selezionare il conto CoGe da utilizzare. |
| Tipo di accredito | Selezionare se questo tipo di costo deve accreditare l'articolo, il conto CoGe o il fornitore. |
| Accredito | Se il campo **Tipo di accredito** è impostato su *Conto CoGe*, selezionare la descrizione della registrazione. |
| Conto in Avere | Se il campo **Tipo di accredito** è impostato su *Conto CoGe*, selezionare il conto CoGe da utilizzare. |
| Conto di compensazione | Selezionare il conto di compensazione per il tipo di costo. Si consiglia di specificare un conto di compensazione separato per tipo di costo per facilitare la riconciliazione. |
| Tipo di registrazione costo standard | Se si utilizza la determinazione dei costi standard, selezionare la descrizione della registrazione. |
| Conto scostamento costo standard | <p>Se utilizzi la determinazione dei costi standard, il conto specificato qui verrà utilizzato per registrare eventuali scostamenti. Questo conto utilizza la ripartizione dei costi sbarcati nella pagina **Prezzi articoli**. Questa ripartizione viene creata utilizzando la routine periodica per aggiornare i prezzi.</p><p>Ad esempio, il costo standard di un articolo è $15,00, il FOB è $13,00 e il trasporto è $2,00. Quando viene ricevuta la fattura per le scorte, l'articolo viene ricevuto a $15,00, ma si ha uno scostamento del prezzo standard di $2,00 per l'articolo, poiché il FOB effettivo è $13,00. Questo scostamento viene registrato nel conto scostamento costo standard impostato nel profilo di registrazione articolo. Poiché il trasporto stimato è $2,00, non vi è alcuno scostamento quando viene registrata la fattura delle scorte. Tuttavia, quando viene ricevuta la fattura per il trasporto, il trasporto è $2,50 per unità. Pertanto, lo scostamento di $0,50 viene registrato nel costo specificato. |
| Conto scostamento medio mobile | <p>Se utilizzi la determinazione dei costi media standard, il conto specificato qui verrà utilizzato per registrare eventuali scostamenti.</p><p>Ad esempio, il trasporto stimato è $2,00. Tuttavia, quando viene ricevuta la fattura per il trasporto, il trasporto è $2,50 per unità. Pertanto, è necessario registrare uno scostamento di $0,50.</p><p>Quando l'opzione **Registra rettifiche come scostamento** è impostata su *Sì* nella pagina **Parametri del costo sbarcato**, tutti gli scostamenti tra i costi di spedizione stimati ed effettivi verranno registrati nel conto scostamento medio mobile qui specificato. Quando l'opzione **Registra rettifiche come scostamento** è impostata su *No*, verrà utilizzata la funzionalità standard e lo scostamento verrà applicato all'inventario o al conto scostamento medio mobile specificato qui, a seconda delle scorte disponibili.</p> |
| Conto ratei di addebito | Selezionare il conto utilizzato per i ratei delle stime dei costi quando viene registrata la fattura di acquisto. Questo campo viene utilizzato solo quando l'opzione **Usa conto ratei di addebito del tipo di costo** è impostata su *Sì* nella Scheda dettaglio **Determinazione costi** della scheda **Generale** della pagina **Parametri del costo sbarcato**. |
| Conto di addebito | Selezionare il conto utilizzato per acquisire i costi di trasporto in entrata fatturati da un fornitore. L'importo viene registrato come addebito. Il conto di contropartita è il conto di variazione delle scorte. Questa registrazione viene utilizzata solo quando l'opzione **Registra nel conto di addebito nella contabilità generale** è impostata su *Sì* nella pagina **Parametri contabilità fornitori**. |
| Conto scostamento | Il conto che verrà utilizzato per compensare i ratei di addebito al momento della registrazione della fattura di acquisto. Questo campo viene utilizzato solo quando l'opzione **Usa conto ratei di addebito del tipo di costo** è impostata su *Sì* nella Scheda dettaglio **Determinazione costi** della scheda **Generale** della pagina **Parametri del costo sbarcato**. |

## <a name="vendor-cost-type-groups"></a>Gruppi di tipi di costo fornitore

I gruppi di tipi di costo fornitore aiutano a determinare il modo in cui gli addebiti dei *costi automatici* vengono rilevati e applicati a un viaggio. I fornitori che hanno costi di importazione simili sono collegati tra loro. Ad esempio, tutti i fornitori dei mercati emergenti pagano la stessa percentuale di dazio per lo stesso tipo di prodotto acquistato da un mercato consolidato.

È possibile gestire i gruppi di tipi di costo fornitore selezionando **Costo sbarcato \> Configurazione dei costi \> Gruppi di tipi di costo fornitore**. La pagina **Gruppi di tipi di costo fornitore** fornisce una griglia che elenca tutti i gruppi di tipi di costo fornitore esistenti. È possibile utilizzare i pulsanti nel riquadro Azioni per aggiungere, rimuovere e modificare righe nella griglia.

Nella seguente tabella sono descritti i campi disponibili in ogni riga della griglia.

| Campo | Descrizione |
|---|---|
| Gruppi di tipi di costo fornitore | Immettere un nome univoco per il gruppo di tipi di costo fornitore (ad esempio *Mercati emergenti*). |
| Descrizione | Immettere una descrizione del gruppo di tipi di costo fornitore. Questa descrizione può fornire dettagli sul livello o sul tipo di addebito associato al gruppo di fornitori. |

## <a name="item-cost-type-groups"></a>Gruppi di tipi di costo articoli

I gruppi di tipi di costo articoli aiutano a determinare il modo in cui gli addebiti dei *costi automatici* vengono rilevate e applicate a un viaggio. Articoli simili sono collegati tra loro. Ad esempio, tutti gli articoli con un'aliquota di dazio del 5% potrebbero appartenere a uno specifico gruppo di tipi di costo.

È possibile gestire i gruppi di tipi di costo articoli selezionando **Costo sbarcato \> Configurazione dei costi \> Gruppi di tipi di costo articoli**. La pagina **Gruppi di tipi di costo articoli** fornisce una griglia che elenca tutti i gruppi di tipi di costo articoli esistenti. È possibile utilizzare i pulsanti nel riquadro Azioni per aggiungere, rimuovere e modificare righe nella griglia.

Nella seguente tabella sono descritti i campi disponibili in ogni riga della griglia.

| Campo | Descrizione |
|---|---|
| Gruppi di tipi di costo articoli | Immettere un nome univoco per il gruppo di tipi di costo articoli (ad esempio *Dazio 5%*). |
| Descrizione | Immettere una descrizione del gruppo di tipi di costo articoli. Questa descrizione può fornire dettagli sul livello o sul tipo di addebito associato al gruppo di articoli. |

> [!NOTE]
> Il tipo di costo articoli è collegato all'articolo tramite il campo **Gruppo di tipi di costo** nella Scheda dettaglio **Acquisto** della pagina **Prodotto rilasciato** dell'articolo.

## <a name="transfer-order-cost-type-groups"></a>Gruppi di tipi di costo ordine di trasferimento

I gruppi di tipi di costo ordini di trasferimento aiutano a determinare il modo in cui gli addebiti dei *costi automatici* vengono trovati. Articoli simili sono collegati tra loro. Ad esempio, tutti gli articoli con un'aliquota di dazio del 7% potrebbero appartenere a uno specifico gruppo di tipi di costo.

È possibile gestire gruppi di tipi di costo ordine di trasferimento selezionando **Costo sbarcato \> Configurazione dei costi \> Gruppi di tipi di costo ordine di trasferimento**. La pagina **Gruppi di tipi di costo ordine di trasferimento** fornisce una griglia che elenca tutti i gruppi di tipi di costo ordine di trasferimento esistenti. È possibile utilizzare i pulsanti nel riquadro Azioni per aggiungere, rimuovere e modificare righe nella griglia.

Nella seguente tabella sono descritte le impostazioni disponibili in ogni riga della griglia.

| Campo | Descrizione |
|---|---|
| Gruppi di tipi di costo ordine di trasferimento | Immettere un nome univoco per il gruppo di tipi di costo ordine di trasferimento (ad esempio *Dazio 7%*). |
| Descrizione | Immettere una descrizione del gruppo di tipi di costo ordine di trasferimento. Questa descrizione può fornire dettagli sul livello o sul tipo di addebito associato al gruppo del tipo di costi ordine di trasferimento. |

> [!NOTE]
> Il tipo di costo ordine di trasferimento è collegato all'articolo tramite il campo **Gruppo di tipi di costo ordine di trasferimento** nella Scheda dettaglio **Acquisto** della pagina **Prodotto rilasciato** dell'articolo.

## <a name="cost-templates"></a>Modelli dei costi

I modelli di costo sono utilizzati per impostare valori predefiniti per le impostazioni che gli utenti che ricevono la stima dei costi potrebbero non conoscere. I modelli di costo possono aiutare a ridurre la complessità del processo di stima riducendo al minimo le selezioni che gli utenti devono effettuare per ottenere una stima accurata.

Per utilizzare i modelli di costo, selezionare **Costo sbarcato \> Configurazione dei costi \> Modelli dei costi**. Nella pagina **Modelli di costo**, il riquadro elenco a sinistra mostra tutti i modelli di costo correnti. È possibile utilizzare i pulsanti del riquadro Azioni per aggiungere, rimuovere e modificare i modelli.

Nella seguente tabella sono descritte le impostazioni disponibili per ogni modello.

| Campo | Descrizione |
|---|---|
| Modello dei costi | Immettere un nome univoco per il modello di costo. Il nome in genere descrive il fattore o il moltiplicatore di costo per il modello. |
| Descrizione | Immettere una descrizione del modello di costo. |
| Società di spedizione | Selezionare il conto fornitore della società di spedizione da associare al modello di costo. |
| Modalità di consegna | Selezionare la modalità di consegna che il modello di costo deve utilizzare quando viene calcolato il costo stimato di un articolo. Questo campo consentirà di determinare i costi automatici associati alle merci nella stima dei costi. |
| Tipo di contenitore di spedizione | Selezionare il tipo di contenitore di spedizione da associare al modello di costo. Questo campo consentirà di determinare i costi automatici associati alle merci nella stima dei costi. |
| Broker doganale | Selezionare il broker doganale (fornitore) da associare al modello di costo. Questo campo consentirà di determinare i costi automatici associati alla stima dei costi. |
| Fattore | Immettere un fattore da applicare alla stima del costo finale delle merci. Ad esempio, per aggiungere il 10 percento alla stima dei costi calcolata, immettere *1,10*. |

## <a name="volumetric-divisors"></a>Divisori volumetrici

I divisori volumetrici vengono utilizzati per calcolare il peso volumetrico. Ogni società di spedizione/trasporto formula i propri divisori volumetrici. Inoltre, i divisori di una società in genere variano a seconda della modalità di consegna. Ad esempio, per il trasporto aereo e per quello marittimo i divisori sono molto diversi. Una società può anche rendere le proprie regole più complesse, a seconda del luogo da cui effettua le spedizioni.

Ad esempio, un pacco spedito per via aerea ha un volume di 3 metri cubi (m³). La società addebita in base al peso volumetrico e applica un divisore volumetrico di 6. Questo divisore viene moltiplicato per il volume per determinare il peso volumetrico. Pertanto, il peso volumetrico per questo esempio è 3 × 6 = 18 chilogrammi (kg).

Per impostare divisori volumetrici, selezionare **Costo sbarcato \> Configurazione dei costi \> Divisori volumetrici**. La pagina **Divisori volumetrici** fornisce una griglia che elenca tutti i divisori volumetrici esistenti. È possibile utilizzare i pulsanti nel riquadro Azioni per aggiungere, rimuovere e modificare righe nella griglia.

Nella seguente tabella sono descritti i campi disponibili in ogni riga della griglia.

| Campo | Descrizione |
|---|---|
| Società di spedizione | Selezionare il conto fornitore della società di spedizione associata al divisore volumetrico. |
| Codice tipo di costo | Selezionare il codice di tipo di costo associato al divisore volumetrico. Utilizzare questo campo per inserire i tipi di costo nei bucket di report. I report possono essere stampati sia per categorie di report che per tipo di costo. |
| Porto di origine | Selezionare il porto di origine a cui si applica il divisore volumetrico. |
| Divisore volumetrico | Immettere il valore del divisore volumetrico che si applica alla riga. Il valore immesso verrà *moltiplicato* per il volume di ogni pacco per determinare il peso volumetrico di quel pacco. |
