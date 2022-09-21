---
title: Scenario del tempo di inattività cespite
description: Questo articolo descrive lo scenario del tempo di inattività cespite, che consente di utilizzare i dati del sensore per monitorare la disponibilità dei cespiti.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, EntAssetObjectProductionStop
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 944818557deebed06c02c00fd69de6e8f08bda83
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428374"
---
# <a name="the-asset-downtime-scenario"></a>Scenario del tempo di inattività cespite

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Lo scenario del tempo di inattività cespite genera un record di del tempo di inattività cespite per manutenzione se non viene ricevuto alcun segnale da una macchina entro una determinata soglia di tempo dalla ricezione dell'ultimo segnale. Lo scenario richiede di dotare la macchina di un sensore che invii periodicamente un segnale all'hub IoT di Azure mentre la macchina è in funzione, ma non invii un segnale quando la macchina non è in funzione.

## <a name="set-up-the-asset-downtime-scenario"></a>Impostare lo scenario del tempo di inattività cespite

Segui questi passaggi per impostare lo scenario *tempo di inattività cespite* in Supply Chain Management.

1. Vai a **Gestione cespiti \> Impostazione \> Intelligence dei dati del sensore \> Scenari** per aprire la pagina **Scenari**.
2. Nella casella dello scenario **tempo di inattività cespite** seleziona **Configura** per aprire la procedura guidata di configurazione per questo scenario.
3. Nella pagina **Sensori**, seleziona **Nuovo** per aggiungere un sensore alla griglia. Quindi imposta i seguenti campi per il sensore:

    - **ID sensore** – Inserisci l'ID del sensore che stai utilizzando. Se stai usando il simulatore online Azure IoT Raspberry PI e lo hai configurato come descritto in [Impostare un sensore simulato per il test](sdi-set-up-simulated-sensor.md), immetti *AssetDownTime*.
    - **Descrizione sensore** - Immetti una descrizione del sensore.

4. Ripeti il passaggio precedente per ogni sensore aggiuntivo che vuoi aggiungere. Puoi tornare e aggiungere più sensori in qualsiasi momento.
5. Selezionare **Avanti**.
6. Sulla pagina **Mapping di record aziendale**, nella sezione **Sensori** seleziona il record per uno dei sensori che hai appena aggiunto.
7. Nella sezione **Mapping di record aziendale** seleziona **Nuovo** per aggiungere una riga alla griglia.
8. Nella nuova riga, imposta il campo **Record aziendale** sulla risorsa che stai utilizzando per monitorare il sensore selezionato. Se stai utilizzando i dati demo, seleziona *AK-101, lama d'aria per la riga 1*.
9. Selezionare **Avanti**.
10. Sulla pagina **soglia del tempo di inattività cespite**, definisci quanto tempo dopo l'ultimo segnale il sistema deve attendere prima di inviare una notifica di inattività del cespite. Sono disponibili due metodi per definire la soglia:

    - **Soglia predefinita (minuti)** – Imposta questo campo per definire la soglia predefinita. Questo valore si applica a tutte le risorse in cui il campo **Soglia di notifica (minuti)** è impostato su due minuti o meno. Il valore massimo è *2* (minuti).
    - **Soglia per determinare la macchina che non risponde (minuti)** – Per ogni risorsa nella griglia per la quale non si desidera utilizzare la soglia predefinita, immetti un valore di sostituzione in questo campo. Le risorse impostate per utilizzare una soglia di due minuti o meno utilizzeranno l'impostazione **Soglia predefinita (minuti)**.
11. Selezionare **Avanti**.
12. Sulla pagina **Attiva sensori** nella griglia, seleziona il sensore che hai impostato, quindi seleziona **Attiva**. Per ogni sensore attivato nella griglia, viene visualizzato un segno di spunta nella colonna **Attivo**.
13. Selezionare **Fine**.

## <a name="work-with-the-asset-downtime-scenario"></a>Utilizzare lo scenario del tempo di inattività cespite

Se non viene ricevuto alcun segnale del sensore da un cespite entro la soglia definita nella configurazione dello scenario, il sistema creerà un record del tempo di inattività per manutenzione del cespite. I responsabili devono rivedere periodicamente i record dei tempi di inattività (ad esempio, una volta durante ogni turno di lavoro) e applicare i codici di motivazione e gli orari di fine appropriati per ogni registrazione dei tempi di inattività. Attenersi alla seguente procedura per visualizzare i record dei tempi di inattività per manutenzione di un cespite:

1. Vai a **Gestione cespiti > Cespiti > Tutti i cespiti**.
2. Trova e seleziona il cespite che vuoi controllare. Se stai utilizzando i dati demo, seleziona *AK-101*.
3. Nel riquadro azioni, apri la scheda **Cespite** e, dal gruppo **Ordine di lavoro** seleziona **Tempi di inattività per manutenzione** per aprire la pagina dei record dei tempi di inattività per manutenzione per il cespite selezionato.
