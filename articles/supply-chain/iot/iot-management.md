---
title: Monitorare e gestire l'Intelligence IoT
description: Questo argomento spiega come monitorare e gestire l'Intelligence IoT.
author: johanhoffmann
ms.date: 08/16/2019
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
ms.openlocfilehash: e078f1895b44ca388b75f5cd3d19e0e8f7c36630
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669742"
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
