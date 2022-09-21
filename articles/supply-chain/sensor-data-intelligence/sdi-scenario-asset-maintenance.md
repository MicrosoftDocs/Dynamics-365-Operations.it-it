---
title: Scenario di manutenzione dei cespiti
description: Questo articolo descrive lo scenario di manutenzione dei cespiti che consente di utilizzare i dati dei sensori per creare record di contatori che tengono traccia dell'utilizzo di un cespite macchina.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: ff3944b987314a688a5829b05f8627479e3e79ed
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428340"
---
# <a name="the-asset-maintenance-scenario"></a>Scenario di manutenzione dei cespiti

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Lo scenario *manutenzione dei cespiti* consente di utilizzare i dati del sensore per creare record di contatori. I record del contatore tengono traccia dell'utilizzo di un cespite macchina e vengono utilizzati come input per generare il programma di manutenzione per i cespiti macchina.

## <a name="prepare-demo-data-for-the-asset-maintenance-scenario"></a>Preparare i dati demo per lo scenario di manutenzione dei cespiti

Se vuoi utilizzare un sistema demo per testare lo scenario *manutenzione dei cespiti* utilizza un sistema in cui i [dati demo](../../fin-ops-core/fin-ops/get-started/demo-data.md) sono installati, seleziona la persona giuridica *USMF* (società) e prepara i dati demo aggiuntivi come descritto in questa sezione. Se stai utilizzando i tuoi sensori e dati, puoi saltare questa sezione.

In questa sezione, imposterai il cespite *AK-101, lama d'aria* nei dati demo come esempio. Vedrai quindi come prevedere gli imminenti lavori di manutenzione in base ai segnali dei sensori che misurano il numero di ore di funzionamento della lama d'aria. Stabilirai anche un piano di manutenzione in cui la lama d'aria deve essere mantenuta ogni 10.000 ore.

### <a name="set-up-a-sensor-simulator"></a>Configurare un simulatore di sensori

Se vuoi provare questo scenario senza utilizzare un sensore fisico, puoi impostare un simulatore per generare i segnali richiesti. Per ulteriori informazioni, vedi [Impostare un sensore simulato per il test](sdi-set-up-simulated-sensor.md).

### <a name="create-an-asset-counter-to-track-production-hours"></a>Creare un contatore di cespiti per tenere traccia delle ore di produzione

Segui questi passaggi per creare un contatore di cespiti per tenere traccia delle ore di produzione.

1. Vai a **Gestione cespiti \> Imposta \> Tipi di cespiti \> Contatori**.
1. Nel riquadro azioni seleziona **Nuovo** per creare un contatore.
1. Nell'intestazione, impostare i seguenti valori:

    - **Contatore:** *ProductionHr*
    - **Nome:** *Ore di produzione*

1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Unità:** *ora*
    - **Aggiornamento:** *manuale*
    - **Totale aggregato:** *somma*

1. Nella Scheda dettaglio **Tipi di cespite** seleziona **Aggiungi riga**.
1. Sulla nuova riga, imposta il campo **Tipo di cespite** su *lama d'aria*.

### <a name="create-a-maintenance-plan-for-the-asset"></a>Creare un piano di manutenzione per il cespite

Segui questi passaggi per creare un piano di manutenzione per il cespite.

1. Passa a **Gestione cespiti \> Impostazione \> Manutenzione preventiva \> Piano di manutenzione**.
1. Nel riquadro azioni, seleziona **Nuova** per creare un piano di manutenzione.
1. Nell'intestazione, impostare i seguenti valori:

    - **Piano di manutenzione:** *AirKnife*
    - **Nome:** *Piano per lame d'aria*

1. Nella Scheda dettaglio **Dettagli** impostare i seguenti valori:

    - **Data piano:** immetti la data odierna.
    - **Attivo:** *Sì*

1. Nella Scheda dettaglio **Righe**, seleziona **Aggiungi riga del contatore cespiti** per aggiungere una riga alla griglia. Quindi imposta i seguenti valori per la riga:

    - **Descrizione dell'ordine di lavoro:** *Manutenzione per lama d'aria*
    - **Tipo di processo di manutenzione:** *Preventivo*
    - **Tipo di intervallo:** *Ripetuto a partire dall'ultimo ordine di lavoro*
    - **Frequenza periodo:** *10000*
    - **Contatore:** *ProductionHr*

## <a name="set-up-the-asset-maintenance-scenario"></a>Impostare lo scenario di manutenzione dei cespiti

Segui questi passaggi per impostare lo scenario *manutenzione dei cespiti* in Supply Chain Management.

1. Vai a **Gestione cespiti \> Impostazione \> Intelligence dei dati del sensore \> Scenari**.
1. Nella casella dello scenario **Manutenzione dei cespiti** seleziona **Configura** per aprire la procedura guidata di configurazione per questo scenario.
1. Nella pagina **Sensori**, seleziona **Nuovo** per aggiungere un sensore alla griglia. Quindi imposta i seguenti campi per il sensore:

    - **ID sensore** – Inserisci l'ID del sensore che stai utilizzando. Se stai usando il simulatore online Azure IoT Raspberry PI e lo hai configurato come descritto in [Impostare un sensore simulato per il test](sdi-set-up-simulated-sensor.md), immetti *AssetMaintenance*.
    - **Descrizione sensore** - Immetti una descrizione del sensore.

1. Ripeti il passaggio precedente per ogni sensore aggiuntivo che vuoi aggiungere. Puoi tornare e aggiungere più sensori in qualsiasi momento.
1. Selezionare **Avanti**.
1. Sulla pagina **Mapping di record aziendale**, nella sezione **Sensori** seleziona il record per uno dei sensori che hai appena aggiunto.
1. Nella sezione **Mapping di record aziendale** seleziona **Nuovo** per aggiungere una riga alla griglia.
1. Nella nuova riga, il campo **Tipo di record aziendale** dovrebbe essere impostato automaticamente su *Assets(EntAssetObjectTable)*. Imposta il campo **Record aziendale** sulla risorsa che stai utilizzando per monitorare il sensore selezionato. Se stai utilizzando i dati demo che hai creato in precedenza in questo articolo, impostalo su *AK-101, AK-101 lama d'aria per riga 1*.
1. Immediatamente dopo aver selezionato un tipo di record aziendale per la riga aggiunta nel passaggio precedente, una seconda riga viene aggiunta automaticamente alla griglia. In questa riga, il campo **Tipo di record aziendale** deve essere impostato su *Counters(EntAssetCounterType)*. Imposta il campo **Record aziendale** sul contatore dei cespiti che stai aggiornando in base ai segnali del sensore selezionato. Se stai utilizzando i dati demo che hai creato in precedenza in questo articolo, impostalo su *ProductionHr, ore di produzione*.
1. Selezionare **Avanti**.
1. Sulla pagina **Attiva sensori** nella griglia, seleziona il sensore che hai aggiunto, quindi seleziona **Attiva**. Per ogni sensore attivato nella griglia, viene visualizzato un segno di spunta nella colonna **Attivo**.
1. Selezionare **Fine**.

## <a name="work-with-the-asset-maintenance-scenario"></a>Utilizzare lo scenario di manutenzione dei cespiti

### <a name="view-counter-values"></a>Visualizzare i valori contatore

Dopo che i dati sono stati preparati, e lo scenario *manutenzione dei cespiti* è configurato e attivato, puoi vedere come vengono inseriti i record per un contatore di cespiti in base ai dati del sensore.

1. Vai a **Gestione cespiti \> Cespiti \> Tutti i cespiti**.
1. Trova e seleziona il cespite che vuoi controllare. Se stai utilizzando i dati demo che hai creato in precedenza in questo articolo, seleziona *AK-101*.
1. Nel riquadro azioni, nella scheda **Cespite**, nel gruppo **Preventivo** seleziona **Contatori** per aprire la pagina dei record dei contatori per il cespite *AK-101*.

### <a name="generate-maintenance-work-orders"></a>Generare gli ordini di lavoro in manutenzione

Dopo aver abilitato lo scenario *manutenzione dei cespiti* e impostato il piano di manutenzione, è possibile eseguire il programma di manutenzione per generare ordini di lavoro di manutenzione. Per ulteriori informazioni su come utilizzare la manutenzione preventiva, vedi [Panoramica della manutenzione preventiva](../asset-management/preventive-and-reactive-maintenance/preventive-maintenance-overview.md).
