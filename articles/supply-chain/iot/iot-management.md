---
title: Monitorare e gestire l'Intelligence IoT
description: Questo argomento spiega come monitorare e gestire l'Intelligence IoT.
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
ms.openlocfilehash: 05aee9865dc90c97e026d5c05fa2032fc0625f7a
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597410"
---
# <a name="monitor-and-manage-iot-intelligence"></a>Monitorare e gestire l'Intelligence IoT

[!include [banner](../../includes/banner.md)]

Questo argomento spiega come monitorare e gestire l'Intelligence IoT.

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a>Monitorare gli scenari in Microsoft Dynamics 365 Supply Chain Management

Puoi monitorare l'elaborazione Intelligence IoT da diverse posizioni:

+ **Moduli \> Controllo produzione \> Richieste di informazioni e report \> Intelligence IoT \> Notifiche**: visualizza l'elenco di notifiche non risolte.
+ **Moduli \> Controllo produzione \> Richieste di informazioni e report \> Intelligence IoT \> Notifiche chiuse**: visualizza l'elenco di notifiche risolte o ignorate.
+ **Moduli \> Controllo produzione \> Richieste di informazioni e report \> Intelligence IoT \> Metrica chiave**: visualizza la metrica chiave per i grafici delle serie temporali **Stato risorsa**.
+ **Moduli \> Controllo produzione \> Esecuzione produzione \> Stato risorsa**: traccia le metriche specifiche utilizzando la finestra di dialogo **Configura**. Se uno scenario rileva un'eccezione, una notifica mostra i dettagli dell'eccezione.
+ **Aree di lavoro \> Gestione area di produzione \> Notifiche**: visualizza l'elenco delle notifiche non risolte.

## <a name="modify-a-running-iot-intelligence-scenario"></a>Modifica uno scenario Intelligence IoT in esecuzione

Quando uno scenario è in esecuzione, puoi apportare queste modifiche:

+ Aggiungi nuove definizioni dello schema del sensore.
+ Seleziona nuovi valori dei dati del segnale.
+ Annulla la selezione dei valori dei dati del segnale esistenti.
+ Aggiungi e mappa nuovi valori dei dati del segnale.
+ Aggiorna valori soglia.

Quando uno scenario è in esecuzione, queste modifiche sono proibite:

+ Elimina o modifica le definizioni dello schema attualmente utilizzate da uno scenario abilitato.
+ Modifica i percorsi dello schema selezionati dello scenario abilitato.

## <a name="simulation-options"></a>Opzioni di simulazione

Puoi simulare i segnali di fabbrica. Per ulteriori informazioni, vedi questi argomenti:

+ [Connettere IoT DevKit AZ3166 all'hub IoT di Azure](https://docs.microsoft.com/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [Connettere il simulatore online di Raspberry Pi all'hub IoT di Azure (Node.js)](https://docs.microsoft.com/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [Panoramica dell'acceleratore di soluzione Simulazione dispositivi](https://docs.microsoft.com/azure/iot-accelerators/iot-accelerators-device-simulation-overview)
