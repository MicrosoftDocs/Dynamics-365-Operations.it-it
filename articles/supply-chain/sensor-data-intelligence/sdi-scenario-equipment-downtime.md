---
title: Scenario dello stato della macchina
description: Questo articolo descrive lo scenario dello stato della macchina, che consente di utilizzare i dati del sensore per monitorare la disponibilità delle apparecchiature.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreNotification, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 30fdfb898384aea4c1f8cb2f36f9e104cd316f90
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689641"
---
# <a name="the-machine-status-scenario"></a>Scenario dello stato della macchina

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Lo scenario dello *stato della macchina* consente di utilizzare i dati del sensore per monitorare la disponibilità delle apparecchiature. Se imposti un sensore che invia un segnale quando un processo di produzione su una risorsa macchina produce output, ma non viene ricevuto alcun segnale del sensore entro un intervallo specificato, viene visualizzata una notifica sul dashboard del supervisore.

## <a name="scenario-dependencies"></a>Dipendenze dello scenario

Lo scenario *stato della macchina* ha le seguenti dipendenze:

- Una notifica può essere attivata solo se un processo di produzione è in esecuzione su un computer mappato.
- Un segnale che rappresenta un segnale *part-out* deve essere inviato all'hub IoT.

## <a name="prepare-demo-data-for-the-machine-status-scenario"></a>Preparare i dati demo per lo scenario dello stato della macchina

Se vuoi utilizzare un sistema demo per testare lo scenario *stato della macchina* utilizza un sistema in cui i [dati demo](../../fin-ops-core/fin-ops/get-started/demo-data.md) sono installati, seleziona la persona giuridica *USMF* (società) e prepara i dati demo aggiuntivi come descritto in questa sezione. Se stai utilizzando i tuoi sensori e dati, puoi saltare questa sezione.

### <a name="set-up-a-sensor-simulator"></a>Configurare un simulatore di sensori

Se vuoi provare questo scenario senza utilizzare un sensore fisico, puoi impostare un simulatore per generare i segnali richiesti. Per ulteriori informazioni, vedi [Impostare un sensore simulato per il test](sdi-set-up-simulated-sensor.md).

### <a name="verify-that-resource-3118-is-used-for-product-p0111"></a>Verificare che la risorsa 3118 sia utilizzata per il prodotto P0111

Un ordine di produzione verrà programmato e rilasciato. Pertanto, un processo di produzione viene rilasciato alla risorsa *3118* (*Macchina per il taglio della gomma*). Segui questi passaggi per verificare che la risorsa *3118* sia usata per il prodotto *P0111* nei tuoi dati demo.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Trova e seleziona il prodotto in cui il campo **Numero articolo** è impostato su *P0111*.
1. Nel riquadro azioni, scheda **Progetta**, gruppo **Visualizza**, seleziona **Ciclo**.
1. Sulla pagina **Ciclo**, nella scheda **Panoramica** nella parte inferiore della pagina, seleziona la riga in cui il campo **Numero operazione** è impostato su *30*.
1. Sulla scheda **Requisiti risorsa** nella parte inferiore della pagina, assicurati che la risorsa *3118* (*Macchina per il taglio della gomma*) sia associata all'operazione.

### <a name="create-and-release-a-production-order-for-product-p0111"></a>Creare e rilasciare un ordine di produzione per il prodotto P0111

Attieniti alla seguente procedura per creare e rilasciare un ordine di produzione per il prodotto *P0111*.

1. Fare clic su **Controllo produzione \> Ordini di produzione \> Tutti gli ordini di produzione**.
1. Sulla pagina **Tutti gli ordini di produzione** nel riquadro azioni, seleziona **Nuovo ordine batch**.
1. Nella finestra di dialogo **Crea batch** imposta i valori seguenti:

    - **Numero articolo:** *P0111*
    - **Quantità:** *10*

1. Seleziona **Crea** per creare l'ordine e tornare alla pagina **Tutti gli ordini di produzione**.
1. Utilizza il campo **Filtro** per cercare gli ordini di produzione in cui il campo **Numero articolo** è impostato su *P0111*. Quindi trova e seleziona l'ordine di produzione appena creato.
1. Nel riquadro azioni, scheda **Ordine di produzione**, gruppo **Processo**, selezionare **Stima**.
1. Nella finestra di dialogo **Stima**, seleziona **OK** per eseguire la stima.
1. Nel riquadro azioni, scheda **Ordine di produzione**, gruppo **Processo**, seleziona **Rilascia**.
1. Nella finestra di dialogo **Rilascia** prendi nota del numero dell'ordine batch appena creato.
1. Seleziona **OK** per rilasciare l'ordine.

### <a name="configure-the-production-floor-execution-interface"></a><a name="config-pfe"></a>Configurare l'interfaccia di esecuzione dell'area di produzione

Utilizzerai l'interfaccia di esecuzione del reparto di produzione per avviare il processo pianificato e rilasciato per il numero articolo *P0111* nella sezione precedente. Segui questi passaggi per configurare l'interfaccia di esecuzione dell'area di produzione.

1. Andare a **Controllo produzione \> Esecuzione produzione \> Esecuzione area di produzione**.
1. Se non hai configurato l'interfaccia in precedenza, viene visualizzata una pagina di accesso. Immettere le proprie credenziali.
1. Nella pagina di benvenuto, seleziona **Configura** per aprire la procedura guidata **Configura dispositivo**.
1. Sulla pagina **Configura dispositivo - Passaggio 1: seleziona la configurazione** seleziona la configurazione *predefinita*.
1. Selezionare **Avanti**.
1. Sulla pagina **Configura dispositivo - Passaggio 2 - Definisci l'area di produzione** imposta il campo **Risorsa** su *3118*.
1. Seleziona **OK**.

### <a name="enable-the-search-option-in-the-production-floor-execution-interface"></a><a name="enable-pfe-search"></a>Abilitare l'opzione ricerca nell'interfaccia di esecuzione dell'area di produzione

Per facilitare la ricerca del processo di produzione per l'ordine di produzione rilasciato in precedenza, attieniti alla seguente procedura per abilitare l'opzione di ricerca nell'interfaccia di esecuzione del reparto di produzione.

1. Andare a **Controllo produzione \> Imposta \> Esecuzione produzione \> Configura esecuzione area di produzione**.
1. Seleziona la configurazione *predefinita*.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella Scheda dettaglio **Generale**, imposta l'opzione **Abilita ricerca** su *Sì*.
1. Chiudi la pagina.

### <a name="start-the-first-job-in-the-batch-order"></a>Avviare il primo processo nell'ordine batch

Attieniti alla seguente procedura per avviare il processo pianificato sulla risorsa *3118*.

1. Andare a **Controllo produzione \> Esecuzione produzione \> Esecuzione area di produzione**.
1. Nel campo **ID badge** immetti *123*. Quindi seleziona **Accedi**.
1. Se ti viene richiesto un motivo di assenza, seleziona una delle schede per l'assenza, quindi seleziona **OK**.
1. Nel campo **Ricerca** inserisci il numero dell'ordine batch che hai precedentemente annotato. Quindi seleziona il tasto **Reso**.
1. Seleziona l'ordine, quindi seleziona **Avvia processo**.
1. Nella finestra di dialogo **Avvia processo** seleziona **Avvia**.

## <a name="set-up-the-machine-status-scenario"></a>Impostare lo scenario dello stato della macchina

Segui questi passaggi per impostare lo scenario *stato della macchina* in Supply Chain Management.

1. Vai a **Controllo di produzione \> Impostazione \> Intelligence dei dati del sensore \> Scenari**.
1. Nella casella dello scenario **stato della macchina** seleziona **Configura** per aprire la procedura guidata di configurazione per questo scenario.
1. Nella pagina **Sensori**, seleziona **Nuovo** per aggiungere un sensore alla griglia. Quindi imposta i seguenti campi per il sensore:

    - **ID sensore** – Inserisci l'ID del sensore che stai utilizzando. Se stai usando il simulatore online Azure IoT Raspberry PI e lo hai configurato come descritto in [Impostare un sensore simulato per il test](sdi-set-up-simulated-sensor.md), immetti *MachineStatus*.
    - **Descrizione sensore** - Immetti una descrizione del sensore.

1. Ripeti il passaggio precedente per ogni sensore aggiuntivo che vuoi aggiungere. Puoi tornare e aggiungere più sensori in qualsiasi momento.
1. Selezionare **Avanti**.
1. Sulla pagina **Mapping di record aziendale**, nella sezione **Sensori** seleziona il record per uno dei sensori che hai appena aggiunto.
1. Nella sezione **Mapping di record aziendale** seleziona **Nuovo** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta il campo **Record aziendale** sulla risorsa che stai utilizzando per monitorare il sensore selezionato. Se stai utilizzando i dati demo che hai creato in precedenza in questo articolo, imposta il campo su *3118, Macchina per il taglio della gomma*.
1. Selezionare **Avanti**.
1. Sulla pagina **Soglia stato della macchina** definisci quanto tempo dopo l'ultimo segnale *part-out* che il sistema deve inviare una notifica sullo stato della macchina. Sono disponibili due metodi per definire la soglia:

    - **Soglia predefinita (minuti)** – Imposta questo campo per definire la soglia predefinita. Il valore si applicherà quindi a tutte le risorse in cui il campo **Soglia per determinare la macchina che non risponde (minuti)** è impostato su due minuti o meno. Il valore massimo è *2* (minuti).
    - **Soglia per determinare la macchina che non risponde (minuti)** – Per ogni risorsa nella griglia per la quale non si desidera utilizzare la soglia predefinita, immetti un valore di sostituzione in questo campo. Le risorse impostate per utilizzare una soglia di due minuti o meno utilizzeranno l'impostazione **Soglia predefinita (minuti)**.

    > [!NOTE]
    > In genere, utilizzerai un segnale *part-out* per monitorare lo stato della macchina. Pertanto, è necessario verificare che la soglia per ciascuna risorsa macchina sia più lunga di quella richiesta dalla macchina per produrre ciascuna parte.

1. Selezionare **Avanti**.
1. Sulla pagina **Attiva sensori** nella griglia, seleziona il sensore che hai aggiunto, quindi seleziona **Attiva**. Per ogni sensore attivato nella griglia, viene visualizzato un segno di spunta nella colonna **Attivo**.
1. Selezionare **Fine**.

## <a name="work-with-the-machine-status-scenario"></a>Utilizzare lo scenario dello stato della macchina

Dopo aver installato i sensori e configurato lo scenario, è possibile visualizzare gli eventi stato della macchina in Supply Chain Management. Questa sezione descrive dove e come visualizzare queste informazioni.

### <a name="view-machine-status-data-on-the-resource-status-page"></a>Visualizzare i dati sullo stato della macchina nella pagina Stato risorsa

Sulla pagina **Stato risorsa** i supervisori possono monitorare una sequenza temporale del segnale *part-out* ricevuto dai sensori mappati su ciascuna risorsa macchina. Segui questi passaggi per configurare la sequenza temporale.

1. Vai a **Controllo produzione \> Esecuzione produzione \> Stato risorsa**.
1. Nella finestra di dialogo **Configura**, imposta i seguenti campi:

    - **Risorsa** – Seleziona le risorse che desideri monitorare. Se stai lavorando con i dati demo, seleziona *3118*.
    - **Serie temporale 1** – Seleziona il record (chiave metrica) che ha il seguente formato per il nome: *MachineReportingStatus:&lt;Sensor&gt;*
    - **Nome visualizzato** - Immetti *Segnale parte completata*.

L'illustrazione seguente mostra un esempio di dati di stato della macchina sulla pagina **Stato risorsa** durante il funzionamento standard.

![Dati sullo stato della macchina nella pagina Stato risorsa durante il funzionamento standard.](media/sdi-resource-status-downtime-up.png "Dati sullo stato della macchina nella pagina Stato risorsa durante il funzionamento standard")

L'illustrazione seguente mostra un esempio di dati sullo stato della macchina quando viene rilevato un tempo di inattività.

![Dati sullo stato della macchina nella pagina Stato risorsa quando viene rilevato un tempo di inattività.](media/sdi-resource-status-downtime-down.png "Dati sullo stato della macchina nella pagina Stato risorsa quando viene rilevato un tempo di inattività")

### <a name="view-machine-status-on-the-notifications-page"></a>Visualizzare lo stato della macchina nella pagina Notifiche

Sulla pagina **Notifiche** i supervisori possono visualizzare le notifiche che vengono generate quando è trascorso troppo tempo dall'ultima consegna del sensore di un segnale *part-out*. Ciascuna notifica fornisce una panoramica del processo di produzione interessato dall'interruzione e offre la possibilità di riassegnare il processo interessato a un'altra risorsa.

Per aprire la pagina **Notifiche** vai a **Controllo produzione \> Richieste di informazioni e report \> Intelligence dei dati del sensore \> Notifiche**.

Nella figura seguente viene illustrato un esempio di notifica dello stato della macchina.

![Esempio di notifica dello stato della macchina.](media/sdi-resource-status-downtime-notification.png "Esempio di notifica dello stato della macchina")
