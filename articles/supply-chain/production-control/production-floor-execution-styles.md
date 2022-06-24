---
title: Creare lo stile per l'interfaccia di esecuzione dell'area di produzione
description: L'articolo spiega come configurare i controlli del modulo in modo che vengano applicati gli stili di esecuzione del piano di produzione predefiniti.
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: ad6ecd591353fe8ddc1a5b9049d65491fb58e98a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859142"
---
# <a name="style-the-production-floor-execution-interface"></a>Creare lo stile per l'interfaccia di esecuzione dell'area di produzione

[!include [banner](../includes/banner.md)]

L'articolo spiega come configurare i controlli del modulo in modo che vengano applicati gli stili di esecuzione del piano di produzione predefiniti.

## <a name="forms-and-dialogs"></a>Moduli e finestre di dialogo

Gli stili possono essere applicati a un modulo o a una finestra di dialogo solo se vengono soddisfatti i seguenti requisiti:

- Se il modulo deve assomigliare al modulo di avanzamento del report esistente, il nome del modulo o della finestra di dialogo deve iniziare con `JmgProductionFloorExecutionCustomInputDialog`.
- Il modulo o la finestra di dialogo può contenere una parte del modulo di dettaglio. Per applicare gli stili, il nome della parte del modulo di dettaglio deve iniziare con `JmgProductionFloorExecutionCustomDetailsDialog`.
- Se il modulo o la finestra di dialogo deve avere una vista semplice, il nome della vista semplice deve iniziare con `JmgProductionFloorExecutionCustomDialog`. Esempi di moduli che hanno una visualizzazione semplice includono il modulo di inizio e il modulo dell'attività indiretta.
- Tutti i controlli nella finestra di dialogo devono essere configurati come descritto in questo articolo.

> [!IMPORTANT]
> Le funzionalità menzionate nei primi due punti di questo elenco richiedono Supply Chain Management versione 10.0.19 o successiva.

Gli stili possono essere applicati al pulsante **OK** in una finestra di dialogo solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con `OkButtonGroup`.

Gli stili possono essere applicati al pulsante **Annulla** in una finestra di dialogo solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con `CancelButtonGroup`.

### <a name="header"></a>Intestazione

L'illustrazione seguente mostra un modulo tipico o un'intestazione di finestra di dialogo.

![Modulo tipico o intestazione della finestra di dialogo.](media/pfe-styles-header.png "Modulo tipico o intestazione della finestra di dialogo")

In Visual Studio, le intestazioni vengono create utilizzando una struttura come quella mostrata nell'illustrazione seguente.

![Tipica struttura del codice per la creazione di un'intestazione.](media/pfe-styles-header-code-structure.png "Tipica struttura del codice per la creazione di un'intestazione")

Per aggiungere testo all'intestazione, utilizza un codice come il seguente esempio.

```xpp
private void setCaption()
{
    HeaderFieldWithSeparatorText1.text("Report Progress");
    HeaderFieldWithSeparatorText2.text(ProdId);

    …

    HeaderFieldText.text(OprNum);
}
```

Quando scrivi il codice dell'intestazione, applica le seguenti regole:

- Il nome del gruppo principale deve essere `TableRowHeaderGroup`.
- Ogni blocco di testo (separato da punti elenco) deve iniziare con `HeaderFieldWithSeparatorText`.
- Il nome dell'ultimo testo deve iniziare con `HeaderFieldText`.
- `CaptionImage` può essere ignorato.

### <a name="progress-indicator"></a>Indicatore di stato

Puoi includere un indicatore di avanzamento, mostrato a destra dell'intestazione. L'illustrazione seguente mostra un indicatore di avanzamento.

![Indicatore di avanzamento tipico.](media/pfe-styles-header-progress.png "Indicatore di avanzamento tipico")

Per mostrare l'indicatore di avanzamento, il campo di testo deve essere denominato `ShowProgress`.

## <a name="grid"></a>Griglia

Gli stili vengono applicati automaticamente. Non è richiesta alcuna configurazione specifica.

La griglia dovrebbe avere uno stile `TabularView` e il metodo `run()` nel modulo personalizzato deve essere sovrascritto, perché una nuova griglia non è ancora supportata. Aggiungi il seguente codice.

```xpp
public void run()
{
    super();
    // To opt out a page from the new grid
    this.forceLegacyGrid();
}
```

Per aggiornare i dati in una visualizzazione principale, è consigliabile utilizzare qualcosa come `this.parmParentForm().updateLayout();` in un metodo `click` della tua azione. (Ad esempio, guarda la classe `JmgProductionFloorExecutionReportFeedbackAction`.) Assicurati solo che `parmDataSource` sia impostato nel metodo `init` del tuo nuovo modulo (`formCaller.parmDataSource(this.dataSource(1));`). Ad esempio, guarda il modulo `JmgProductionFloorExecutionMainGrid`.

## <a name="card-view"></a>Visualizzazione scheda

Gli stili possono essere applicati ai controlli della visualizzazione scheda solo se vengono soddisfatti i seguenti requisiti:

- Ogni visualizzazzione scheda è contenuta in un gruppo di moduli.
- Il nome del gruppo inizia con `CardGroup` (ad esempio, `CardGroupJobsView`).

L'illustrazione seguente mostra una visualizzazione scheda senza controlli al suo interno.

![Visualizzazione scheda senza elementi.](media/pfe-styles-empty-card.png)

Le seguenti illustrazioni mostrano le visualizzazioni scheda che contengono controlli al loro interno.

![Scheda con elementi che mostrano Hz.](media/pfe-styles-elements.png)

![Scheda con elementi per una richiesta di intervento di manutenzione.](media/pfe-styles-elements-maintenance.png)

## <a name="business-card"></a>Carta aziendale

Gli stili possono essere applicati ai controlli della carta aziendale solo se vengono soddisfatti i seguenti requisiti:

- Ogni carta aziendale è contenuta in un gruppo di moduli.
- Il nome del gruppo inizia con `BusinessCardGroup` (ad esempio, `BusinessCardGroupJobsList`).

Imposta le seguenti proprietà nella carta aziendale:

- **Stile:** *elenco*
- **Stile esteso:** *cardList*
- **Selezione multipla:** *No*
- **Mostra etichette colonna:** *No*

![Carta aziendale.](media/pfe-styles-business-card.png)

## <a name="radio-button"></a>Pulsante di opzione

Gli stili possono essere applicati ai pulsanti di opzione solo se vengono soddisfatti i seguenti requisiti:

- Ogni pulsante di opzione è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con `RadioTextBelow` o `RadioTextRight`, a seconda di dove vuoi che appaia il testo.

Imposta le seguenti proprietà nel pulsante di opzione:

- **Interruttore:** *Controllo*
- **Valore interruttore:** *Attiva* se il pulsante di opzione deve essere selezionato; altrimenti, *Disattiva*

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

- **Visualizzazione pulsante:** *TextWithImageLeft*
- **Immagine normale:** questa proprietà non può essere vuota. Ad esempio, utilizza *CoffeeScript*.
- **Testo:** questa proprietà non può essere vuota. Ad esempio, utilizza *Inizio pausa*.
- **Larghezza:** *Auto* o *SizeToContent*
- **Altezza:** *Auto* o *SizeToContent*

### <a name="primary-button"></a>Pulsante primario

Gli stili possono essere applicati a un pulsante primario solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con `DefaultButtonGroup` o `PrimaryButtonGroup` (ad esempio `DefaultButtonGroup10`).

![Pulsante primario.](media/pfe-styles-first.png)

### <a name="secondary-button"></a>Pulsante secondario

Gli stili possono essere applicati a un pulsante secondario solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il gruppo è denominato **Pannello destro**, o il nome del gruppo inizia con `SecondaryButtonGroup`.

![Pulsante secondario.](media/pfe-styles-second.png)

### <a name="third-group-button"></a>Pulsante del terzo gruppo

Gli stili possono essere applicati a un pulsante del terzo gruppo solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il gruppo è denominato **Pannello sinistro**, o il nome del gruppo inizia con `ThirdButtonGroup`.

![Pulsante del terzo gruppo.](media/pfe-styles-third.png)

### <a name="fourth-group-button"></a>Pulsante del quarto gruppo

Gli stili possono essere applicati a un pulsante del quarto gruppo solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con `FourthButtonGroup`.

Imposta le seguenti proprietà nel pulsante:

- **Visualizzazione pulsante:** *TextOnly*
- **Immagine normale:** questa proprietà deve essere vuota.
- **Testo:** questa proprietà non può essere vuota. Ad esempio, usa *Visualizza* o *Modifica*.
- **Larghezza:** *Automatico*
- **Altezza:** *Automatico*

![Pulsante del quarto gruppo.](media/pfe-styles-fourth.png)

### <a name="flat-button"></a>Pulsante Flat

Gli stili possono essere applicati a un pulsante Flat solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con `FlatButtonGroup`.

Imposta le seguenti proprietà nel pulsante:

- **Visualizzazione pulsante:** *ImageOnly*
- **Immagine normale:** questa proprietà non può essere vuota. Ad esempio, utilizza *CoffeeScript*.
- **Testo:** questa proprietà deve essere vuota.
- **Larghezza:** *Auto* o *SizeToContent*
- **Altezza:** *Auto* o *SizeToContent*

![Pulsante Flat.](media/pfe-styles-flat-button.png)

### <a name="continue-button"></a>Pulsante Continua

Gli stili possono essere applicati a un pulsante Continua solo se vengono soddisfatti i seguenti requisiti:

- Il pulsante è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con `ContinueButtonGroup`.

Imposta le seguenti proprietà nel pulsante:

- **Visualizzazione pulsante:** *ImageOnly*
- **Immagine normale:** *Inoltra*
- **Testo:** questa proprietà deve essere vuota.
- **Larghezza:** *Auto* o *SizeToContent*
- **Altezza:** *Auto* o *SizeToContent*

![Pulsante Continua.](media/pfe-styles-continue-button.png)

## <a name="combo-box"></a>Casella combinata

Una casella combinata è una combinazione di tre controlli: un controllo di input, un pulsante che cancella il controllo di input e un pulsante che esegue una ricerca.

Gli stili possono essere applicati a una casella combinata solo se vengono soddisfatti i seguenti requisiti:

- La casella combinata è contenuta in un gruppo di moduli.
- Il nome del gruppo inizia con `Combobox`.
- All'interno del gruppo, il primo controllo è un controllo `AxFormStringControl`. Questo controllo mostra il valore corrente ed è qui che l'utente immette il valore richiesto.
- Il secondo controllo è un controllo `CommonButton`, e il suo nome inizia con `ClearButton`. Questo pulsante deve contenere un codice che utilizza la proprietà `enable` per mostrare o nascondere il pulsante. Ad esempio, per mostrare o nascondere il pulsante **Cancella** mentre l'utente sta digitando le informazioni nel controllo di input, è possibile utilizzare il codice seguente.

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

    Utilizza il seguente codice per il metodo `clicked` del pulsante **Cancella**.

    ```xpp
    public void clicked()
    {
        element.setSerialId('');
        InventSerialId.setFocus(); // set focus back to the input box
    }
    ```

    Imposta il valore del controllo di input, `AxFormStringControl`, quando il modulo viene inizializzato usando il metodo `init`. Se il valore non è vuoto, abilita il pulsante **Cancella**. Se il valore è vuoto, disabilita il pulsante **Cancella**.

- Il terzo controllo è un controllo `CommonButton`, e il suo nome inizia con `SearchButton`.

L'illustrazione seguente mostra due controlli di casella combinata. La casella combinata a sinistra ha una casella di testo vuota e il pulsante **Cancella** è disabilitato. La casella combinata a destra ha il testo nella casella di testo e il pulsante **Cancella** è abilitato.

![Caselle combinate con e senza pulsante Cancella.](media/pfe-styles-combo.png)

## <a name="quick-filter"></a>Filtro rapido

Il controllo del filtro rapido aggiunge un campo di ricerca alla pagina. Puoi applicare gli stili a un filtro rapido purché siano soddisfatti i seguenti requisiti:

- Il filtro rapido è contenuto in un gruppo di moduli.
- Il nome del gruppo inizia con `SearchInputGroup`.
- All'interno del gruppo, il primo controllo è un controllo `QuickFilter`. (Qui è dove l'utente immette la stringa di ricerca.)
- Il secondo controllo è un `FormStaticTextControl` denominato `NumberOfResults`. (Questo controllo è facoltativo. Se incluso, mostra il numero di elementi trovati).
- Il terzo controllo è un controllo `CommonButton`, e il suo nome inizia con `ClearButton`.

L'illustrazione seguente mostra due controlli di filtro rapido. Il filtro rapido a sinistra ha un filtro rapido vuoto e il numero di risultati non è visibile. Il filtro rapido a destra contiene una stringa di ricerca e mostra il numero di risultati.

![Esempi di un controllo di filtro rapido con e senza una stringa di ricerca.](media/pfe-styles-quick-filter.png "Esempi di un controllo di filtro rapido con e senza una stringa di ricerca")

## <a name="center-align-elements-on-a-tab"></a>Allinea al centro gli elementi su una scheda

Per allineare gli elementi al centro di una scheda, il nome del gruppo deve iniziare con `TabContentGroup` e il gruppo deve avere le seguenti proprietà:

- **Modalità larghezza:** `SizeToAvailable`
- **Modalità altezza:** `SizeToAvailable`

## <a name="align-a-grid-detail-part-and-quick-filter"></a>Allinea una griglia, una parte di dettaglio e un filtro rapido

Per organizzare una griglia personalizzata, una parte di dettaglio e un filtro rapido in modo che assomiglino al design standard, tieni presente i seguenti punti quando li metti tutti insieme:

- Se la griglia ha un filtro rapido, sia la griglia che il filtro rapido dovrebbero trovarsi all'interno del gruppo il cui nome inizia con `GridGroup`.
- Per applicare gli stili a una parte del dettaglio, il nome del gruppo deve iniziare con `DetailInformationGroup`.

L'illustrazione seguente mostra una griglia tipica che include un filtro rapido e una parte di dettaglio sulla destra.

![Griglia tipica che include una parte di dettaglio e un filtro rapido](media/pfe-styles-align-grid.png "Griglia tipica che include una parte di dettaglio e un filtro rapido")

In Visual Studio, una griglia, la parte di dettaglio e il filtro rapido possono essere creati utilizzando una struttura come quella mostrata nell'illustrazione seguente.

![Struttura di codice tipica che allinea una griglia, la parte di dettaglio e un filtro rapido](media/pfe-styles-header-code-structure2.png "Struttura di codice tipica che allinea una griglia, la parte di dettaglio e un filtro rapido")

## <a name="additional-resources"></a>Risorse aggiuntive

- [Personalizzare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-customize.md)
- [Progettare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-tabs.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
