---
title: Stato ubicazione magazzino
description: Questo argomento fornisce una panoramica della funzionalità di stato dell'ubicazione di magazzino.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 128083b22bb14d9b445863a0ba1217f723727ee4
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597508"
---
# <a name="warehouse-location-status"></a>Stato ubicazione magazzino

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management include diversi campi di ubicazione che ti offrono flessibilità quando lavori e mantieni le ubicazioni. È possibile includere gli stati delle ubicazioni nella query della direttiva di ubicazione per fornire un migliore controllo sul flusso del magazzino.

I seguenti quattro campi nella pagina **Ubicazioni** tengono traccia delle informazioni sullo stato corrente di un'ubicazione. Questi campi consentono ai responsabili del magazzino di ottenere una panoramica dello stato delle ubicazioni di magazzino. Consentono inoltre report e filtri avanzati.

- **Numero articolo**: l'articolo che si trova attualmente nell'ubicazione. Se l'ubicazione contiene più articoli, questo campo è vuoto.
- **Data e ora dell'ultima attività**: il timestamp dell'ultima transazione di magazzino eseguita a fronte dell'ubicazione.
- **Data di aging**: la data in cui le scorte nell'ubicazione sono state portate nel magazzino. Questo valore viene calcolato in base alla data di aging della targa. È precisa per le ubicazioni che sono tracciate in base alla targa, ma potrebbe non essere precisa per le ubicazioni che non sono tracciate in base alla targa.
- **Stato ubicazione**: lo stato dell'ubicazione. I valori possibili sono quattro:

    - **Indeterminato**: il profilo dell'ubicazione non può tener traccia dello stato. Pertanto, lo stato corrente è sconosciuto.
    - **Vuoto**: al momento non ci sono scorte nell'ubicazione.
    - **Prelievo**: sono state eseguite transazioni in uscita a fronte dell'ubicazione dall'ultima volta in cui era vuota.
    - **Immagazzinamento**: sono state eseguite transazioni in uscita a fronte dell'ubicazione dall'ultima volta in cui l'ubicazione era vuota.

## <a name="turn-on-the-warehouse-location-status-feature"></a>Attivare la funzionalità di stato dell'ubicazione di magazzino

Prima di poter utilizzare la funzionalità *Stato ubicazione magazzino*, tale funzionalità deve essere attivata nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità** *Stato ubicazione magazzino*

## <a name="set-up-warehouse-location-status"></a>Impostare lo stato dell'ubicazione di magazzino

### <a name="prepare-the-sample-data-that-is-required-for-the-example-scenario"></a>Preparare i dati di esempio richiesti per lo scenario di esempio

Prima di iniziare ad analizzare lo scenario, devi attivare i dati di esempio e impostare la funzionalità come descritto in questa sezione. Per completare lo scenario di esempio, è necessario utilizzare l'app del magazzino o l'emulatore basato sul browser. I passaggi forniti qui utilizzano l'app del magazzino. I passaggi per l'emulatore basato su browser sono simili.

#### <a name="use-the-usmf-legal-entity"></a>Utilizzare la persona giuridica USMF

Per elaborare lo scenario di esempio utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

#### <a name="set-up-location-profiles"></a>Imposta profili ubicazione

Lo scenario di esempio richiede la preparazione di due profili di ubicazione.

1. Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.
1. Seleziona **Modifica** per mettere la pagina in modalità modifica.
1. Seleziona il profilo **BULK-06**.
1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Abilita articolo nell'ubicazione**: impostare questa opzione su _Sì_.
    - **Abilita data e ora attività ubicazione:** impostare questa opzione su _Sì_.
    - **Abilita stato ubicazione**: impostare questa opzione su _Sì_.

    Queste opzioni controllano se i campi di riferimento sull'ubicazione sono attivi.

1. Ripeti i passaggi da 3 a 4 per il profilo **PICK-06**.

### <a name="scenario"></a>Scenario

1. Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine fornitore**, nella Scheda dettaglio **Fornitore**, nel campo **Conto fornitore**, seleziona *104*.
1. Nel campo **Magazzino** della Scheda dettaglio **Generale**, selezionare *61*.
1. Selezionare **OK**.
1. Il tuo nuovo ordine fornitore viene aperto. Include una riga vuota nella griglia **Righe ordine fornitore**. Su questa riga, impostare i seguenti valori:

    - **Numero articolo:** _A0002_
    - **Quantità:** _5_

1. Nella scheda **Acquisti** del riquadro azioni, nel gruppo **Azioni**, seleziona **Conferma** per confermare l'ordine fornitore.
1. Sul dispositivo mobile, vai a **In entrata \> Entrata acquisto**.
1. Seleziona il campo **PONUM**, quindi inserisci il numero dell'ordine fornitore e conferma.
1. Seleziona il campo **ITEM**, quindi inserisci *A0002* come numero articolo e conferma.
1. Nella pagina **Qtà**, inserisci *5* come quantità e conferma.

    È possibile immettere la quantità in uno dei seguenti modi:

    - Seleziona il segno più (**+**) o segno meno (**-**) per aggiungere o sottrarre un valore numerico.
    - Seleziona il campo vuoto tra il segno più (**+**) e segno meno (**-**) per aprire il tastierino numerico.

1. Conferma la selezione del numero di articolo *A0002* e una quantità di *5*. Viene visualizzato un messaggio "Lavoro completato" nella parte inferiore della pagina.
1. Seleziona il pulsante Menu (a volte indicato come hamburger o pulsante hamburger) nell'angolo in alto a destra, quindi seleziona **Annulla** per uscire da **Entrata acquisti** e tornare al menu **In entrata**.
1. Nella pagina dell'ordine fornitore, seleziona **Dettagli lavoro** sopra la griglia **Righe ordine fornitore**.
1. Nella scheda **Generale**, prendi nota dei valori **ID lavoro** e **ID targa di destinazione** che sono stati creati.
1. Nella sezione **Righe**, prendi nota dei valori **Ubicazione** per i tipo di lavoro *Prelievo* e *Inserimento*.
1. Sul dispositivo mobile, vai a **In entrata \> Stoccaggio acquisto**.
1. Seleziona il campo **ID**, inserisci l'ID lavoro e conferma.
1. Conferma un'altra volta per completare l'immissione di *Prelievo*.
1. Seleziona il pulsante Menu nell'angolo superiore destro e seleziona **Fatto** per completare il lavoro *Prelievo*.
1. Prendi nota dell'ubicazione di stoccaggio e conferma. Viene visualizzato un messaggio "Lavoro completato" nella parte inferiore della pagina.
1. Seleziona il pulsante Menu nell'angolo in alto a destra, quindi seleziona **Annulla** per chiudere **Stoccaggio acquisto** e tornare al menu **In entrata**.
1. Seleziona **Indietro** per tornare al menu principale.
1. In Dynamics 365 Supply Chain Management, vai a **Gestione magazzino \> Impostazione \> Magazzino \> Ubicazioni**.
1. Applica il filtro su **Ubicazione** e immetti l'ubicazione di stoccaggio dal lavoro dell'ordine fornitore. Dovresti vedere i seguenti risultati:

    - La colonna **Stato ubicazione** mostra un valore di *Immagazzinamento*, poiché l'ultima transazione a fronte di questa ubicazione era un inserimento.
    - La colonna **Numero articolo** mostra un valore di *A0002*, perché tale articolo è stato ricevuto e inserito nell'ubicazione.
    - La colonna **Data e ora dell'ultima attività** mostra il timestamp per la data e l'ora in cui il lavoro è stato completato nell'ubicazione.

1. Sul dispositivo mobile, vai a **Qualità \> Movimento**.
1. Seleziona il campo **UBICAZIONE/TARGA** e immetti l'ubicazione di cui hai preso nota nei passaggi precedenti.
1. Conferma le informazioni visualizzate. Prendi nota del numero di targa che viene generato.
1. Nella schermata **Informazioni di destinazione**, seleziona il campo **UBICAZIONE/TARGA** e immetti *06A07R2S1B* come ubicazione in cui spostare l'articolo.
1. Nella schermata **Informazioni di destinazione**, conferma il valore **Targa** (ID targa di destinazione), che viene generato automaticamente. Viene visualizzato un messaggio "Lavoro completato" nella parte inferiore della pagina.
1. Seleziona il pulsante Menu nell'angolo in alto a destra, quindi seleziona **Annulla** per chiudere **Movimento** e tornare al menu **Gestione qualità**.
1. Seleziona **Indietro** per tornare al menu principale.
1. In Dynamics 365 Supply Chain Management, vai a **Gestione magazzino \> Impostazione \> Magazzino \> Ubicazioni**.
1. Aggiorna la pagina **Ubicazioni** e visualizza nuovamente l'ubicazione di stoccaggio originale. Nota che il campo **Stato ubicazione** è ora impostato su *Vuoto* e la colonna **Numero articolo** è vuota.
1. Visualizza il record per l'ubicazione *06A07R2S1B* e notare che il valore **Stato** è cambiato in *Immagazzinamento* e i campi **Numero articolo** e **Data e ora dell'ultima attività** sono stati aggiornati.
1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine cliente**, nel campo **Conto cliente**, seleziona *US-002*.
1. Nel campo **Magazzino** selezionare *61*.
1. Selezionare **OK**.
1. Viene aperto il nuovo ordine cliente. Include una riga vuota nella griglia **Righe ordine cliente**. Su questa riga, impostare i seguenti valori:

    - **Numero articolo:** _A0002_
    - **Quantità:** _1_

1. Nella scheda dettaglio **Righe ordine cliente**, nel menu **Scorte**, seleziona **Prenotazione**.
1. Nella pagina **Prenotazione**, seleziona **Prenota lotto** per prenotare la riga ordine. Quindi seleziona il pulsante **Chiudi** (**X**) nell'angolo superiore destro per chiudere la pagina.
1. Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.
1. Nella sezione **Righe ordine cliente**, nel menu **Magazzino**, seleziona **Dettagli lavoro**.
1. Copia il valore **ID lavoro** che è stato creato.
1. Sul dispositivo mobile, vai a **In uscita \> Prelievo vendite**.
1. Seleziona il campo **ID**, inserisci l'ID lavoro copiato in precedenza e conferma.
1. Nella pagina **Ordini cliente: Prelievo** il campo **UBICAZIONE** suggerisce l'ubicazione di prelievo come l'ubicazione di stoccaggio creata in precedenza. Prendi nota dell'ubicazione.
1. Seleziona il campo **UBICAZIONE**, inserisci l'ubicazione e conferma.
1. Seleziona il **Targa**, inserisci il numero di targa di cui hai preso nota durante l'attività di movimento e conferma.
1. Seleziona il campo **Articolo**, quindi inserisci *A0002* come numero articolo e conferma.
1. Nella pagina **Qtà**, inserisci *1* come quantità e conferma.

    È possibile immettere la quantità in uno dei seguenti modi:

    - Seleziona il segno più (**+**) o segno meno (**-**) per aggiungere o sottrarre un valore numerico.
    - Seleziona il campo vuoto tra il segno più (**+**) e segno meno (**-**) per aprire il tastierino numerico.

1. Seleziona il campo **Targa di destinazione**, immetti un ID targa di destinazione definito dall'utente e conferma.
1. Conferma un'altra volta per completare il lavoro di prelievo. Viene visualizzato un messaggio "Lavoro completato" nella parte inferiore della pagina.
1. Seleziona il pulsante Menu nell'angolo in alto a destra, quindi seleziona **Annulla** per completare l'attività di prelievo e tornare al menu **In uscita**.
1. In Dynamics 365 Supply Chain Management, vai a **Gestione magazzino \> Impostazione \> Magazzino \> Ubicazioni**.
1. Applica il filtro su **Ubicazione** e immetti l'ubicazione di prelievo dal lavoro dell'ordine cliente.
1. Nota che il campo **Stato ubicazione** per l'ubicazione da cui viene prelevato il lavoro dell'ordine cliente è ora impostato su *Prelievo* e il campo **Data e ora dell'ultima attività** è stato aggiornato.

> [!NOTE]
> I campi dell'ubicazione vengono aggiornati solo dalle transazioni di magazzino. Se sposti le scorte utilizzando un giornale di registrazione o altri processi non di magazzino, i campi non verranno aggiornati.
