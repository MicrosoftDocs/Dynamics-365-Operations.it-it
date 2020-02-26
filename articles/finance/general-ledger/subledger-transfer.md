---
title: Trasferire il giornale di registrazione secondario alla contabilità generale
description: In questo argomento vengono descritte le funzionalità di Microsoft Dynamics 365 Finance correlate al processo di trasferimento del giornale di registrazione secondario alla contabilità generale.
author: roschlom
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 1ae10f406148e213fd0272d1387f15606233be27
ms.sourcegitcommit: 9168621ca9b5061c65f3e05dbc5918b6a11d53d5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2020
ms.locfileid: "3000449"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Trasferire il giornale di registrazione secondario alla contabilità generale

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le funzionalità di Microsoft Dynamics 365 Finance correlate alle regole per il trasferimento di batch delle voci del giornale di registrazione secondario.

Nella versione 8.1, sono state apportate modifiche per consentire il trasferimento di regole che hanno deprecato l'opzione Sincrona. Per ulteriori informazioni vedere [Funzionalità rimosse o deprecate per Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).

Per il trasferimento di batch del giornale di registrazione secondario sono disponibili le seguenti opzioni. 

 - Asincrono: questa opzione pianificherà immediatamente il trasferimento delle voci di contabilità del giornale di registrazione secondario alla contabilità generale. Il giustificativo della contabilità generale verrà registrato non appena le risorse possono elaborare questa richiesta sul server. 

- Batch programmato: questa opzione aggiungerà le voci contabili del giornale di registrazione secondario che vengono trasferite alla coda di elaborazione nella contabilità generale, dove le voci verranno elaborate nell'ordine ricevuto. Il giustificativo della contabilità generale verrà registrato all'ora pianificata se le risorse possono elaborare questo processo batch sul server. 
 
Nella versione 10.0.8, sono stati apportati dei miglioramenti per migliorare le prestazioni dell'opzione Asincrono. Questa funzionalità è abilitata con il nome **Ottimizzazione delle prestazioni con trasferimento del giornale di registrazione secondario alla contabilità generale**. 
 
Questa funzionalità migliora il trasferimento di dati dal giornale di registrazione secondario alla contabilità generale. Rende il processo più efficiente e raggruppa set di transazioni più piccole da trasferire. Ciò consente un uso più efficiente del server batch. Questa funzionalità richiede che il server batch sia configurato, online e funzionante affinché l'opzione di trasferimento Asincrono funzioni. 
