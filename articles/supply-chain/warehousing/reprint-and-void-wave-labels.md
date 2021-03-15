---
title: Ristampare e annullare etichette ondata
description: Questo argomento spiega come annullare e ristampare le etichette ondata esistenti.
author: GarmMSFT
manager: PJacobse
ms.date: 07/09/2020
ms.topic: article
ms.service: dynamics-ax-applications
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSWaveTableListPage, WHSWorkException, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelLayout, WHSWaveLabelType, WHSWaveLabelTemplateGroup
audience: Application User
ms.reviewer: PJacobse
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-07-09
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: cc76a3915d6a1e58a71eb997b5af58941905e879
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996050"
---
# <a name="reprint-and-void-wave-labels"></a>Ristampare e annullare etichette ondata

[!include [banner](../includes/banner.md)]

Questo argomento spiega come gestire le etichette generate dall'elaborazione di ondate (per una descrizione dettagliata e le istruzioni di configurazione, vedere [Configurare la stampa di etichette ondata](../warehousing/configure-wave-label-printing.md)).

È possibile ristampare le etichette ondata in qualsiasi momento. Ad esempio, potrebbe essere necessario stampare una singola etichetta se un'etichetta esistente è stata persa o risulta danneggiata. In alternativa, un addetto al magazzino o un supervisore potrebbe dover ristampare un intero rotolo di etichette se il numero e/o la composizione di un'intera serie di etichette ondata è cambiata (ad esempio, a causa della carenza di scorte o per altri motivi). Spesso, anche se è cambiato solo il numero di cartoni, l'intero rotolo deve essere ristampato per mantenere accurato il numero totale nella sezione "Cartone X di Y" di ciascuna etichetta.

La funzionalità di ristampa di etichette ondata include:

- Ristampare le etichette sia dall'app di magazzino che dal rich client.
- Annullare e ristampare contemporaneamente le etichette (la possibilità di annullare le etichette è ad esempio incorporata negli scenari di prelievo in difetto).
- Pulire lo storico delle etichette ondata.

Questo argomento presenta una raccolta di scenari che mostrano, attraverso esempi, come utilizzare le funzionalità di ristampa di etichette ondata.

> [!IMPORTANT]
> Per utilizzare gli scenari presentati in questo argomento, è necessario innanzitutto attivare e configurare le funzionalità di stampa di etichette ondata pertinenti, come descritto in [Configurare la stampa di etichette ondata](../warehousing/configure-wave-label-printing.md). Vari scenari in questo argomento richiedono inoltre l'esecuzione degli scenrari in quell'argomento per generare dati di esempio dei prerequisiti.

## <a name="scenario-1-reprint-labels-from-the-web-client"></a>Scenario 1: ristampare le etichette dal client Web

È possibile visualizzare e ristampare le etichette ondata dalle seguenti pagine. Nel riquadro azioni di ogni pagina della scheda **Spedizioni** nel gruppo **Informazioni correlate**, selezionare **Etichette ondata**.

- Tutte le spedizioni \> Dettagli spedizione
- Tutti i carichi \> Dettagli carico
- Tutte le ondate
- Etichette ondata
- Storico etichette ondata

Per ristampare un'etichetta ondata dal client Web, attenersi alla seguente procedura.

1. Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.
1. Selezionare l'ondata da cui ristampare le etichette.
1. Nel riquadro azioni, scheda **Ondata**, gruppo **Stampa**, selezionare **Etichette ondata**.
1. Seguire uno o entrambi i seguenti passaggi:

    - Nel campo **Nome stampante**, selezionare una stampante per ristampare l'etichetta. (lasciare vuoto questo campo se si desidera semplicemente aggiornare i dettagli dell'etichetta ondata, senza ristampare l'etichetta).
    - Per aggiornare l'etichetta, selezionare la casella di controllo **Aggiorna dettagli etichetta ondata** (lasciare deselezionata questa casella di controllo se si desidera ristampare l'etichetta precedente).

    > [!NOTE]
    > Ogni volta che un'etichetta ondata viene stampata o ristampata, i relativi dati vengono convertiti mediante il layout di etichetta ondata appropriato e tutti i segnaposto vengono sostituiti con valori effettivi. La stringa risultante viene memorizzata come record nella cronologia delle etichette ondata. Se la casella di controllo **Aggiorna dettagli etichetta ondata** è deselezionata, i dati ZPL (Zebra Programming Language) memorizzati vengono utilizzati quando viene ristampata un'etichetta. Se la casella di controllo **Aggiorna dettagli etichetta ondata** è selezionata, viene generata una nuova stringa. Anche le etichette ondata esistenti vengono ricalcolate e tutte le etichette in eccesso (ad esempio, se le relative righe di lavoro sono state cancellate o modificate) vengono contrassegnate come **Annullate** e non sono ristampate.

1. Selezionare **OK** per confermare la selezione.

## <a name="scenario-2-reprint-labels-from-the-warehousing-app"></a>Scenario 2: ristampare le etichette dall'app di magazzino

Questo scenario si applica in genere se un rotolo di etichette è stato perso o risulta danneggiato. Fornisce un esempio che mostra come impostare le voci di menu del dispositivo mobile che consentiranno ai lavoratori di ristampare etichette singole e multiple. Quindi mostra come utilizzare queste nuove voci di menu su un dispositivo mobile.

### <a name="set-up-the-required-menu-items-and-menu-for-the-mobile-device"></a>Impostare le voci di menu e il menu necessari per il dispositivo mobile

Affinché i lavoratori possano ristampare le etichette da un dispositivo mobile, è necessario impostare le voci di menu per fornire questa funzionalità e quindi aggiungere tali voci al menu dell'app di magazzino.

#### <a name="create-new-mobile-device-menu-items"></a>Creare nuove voci di menu per dispositivo mobile

Seguire questi passaggi per creare una nuova raccolta di voci di menu con cui ristampare etichette dall'app di magazzino.

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Creare una voce di menu e impostare i seguenti valori per la stessa:

    - **Nome voce di menu:** *Ristampa singola etichetta ondata*
    - **Titolo:** *Ristampa singola etichetta ondata*
    - **Modalità:** *Indiretta*
    - **Codice attività:** *Ristampa singola etichetta ondata*

1. Creare una seconda voce di menu e impostare i seguenti valori per la stessa:

    - **Nome voce di menu:** *Ristampa etichette (articolo)*
    - **Titolo:** *Ristampa etichetta ondata (articolo)*
    - **Modalità:** *Indiretta*
    - **Codice attività:** *Ristampa molteplici etichette ondata*
    - **Visualizza filtro raggruppamento elenco di lavori:** *Sì*
    - **Campo di raggruppamento sistema:** *ShipmentID*
    - **Campo di raggruppamento etichetta:** *ID spedizione*
    - **Modalità di stampa:** *Prodotto*

1. Nel riquadro azioni selezionare **Elenco campi** per aprire una pagina in cui è possibile selezionare i campi che verranno visualizzati per aiutare i lavoratori a identificare il rotolo di etichette corretto.
1. È possibile visualizzare fino a sette campi. Utilizzare gli elenchi a discesa per selezionare il campo visualizzato in ogni posizione disponibile. Lasciare vuoti tutti i campi non necessari. 

    Ecco un esempio:

    - **Campo di visualizzazione:** *LabelItemId*
    - **Campo di visualizzazione 2:** *LabelItemName*
    - **Campo di visualizzazione 3:** *InventQty*
    - **Campo di visualizzazione 4:** *LabelUnitId*

1. Chiudere la pagina.
1. Creare una terza voce di menu e impostare i seguenti valori per la stessa:

    - **Nome voce di menu:** *Ristampa etichette (enumerazione)*
    - **Titolo:** *Ristampa etichette ondata (enumerazione)*
    - **Modalità:** *Indiretta**
    - **Codice attività:** *Ristampa molteplici etichette ondata*
    - **Visualizza filtro raggruppamento elenco di lavori:** *Sì*
    - **Campo di raggruppamento sistema:** *ShipmentID*
    - **Campo di raggruppamento etichetta:** *ID spedizione*
    - **Modalità di stampa:** *Enumerazione*

1. Nel riquadro azioni selezionare **Elenco campi**, quindi utilizzare gli elenchi a discesa per selezionare i campi che verranno visualizzati per aiutare i lavoratori a identificare il rotolo di etichette corretto (ad esempio, *LabelItemId*, *LabelItemName*, *InventQty*, *LabelUnitId* e *NumberOfLabels*).
1. Chiudere la pagina.
1. Creare una quarta voce di menu e impostare i seguenti valori per la stessa:

    - **Nome voce di menu:** *Ristampa etichette (in base a ultima)*
    - **Titolo:** *Ristampa etichette ondata (in base a ultima)*
    - **Modalità:** *Indiretta*
    - **Codice attività:** *Ristampa molteplici etichette ondata*
    - **Visualizza filtro raggruppamento elenco di lavori:** *Sì*
    - **Campo di raggruppamento sistema:** *ShipmentID*
    - **Campo di raggruppamento etichetta:** *ID spedizione*
    - **Modalità di stampa:** *ID ultima etichetta ondata valida*

1. Nel riquadro azioni selezionare **Elenco campi**, quindi utilizzare gli elenchi a discesa per selezionare i campi che verranno visualizzati per aiutare i lavoratori a identificare il rotolo di etichette corretto (ad esempio, *LabelItemId*, *LabelItemName*, *InventQty*, *LabelUnitId* e *NumberOfLabels*).
1. Chiudere la pagina.

#### <a name="set-up-the-mobile-device-menu"></a>Configurare il menu per dispositivo mobile

Seguire questi passaggi per aggiungere le nuove voci di menu al menu dell'app di magazzino.

1. Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.
1. Selezionare un menu **In uscita** esistente.
1. Nell'elenco a sinistra, trovare le voci del menu di ristampa appena create, quindi utilizzare il pulsante freccia destra per aggiungerle all'elenco a destra.
1. Chiudere la pagina.

### <a name="use-cases"></a>Casi d'uso

I casi d'uso descritti qui forniscono esempi che mostrano come utilizzare le varie voci del menu per dispositivi mobili impostate per consentire ai lavoratori di ristampare le etichette ondata.

Prima di esaminare questi casi d'uso, devono essere presenti i seguenti prerequisiti:

- I dati dimostrativi devono essere installati ed è necessario selezionare la persona giuridica **USMF**.
- La stampa di etichette ondata deve essere configurata e alcune etichette devono essere generate, come descritto in [Configurare la stampa di etichette ondata](../warehousing/configure-wave-label-printing.md).

#### <a name="use-case-21-a-single-wave-label-is-scratched-and-must-be-reprinted"></a>Caso d'uso 2.1: una singola etichetta ondata è danneggiata e deve essere ristampata.

1. Accedere all'app di magazzino come utente che accede al magazzino *62* (nei dati demo standard, è possibile accedere utilizzando *62* come ID utente e *1* come password).
1. Andare a **In uscita \> Ristampa singola etichetta ondata**.
1. Immettere l'ID etichetta ondata o eseguirne la scansione.
1. Selezionare la stampante su cui ristampare.
1. Selezionare **OK** per confermare l'azione.

#### <a name="use-case-22-several-labels-for-boxes-of-the-same-item-were-damaged-and-must-be-reprinted-each-label-has-a-product-bar-code-but-no-enumeration-or-sscc-number"></a>Caso d'uso 2.2: diverse etichette per scatole dello stesso articolo sono danneggiate e devono essere ristampate. Ogni etichetta ha un codice a barre del prodotto, ma nessuna enumerazione o numero SSCC.

1. Accedere all'app di magazzino come utente che ha accesso al magazzino *62* (nei dati demo standard, è possibile accedere utilizzando *62* come ID utente e *1* come password).
1. Andare a **In uscita \> Ristampa etichette (articolo)**.
1. Immettere l'ID spedizione o eseguirne la scansione.
1. Selezionare il riquadro con il rotolo di etichette corretto da cui ristampare.
1. Eseguire la scansione del codice a barre del prodotto da un'etichetta esistente per confermare che è stata selezionata la riga corretta.
1. Immettere il numero di etichette da ristampare.
1. Selezionare la stampante su cui ristampare.
1. Selezionare **OK** per confermare l'azione.

#### <a name="use-case-23-several-labels-for-boxes-werent-printed-because-of-a-printer-jam-because-the-labels-have-enumeration-you-can-define-the-carton-range-to-reprint"></a>Caso d'uso 2.3: diverse etichette per scatole non sono state stampate a causa di un inceppamento della stampante. Poiché le etichette hanno un'enumerazione, è possibile definire l'intervallo di cartoni da ristampare.

1. Accedere all'app di magazzino come utente che ha accesso al magazzino *62* (nei dati demo standard, è possibile accedere utilizzando *62* come ID utente e *1* come password).
1. Andare a **In uscita \> Ristampa etichette (enumerazione)**.
1. Immettere l'ID spedizione o eseguirne la scansione.
1. Selezionare il riquadro con il rotolo di etichette corretto da cui ristampare.
1. Immettere il primo cartone per cui ristampare un'etichetta.
1. Immettere l'ultimo cartone per cui ristampare un'etichetta. In alternativa, lasciare vuoto questo campo per ristampare le etichette per tutti i cartoni dopo il primo cartone specificato.
1. Selezionare la stampante su cui ristampare.
1. Selezionare **OK** per confermare l'azione.

#### <a name="use-case-24-several-labels-for-boxes-werent-printed-because-of-a-printer-jam-the-last-good-label-has-a-wave-label-id-that-is-printed-as-a-bar-code"></a>Caso d'uso 2.4: diverse etichette per scatole non sono state stampate a causa di un inceppamento della stampante. L'ultima etichetta valida ha un ID etichetta ondata che viene stampato come codice a barre.

1. Accedere all'app di magazzino come utente che ha accesso al magazzino *62* (nei dati demo standard, è possibile accedere utilizzando *62* come ID utente e *1* come password).
1. Andare a **In uscita \> Ristampa etichette (in base a ultima)**.
1. Immettere l'ID spedizione o eseguirne la scansione.
1. Selezionare il riquadro con il rotolo di etichette corretto da cui ristampare.
1. Immettere l'ID dell'ultima etichetta ondata valida o eseguirne la scansione. L'app identifica l'etichetta successiva nella sequenza come il primo cartone per il quale verrà ristampata un'etichetta.
1. Immettere l'ultimo cartone per cui ristampare un'etichetta. In alternativa, lasciare vuoto questo campo per ristampare le etichette per tutti i cartoni dopo il primo cartone specificato.
1. Selezionare la stampante su cui ristampare.
1. Selezionare **OK** per confermare l'azione.

## <a name="scenario-3-short-pick-and-reprint"></a>Scenario 3: prelievo in difetto e ristampa

Prima di esaminare questo scenario, devono essere presenti i seguenti prerequisiti:

- I dati dimostrativi devono essere installati ed è necessario selezionare la persona giuridica **USMF**.
- La stampa di etichette ondata deve essere configurata e alcune etichette devono essere generate, come descritto in [Configurare la stampa di etichette ondata](../warehousing/configure-wave-label-printing.md).

### <a name="set-up-work-exceptions"></a>Impostare eccezioni lavoro

Le eccezioni lavoro controllano il comportamento del prelievo in difetto. Per impostare un'eccezione lavoro, effettuare le operazioni descritte di seguito.

1. Passare a **Gestione magazzino \> Impostazione \> Lavoro \> Eccezioni lavoro**.
1. Crea un record con le seguenti impostazioni:

    - **Codice di eccezione lavoro:** *Prelievo in difetto e stampa*
    - **Tipo di eccezione:** *Prelievo in difetto*
    - **Suggerisci ristampa etichette ondata:** *Sì*

### <a name="void-and-reprint-after-a-short-pick"></a>Annullare e ristampare dopo un prelievo in difetto

1. Accedere all'app di magazzino come utente che ha accesso al magazzino *62* (nei dati demo standard, è possibile accedere utilizzando *62* come ID utente e *1* come password).
1. Aprire un flusso di lavoro per il lavoro dell'ordine cliente creato al momento della stampa originale delle etichette ondata.
1. Selezionare **Prelievo in difetto**.
1. Selezionare il codice di eccezione lavoro creato per questo scenario.
1. Se è stata selezionata l'eccezione corretta, la casella di controllo **Annulla e ristampa** deve essere disponibile. Selezionare questa casella e confermare. Dopo la conferma, la sequenza di rotoli di etichette identificata dal campo **ID build etichetta** viene ricalcolata in base alla quantità della riga di lavoro modificata. Viene quindi ristampata sulla stampante specificata.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]