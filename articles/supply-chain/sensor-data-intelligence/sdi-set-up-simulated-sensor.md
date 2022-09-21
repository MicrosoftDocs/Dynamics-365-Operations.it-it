---
title: Impostare un sensore simulato per il test
description: Questo articolo descrive come configurare un simulatore da utilizzare per testare Intelligence dei dati del sensore senza installare alcun sensore fisico.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: edfa20bec7438124844f8b6afa91ca4941b6bb56
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428381"
---
# <a name="set-up-a-simulated-sensor-for-testing"></a>Impostare un sensore simulato per il test

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Se desideri testare Intelligence dei dati del sensore senza installare alcun sensore fisico, puoi utilizzare il servizio *Simulatore online di Raspberry PI Azure IoT* per emulare i segnali dei sensori e inviarli alla tua soluzione Internet delle cose (IoT) su Microsoft Azure. Per ulteriori informazioni sul simulatore, vedi [Connettere il simulatore online di Raspberry Pi all'hub IoT di Azure (Node.js)](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started).

## <a name="create-a-device-in-azure-iot-hub"></a>Creare un dispositivo nell'hub IoT di Azure

Devi prima configurare un dispositivo per autenticare i segnali del sensore nell'hub IoT di Azure.

1. In Azure, vai all'elenco delle risorse per il gruppo di risorse che hai creato per l'uso con Intelligence dei dati del sensore. Per ulteriori informazioni, vedi [Distribuire una soluzione IoT in Azure](sdi-deploy-iot-solution-on-azure.md).
1. Nell'elenco delle risorse, trova il record in cui il campo **Tipo** è impostato su *Hub IoT*. Nella colonna **Nome**, seleziona il nome per aprire la pagina dei dettagli della risorsa.
1. Nel pannello di navigazione a sinistra, seleziona **Dispositivi**.
1. Sulla pagina **Dispositivi** seleziona **Aggiungi dispositivo**.
1. Nella pagina **Crea un dispositivo**, imposta i seguenti campi:

    - **ID dispositivo** – Immetti un nome per il nuovo dispositivo (ad esempio, *Il mio dispositivo IoT*).
    - **Tipo di autenticazione** - Seleziona *Chiavi simmetriche*.
    - **Genera automaticamente chiavi** – Seleziona questa casella di controllo.
    - **Connetti questo dispositivo a un hub IoT** - Seleziona *Abilita*.

1. Seleziona **Salva** per tornare alla pagina **Dispositivi**.
1. Trova il nuovo dispositivo nell'elenco. Nella colonna **ID dispositivo**, seleziona il nome per aprire la pagina dei dettagli del dispositivo. Se non vedi il nuovo dispositivo nell'elenco, aggiorna la pagina.
1. Copia il valore **Stringa di connessione primaria** (ad esempio, selezionando il pulsante **Copia negli appunti**). Avrai bisogno di questo valore in seguito quando configuri il simulatore IoT Raspberry Pi per emulare i segnali dei sensori. Pertanto, per il momento, considera di incollarlo in un file di testo.

## <a name="add-the-azure-connection-string-to-the-raspberry-pi-iot-simulator"></a>Aggiungi la stringa di connessione di Azure al simulatore IoT Raspberry Pi

Attieniti alla seguente procedura per aggiungere la stringa di connessione dal dispositivo nell'hub IoT di Azure allo script nel servizio Raspberry.

1. Apri il [simulatore IoT Raspberry Pi](https://azure-samples.github.io/raspberry-pi-web-simulator/).
1. Nel riquadro dell'editor di codice, trova la riga che contiene il comando seguente.

    `const connectionString = '[Your IoT hub device connection string]';`

1. Sostituisci il testo della guida, comprese le parentesi, con il valore **Stringa di connessione primaria** che hai copiato nella sezione precedente. Il risultato sarà simile all'esempio seguente.

    `const connectionString = 'HostName=XXX;DeviceId=YYY;SharedAccessKey=ZZZ';`

## <a name="add-sensor-ids-and-values-to-the-payload-in-the-raspberry-pi-iot-simulator"></a>Aggiungere gli ID sensore e i valori al payload nel simulatore IoT Raspberry Pi

Ora devi configurare il simulatore IoT Raspberry Pi con sensori simulati e i valori che vengono inviati come payload.

- Nell'editor di codice del simulatore IoT Raspberry Pi, trova la funzione `getMessage` e modificala in modo che corrisponda al codice seguente. I sensori sono configurati nelle righe `cb()`.

    ```cpp
    function getMessage(cb) {
        messageId++;
        sensor.readSensorData()
        .then(function (data) {
            cb(JSON.stringify({ value: 1, sensorId: 'MachineStatus' }), false);
            cb(JSON.stringify({ value: 70, sensorId: 'Quality' }), false);
            cb(JSON.stringify({ value: 1, sensorId: 'AssetMaintenance' }), false);
            cb(JSON.stringify({ value: 1, sensorId: 'ProductionDelay' }), false);
            cb(JSON.stringify({ value: 20, sensorId: 'AssetDowntime' }), false);
        })
        .catch(function (err) {
            console.error('Failed to read out sensor data: ' + err);
        });
    }
    ```

    > [!IMPORTANT]
    > Gli ID dei sensori definiti nell'editor di codice per il simulatore IoT Raspberry Pi devono essere identici agli ID dei sensori che verranno specificati in seguito per gli scenari in Supply Chain Management. Il codice di esempio precedente utilizza ID sensore leggibili dall'uomo. Tuttavia, in uno scenario reale, gli ID sensore saranno valori GUID forniti dal produttore del sensore. Gli ID dei sensori leggibili dall'uomo utilizzati in questo codice di esempio vengono utilizzati anche negli esempi in [Scenario della qualità del prodotto](sdi-scenario-product-quality.md), [Scenario di manutenzione dei cespiti](sdi-scenario-asset-maintenance.md), [Scenario dei ritardi di produzione](sdi-scenario-production-delays.md), e [Scenario dello stato della macchina](sdi-scenario-equipment-downtime.md)). Pertanto, utilizza questo codice se lavorerai in questi scenari.

## <a name="edit-the-interval-for-sending-sensor-signals"></a>Modificare l'intervallo per l'invio dei segnali del sensore

È ora necessario impostare l'intervallo in cui il simulatore IoT Raspberry Pi deve inviare i segnali del sensore emulato.

1. Nell'editor di codice del simulatore IoT Raspberry Pi, trova la seguente chiamata di funzione.

    `setInterval(sendMessage, 2000);`

2. Per impostazione predefinita, il simulatore IoT Raspberry Pi invia un segnale del sensore ogni 2.000 millisecondi (due secondi). Puoi modificare il valore come necessario.

## <a name="run-the-raspberry-pi-iot-simulator"></a>Eseguire il simulatore IoT Raspberry Pi

- Seleziona **Esegui** per avviare il simulatore e iniziare a inviare i dati del sensore simulato.
