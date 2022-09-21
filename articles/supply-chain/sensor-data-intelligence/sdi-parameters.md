---
title: Parametri di Sensor Data Intelligence
description: Questo articolo fornisce informazioni sulle impostazioni di configurazione disponibili nella pagina dei parametri di Intelligence dei dati del sensore.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreServiceParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 4a6665cc078e54da4ebb7920ec8826352ab7a816
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428363"
---
# <a name="sensor-data-intelligence-parameters"></a>Parametri di Sensor Data Intelligence

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

La pagina **Parametri di Intelligence dei dati del sensore** fornisce alcune impostazioni che è possibile utilizzare per configurare la funzione. Queste impostazioni includono i parametri di connessione di Azure e un parametro per la durata dei messaggi di avviso inviati agli utenti in risposta alle misure dei sensori.

## <a name="read-and-change-connection-details-for-your-azure-iot-solution"></a>Leggere e modificare i dettagli di connessione per la soluzione Azure IoT

In genere, configurerai la tua soluzione IoT di Azure e la collegherai a Microsoft Dynamics 365 Supply Chain Management dalla pagina **Distribuisci e connetti le risorse di Azure**, che ti guiderà per entrambe le procedure. Per ulteriori informazioni, vedi [Distribuire una soluzione IoT in Azure](sdi-deploy-iot-solution-on-azure.md). È inoltre possibile visualizzare e modificare i dettagli della connessione in qualsiasi momento in Supply Chain Management seguendo questi passaggi.

1. Vai ad **Amministrazione di sistema \> Impostazioni \> Intelligence dei dati del sensore \> Parametri di Intelligence dei dati del sensore**.
1. Sulla scheda **Serie temporale**, nel campo **Stringa di connessione archivio metriche di Redis**, immetti il valore **Stringa di connessione primaria (StackExchange.Redis)** per la soluzione Azure IoT a cui ti vuoi connettere. Per ulteriori informazioni su come trovare questo valore, vedi [Distribuire una soluzione IoT in Azure](sdi-deploy-iot-solution-on-azure.md).
1. Sulla scheda **Integrazioni**, nel campo **ID client dell'applicazione Azure AD** immetti il valore **ID client** per la soluzione Azure IoT a cui vuoi connetterti. Per ulteriori informazioni su come trovare questo valore, vedi [Distribuire una soluzione IoT in Azure](sdi-deploy-iot-solution-on-azure.md).

## <a name="set-the-lifetime-of-alert-messages"></a>Impostare la durata dei messaggi di avviso

Ogni volta che Intelligence dei dati del sensore rileva una situazione che richiede l'attenzione dell'utente, invia una notifica all'utente interessato. Per evitare che queste notifiche si accumulino nel sistema, dovresti impostarle in modo che scadano dopo alcuni giorni.

1. Vai ad **Amministrazione di sistema \> Impostazioni \> Intelligence dei dati del sensore \> Parametri di Intelligence dei dati del sensore**.
1. Sulla scheda **Notifiche** nel campo **Giorni di notifica**, inserisci il numero di giorni in cui conservare una notifica. Trascorso il periodo di tempo specificato, la notifica verrà eliminata.
