---
title: Configurazione dello scenario per l'Intelligence IoT
description: Questo argomento descrive come configurare uno scenario in Supply Chain Management per l'Intelligence IoT.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5633741fcd9c04b68e5b174447d7ead3c521ccd7
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597170"
---
# <a name="scenario-setup-for-iot-intelligence"></a>Configurazione dello scenario per l'Intelligence IoT

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come configurare uno scenario in Supply Chain Management per l'Intelligence IoT. Prima di poter impostare gli scenari, devi [configurare LCS](iot-lcs-setup.md).

In questo argomento, configurerai lo scenario **Tempo morto dell'attrezzatura** per generare una notifica in Supply Chain Management quando un computer si arresta.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>Configura lo scenario **Tempo morto dell'attrezzatura** in Supply Chain Management

Lo scenario **Tempo morto dell'attrezzatura** associa un segnale di part-out a una soglia di avviso del computer. Il computer viene monitorato solo quando il computer è selezionato per lo scenario ed è impostato per funzionare in Supply Chain Management. Se il tempo trascorso dall'ultimo segnale Part Out della computer è superiore alla soglia di avviso, viene quindi attivata una notifica **Macchina giù**. Se la macchina è ancora in funzione, al successivo segnale **PartOut** ricevuto viene attivata una notifica **Macchina su**. Se una macchina rimane ferma per 30 minuti viene attivata una nuova notifica **Macchina giù**.

Lo scenario **Tempo morto dell'attrezzatura** ha queste dipendenze:

+ Un ordine di produzione deve essere in esecuzione su un computer mappato per attivare un avviso.
+ Un segnale che rappresenta il segnale di part-out di un computer mappato deve essere inviato all'hub IoT con un nome di proprietà univoco.
+ Una proprietà del timestamp dei millisecondi Unix deve essere presente nel messaggio dell'hub IoT.

Per configurare lo scenario, attieniti a questa procedura:

1. Accedi a Supply Chain Management.
2. Abilita il flag della funzionalità di Intelligence IoT. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
3. Configurare le metriche. Per ulteriori informazioni, vedi [Come configurare le metriche](iot-metrics-setup.md#configure-metrics).
4. Accedi a **Controllo di produzione**.
5. Accedi a **Impostazioni \> Intelligence IoT \> Gestione scenario**.
6. Fai clic su **Configura** nel riquadro **Tempo morto dell'attrezzatura**. La procedura guidata di configurazione inizia con la pagina **Definizione dello schema del sensore dell'apparecchiatura**. L'obiettivo qui è configurare lo schema in Supply Chain Management in modo che corrisponda al formato JSON dei messaggi IoT. È possibile definire più schemi di messaggi multipli. Per ulteriori informazioni, vedi [Formati dello schema dei messaggi per l'hub IoT](iot-schema-format.md). In questo esempio, il payload del messaggio contiene un batch di messaggi con questo formato:

    ```json
    {
        "timestamp": 1576016821614,
        "payload": [
            {
                "id": "IoTInt.Machine1225.PartOut",
                "timestamp": 1576016821614,
                "value": True
            },
            {
                "id": "IoTInt.Machine1226.PartOut",
                "timestamp": 1576016991616,
                "value": True
            }
        ]
    }
    ```

7. Aggiungi una riga alla tabella.

    1. Imposta il **Nome dello schema** per **ID**.
    2. Imposta **Percorso schema** su **/payload[\*]/id**.
    3. Imposta **Descrizione** su **ID messaggio**.

8. Aggiungi una riga alla tabella.

    1. Imposta **Nome schema** su **Timestamp**.
    2. Imposta **Percorso schema** su **/payload[\*]/timestamp**.
    3. Imposta **Descrizione** su **Timestamp messaggio**.

9. Aggiungi una riga alla tabella.

    1. Imposta **Nome schema** su **Valore**.
    2. Imposta **Percorso schema** su **/payload[\*]/value**.
    3. Imposta **Descrizione** su **Valore messaggio**.

    Non devi definire tutte le proprietà nel messaggio, solo quelle necessarie. In questo esempio, non è stata creata una riga per **Timestamp radice**. Il percorso per **Timestamp radice** sarebbe **/timestamp**.
  
10. Fai clic su **Avanti** per andare alla pagina **Mappa dello schema del sensore dell'apparecchiatura**.
11. In fila per **ID risorsa attrezzatura** imposta **Nome schema** su **ID**. I valori validi sono visualizzati in una tabella a discesa.
12. Nella fila per **Ora UTC** imposta **Nome schema** su **Timestamp**. I valori validi sono visualizzati in una tabella a discesa.
13. Nella riga per **Parte prodotta da segnale** imposta **Nome schema** su **Valore**. I valori validi sono visualizzati in una tabella a discesa.
14. Fai clic su **Avanti** per la pagina **Configurazione ID risorsa apparecchiatura**.
15. In questo passaggio, si mappano i valori dei messaggi dell'hub IoT sulle risorse Supply Chain Management.

    1. Nella tabella **Valori dati segnale**, aggiungi una nuova riga e inserisci **IoTInt.Machine1225.PartOut** nella colonna **Valore**. Il valore **IoTInt.Machine1225.PartOut** viene dalla proprietà JSON **id** nel messaggio dell'hub IoT.
    2. Fare clic su **Salva**.
    3. Nella tabella **Mappatura record aziendali**, fai clic su **Nuovo**. Il valore predefinito per **Tipo di record aziendale** viene popolato automaticamente e non è necessario modificarlo.
    4. Nella colonna **Record aziendali**, seleziona la risorsa della macchina Supply Chain Management da cui viene inviato il valore del segnale.
    5. Fare clic su **Salva**.
    6. Ripeti questi passaggi, aggiungendo una nuova mappatura dei record aziendali per **Machine1226**. Puoi mappare più valori dei dati del segnale su un singolo record in Supply Chain Management.

16. Usa la colonna **Selezionato** per scegliere quali computer desideri elaborare. Non devi definire tutti i valori del segnale e non devi selezionare tutte le macchine.
17. Fai clic su **Avanti** per andare alla pagina **Configurazione segnale prodotto dalla parte**.
18. Nella tabella **Valori dati segnale**, aggiungi una riga e imposta **Valore** su **True**. Il valore **True** viene dalla proprietà JSON **valore** nel messaggio dell'hub IoT. Puoi aggiungere tutti i valori di cui hai bisogno per il tuo scenario.
19. Fare clic su **Salva**.
20. Fai clic su **Avanti** per andare alla pagina **Soglia tempo di fermo dell'apparecchiatura**. I computer elencati sono computer precedentemente mappati ai valori dei segnali. In questo passaggio, definisci una soglia per determinare se un computer è inattivo. Ad esempio, se imposti la soglia su 10, Supply Chain Management genera una notifica se non viene inviato alcun messaggio di part-out da un computer per 10 minuti.
21. Scegli **Avanti** per andare alla pagina **Abilita scenario**. Attiva/disattiva il dispositivo di scorrimento per abilitare lo scenario.
22. Scegliere **Fine**.

La configurazione dello scenario è completa. Intelligence IoT inizierà automaticamente l'elaborazione dei messaggi dell'hub IoT.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>Configura lo scenario **Qualità prodotto** in Supply Chain Management

Lo scenario **Qualità prodotto** genera una notifica se un attributo di un articolo è al di fuori di un intervallo specificato. Ad esempio, un sensore potrebbe inviare il peso di ciascun articolo all'hub IoT. In Supply Chain Management, verrebbe generata una notifica se l'articolo fosse troppo pesante o troppo leggero.

Lo scenario ha queste dipendenze:

+ Un ordine di produzione deve essere in esecuzione su un computer mappato e procedere un prodotto con un attributo batch mappato per attivare un avviso.
+ Un segnale che rappresenta l'attributo batch deve essere inviato all'hub IoT con un nome di proprietà univoco.
+ Una proprietà del timestamp dei millisecondi Unix deve essere presente nel messaggio dell'hub IoT.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>Configura lo scenario **Ritardi produzione** in Supply Chain Management

Lo scenario **Ritardi produzione** genera una notifica se la produttività scende al di sotto di un valore di soglia. In questo scenario, un segnale **PartOut** viene inviato all'hub IoT per ciascun articolo prodotto. In Supply Chain Management, il ritardo dell'ordine viene calcolato in base alla durata di esecuzione dell'ordine di produzione, al numero di articoli da produrre, alla durata del processo e al numero di segnali **PartOut** ricevuti. Una notifica di ritardo verrebbe generata se il numero di segnali **PartOut** per il lavoro scendono al di sotto del valore della soglia del valore previsto.

Lo scenario ha queste dipendenze:

+ Un ordine di produzione deve essere in esecuzione su un computer mappato per attivare un avviso.
+ Un segnale che rappresenta il segnale di part-out di un computer mappato deve essere inviato all'hub IoT con un nome di proprietà univoco.
+ Una proprietà del timestamp dei millisecondi Unix deve essere presente nel messaggio dell'hub IoT.

## <a name="how-to-disable-a-scenario"></a>Come disabilitare uno scenario

Per disabilitare uno scenario, attieniti alla procedura seguente:

1. In Supply Chain Management, accedi a **Controllo produzione \> Impostazioni \> Intelligence IoT \> Gestione scenario**.
2. Fai clic su **Configura** sullo scenario.
3. Fai clic su **Avanti** per andare all'ultima scheda della procedura guidata.
4. Attiva/disattiva il dispositivo di scorrimento per disabilitare lo scenario.
