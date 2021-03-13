---
title: Materiali pericolosi in prodotti, ordini, spedizioni e carichi
description: In questo argomento viene illustrato come impostare le proprietà dei materiali pericolosi per i prodotti rilasciati, come stabilire limiti delle scorte per gli articoli pericolosi e come includere i materiali pericolosi in un ordine di vendita, spedizione o carico.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 3836273b1c782fe80172443f4d4c29001ccea83a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007668"
---
# <a name="hazardous-materials-in-products-orders-shipments-and-loads"></a>Materiali pericolosi in prodotti, ordini, spedizioni e carichi

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

In questo argomento viene illustrato come impostare le proprietà dei materiali pericolosi per i prodotti rilasciati, come stabilire limiti delle scorte per gli articoli pericolosi e come includere i materiali pericolosi in un ordine di vendita, spedizione o carico.

## <a name="set-hazardous-material-specifications-for-products"></a>Impostare le specifiche dei materiali pericolosi per i prodotti

Dopo aver definito una normativa sui materiali pericolosi e impostato i relativi codici di riferimento come descritto in [Impostare i materiali pericolosi](hazmat-setup.md), è possibile associare queste informazioni agli articoli rilasciati. Il testo di spedizione per i documenti di spedizione proviene dalle informazioni sui materiali pericolosi per gli articoli rilasciati.

Come parte del processo di associazione di un articolo rilasciato con un materiale pericoloso, è necessario specificare il codice normativa e il materiale. A un articolo possono essere associati codici normativa diversi, a seconda delle modalità di trasporto, ed è possibile associare più normative e codici materiale a ciascun articolo.

Per impostare un prodotto rilasciato come materiale pericoloso, attenersi alla seguente procedura.

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Selezionare o creare un prodotto per aprire la relativa pagina **Dettagli prodotto rilasciato**.
1. Nella Scheda dettaglio **Gestione articoli**, impostare l'opzione **Materiale pericoloso** su **Sì**. Questa impostazione identifica l'articolo come merce pericolosa e viene utilizzata durante la stampa della documentazione di spedizione.
1. Nel riquadro azioni, nella scheda **Gestione articoli**, nel gruppo **Conformità**, selezionare **Materiale pericoloso articolo**.
1. Compilare la pagina **Materiali pericolosi articolo** per l'articolo selezionato utilizzando i campi descritti nelle sottosezioni seguenti.

### <a name="item-hazardous-materials-header"></a>Intestazione materiali pericolosi articolo

La tabella seguente descrive i campi disponibili nella parte superiore della pagina **Materiali pericolosi articolo**.

| Campo | descrizione |
|---|---|
| Numero articolo | Il prodotto rilasciato con cui si sta lavorando. |
| Codice normativa | Selezionare la normativa sui materiali pericolosi che si applica al prodotto. La normativa definisce come viene creato il testo di spedizione stampato per un articolo e le modalità di consegna associate. Una volta assegnato, il codice non può essere modificato in questa pagina. Tuttavia, è possibile assegnare un nuovo codice normativa selezionando **Nuovo**. |
| Codice materiale | (Facoltativo) Selezionare il codice materiale pericoloso che si applica al prodotto. Il codice materiale fornisce un modello che include valori predefiniti per molti altri campi in questa pagina. Quando si seleziona un codice, tutte le sue specifiche sui materiali pericolosi vengono copiate nel prodotto corrente. Tuttavia, il sistema richiede prima di confermare che i dati del materiale dell'articolo siano stati inseriti dal codice materiale. |
| Codice gruppo | (Facoltativo) Selezionare il codice gruppo di classificazione materiale pericoloso che si applica al prodotto. Come per il campo **Codice materiale**, quando si seleziona un codice, tutte le sue specifiche sui materiali pericolosi vengono copiate nel prodotto corrente. Tuttavia, il sistema richiede prima di confermare che i dati del gruppo di classi dell'articolo siano stati inseriti dal codice gruppo. |

### <a name="descriptions-fasttab"></a><a name="hazmat-description"></a>Scheda dettaglio Descrizioni

Nella seguente tabella vengono illustrati i campi disponibili nella Scheda dettaglio **Descrizioni**.

| Campo | descrizione |
|---|---|
| Nome spedizione corretto | Immettere la descrizione standard per il materiale, come specificato dalla normativa applicabile. È possibile fornire le traduzioni per questo valore nella Scheda dettaglio **Traduzione del testo spedizione articolo**, come descritto nella sezione successiva. |
| Nome tecnico | Selezionare il nome comune o generico per il materiale. Questo nome potrebbe essere un nome che la tua azienda utilizza internamente per il materiale. |
| Non diversamente specificato | Selezionare questa casella di controllo per indicare che il valore **Nome spedizione corretto** è un nome di spedizione non diversamente specificato per l'articolo. Non diversamente specificato viene utilizzato per gruppi di sostanze chimiche e materiali simili che hanno usi finali specifici, ma che potrebbero non essere elencati per nome nella tabella delle sostanze pericolose in una normativa specifica. |

### <a name="item-ship-text-translation-fasttab"></a>Scheda dettaglio Traduzione del testo spedizione articolo

La scheda dettaglio **Traduzione del testo spedizione articolo** contiene una griglia che mostra le traduzioni dei valori **Nome spedizione corretto** definiti per la lingua principale nella scheda dettaglio **Descrizioni**. Queste traduzioni possono essere utilizzate nel testo della stampa della spedizione per una o più lingue aggiuntive.

Nella seguente tabella vengono illustrati i campi disponibili nella Scheda dettaglio **Traduzione del testo spedizione articolo**.


| Campo | descrizione |
|---|---|
| Lingua | Il codice della lingua utilizzato dalla riga. Per esempio, **pt-br** indica il portoghese brasiliano. |
| Testo stampa spedizione | Il valore **Nome spedizione corretto** tradotto nella lingua utilizzata dalla riga. |

Per aggiungere o modificare una traduzione, selezionare **Traduzioni** sopra la griglia per aprire la pagina **Traduzioni di testi**. Eseguire quindi uno dei passaggi seguenti:

- Per aggiungere una nuova traduzione nel riquadro azioni selezionare **Aggiungi**. Selezionare la lingua da aggiungere, quindi, nel campo **Testo tradotto** immettere il testo tradotto.
- Per modificare una traduzione esistente, selezionare una lingua di destinazione nel campo **Lingua** e modificare il testo tradotto nel campo **Testo tradotto**, come necessario.

### <a name="material-management-fasttab"></a><a name="material-management"></a>Scheda dettaglio Gestione materiali

Nella seguente tabella vengono illustrati i campi disponibili nella Scheda dettaglio **Gestione materiali**.

| Campo | descrizione |
|---|---|
| Classe | Selezionare la classe di materiale pericoloso a cui appartiene il prodotto, come definito dalla normativa a cui si fa riferimento per la conformità. È necessario assegnare sia una divisione che una classe a ogni prodotto che include materiali pericolosi. |
| descrizione | La descrizione definita per la classe selezionata nel campo **Classe**. Questo campo è di sola lettura. |
| Divisione | Selezionare la divisione di materiale pericoloso a cui appartiene il prodotto, come definito dalla normativa a cui si fa riferimento per la conformità. La divisione è un sottoinsieme della classe. È necessario assegnare sia una divisione che una classe a ogni prodotto che include materiali pericolosi. |
| Identificazione | Selezionare il codice di identificazione del materiale pericoloso. In genere, questo codice si basa su uno standard delle Nazioni Unite (ONU). |
| Gruppo di imballaggio | Selezionare il gruppo di imballaggio applicabile all'articolo corrente. |
| descrizione | La descrizione definita per il gruppo selezionato nel campo **Gruppo di imballaggio**. Questo campo è di sola lettura. |
| Descrizioni imballaggio | Selezionare il codice di descrizione dell'imballaggio applicabile. Questo codice fa riferimento a una descrizione che indica come il prodotto deve essere imballato. |
| Etichette materiali pericolosi | Selezionare un codice che faccia riferimento all'etichetta di merci pericolose applicabile che deve essere applicata al prodotto. |
| Quantità limitata | Impostare questa opzione su **Sì** per indicare il peso totale del prodotto incluso in ogni carico e in ciascuna riga di carico. |
| Quantità | Immettere la quantità di materiale pericoloso nel prodotto, nell'unità specificata. Questo valore viene utilizzato per calcolare il punteggio totale relativo ai materiali pericolosi per i carichi e le spedizioni che includono il prodotto. |
| Moltiplicatore | Immettere il moltiplicatore applicato quando viene calcolato il punteggio relativo ai materiali pericolosi per ciascuna riga di carico che include il prodotto. Questo valore è specificato dalla normativa applicabile, in base al tipo di materiale pericoloso contenuto nel prodotto. |
| Unità | Selezionare l'unità di misura che si applica alla quantità di materiale pericoloso nel prodotto, come specificato nel campo **Quantità**. Questo valore viene utilizzato per calcolare il punteggio totale relativo ai materiali pericolosi per i carichi e le spedizioni che includono il prodotto. |

#### <a name="how-the-hazardous-material-score-is-calculated"></a>Come viene calcolato il punteggio relativo ai materiali pericolosi

Molti dei valori specificati nella scheda dettaglio **Gestione materiali** per un prodotto vengono utilizzati per calcolare un *punteggio di materiale pericoloso* per ogni riga di carico che include quel prodotto. Il punteggio viene calcolato utilizzando la seguente formula:

Punteggio materiale pericoloso = *&lt;LineQty&gt;* × *&lt;HazmatQty&gt;* × *&lt;UnitConversion&gt;* × *&lt;Moltiplicatore&gt;*

Ecco la chiave per la formula:

- *&lt;LineQty&gt;* è la quantità di prodotto specificata per una riga di carico.
- *&lt;HazmatQty&gt;* è la quantità di materiale pericoloso specificata per un prodotto nel campo **Quantità** nella scheda dettaglio **Gestione materiali**.
- *&lt;UnitConversion&gt;* è un fattore di conversione per la conversione tra l'unità utilizzata per la quantità della riga di carico e l'unità specificata per un prodotto nel campo **Unità** nella scheda dettaglio **Gestione materiali**.
- *&lt;Moltiplicatore&gt;* è il moltiplicatore specificato per un prodotto nel campo **Moltiplicatore** nella scheda dettaglio **Gestione materiali**.

Questo punteggio viene riportato per ogni riga di carico che contiene un prodotto in cui sono specificati questi valori. Per ulteriori informazioni, vedere le sezioni [Spedizioni che includono materiali pericolosi](#hazmat-shipments) e [Carichi che includono materiali pericolosi](#hazmat-loads) più avanti in questo argomento.

#### <a name="how-the-hazardous-material-weight-is-calculated"></a>Come viene calcolato il peso relativo ai materiali pericolosi

Carichi e righe di carico che contengono prodotti in cui l'opzione **Quantità limitata** nella scheda dettaglio **Gestione materiali** è impostata su **Sì** mostrano il peso totale del materiale pericoloso, come descritto nelle sezioni [Spedizioni che includono materiali pericolosi](#hazmat-shipments) e [Carichi che includono materiali pericolosi](#hazmat-loads) più avanti in questo argomento. Il peso relativo al materiale pericoloso viene calcolato utilizzando la seguente formula:

Peso materiale pericoloso = *&lt;LineQty&gt;* × *&lt;ProductWeight&gt;* × *&lt;UnitConversion&gt;*

Ecco la chiave per la formula:

- *&lt;LineQty&gt;* è la quantità di prodotto specificata per una riga di carico.
- *&lt;ProductWeight&gt;* è il peso netto specificato per il prodotto, nell'unità di magazzino specificata per il prodotto.
- *&lt;UnitConversion&gt;* è un fattore di conversione per la conversione tra l'unità utilizzata per la quantità della riga di carico e l'unità di magazzino utilizzata per *&lt;ProductWeight&gt;*.

### <a name="transport-information-fasttab"></a>Scheda dettaglio Informazioni sul trasporto

Nella seguente tabella vengono illustrati i campi disponibili nella Scheda dettaglio **Informazioni sul trasporto**.

| Campo | descrizione |
|---|---|
| Categoria trasporto | Selezionare la categoria di trasporto correlata. |
| Codice tunnel | Selezionare il codice di restrizione del tunnel correlato per l'articolo. |
| Stivaggio materiali pericolosi | Selezionare il codice di riferimento utilizzato per la gestione dello stivaggio del trasporto marittimo quando l'articolo viene spedito via mare. |
| Tipo di aereo | Selezionare la restrizione dell'aero che si applica al materiale quando viene spedito per via aerea. |
| Imballaggio - Solo aereo da trasporto | In base al valore selezionato nel campo **Tipo di aero** selezionare il codice delle istruzioni di imballaggio che si applica quando il prodotto può essere spedito solo tramite aereo cargo. |
| Imballaggio - Aereo da trasporto e passeggeri | In base al valore selezionato nel campo **Tipo di aero** selezionare il codice delle istruzioni di imballaggio che si applica quando il prodotto può essere spedito solo tramite aereo cargo o passeggeri. |
| Stella IATA | Impostare questa opzione su **Sì** per indicare che le specifiche di trasporto aereo inserite in questa Scheda dettaglio sono correlate allo standard per le merci pericolose dell'Associazione internazionale per il trasporto aereo (IATA). Questo campo è fornito solo a scopo informativo. |
| Risposta all'emergenza | Selezionare il codice che fa riferimento alle istruzioni per la gestione del materiale in caso di emergenza. |

### <a name="environmental-information-fasttab"></a>Scheda dettaglio Informazioni sull'ambiente

Nella seguente tabella vengono illustrati i campi disponibili nella Scheda dettaglio **Informazioni sull'ambiente**.

| Campo | descrizione |
|---|---|
| Pericoloso per l'ambiente | Impostare questa opzione su **Sì** per indicare che il prodotto è pericoloso per l'ambiente. Utilizzare questo campo per la creazione di report. |
| Inquinante marino | Impostare questa opzione su **Sì** per indicare che il prodotto è inquinante per il mare. Utilizzare questo campo per la creazione di report. |

## <a name="set-stock-limits-for-hazardous-products"></a><a name="stock-limits"></a>Impostare i limiti delle scorte per prodotti pericolosi

Per motivi di sicurezza, potrebbe essere necessario limitare la quantità totale di un determinato prodotto che può essere immagazzinato in un unico luogo. Per impostare i limiti delle scorte per un prodotto rilasciato, effettuare le operazioni indicate di seguito.

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Selezionare un prodotto per aprire la relativa pagina **Dettagli prodotto rilasciato**.
1. Nel riquadro azioni, nella scheda **Gestione articoli**, nel gruppo **Conformità**, selezionare **Dettagli dichiarazioni**.
1. Nei campi **Limite scorte pericolose** e **Limite avvertenza di pericolo**, impostare i valori appropriati per il prodotto selezionato.

Il report **Limite delle scorte di materiali pericolosi** consente di monitorare i livelli delle scorte di materiali pericolosi nelle ubicazioni del magazzino, per assicurarsi che rimangano entro i limiti di sicurezza stabiliti qui. Per ulteriori informazioni, vedere [Report sui limiti delle scorte di materiali pericolosi](hazmat-reports.md#stock-limit-report).

## <a name="sales-order-transactions-that-include-hazardous-materials"></a>Transazioni di ordini di vendita che includono materiali pericolosi

Per includere un prodotto classificato come materiale pericoloso in un ordine di vendita, è necessario associare il corriere di spedizione pertinente all'ordine di vendita. Aprire l'ordine di vendita e quindi nella scheda dettaglio **Consegna** impostare i campi **Vettore spedizione** e **Servizio trasporto** come necessario.

Il vettore spedizione è anche associato alla modalità di consegna. Pertanto, è necessario assicurarsi che queste informazioni siano allineate con la normativa sui materiali pericolosi. In altre parole, la modalità di consegna specificata nella normativa sui materiali pericolosi deve corrispondere alle specifiche nell'intestazione dell'ordine di vendita. In questo modo, la normativa, il vettore di spedizione e il servizio sono collegati alle righe di spedizione utilizzate in un ordine di vendita.

Dopo che un ordine di vendita è stato finalizzato e pronto per essere spedito, può essere rilasciato al magazzino per indicare il trasferimento tra le operazioni di vendita e di magazzino.

## <a name="shipments-that-include-hazardous-materials"></a><a name="hazmat-shipments"></a>Spedizioni che includono materiali pericolosi

### <a name="view-hazardous-material-scores-for-each-shipment-line"></a>Visualizzare i punteggi relativi ai materiali pericolosi per ciascuna riga di spedizione

La pagina **Dettagli spedizione** di una spedizione mostra il peso totale del materiale pericoloso e i valori in punti calcolati per ciascuna riga di carico inclusa in quella spedizione. Per visualizzare i punteggi e i pesi, seguire questi passaggi.

1. Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.
1. Selezionare una spedizione per aprire la relativa pagina **Dettagli spedizione**.
1. Nella scheda dettaglio **Righe di carico** controllare le righe. Per ogni riga, sono visualizzati i calcoli dei materiali pericolosi nei seguenti campi:

    - **Punti materiale pericoloso** - Questo campo mostra il punteggio relativo al materiale pericoloso per la riga di carico. Il valore viene calcolato in base alle regole e ai valori stabiliti per la normativa applicabile e nella configurazione del prodotto rilasciato. Il calcolo include la quantità sulla riga di carico e fa riferimento al moltiplicatore nell'[impostazione della gestione dei materiali](#material-management) per il prodotto rilasciato.
    - **Peso netto in quantità limitata** - Per i prodotti contrassegnati come prodotti in quantità limitata a causa del loro contenuto di materiali pericolosi, questo campo mostra il peso netto totale del contenuto pericoloso incluso nella riga di carico. Il calcolo si basa sui prodotti contrassegnati come materiali pericolosi nell'impostazione del prodotto rilasciato. Se un articolo è contrassegnato come articolo a quantità limitata, il calcolo include la quantità su ciascuna riga di carico e fa riferimento al peso nell'[impostazione della gestione dei materiali](#material-management) per il prodotto rilasciato.

### <a name="check-for-compatibility-among-hazardous-materials-that-are-included-in-a-shipment"></a>Verificare la compatibilità tra i materiali pericolosi inclusi in una spedizione

Il sistema può valutare se tutti i materiali pericolosi inclusi in una spedizione sono idonei per essere spediti insieme. Per valutare la compatibilità, il sistema controlla il gruppo di compatibilità assegnato a ciascun prodotto incluso nella spedizione. Per ulteriori informazioni, vedere [Gruppi di compatibilità di materiali pericolosi](hazmat-setup.md#compatibility-groups).

Per eseguire il controllo di compatibilità attenersi a questi passaggi.

1. Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.
1. Selezionare una spedizione per aprire la relativa pagina **Dettagli spedizione**.
1. Nel riquadro azioni della scheda **Spedizioni** del gruppo **Azioni**, selezionare **Controllo compatibilità**.

Viene inviato un messaggio contenente i risultati del controllo.

## <a name="loads-that-include-hazardous-materials"></a><a name="hazmat-loads"></a>Carichi che includono materiali pericolosi

### <a name="view-hazardous-material-scores-for-each-load-line"></a>Visualizzare i punteggi relativi ai materiali pericolosi per ciascuna riga di carico

La pagina **Dettagli carico** di un carico mostra il peso totale del materiale pericoloso e i valori in punti calcolati per il carico e ciascuna riga di carico. Per visualizzare i punteggi e i pesi, seguire questi passaggi.

1. Vai a **Gestione magazzino \> Spedizioni \> Tutti i carichi**.
1. Selezionare un carico per aprire la relativa pagina **Dettagli carico**. È anche possibile aprire i dettagli del carico selezionando un collegamento da una spedizione correlata.
1. Nella scheda dettaglio **Carico** è possibile rivedere i punteggi e i pesi totali dei materiali pericolosi per l'intero carico controllando i seguenti campi:

    - **Punti materiale pericoloso** - Questo campo mostra il punteggio relativo al materiale pericoloso per il carico. Il valore viene calcolato in base alle regole e ai valori stabiliti per la normativa applicabile e nella configurazione del prodotto rilasciato. Il calcolo include la quantità del carico e fa riferimento al moltiplicatore nell'[impostazione della gestione dei materiali](#material-management) per il prodotto rilasciato.
    - **Peso netto in quantità limitata** - Per i prodotti contrassegnati come prodotti in quantità limitata a causa del loro contenuto di materiali pericolosi, questo campo mostra il peso netto totale del contenuto pericoloso incluso nel carico. Il calcolo si basa sui prodotti contrassegnati come materiali pericolosi nell'impostazione del prodotto rilasciato. Se un articolo è contrassegnato come articolo a quantità limitata, il calcolo include la quantità su ogni carico e fa riferimento al peso nell'[impostazione della gestione dei materiali](#material-management) per il prodotto rilasciato.

1. Per rivedere i punteggi e i pesi per le singole righe, selezionare la scheda dettaglio **Righe di carico**. I valori forniti per ciascuna riga sono simili ai valori forniti per l'intero carico, come descritto nel passaggio precedente.

### <a name="check-for-compatibility-among-hazardous-materials-that-are-included-in-a-load"></a>Verificare la compatibilità tra i materiali pericolosi inclusi in un carico

Il sistema può valutare se tutti i materiali pericolosi inclusi in un carico sono idonei per essere spediti insieme. Per valutare la compatibilità, il sistema controlla il gruppo di compatibilità assegnato a ciascun prodotto incluso nel carico. Per ulteriori informazioni, vedere [Gruppi di compatibilità di materiali pericolosi](hazmat-setup.md#compatibility-groups).

Per eseguire il controllo di compatibilità attenersi a questi passaggi.

1. Vai a **Gestione magazzino \> Spedizioni \> Tutti i carichi**.
1. Selezionare una spedizione per aprire la relativa pagina **Dettagli carico**. È anche possibile aprire i dettagli del carico selezionando un collegamento da una spedizione correlata.
1. Nel riquadro azioni della scheda **Carichi** del gruppo **Azioni**, selezionare **Controllo compatibilità**.

Viene inviato un messaggio contenente i risultati del controllo.
