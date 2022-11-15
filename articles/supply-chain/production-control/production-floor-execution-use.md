---
title: Modalità di utilizzo dell'interfaccia di esecuzione dell'area di produzione da parte dei lavoratori
description: Questo articolo descrive come utilizzare l'interfaccia di esecuzione dell'area di produzione dal punto di vista di un lavoratore.
author: johanhoffmann
ms.date: 01/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 876ee36c75a31ca89a9351d0ee1484e66076b6aa
ms.sourcegitcommit: 4abf9b375fed6885ea11a425c524958fea29c3b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2022
ms.locfileid: "9748715"
---
# <a name="how-workers-use-the-production-floor-execution-interface"></a>Modalità di utilizzo dell'interfaccia di esecuzione dell'area di produzione da parte dei lavoratori

[!include [banner](../includes/banner.md)]

L'interfaccia di esecuzione dell'area di produzione è ottimizzata per l'interazione a tocco. Il design offre un contrasto visivo che soddisfa i requisiti di accessibilità per gli ambienti di produzione. Offre tutte le stesse capacità funzionali del dispositivo scheda di processo. Tuttavia, consente anche di avviare più processi in parallelo da un elenco di processi. (Questa funzionalità è nota anche come *raggruppamento di processi*.) Inoltre, da un elenco di processi i lavoratori possono aprire una guida creata in Microsoft Dynamics 365 Guides. In questo modo, possono ottenere istruzioni visive in un HoloLens.

## <a name="sign-in-to-the-production-floor-execution-interface-as-a-worker"></a>Accedere all'interfaccia di esecuzione dell'area di produzione come lavoratore

Prima che i lavoratori possano iniziare a utilizzare il dispositivo, un supervisore o lo staff tecnico deve prepararlo e aprire la pagina corretta in Dynamics 365 Supply Chain Management. Per ulteriori informazioni su come configurare il dispositivo, vedere [Configurare un dispositivo per eseguire l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-setup.md).

Dopo che il dispositivo è stato preparato, viene visualizzata la pagina di accesso. Questa pagina mostra le informazioni sullo stato dei processi per la cella di lavoro locale. Queste informazioni vengono aggiornate periodicamente. Nella pagina, i lavoratori utilizzano i loro ID badge per accedere. Sebbene i lavoratori non debbano disporre di un account utente per Supply Chain Management, devono avere un account *lavoratore registrato nel tempo* che possono utilizzare quando effettuano l'accesso.

![Pagina di accesso all'interfaccia di esecuzione dell'area di produzione.](media/pfei-sign-in-page.png "Pagina di accesso all'interfaccia di esecuzione dell'area di produzione")

Le sezioni rimanenti di questo articolo descrivono il modo in cui i lavoratori interagiscono con l'interfaccia.

## <a name="all-jobs-tab"></a>Scheda Tutti i processi

La scheda **Tutti i processi** fornisce un elenco che mostra tutti i processi di produzione che hanno uno stato di *Non avviato*, *Arrestato* o *Avviato*. Il nome di questa scheda è personalizzabile e potrebbe essere diverso per il tuo sistema.

![Scheda Tutti i processi.](media/pfei-all-jobs-tab.png "Scheda Tutti i processi")

L'elenco dei processi ha le seguenti colonne. I numeri corrispondono ai numeri della precedente figura.

1. **Colonna di selezione** - La colonna più a sinistra utilizza segni di spunta per indicare i processi che sono stati selezionati dal lavoratore. I lavoratori possono selezionare più processi nell'elenco contemporaneamente. Per selezionare tutti i processi nell'elenco, selezionare il segno di spunta nell'intestazione della colonna. Quando viene selezionato un singolo processo, i dettagli su quel processo vengono visualizzati nella parte inferiore della pagina.
1. **Colonna Stato processo** - Questa colonna utilizza simboli per indicare lo stato di ogni processo. I processi che non hanno alcun simbolo in questa colonna hanno uno stato di *Non avviato*. Un triangolo verde indica i lavori con stato *Avviato*. Due linee verticali gialle indicano i lavori con stato *Arrestato*.
1. **Colonna Alta priorità** - Questa colonna utilizza punti esclamativi per indicare i processi con priorità alta.
1. **Ordine** - Questa colonna mostra il numero dell'ordine di produzione per un processo.
1. **Descrizione** - Questa colonna mostra una descrizione dell'operazione di cui fa parte un processo.
1. **Richiesto** - Questa colonna mostra la quantità che si prevede di produrre per un processo.
1. **Avviato** - Questa colonna mostra la quantità che è già stata avviata per un processo.
1. **Completato** - Questa colonna mostra la quantità che è già stata completata per un processo.
1. **Scartato** - Questa colonna mostra la quantità che è già stata scartata per un processo.
1. **Rimanente** - Questa colonna mostra la quantità che resta da completare per un processo.

## <a name="active-jobs-tab"></a>Scheda Processi attivi

La scheda **Processi attivi** mostra un elenco di tutti i lavori che il lavoratore che ha effettuato l'accesso ha già avviato. Il nome di questa scheda è personalizzabile e potrebbe essere diverso per il tuo sistema.

![Scheda Processi attivi.](media/pfei-active-jobs-tab.png "Scheda Processi attivi")

L'elenco dei processi attivi include le seguenti colonne:

- **Colonna di selezione** - La colonna più a sinistra utilizza segni di spunta per indicare i processi che sono stati selezionati dal lavoratore. I lavoratori possono selezionare più processi nell'elenco contemporaneamente. Per selezionare tutti i processi nell'elenco, selezionare il segno di spunta nell'intestazione della colonna. Quando viene selezionato un singolo processo, i dettagli su quel processo vengono visualizzati nella parte inferiore della pagina.
- **Ordine** - Questa colonna mostra il numero dell'ordine di produzione per un processo.
- **Descrizione** - Questa colonna mostra una descrizione dell'operazione di cui fa parte un processo.
- **Richiesto** - Questa colonna mostra la quantità che si prevede di produrre per un processo.
- **Avviato** - Questa colonna mostra la quantità che è già stata avviata per un processo.
- **Completato** - Questa colonna mostra la quantità che è già stata completata per un processo.
- **Scartato** - Questa colonna mostra la quantità che è già stata scartata per un processo.
- **Rimanente** - Questa colonna mostra la quantità che resta da completare per un processo.

## <a name="my-jobs-tab"></a>Scheda Processi personali

La scheda **Processi personali** consente ai lavoratori di visualizzare facilmente tutti i processi non avviati e non completati assegnati loro specificamente. È utile nelle aziende in cui i processi sono talvolta o sempre assegnati a lavoratori specifici (risorse umane) anziché ad altri tipi di risorse (come le macchine).

Il sistema di pianificazione assegna automaticamente ogni processo di produzione a un record di risorse specifico e ogni record di risorse ha un tipo (come macchina o umano). Quando configuri un dipendente come lavoratore di produzione, puoi associare l'account lavoratore a un record di risorse umane univoco.

La scheda **Processi personali** elenca tutti i processi non avviati e non completati che sono stati assegnati al record delle risorse umane del lavoratore che ha eseguito l'accesso, se un lavoratore ha effettuato l'accesso. Non elenca mai i processi che sono stati assegnati a una macchina o ad un altro tipo di risorsa, anche se il lavoratore che ha eseguito l'accesso ha iniziato a lavorare su quei processi.

Per visualizzare tutti i processi che sono stati avviati dal lavoratore che ha eseguito l'accesso, indipendentemente dal tipo di risorsa a cui è assegnato ciascun processo, utilizza la scheda **Processi attivi**. Per visualizzare tutti i processi non completati che corrispondono alla configurazione del filtro lavori locale, indipendentemente dal lavoratore o dallo stato di inizio, utilizza la scheda **Tutti i processi**.

![Scheda Processi personali.](media/pfei-my-jobs-tab.png "Scheda Processi personali")

## <a name="my-machine-tab"></a>Scheda Macchina personale

La scheda **Macchina personale** consente ai lavoratori di selezionare un cespite connesso a una risorsa di tipo macchina all'interno del filtro impostato nella scheda **Tutti i processi**. Il lavoratore può quindi visualizzare lo stato e l'integrità del cespite selezionato leggendo i valori per un massimo di quattro contatori selezionati e gli elenchi delle recenti richieste di manutenzione e dei tempi di fermo registrati. Il lavoratore può anche richiedere la manutenzione per il cespite selezionato e registrare e modificare i tempi di fermo macchina. Il nome di questa scheda è personalizzabile e potrebbe essere diverso per il tuo sistema.

![Scheda Macchina personale.](media/pfei-my-machine-tab.png "Scheda Macchina personale")

La scheda **Macchina personale** include le seguenti colonne. I numeri corrispondono ai numeri della precedente figura.

1. **Cespite macchina** - Seleziona il cespite di tipo macchina che desideri monitorare. Inizia a digitare un nome per selezionare da un elenco di cespiti di tipo macchino oppure seleziona l'icona della lente di ingrandimento per selezionare da un elenco di tutti i cespiti associati alle risorse che si trovano nel filtro dell'elenco dei processi.

    > [!NOTE]
    > Gli utenti di Supply Chain Management possono assegnare una risorsa a ciascun cespite in base alle esigenze utilizzando la pagina **Tutti i cespiti** pagina (nella scheda **Cespite**, utilizzando il menu a discesa **Risorsa**). Per ulteriori informazioni, vedere [Creare un cespite](../asset-management/objects/create-an-object.md).

1. **Impostazioni** - Seleziona l'icona dell'ingranaggio per aprire una finestra di dialogo in cui è possibile scegliere quali contatori visualizzare per il cespite di tipo macchina selezionato. I valori di questi contatori sono visualizzati nella parte superiore della scheda **Gestione cespiti** tab. Il menu **Impostazioni** (mostrato nella schermata seguente) consente di abilitare fino a quattro contatori. Per ogni contatore che desideri abilitare, utilizza il campo di ricerca nella parte superiore del riquadro per selezionare un contatore. Il campo di ricerca elenca tutti i contatori associati al cespite selezionato nella parte superiore della pagina **Gestione cespiti**. Imposta ogni contatore per monitorare il valore **Aggregato** valore o il valore **Effettivo** più recente per il contatore. Ad esempio, se imposti un contatore che tiene traccia del numero di ore di funzionamento della macchina, dovresti impostarlo su **Aggregato**. Se imposti un contatore per misurare l'ultima temperatura o pressione aggiornata, dovresti impostarlo su **Effettivo**. Selezionare **OK** per salvare le impostazioni e chiudere la finestra di dialogo.

    ![Impostazioni della scheda Macchina personale.](media/pfei-my-machine-tab-settings.png "Impostazioni della scheda Macchina personale")

1. **Richiedi manutenzione** - Seleziona questo pulsante per aprire una finestra di dialogo in cui puoi creare una richiesta di manutenzione. Sarai in grado di fornire una descrizione e una nota. La richiesta verrà portata all'attenzione di un utente di Supply Chain Management, che potrà poi convertire la richiesta di manutenzione in un ordine di lavoro di manutenzione.
1. **Registra tempo di inattività** - Selezionare questo pulsante per aprire una finestra di dialogo in cui è possibile registrare i tempi di fermo macchina. Potrai selezionare un codice motivo e inserire una data/un intervallo di tempo per il tempo di inattività. La registrazione dei tempi di fermo macchina viene utilizzata per calcolare l'efficienza del cespite di tipo macchina.
1. **Visualizza o modifica** - Selezionare questo pulsante per aprire una finestra di dialogo in cui è possibile modificare o visualizzare i record dei tempi di inattività esistenti.

## <a name="starting-and-completing-production-jobs"></a>Avvio e completamento dei processi di produzione

I lavoratori iniziano un processo di produzione selezionando un processo nella scheda **Tutti i processi** e quindi selezionando **Avvia processo** per aprire la finestra di dialogo **Avvia processo**.

![Finestra di dialogo Avvia processo.](media/pfei-start-job-dialog.png "Finestra di dialogo Avvia processo")

I lavoratori usano la finestra di dialogo **Avvia processo** per confermare la quantità di produzione e quindi avviare il processo. I lavoratori possono regolare la quantità selezionando il campo **Quantità** e quindi utilizzando la tastiera numerica che appare. I lavoratori quindi selezionano **Avvia** per iniziare a lavorare sul processo. La finestra di dialogo **Avvia processo** viene chiusa e il processo viene aggiunto alla scheda **Processi attivi**.

I lavoratori possono iniziare un processo che si trova in qualsiasi stato. Quando un lavoratore avvia un processo che ha uno stato di *Non avviato*, il campo **Quantità** nella finestra di dialogo **Avvia processo** mostra inizialmente la quantità totale. Quando un lavoratore avvia un processo che ha uno stato di *Avviato* o *Arrestato*, il campo **Quantità** mostra la quantità rimanente.

## <a name="reporting-good-quantities"></a>Dichiarazione di buone quantità

Quando un lavoratore completa o completa parzialmente un processo, può dichiarare le buone quantità prodotte selezionando un processo nella scheda **Processi attivi** e quindi selezionando **Dichiara avanzamento**. Quindi, nella finestra di dialogo **Dichiara avanzamento** il lavoratore inserisce la buona quantità utilizzando la tastiera numerica. La quantità è vuota per impostazione predefinita. Dopo aver immesso una quantità, il lavoratore può aggiornare lo stato del processo a *In corso*, *Arrestato* o *Completato*.

![Finestra di dialogo Dichiarazione avanzamento.](media/pfei-report-progress-dialog.png "Finestra di dialogo Dichiarazione avanzamento")

## <a name="reporting-good-quantities-on-batch-orders-that-have-co-products-and-by-products"></a>Dichiarazione di buone quantità su ordini batch che hanno co-prodotti e sottoprodotti

I lavoratori possono utilizzare l'interfaccia di esecuzione del reparto di produzione per dichiarare lo stato di avanzamento degli ordini batch. Questo report include la dichiarazione di co-prodotti e sottoprodotti.

Alcuni produttori, soprattutto nei settori della trasformazione, utilizzano ordini batch per gestire i propri processi di produzione. Gli ordini batch vengono creati da formule che possono essere definite in modo che abbiano co-prodotti e sottoprodotti come output. Quando viene dichiarato il feedback su tali ordini batch, la quantità di output deve essere registrata nell'elemento della formula e anche nei co-prodotti e sottoprodotti.

Quando un lavoratore completa totalmente o parzialmente un lavoro su un ordine batch, può dichiarare quantità buone o scartate per ogni prodotto definito come output per l'ordine. I prodotti definiti come output per un ordine batch possono essere di tipo *Formula*, *Co-prodotto*, o *Sottoprodotto*.

Per dichiarare le buone quantità sui prodotti, un lavoratore seleziona un processo nella scheda **Processi attivi** e poi seleziona **Dichiarazione avanzamento**.

Poi, nella finestra di dialogo **Dichiarazione avanzamento**, il lavoratore può selezionare tra i prodotti definiti come output per l'ordine batch di cui deve dichiarare l'avanzamento. L'operatore può selezionare uno o più prodotti nell'elenco, quindi seleziona **Dichiarazione avanzamento**. Per ogni prodotto, la quantità è vuota per impostazione predefinita e il lavoratore può utilizzare la tastierina numerica per inserire la quantità. Il lavoratore può utilizzare i pulsanti **Indietro** e **Avanti** per spostarsi tra i prodotti selezionati. Dopo aver immesso la quantità per ogni prodotto, il lavoratore può aggiornare lo stato del processo a *In corso*, *Arrestato* o *Completato*.

![Dichiara co-prodotti e sottoprodotti.](media/report-co-by-products.png "Dichiarazione co-prodotti e sottoprodotti")

### <a name="reporting-on-batch-orders-for-planning-items"></a>Dichiarazione negli ordini batch per gli elementi di pianificazione

Quando un lavoratore completa un processo su un ordine batch per un elemento di pianificazione, dichiara le quantità solo su coprodotti e sottoprodotti, perché gli elementi di pianificazione non contengono un elemento di tipo *Formula*.

### <a name="reporting-co-product-variation"></a>Dichiarazione di variazione co-prodotto

Se viene creato un ordine batch da una versione della formula in cui l'opzione **Variazioni co-prodotti** è impostata su *Sì*, il lavoratore può dichiarare i co-prodotti che non fanno parte della definizione per gli ordini batch. Questa funzionalità viene utilizzata in scenari in cui può verificarsi un output di prodotto imprevisto nel processo di produzione.

In questo caso, il lavoratore può specificare il coprodotto e la quantità da dichiarare selezionando **Variazioni co-prodotti** nella finestra di dialogo Dichiarazione avanzamento. Il lavoratore può quindi selezionare tra tutti i prodotti rilasciati che sono definiti come co-prodotti.

### <a name="reporting-catch-weight-items"></a>Creazione di report di articoli a peso variabile

I lavoratori possono utilizzare l'interfaccia di esecuzione dell'area di produzione per dichiarare lo stato di avanzamento degli ordini batch creati per articoli a peso variabile. Gli ordini batch vengono creati da formule che possono essere definite in modo che abbiano articoli a peso variabile come articoli formula, co-prodotti e sottoprodotti. È anche possibile definire una formula per avere righe di formula per gli ingredienti definiti per il peso variabile. Gli articoli a peso variabile utilizzano due unità di misura per tener traccia dell'inventario: la quantità a peso variabile e la quantità di inventario. Ad esempio, nell'industria alimentare, la carne in scatola può essere definita come un articolo a peso variabile, in cui la quantità a peso variabile viene utilizzata per tenere traccia del numero di scatole e la quantità di inventario viene utilizzata per tenere traccia del peso delle scatole.

## <a name="reporting-scrap"></a>Dichiarazione dello scarto

Quando un lavoratore completa o completa parzialmente un processo, può dichiarare lo scarto selezionando un processo nella scheda **Processi attivi** e quindi selezionando **Dichiara scarto**. Quindi, nella finestra di dialogo **Dichiara scarto** il lavoratore inserisce la quantità di scarto utilizzando la tastiera numerica. Il lavoratore seleziona anche un motivo (*Nessuno*, *Macchina*, *Operatore* o *Materiale*).

![Finestra di dialogo Dichiarazione scarto.](media/pfei-report-scrap-dialog.png "Finestra di dialogo Dichiarazione scarto")

## <a name="adjust-material-consumption-and-make-material-reservations"></a>Regola il consumo di materiale ed effettua prenotazioni di materiale

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

I lavoratori possono regolare il consumo di materiale per ogni processo di produzione. Questa funzionalità viene utilizzata negli scenari in cui la quantità effettiva di materiali consumata da un processo di produzione era maggiore o minore della quantità pianificata. Pertanto, deve essere regolato per mantenere aggiornati i livelli di inventario.

I lavoratori possono anche effettuare prenotazioni sul batch e sui numeri di serie dei materiali. Questa funzionalità viene utilizzata negli scenari in cui un lavoratore deve specificare manualmente quale batch di materiale o numeri di serie sono stati consumati, per soddisfare i requisiti di tracciabilità del materiale.

I lavoratori possono specificare la quantità da rettificare selezionando **Rettifica materiale**. Questo pulsante è disponibile nelle posizioni seguenti:

- Nella finestra di dialogo **Dichiara scarto**
- Nella finestra di dialogo **Segnala stato**
- Sulla barra degli strumenti a destra

### <a name="adjust-material-consumption-from-the-report-scrap-and-report-progress-dialog-boxes"></a>Regola il consumo di materiale dalle finestre di dialogo Dichiara scarto e Segnala stato

Dopo che un lavoratore ha immesso la quantità da segnalare nella finestra di dialogo **Segnala stato** o **Dichiara scarto**, il pulsante **Regola il materiale** diventa disponibile. Quando l'utente seleziona questo pulsante, viene visualizzata la finestra di dialogo **Regola materiale**. Questa finestra di dialogo elenca gli articoli che si prevede di consumare quando la quantità buona o scartata viene dichiarata per il lavoro.

L'elenco nella finestra di dialogo mostra le informazioni seguenti:

- **Numero prodotto** – La rappresentazione generale prodotto e la variante prodotto.
- **Nome prodotto** - Il nome del prodotto.
- **Proposta** – La quantità stimata di materiale che verrà consumata quando viene segnalo lo stato o dichiarato lo scarto per la quantità specificata per il lavoro.
- **Consumo** – La quantità effettiva di materiale che verrà consumata quando viene segnalo lo stato o dichiarato lo scarto per la quantità specificata per il lavoro.
- **Prenotata** – La quantità di materiale che è stata fisicamente prenotata nell'inventario.
- **Unità** – L'unità della distinta base.

Nel lato destro della finestra di dialogo vengono visualizzate le informazioni seguenti:

- **Numero prodotto** – La rappresentazione generale prodotto e la variante prodotto.
- **Stimata** – Quantità stimata da consumare.
- **Avviata** – La quantità che è stata avviata nel processo di produzione.
- **Quantità rimanente** – La quantità che resta da consumare della quantità stimata.
- **Quantità rilasciata** – La quantità non è stata ancora consumata.

Sarà quindi possibile effettuare le azioni riportate di seguito:

- Il lavoratore può specificare la quantità da rettificare per un materiale selezionando **regola consumo**. Dopo che la quantità è stata confermata, la quantità nella colonna **Consumo** viene aggiornata con la quantità rettificata.
- Quando il lavoratore seleziona **Regola materiale**, viene creato un giornale di registrazione distinta di prelievo produzione. Questo giornale di registrazione contiene gli stessi articoli e le stesse quantità dell'elenco **Regola materiale**.
- Quando il lavoratore regola una quantità nella finestra di dialogo **Regola materiale**, il campo **Proposta** della riga del giornale di registrazione corrispondente viene aggiornato con la stessa quantità. Se il lavoratore seleziona **Annulla** nella finestra di dialogo **Regola materiale**, la distinta di prelievo viene eliminata.
- Se il lavoratore seleziona **OK**, la distinta di prelievo non viene eliminata. Verrà pubblicata quando il lavoro sarà segnalato nella finestra di dialogo **Dichiara scarto** o **Segnala stato**.
- Se il lavoratore seleziona **Annulla** nella finestra di dialogo **Segnala stato** o **Dichiara scarto**, la distinta di prelievo viene eliminata.

### <a name="adjust-material-from-the-primary-or-secondary-toolbar"></a>Rettificare il materiale dalla barra degli strumenti principale o secondaria

Il pulsante **Rettifica materiale** può essere configurato in modo da essere visualizzato sulla barra degli strumenti principale o secondaria. (Per ulteriori informazioni, vedi [Progettare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-tabs.md)). Un lavoratore può selezionare **Regola materiale** per un processo di produzione in corso. In questo caso, viene visualizzata la finestra di dialogo **Regola materiale** in cui l'operatore può apportare le modifiche desiderate. Quando si apre la finestra di dialogo, per l'ordine di produzione viene creata una distinta di prelievo di produzione che contiene le righe per le quantità rettificate. Se il lavoratore seleziona **Pubblica ora**, la rettifica viene confermata e la distinta di prelievo viene registrata. Se il lavoratore seleziona **Annulla**,la distinta di prelievo viene eliminata e non viene apportata aluna modifica.

### <a name="adjust-material-consumption-for-catch-weight-items"></a>Regolare il consumo di materiale per gli articoli a peso variabile

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

I lavoratori possono regolare il consumo di materiale per gli articoli a peso variabile. Questa funzionalità viene utilizzata negli scenari in cui la quantità effettiva di un materiale a peso variabile consumato da un processo di produzione era maggiore o minore della quantità pianificata. Pertanto, deve essere regolato per mantenere aggiornati i livelli di inventario. Quando un lavoratore regola il consumo di un articolo a peso variabile, può regolare sia la quantità a peso variabile che la quantità di magazzino. Ad esempio, se un processo di produzione prevede di consumare cinque scatole con un peso stimato di 2 chilogrammi per scatola, il lavoratore può regolare sia il numero di scatole da consumare che il peso delle scatole. Il sistema convaliderà che il peso specificato delle scatole rientra nella soglia minima e massima definita sul prodotto rilasciato.

### <a name="reserve-materials"></a>Prenotare materiali

Nella finestra di dialogo **Regola materiale**, un lavoratore può effettuare e modificare le prenotazioni di materiale selezionando **Prenota materiale**. La finestra di dialogo **Prenota materiale** visualizzata mostra le scorte fisicamente disponibili per l'articolo per ciascuna dimensione di tracciabilità e stoccaggio.

Se il materiale è abilitato per i processi di gestione del magazzino (WMS), l'elenco mostra solo le scorte fisicamente disponibili per il percorso dell'input di produzione per il materiale. Il percorso dell'input di produzione è definito sulla risorsa in cui è pianificato il processo di produzione. Se il numero dell'articolo è controllato dal batch o dal numero di serie, viene visualizzato l'elenco completo dei numeri di batch e di serie fisicamente disponibili. Per specificare una quantità da prenotare, il lavoratore può selezionare **Prenota materiale**. Per rimuovere una prenotazione esistente, il lavoratore può selezionare **Rimuovi prenotazione**.

Per ulteriori informazioni su come configurare il percorso di input di produzione, vedere il seguente post del blog: [Configurazione della posizione dell'input di produzione](/archive/blogs/axmfg/deliver-picked-materials-to-the-locations-where-the-materials-are-consumed-by-operations-in-production).

> [!NOTE]
> Le prenotazioni che un lavoratore effettua nella finestra di dialogo **Prenota materiale** rimarranno quando il lavoratore seleziona **Annulla** nella finestra di dialogo **Segnala stato** o **Dichiara scarto**.
>
> Non è possibile modificare le prenotazioni per gli articoli a peso variabile.

## <a name="completing-a-job-and-starting-a-new-job"></a>Completare un processo e iniziare un nuovo processo

Di solito, i lavoratori completano un processo selezionando uno o più processi correnti nella scheda **Processi attivi** e quindi selezionando **Dichiara avanzamento**. Quindi inseriscono la quantità prodotta (la buona quantità) e impostano lo stato su *Completato*. Se è stato selezionato più di un processo, un lavoratore utilizza i pulsanti **Indietro** e **Avanti** per spostarsi tra loro. Per iniziare un nuovo processo, il lavoratore lo seleziona nella scheda **Tutti i processi** e quindi seleziona **Avvia processo**.

Un lavoratore può anche avviare un nuovo processo mentre il processo precedente è ancora aperto. Ancora una volta il lavoratore seleziona il nuovo processo nella scheda **Tutti i processi** e quindi seleziona **Avvia processo**. Tuttavia, in questo caso, la finestra di dialogo **Avvia processo** informa il lavoratore che sta attualmente lavorando su un processo e che deve quindi interrompere o completare quel processo prima di iniziare il nuovo processo.

## <a name="working-on-multiple-jobs-in-parallel"></a>Lavorare su più processi in parallelo

Un lavoratore può svolgere più processi contemporaneamente (ovvero, in parallelo). In questo caso, la raccolta di processi su cui sta lavorando il lavoratore è chiamata *aggregazione di processi*. Il lavoratore può aggiungere nuovi processi all'aggregazione o completare uno o più processi nell'aggregazione. I due scenari seguenti mostrano come un lavoratore può lavorare sui processi in parallelo.

### <a name="scenario-1-a-worker-who-has-no-active-jobs-wants-to-start-two-jobs-and-work-on-them-in-parallel"></a>Scenario 1: un lavoratore che non ha processi attivi desidera avviare due processi e lavorarci in parallelo

Il lavoratore seleziona il due processi nella scheda **Tutti i processi** e quindi seleziona **Avvia processo**. La finestra di dialogo **Avvia processo** mostra entrambi i processi selezionati e il lavoratore può regolare la quantità da avviare su ogni processo. Il lavoratore quindi conferma la finestra di dialogo e può avviare entrambi i processi.

### <a name="scenario-2-a-worker-who-has-two-active-jobs-that-are-in-progress-wants-to-start-a-third-job-and-work-on-it-in-parallel-with-the-other-two"></a>Scenario 2: un lavoratore che ha due processi attivi in corso e desidera avviare un terzo processo e lavorarci parallelamente agli altri due

Il lavoratore seleziona il terzo processo nella scheda **Tutti i processi** e quindi seleziona **Aggregazione**. Nella finestra di dialogo **Aggregazione**, il lavoratore può regolare la quantità da avviare. Il lavoratore quindi conferma la finestra di dialogo selezionando **Aggregazione**.

## <a name="working-on-indirect-activities"></a>Utilizzo delle attività indirette

Le attività indirette sono attività che non sono direttamente correlate a un ordine di produzione. Le attività indirette possono essere definite in modo flessibile, come descritto in [Impostare attività indirette per orario e presenze](/dynamicsax-2012/appuser-itpro/set-up-indirect-activities-for-time-and-attendance).

Ad esempio, Shannon, una lavoratrice del reparto produzione presso Contoso, desidera partecipare a una riunione aziendale e le riunioni sono considerate un'attività indiretta. Si applica uno dei due scenari seguenti:

- **Shannon sta lavorando a uno o più processi attivi.** Shannon sceglie **Attività**, identifica l'attività (riunione) e conferma la sua selezione. Un messaggio che appare la informa che ha dei processi in corso. Dal messaggio, Shannon può scegliere di completare o arrestare i processi su cui sta lavorando prima di andare alla riunione.
- **Shannon non ha processi attivi.** Shannon sceglie **Attività**, identifica l'attività (riunione) e conferma la sua selezione. Ora è registrata come partecipante alla riunione.

In entrambi gli scenari, dopo che Shannon ha confermato la sua selezione, va alla pagina di accesso o a una pagina che attende la conferma di essere tornata dalla sua attività indiretta. La pagina che appare dipende dalla configurazione dell'interfaccia di esecuzione dell'area di produzione. (Per ulteriori informazioni, vedere [Configurare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-configure.md).)

## <a name="registering-breaks"></a>Pause registrazione

I lavoratori possono registrare le pause. Le pause possono essere definite in modo flessibile, come descritto in [Retribuzione basata sulle registrazioni](pay-based-on-registrations.md).

Un lavoratore registra una pausa selezionando **Pausa** e quindi selezionando la scheda che rappresenta il tipo di pausa (come pranzo). Dopo che il lavoratore ha confermato la selezione, il dispositivo mostra la pagina di accesso o una pagina che attende che il lavoratore confermi di essere tornato dalla pausa. La pagina che appare dipende dalla configurazione dell'interfaccia di esecuzione dell'area di produzione. (Per ulteriori informazioni, vedere [Configurare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-configure.md).)

## <a name="view-the-my-day-dialog"></a>Visualizzare la finestra di dialogo "Registrazioni quotidiane"

La finestra di dialogo **Registrazioni quotidiane** fornisce ai lavoratori una panoramica delle registrazioni e dei saldi. La finestra di dialogo è suddivisa nelle tre sezioni seguenti:

- La sezione principale elenca le registrazioni che l'attuale lavoratore ha effettuato in una data selezionata. Si apre mostrando le registrazioni per il giorno corrente e fornisce un selettore di date che consente al lavoratore di visualizzare altri giorni.
- La sezione **Ultimo saldo giornaliero calcolato** mostra i saldi correnti del lavoratore per ore retribuite, straordinari retribuiti, assenze e assenze retribuite. Questi valori si basano sulle registrazioni che sono state calcolate durante il processo di approvazione.
- La sezione **Saldi** fornisce una panoramica dei saldi entro un periodo definito per le categorie selezionate di registrazioni (come ferie, orari standard e straordinari). Questi saldi si basano sul modo in cui i saldi statistici sono impostati nel modulo **Orario e presenze**. Per ulteriori informazioni su come impostarlo, vedi [Mostrare i saldi ferie nell'interfaccia di esecuzione dell'area di produzione](production-floor-execution-payroll-stats.md).

Gli amministratori possono aggiungere questa funzione all'interfaccia inserendo il pulsante **Registrazioni quotidiane** su una barra degli strumenti per ciascuna scheda pertinente come descritto in [Progettare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-tabs.md).

## <a name="working-in-teams"></a>Lavorare in team

Quando più lavoratori vengono assegnati allo stesso processo di produzione, possono formare un team. Il team può nominare un lavoratore come pilota. I restanti lavoratori quindi diventano automaticamente assistenti del pilota. Per il team risultante, solo il pilota deve registrare lo stato del processo. I record di tempo si applicano a tutti i membri del team.

### <a name="prerequisites"></a>Prerequisiti

Per utilizzare i team, un amministratore deve abilitare l'azione **Assistente** per la barra degli strumenti principale nella scheda **Tutti i processo** dell'interfaccia di esecuzione dell'area di produzione. Per istruzioni, vedi [Progettare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-tabs.md).

### <a name="form-a-new-team-that-has-a-pilot-and-an-assistant"></a>Formare un nuovo team che ha un pilota e un assistente

Un lavoratore può registrarsi come assistente selezionando **Assistente** nella scheda **Tutti i processi**. Poi, nella finestra di dialogo **Selezionare un dipendente per l'assistenza** visualizzata, il lavoratore può selezionare un pilota in un elenco di lavoratori che stanno attivamente lavorando a un processo. Dopo che il lavoratore ha confermato la selezione, diventa assistente del lavoratore selezionato, che diventa il pilota del nuovo team.

### <a name="assign-a-new-pilot-to-an-existing-team"></a>Assegnare un nuovo pilota a un team esistente

Quando un team vuole selezionare un nuovo pilota, il pilota attuale deve nominare un altro lavoratore del team come nuovo pilota. Per nominare un nuovo pilota, il pilota attuale seleziona **Assistente** nella scheda **Tutti i processi**. Poi, nella finestra di dialogo **Cambia pilota** visualizzata, il pilota può selezionare un nuovo pilota in un elenco di lavoratori che fanno già parte del team. Dopo che il pilota corrente ha confermato la selezione, viene completamente rimosso dal team. Tuttavia, può rientrare nel team se necessario.

### <a name="assistant-clocks-out"></a>Uscita dell'assistente

Quando un lavoratore che lavora come assistente esce, lascia il team. Se le opzioni **Team permanenti** e **Riavvia all'entrata** sono impostate su *sì*, un lavoratore che esce, rientra automaticamente nel team la prossima volta che effettua la timbratura per entrare. Puoi trovare queste opzioni nella scheda **Generale** della pagina **Parametri di orari e presenze**.

## <a name="opening-instructions"></a>Apertura delle istruzioni

I lavoratori possono aprire un documento allegato a un processo selezionando **Istruzioni**. Il pulsante **Istruzioni** è disponibile solo se un documento è associato al processo nei dati master. Ad esempio, un documento allegato a un prodotto nella pagina **Prodotti rilasciati** in Supply Chain Management sarà disponibile per essere aperta dai lavoratori nell'interfaccia di esecuzione del reparto produzione.

## <a name="opening-mixed-reality-guides-for-hololens"></a>Apertura delle guide di realtà mista per HoloLens

[Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/) può aiutare a potenziare i lavoratori fornendo un apprendimento pratico che utilizza la realtà mista. È possibile definire processi standardizzati con istruzioni dettagliate che guidano i lavoratori all'individuazione di strumenti e parti di cui hanno bisogno e mostrano il modo in cui utilizzare questi strumenti in situazioni di lavoro reali. Ecco una panoramica del processo.

1. Ogni volta che un lavoratore apre un elenco di processi nell'interfaccia di esecuzione del reparto di produzione, l'interfaccia trova tutte le guide pertinenti per i processi visualizzati.
1. Il lavoratore seleziona **Guides** per visualizzare l'elenco delle guide.
1. Il lavoratore seleziona una guida pertinente nell'elenco.
1. L'interfaccia di esecuzione del reparto di produzione mostra un codice QR per la guida selezionata.
1. Il lavoratore indossa un dispositivo HoloLens e fissa il codice QR per avviare la guida.
1. Il lavoratore utilizza la guida per apprendere come eseguire l'attività.

Per ulteriori informazioni su come creare, assegnare e utilizzare le guide per HoloLens, vedere [Fornire guide di realtà mista per i lavoratori in produzione](instruction-guides-in-production-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
