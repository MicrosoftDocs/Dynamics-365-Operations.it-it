---
title: Elaborare le allocazioni
description: "L&quot;articolo prevede le informazioni sulle allocazioni, le opzioni di elaborarle in Microsoft Dynamics 365 per le operazioni come e possono essere utilizzate nella pianificazione del budget. Le allocazioni vengono utilizzate per distribuire importi tra più combinazioni di conti CoGe. Consentono di garantire che le spese o i ricavi vengano contabilizzate in relazione all&quot;oggetto corretto."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: 37f4df5d0b79208a8c565bc9101ddde193a6ef5b
ms.lasthandoff: 03/31/2017


---

# <a name="process-allocations"></a>Elaborare le allocazioni

L'articolo prevede le informazioni sulle allocazioni, le opzioni di elaborarle in Microsoft Dynamics 365 per le operazioni come e possono essere utilizzate nella pianificazione del budget. Le allocazioni vengono utilizzate per distribuire importi tra più combinazioni di conti CoGe. Consentono di garantire che le spese o i ricavi vengano contabilizzate in relazione all'oggetto corretto.

Microsoft Dynamics 365 per le operazioni sono disponibili le seguenti funzionalità per supportare questo processo:

-   Assegnare manualmente gli importi delle transazioni mediante l'azione divise nelle distribuzioni contabili o, applicando i modelli predefiniti di dimensione finanziaria a un documento. Per ulteriori informazioni, vedere distribuzioni contabili []. (\ \ contabilità fornitori accounting-distributions.md)
-   Allocare automaticamente gli importi delle transazioni in base ai termini di allocazione definite in un conto principale. Le voci del conto di allocazione verranno generate per ciascun giornale di registrazione in base alla percentuale e al conto CoGe di destinazione ogni volta che una voce contabile soddisfa i criteri definiti come conto CoGe originale.
-   Allocare automaticamente i saldi contabili o gli importi fissi in base alle regole di allocazione contabile. Le regole di allocazione contabile vengono elaborate su base periodica utilizzando i giornali di registrazione allocazione. 

###  <a name="allocations-in-budget-planning"></a>Allocazioni in fase di pianificazione del budget

Le regole di allocazione contabile possono essere utilizzate per il piano di budget. Quando si utilizzano le regole di allocazione contabile nella pianificazione del budget, le regole di allocazione hanno un funzionamento analogo a quello nella contabilità generale, ma i dati di origine e i dati di destinazione provengono dal piano di budget. È possibile selezionare manualmente le regole di allocazione contabile da utilizzare per il piano di budget. In alternativa, è possibile utilizzare una programmazione di allocazione che viene eseguita come parte di un processo del flusso di lavoro.

> [!NOTE]
> Non è possibile utilizzare le regole di allocazione contabile interaziendali per la pianificazione del budget.




