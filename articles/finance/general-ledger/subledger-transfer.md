---
title: Trasferire il giornale di registrazione secondario alla contabilità generale
description: In questo argomento vengono descritte le funzionalità di Microsoft Dynamics 365 Finance correlate al processo di trasferimento del giornale di registrazione secondario alla contabilità generale.
author: roschlom
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 1efdf095e379b73d553ca3525abbeee8ca35bcbb
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897506"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Trasferire il giornale di registrazione secondario alla contabilità generale

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le funzionalità di Microsoft Dynamics 365 Finance correlate alle regole per il trasferimento di batch delle voci del giornale di registrazione secondario.

Nella versione 8.1, sono state apportate modifiche per consentire il trasferimento di regole che hanno deprecato l'opzione **Sincrona**. Per ulteriori informazioni vedere [Funzionalità rimosse o deprecate per Finance and Operations](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20).

Per il trasferimento di batch del giornale di registrazione secondario sono disponibili le seguenti opzioni. 

 - Asincrono: questa opzione pianificherà immediatamente il trasferimento delle voci di contabilità del giornale di registrazione secondario alla contabilità generale. Il giustificativo della contabilità generale verrà registrato non appena le risorse possono elaborare questa richiesta sul server. 

- Batch programmato: questa opzione aggiungerà le voci contabili del giornale di registrazione secondario che vengono trasferite alla coda di elaborazione nella contabilità generale, dove le voci verranno elaborate nell'ordine ricevuto. Il giustificativo della contabilità generale verrà registrato all'ora pianificata se le risorse possono elaborare questo processo batch sul server. 
 
Nella versione 10.0.8, sono stati apportati dei miglioramenti per migliorare le prestazioni dell'opzione Asincrono. Questa funzionalità è abilitata con il nome **Ottimizzazione delle prestazioni con trasferimento del giornale di registrazione secondario alla contabilità generale**. 
 
Questa funzionalità migliora il trasferimento di dati dal giornale di registrazione secondario alla contabilità generale. Rende il processo più efficiente e raggruppa set di transazioni più piccole da trasferire. Ciò consente un uso più efficiente del server batch. Questa funzionalità richiede che il server batch sia configurato, online e funzionante affinché l'opzione di trasferimento Asincrono funzioni. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]