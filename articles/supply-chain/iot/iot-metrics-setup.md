---
title: Configurazione delle metriche per Intelligence IoT
description: Questo argomento spiega come configurare metriche per l'Intelligence IoT.
author: johanhoffmann
ms.date: 04/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b67292e45746ee45460141b4be32f2f8f14076ad
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674339"
---
# <a name="set-up-metrics-for-iot-intelligence"></a>Configurazione delle metriche per Intelligence IoT

[!include [banner](../../includes/banner.md)]

## <a name="configure-metrics"></a>Configurare le metriche

Se desideri visualizzare i grafici delle serie temporali dei tuoi messaggi in Microsoft Dynamics 365 Supply Chain Management, devi impostare le metriche seguendo questi passaggi.

1. Copia la stringa di connessione della cache Redis:

    1. Nel portale di Azure, vai alla cache Redis.
    2. Vai a **Impostazioni** \> **Chiavi di accesso**.
    3. Copia il valore nel campo **Stringa di connessione primaria**.

2. In Supply Chain Management, vai a **Controllo produzione \> Impostazioni \> Intelligence IoT \> Parametri scenario**.
3. Nella pagina **Parametri scenario**, nella scheda **Serie temporali**, nel campo **Stringa di connessione dell'archivio metriche Redis**, incolla la stringa di connessione che hai copiato in precedenza. Questo passaggio consente di visualizzare le metriche dell'hub IoT di Azure in Supply Chain Management. Quando incolli il valore nel campo, viene mostrato come **\*\*\*\*\*\***.

    > [!NOTE]
    > Ogni volta che aggiorni la stringa di connessione della cache Redis, devi anche aggiornare questo campo.

4. Vai a **Controllo produzione \> Richieste di informazioni e report \> Intelligenza IoT \> Metrica chiave**.
5. Nella pagina **Metrica chiave**, seleziona **Aggiorna**.
6. Nella finestra di dialogo **Aggiorna metriche chiave**, nota che **Esegui in background** è selezionata nel campo. Selezionare **OK**.

Tutte le chiavi della metrica nella cache Redis vengono recuperate e aggiunte all'elenco **Metrica chiave**. I valori delle metriche non appariranno finché non si [abilitano gli scenari](iot-scenario-setup.md).

## <a name="configure-the-resource-status-time-series"></a>Configurare le serie temporali dello stato delle risorse

Per configurare le serie temporali **Stato delle risorse**, seguire questi passaggi.

1. In Supply Chain Management, vai a **Controllo di produzione \> Esecuzione della produzione \> Stato delle risorse**.
2. Nella pagina **Stato risorse** selezionare **Configura**.
2. Nella finestra di dialogo **Configura**, nell'elenco **Risorsa**, seleziona un elemento da monitorare.
3. Seleziona il pulsante **Modifica** per **Serie temporale 1**.
4. Nella finestra di dialogo **Seleziona serie temporali**, seleziona una metrica nella griglia. Puoi anche usare il collegamento **Aggiorna metriche chiave** per aggiornare le metriche chiave da questa finestra di dialogo.
5. Seleziona **OK** per tornare alla finestra di dialogo **Configura**.
6. Immetti un nome visualizzato.
7. Nel campo **Mostra dati da**, seleziona un intervallo di tempo.
8. Selezionare **OK**.

Il grafico viene visualizzato.

## <a name="delete-a-metric-key"></a>Elimina una metrica chiave

1. In Supply Chain Management, vai a **Controllo produzione \> Richieste di informazioni e report \> Intelligenza IoT \> Metriche chiave**.
2. Nella pagina **Metriche chiave**, seleziona la chiave della metrica da eliminare.
3. Selezionare **Elimina**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]