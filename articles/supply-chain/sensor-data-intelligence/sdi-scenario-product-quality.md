---
title: Scenario della qualità del prodotto
description: In questo articolo vengono fornite informazioni sullo scenario della qualità del prodotto. Questo scenario utilizza un sensore per misurare la qualità di un batch di prodotti e genera un avviso se una misura non rientra in una soglia definita.
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
ms.openlocfilehash: c0f1c57251234921779f67faf61d47cdde119e64
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690050"
---
# <a name="the-product-quality-scenario"></a>Scenario della qualità del prodotto

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Nello scenario *qualità del prodotto* viene impostato un sensore per misurare la qualità di un batch di prodotti nel reparto produzione. Se una misura non rientra in una soglia definita per il prodotto, viene visualizzata una notifica sul dashboard del supervisore. Ad esempio, un sensore misura l'umidità di un prodotto alimentare che esce dalla linea di produzione. Se la misura è al di fuori del valore minimo o massimo consentito per l'umidità del prodotto, viene generata una notifica.

## <a name="scenario-dependencies"></a>Dipendenze dello scenario

Lo scenario *qualità del prodotto* ha le seguenti dipendenze:

- È possibile attivare un avviso solo se un ordine di produzione è in esecuzione su una macchina mappata e se la macchina produce un prodotto con un attributo batch mappato.
- Un segnale che rappresenta l'attributo batch deve essere inviato all'hub IoT e un nome di proprietà univoco deve essere incluso.

## <a name="prepare-demo-data-for-the-product-quality-scenario"></a>Preparare i dati demo per lo scenario di qualità del prodotto

Se vuoi utilizzare un sistema demo per testare lo scenario *qualità del prodotto* utilizza un sistema in cui i [dati demo](../../fin-ops-core/fin-ops/get-started/demo-data.md) sono installati, seleziona la persona giuridica *USMF* (società) e prepara i dati demo aggiuntivi come descritto in questa sezione. Se stai utilizzando i tuoi sensori e dati, puoi saltare questa sezione.

In questa sezione, imposterai i dati demo in modo da poter utilizzare il prodotto rilasciato *P0111* (*Caso composito*) con lo scenario *qualità del prodotto*. In questo scenario, il sistema tiene traccia se un valore di attributo batch misurato da un sensore è al di fuori della soglia definita per un attributo batch associato al prodotto.

### <a name="set-up-a-sensor-simulator"></a>Configurare un simulatore di sensori

Se vuoi provare questo scenario senza utilizzare un sensore fisico, puoi impostare un simulatore per generare i segnali richiesti. Per ulteriori informazioni, vedi [Impostare un sensore simulato per il test](sdi-set-up-simulated-sensor.md).

### <a name="associate-a-batch-attribute-and-resource-with-product-p0111"></a>Associare un attributo batch e una risorsa al prodotto P0111

Segui questi passaggi per associare un attributo batch al prodotto *P0111* (*Caso composito*) e verificare che la risorsa *3118* (*Macchina per il taglio della gomma*) sia usata.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Trova e seleziona il prodotto in cui il campo **Numero articolo** è impostato su *P0111*.
1. Nel riquadro azioni, nella scheda **Gestione articoli**, nel gruppo **Attributi batch**, seleziona **Specifico del prodotto**.
1. Sulla pagina **Specifico del prodotto** seleziona **Nuovo** per creare un attributo batch specifico del prodotto.
1. Nell'intestazione, imposta i seguenti campi:

    - **Codice attributo** – Seleziona l'ambito degli attributi che monitorerai (*Tabella*, *Gruppo*, o *Tutto*). Per questo scenario, seleziona *Tabella*, perché monitorerai sempre un singolo attributo.
    - **Relazione attributo** – Seleziona l'attributo di cui utilizzerai il valore dello scenario *qualità del prodotto* da monitorare. Per questo esempio, seleziona *Concentrazione*, che è un attributo incluso nei dati demo standard.

1. Sulla Scheda dettaglio **Valori**, nei campi **Minimo** e **Massimo** definisci l'intervallo di valori accettabili che l'attributo deve riportare per superare il controllo qualità. Se il sensore segnala un valore al di fuori di questo intervallo, il sistema lo identificherà come una violazione della qualità. Gli altri campi di questa Scheda dettaglio non sono rilevanti per lo scenario *qualità del prodotto*. I valori predefiniti che vedi attualmente provengono dai dati demo. Pertanto, lasciali così come sono e chiudi la pagina **Specifico del prodotto** per tornare alla pagina **Dettagli del prodotto rilasciato** per l'articolo *P0111*.
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

## <a name="set-up-the-product-quality-scenario"></a>Configurare lo scenario della qualità del prodotto

Segui questi passaggi per impostare lo scenario *qualità del prodotto* in Supply Chain Management.

1. Vai a **Controllo di produzione \> Impostazione \> Intelligence dei dati del sensore \> Scenari**.
1. Nella casella dello scenario **Qualità del prodotto** seleziona **Configura** per aprire la procedura guidata di configurazione per questo scenario.
1. Nella pagina **Sensori**, seleziona **Nuovo** per aggiungere un sensore alla griglia. Quindi imposta i seguenti campi per il sensore:

    - **ID sensore** – Inserisci l'ID del sensore che stai utilizzando. Se stai usando il simulatore online Azure IoT Raspberry PI e lo hai configurato come descritto in [Impostare un sensore simulato per il test](sdi-set-up-simulated-sensor.md), immetti *Qualità*.
    - **Descrizione sensore** - Immetti una descrizione del sensore.

1. Ripeti il passaggio precedente per ogni sensore aggiuntivo che vuoi aggiungere. Puoi tornare e aggiungere più sensori in qualsiasi momento.
1. Selezionare **Avanti**.
1. Sulla pagina **Mapping di record aziendale**, nella sezione **Sensori** seleziona il record per uno dei sensori che hai appena aggiunto.
1. Nella sezione **Mapping di record aziendale** seleziona **Nuovo** per aggiungere una riga alla griglia.
1. Nella nuova riga, il campo **Tipo di record aziendale** dovrebbe essere impostato automaticamente su *Resources(WrkCtrTable)*. Imposta il campo **Record aziendale** sulla risorsa che stai utilizzando per monitorare il sensore selezionato. Se stai utilizzando i dati demo che hai creato in precedenza in questo articolo, impostalo su *3118, Macchina per il taglio della gomma*.
1. Immediatamente dopo aver selezionato un tipo di record aziendale per la riga aggiunta nel passaggio precedente, una seconda riga viene aggiunta automaticamente alla griglia. In questa riga, il campo **Tipo di record aziendale** deve essere impostato su *Batch attributes(PdsBatchAttrib)*. Imposta il campo **Record aziendale** sull'attributo batch che stai utilizzando per monitorare il sensore selezionato. Se stai utilizzando i dati demo che hai creato in precedenza in questo articolo, impostalo su *Concentrazione, percentuale di concentrazione*.
1. Selezionare **Avanti**.
1. Sulla pagina **Attiva sensori** nella griglia, seleziona il sensore che hai aggiunto, quindi seleziona **Attiva**. Per ogni sensore attivato nella griglia, viene visualizzato un segno di spunta nella colonna **Attivo**.
1. Selezionare **Fine**.

## <a name="work-with-the-product-quality-scenario"></a>Utilizzare lo scenario della qualità del prodotto

### <a name="view-product-quality-data-on-the-resource-status-page"></a>Visualizzare i dati sulla qualità del prodotto nella pagina Stato risorsa

Sulla pagina **Stato risorsa** i supervisori possono monitorare una sequenza temporale del segnale di qualità del prodotto ricevuto dai sensori mappati su ciascuna risorsa macchina. Segui questi passaggi per configurare la sequenza temporale.

1. Vai a **Controllo produzione \> Esecuzione produzione \> Stato risorsa**.
1. Nella finestra di dialogo **Configura**, imposta i seguenti campi:

    - **Risorsa** – Seleziona le risorse che desideri monitorare. Se stai lavorando con i dati demo, seleziona *3118*.
    - **Serie temporale 1** – Seleziona il record (chiave metrica) che ha il seguente formato per il nome: *ProductQuality:&lt;JobId&gt;:&lt;AttributeName&gt;*
    - **Nome visualizzato** - Immetti *Valori di attributo batch*.

L'illustrazione seguente mostra un esempio di dati sulla qualità del prodotto sulla pagina **Stato risorsa** quando il valore rientra nell'intervallo di valori accettabili.

![Dati sulla qualità del prodotto nella pagina Stato risorsa quando il valore rientra nell'intervallo.](media/sdi-product-quality-in-range.png "Dati sulla qualità del prodotto nella pagina Stato risorsa quando il valore rientra nell'intervallo")

L'illustrazione seguente mostra un esempio di dati sulla qualità del prodotto quando viene rilevato un valore fuori intervallo.

![Dati sulla qualità del prodotto nella pagina Stato risorsa quando il valore fuori intervallo viene rilevato.](media/sdi-product-quality-out-of-range.png "Dati sulla qualità del prodotto nella pagina Stato risorsa quando il valore fuori intervallo viene rilevato")

### <a name="view-product-quality-data-on-the-notifications-page"></a>Visualizzare i dati sulla qualità del prodotto nella pagina Notifiche

Sulla pagina **Notifiche** i supervisori possono visualizzare la notifica che viene generata quando il sensore misura un valore di attributo batch che non rientra nella soglia definita per l'attributo batch. Ciascuna notifica fornisce una panoramica del processo di produzione interessato dall'interruzione e offre la possibilità di riassegnare il processo interessato a un'altra risorsa.

Per aprire la pagina **Notifiche** vai a **Controllo produzione \> Richieste di informazioni e report \> Intelligence dei dati del sensore \> Notifiche**.

Nella figura seguente viene illustrato un esempio di notifica della qualità del prodotto.

![Esempio di notifica della qualità del prodotto.](media/sdi-product-quality-notification.png "Esempio di notifica della qualità del prodotto")
