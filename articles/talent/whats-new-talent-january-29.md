---
title: Novità o modifiche in Dynamics 365 Talent (31 gennaio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 01/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8e8c11e460a4678efea81f8d3d1eec96b673d329
ms.sourcegitcommit: 53174ed4e7cc4e1ba07cdfc39207e7296ef87c1f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/07/2020
ms.locfileid: "4690054"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-31-2019"></a>Novità o modifiche in Dynamics 365 Talent (31 gennaio 2019)

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

**Build 8.1.2128**

## <a name="core-hr-changes"></a>Modifiche di Core HR

### <a name="time-off-taken-on-leave-people-card-doesnt-consider-leave-plan-dates"></a>Il permesso richiesto nella scheda delle persone in congedo non considera le date del piano di congedo
Per i piani di congedo non eseguiti in un anno di calendario, la scheda **Richiesto** ora visualizza il permesso richiesto nell'anno di congedo definito nel piano. Ad esempio, se l'anno di congedo dell'organizzazione va dal 1° giugno al 30 maggio e un dipendente ha preso tre giorni di congedo a dicembre, il 15 gennaio la scheda **Richiesto** visualizzerà 3 giorni. 

### <a name="accrual-amounts-not-matching-tier-date-basis"></a>Importi accumulo non corrispondenti alla base della data livello
Alcune nuove opzioni sono state aggiunte a congedi e assenze (parametri **Risorse umane** ) per consentire ai clienti di determinare quando la data dei mesi di servizio dei dipendenti è valida. Per alcune organizzazioni, la data è la fine del mese, ma per altre può essere l'inizio del mese successivo. Ad esempio, un'organizzazione può concedere permessi il 31 dicembre, mentre un'altra il 1° gennaio. Questa opzione consentirà di scegliere quando concedere i permessi. 

### <a name="worker-hire-actions-are-stuck-in-workflow-complete-state"></a>Le azioni di assunzione dei lavoratori sono bloccate allo stato "Flusso di lavoro completato"
Alcune modifiche sono state apportate per correggere un problema in cui un piccolo numero di flussi di lavoro termina con lo stato "Flusso di lavoro completato". I nuovi flussi di lavoro dovrebbero ora passare allo stato "Completato" quando vengono terminati. Qualsiasi flusso di lavoro in uno stato completato passerà a uno stato di errore per consentire l'aggiornamento o la rimozione se necessario. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]