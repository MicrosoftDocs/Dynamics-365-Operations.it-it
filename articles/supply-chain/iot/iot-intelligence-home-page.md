---
title: Home page intelligence IoT
description: Questo argomento fornisce collegamenti a informazioni sull'intelligenza IoT.
author: johanhoffmann
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2386d71fde8196304fde846cbff4cd45d1edc834
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674423"
---
# <a name="iot-intelligence-home-page"></a>Home page intelligence IoT

[!include [banner](../../includes/banner.md)]

> [!IMPORTANT]
> Questa funzionalità è disponibile solo per i seguenti paesi e aree:
>
> - USA (Stati Uniti d'America)
> - UE (Unione Europea)
> - AU (Australia)
> - CA (Canada)
> - UK (Regno Unito)

Intelligenza IoT è un componente aggiuntivo per Microsoft Dynamics 365 Supply Chain Management. Integra i segnali dell'Internet delle cose (IoT) con i dati in Supply Chain Management per produrre informazioni dettagliate fruibili.

L'intelligenza IoT supporta i seguenti scenari:

- **Ritardi produzione**: questo scenario confronta la durata del ciclo effettiva con la durata del ciclo pianificata. Supply Chain Management ti avvisa quando la produzione non è nei tempi previsti, così puoi intervenire per massimizzare l'efficienza operativa ed evitare ritardi negli ordini.
- **Tempo morto dell'attrezzatura**: questo scenario confronta il tempo di attività misurato con i parametri definiti dall'utente. Supply Chain Management ti avvisa quando viene superata una soglia di interruzione, in modo che tu possa intraprendere azioni come la riprogrammazione di un ordine di lavoro di produzione o la creazione di un ordine di lavoro di manutenzione.
- **Qualità del prodotto**: questo scenario confronta le letture del sensore, come umidità e temperatura, con le metriche di qualità definite dall'utente. Supply Chain Management ti avvisa quando si verifica una deviazione, in modo che tu possa intervenire per mantenere gli standard di qualità e ridurre al minimo gli sprechi.

L'illustrazione seguente mostra l'interazione dell'Hub IoT di Azure, Intelligenza IoT e Supply Chain Management.

![Hub IoT, Intelligenza IoT e Supply Chain Management.](media/iot_intelligence.png)

<!-- KFM: hide setup info for now

## Setup

You can set up and configure IoT Intelligence without writing any code. Here are the basic steps.

1. [Set up Azure resources](iot-azure-setup.md) – Create an IoT hub, a Redis cache, and a key vault that can be accessed from Supply Chain Management.
2. [Message schema formats for IoT Hub](iot-schema-format.md) – Configure your devices to send messages to IoT Hub, and define the JavaScript Object Notation (JSON) message format.
3. In Feature Management, enable the IoT Intelligence feature flag. 
4. [Install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md) – Install the add-in in LCS, and configure the Azure secrets.
5. [Set up metrics](iot-metrics-setup.md) – Set up metrics in Supply Chain Management.
6. [Scenario setup](iot-scenario-setup.md) – Set up the scenarios in Supply Chain Management.

-->

## <a name="tracking-and-maintenance"></a>Rilevamento e manutenzione

- [Monitorare gli scenari in Dynamics 365 Supply Chain Management](iot-management.md#monitor-scenarios)
- [Disabilitare uno scenario](iot-scenario-setup.md#disable-a-scenario)
- [Modifica uno scenario Intelligence IoT in esecuzione](iot-management.md#modify-a-running-iot-intelligence-scenario)
- [Opzioni di simulazione](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]