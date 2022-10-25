---
title: Scenario dei ritardi di produzione
description: Questo articolo descrive lo scenario dei ritardi di produzione, che genera una notifica se la velocità effettiva di produzione scende al di sotto di un valore di soglia specifico.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 25ccbda1628544f14dc32d9bea3f2162ad47d79e
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690023"
---
# <a name="the-production-delays-scenario"></a>Scenario dei ritardi di produzione

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Lo scenario *ritardi di produzione* genera una notifica se la produttività scende al di sotto di un valore di soglia specifico. In questo scenario, un segnale *part-out* viene inviato all'hub IoT Microsoft Azure per ciascun articolo prodotto. In Dynamics 365 Supply Chain Management, il ritardo dell'ordine viene calcolato in base al tempo di esecuzione pianificato dell'ordine di produzione, al numero di articoli che devono essere prodotti, al tempo di esecuzione del processo e al numero di segnali *part-out* ricevuti. Una notifica di ritardo viene generata se il numero di segnali *part-out* per il processo scendono al di sotto del valore della soglia.

## <a name="scenario-dependencies"></a>Dipendenze dello scenario

Lo scenario *ritardi di produzione* ha le seguenti dipendenze:

- Un avviso può essere attivato solo se un ordine di produzione è in esecuzione su un computer mappato.
- Un segnale che rappresenta il segnale *part-out* di un computer mappato deve essere inviato all'hub IoT con un nome di proprietà univoco.
- Una proprietà UNIX timestamp, dove il valore è espresso in millisecondi (ms), deve essere presente nel messaggio dell'hub IoT di Azure.

## <a name="prepare-demo-data-for-the-product-delays-scenario"></a>Preparare i dati demo per lo scenario di ritardi del prodotto

Se vuoi utilizzare un sistema demo per testare lo scenario *ritardi di produzione* utilizza un sistema in cui i [dati demo](../../fin-ops-core/fin-ops/get-started/demo-data.md) sono installati, seleziona la persona giuridica *USMF* (società) e prepara i dati demo aggiuntivi come descritto in questa sezione. Se stai utilizzando i tuoi sensori e dati, puoi saltare questa sezione.

### <a name="set-up-sensor-simulator"></a>Configurare un simulatore di sensori

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

### <a name="configure-the-production-floor-execution-interface"></a>Configurare l'interfaccia di esecuzione dell'area di produzione

Se non l'hai già fatto, configura l'interfaccia di esecuzione del reparto di produzione per mostrare i processi assegnati alla risorsa *3118* (*Macchina per il taglio della gomma*). Per le istruzioni, vedi le sezioni successive:

- [Configurare l'interfaccia di esecuzione dell'area di produzione](sdi-scenario-equipment-downtime.md#config-pfe)
- [Abilitare l'opzione ricerca nell'interfaccia di esecuzione dell'area di produzione](sdi-scenario-equipment-downtime.md#enable-pfe-search)

### <a name="start-the-first-job-in-the-batch-order"></a>Avviare il primo processo nell'ordine batch

Attieniti alla seguente procedura per avviare il primo processo nell'ordine batch.

1. Andare a **Controllo produzione \> Esecuzione produzione \> Esecuzione area di produzione**.
1. Nel campo **ID badge** immetti *123*. Quindi seleziona **Accedi**.
1. Se ti viene richiesto un motivo di assenza, seleziona una delle schede per l'assenza, quindi seleziona **OK**.
1. Nel campo **Ricerca** inserisci il numero dell'ordine batch che hai precedentemente annotato. Quindi seleziona il tasto **Reso**.
1. Seleziona l'ordine, quindi seleziona **Avvia processo**.
1. Nella finestra di dialogo **Avvia processo** seleziona **Avvia**.

## <a name="set-up-the-production-delays-scenario"></a>Impostare lo scenario ritardi di produzione

Segui questi passaggi per impostare lo scenario *ritardi di produzione* in Supply Chain Management.

1. Vai a **Controllo di produzione \> Impostazione \> Intelligence dei dati del sensore \> Scenari**.
1. Nella casella dello scenario **ritardi di produzione** seleziona **Configura** per aprire la procedura guidata di configurazione per questo scenario.
1. Nella pagina **Sensori**, seleziona **Nuovo** per aggiungere un sensore alla griglia. Quindi imposta i seguenti campi per il sensore:

    - **ID sensore** – Inserisci l'ID del sensore che stai utilizzando. Se stai usando il simulatore online Azure IoT Raspberry PI e lo hai configurato come descritto in [Impostare un sensore simulato per il test](sdi-set-up-simulated-sensor.md), immetti *ProductionDelay*.
    - **Descrizione sensore** - Immetti una descrizione del sensore.

1. Ripeti il passaggio precedente per ogni sensore aggiuntivo che vuoi aggiungere. Puoi tornare e aggiungere più sensori in qualsiasi momento.
1. Selezionare **Avanti**.
1. Sulla pagina **Mapping di record aziendale**, nella sezione **Sensori** seleziona il record per uno dei sensori che hai appena aggiunto.
1. Nella sezione **Mapping di record aziendale** seleziona **Nuovo** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta il campo **Record aziendale** sulla risorsa che stai utilizzando per monitorare il sensore selezionato. Se stai utilizzando i dati demo che hai creato in precedenza in questo articolo, impostalo su *3118, Macchina per il taglio della gomma*.
1. Selezionare **Avanti**.
1. Sulla pagina **Soglia di deviazione ritardo di produzione**, se stai utilizzando i dati demo che hai creato in precedenza in questo articolo, procedi nel seguente modo:

    1. Seleziona l'intestazione di colonna **Relazione articolo** per aprire una finestra di dialogo a discesa che include filtri di ricerca per la colonna. Immetti *P0111* nella casella di ricerca, quindi seleziona **Applica**.
    2. Seleziona la riga in cui il campo **Operazione** è impostato su *Trim/Taglia*. Imposta il campo **Soglia di notifica per ritardo (%)** sulla soglia (in percentuale) a cui deve essere inviata una notifica.

1. Selezionare **Avanti**.
1. Sulla pagina **Attiva sensori** nella griglia, seleziona il sensore che hai aggiunto, quindi seleziona **Attiva**. Per ogni sensore attivato nella griglia, viene visualizzato un segno di spunta nella colonna **Attivo**.
1. Selezionare **Fine**.

## <a name="work-with-the-production-delays-scenario"></a>Utilizzare lo scenario ritardi di produzione

### <a name="view-production-delay-data-on-the-resource-status-page"></a>Visualizzare i dati sul ritardo di produzione nella pagina Stato risorsa

Sulla pagina **Stato risorsa** i supervisori possono monitorare una sequenza temporale dei segnali ricevuti dai sensori mappati su ciascuna risorsa macchina. Segui questi passaggi per configurare la sequenza temporale.

1. Vai a **Controllo produzione \> Esecuzione produzione \> Stato risorsa**.
1. Nella finestra di dialogo **Configura**, imposta i seguenti campi:

    - **Risorsa** – Seleziona le risorse che desideri monitorare. Se stai lavorando con i dati demo, seleziona *3118*.
    - **Serie temporale 1** – Seleziona il record (chiave metrica) che ha il seguente formato per il nome: *ProductionJobDelayed:ActualQuantity:&lt;JobId&gt;*
    - **Nome visualizzato** - Immetti *Segnale parte completata*.
