---
title: Monitorare e gestire l'Intelligence IoT
description: Questo argomento spiega come monitorare e gestire l'Intelligence IoT.
author: robinarh
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 86e20b9e60e890833c0eb8573e92c0fbb27f8c9a
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908421"
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

+ [Connettere IoT DevKit AZ3166 all'hub IoT di Azure](/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [Connettere il simulatore online di Raspberry Pi all'hub IoT di Azure (Node.js)](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [Panoramica dell'acceleratore di soluzione Simulazione dispositivi](/azure/iot-accelerators/iot-accelerators-device-simulation-overview)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]