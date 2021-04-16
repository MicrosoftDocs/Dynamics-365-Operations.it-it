---
title: Procedura dettagliata per le funzionalità di gestione delle modifiche di progettazione
description: Questo argomento fornisce una procedura dettagliata completa per utilizzare le funzionalità di gestione delle modifiche di progettazione.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 91b19598075871dcfaed3ad9978aa8fe8181aa6f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836664"
---
# <a name="engineering-change-management-feature-walkthrough"></a>Procedura dettagliata per le funzionalità di gestione delle modifiche di progettazione

[!include [banner](../includes/banner.md)]

Questo argomento fornisce una procedura dettagliata completa per utilizzare le funzionalità di gestione delle modifiche di progettazione. Viene descritto ciascuno degli scenari più importanti:

- Configurazione delle funzioni di base
- Come una società di progettazione crea un nuovo prodotto di progettazione
- Come una società di progettazione rilascia un prodotto di progettazione a una società locale
- Come una società locale può esaminare e accettare un prodotto che le è stato rilasciato da una società di progettazione
- Come una società locale può utilizzare un prodotto di progettazione nelle transazioni standard
- Come aggiungere un prodotto di progettazione a un ordine cliente
- Come richiedere modifiche a un prodotto di progettazione creando una richiesta di modifica di progettazione
- Come pianificare e implementare le modifiche richieste creando un ordine di modifica di progettazione
- Come rilasciare un prodotto che è stato modificato

Tutti gli esercizi in questo argomento utilizzano i dati di esempio standard forniti per Microsoft Dynamics 365 Supply Chain Management. Inoltre, ogni esercizio si basa sull'esercizio precedente. Pertanto, si consiglia di eseguire gli esercizi nell'ordine presentato, dall'inizio alla fine, soprattutto se in precedenza non sono state mai utilizzate funzionalità di gestione delle modifiche di progettazione. In questo modo, acquisirai una conoscenza completa della funzionalità.

## <a name="set-up-for-the-sample-scenario"></a>Configurazione per lo scenario di esempio

Per seguire lo scenario di esempio fornito in questo argomento, è necessario prima preparare la funzionalità rendendo disponibili i dati dimostrativi aggiungendo alcuni record personalizzati.

Prima di provare a eseguire uno degli esercizi nel resto di questo argomento, seguire le istruzioni in tutte le sottosezioni seguenti. Queste sottosezioni introducono anche diverse pagine di impostazioni importanti da utilizzare quando si configura la gestione delle modifiche di progettazione per la propria organizzazione.

### <a name="make-standard-demo-data-available"></a>Rendere disponibili i dati dimostrativi standard

Utilizzare un sistema in cui i [dati dimostrativi demo siano installati](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). I dati dimostrativi standard aggiungono dati per diverse persone giuridiche (aziende e organizzazioni). Mentre si svolgono gli esercizi, viene utilizzato il selettore di aziende sul lato destro della barra di navigazione per passare da una società (*DEMF*), impostata come *organizzazione di progettazione* a un'altra (*USMF*), impostata come *organizzazione operativa*.

### <a name="set-up-an-engineering-organization"></a>Impostare un'organizzazione di progettazione

Un'organizzazione di progettazione possiede i dati di progettazione ed è responsabile della progettazione e delle modifiche del prodotto. Per impostare le organizzazioni di progettazione, eseguire queste operazioni.

1. Andare a **Gestione modifiche di progettazione &gt; Imposta &gt; Organizzazioni di progettazione**.
1. Selezionare **Nuovo** per aggiungere una riga alla griglia e quindi impostare i seguenti valori:

    - **Organizzazione di progettazione:** *DEMF*
    - **Nome organizzazione:** *Contoso Entertainment System Germany*

    ![Aggiunta di un'organizzazione di progettazione](media/engineering-org.png "Aggiunta di un'organizzazione di progettazione")

### <a name="set-up-the-version-product-dimension-group"></a>Impostare il gruppo di dimensioni prodotto della versione

1. Andare a **Gestione informazioni sul prodotto &gt; Imposta &gt; Dimensioni e gruppi di varianti &gt; Gruppi di dimensioni prodotto**.
1. Selezionare **Nuovo** per creare un gruppo di dimensioni prodotto.
1. Impostare il campo **Nome** su *Versione*.
1. Selezionare **Salva** per salvare la nuova dimensione e caricare i valori nella Scheda dettaglio **Dimensioni prodotto**.
1. Nella Scheda dettaglio **Dimensioni prodotto** impostare **Versione** come dimensione prodotto attiva.

    ![Aggiunta di un gruppo di dimensioni prodotto](media/product-dimension-groups.png "Aggiunta di un gruppo di dimensioni prodotto")

### <a name="set-up-product-lifecycle-states"></a>Impostare gli stati del ciclo di vita prodotto

Mentre un prodotto di progettazione attraversa il suo ciclo di vita, è importante essere in grado di controllare quali transazioni sono consentite per ogni stato del ciclo di vita. Per impostare gli stati del ciclo di vita del prodotto, eseguire queste operazioni.

1. Andare a **Gestione modifiche di progettazione &gt; Imposta &gt; Stato del ciclo di vita prodotto**.
1. Selezionare **Nuovo** per aggiungere uno stato del ciclo di vita e quindi impostare i seguenti valori:

    - **Stato:** *Operativo*
    - **Descrizione:** *Operativa*

1. Selezionare **Salva** per salvare lo stato del ciclo di vita prodotto e caricare i valori nella Scheda dettaglio **Processi aziendali abilitati**.
1. Nella Scheda dettaglio **Processi aziendali abilitati** selezionare i processi aziendali che devono essere disponibili. Per questo esempio, lasciare il campo **Criteri** impostato su *Abilitato* per tutti i processi aziendali.

    ![Abilitazione dei processi aziendali per uno stato del ciclo di vita](media/product-lifecycle-states-1.png "Abilitazione dei processi aziendali per uno stato del ciclo di vita")

1. Selezionare **Nuovo** per aggiungere un altro stato del ciclo di vita e quindi impostare i seguenti valori:

    - **Stato:** *Prototipo*
    - **Descrizione:** *Prototipo*

1. Selezionare **Salva** per salvare lo stato del ciclo di vita prodotto e caricare i valori nella Scheda dettaglio **Processi aziendali abilitati**.
1. Nella Scheda dettaglio **Processi aziendali abilitati** selezionare i processi aziendali che devono essere disponibili. Per questo esempio, impostare il campo **Criteri** su *Abilitato con avviso* per tutti i processi aziendali.

    ![Abilitazione (con avvisi) dei processi aziendali per uno stato del ciclo di vita](media/product-lifecycle-states-2.png "Abilitazione (con avvisi) dei processi aziendali per uno stato del ciclo di vita")

### <a name="set-up-a-version-number-rule"></a>Imposta una regola per il numero di versione

1. Andare a **Gestione modifiche di progettazione &gt; Imposta &gt; Regola numero di versione prodotto**.
1. Selezionare **Nuovo** per aggiungere una regola e quindi impostare i seguenti valori:

    - **Nome:** *Automatico*
    - **Regola numero:** *Automatico*
    - **Formato:** *V-\#\#*

    ![Aggiunta di una regola per il numero di versione del prodotto](media/version-number-rule.png "Aggiunta di una regola per il numero di versione del prodotto")

### <a name="set-up-a-product-release-policy"></a>Impostare i criteri di rilascio del prodotto

1. Andare a **Gestione modifiche di progettazione &gt; Imposta &gt; Criteri di rilascio del prodotto**.
1. Selezionare **Nuovo** per aggiungere criteri di rilascio e quindi impostare i seguenti valori:

    - **Nome:** *Componenti*
    - **Descrizione:** *Componenti*

1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Tipo di prodotto:** *Articolo*
    - **Applica modelli:** *Sempre*
    - **Attivo:** *Sì*

1. Nella Scheda dettaglio **Tutti i prodotti**, selezionare **Aggiungi** per aggiungere una riga e quindi impostarne i valori seguenti:

    - **Società** *DEMF*
    - **Modello prodotto rilasciato** *D0006*

1. Selezionare **Aggiungi** per aggiungere un'altra riga, quindi imposta i seguenti valori:

    - **ID account società:** *USMF*
    - **Modello prodotto rilasciato** *D0006*
    - **Ricevi DBA:** selezionare questa casella di controllo.
    - **Copia approvazione DBA:** selezionare questa casella di controllo.
    - **Copia attivazione DBA:** selezionare questa casella di controllo.
    - **Ricevi ciclo di lavorazione:** selezionare questa casella di controllo.
    - **Copia approvazione ciclo di lavorazione:** selezionare questa casella di controllo.
    - **Copia attivazione ciclo di lavorazione:** selezionare questa casella di controllo.

    ![Aggiunta di criteri di rilascio del prodotto](media/product-release-policy.png "Aggiunta di criteri di rilascio del prodotto")

### <a name="set-up-an-engineering-product-category"></a>Impostare una categoria di prodotti di progettazione 

Le categorie di prodotti di progettazione forniscono la base per la creazione di prodotti di progettazione (ovvero prodotti con versione e controllati tramite la gestione delle modifiche di progettazione). Per impostare le categorie di prodotti di progettazione, eseguire queste operazioni.

1. Andare a **Gestione modifiche di progettazione &gt; Dettagli categoria prodotti di progettazione**.
1. Selezionare **Nuovo** per creare una categoria.
1. Nella Scheda dettaglio **Dettagli** impostare i seguenti valori:

    - **Nome:** *Componenti*
    - **Organizzazione di progettazione:** *DEMF*
    - **Tipo di prodotto:** *Articolo*
    - **Tenere traccia delle versioni nelle transazioni:** *Sì*
    - **Gruppo di dimensioni prodotto:** *Versione*
    - **Stato del ciclo di vita del prodotto alla creazione:** *Operativo*
    - **Regola numero versione:** *Automatico*
    - **Applica validità:** *Sì*
    - **Usa nomenclatura regola numero:** *No*
    - **Usa nomenclatura regola nome:** *No*
    - **Usa nomenclatura descrizione:** *No*

1. Nella Scheda dettaglio **Criteri di rilascio** impostare il campo **Criteri di rilascio prodotto** su *Componenti*.
1. Selezionare **Salva**.

    ![Aggiunta di una categoria di prodotti di progettazione](media/product-category-details.png "Aggiunta di una categoria di prodotti di progettazione")

### <a name="set-up-product-acceptance-conditions"></a>Impostare le condizioni di accettazione del prodotto

1. Utilizzare il selettore per le aziende sul lato destro della barra di navigazione per passare alla persona giuridica *USMF* (società).
1. Andare a **Gestione modifiche di progettazione &gt; Imposta &gt; Parametri per gestione modifiche di progettazione**.
1. Nella scheda **Controllo rilascio**, nella sezione **Accettazione del prodotto** impostare il campo **Accettazione del prodotto** su *Manuale*.

    ![Impostazione delle condizioni di accettazione del prodotto](media/engineering-change-management-parameters.png "Impostazione delle condizioni di accettazione del prodotto")

## <a name="create-a-new-engineering-product"></a>Creare un nuovo prodotto di progettazione

Un prodotto di progettazione è un prodotto con versione e controllato tramite la gestione delle modifiche di progettazione. In altre parole, è possibile controllare le modifiche durante la vita del prodotto e le informazioni sulle modifiche verranno salvate utilizzando gli ordini di modifica di progettazione. Per creare prodotti di progettazione, eseguire queste operazioni.

1. Verificare di trovarsi nella persona giuridica dell'organizzazione di progettazione (*DEMF* per questo esempio). Utilizzare il selettore per le aziende sul lato destro della barra di navigazione in base alle esigenze.
1. Aprire la pagina **Prodotti rilasciati** eseguendo una di queste operazioni.

    - Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.
    - Andare a **Gestione modifiche di progettazione &gt; Comune &gt; Prodotti rilasciati**.

1. Nel riquadro azioni, nella scheda **Prodotto**, nel gruppo **Nuovo** selezionare **Prodotto di progettazione**.
1. Nella finestra di dialogo **Nuovo prodotto**, imposta i seguenti valori:

    - **Categoria prodotti di progettazione:** *Componenti*
    - **Numero prodotto:** *Z0001*
    - **Nome prodotto:** *Set altoparlanti*

    ![Aggiunta di un prodotto di progettazione](media/new-product-dialog.png "Aggiunta di un prodotto di progettazione")

    Si noti che il campo **Versione** viene impostato automaticamente utilizzando la regola del numero di versione del prodotto impostata in precedenza.

1. Selezionare **OK** per creare il prodotto e chiudere la finestra di dialogo.
1. Viene visualizzata la pagina dei dettagli del nuovo prodotto. Si noti che i valori sono già stati inseriti per alcuni campi, ad esempio **Gruppo di dimensioni di immagazzinamento**, **Gruppo di dimensioni di tracciabilità** e/o **Gruppo di modelli di articoli**. Questi campi sono stati impostati automaticamente perché il prodotto viene rilasciato nella persona giuridica *DEMF* e utilizza i criteri di rilascio prodotto *Componenti* associati alla categoria di prodotti di progettazione *Componenti*. Poiché l'articolo *D0006* è stato utilizzato in precedenza con un modello per impostare una riga per la persona giuridica *DEMF*, i valori inseriti sono stati presi dall'articolo *D0006*.

    ![Dettagli prodotto rilasciato](media/product-details.png "Dettagli prodotto rilasciato")

1. Nel riquadro azioni, nella scheda **Progetta**, nel gruppo **Gestione modifiche di progettazione** selezionare **Versioni di progettazione** per visualizzare le versioni del prodotto.

    ![Versioni di progettazione](media/engineering-versions-list.png "Versioni di progettazione")

1. Nella pagina **Versioni di progettazione** si noti che è presente una sola versione per il prodotto e che è attiva.
1. Selezionare la versione per visualizzarne i dettagli.

    ![Dettagli della versione di progettazione](media/engineering-version-details.png "Dettagli della versione di progettazione")

1. Nella pagina **Versione di progettazione**, nella Scheda dettaglio **Distinta base** selezionare **Crea DBA**.
1. Nella finestra di dialogo **Crea DBA** impostare i valori seguenti:

    - **Numero DBA:** Z0001
    - **Nome:** Set altoparlanti
    - **Sito:** 1

    ![Creazione di una DBA](media/create-bom.png "Creazione di una DBA")

1. Selezionare **OK** per aggiungere la DBA e chiudere la finestra di dialogo.
1. Nella Scheda dettaglio **Distinte base** selezionare **Distinta base**.
1. Nella pagina **Distinte base**, nella Scheda dettaglio **Righe distinte base** aggiungere tre righe, una per ogni numero di articolo *D0001*, *D0003* e *D0006*.

    ![Aggiunta di righe DBA](media/bom.png "Aggiunta di righe DBA")

1. Selezionare **Salva**.
1. Chiudere la pagina.
1. Nella pagina **Versione di progettazione**, nella Scheda dettaglio **Distinta base** selezionare **Approva**.
1. Nella finestra di dialogo visualizzata, selezionare **OK**.

    ![Approvazione della DBA](media/approve-dialog.png "Approvazione della DBA")

1. Nella pagina **Versione di progettazione**, nella Scheda dettaglio **Distinta base** selezionare **Attiva**.
1. Si noti che le caselle di controllo **Attiva** e **Approvata** sono selezionate per la DBA.

    ![DBA attiva e approvata](media/approved-bom.png "DBA attiva e approvata")

1. Chiudere la pagina.

## <a name="release-an-engineering-product-to-a-local-company"></a><a name="release"></a>Rilasciare un prodotto di progettazione a un'azienda locale

Il prodotto è ora stato progettato dal reparto tecnico. Per questo esempio, il prodotto è un prototipo che il reparto tecnico progettato per un cliente. Perché il cliente è un cliente della persona giuridica *USMF*, il prodotto deve essere rilasciato a tale persona giuridica.

1. Mantenere la persona giuridica impostata su *DEMF*. Utilizzare il selettore per le aziende sul lato destro della barra di navigazione in base alle esigenze.
1. Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.
1. Selezionare il prodotto *Z0001*.
1. Nella scheda **Prodotto** del riquadro azioni, nel gruppo **Gestisci** selezionare **Struttura prodotto di rilascio** per aprire la procedura guidata **Rilascia prodotti**.
1. Nella pagina **Seleziona i prodotti di progettazione da rilasciare** selezionare la casella di controllo **Seleziona** per il prodotto *Z0001*.

    ![Selezione dei prodotti di progettazione da rilasciare](media/select-eng-product-to-release.png "Selezione dei prodotti di progettazione da rilasciare")

1. Selezionare **Dettagli sul rilascio**.
1. Viene visualizzata la pagina **Dettagli rilascio prodotto** in cui è possibile esaminare i dettagli del prodotto che verrà rilasciato e la sua struttura. Si noti che l'opzione **Invia DBA** è impostata su *Sì*. Pertanto, sia il prodotto *Z0001* e tutti i relativi articoli figlio della DBA verranno rilasciati.

    È possibile selezionare qualsiasi elemento figlio nel riquadro sinistro per rivederne i dettagli. Se a un articolo figlio è associata una DBA, è anche possibile scegliere di rilasciare la DBA di tale articolo.

    ![Revisione dei dettagli di rilascio del prodotto](media/product-release-details.png "Revisione dei dettagli di rilascio del prodotto")

1. Chiudere la pagina per tornare alla procedura guidata **Rilascia prodotti**.
1. Selezionare **Avanti** per aprire la pagina **Seleziona prodotti da rilasciare**. Eventuali prodotti standard (non di progettazione) selezionati verrebbero visualizzati in questa pagina. Si noti che quando si rilascia un prodotto standard selezionando **Struttura prodotto di rilascio**, vengono rilasciati anche il ciclo di lavorazione e la DBA relativi.

    ![Selezione dei prodotti standard da rilasciare](media/select-std-product-to-release.png "Selezione dei prodotti standard da rilasciare")

1. Selezionare **Avanti** per aprire la pagina **Seleziona varianti prodotto da rilasciare**. Per questo esempio non sono presenti varianti.
1. Selezionare **Avanti** per aprire la pagina **Seleziona società**.
1. Selezionare le società a cui il prodotto deve essere rilasciato. Per questo esempio, selezionare la casella di controllo per **USMF**.

    ![Selezione delle aziende a cui eseguire il rilascio](media/select-release-companies.png "Selezione delle società a cui eseguire il rilascio")

1. Selezionare **Avanti** per aprire la pagina **Conferma selezione**.
1. Selezionare **Fine**.

## <a name="review-and-accept-the-product-before-you-release-it-in-the-local-company"></a><a name="accept"></a>Esaminare e accettare il prodotto prima di rilasciarlo nell'azienda locale

Il reparto tecnico ha ora rilasciato le informazioni alle aziende locali in cui verrà utilizzato il prodotto. In questo esempio, l'azienda locale è *USMF*.

Poiché il campo **Accettazione prodotto** è stato impostato su *Manuale* nella pagina **Parametri per gestione modifiche di progettazione** per la società *USMF*, i prodotti devono essere accettati manualmente prima di essere rilasciati a tale società. In altre parole, i prodotti devono essere esaminati e accettati prima che vengano rilasciati.

Per esaminare il prodotto e rilasciarlo nella società *USMF*, eseguire queste operazioni.

1. Impostare la persona giuridica impostata *USMF*. Utilizzare il selettore per le aziende sul lato destro della barra di navigazione.
1. Andare a **Gestione modifiche di progettazione &gt; Comune &gt; Rilasci prodotto &gt; Rilasci di prodotto aperti**.

    Nella pagina **Rilasci di prodotto aperti** viene visualizzato il prodotto *Z0001*, con stato *In attesa di accettazione*.

    ![Rilasci di prodotti aperti](media/open-product-releases.png "Rilasci di prodotti aperti")

1. Selezionare il valore nella colonna **Numero prodotto** per aprire la pagina **Dettagli rilascio prodotto**. Si notino i seguenti dettagli:

    - La Scheda dettaglio **Generale** mostra le informazioni sul rilascio del prodotto, come la società di rilascio (*DEMF* per questo esempio), il sito di rilascio (*1*) e il sito ricevente (*1*). Perché non è stato specificato un sito di ricevimento nella procedura guidata **Prodotti di rilascio**, il valore del sito di rilascio viene copiato nel sito ricevente.
    - Nella Scheda dettaglio **Dettagli sul rilascio** vengono visualizzate le informazioni sul prodotto e sulla versione rilasciata. Qui è possibile modificare le impostazioni, ad esempio le date di validità.
    - La Scheda dettaglio **Ciclo di lavorazione** mostra il ciclo di lavorazione del prodotto. Tuttavia, per questo esempio, non è stato rilasciato alcun ciclo di lavorazione.

    ![Dettagli rilascio del prodotto](media/product-release-details-2.png "Dettagli rilascio del prodotto")

1. Dopo aver esaminato le informazioni, è possibile accettare il prodotto e, in questo modo, rilasciarlo nella società *USMF*. Nel riquadro azioni selezionare **Azioni &gt; Accetta**.
1. Il prodotto è stato rilasciato nella società *USMF*. Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**. Viene visualizzato l'articolo *Z0001*.

## <a name="use-the-product-in-transactions-in-the-local-company"></a>Utilizzare il prodotto nelle transazioni nell'azienda locale

Il responsabile dei dati master per la società *USMF* desidera assicurarsi che il prodotto sia nello stato *Prototipo* per garantire che gli utenti vengano avvisati se lo aggiungono accidentalmente ai processi su cui lavorano.

1. Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**.
1. Selezionare il prodotto *Z0001* per aprirne la pagina dei dettagli. Per trovare il prodotto, è possibile utilizzare il filtro.
1. Nella scheda **Progetta** del riquadro azioni, nel gruppo **Gestione modifiche di progettazione** selezionare **Versioni di progettazione**.
1. Nella pagina **Versioni di progettazione** selezionare il numero di versione *V-01* per aprire la pagina dei dettagli.
1. Nel riquadro azioni, nella scheda **Prodotto**, nel gruppo **Stato del ciclo di vita** selezionare **Modifica stato del ciclo di vita**.
1. Nella finestra di dialogo a discesa **Modifica stato del ciclo di vita** impostare il campo **Stato** su *Prototipo*, quindi selezionare **OK**.

    ![Modifica dello stato del ciclo di vita](media/change-lifecycle-state.png "Modifica dello stato del ciclo di vita")

## <a name="add-the-engineering-product-to-a-sales-order"></a>Aggiungere un prodotto di progettazione a un ordine cliente

Il prodotto può ora essere venduto a un cliente. Per aggiungere il prodotto a un ordine cliente, eseguire queste operazioni:

1. Selezionare **Vendite e marketing &gt; Ordini cliente &gt; Tutti gli ordini cliente**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine cliente** impostare il campo **Conto cliente** su *US-0002* e quindi selezionare **OK**.
1. Viene aperto il nuovo ordine cliente. Nella Scheda dettaglio **Righe ordine cliente** aggiungere una riga e impostare il campo **Numero articolo** su *Z000*.
1. Nel riquadro azioni selezionare **Salva**.

    Viene visualizzato un messaggio di avviso che informa che l'articolo ha uno stato uguale a *Prototipo*. Tuttavia, poiché il messaggio è solo un avviso, l'ordine cliente è stato comunque creato.

    ![Ordine cliente per un prodotto di progettazione](media/sales-order-eng-product.png "Ordine cliente per un prodotto di progettazione")

## <a name="request-changes-in-the-engineering-product"></a>Richiedere modifiche nel prodotto di progettazione

Il prodotto è stato inviato a un cliente, ma il cliente non era completamente soddisfatto e fornisce un feedback che include suggerimenti per il miglioramento. Mentre il cliente parla al telefono con un addetto alle vendite, quest'ultimo può richiedere le modifiche che il cliente descrive.

1. Selezionare **Vendite e marketing &gt; Ordini cliente &gt; Tutti gli ordini cliente**.
1. Trovare e aprire l'ordine cliente creato nell'esercizio precedente.
1. Nella Scheda dettaglio **Righe ordine cliente** selezionare **Gestione modifiche di progettazione &gt; Nuova richiesta modifica di progettazione**.

    ![Creazione di una richiesta di modifica di progettazione per un ordine cliente](media/sales-order-eng-change-request.png "Creazione di una richiesta di modifica di progettazione per un ordine cliente")

1. Compilare la richiesta di modifica di progettazione, in base al feedback del cliente. Per questo esempio, impostare i seguenti valori:

    - **Richiesta di modifica:** *555*
    - **Titolo:** *Modifica cliente Z0001*
    - **Priorità:** *Bassa*
    - **Categoria:** Imposta modifica
    - **Gravità:** *Media*

1. Nella Scheda dettaglio **Informazioni** selezionare **Nuovo &gt; Nota** per aggiungere una nota alla griglia.
1. Nel campo **Descrizione** per la nuova nota, indicare che l'articolo *D0003* deve essere eliminato dalla DBA. Se è necessario aggiungere ulteriori informazioni per la nota, è possibile inserire testo nel campo **Note**.

    ![Richiesta di modifica di progettazione](media/eng-change-request.png "Richiesta di modifica di progettazione")

1. Nel riquadro azioni selezionare **Salva**.
1. Si noti che l'articolo è stato aggiunto automaticamente alla Scheda dettaglio **Prodotti** e che l'origine della richiesta di modifica di progettazione (l'ordine cliente) è stata aggiunta alla Scheda dettaglio **Origine**.

## <a name="make-changes-to-the-product-by-using-an-engineering-change-order"></a>Apportare modifiche al prodotto utilizzando un ordine di modifica di progettazione

L'addetto alle vendite sa che il prodotto è importante e che è stato progettato appositamente per il cliente. Pertanto, l'addetto alle vendite chiama un tecnico nella società *DEMF* per informarli della richiesta di modifica. In questo modo, il tecnico può accelerare il processo.

Il tecnico ora esamina la richiesta del cliente e crea un ordine di modifica per il prodotto.

1. Perché l'ingegnere lavora nella società *DEMF*, impostare l'entità giuridica su *DEMF*. Utilizzare il selettore per le aziende sul lato destro della barra di navigazione.
1. Andare a **Gestione modifiche di progettazione &gt; Comune &gt; Richieste modifiche di progettazione**.
1. Aprire la richiesta di modifica *555*.
1. Esaminare le informazioni e approvare la modifica. Nel riquadro azioni, nella scheda **Modifica richiesta**, nel gruppo **Cambia stato** selezionare **Approva**.
1. Andare a **Gestione modifiche di progettazione &gt; Comune &gt; Ordini di modifica di progettazione**.
1. Nel riquadro azioni selezionare **Nuovo** per creare un ordine di modifica e impostarne i seguenti valori:

    - **Ordine di modifica:** *555*
    - **Titolo:** *Modifica cliente Z0001*
    - **Categoria:** *Modifica cliente*
    - **Priorità:** *Bassa*
    - **Gravità:** *Media*

1. Nella Scheda dettaglio **Prodotti interessati**, selezionare **Nuovo &gt; Aggiungi prodotto esistente** per aggiungere una riga alla griglia e impostare i valori seguenti:

    - **Prodotto:** *Z0001*
    - **Impatto:** *Nuova versione*

    ![Creazione di un ordine di modifica di progettazione](media/eng-change-order.png "Creazione di un ordine di modifica di progettazione")

1. Si noti che, poiché il campo **Impatto** è stato impostato su *Nuova versione*, il campo **Nuova versione** nella scheda **Dettagli** della Scheda dettaglio **Dettagli prodotto** mostra il numero della nuova versione (in questo esempio *V-02*).

    ![Dettagli prodotto per un ordine di modifica di progettazione](media/eng-change-order-product-details.png "Dettagli prodotto per un ordine di modifica di progettazione")

1. Nel riquadro azioni selezionare **Salva**.
1. Nella Scheda dettaglio **Dettagli prodotto**, nella scheda **Distinta base**, selezionare **Righe** per aprire la DBA per la versione *V-01* del prodotto *Z0001*.

    ![Righe DBA per prodotti di progettazione](media/eng-product-bom-lines.png "Righe DBA per prodotti di progettazione")

1. Selezionare la riga per il numero di articolo *D0003* e quindi, nel riquadro azioni, selezionare **Elimina**. Il valore del campo **Tipo di modifica** per la riga viene modificato in *Eliminato*.
1. Nel riquadro azioni selezionare **Salva**.

    ![Righe DBA per prodotti di progettazione modificate](media/eng-product-bom-lines-modified.png "Righe DBA per prodotti di progettazione modificate")

1. Chiudere la pagina **Riga DBA** per tornare alla pagina **Ordine di modifica di progettazione**.
1. Nella Scheda dettaglio **Dettagli prodotto**, nella scheda **Distinta base** si noti che il valore del campo **Tipo di modifica** per la DBA *Z0001* è ora *Modificato*.

    ![Ordine di modifica di progettazione che include una DBA modificata](media/eng-change-order-changed-bom.png "Ordine di modifica di progettazione che include una DBA modificata")

    L'ordine ora deve essere approvato prima che le modifiche possano essere elaborate. Quando le modifiche vengono elaborate, i prodotti vengono aggiornati con le modifiche incluse nell'ordine di modifica di progettazione. Per questo esempio, la persona che crea l'ordine di modifica di progettazione è stata specificata come approvatore.

1. Nel riquadro azioni, nella scheda **Ordine di modifica**, nel gruppo **Cambia stato** selezionare **Approva**.
1. Selezionare **Elabora** per aggiornare le informazioni sul prodotto.

## <a name="release-the-changed-product"></a>Rilasciare il prodotto modificato

Il prodotto può ora essere rilasciato di nuovo nella società *USMF* e quindi inviato al cliente. Per rilasciare il prodotto direttamente dall'ordine di modifica di progettazione, eseguire queste operazioni.

1. Aprire l'ordine di modifica di progettazione creato nell'esercizio precedente, se non è già aperto.
1. Nel riquadro azioni, nella scheda **Ordine di modifica**, nel gruppo **Rilasci prodotto** selezionare **Cerca**.
1. I risultati della ricerca mostrano a quali aziende sono stati rilasciati i prodotti interessati. Chiudere i risultati della ricerca.
1. Nel riquadro azioni, nella scheda **Ordine di modifica**, nel gruppo **Rilasci prodotto** selezionare **Visualizza** per aprire la finestra di dialogo **Rilasci** in cui è possibile visualizzare i risultati della ricerca precedente.
1. Selezionare ogni azienda a cui si desidera rilasciare i prodotti.
1. Selezionare **OK** per chiudere la finestra di dialogo **Rilasci** e tornare all'ordine di modifica.
1. Nel riquadro azioni, nella scheda **Ordine di modifica**, nel gruppo **Rilasci prodotto** selezionare **Elabora** per rilasciare i prodotti interessati alle aziende selezionate. In alternativa, selezionare **Struttura prodotto di rilascio** per avviare il processo di rilascio.

## <a name="complete-the-change-order"></a>Completare l'ordine di modifica

Per contrassegnare l'ordine di modifica come completato, a indicare che non sono rimaste ulteriori azioni, selezionare **Completa** nel riquadro Azioni.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
