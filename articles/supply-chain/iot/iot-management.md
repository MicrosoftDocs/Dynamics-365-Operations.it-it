---
title: Monitorare e gestire l'Intelligence IoT
description: Questo articolo spiega come monitorare e gestire l'Intelligence IoT.
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
ms.openlocfilehash: a640b523adac619377e19d670f932d4d85cfb6a9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852420"
---
# <a name="monitor-and-manage-iot-intelligence"></a>Monitorare e gestire l'Intelligence IoT

[!include [banner](../../includes/banner.md)]

Questo articolo spiega come monitorare e gestire l'Intelligence IoT.

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

Puoi simulare i segnali di fabbrica. Per ulteriori informazioni, vedi questi articoli:

+ [Connettere IoT DevKit AZ3166 all'hub IoT di Azure](/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [Connettere il simulatore online di Raspberry Pi all'hub IoT di Azure (Node.js)](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
