---
title: Elaborare le allocazioni
description: Questo articolo fornisce informazioni sulle allocazioni, le opzioni per elaborarle in Microsoft Dynamics 365 Finance e sul modo in cui possono essere utilizzate nella pianificazione del budget. Le allocazioni vengono utilizzate per distribuire importi tra più combinazioni di conti CoGe. Consentono di garantire che le spese o i ricavi vengano contabilizzate in relazione all'oggetto corretto.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4c8216ebdd1f26601743e6b35849be0813d06b4a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444791"
---
# <a name="process-allocations"></a>Elaborare le allocazioni

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sulle allocazioni, le opzioni per elaborarle e sul modo in cui possono essere utilizzate nella pianificazione del budget. Le allocazioni vengono utilizzate per distribuire importi tra più combinazioni di conti CoGe. Consentono di garantire che le spese o i ricavi vengano contabilizzate in relazione all'oggetto corretto.

Le seguenti funzionalità supportano questo processo:

-   Allocare manualmente gli importi delle transazioni utilizzando l'operazione Dividi nelle distribuzioni contabili o applicando i modelli predefiniti di dimensioni finanziarie a un documento. Per ulteriori informazioni, vedere [Distribuzioni contabili](../accounts-payable/accounting-distributions.md).
-   Allocare automaticamente gli importi delle transazioni in base ai termini di allocazione definite in un conto principale. Le voci del conto di allocazione verranno generate per ciascun giornale di registrazione in base alla percentuale e al conto CoGe di destinazione ogni volta che una voce contabile soddisfa i criteri definiti come conto CoGe originale. Per ulteriori informazioni, vedere [Condizioni di allocazione del conto principale](../general-ledger/main-account-allocation-terms.md).
-   Allocare automaticamente i saldi contabili o gli importi fissi in base alle regole di allocazione contabile. Le regole di allocazione contabile vengono elaborate su base periodica utilizzando i giornali di registrazione allocazione. Per ulteriori informazioni, vedere [Regole di allocazione](../general-ledger/ledger-allocation-rules.md).

###  <a name="allocations-in-budget-planning"></a>Allocazioni in fase di pianificazione del budget

Le regole di allocazione contabile possono essere utilizzate per il piano di budget. Quando si utilizzano le regole di allocazione contabile nella pianificazione del budget, le regole di allocazione hanno un funzionamento analogo a quello nella contabilità generale, ma i dati di origine e i dati di destinazione provengono dal piano di budget. È possibile selezionare manualmente le regole di allocazione contabile da utilizzare per il piano di budget. In alternativa, è possibile utilizzare una programmazione di allocazione che viene eseguita come parte di un processo del flusso di lavoro.

> [!NOTE]
> Non è possibile utilizzare le regole di allocazione contabile interaziendali per la pianificazione del budget.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]