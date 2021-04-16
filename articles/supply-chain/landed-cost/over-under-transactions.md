---
title: Transazioni in eccesso/in difetto
description: Questo argomento fornisce informazioni che consentono di impostare i dettagli dei criteri relativi alle transazioni in eccesso/in difetto, di modo che il sistema possa determinare come gestire l'elaborazione in eccesso e in difetto delle merci al momento del ricevimento.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMOverUnderTrans, ITMOverUnderToleranceTable, ITMOverUnderReasonTable, ITMOverUnderToleranceGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: c7e75e39877b36e482dd4aaa5cc7c8f84d57d81b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833739"
---
# <a name="overunder-transactions"></a>Transazioni in eccesso/in difetto

[!include [banner](../../includes/banner.md)]

Quando gli ordini di un viaggio vengono elaborati, il sistema prevede che la quantità degli articoli ricevuta nel magazzino di destinazione finale per il consumo corrisponda alla quantità specificata nelle righe di ordine fornitore associate al viaggio. Tuttavia, poiché la quantità esatta nelle righe di ordine fornitore non viene sempre ricevuta in magazzino, il modulo **Costo sbarcato** definisce un insieme di regole che vengono utilizzate per gestire il ricevimento in eccesso e in difetto di merci. Queste regole sono particolarmente importanti poiché l'ordine fornitore originale è stato fatturato e non può più essere modificato. Mediante la configurazione dei dettagli dei criteri relativi alle transazioni in eccesso/in difetto, il sistema determina il modo in cui gestire l'elaborazione in eccesso e in difetto delle merci al momento del ricevimento. È anche possibile gestire manualmente le scorte in eccesso e in difetto utilizzando la, pagina **Transazioni in eccesso/in difetto**.

## <a name="overunder-tolerances"></a>Tolleranze eccesso/difetto

Si impostano le tolleranze di consegna in eccesso e in difetto per specificare le quantità o i volumi in eccesso e in difetto che possono essere elaborati in un viaggio senza causare un errore. Se il ricevimento della riga di viaggio non rientra in queste tolleranze, deve essere modificato e risolto prima che la riga di viaggio possa essere chiusa per ulteriori elaborazioni.

Per configurare le tolleranze, selezionare **Costo sbarcato \> Configurazione eccesso/difetto \> Tolleranze eccesso/difetto** dove è possibile visualizzare, modificare, aggiungere e rimuovere record di tolleranza. Nella seguente tabella sono descritti i campi disponibili per ogni record.

| Campo | Descrizione |
|---|---|
| Codice conto | <p>Definire l'ambito dei fornitori a cui si applica la tolleranza selezionando uno dei seguenti valori:</p><ul><li>**Tabella** - La tolleranza eccesso/difetto si applica solo al fornitore selezionato per la riga.</li><li>**Gruppo** - La tolleranza eccesso/difetto si applica a tutti i fornitori nel gruppo di tolleranze di fornitori selezionato per la riga.</li><li>**Tutti** - La tolleranza eccesso/difetto si applica a tutti i fornitori.</li></ul> |
| Relazione conto | Selezionare il fornitore o il gruppo di fornitori a cui si applica la tolleranza eccesso/difetto, a seconda del valore selezionato nel campo **Codice conto**. |
| Codice articolo | <p>Definire l'ambito degli articoli a cui si applica la tolleranza selezionando uno dei seguenti valori:</p><ul><li>**Tabella** - La tolleranza eccesso/difetto si applica solo all'articolo selezionato per la riga.</li><li>**Gruppo** - La tolleranza eccesso/difetto si applica a tutti gli articoli nel gruppo di tolleranze di articoli selezionato per la riga.</li><li>**Tutti** - La tolleranza eccesso/difetto si applica a tutti gli articoli.</li></ul> |
| Relazione articolo | Selezionare l'articolo o il gruppo di articoli a cui si applica la tolleranza eccesso/difetto, a seconda del valore selezionato nel campo **Codice articolo**. |
| Tolleranza importo | Immettere la tolleranza dell'importo da applicare a un intero ordine fornitore. |
| Tolleranza in percentuale | Immettere la tolleranza in percentuale da applicare a una singola riga dell'ordine fornitore. |

## <a name="overunder-reasons"></a>Motivi eccesso/difetto

Quando una quantità in eccesso o in difetto è associata a una riga di viaggio ricevuta, potrebbe essere necessario identificare il motivo della quantità in eccesso o in difetto. In questo caso, è possibile selezionare il motivo della consegna in eccesso o in difetto nella riga di ricevimento quando le merci vengono ricevute.

Per impostare i motivi di consegna in eccesso e in difetto, selezionare **Costo sbarcato \> Configurazione eccesso/difetto \> Motivi eccesso/difetto** dove è possibile visualizzare, modificare, aggiungere e rimuovere i motivi di consegna in eccesso e in difetto. Nella seguente tabella vengono descritti i campi disponibili per ogni motivo.

| Campo | Descrizione |
|---|---|
| Motivo eccesso/difetto | Immettere un nome univoco per il motivo della transazione ricevimento in eccesso o in difetto. |
| Descrizione | Immettere una descrizione del motivo di eccesso/difetto. |
| Movimento | Selezionare il giornale di registrazione movimenti associato al motivo di eccesso/difetto. Questo campo elenca tutti i giornali di registrazioni disponibili a cui un tipo di giornale di registrazione *Movimento* è associato nella pagina **Nomi giornale di registrazione magazzino** (**Gestione scorte \> Impostazioni \> Nomi giornale di registrazione \> Inventario**). |

## <a name="item-overunder-tolerance-groups"></a>Gruppi di tolleranza eccesso/difetto articoli

Gli articoli che hanno tolleranze simili possono essere raggruppati. In questo modo, è possibile impostare la tolleranza eccesso/difetto per tutti gli articoli in quel gruppo contemporaneamente.

Per configurare gruppi con tolleranza eccesso/difetto di articoli, selezionare **Costo sbarcato \> Configurazione eccesso/difetto \> Gruppi di tolleranza eccesso/difetto articoli** dove è possibile visualizzare, modificare, aggiungere e rimuovere record di gruppi di tolleranza eccessodifetto. Nella seguente tabella sono descritti i campi disponibili per ogni record.

| Campo | Descrizione |
|---|---|
| Gruppo di tolleranza eccesso/difetto | Immettere un nome univoco per il gruppo. Scegliere un nome che descriva la tolleranza, ad esempio *1% Var*. |
| Descrizione | Immettere una descrizione del gruppo. |

## <a name="vendor-overunder-tolerance-groups"></a>Gruppi di tolleranza eccesso/difetto fornitore

È possibile raggruppare i fornitori che effettuano regolarmente consegne in eccesso o in difetto. È quindi possibile impostare la tolleranza eccesso/difetto per gruppo.

Per configurare i gruppi di tolleranza eccesso/difetto di fornitori, selezionare **Costo sbarcato \> Configurazione eccesso/difetto \> Gruppi di tolleranza eccesso/difetto fornitore**. dove è possibile visualizzare, modificare, aggiungere e rimuovere record di gruppi di tolleranza eccessodifetto. Nella seguente tabella sono descritti i campi disponibili per ogni record.

| Campo | Descrizione |
|---|---|
| Gruppi eccesso/difetto | Immettere un nome univoco per il gruppo. Scegliere un nome che descriva il tipo di fornitori che appartengono al gruppo. |
| Descrizione | Immettere una descrizione del gruppo. |

## <a name="view-and-process-overunder-transactions"></a>Visualizzare ed elaborare transazioni in eccesso/in difetto

Le transazioni in eccesso e in difetto vengono generate quando la quantità di merci stoccata non corrisponde alla quantità inizializzata. La quantità nel giornale di registrazione arrivi deve essere aggiornata solo con la quantità stoccata.

Quando viene elaborato il ricevimento delle righe di viaggio, è possibile impostare tolleranze in eccesso/in difetto per un fornitore. Gli articoli verranno quindi esaminati e convalidati. La tolleranza può essere impostata come percentuale, importo locale o entrambi.

Se un articolo ricevuto rientra nella tolleranza, il sistema genererà un giornale di registrazione movimenti. Questo giornale di registrazione può essere specificato nella pagina dei parametri di viaggio. Inoltre, verrà creata una transazione in eccesso/in difetto. Ad esempio, il valore dell'ordine è $100, il valore del ricevimento è $99 e questi valori soddisfano le regole di tolleranza. In questo caso, verrà creato un giornale di registrazione movimenti negativo per la quantità in difetto ricevuta.

Se un articolo ricevuto non rientra nella tolleranza, il sistema genererà una transazione in eccesso/in difetto per la differenza di quantità.

Per visualizzare ed elaborare transazioni in eccesso/in difetto, selezionare **Costo sbarcato \> Richieste di informazioni \> Transazioni in eccesso/in difetto**. Una transazione in eccesso/in difetto sarà associata a tutti gli articoli in un viaggio che sono stati ricevuti in eccesso o in difetto. Si consiglia di utilizzare la pagina **Transazioni in eccesso/in difetto** per risolvere tutte le transazioni in eccesso/in difetto associate ai viaggi. Consigliamo anche di **non** utilizzare giornali di registrazione movimenti o conteggi per risolvere manualmente transazioni di magazzino con consegna in difetto. Si deve invece utilizzare la pagina **Transazioni in eccesso/in difetti** per gestire quantità di magazzino con consegna in difetto.

### <a name="upper-overview-tab"></a>Scheda Panoramica superiore

Per visualizzare le transazioni in eccesso/in difetto, selezionare la scheda **Panoramica** nella parte superiore della pagina **Transazioni in eccesso/in difetto**. Nella seguente tabella vengono descritti i campi disponibili nella griglia.

| Campo | Descrizione |
|---|---|
| Numero transazione in eccesso/in difetto | Il nome univoco del record di transazione in eccesso/in difetto creato automaticamente quando è stato elaborato il giornale di registrazione arrivi. |
| Viaggio | Il viaggio a cui era associata la riga di acquisto. |
| Contenitore di spedizione | Il contenitore a cui era associata la riga di acquisto. |
| Giornale di registrazione arrivi | Il giornale di registrazione arrivi da cui è stata generata la riga eccesso/difetto. |
| Riferimento | Un riferimento all'ordine fornitore o all'ordine di trasferimento associato alla transazione in eccesso/in difetto. |
| Numero | L'ordine fornitore a cui si fa riferimento nella transazione in eccesso/in difetto. |
| Account fornitore | Il fornitore a cui è associato l'eccesso o il difetto. |
| Numero merci in transito | Il numero di merci in transito, se applicabile. |
| Numero articolo | Il numero di articolo a cui è associato l'eccesso o il difetto. |
| Quantità originale | La quantità originale della riga ordine fornitore associata alla spedizione. |
| Quantità ricevuta | La quantità effettivamente ricevuta. |
| Differenza | La differenza tra l'importo del giornale di registrazione arrivi previsti e l'importo registrato nel giornale di registrazione arrivi. Un valore negativo indica una consegna in eccesso di merci. |
| Quantità rimanente | La quantità che rimane nella riga del giornale di registrazione arrivi. |
| Consegna in eccesso/in difetto | Un valore che indica se la quantità ricevuta è in eccesso o in difetto. |
| Stato | Lo stato di una transazione in eccesso/in difetto. A seconda delle impostazioni nella pagina **[Parametri di costo sbarcato](landed-cost-parameters.md)**, la consegna in eccesso può creare automaticamente un giornale di registrazione movimenti per l'importo di consegna in eccesso e registrare il giornale di registrazione. In questo caso, la transazione in eccesso/in difetto avrà lo stato *Completato*. Se è necessario spostare le merci fuori dal magazzino di consegna in difetto, il record avrà lo stato *In corso*. |
| Motivo eccesso/difetto | Il motivo associato alla transazione in eccesso/in difetto. |
| Altre dimensioni inventariali | È possibile visualizzare colonne per ulteriori dimensioni nella griglia come necessario. Tali dimensioni includono il numero di batch, lo stato dell'inventario e il magazzino. Nel riquadro Azioni selezionare **Magazzino \> Visualizza dimensioni** per aprire una finestra di dialogo in cui è possibile selezionare le dimensioni da includere. |

### <a name="upper-general-tab"></a>Scheda Generale superiore

Per visualizzare ulteriori informazioni sulla riga attualmente selezionata nella scheda **Panoramica** superiore, selezionare la scheda **Generale** nella parte superiore della pagina **Transazioni in eccesso/in difetto**. Le informazioni in questa scheda includono i valori per tutte le dimensioni disponibili. Queste informazioni sono estratte dall'ordine fornitore di origine.

### <a name="lower-overview-tab"></a>Scheda Panoramica inferiore

Per visualizzare il tipo di documento per la riga attualmente selezionata nella scheda **Panoramica** superiore, selezionare la scheda **Panoramica** nella parte inferiore della pagina **Transazioni in eccesso/in difetto**. Nella seguente tabella vengono illustrati i campi disponibili.

| Campo | Descrizione |
|---|---|
| Nuovo tipo di documento | Questo campo è impostato su *Giornale di registrazione movimenti* o *Ordine fornitore*, a seconda dell'azione visualizzata nella riga della transazione in eccesso/in difetto selezionata. |
| Numero | Un riferimento e un collegamento all'ordine fornitore o al giornale di registrazione movimenti associato alla riga della transazione in eccesso/in difetto selezionata. |
| Motivo eccesso/difetto | Il motivo associato alla riga della transazione in eccesso/in difetto selezionata. |
| Quantità | La quantità selezionata per l'ordine fornitore o il giornale di registrazione movimenti associato alla riga della transazione in eccesso/in difetto selezionata. |

### <a name="lower-general-tab"></a>Scheda Generale inferiore

Per visualizzare il numero di transazione in eccesso/in difetto, l'ID lotto e il numero di dimensione associati alla riga della transazione in eccesso/in difetto selezionata, selezionare la scheda **Generale** nella parte inferiore della pagina **Transazioni in eccesso/in difetto**. 

### <a name="process-overunder-transactions"></a>Elaborare transazioni in eccesso/in difetto

Il riquadro Azioni nella pagina **Transazioni in eccesso/in difetto** fornisce i seguenti comandi per l'elaborazione delle transazioni selezionate nella pagina. Ogni comando consente di scegliere come elaborare ogni transazione.

- **Crea \> Movimento** - Creare e registrare un giornale di registrazione movimenti per la transazione selezionata. Per le transazioni in difetto, viene automaticamente creato e registrato un giornale di registrazione movimenti per la differenza tra la quantità prevista e quella ricevuta effettiva. Selezionare questo comando per le transazioni in eccesso se il fornitore deve determinare la differenza di costo.
- **Crea \> Ordine fornitore** - Creare un ordine fornitore per la differenza tra la quantità prevista e quella ricevuta effettiva della transazione selezionata. Selezionare questo comando per le transazioni in eccesso se l'organizzazione determinerà la differenza di costo.
- **Crea \> Trasferimento a destinazione** - Questo comando si applica solo agli ordini di trasferimento. Selezionarlo per trasferire la quantità in eccesso o in difetto al magazzino di destinazione.
- **Crea \> Trasferimento a origine** - Questo comando si applica solo agli ordini di trasferimento. Selezionarlo per trasferire la quantità in eccesso o in difetto al magazzino di origine.
