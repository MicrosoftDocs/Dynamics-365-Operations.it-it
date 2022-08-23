---
title: Configurazione dello scenario per l'Intelligence IoT
description: Questo articolo spiega come configurare gli scenari per Intelligence IoT in Microsoft Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 08/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2f097f33abb55dd69d4a38a9a7b0b2e9bdfbaea1
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2022
ms.locfileid: "9227805"
---
# <a name="scenario-setup-for-iot-intelligence"></a>Configurazione dello scenario per l'Intelligence IoT

[!include [banner](../../includes/banner.md)]
[!INCLUDE [iot-sdi-announcement](../../includes/iot-sdi-announcement.md)]

Questo articolo spiega come configurare gli scenari per Intelligence IoT in Microsoft Dynamics 365 Supply Chain Management. <!-- KFM: Hide setup info for now: Before you can set up the scenarios, you must [set up Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md). -->

In questo articolo, configurerai lo scenario **Tempo morto dell'attrezzatura** per generare una notifica in Supply Chain Management quando un computer si arresta. L'articolo mostra anche come configurare lo scenario **Qualità del prodotto** in modo che venga generata una notifica se un attributo di un articolo è al di fuori di un intervallo specificato e come configurare lo scenario **Ritardi in produzione** in modo che venga generata una notifica se la velocità di produzione scende al di sotto di un valore di soglia.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>Configura lo scenario Tempo morto dell'attrezzatura in Supply Chain Management

Lo scenario **Tempo di inattività dell'attrezzatura** associa un segnale di **PartOut** a una soglia di avviso del computer. Il computer viene monitorato solo quando è selezionato per lo scenario ed è impostato su **In esecuzione** in Supply Chain Management. Se il tempo trascorso dall'ultimo segnale **PartOut** del computer è superiore alla soglia di avviso, viene quindi attivata una notifica **Computer inattivo**. Se la macchina è ancora in funzione, al successivo segnale **PartOut** ricevuto viene attivata una notifica **Computer attivo**. Se una macchina rimane ferma per 30 minuti viene attivata una nuova notifica **Computer inattivo**.

Lo scenario **Tempo di inattività dell'attrezzatura** ha le seguenti dipendenze:

+ Un avviso può essere attivato solo se un ordine di produzione è in esecuzione su un computer mappato.
+ Un segnale che rappresenta il segnale **PartOut** di un computer mappato deve essere inviato all'hub IoT con un nome di proprietà univoco.
+ Una proprietà UNIX **timestamp**, dove il valore è espresso in millisecondi (ms), deve essere presente nel messaggio dell'hub IoT di Azure.

Per configurare lo scenario, attieniti a questa procedura.

1. Accedere a Supply Chain Management.
2. Abilita il flag della funzionalità di Intelligence IoT. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
3. Configurare le metriche. Per ulteriori informazioni, vedi [Come configurare le metriche](iot-metrics-setup.md#configure-metrics).
4. Andare a **Controllo di produzione \> Impostazione \> Intelligence IoT \> Gestione scenari**.
6. Nel riquadro **Tempi di inattività dell'attrezzatura** selezionare **Configura** per aprire la configurazione guidata.

   La prima pagina della procedura guidata è la pagina **Definizione dello schema del sensore dell'apparecchiatura**. In questa pagina, l'obiettivo è impostare lo schema in Supply Chain Management in modo che corrisponda al formato JSON (JavaScript Object Notation) dei messaggi dell'hub IoT. È possibile definire più schemi di messaggi multipli. Per ulteriori informazioni, vedi [Formati dello schema dei messaggi per l'hub IoT](iot-schema-format.md). In questo esempio, il payload del messaggio contiene un batch di messaggi con il seguente formato.

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

7. Aggiungere una riga alla tabella e impostare i seguenti valori:

    1. Impostare il campo **Nome schema** su **ID**.
    2. Impostare il campo **Percorso schema** su **/payload\[\*\]/id**.
    3. Impostare il campo **Descrizione** su **ID messaggio**.

8. Aggiungere un'altra riga alla tabella e impostare i seguenti valori:

    1. Impostare il campo **Nome schema** su **Timestamp**.
    2. Impostare il campo **Percorso schema** su **/payload\[\*\]/timestamp**.
    3. Impostare il campo **Descrizione** su **Timestamp messaggio**.

9. Aggiungere un'altra riga alla tabella e impostare i seguenti valori:

    1. Impostare il campo **Nome schema** su **Valore**.
    2. Impostare il campo **Percorso schema** su **/payload\[\*\]/value**.
    3. Impostare il campo **Descrizione** su **Valore messaggio**.

    > [!NOTE]
    > Non è necessario definire tutte le proprietà nel messaggio. Definire solo le proprietà necessarie. Nei passaggi precedenti, non è stata creata una riga per **Timestamp radice**. Il percorso di **Timestamp radice** è **/timestamp**.

10. Selezionare **Avanti** per andare alla pagina **Mappa dello schema del sensore dell'apparecchiatura**.
11. Nella riga per **ID risorsa attrezzatura** nel campo **Nome schema** selezionare **ID**.
12. Nella riga per **Ora UTC** nel campo **Nome schema** selezionare **Timestamp**.
13. Nella riga per **Parte prodotta da segnale** nel campo **Nome schema** selezionare **Valore**.
14. Selezionare **Avanti** per andare alla pagina **Configurazione ID risorsa apparecchiatura**.
15. Seguire questi passaggi per mappare i valori nel messaggio dell'hub IoT alle risorse Supply Chain Management:

    1. Nella tabella **Valori dati segnale** aggiungere una nuova riga. Nel campo **Valore** immettere **IoTInt.Machine1225.PartOut**. Questo valore viene dalla proprietà **id** JSON nel messaggio dell'hub IoT.
    2. Selezionare **Salva**.
    3. Nella tabella **Mappatura record aziendali** selezionare **Nuovo**. Il valore predefinito per il campo **Tipo di record aziendale** viene popolato automaticamente e non è necessario modificarlo.
    4. Nel campo **Record aziendali**, selezionare la risorsa computer Supply Chain Management da cui viene inviato il valore del segnale.
    5. Selezionare **Salva**.
    6. Ripetere questi passaggi per aggiungere una nuova mappatura dei record aziendali per **Machine1226**. Puoi mappare più valori dei dati del segnale su un singolo record in Supply Chain Management.

16. Usare la colonna **Selezionato** per scegliere quali computer elaborare. Non è necessario definire tutti i valori del segnale e non è necessario selezionare tutti i computer.
17. Selezionare **Avanti** per andare alla pagina **Configurazione segnale prodotto dalla parte**.
18. Nella tabella **Valori dati segnale**, aggiungere una riga e impostare il campo **Valore** su **True**. Questo valore viene dalla proprietà **value** JSON nel messaggio dell'hub IoT. È possibile aggiungere tutti i valori necessari per lo scenario.
19. Selezionare **Salva**.
20. Selezionare **Avanti** per andare alla pagina **Soglia tempo di fermo dell'apparecchiatura**. I computer elencati sono computer precedentemente mappati ai valori dei segnali. In questa pagina, definire una soglia per determinare se un computer è inattivo. Ad esempio, se si imposta la soglia su **10**, Supply Chain Management genera una notifica se non viene inviato alcun messaggio di **PartOut** da un computer per 10 minuti.
21. Selezionare **Avanti** per andare alla pagina **Abilita scenario**. Impostare l'opzione per abilitare lo scenario.
22. Selezionare **Fine**.

La configurazione dello scenario è ora completata. Intelligence IoT inizierà automaticamente l'elaborazione dei messaggi dell'hub IoT.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>Configura lo scenario Qualità prodotto in Supply Chain Management

Lo scenario **Qualità prodotto** genera una notifica se un attributo di un articolo è al di fuori di un intervallo specificato. Ad esempio, un sensore invia il peso di ciascun articolo all'hub IoT. Se un articolo è troppo pesante o troppo leggero, viene generata una notifica in Supply Chain Management.

Lo scenario **Qualità prodotto** ha le seguenti dipendenze:

+ È possibile attivare un avviso solo se un ordine di produzione è in esecuzione su una macchina mappata e produce un prodotto con un attributo batch mappato.
+ Un segnale che rappresenta l'attributo batch deve essere inviato all'hub IoT e un nome di proprietà univoco deve essere incluso.
+ Una proprietà UNIX **timestamp**, dove il valore è espresso in millisecondi, deve essere presente nel messaggio dell'hub IoT.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>Configura lo scenario Ritardi produzione in Supply Chain Management

Lo scenario **Ritardi produzione** genera una notifica se la produttività scende al di sotto di un valore di soglia. In questo scenario, un segnale **PartOut** viene inviato all'hub IoT per ciascun articolo prodotto. In Supply Chain Management, il ritardo dell'ordine viene calcolato in base al tempo di esecuzione pianificato dell'ordine di produzione, al numero di articoli che devono essere prodotti, al tempo di esecuzione del processo e al numero di segnali **PartOut** ricevuti. Una notifica di ritardo viene generata se il numero di segnali **PartOut** per il processo scendono al di sotto del valore della soglia.

Lo scenario **Ritardi produzione** ha le seguenti dipendenze:

+ Un avviso può essere attivato solo se un ordine di produzione è in esecuzione su un computer mappato.
+ Un segnale che rappresenta il segnale **PartOut** di un computer mappato deve essere inviato all'hub IoT di Azure con un nome di proprietà univoco.
+ Una proprietà UNIX **timestamp**, dove il valore è espresso in millisecondi, deve essere presente nel messaggio dell'hub IoT.

## <a name="disable-a-scenario"></a>Disabilitare uno scenario

Per disabilitare uno scenario, attenersi alla procedura seguente.

1. In Supply Chain Management, andare a **Controllo produzione \> Impostazioni \> Intelligence IoT \> Gestione scenario**.
2. Nel riquadro dello scenario, selezionare **Configura**.
3. Selezionare **Avanti** per andare all'ultima pagina della procedura guidata.
4. Impostare l'opzione per disabilitare lo scenario.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]