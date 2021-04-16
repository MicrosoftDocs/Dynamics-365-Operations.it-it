---
title: Casi e violazioni dei criteri di controllo
description: L'articolo illustra come i casi di controllo vengono generati dalle violazioni delle regole dei criteri di controllo. Include inoltre le informazioni sulle varie modalità in cui i criteri di controllo utilizzano l'intervallo di date per la selezione dei documenti.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4c7b9426cc98f62cd7a62b841c0f90c7c57889d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821963"
---
# <a name="audit-policy-violations-and-cases"></a>Casi e violazioni dei criteri di controllo

[!include [banner](../includes/banner.md)]

L'articolo illustra come i casi di controllo vengono generati dalle violazioni delle regole dei criteri di controllo. Include inoltre le informazioni sulle varie modalità in cui i criteri di controllo utilizzano l'intervallo di date per la selezione dei documenti.

<a name="how-audit-cases-are-generated"></a>Modalità di generazione dei casi di controllo
-----------------------------

I criteri di controllo vengono utilizzati per identificare note spese, ordini fornitore e fatture fornitore che non sono conformi alle regole di business definite e configurate come regole dei criteri di controllo. 

I criteri di controllo vengono eseguiti in modalità batch. Quando si eseguono dei criteri di controllo, tutte le regole dei criteri che rientrano in tali criteri vengono eseguite contemporaneamente.

Ogni regola dei criteri valuta un insieme di documenti. La regola dei criteri seleziona i documenti che sono inclusi nell'intervallo di date di selezione e che soddisfano i criteri specificati. Ad esempio, una regola dei criteri potrebbe selezionare le note spese con pasti di valore superiore a 50,00. Un'altra regola dei criteri potrebbe selezionare le fatture fornitore a debito per un fornitore specifico. Per ogni documento selezionato nell'insieme, viene generata una violazione. Tale violazione è costituita da un record di un documento specifico, ad esempio la fattura 12345, che non è conforme alla regola dei criteri. 

Più record di violazione di controllo vengono raggruppati e associati ai casi di controllo. Per impostazione predefinita, i casi relativi a ogni criterio di controllo vengono raggruppati per regola dei criteri di controllo. Se si preferisce, è possibile selezionare altri criteri di raggruppamento tramite la pagina **Criteri di raggruppamento casi**. È possibile, ad esempio, raggruppare le intestazioni di spesa per ID progetto e le fatture fornitore per conto fornitore. In tal caso, tutte le violazioni alle intestazioni di spesa con lo stesso ID progetto e tutte le fatture fornitore con lo stesso conto fornitore verranno raggruppate, rispettivamente, nello stesso caso. 

> [!NOTE]
> Per le regole dei criteri di controllo basate su un tipo di query **Duplicato**, le violazioni non vengono raggruppate in base alla regola dei criteri di controllo o in base ai criteri specificati nella pagina **Criteri di raggruppamento casi**. ma verranno invece raggruppate in base ai criteri incorporati nella regola dei criteri di controllo. Ad esempio, se una regola dei criteri valuta le note spese in base alle spese duplicate con uguale importo, ID esercente e data, tutte le spese con gli stessi valori in questi campi rappresenteranno un caso. Qualsiasi spesa con valori diversi rappresenterà un caso distinto.

Dopo la generazione, i casi di controllo verranno gestiti mediante i tipici processi di gestione dei casi.

## <a name="document-selection-date-ranges"></a>Intervalli di date per la selezione di documenti
Quando si esegue un criterio di controllo, ogni regola dei criteri seleziona documenti del tipo specificato con data inclusa nell'intervallo di date per la selezione dei documenti. L'intervallo delle date di selezione di documenti viene specificato nella pagina **Opzioni aggiuntive**. A molti documenti è associata più di una data. Il campo date utilizzato dalla regola dei criteri di controllo è specificato nella pagina **Tipo di regola dei criteri**.

Di seguito sono riportate altre modalità in cui un criterio di controllo utilizza l'intervallo di date per selezione documenti:

-   I criteri utilizzano la versione di ogni regola dei criteri che risulta valida nell'ultimo giorno dell'intervallo delle date per la selezione dei documenti. È possibile visualizzare le date di validità di ogni regola dei criteri nella pagina elenco **Criteri di controllo**.
-   I criteri utilizzano i nodi dell'organizzazione che risultano associati ai criteri nell'ultimo giorno dell'intervallo delle date per la selezione dei documenti. Solo i nodi dell'organizzazione attualmente associati ai criteri vengono visualizzati nella pagina elenco **Criteri di controllo**.
-   Per le regole dei criteri che si basano su un tipo di query **Elenca ricerca**, i criteri valutano documenti per le entità controllate che risultano valide nell'ultimo giorno dell'intervallo delle date per la selezione dei documenti.


Per ulteriori informazioni, vedere [Regole dei criteri di controllo](audit-policy-rules.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]