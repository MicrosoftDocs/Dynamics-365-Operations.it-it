---
title: Home page intelligence IoT
description: Questo argomento fornisce collegamenti a informazioni sull'intelligenza IoT.
author: robinarh
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: intro-internal
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f32cb5578f3c15a10f863980491a687f64312cd
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652026"
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

+ **Ritardi produzione**: questo scenario confronta la durata del ciclo effettiva con la durata del ciclo pianificata. Supply Chain Management ti avvisa quando la produzione non è nei tempi previsti, così puoi intervenire per massimizzare l'efficienza operativa ed evitare ritardi negli ordini.
+ **Tempo morto dell'attrezzatura**: questo scenario confronta il tempo di attività misurato con i parametri definiti dall'utente. Supply Chain Management ti avvisa quando viene superata una soglia di interruzione, in modo che tu possa intraprendere azioni come la riprogrammazione di un ordine di lavoro di produzione o la creazione di un ordine di lavoro di manutenzione.
+ **Qualità del prodotto**: questo scenario confronta le letture del sensore, come umidità e temperatura, con le metriche di qualità definite dall'utente. Supply Chain Management ti avvisa quando si verifica una deviazione, in modo che tu possa intervenire per mantenere gli standard di qualità e ridurre al minimo gli sprechi.

L'illustrazione seguente mostra l'interazione dell'Hub IoT di Azure, Intelligenza IoT e Supply Chain Management.

![Hub IoT, Intelligenza IoT e Supply Chain Management.](media/iot_intelligence.png)

## <a name="setup"></a>Impostazione

Puoi impostare e configurare Intelligenza IoT senza scrivere alcun codice. Ecco i passaggi di base.

1. [Impostare le risorse di Azure](iot-azure-setup.md): creare un hub IoT, una cache Redis e un insieme di credenziali delle chiavi a cui è possibile accedere da Supply Chain Management.
2. [Formati dello schema dei messaggi per l'hub IoT](iot-schema-format.md): configurare i dispositivi per inviare messaggi all'hub IoT e definire il formato del messaggio JavaScript Object Notation (JSON).
3. In Gestione funzionalità, abilitare il flag della funzionalità di Intelligenza IoT. 
4. [Installa il componente aggiuntivo Intelligenza IoT in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md): installare il componente aggiuntivo in LCS e configurare i segreti di Azure.
5. [Impostare le metriche](iot-metrics-setup.md): impostare le metriche in Supply Chain Management.
6. [Configurazione dello scenario](iot-scenario-setup.md): configurare gli scenari in Supply Chain Management.

## <a name="tracking-and-maintenance"></a>Rilevamento e manutenzione

+ [Monitorare gli scenari in Dynamics 365 Supply Chain Management](iot-management.md#monitor-scenarios)
+ [Disabilitare uno scenario](iot-scenario-setup.md#disable-a-scenario)
+ [Disinstallare il componente aggiuntivo](iot-lcs-setup.md#uninstall-addin)
+ [Modifica uno scenario Intelligence IoT in esecuzione](iot-management.md#modify-a-running-iot-intelligence-scenario)
+ [Opzioni di simulazione](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]