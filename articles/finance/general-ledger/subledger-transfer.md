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
# <a name="subledger-transfer-to-the-general-ledger"></a><span data-ttu-id="c43cf-103">Trasferire il giornale di registrazione secondario alla contabilità generale</span><span class="sxs-lookup"><span data-stu-id="c43cf-103">Subledger transfer to the General ledger</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c43cf-104">In questo argomento vengono descritte le funzionalità di Microsoft Dynamics 365 Finance correlate alle regole per il trasferimento di batch delle voci del giornale di registrazione secondario.</span><span class="sxs-lookup"><span data-stu-id="c43cf-104">This topic describes capabilities in Microsoft Dynamics 365 Finance that are related to the rules for transferring batches of subledger journal entries.</span></span>

<span data-ttu-id="c43cf-105">Nella versione 8.1, sono state apportate modifiche per consentire il trasferimento di regole che hanno deprecato l'opzione **Sincrona**.</span><span class="sxs-lookup"><span data-stu-id="c43cf-105">In version 8.1, changes were made to allow the transfer of rules, which deprecated the **Synchronous** option.</span></span> <span data-ttu-id="c43cf-106">Per ulteriori informazioni vedere [Funzionalità rimosse o deprecate per Finance and Operations](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20).</span><span class="sxs-lookup"><span data-stu-id="c43cf-106">For more information, see [Removed or deprecated features for Finance and Operations](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20).</span></span>

<span data-ttu-id="c43cf-107">Per il trasferimento di batch del giornale di registrazione secondario sono disponibili le seguenti opzioni.</span><span class="sxs-lookup"><span data-stu-id="c43cf-107">The following options are available for transferring subledger batches.</span></span> 

 - <span data-ttu-id="c43cf-108">Asincrono: questa opzione pianificherà immediatamente il trasferimento delle voci di contabilità del giornale di registrazione secondario alla contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="c43cf-108">Asynchronous – This option will immediately schedule the transfer of the subledger accounting entries to the general ledger.</span></span> <span data-ttu-id="c43cf-109">Il giustificativo della contabilità generale verrà registrato non appena le risorse possono elaborare questa richiesta sul server.</span><span class="sxs-lookup"><span data-stu-id="c43cf-109">The general ledger voucher will be recorded as soon as resources are free to process this request on the server.</span></span> 

- <span data-ttu-id="c43cf-110">Batch programmato: questa opzione aggiungerà le voci contabili del giornale di registrazione secondario che vengono trasferite alla coda di elaborazione nella contabilità generale, dove le voci verranno elaborate nell'ordine ricevuto.</span><span class="sxs-lookup"><span data-stu-id="c43cf-110">Scheduled batch – This option will add the subledger accounting entries that are being transferred to the processing queue in the general ledger, where the entries will be processed in order received.</span></span> <span data-ttu-id="c43cf-111">Il giustificativo della contabilità generale verrà registrato all'ora pianificata se le risorse possono elaborare questo processo batch sul server.</span><span class="sxs-lookup"><span data-stu-id="c43cf-111">The general ledger voucher will be recorded at the scheduled time if resources are free to process this batch job on the server.</span></span> 
 
<span data-ttu-id="c43cf-112">Nella versione 10.0.8, sono stati apportati dei miglioramenti per migliorare le prestazioni dell'opzione Asincrono.</span><span class="sxs-lookup"><span data-stu-id="c43cf-112">In version 10.0.8, improvements were made to enhance the performance of the Asynchronous option.</span></span> <span data-ttu-id="c43cf-113">Questa funzionalità è abilitata con il nome **Ottimizzazione delle prestazioni con trasferimento del giornale di registrazione secondario alla contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="c43cf-113">This feature is enabled under the feature name **Subledger transfer to General Ledger performance optimization**.</span></span> 
 
<span data-ttu-id="c43cf-114">Questa funzionalità migliora il trasferimento di dati dal giornale di registrazione secondario alla contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="c43cf-114">This functionality improves the transfer of data from the subledger to the general ledger.</span></span> <span data-ttu-id="c43cf-115">Rende il processo più efficiente e raggruppa set di transazioni più piccole da trasferire.</span><span class="sxs-lookup"><span data-stu-id="c43cf-115">It allows the process to be more efficient, and it groups together sets of smaller transactions to transfer.</span></span> <span data-ttu-id="c43cf-116">Ciò consente un uso più efficiente del server batch.</span><span class="sxs-lookup"><span data-stu-id="c43cf-116">This allows for a more efficient use of the batch server.</span></span> <span data-ttu-id="c43cf-117">Questa funzionalità richiede che il server batch sia configurato, online e funzionante affinché l'opzione di trasferimento Asincrono funzioni.</span><span class="sxs-lookup"><span data-stu-id="c43cf-117">This functionality requires that the batch server be set up, online, and functioning in order for the Asynchronous transfer option to work.</span></span> 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]