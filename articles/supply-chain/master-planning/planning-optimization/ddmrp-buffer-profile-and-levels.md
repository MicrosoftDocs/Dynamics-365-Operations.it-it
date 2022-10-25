---
title: Profilo e livelli di buffer
description: Questo articolo fornisce informazioni sui profili e i livelli di buffer, che determinano i livelli di scorte minimo e massimo da mantenere per ogni punto di disaccoppiamento.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ReqItemDecoupledLeadTime
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: d254b949d31d0b15141646503c64760062b77fc7
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689148"
---
# <a name="buffer-profile-and-levels"></a>Profilo e livelli di buffer

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Dopo aver identificato i punti di disaccoppiamento (articoli chiave conservati strategicamente in magazzino), occorre decidere quante scorte (buffer) di ognuno dovranno essere conservate. Questa attività è il secondo passaggio di Demand Driven Materials Resource Planning (DDMRP).

## <a name="buffer-levels-and-zones"></a>Livelli e zone di buffer

In DDMRP, ogni buffer delle scorte è definito usando tre valori: quantità minima, quantità massima e punto di riordino. Questi valori stabiliscono tre zone differenti, identificate dai seguenti codici colore:

- **Zona rossa**: l'area al di sotto della quantità minima. La quantità minima è anche indicata come "sopra il rosso" e la strategia di pianificazione deve essere progettata per assicurarsi che i livelli di scorte siano sempre al di sopra di questo punto.
- **Zona gialla**: l'area tra la quantità minima e il punto di riordino. Il punto di riordino è anche indicato come "sopra il giallo". Quando viene raggiunto questo punto, il sistema deve provvedere al riordino.
- **Zona verde**: l'area tra il punto di riordino e la quantità massima. La quantità massima è anche indicata come "sopra il verde". Questo punto è il livello massimo di rifornimento delle scorte.

L'immagine seguente mostra le tre zone colorate e la loro relazione con la quantità minima, la quantità massima e il punto di riordino.

![Livelli e zone di buffer DDMRP.](media/ddmrp-buffer-levels.png "Livelli e zone di buffer DDMRP")

## <a name="calculating-the-buffer-zones"></a>Calcolo delle zone di buffer

Questa sezione spiega come viene calcolata l'altezza di ciascuna zona di buffer.

In genere viene calcolata per prima la zona gialla. Questa zona rappresenta la quantità consumata dal momento dell'invio dell'ordine all'arrivo dello stesso. In altre parole, è il consumo previsto durante il lead time di rifornimento. Si calcola con la seguente equazione:

- **Zona gialla** = *Utilizzo giornaliero medio (ADU)* × *Lead time disaccoppiato*

Il *lead time disaccoppiato* rappresenta il tempo necessario per produrre o ricevere un articolo se i punti di disaccoppiamento sono sempre in magazzino. In genere è molto più breve rispetto al *lead time cumulativo* tradizionalmente usato nella pianificazione generale. È fondamentale definire impostazioni di buffer corrette per far sì che i punti di disaccoppiamento siano sempre presenti in magazzino ma senza avere scorte in eccesso.

La zona rossa si calcola con le seguenti equazioni:

- **Base rossa** = *ADU* × *Lead time disaccoppiato* × *Fattore di lead time*
- **Sicurezza rossa** = *Base rossa* × *Fattore di variabilità*
- **Zona rossa** = *Base rossa* + *Sicurezza rossa*

La zona verde viene calcolata come risultato massimo delle seguenti tre equazioni:

- *Quantità ordine minima*
- *ADU* × *Ciclo ordine*
- *ADU* × *Lead time disaccoppiato* × *Fattore di lead time*

## <a name="calculating-average-daily-usage"></a>Calcolo dell'utilizzo giornaliero medio

Il sistema usa uno dei seguenti tre approcci per calcolare l'importo consumato giornalmente:

- **Utilizzo giornaliero medio (passato)**: questo approccio si basa sul consumo passato effettivo.
- **Utilizzo giornaliero medio (futuro)**: questo approccio si basa sul consumo futuro previsto.
- **Utilizzo giornaliero medio (misto)**: questo approccio si basa su un mix ponderato di consumo passato e previsto.

### <a name="average-daily-usage-past"></a>Utilizzo giornaliero medio (passato)

L'ADU passato viene calcolato come media aggiungendo le quantità usate ogni giorno per un numero specificato di giorni passati e dividendo poi il totale per il numero di giorni. L'immagine seguente mostra il funzionamento di questo approccio quando il calcolo prende in esame tre giorni passati.

![Grafico dell'utilizzo giornaliero medio (passato)](media/ddmrp-adu-past.png "Grafico dell'utilizzo giornaliero medio (passato)")

Nell'immagine seguente, se oggi è la mattina dell'11 giugno, l'ADU per i tre giorni precedenti (8, 9 e 10 giugno) è 21.

- **ADU (passato)** = (29 + 11 + 23) ÷ 3 = 21

Per il calcolo dell'utilizzo giornaliero medio (passato) vengono prese in considerazione le seguenti transazioni:

- Transazioni che diminuiscono la quantità dell'articolo (nella tabella `inventtrans` dove la quantità è minore di zero)
- Transazioni con stato di *Su ordine*, *Ordinato riservato*, *Fisico riservato*, *Scelto*, *Dedotto*, o *Venduto*
- Transazioni datate all'interno del periodo a ritroso scelto (l'utilizzo giornaliero medio del periodo passato)
- Transazioni diverse da lavoro di magazzino, quarantena, offerte di vendita o rendiconti (`WHSWork`, `WHSQuarantine`, `SalesQuotation`, o `Statement`)
- Transazioni diverse dai giornali di registrazione di trasferimento che rientrano nella stessa dimensione di copertura

### <a name="average-daily-usage-forward"></a>Utilizzo giornaliero medio (futuro)

Per un nuovo prodotto, si potrebbero non avere dati sull'utilizzo passato. Pertanto, si potrebbe usare invece l'ADU previsto in futuro (ad esempio, in base alla domanda prevista). L'immagine seguente mostra il funzionamento di questo approccio quando il calcolo prende in esame tre giorni futuri (incluso oggi).

![Grafico dell'utilizzo giornaliero medio (futuro)](media/ddmrp-adu-forward.png "Grafico dell'utilizzo giornaliero medio (futuro)")

Nell'immagine seguente, se oggi è la mattina dell'11 giugno, l'ADU per i tre giorni successivi (11, 12 e 13 giugno) è 21,66.

- **ADU (futuro)** = (18 + 18 + 29) ÷ 3 = 21,66

Per il calcolo dell'utilizzo giornaliero medio (futuro) vengono prese in considerazione le seguenti transazioni:

- Transazioni di previsione per l'articolo in cui è selezionata la previsione nel piano principale
- Transazioni datate all'interno del periodo in avanti scelto (l'utilizzo giornaliero medio del periodo futuro)

### <a name="average-daily-usage-blended"></a>Utilizzo giornaliero medio (misto)

L'ADU misto combina l'utilizzo medio passato e l'utilizzo medio futuro, come mostrato nell'immagine seguente.

![Grafico dell'utilizzo giornaliero medio (misto)](media/ddmrp-adu-blended.png "Grafico dell'utilizzo giornaliero medio (misto)")

Nell'immagine seguente, se oggi è la mattina dell'11 giugno, l'ADU misto per i tre giorni precedenti e i tre giorni successivi (8-13 giugno) è 21,33.

- **ADU misto** = (*ADU passato* + *ADU futuro*) ÷ 2<br>= (21 + 21,66) ÷ 2<br>= 21,33

## <a name="buffer-calculation-factors"></a>Fattori di calcolo del buffer

Per ogni articolo, è possibile definire due fattori per rettificare le dimensioni delle zone rossa e verde. In questo modo, è possibile compensare il lead time previsto e la variabilità della domanda.

![Fattori di variabilità del lead time.](media/ddmrp-zone-factors.png "Fattori di variabilità del lead time")

Il primo fattore è il *fattore di lead time*. Il valore è un valore decimale da 0 a 1. Maggiore è il lead time, minore deve essere il valore. Il Demand Driven Institute consiglia i seguenti intervalli:

- **Lead time lungo:** 0,20 - 0,40
- **Lead time medio:** 0,41 - 0,60
- **Lead time breve:** 0,61 - 1

Il secondo fattore è il *fattore di variabilità*. Il valore è un valore decimale da 0 a 1. Maggiore è la variabilità della domanda, minore deve essere il valore. Il Demand Driven Institute consiglia i seguenti intervalli:

- **Variabilità bassa:** 0,20 - 0,40
- **Variabilità media:** 0,41 - 0,60
- **Variabilità alta:** 0,61 - 1

## <a name="buffer-calculation-examples"></a>Esempi di calcolo del buffer

Questo esempio riprende l'esempio di produzione di cuscini fornito in [Posizionamento delle scorte](ddmrp-inventory-positioning.md). In quell'esempio, erano stati selezionati punti di disaccoppiamento che riducevano il lead time da 21 a 5 giorni, come mostrato nell'immagine seguente.

![Esempio di lead time disaccoppiato.](media/ddmrp-bom-decoupled-lead-time-example.png "Esempio di lead time disaccoppiato")

Ai fini di questo esempio, si presuppone che l'ADU sia stato calcolato in 23 pezzi e, come mostrato nella figura precedente, il lead time disaccoppiato è di cinque giorni. Usando questi valori, è possibile calcolare la zona gialla mediante la seguente equazione:

- **Zona gialla** = *ADU* × *Lead time disaccoppiato* = 115

![Esempio di calcolo della zona gialla.](media/ddmrp-example-calc-yellow.png "Esempio di calcolo della zona gialla")

Il calcolo della zona rossa è simile a quello della zona gialla, ma tiene conto del lead time e della variabilità. Ai fini di questo esempio, si presuppone di aver osservato un lead time medio (fattore = 0,50) e un'elevata variabilità della domanda (fattore = 0,80). Usando questi valori assieme ai componenti dell'equazione della zona gialla, è possibile calcolare la zona rossa mediante le seguenti equazioni:

- **Base rossa** = *ADU* × *Lead time disaccoppiato* × *Fattore di lead time* = 57,5
- **Sicurezza rossa** = *Base rossa* × *Fattore di variabilità* = 46
- **Zona rossa** = *Base rossa* + *Sicurezza rossa* = 103,5

Il sistema arrotonderà la zona rossa a 104 pezzi (ea), perché i pezzi vengono conteggiati in numeri interi.

![Esempio di calcolo della zona rossa.](media/ddmrp-example-calc-red.png "Esempio di calcolo della zona rossa")

Anche il calcolo della zona verde include i componenti dell'equazione della zona gialla, ma ammette una dimensione minima dell'ordine, un ciclo dell'ordine e un fattore di lead time. Ai fini di questo esempio, si presuppone che non vi sia ciclo dell'ordine (pertanto, non vi sono vincoli temporali in termini di frequenza di ordinazione) e che la quantità minima dell'ordine sia di 10 pezzi. La zona verde viene quindi calcolata come risultato massimo delle seguenti tre equazioni:

- *Quantità minima ordine* = 10
- *ADU* × *Ciclo ordine* = 0
- *ADU* × *Lead time disaccoppiato* × *Fattore di lead time* = 57,5

Il sistema arrotonderà la zona verde a 58 pezzi (ea), perché i pezzi vengono conteggiati in numeri interi.

![Esempio di calcolo della zona verde.](media/ddmrp-example-calc-green.png "Esempio di calcolo della zona verde")

Nell'immagine seguente vengono riepilogati i risultati del calcolo delle zone usando il grafico a imbuto spesso adottato in DDMRP.

![Riepilogo dei risultati del calcolo delle zone.](media/ddmrp-example-calc-summary.png "Riepilogo dei risultati del calcolo delle zone")

## <a name="dynamic-adjustments"></a><a name="dynamic-adjustments"></a>Rettifiche dinamiche

Le rettifiche dinamiche permettono di applicare un *fattore di rettifica della domanda* durante i periodi di bassa domanda o di domanda elevata. Il fattore moltiplica l'ADU in tutti i calcoli per il periodo selezionato. Le zone di buffer vengono quindi modificate di conseguenza. In genere questo fattore viene applicato dopo la generazione dei valori di buffer iniziali, in modo da ottenere un affinamento nel tempo e in risposta al mutare delle condizioni. Questa attività è il terzo passaggio di DDMRP.

Ad esempio, potrebbe esserci una maggiore domanda del prodotto cuscino in agosto, poiché la gente va in vacanza. Pertanto, si può prevedere un incremento delle vendite. In questo caso, è possibile modificare il valore **Fattore di rettifica della domanda** per il prodotto in *1,5* per tutte le settimane di agosto.

Così facendo, è possibile calcolare i valori di buffer nel tempo e rettificarli in base a informazioni aggiuntive rispetto a quelle disponibili nel sistema. In un'implementazione DDMRP completa, i nuovi valori di buffer verranno calcolati ogni giorno mediante un processo batch e automaticamente accettati. Si eseguirà quindi una pianificazione come processo batch e si rivedranno gli ordini pianificati ogni giorno per riempire i buffer.

## <a name="implement-buffers-in-supply-chain-management"></a>Implementazione dei buffer in Supply Chain Management

Questa sezione descrive come implementare la strategia della zona di buffer in Microsoft Dynamics 365 Supply Chain Management. Si presume che l'analisi e i calcoli illustrati nella prima parte di questo articolo siano già stati portati a termine.

### <a name="set-up-buffers-for-a-decoupling-point-item"></a><a name="set-up-buffers"></a>Impostare i buffer per un articolo punto di disaccoppiamento

Attenersi ai seguenti passaggi per impostare i valori di buffer per un punto di disaccoppiamento.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Selezionare un articolo rilasciato impostato come punto di disaccoppiamento. (Per ulteriori informazioni, vedere [Posizionamento delle scorte](ddmrp-inventory-positioning.md).)
1. Nella scheda **Piano** del riquadro Azioni selezionare **Copertura articolo**.
1. Nella pagina **Copertura articoli** selezionare un record di copertura articoli che crea un punto di disaccoppiamento. (Questo record mostrerà il nome di un gruppo di copertura impostato per creare punti di disaccoppiamento.)
1. Selezionare la scheda **Generale**.
1. Se si desidera che il sistema ricalcoli i valori di buffer ogni giorno oppure ogni settimana in base allo storico delle vendite, alle previsioni e alle impostazioni del gruppo di copertura, attenersi alla seguente procedura:

    1. Impostare l'opzione **Valori di buffer nel tempo** su *Sì*.
    1. Una casella di messaggio notifica che, se si procede, le impostazioni di buffer manuali (**Minimo**, **Punto di riordino** e **Massimo**) verranno reimpostate. Selezionare **Sì** per conservare la nuova impostazione.

    In alternativa, se si preferisce calcolare o immettere le impostazioni di buffer una volta sola, attenersi alla seguente procedura:

    1. Impostare l'opzione **Valori di buffer nel tempo** su *No*.
    1. Impostare i campi **Minimo**, **Punto di riordino** e **Massimo** sui valori di buffer calcolati per l'articolo, come descritto in precedenza in questo articolo.

1. Impostare i seguenti campi per completare l'impostazione dei calcoli DDMRP per l'articolo:

    - **Ciclo ordine**: specificare il numero di giorni che devono intercorrere tra gli ordini di acquisto per l'articolo. Impostare il valore su *0* (zero) se non esistono restrizioni per l'ordine. Questo campo incide sul buffer di quantità massima, come trattato in precedenza in questo articolo.
    - **Utilizzo giornaliero medio**: facoltativamente, è possibile immettere un ADU stimato per l'articolo. Questo campo è fornito solo a scopo informativo. In genere, il valore viene automaticamente calcolato come parte dei calcoli del buffer.
    - **Soglia picco ordine**: specificare l'ordine minimo di vendite giornaliere dell'articolo affinché venga considerato un picco di vendite (domanda insolitamente elevata). Il sistema usa questo campo per aumentare la quantità di riordino degli ordini pianificati nei periodi di domanda elevata. Per ulteriori informazioni, vedere [Pianificazione basata sulla domanda](ddmrp-planning.md).

### <a name="calculate-or-enter-decoupled-lead-times"></a><a name="calc-lead-time"></a>Calcolare o immettere lead time disaccoppiati

Per gli articoli per i quali si sceglie di consentire al sistema di [calcolare automaticamente le zone di buffer](#set-up-buffers), attenersi alla seguente procedura per calcolare o immettere lead time disaccoppiati per un articolo del punto di disaccoppiamento.

1. Aprire la pagina **Copertura articoli** per l'articolo del punto di disaccoppiamento. (Per ulteriori informazioni, vedere [Impostare i buffer per un articolo punto di disaccoppiamento](#set-up-buffers).)
1. Selezionare un record di copertura articoli che crea un punto di disaccoppiamento.
1. Selezionare la scheda **Valori buffer**.
1. Se nella griglia non è visualizzato alcun periodo di tempo, nel riquadro Azione, nella scheda **Valori buffer**, selezionare **Aggiungi periodi di tempo**. La griglia viene automaticamente compilata con le righe per ciascun periodo di tempo giornaliero o settimanale, a seconda se il campo **Periodo minimo, massimo e punto di riordino** per il [gruppo di copertura](ddmrp-inventory-positioning.md) è impostato su *Giornaliero* o su *Settimanale*. Verrà aggiunto un numero di righe sufficiente per raggiungere l'intervallo temporale specificato per il gruppo di copertura assegnato all'articolo.
1. Selezionare il periodo di tempo per il quale si desidera calcolare il lead time disaccoppiato. (In genere, questo periodo di tempo è il periodo che include la data odierna.)
1. Nella scheda **Valori buffer** del riquadro Azioni selezionare **Calcola lead time disaccoppiato**.
1. Nella finestra di dialogo **Calcola lead time disaccoppiato** impostare i seguenti campi:

    - **Distinta base**: selezionare la distinta base su cui dovrà essere eseguito il calcolo.
    - **Data**: selezionare la data in cui dovrà essere eseguito il calcolo. Il set di distinte base disponibili verrà filtrato in modo da visualizzare soltanto le distinte base attive per la data selezionata.
    - **Quantità**: immettere la quantità per la quale dovrà essere eseguito il calcolo. Il set di distinte base disponibili verrà filtrato in modo da visualizzare soltanto le distinte base applicabili alla quantità specificata.

1. Selezionare **OK** per eseguire il calcolo e chiudere la finestra di dialogo **Calcola lead time disaccoppiato**. La colonna **Lead time disaccoppiato** per il periodo di tempo selezionato ora mostra il valore calcolato.

### <a name="calculate-or-enter-average-daily-usage"></a><a name="calc-adu"></a>Calcolare o immettere l'utilizzo giornaliero medio

Per gli articoli per i quali si sceglie di consentire al sistema di [calcolare automaticamente le zone di buffer](#set-up-buffers), attenersi alla seguente procedura per calcolare o immettere l'ADU per un articolo del punto di disaccoppiamento.

1. Aprire la pagina **Copertura articoli** per l'articolo del punto di disaccoppiamento. (Per ulteriori informazioni, vedere [Impostare i buffer per un articolo punto di disaccoppiamento](#set-up-buffers).)
1. Selezionare un record di copertura articoli che crea un punto di disaccoppiamento.
1. Selezionare la scheda **Valori buffer**.
1. Se nella griglia non è visualizzato alcun periodo di tempo, nel riquadro Azione, nella scheda **Valori buffer**, selezionare **Aggiungi periodi di tempo**. La griglia viene automaticamente compilata con le righe per ciascun periodo di tempo giornaliero o settimanale, a seconda se il campo **Periodo minimo, massimo e punto di riordino** per il [gruppo di copertura](ddmrp-inventory-positioning.md) è impostato su *Giornaliero* o su *Settimanale*. Inoltre, i valori predefiniti per i campi **Fattore di lead time** e **Fattore di variabilità** vengono presi dal gruppo di copertura. È possibile modificare questi valori per ogni riga in base alle esigenze.
1. Selezionare un periodo di tempo per il quale si desidera calcolare l'ADU.
1. Nella scheda **Valori buffer** del riquadro Azioni selezionare **Calcola utilizzo giornaliero medio**. Il sistema tenta di raccogliere i dati richiesti per il calcolo dell'ADU, in base a quanto definito per il [gruppo di copertura](ddmrp-inventory-positioning.md).
1. Eseguire uno dei passaggi riportati di seguito.

    - Se i dati obbligatori non sono disponibili, i risultati del calcolo vengono aggiunti alla colonna **Utilizzo medio giornaliero**. In questo caso, non è necessaria alcuna azione.
    - Se i dati obbligatori non sono disponibili, non verrà automaticamente aggiunto alcun valore. In questo caso, immettere manualmente i valori stimati per ogni riga per cui si prevede di calcolare i valori di buffer.

### <a name="calculate-and-apply-buffer-values"></a>Calcolare e applicare i valori di buffer

Per gli articoli per i quali si sceglie di consentire al sistema di [calcolare automaticamente le zone di buffer](#set-up-buffers), è possibile attivare manualmente il calcolo dei valori di buffer mediante la seguente procedura.

1. Per l'articolo del punto di disaccoppiamento pertinente, [configurare il calcolo del buffer](#set-up-buffers), [calcolare o immettere i lead time disaccoppiati](#calc-lead-time) e [calcolare o immettere l'utilizzo giornaliero medio](#calc-adu) per tutti i periodi di tempo pertinenti, come descritto in precedenza in questo articolo.
1. Aprire la pagina **Copertura articoli** per l'articolo del punto di disaccoppiamento.
1. Selezionare la scheda **Valori buffer**, che dovrebbe già mostrare un elenco di periodi di tempo.
1. Selezionare il periodo di tempo per il quale si desidera calcolare i valori di buffer. (In genere, questo periodo di tempo include il giorno di oggi.) La riga selezionata deve già avere valori diversi da zero nelle colonne **Utilizzo giornaliero medio** e **Lead time disaccoppiato**.
1. Modificare il campo **Fattore di rettifica della domanda** per una o più righe, come richiesto. Il sistema applicherà questo fattore al valore **Utilizzo giornaliero medio** in tutti i calcoli di buffer in cui viene usato il valore. Questo fattore permette di rettificare la fluttuazione della domanda in base alla data (ad esempio, per le vacanze o per gli articoli stagionali).
1. Nella scheda **Valori buffer** del riquadro Azioni selezionare **Calcola quantità minima, massime e punto di riordino**. Le colonne **Minimo calcolato**, **Punto di riordino calcolato** e **Massimo calcolato** nella griglia della pagina **Copertura articoli** vengono automaticamente calcolate e compilate.
1. Una volta rivisti, i valori calcolati devono essere applicati. In caso contrario, non avranno effetto. Quando si applica un calcolo per una o più righe, i valori dei campi **Minimo calcolato**, **Riordino calcolato** e **Massimo calcolato** vengono copiati rispettivamente nelle colonne **Minimo**, **Punto di riordino** e **Massimo**. Nel riquadro Azioni, nella scheda **Valori buffer**, nel gruppo **Intraprendi azione** selezionare uno dei pulsanti seguenti:

    - **Accetta tutti i calcoli**: applica tutti i valori calcolati nella griglia.
    - **Accetta calcoli per le righe selezionate**: applica i valori calcolati solo per le righe selezionate.
    - **Elimina tutti i calcoli**: elimina tutti i valori calcolati per le quantità minime, le quantità massime e i punti di riordino nella griglia.
    - **Elimina calcoli per le righe selezionate**: elimina tutti i valori calcolati per le quantità minime, le quantità massime e i punti di riordino per le righe selezionate.

### <a name="schedule-automatic-buffer-value-calculations"></a>Pianificare calcoli automatici dei valori di buffer

Una volta completamente configurate le impostazioni DDMRP e confermato il corretto funzionamento, è probabilmente il momento di impostare un processo batch per ricalcolare periodicamente l'ADU e i valori di buffer correlati secondo necessità, in base ai dati del consumo effettivo e/o alle previsioni aggiornate. Questa procedura si applica soltanto agli articoli per i quali si sceglie di consentire al sistema di [calcolare automaticamente le zone di buffer](#set-up-buffers).

Seguire questi passaggi per pianificare calcoli automatici dei valori di buffer.

1. Andare a **Pianificazione generale \> Pianificazione generale \> DDMRP \> Calcola valori buffer**.
1. Nella finestra di dialogo **Calcola valori buffer** impostare i seguenti campi:

    - **Calcola utilizzo giornaliero medio**: impostare questa opzione su *Sì* per ricalcolare l'ADU degli articoli del punto di disaccoppiamento ogni volta che viene eseguito il processo. Impostarla su *No* per ignorare questo calcolo. Di solito, questa opzione deve essere impostata su *Sì*.
    - **Calcola lead time disaccoppiato**: impostare questa opzione su *Sì* per ricalcolare i lead time disaccoppiati ogni volta che viene eseguito il processo. Impostarla su *No* per ignorare questo calcolo. Di solito, questa opzione deve essere impostata su *Sì*.
    - **Calcola valori buffer**: impostare questa opzione su *Sì* per ricalcolare i valori di buffer ogni volta che viene eseguito il processo. Impostarla su *No* per ignorare questo calcolo. Di solito, questa opzione deve essere impostata su *Sì*.
    - **Accetta calcolo per minimo, massimo e punto di riordino**: impostare questa opzione su *Sì* per approvare e applicare automaticamente i valori di buffer ricalcolati ogni volta che viene eseguito il processo. Impostarla su *No* se non si desidera applicare i valori ricalcolati. In questo caso, i valori ricalcolati non avranno effetto a meno che qualcuno non li applichi manualmente dalla pagina **Copertura articolo** dei singoli prodotti. Di solito, questa opzione deve essere impostata su *Sì*.
    - **Piano generale**: selezionare un piano generale che include gli articoli interessati dal calcolo. Il calcolo verrà applicato a tutti gli articoli nel filtro del piano, che sarà ulteriormente limitato dalle impostazioni **Filtro** in questa finestra di dialogo.

1. Per limitare il set di record su cui dovrà essere eseguito questo processo batch, nella Scheda dettaglio **Record da includere**, selezionare **Filtro** per aprire la finestra di dialogo **Richiesta di informazioni**. Questa finestra di dialogo funziona esattamente come per gli altri tipi di [processi in background](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) in Supply Chain Management.
1. Nella Scheda dettaglio **Esegui in background**, specificare come, quando e con quale frequenza devono essere eseguiti i calcoli selezionati per gli articoli selezionati. I campi funzionano esattamente come funzionano per altri tipi di [processi in background](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) in Supply Chain Management.
1. Selezionare **OK** per aggiungere un nuovo processo alla coda batch per l'esecuzione.

### <a name="review-and-recalculate-decoupled-lead-times-for-all-items"></a>Rivedere e ricalcolare i lead time disaccoppiati per tuti gli articoli

Attenersi a questa procedura per rivedere e ricalcolare tutti i lead time disaccoppiati disponibili nella persona giuridica (società).

1. Andare a **Pianificazione generale \> Pianificazione generale \> DDMRP \> Lead time disaccoppiato**.
1. Nella pagina **Lead time disaccoppiato**, sfogliare e filtrare l'elenco in base alle esigenze per trovare le informazioni desiderate. Per visualizzare ulteriori informazioni per un articolo, selezionare il relativo collegamento nella colonna **Numero articolo**.
1. Se si desidera ricalcolare il lead time disaccoppiato per un qualsiasi articolo, selezionare l'articolo, quindi selezionare **Calcola lead time disaccoppiato** nel riquadro Azioni. Viene visualizzata la finestra di dialogo **Calcola lead time disaccoppiato**. Questa finestra di dialogo funziona esattamente come quando si [calcolano i lead time disaccoppiati](#calc-lead-time) per lo stesso articolo nella pagina **Copertura articolo**.
