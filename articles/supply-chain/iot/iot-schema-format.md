---
title: Formati degli schemi per i messaggi dell'Hub IoT
description: Questo argomento spiega come progettare uno schema di messaggi che è possibile usare in Intelligenza IoT.
author: robinarh
ms.date: 04/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ecf4a70d69d24ea75f5448339057e7017cb93af
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652027"
---
# <a name="schema-formats-for-iot-hub-messages"></a>Formati degli schemi per i messaggi dell'Hub IoT

[!include [banner](../../includes/banner.md)]

Questo argomento spiega come progettare uno schema di messaggi che è possibile usare in Intelligenza IoT.

## <a name="message-requirements"></a>Requisiti messaggi

Le seguenti regole si applicano al monitoraggio dei messaggi in Intelligenza IoT:

+ Gli schemi dei messaggi devono essere in formato JavaScript Object Notation (JSON).
+ Una proprietà UNIX **timestamp**, dove il valore è espresso in millisecondi (ms), deve essere presente nel messaggio dell'hub IoT di Microsoft Azure.
+ Un messaggio viene registrato solo se contiene tutte le proprietà definite nell'impostazione dello scenario. Ad esempio, se definisci le proprietà **ID**, **timestamp** e **valore**, viene monitorato il seguente messaggio.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    }
    ```

    Questo messaggio non è monitorato, perché manca la proprietà **valore**.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
    }
    ```

+ Intelligenza IoT ignora le proprietà nel messaggio che non sono definite nella configurazione dello scenario. Ad esempio, se definisci le proprietà **ID**, **timestamp** e **valore**, Intelligenza IoT monitorerà tutti i seguenti messaggi.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
        "machine" : "Machine1225",
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
         "activity": "PartOut"
    },
    ```

+ Intelligenza IoT ignora silenziosamente i messaggi che non corrispondono ai criteri di configurazione dello scenario.
+ È possibile definire e utilizzare più tipi di schemi di messaggio.
+ Non tutti i tipi di schema dei messaggi devono essere definiti. Devono essere definiti solo gli schemi che verranno utilizzati per gli scenari Intelligenza IoT.

## <a name="id-value-pair-schema"></a>Schema coppia ID/valore

Una coppia id/valore è un modello comune per gli schemi dei messaggi di Intelligenza IoT. Utilizzando una coppia id/valore viene garantito che lo schema del tuo messaggio sia lo stesso in tutti gli scenari. Ad esempio, ecco un messaggio per lo scenario **Tempo morto dell'attrezzatura** o **Ritardi di produzione**.

```json
{
    "id": "IoTInt.Machine1225.PartOut",
    "timestamp": 1576016821614,
    "value": True
}
```

Ecco un messaggio per lo scenario **Qualità del prodotto**.

```json
{
    "id": "IoTInt.Machine1225.Temperature",
    "timestamp": 1576016821614,
    "value": 105
}
```

Entrambi i messaggi precedenti contengono proprietà **ID** e **valore**. I valori **ID** possono essere mappati nella tabella **Valori dei dati del segnale** durante l'impostazione dello scenario. Per lo scenario **Tempo di fermo dell'attrezzatura**, mapperai il valore **IoTInt.Machine1225.PartOut**. Per lo scenario **Qualità prodotto**, mapperai il valore **IoTInt.Machine1225.Temperature**.

Per ulteriori informazioni, vedi la [documentazione dell'hub IoT di Azure](/azure/iot-hub/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]