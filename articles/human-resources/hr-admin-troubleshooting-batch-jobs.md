---
title: Ottimizzare le prestazioni pianificando i processi batch dopo le ore lavorative
description: In questo argomento viene spiegato come risolvere problemi di prestazioni con Microsoft Dynamics 365 Human Resources pianificando i processi di lunga durata dopo le ore lavorative.
author: andreabichsel
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 14354ba9454b8837246b75cd413497553423511e
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065428"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a>Ottimizzare le prestazioni pianificando i processi batch dopo le ore lavorative


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



## <a name="issue"></a>Uscita

In Microsoft Dynamics 365 Human Resources possono verificarsi problemi di prestazioni se i processi batch di lunga durata vengono eseguiti durante le normali ore lavorative.

## <a name="resolution"></a>Risoluzione

Pianifica i seguenti processi batch durante le ore non lavorative. Si consiglia inoltre di rivedere la frequenza dei processi batch eseguiti frequentemente. Se possibile, riduci la ricorrenza del processo batch. In molti casi, la frequenza predefinita è sufficiente.

I seguenti processi batch devono essere eseguiti di notte o dopo le ore lavorative. Assicurari di controllare il fuso orario per questi processi batch ricorrenti. Alcuni processi batch potrebbero utilizzare Pacific Standard Time (PST).

| Processo batch | Occorrenza predefinita |
| --- | --- |
| Pulizia Storico processi batch | 1 volta al mese |
| Esporta pulizia gestione temporanea | 1 volta al giorno |
| Sincronizzazione richiesta mancante integrazione Common Data Service | 1 volta al giorno |
| Processo del sistema di compressione del database che deve essere eseguito regolarmente durante le ore non lavorative | 1 volta al giorno |
| Processo del sistema di ricostruzione dell'indice del database che deve essere eseguito regolarmente durante le ore non lavorative | 1 volta al giorno |

1. In Risorse umane, selezionare **Amministrazione sistema**.

2. Nella barra **Cerca**, cerca uno dei processi batch sopra indicati.

3. Selezionare **Esecuzione in background** e quindi selezionare **Ricorrenza**.

   ![Impostare la ricorrenza.](media/talent-batch-history-cleanup-recurrence.png)

4. In **Definisci ricorrenza**, impostare la **Data di inizio** e **Ora di inizio** in modo che si verificano durante le ore non lavorative o nel fine settimana. Seleziona **Nessuna data di fine**. 

   ![Definire la data e l'ora di inizio della ricorrenza.](media/talent-batch-history-cleanup-define-recurrence.png)

5. Selezionare **OK**.

6. Se necessario, apporta le modifiche a tutti gli altri parametri in **Esegui in background** e selezionare **OK**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Ottimizzare le prestazioni con attività di pulizia automatica](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
