---
title: Regole di allocazione contabile
description: Questo articolo fornisce informazioni sulle regole di allocazione della contabilità generale. Descrive i vari componenti delle regole di allocazione e i metodi di allocazione che possono essere utilizzati per tali regole.
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAllocation, LedgerAllocationBasisRule, LedgerAllocationRequest, LedgerAllocationRule
audience: Application User
ms.reviewer: kfend
ms.custom: 15402
ms.assetid: 8147e148-7c11-45ef-95c6-f9889a875b54
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0691c65e6a499f713952070811cefaa7a213af7b
ms.sourcegitcommit: c364f50ea0ad50bac5c30724b6ce301d9574b653
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2022
ms.locfileid: "9787555"
---
# <a name="ledger-allocation-rules"></a>Regole di allocazione contabile

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sulle regole di allocazione della contabilità generale. Descrive i vari componenti delle regole di allocazione e i metodi di allocazione che possono essere utilizzati per tali regole.

Le regole di allocazione contabile vengono utilizzate per calcolare e generare automaticamente i giornali di registrazione e le voci contabili per l'allocazione dei saldi contabili o degli importi fissi. I metodi di allocazione possono essere variabili o fissi. L'allocazione si basa sul valore della valuta della transazione. Ad esempio, le voci contabili perdita/profitto in valuta estera vengono registrate per rettificare gli importi in valuta contabile e di dichiarazione. Queste voci non sono soggette a regole di allocazione perché il loro valore nella valuta della transazione è 0,00. I seguenti metodi di allocazione possono essere utilizzati per le regole di allocazione contabile:

-   **Base**: il metodo variabile viene utilizzato quando l'allocazione dipende dal saldo contabile, in base ai criteri di filtro. È ad esempio possibile allocare le spese relative alla pubblicità in base alle vendite di ciascun reparto in rapporto alle vendite totali di tutti i reparti.
-   **Percentuale fissa** e **Peso fisso**: per questi metodi la percentuale o il peso di allocazione è definito direttamente per la regola. Ad esempio, le spese di pubblicità possono essere allocate in modo che il reparto A ne riceva il 70 percento e il reparto B il 30 percento.
-   **Uniformemente**: il metodo distribuisce equamente l'importo a ogni destinazione definita. Ad esempio, se vengono definite destinazioni per il reparto A e il reparto B, le spese di pubblicità possono essere allocate in modo che sia il reparto A che il reparto B ricevano il 50 percento delle spese di pubblicità.

Se Base è il metodo di allocazione utilizzato per una regola di allocazione, è necessario definire anche regole di base separate di allocazione contabile. Il processo "Elabora richiesta di allocazione" consente agli utenti di elaborare la regola di allocazione contabile e di visualizzare in anteprima gli inserimenti risultanti nel giornale di registrazione allocazioni prima di registrare o eliminare le allocazioni calcolate.

## <a name="components-of-ledger-allocation-rules"></a>Componenti delle regole di allocazione contabile
Le regole di allocazione sono composte da quattro componenti: generale, origine, destinazione e contropartita. Un componente aggiuntivo, regole di base dell'allocazione contabile, è necessario se Base viene utilizzato come metodo di allocazione. Ciascun componente corrisponde a un'informazione critica per l'elaborazione delle allocazioni.

-   **Generale**: in questo componente vengono specificate alcune opzioni, quali il metodo di allocazione, le impostazioni delle regole interaziendali e l'impostazione della regola come attiva o inattiva.
-   **Origine**: in questo componente l'utente specifica i dati di origine per l'allocazione. L'allocazione può essere basata sui saldi contabili (**Origine dati** =  **Contabilità generale**) o gli importi fissi (**Origine dati** =  **Valore fisso**). Quando l'opzione **Origine dati** è impostata su **Contabilità generale**, i criteri di filtro dell'origine devono essere definiti per la regola di allocazione contabile (ad esempio, per le spese di pubblicità).
-   **Destinazione**: in questo componente vengono definiti la distribuzione e l'incidenza del risultato del calcolo di allocazione. Ad esempio, vi può essere una riga di destinazione per ciascun reparto.
-   **Contropartita**: questo componente stabilisce come i conti principali e le dimensioni debbano essere determinati per le voci di contropartita che sono a saldo delle voci di destinazione. Le opzioni definite dall'utente vengono solitamente utilizzate al posto dei conti e delle dimensioni basati sull'origine. Quando l'opzione **Origine dati** è impostata su **Valore fisso**, **Origine** non può essere utilizzata come opzione.
-   **Regole di base di allocazione contabile**: queste regole utilizzano i propri i criteri di filtro di origine per determinare i saldi contabili che devono essere utilizzati per l'allocazione (ad esempio, i ricavi per reparto). È possibile utilizzare ciascuna regola base di allocazione con più regole di allocazione.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
