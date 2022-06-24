---
title: Trasferire il giornale di registrazione secondario alla contabilità generale
description: In questo articolo vengono descritte le funzionalità correlate al processo di trasferimento del giornale di registrazione secondario alla contabilità generale.
author: RyanCCarlson2
ms.date: 12/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 6d9b40409089e2050dc28c21040069107b766aa0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871248"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Trasferire il giornale di registrazione secondario alla contabilità generale

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritte le funzionalità correlate alle regole per il trasferimento di batch delle voci del giornale di registrazione secondario.

Nella versione 8.1, sono state apportate modifiche per consentire il trasferimento di regole che hanno deprecato l'opzione **Sincrona**. Per ulteriori informazioni, vedere [Funzionalità rimosse o deprecate per Finance and Operations](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20).

Per il trasferimento di batch del giornale di registrazione secondario sono disponibili le seguenti opzioni:

- **Asincrono**: il trasferimento delle voci di contabilità del giornale di registrazione secondario alla contabilità generale viene pianificato immediatamente. Il giustificativo della contabilità generale verrà registrato non appena le risorse possono elaborare la richiesta sul server.
- **Batch programmato**: i movimenti contabili del giornale di registrazione secondario che devono essere trasferiti vengono aggiunti alla coda di elaborazione nella contabilità generale. Le voci in coda verranno elaborate nell'ordine in cui sono state ricevute. Ogni giustificativo della contabilità generale aggiorna i conti all'ora pianificata se le risorse possono elaborare il processo batch sul server.

Nella versione 10.0.8, sono stati apportati dei miglioramenti per migliorare le prestazioni dell'opzione **Asincrono**. Questa funzionalità è abilitata con il nome **Ottimizzazione delle prestazioni con trasferimento del giornale di registrazione secondario alla contabilità generale**.

La funzionalità per il trasferimento asincrono dei batch del giornale di registrazione secondario aiuta a migliorare il trasferimento dei dati dal giornale di registrazione secondario alla contabilità generale. Raggruppando set di transazioni più piccole e trasferendo le transazioni in gruppi, la funzionalità elabora le transazioni in modo più efficiente. Quando le transazioni sono raggruppate, le risorse del server batch vengono utilizzate in modo più efficiente.

Il trasferimento asincrono di batch contabilità ausiliaria richiede che il server batch sia configurato, online e funzionante poiché le attività batch vengono create per l'esecuzione immediata sul server batch. Quando la funzionalità **Trasferimento contabilità ausiliaria all'ottimizzazione delle prestazioni della contabilità generale** è abilitata, anche il processo batch di sistema **Automazione del processo** denominato **Processo di sistema di polling di automazione processi** deve essere abilitato. Per ulteriori informazioni, vedere [Automazione dei processi](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

La modifica dell'efficienza a livello di batch utilizza un singolo processo batch ricorrente per tutte le persone giuridiche nel sistema. In fase di esecuzione, viene creato un nuovo processo batch per elaborare i record richiesti che non sono ancora stati trasferiti. È possibile controllare più impostazioni dalla pagina **Automazione processo** nell'amministrazione del sistema. In quella pagina, puoi modificare il processo in background, cambiare la frequenza e definire un periodo di sospensione.

Per ulteriori informazioni sull'impostazione dell'automazione del processo vedi [Automazione del processo](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
