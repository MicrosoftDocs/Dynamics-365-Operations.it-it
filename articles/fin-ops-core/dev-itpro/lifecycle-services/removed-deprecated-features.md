---
title: Funzionalità rimosse o deprecate in Lifecycle Services (LCS)
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Microsoft Dynamics Lifecycle Services (LCS).
author: AngelMarshall
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: abf7a1a0a75ac3098efeeab3df65481999b69acc
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687880"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a>Funzionalità rimosse o deprecate in Lifecycle Services (LCS)

[!include[banner](../includes/banner.md)]

In questo argomento vengono descritte le funzionalità che sono state rimosse o deprecate in Microsoft Dynamics Lifecycle Services (LCS).

- Una funzionalità *rimossa* non è più disponibile nel servizio.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Questo elenco viene fornito per aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione.

## <a name="october-2019-announcements"></a>Annunci di ottobre 2019

### <a name="flowchart-diagrams-in-business-process-modeler"></a>Diagrammi di flusso in Modellatore di processi aziendali

<table>
<tbody>
<tr>
<td><strong>Motivo del deprecamento/rimozione</strong></td>
<td>Il componente diagramma di flusso in Business process modeler (BPM) viene deprecato in ragione dello scarso utilizzo della progettazione legacy.</td>
</tr>
<tr>
<td><strong>Sostituita da un'altra funzionalità?</strong></td>
<td>Nessuno</td>
</tr>
<tr>
<td><strong>Aree interessate</strong></td>
<td>Modellatore di processi aziendali</td>
</tr>
<tr>
<td><strong>Stato</strong></td>
<td>Deprecato: il componente diagrammi di flusso in BPM dovrebbe essere rimosso nel 2020. La seguente funzionalità diventerà non disponibile:
<ul>
<li>Tutti i diagrammi di flusso saranno di sola lettura e non disponibili per la modifica. Anche le proprietà della forma associate alle attività del diagramma di flusso non saranno disponibili. Questi diagrammi di flusso includono sia diagrammi di flusso predefiniti che vengono generati automaticamente sia diagrammi di flusso personalizzati che vengono modificati in base a tali diagrammi di flusso predefiniti.</li>
<li>I passaggi della procedura saranno di sola lettura e non disponibili per la modifica.</li>     
<li>La funzionalità di analisi degli scostamenti/adeguatezza non sarà disponibile. Pertanto, nessun elenco di scostamenti verrà automaticamente creato o sarà disponibile per l'esportazione.
<p><strong>Nota:</strong> questa funzionalità era stata precedentemente deprecata e sostituita dalle integrazioni di  Microsoft Azure DevOps.</p>
</li>
<li>La cronologia delle versioni del diagramma di flusso non sarà disponibile.</li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]