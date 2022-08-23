---
title: Gruppi del modello di ondata
description: Il raggruppamento dei modelli di ondate consente al sistema di utilizzare le configurazioni dei modelli di ondata per determinare, in base a criteri definiti, come dividere le righe rilasciate e assegnarle a ondate nuove o esistenti. Questa funzione può essere utile nei magazzini in cui le ondate vengono create in base a criteri specifici, ma in cui i responsabili preferiscono creare le ondate automaticamente anziché manualmente.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0f0419f1a109f043cb1af6a575704c24420639f1
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218916"
---
# <a name="wave-template-grouping"></a>Gruppi del modello di ondata

[!include [banner](../includes/banner.md)]

Il raggruppamento dei modelli di ondate consente al sistema di utilizzare le configurazioni dei [modelli di ondata](tasks/configure-wave-processing.md) per determinare, in base a criteri definiti, come dividere le righe rilasciate e assegnarle a ondate nuove o esistenti. Questa funzione può essere utile nei magazzini in cui le ondate vengono create in base a criteri specifici, ma in cui i responsabili preferiscono creare le ondate automaticamente anziché manualmente. Consente al sistema di aggiungere ogni spedizione appena rilasciata alla prima ondata rilevata con valori di campo di raggruppamento corrispondenti. Se non viene trovata alcuna corrispondenza, il sistema crea una nuova ondata per la nuova spedizione.

> [!IMPORTANT]
> Il raggruppamento dei modelli di ondata non è supportato per i tipi di lavoro *prelievo di materie prime di produzione* o *Prelievo kanban*. Questo perché il raggruppamento delle ondate si basa sulle spedizioni e questi tipi di lavoro non utilizzano le spedizioni.

## <a name="turn-on-the-wave-template-grouping-feature"></a>Attivare la funzione di raggruppamento dei modelli di ondata

Prima di poter utilizzare la funzionalità *Raggruppamento modello ondata*, deve essere attivata nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Raggruppamento modello ondata*

## <a name="set-a-wave-template-to-use-wave-template-grouping"></a><a name="set-up-template"></a>Impostare un modello di ondata per utilizzare il raggruppamento modello ondata

Per rendere disponibile il raggruppamento modello ondata, attieniti alla seguente procedura per configurare il [modello di ondata](tasks/configure-wave-processing.md).

1. Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.
1. Nel riquadro sinistro, seleziona il modello di ondata da configurare. Se ti stai preparando a lavorare sullo scenario più avanti in questo articolo usando i dati demo, seleziona il modello **62 Spedizione predefinita**.
1. Seleziona **Modifica** per mettere la pagina in modalità modifica.
1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Automatizza creazione ondata:** *Sì*
    - **Assegna a ondate aperte:** *Sì*
    - **Elabora ondata al rilascio in magazzino:** *No*

1. Nel riquadro azioni, seleziona **Modifica query** per aprire la finestra di dialogo dell'editor di query.
1. Nella finestra di dialogo della query, nella scheda **Ordinamento**, rivedi i criteri di ordinamento e assicurati che esista una regola che includa il campo che vuoi utilizzare per raggruppare le ondate.

    Se ti stai preparando a utilizzare lo scenario utilizzando i dati demo, aggiungi una riga con i seguenti valori:

    - **Tabella:** *Spedizioni*
    - **Tabella derivata:** *Spedizioni*
    - **Campo:** *Servizio trasporto*

        > [!NOTE]
        > Dopo aver selezionato questo valore, è possibile che venga visualizzato il messaggio seguente: "Il servizio di trasporto non è un campo indice. Vuoi aggiungere l'ordinamento su questo? " Seleziona **Sì** per aggiungere l'ordinamento.

    - **Direzione di ricerca:** *Crescente*

1. Seleziona **OK** per salvare le modifiche e chiudere la finestra di dialogo della query.
1. Nel riquadro azioni seleziona **Raggruppamento modello ondata**.
1. Nella pagina **Raggruppamento modello ondata**, seleziona la casella di controllo **Raggruppa per** per ogni riga che si desidera utilizzare per raggruppare le righe dell'ordine in ondate, come richiesto. Se ti stai preparando a elaborare lo scenario utilizzando i dati demo, seleziona la casella di controllo **Raggruppa per** controllo per la riga *Servizio trasporto*.
1. Selezionare **Salva**.
1. Chiudi la pagina **Raggruppamento modello ondata**.
1. Seleziona **Salva** per salvare il modello.

## <a name="scenario"></a>Scenario

Questa sezione fornisce uno script che è possibile elaborare per apprendere cosa fa questa funzionalità e come utilizzarla.

### <a name="make-sample-data-available"></a>Rendi disponibili i dati di esempio

Per elaborare lo scenario utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

È inoltre possibile utilizzare questo scenario come indicazioni per l'utilizzo di questa funzionalità quando si lavora su un sistema di produzione. Tuttavia, in questo caso, è necessario sostituire i propri valori e potrebbero mancare alcuni tipi di record richiesti forniti dai dati demo standard.

### <a name="scenario-wave-template-grouping"></a>Scenario: raggruppamento modello ondata

Questo scenario mostra come utilizzare il raggruppamento dei modelli di ondata per creare automaticamente più ondate, in base a criteri di raggruppamento definiti in un modello di ondata. In questo scenario, il modello di ondata è impostato nel sistema per creare un'ondata per servizio di trasporto.

Prima di iniziare, prepara il modello di ondata come descritto in precedenza nella sezione [Impostare un modello di ondata per utilizzare il raggruppamento modello ondata](#set-up-template) in questo articolo. Se lavorerai con i dati dimostrativi per questo scenario, assicurati di usare i valori dei dati dimostrativi suggeriti in quella procedura. Questa configurazione raggrupperà le ondate in base al servizio di trasporto impostato per ciascun ordine cliente.

#### <a name="create-sales-order-1"></a>Creare l'ordine cliente 1

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Selezionare **Nuovo** per creare un ordine cliente.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - Nella Scheda dettaglio **Cliente**, imposta il campo **Conto cliente** su *US-004*.
    - Nel campo **Magazzino** della Scheda dettaglio **Generale**, seleziona *62*.

1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo **Crea ordine cliente**.
1. Il nuovo ordine cliente viene aperto nella visualizzazione **Righe**. Prendi nota del numero di ordine cliente.
1. Passa alla visualizzazione **Intestazione**.
1. Nella Scheda dettaglio **Consegna**, nella sezione **Trasporti**, imposta i seguenti valori:

    - **Vettore spedizione:** *Air cargo*
    - **Servizio trasporto:** *Air*

1. Torna alla visualizzazione **Righe**.
1. Nella sezione **Righe ordine cliente**, seleziona **Aggiungi riga** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Numero articolo:** *A0002*
    - **Quantità:** *2*

1. Seleziona la nuova riga ordine, quindi sul menu **Scorte** sopra la griglia, seleziona **Prenotazione**.
1. Nella pagina **Prenotazione**, nel riquadro azioni, seleziona **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.
1. Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.
1. Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.
1. Riceverai un messaggio informativo che mostra la spedizione e l'ondata per questo ordine. Prendi nota del numero ID ondata e i numeri ID spedizione.

#### <a name="view-the-wave-that-was-created-from-sales-order-1"></a>Visualizzare l'ondata creata dall'ordine cliente 1

1. Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.
1. Seleziona l'ID ondata creato dall'ordine cliente.
1. Seleziona il collegamento ID ondata per aprire la pagina Dettagli ondata.
1. Nota che la spedizione è stata aggiunta alla Scheda dettaglio **Righe ondata**.

#### <a name="create-sales-order-2"></a>Creare l'ordine cliente 2

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Selezionare **Nuovo** per creare un ordine cliente.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - Nella Scheda dettaglio **Cliente**, imposta il campo **Conto cliente** su *US-005*.
    - Nel campo **Magazzino** della Scheda dettaglio **Generale**, seleziona *62*.

1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo **Crea ordine cliente**.
1. Il nuovo ordine cliente viene aperto nella visualizzazione **Righe**. Prendi nota del numero di ordine cliente.
1. Passa alla visualizzazione **Intestazione**.
1. Nella Scheda dettaglio **Consegna**, nella sezione **Trasporti**, imposta i seguenti valori:

    - **Vettore spedizione:** *Flower moving*
    - **Servizio trasporto:** *Std*

1. Torna alla visualizzazione **Righe**.
1. Nella sezione **Righe ordine cliente**, seleziona **Aggiungi riga** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Numero articolo:** *A0001*
    - **Quantità:** *1*

1. Seleziona la nuova riga ordine, quindi sul menu **Scorte** sopra la griglia, seleziona **Prenotazione**.
1. Nella pagina **Prenotazione**, nel riquadro azioni, seleziona **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.
1. Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.
1. Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.
1. Riceverai un messaggio informativo che mostra la spedizione e l'ondata per questo ordine. Prendi nota del numero ID ondata e i numeri ID spedizione. Nota l'ID ondata differisce dall'ID ondata del primo ordine cliente.

#### <a name="view-the-wave-that-was-created-from-sales-order-2"></a>Visualizzare l'ondata creata dall'ordine cliente 2

1. Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.
1. Seleziona l'ID ondata creato dal secondo ordine cliente.
1. Seleziona il collegamento ID ondata per aprire la pagina Dettagli ondata.
1. Nota che la spedizione è stata aggiunta alla Scheda dettaglio **Righe ondata**.

È stata creata una nuova ondata per questa spedizione, poiché utilizza un servizio di trasporto diverso dal primo ordine cliente.

#### <a name="create-sales-order-3"></a>Creare l'ordine cliente 3

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Selezionare **Nuovo** per creare un ordine cliente.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - Nella Scheda dettaglio **Cliente**, imposta il campo **Conto cliente** su *US-006*.
    - Nel campo **Magazzino** della Scheda dettaglio **Generale**, seleziona *62*.

1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo **Crea ordine cliente**.
1. Il nuovo ordine cliente viene aperto nella visualizzazione **Righe**. Prendi nota del numero di ordine cliente.
1. Passa alla visualizzazione **Intestazione**.
1. Nella Scheda dettaglio **Consegna**, nella sezione **Trasporti**, imposta i seguenti valori:

    - **Vettore spedizione:** *Air Cargo*
    - **Servizio trasporto:** *Air*

1. Torna alla visualizzazione **Righe**.
1. Nella sezione **Righe ordine cliente**, seleziona **Aggiungi riga** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Numero articolo:** *A0001*
    - **Quantità:** *1*

1. Seleziona la nuova riga ordine, quindi sul menu **Scorte** sopra la griglia, seleziona **Prenotazione**.
1. Nella pagina **Prenotazione**, nel riquadro azioni, seleziona **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.
1. Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.
1. Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.
1. Riceverai un messaggio informativo che mostra la spedizione e l'ondata per questo ordine. Prendi nota del numero ID ondata e i numeri ID spedizione. La spedizione è stata assegnata all'ondata esistente dal primo ordine cliente.

#### <a name="view-the-wave-for-sales-orders-1-and-3"></a>Visualizzare l'ondata per gli ordini cliente 1 e 3

1. Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.
1. Seleziona l'ID ondata creato dal terzo ordine cliente.
1. Seleziona il collegamento ID ondata per aprire la pagina Dettagli ondata.
1. Nota che la spedizione è stata aggiunta alla Scheda dettaglio **Righe ondata**, insieme alla spedizione per il primo ordine cliente.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]