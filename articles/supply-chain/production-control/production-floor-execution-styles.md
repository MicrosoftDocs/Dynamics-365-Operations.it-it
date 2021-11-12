---
title: Progettare l'interfaccia di esecuzione dell'area di produzione
description: L'argomento spiega come configurare i controlli del modulo in modo che vengano applicati gli stili di esecuzione del piano di produzione predefiniti.
author: johanhoffmann
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 32e49458f6ea7c484bc4200e414d930381b31891
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652024"
---
# <a name="style-the-production-floor-execution-interface"></a>Progettare l'interfaccia di esecuzione dell'area di produzione

[!include [banner](../includes/banner.md)]

L'argomento spiega come configurare i controlli del modulo in modo che vengano applicati gli stili di esecuzione del piano di produzione predefiniti.

## <a name="forms-and-dialogs"></a>Moduli e finestre di dialogo

Gli stili possono essere applicati a un modulo o a una finestra di dialogo solo se vengono soddisfatti i seguenti requisiti:

- Se il modulo deve assomigliare al modulo di avanzamento del report esistente, il nome del modulo o della finestra di dialogo deve iniziare con **JmgProductionFloorExecutionCustomInputDialog**.
- Il modulo o la finestra di dialogo può contenere una parte del modulo di dettaglio. Per applicare gli stili, il nome della parte del modulo di dettaglio deve iniziare con **JmgProductionFloorExecutionCustomDetailsDialog**.
- Se il modulo o la finestra di dialogo deve avere una vista semplice, il nome della vista semplice deve iniziare con **JmgProductionFloorExecutionCustomDialog**. Esempi di moduli che hanno una visualizzazione semplice includono il modulo di inizio e il modulo dell'attività indiretta.
- Tutti i controlli nella finestra di dialogo devono essere configurati come descritto in questo argomento.

> [!IMPORTANT]
> Le funzionalità menzionate nei primi due punti di questo elenco richiedono Supply Chain Management versione 10.0.19 o successiva.

Gli stili possono essere applicati al pulsante **OK** in una finestra di dialogo solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con **OkButtonGroup**.

Gli stili possono essere applicati al pulsante **Annulla** in una finestra di dialogo solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con **CancelButtonGroup**.

## <a name="grid"></a>Griglia

Gli stili vengono applicati automaticamente. Non è richiesta alcuna configurazione specifica.

## <a name="card-view"></a>Visualizzazione scheda

Gli stili possono essere applicati ai controlli della visualizzazione scheda solo se vengono soddisfatti i seguenti requisiti:

- Ogni visualizzazzione scheda è contenuta in un gruppo di moduli.
- Il nome del gruppo inizia con **CardGroup** (ad esempio, **CardGroupJobsView**).

L'illustrazione seguente mostra una visualizzazione scheda senza controlli al suo interno.

![Visualizzazione scheda senza elementi.](media/pfe-styles-empty-card.png)

Le seguenti illustrazioni mostrano le visualizzazioni scheda che contengono controlli al loro interno.

![Scheda con elementi che mostrano Hz.](media/pfe-styles-elements.png)

![Scheda con elementi per una richiesta di intervento di manutenzione.](media/pfe-styles-elements-maintenance.png)

## <a name="business-card"></a>Carta aziendale

Gli stili possono essere applicati ai controlli della carta aziendale solo se vengono soddisfatti i seguenti requisiti:

- Ogni carta aziendale è contenuta in un gruppo di moduli.
- Il nome del gruppo inizia con **BusinessCardGroup** (ad esempio, **BusinessCardGroupJobsList**).

Imposta le seguenti proprietà nella carta aziendale:

- **Stile**: **elenco**
- **Stile esteso**: **cardList**
- **Selezione multipla**: **No**
- **Mostra etichette colonna**: **No**

![Carta aziendale.](media/pfe-styles-business-card.png)

## <a name="radio-button"></a>Pulsante di opzione

Gli stili possono essere applicati ai pulsanti di opzione solo se vengono soddisfatti i seguenti requisiti:

- Ogni pulsante di opzione è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con **RadioTextBelow** o **RadioTextRight**, a seconda di dove vuoi che appaia il testo.

Imposta le seguenti proprietà nel pulsante di opzione:

- **Interruttore**: **Controllo**
- **Valore interruttore**: **Attiva** se il pulsante di opzione deve essere selezionato; altrimenti, **Disattiva**

L'illustrazione seguente mostra un esempio in cui il testo viene visualizzato sotto i pulsanti di opzione.

![Pulsanti di opzione con il testo sottostante.](media/pfe-styles-radio-text-below.png)

L'illustrazione seguente mostra un esempio in cui il testo viene visualizzato a destra dei pulsanti di opzione.

![Pulsanti di opzione con il testo a destra.](media/pfe-styles-radio-text-right.png)

### <a name="radio-buttons-in-internet-explorer"></a>Pulsanti di opzione in Internet Explorer

Gli stili dei pulsanti di opzione non sono supportati in Internet Explorer. L'illustrazione seguente mostra i pulsanti di opzione in Internet Explorer.

![Pulsanti di opzione in Internet Explorer.](media/pfe-styles-browser.png)

## <a name="buttons"></a>Bottoni

Gli stili possono essere applicati ai pulsanti solo se vengono soddisfatti i seguenti requisiti:

- Ogni gruppo di pulsanti è contenuto in un gruppo di moduli. Tutti i pulsanti del gruppo avranno lo stesso stile.
- Non ci sono requisiti sul nome del gruppo.

Imposta le seguenti proprietà nei pulsanti:

- **Visualizzazione pulsante**: **TextWithImageLeft**.
- **Immagine normale**: questa proprietà non può essere vuota. Ad esempio, utilizza **CoffeeScript**.
- **Testo**: questa proprietà non può essere vuota. Ad esempio, utilizza **Inizio pausa**.
- **Larghezza**: **Automatico**.
- **Altezza**: **Automatico**.

### <a name="primary-button"></a>Pulsante primario

Gli stili possono essere applicati a un pulsante primario solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con **DefaultButtonGroup** o **PrimaryButtonGroup** (ad esempio, **DefaultButtonGroup10**).

![Pulsante primario.](media/pfe-styles-first.png)

### <a name="secondary-button"></a>Pulsante secondario

Gli stili possono essere applicati a un pulsante secondario solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il gruppo è denominato **Pannello destro**, o il nome del gruppo inizia con **SecondaryButtonGroup**.

![Pulsante secondario.](media/pfe-styles-second.png)

### <a name="third-group-button"></a>Pulsante del terzo gruppo

Gli stili possono essere applicati a un pulsante del terzo gruppo solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il gruppo è denominato **Pannello sinistro**, o il nome del gruppo inizia con **ThirdButtonGroup**.

![Pulsante del terzo gruppo.](media/pfe-styles-third.png)

### <a name="fourth-group-button"></a>Pulsante del quarto gruppo

Gli stili possono essere applicati a un pulsante del quarto gruppo solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con **FourthButtonGroup**.

Imposta le seguenti proprietà nel pulsante:

- **Visualizzazione pulsante**: **TextOnly**.
- **Immagine normale**: questa proprietà deve essere vuota.
- **Testo**: questa proprietà non può essere vuota. Ad esempio, usa **Visualizza** o **Modifica**.
- **Larghezza**: **Automatico**.
- **Altezza**: **Automatico**.

![Pulsante del quarto gruppo.](media/pfe-styles-fourth.png)

### <a name="flat-button"></a>Pulsante Flat

Gli stili possono essere applicati a un pulsante Flat solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con **FlatButtonGroup**.

Imposta le seguenti proprietà nel pulsante:

- **Visualizzazione pulsante**: **ImageOnly**.
- **Immagine normale**: questa proprietà non può essere vuota. Ad esempio, utilizza **CoffeeScript**.
- **Testo**: questa proprietà deve essere vuota.
- **Larghezza**: **Automatico**.
- **Altezza**: **Automatico**.

![Pulsante Flat.](media/pfe-styles-flat-button.png)

## <a name="combo-box"></a>Casella combinata

Una casella combinata è una combinazione di tre controlli: un controllo di input, un pulsante che cancella il controllo di input e un pulsante che esegue una ricerca.

Gli stili possono essere applicati a una casella combinata solo se vengono soddisfatti i seguenti requisiti:

- La casella combinata è contenuta in un gruppo di moduli.
- Il nome del gruppo inizia con **Combobox**.
- All'interno del gruppo, il primo controllo è un controllo **AxFormStringControl**. Questo controllo mostra il valore corrente ed è qui che l'utente immette il valore richiesto.
- Il secondo controllo è un controllo **CommonButton**, e il suo nome inizia con **ClearButton**. Questo pulsante deve contenere un codice che utilizza la proprietà **abilita** per mostrare o nascondere il pulsante. Ad esempio, per mostrare o nascondere il pulsante **Cancella** mentre l'utente sta digitando le informazioni nel controllo di input, è possibile utilizzare il codice seguente.

    ```xpp
    public void textChange()
    {
        super();
        ClearButtonSerial.enabled(this.text()? true : false);
    }
    ```

    Dovresti avere un metodo in cui i dati sono impostati nel controllo di input. Abilita il pulsante **Cancella** in quel metodo. Ecco un esempio.

    ```xpp
    public void setSerialId(str _serialId)
    {
        JmgTmpJobBundleProdFeedback.InventSerial = _serialId;
        ClearButtonSerial.enabled(_serialId? true : false);

        if (_serialId)
        {
            this.addSerialNumber();
        }
    }
    ```

    Utilizza il seguente codice per il metodo **cliccato** del pulsante **Cancella**.

    ```xpp
    public void clicked()
    {
        element.setSerialId('');
        InventSerialId.setFocus(); // set focus back to the input box
    }
    ```

    Imposta il valore del controllo di input, **AxFormStringControl**, quando il modulo viene inizializzato usando il metodo **init**. Se il valore non è vuoto, abilita il pulsante **Cancella**. Se il valore è vuoto, disabilita il pulsante **Cancella**.

- Il terzo controllo è un controllo **CommonButton**, e il suo nome inizia con **SearchButton**.

L'illustrazione seguente mostra due controlli di casella combinata. La casella combinata a sinistra ha una casella di testo vuota e il pulsante **Cancella** è disabilitato. La casella combinata a destra ha il testo nella casella di testo e il pulsante **Cancella** è abilitato.

![Caselle combinate con e senza pulsante Cancella.](media/pfe-styles-combo.png)

## <a name="quick-filter"></a>Filtro rapido

Il controllo del filtro rapido aggiunge un campo di ricerca alla pagina. Puoi applicare gli stili a un filtro rapido purché siano soddisfatti i seguenti requisiti:

- Il filtro rapido è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con **SearchInputGroup**.
- All'interno del gruppo, il primo controllo è un controllo **QuickFilter**. (Qui è dove l'utente immette la stringa di ricerca.)
- Il secondo controllo è un **FormStaticTextControl** con il nome **NumberOfResults**. (Questo controllo è facoltativo e mostra il numero di elementi trovati se incluso.)
- Il terzo controllo è un controllo **CommonButton** con un nome che inizia con **ClearButton**.

L'illustrazione seguente mostra due controlli di filtro rapido. Il filtro rapido a sinistra ha un filtro rapido vuoto e il numero di risultati non è visibile. Il filtro rapido a destra contiene una stringa di ricerca e mostra il numero di risultati.

![Esempi di un controllo di filtro rapido con e senza una stringa di ricerca.](media/pfe-styles-quick-filter.png "Esempi di un controllo di filtro rapido con e senza una stringa di ricerca")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
