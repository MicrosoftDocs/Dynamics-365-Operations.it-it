---
title: Spedizione pacchi di piccole dimensioni
description: In questo argomento vengono fornite informazioni sulla funzionalità di spedizione di pacchi di piccole dimensioni. Questa funzionalità consente a Microsoft Dynamics 365 Supply Chain Management di inviare i dettagli su un contenitore imballato al vettore, quindi ricevere un'etichetta di spedizione, una tariffa di spedizione e un numero di riferimento da quel vettore.
author: Mirzaab
manager: tfehr
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRateEngine, TMSCarrier, CustTable, TMSShippingCarrierCustomerAccount, TMSSmallParcelShippingFeature
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-08
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 350193a0054ef879ece3dd2dfcc4105476981837
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078277"
---
# <a name="small-parcel-shipping"></a>Spedizione pacchi di piccole dimensioni

[!include [banner](../includes/banner.md)]

La funzionalità per la spedizione di pacchi di piccole dimensioni consente a Microsoft Dynamics 365 Supply Chain Management di interagire direttamente con i vettori fornendo un framework per la comunicazione tramite le API del vettore. Questa funzionalità è utile quando si spediscono singoli ordini cliente tramite vettori di spedizione commerciali invece di utilizzare la spedizione in container o la spedizione a carico parziale (LTL).

La funzione di spedizione di pacchi di piccole dimensioni con il tuo corriere tramite un apposito *motore tariffe*. La tua organizzazione deve sviluppare questo motore tariffe in collaborazione con il vettore o il servizio hub del vettore. Il motore tariffe consente a Supply Chain Management di inviare i dettagli su un contenitore imballato al vettore, quindi ricevere un'etichetta di spedizione, una tariffa di spedizione e un numero di riferimento da quel vettore.

La tariffa di spedizione restituita viene aggiunta all'ordine cliente associato come addebito vario. L'etichetta di spedizione restituita può quindi essere stampata automaticamente utilizzando una stampante Zebra Programming Language (ZPL) e applicata alla spedizione. Il vettore eseguirà la scansione di questa etichetta di spedizione quando ritira i pacchi presso il magazzino.

## <a name="prepare-your-system-to-support-sps"></a>Preparare il sistema per supportare la spedizione di pacchi di piccole dimensioni

Prima di poter iniziare a utilizzare la funzionalità di spedizione di pacchi di piccole dimensioni:, è necessario attivare la funzionalità spedizione di pacchi di piccole dimensioni: in Gestione delle funzionalità, aggiungere il motore tariffe e configurare i moduli **Gestione trasporti** e **Gestione magazzino** per supportarlo.

### <a name="turn-on-the-sps-feature"></a>Attivare la funzionalità di spedizione di pacchi di piccole dimensioni

Prima di poter utilizzare questa funzionalità, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Gestione trasporto*
- **Nome funzionalità:** *Spedizione di pacchi di piccole dimensioni*

### <a name="deploy-and-set-up-rate-engines"></a>Distribuire e configurare i motori tariffe

Supply Chain Management non include motori tariffe. È necessario ottenere o creare tutti i motori tariffe richiesti e quindi aggiungerli al sistema. Tuttavia, Microsoft fornisce un motore tariffe demo che è possibile utilizzare per i test.

#### <a name="download-and-deploy-the-demo-rate-engine"></a>Scaricare e distribuire il motore tariffe demo

Seguire questi passaggi per scaricare il motore tariffe demo.

1. Su GitHub, scaricare la [libreria di collegamento dinamico (DLL) per il motore tariffe demo](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).
1. Sul server di Supply Chain Management, salvare la DLL nella cartella **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin**.

#### <a name="create-and-deploy-functional-rate-engines"></a>Creare e distribuire motori tariffe funzionali

Per informazioni su come creare e distribuire motori tariffe funzionali in modo che possano essere utilizzati in un ambiente di produzione o di test, vedere i seguenti argomenti:

- [Creare un nuovo motore di gestione del trasporto](../transportation/create-new-transportation-management-engine.md)
- [Impostare i motori di gestione del trasporto](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-transportation-management-engines)

Per altre informazioni su come creare un motore tariffe per spedizione di pacchi di piccole dimensioni:, vedere il seguente post di blog: [Spedizione di pacchi di piccole dimensioni: come sfruttare la funzionalità di spedizione di pacchi di piccole dimensioni: in Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).

#### <a name="set-up-a-rate-engine-in-supply-chain-management"></a>Configurare un motore tariffe in Supply Chain Management

Dopo aver creato e distribuito un motore tariffe per spedizione di pacchi di piccole dimensioni, segui questi passaggi per configurarlo.

1. Passare a **Gestione trasporto \> Impostazioni \> Motori \> Motore tariffe**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, impostare i seguenti campi.

    - **Motore tariffe**: immettere un nome univoco per il motore tariffe. Se si utilizza il motore tariffe demo, immettere *Motore tariffe demo*.
    - **Nome**: immettere una breve descrizione del motore tariffe. Se si utilizza il motore tariffe demo, immettere *Motore tariffe demo*.
    - **ID di valutazione dei metadati**: selezionare la base da utilizzare per calcolare la tariffa. Ad esempio, la tariffa potrebbe essere calcolata in base alla distanza. Se si sta utilizzando il motore tariffe demo, è possibile lasciare vuoto questo campo.
    - **Assembly motore**: immettere il nome file del pacchetto DLL distribuito. Se si utilizza il motore tariffe demo, immettere *TMSSmallParcelShippingEngine.dll*.
    - **Classe motore**: immettere il nome della classe che è stato stabilito per il motore tariffe. Se si utilizza il motore tariffe demo, immettere *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.

## <a name="example-scenario"></a>Scenario di esempio

Questo scenario di esempio mostra come configurare e utilizzare la spedizione di pacchi di piccole dimensioni dopo aver preparato il sistema come descritto in precedenza in questo argomento. Questo scenario utilizza il motore tariffe demo citato in precedenza.

### <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Per elaborare lo scenario utilizzando i record e i valori demo specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

### <a name="set-up-the-scenario"></a>Impostare lo scenario

Per questo scenario di esempio, è necessario disporre di un vettore demo, gruppo di vettori, criteri di imballaggio e profilo di imballaggio. Le seguenti sottosezioni spiegano come preparare i record necessari per lo scenario. In uno scenario di produzione, il processo di installazione configurazione in genere è simile al processo descritto qui. Tuttavia, verranno impostati valori diversi.

#### <a name="set-up-carriers"></a>Configurare i vettori

Per configurare un vettore, seguire questi passaggi:

1. Vai a **Gestione trasporto \> Impostazioni \> Vettori \> Vettori spedizione**.
1. Nel riquadro azioni selezionare **Nuovo** per aggiungere un vettore.
1. Nell'intestazione, impostare i seguenti valori:

    - **Vettore spedizione:** *vettore demo*
    - **Nome:** *vettore demo*
    - **Modalità:** *Terra*

1. Nella Scheda dettaglio **Panoramica**, impostare i seguenti valori:

    - **Attiva vettore di spedizione:** *Sì*
    - **Attiva valutazione vettore:** *Sì*

1. Nella Scheda dettaglio **Servizi**, seleziona **Nuovo** per aggiungere una servizio alla griglia.
1. Impostare i seguenti valori per il nuovo servizio:

    - **Servizio vettore:** *servizio vettore demo*
    - **Nome:** *servizio vettore demo*
    - **Metodo di trasporto:** *Terra*

    Immettere valori arbitrari per tutti gli altri campi, come richiesto. (Quando si salva il nuovo record del vettore di spedizione, verrà creata una nuova modalità di consegna e il campo **Modalità di spedizione** verrà impostato automaticamente.)

1. Nella Scheda dettaglio **Profili valutazione** selezionare **Nuovo** per aggiungere un profilo di valutazione alla griglia.
1. Impostare i seguenti valori per il nuovo profilo:

    - **Profilo di valutazione:** *Servizio vettore demo*
    - **Nome:** *servizio vettore demo*
    - **Motore tariffe:** *Motore tariffe demo*

    Immettere valori arbitrari per tutti gli altri campi, come richiesto.

1. Nel riquadro azioni selezionare **Salva**.

Per ulteriori informazioni su come configurare i vettori, vedere [Configurare vettori di spedizione](../transportation/tasks/set-up-shipping-carriers.md).

#### <a name="set-up-carrier-service-accounts"></a>Configurare gli account del servizio vettori

Seguire questi passaggi per configurare un account di servizio vettore.

1. Andare a **Gestione trasporto \> Impostazioni \> Valutazione \> Account di servizio vettore**.
1. Nel riquadro azioni seleziona **Nuovo** per aggiungere un account di servizio vettore.
1. Impostare i seguenti valori per il nuovo account:

    - **Vettore spedizione:** *vettore demo*
    - **Servizio vettore:** *servizio vettore demo*
    - **Numero di conto cliente del vettore:** il numero di conto cliente del vettore utilizzato per verificare e autenticare la connessione al vettore di spedizione. Il vettore fornirà questo valore. Se stai utilizzando il servizio demo, puoi inserire un valore arbitrario.
    - **Sito:** *6*
    - **Magazzino:** *62*

    > [!NOTE]
    > Spesso, il valore **Numero di conto cliente del vettore** è l'unico valore richiesto per autenticare la connessione. Tuttavia, se l'operatore richiede parametri di autenticazione aggiuntivi, l'organizzazione dovrebbe personalizzare questa pagina per aggiungere campi extra come appropriato.

#### <a name="set-up-a-container-packing-policy"></a>COnfigurare i criteri di imballaggio dei contenitori

Per configurare i criteri di imballaggio del contenitore, seguire questi passaggi.

1. Se non hai già configurato una definizione di stampante ZPL, utilizza l'applicazione dell'agente di distribuzione documenti per configurarla. Per ulteriori informazioni, vedere [Panoramica sulla stampa dei documenti](../../fin-ops-core/dev-itpro/analytics/print-documents.md) e argomenti correlati.
1. Passare a **Gestione magazzino \> Impostazioni \> Contenitori \> Criteri imballaggio contenitore**.
1. Nel riquadro azioni selezionare **Nuovo** per aggiungere un criteri di imballaggio dei contenitori.
1. Nell'intestazione dei nuovi criteri, impostare i seguenti valori:

    - **Criteri di imballaggio del contenitore:** *Criteri di imballaggio demo*
    - **Descrizione:** una descrizione dei criteri

1. Nella Scheda dettaglio **Panoramica**, impostare i seguenti valori:

    - **Magazzino:** *62*
    - **Ubicazione predefinita per spedizione finale:** *Portellone*
    - **Unità peso:** *KG*
    - **Criteri chiusura contenitore:** *Rilascio automatico*
    - **Criteri rilascio contenitore:** *Rendi disponibile in ubicazione di spedizione finale*

1. Nella scheda Dettagli **Manifesto contenitore**, è possibile impostare i seguenti valori:

    - **Manifesto automatico alla chiusura del contenitore:** *Sì*
    - **Requisiti manifesto per contenitore:** *Gestione trasporto*
    - **Stampa contenuto contenitore:** *No*

1. Nella scheda Dettagli **Stampa etichetta vettore**, è possibile impostare i seguenti valori:

    - **Stampa etichetta spedizione contenitore:** *Sempre*
    - **Nome stampante:** il nome della stampante ZPL che deve stampare le etichette di spedizione

#### <a name="set-up-a-packing-profile"></a>Configurare un profilo imballaggio

Per configurare un profilo di imballaggio, seguire questi passaggi.

1. Andare a **Gestione magazzino \> Impostazioni \> Imballaggio \> Profili imballaggio**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere un profilo di imballaggio.
1. Impostare i seguenti valori per il nuovo profilo:

    - **ID profilo imballaggio:** *Profilo di imballaggio demo*
    - **Descrizione:** una descrizione del profilo
    - **Criteri di imballaggio del contenitore:** *Criteri di imballaggio demo*
    - **Modalità ID contenitore:** *Auto*
    - **Tipo di contenitore:** *Piccola scatola*

#### <a name="set-up-a-customer-to-use-the-sps-carrier"></a>Configurare un cliente per utilizzare il vettore per la spedizione di pacchi di piccole dimensioni

Segui questi passaggi per configurare un cliente in modo che possa utilizzare il vettore che hai creato.

1. Passare a **Contabilità clienti \> clienti \> Tutti i clienti**.
1. Nella griglia, trovare e selezionare il cliente *US-027*.
1. Nel riquadro azioni, nella scheda **Generale**, nel gruppo **Configura**, selezionare **Conti cliente vettore**.
1. Nella pagina **Conti cliente vettore**, nel riquadro Azioni selezionare **Nuovo** per aggiungere un conto alla griglia.
1. Impostare i seguenti valori per il nuovo account:

    - **Vettore spedizione:** *vettore demo*
    - **Numero di conto cliente del vettore:** *12345* (il valore non è importante per questo scenario, ma verrà indicato nella sezione successiva.)

### <a name="go-through-the-example-scenario"></a>Seguire lo scenario di esempio

Dopo aver configurato tutti i dati di esempio come descritto nella sezione precedente, sei pronto per passare allo scenario di esempio.

#### <a name="create-a-sales-order-and-process-the-work"></a>Creare un ordine cliente ed elaborare il lavoro

Segui questi passaggi per creare un ordine cliente.

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Selezionare **Nuovo** per creare un ordine cliente.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta il campo **Conto cliente**, su *US-027*.
1. Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.
1. Viene aperto il nuovo ordine cliente. Nella Scheda dettaglio **Intestazione ordine cliente**, imposta il campo **Numero di conto cliente del vettore** sul valore che hai selezionato per questo cliente in precedenza (*12345*).
1. Nella sezione **Righe ordine cliente**, aggiungi una riga di vendita e imposta i seguenti valori per essa:

    - **Numero articolo:** *A0002*
    - **Quantità:** *1*
    - **Sito:** *6*
    - **Magazzino:** *62*

1. Passa alla visualizzazione **Intestazione**.
1. Nella Scheda dettaglio **Consegna**, imposta i seguenti valori:

    - **Vettore spedizione:** *vettore demo*
    - **Servizio vettore:** *servizio vettore demo*

1. Torna alla visualizzazione **Righe**. Se viene richiesto di aggiornare la modalità di consegna per le righe di vendita, seleziona **Sì**.
1. Nella sezione **Righe ordine cliente**, seleziona la riga dell'ordine che hai configurato in precedenza, quindi seleziona **Inventario \> Prenotazione**.
1. Nella pagina **Prenotazione**, seleziona **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.
1. Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.

    Viene creato il lavoro per spostare gli articoli dall'ubicazione di prelievo alla stazione di imballaggio.

1. Nella sezione **Righe ordine di vendita**, seleziona **Magazzino \> Dettagli spedizione**.
1. Nella pagina **Dettagli spedizione**, prendi nota dell'ID spedizione. Ne avrai bisogno quando imballerai il pacco per spedizione alla stazione di imballaggio.
1. Chiudi la pagina **Dettagli spedizione** per tornare all'ordine cliente.
1. Prendi nota del numero dell'ordine cliente, quindi passa a **Gestione magazzino \> Lavoro \> Tutti i lavori**.
1. Utilizza il numero dell'ordine cliente per trovare e selezionare il lavoro creato per l'ordine.
1. Nel riquadro Azioni, nella scheda **Lavoro**, seleziona **Lavoro completato**.
1. Nella pagina **Completamento del lavoro**, nel campo **ID utente** seleziona un ID utente. Quindi, nel riquadro azioni seleziona **Convalida lavoro**.
1. Se il lavoro supera la convalida, seleziona **Completa lavoro** nel riquadro Azioni.

    Il lavoro viene contrassegnato come completato per simulare lo spostamento degli articoli verso la stazione di imballaggio.

#### <a name="pack-the-shipment"></a>Imballare la spedizione

Segui questi passaggi per imballare la spedizione.

1. Vai a **Gestione magazzino \> Configura \> Lavoratore** e assicurati che il tuo account utente sia associato a un account lavoratore per la gestione del magazzino.
1. Vai a **Gestione magazzino \> Prelievo e containerizzazione \> Imballaggio**.
1. Nella finestra di dialogo **Seleziona stazione di imballaggio**, imposta i seguenti valori:

    - **Sito:** *6*
    - **Magazzino:** *62*
    - **Ubicazione:** *Imballaggio*
    - **ID profilo imballaggio:** *Profilo di imballaggio demo*

1. Selezionare **OK**.
1. Viene visualizzata la pagina **Imballa**. In uno scenario di produzione, un lavoratore eseguirà la scansione di una targa o un ID spedizione. Tuttavia, per questo scenario, apri la pagina **Tutte le spedizioni** e cerca il numero di spedizione per la spedizione appena creata. Quindi immetti questo valore nel campo **Targa o spedizione** della pagina **Imballa**. In alternativa, immetti l'ID della spedizione di cui hai preso nota in precedenza.
1. Nel riquadro azioni selezionare **Nuovo contenitore**.
1. La finestra di dialogo che appare mostra i dettagli sul nuovo contenitore. Lascia i valori predefiniti, quindi seleziona **OK**.
1. Nella pagina **Imballa**, nella Scheda dettaglio **Imballaggio articolo**, nel campo **Identificatore**, seleziona *A0002* per imballare quell'articolo. L'articolo viene aggiunto al contenitore.
1. Nel riquadro azioni, seleziona **Contenitori per spedizione**.

    La pagina **Contenitori per spedizione** visualizzata ha una riga per il contenitore che hai appena creato. Tuttavia, il campo **ID manifesto contenitore** in quella riga è attualmente vuoto, perché non hai ancora ricevuto l'etichetta di spedizione e il numero di tracciamento dal corriere.

1. Nel riquadro azioni selezionare **Chiudi contenitore**.
1. Nella finestra di dialogo **Chiudi contenitore**, imposta il campo **Peso lordo** su *1 kg* e quindi seleziona **OK**.

    L'etichetta di spedizione dovrebbe ora essere stampata sulla stampante ZPL selezionata in precedenza. Il risultato sarà simile all'esempio seguente.

    ![Etichetta di spedizione di esempio](media/sps-label-example.png "Etichetta di spedizione di esempio")

1. Tieni presente che i valori **ID manifesto contenitore** e **Trasporto totale** sono stati aggiunti come ricevuti dal vettore.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]