---
title: Impostare le regole di abbinamento della riconciliazione estratti conto
description: Questo argomento spiega come impostare le regole di abbinamento della riconciliazione e i set di regole di abbinamento della riconciliazione per agevolare il processo di riconciliazione estratti conto. Le regole di abbinamento della riconciliazione sono un set di criteri utilizzati per filtrare le righe del rendiconto bancario e le righe del documento bancario durante il processo di riconciliazione.
author: panolte
manager: AnnBe
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3302738a05852dfb37f8266074386d9f2998994d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444783"
---
# <a name="set-up-bank-reconciliation-matching-rules"></a>Impostare le regole di abbinamento della riconciliazione estratti conto

[!include [banner](../includes/banner.md)]

Questo argomento spiega come impostare le regole di abbinamento della riconciliazione e i set di regole di abbinamento della riconciliazione per agevolare il processo di riconciliazione estratti conto. Le regole di abbinamento della riconciliazione sono un set di criteri utilizzati per filtrare le righe del rendiconto bancario e le righe del documento bancario durante il processo di riconciliazione.

È possibile impostare le regole di abbinamento della riconciliazione e i set di regole di abbinamento della riconciliazione per agevolare il processo di riconciliazione estratti conto. Una regola di abbinamento della riconciliazione è un set di criteri utilizzati per filtrare le righe del rendiconto bancario e le righe di transazione bancaria di Dynamics 365 Finance durante il processo di riconciliazione. Utilizzare la pagina **Regole di abbinamento della riconciliazione** per impostare le regole di abbinamento della riconciliazione. È possibile impostare più regole di abbinamento e quindi creare un set di regole di abbinamento della riconciliazione nella pagina **Set di regole di abbinamento della riconciliazione**. 

> [!NOTE] 
> Le regole di abbinamento della riconciliazione bancaria vengono utilizzate se si riconcilia un rendiconto bancario elettronico tramite la riconciliazione bancaria avanzata. 

Nella pagina **Regole di abbinamento della riconciliazione** è possibile selezionare le azioni e i criteri di selezione utilizzati quando la regola di abbinamento viene eseguita. Nel gruppo di campi **Azioni** selezionare l'azione che verrà eseguita quando la regola di abbinamento viene eseguita durante il processo di riconciliazione.  

Per impostazione predefinita, le regole di corrispondenza si applicano al primo documento bancario che soddisfa i criteri della regola di corrispondenza. Se più documenti bancari soddisfano i criteri della regola, il parametro per richiedere la corrispondenza manuale può essere attivato andando in **Gestione cassa e banche > Impostazione > Parametri di gestione cassa e banche > Riconciliazione bancaria > Richiedi corrispondenza manuale quando le regole di corrispondenza riconciliazione bancaria avanzate trovano più documenti che corrispondono all'importo**.

> [!NOTE] 
> L'opzione selezionata determina i campi visualizzati.

|                                    |                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Azione**                         |                                                                                                                                                                                                                                                                                                               | **Criteri di selezione disponibili quando l'azione viene selezionata**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Abbina con documento bancario**       | Creare i criteri per specificare la modalità di abbinamento dei documenti bancari e delle righe del rendiconto bancario quando la regola di abbinamento viene eseguita dalla pagina **Foglio di lavoro riconciliazione estratti conto**. Le righe di transazione vengono selezionate in base ai criteri aggiuntivi impostati nelle Schede dettaglio.                                | **Passaggio 1: definire la regola di abbinamento** Selezionare i criteri per specificare i rendiconti bancari che devono essere abbinati alle transazioni bancarie di Finance. **Passaggio 2 (facoltativo): selezionare le righe del rendiconto bancario per eseguire le regole di corrispondenza:** Applicare un filtro nella riga del rendiconto bancario per eseguire le regole.                                                                                                                                                                                                                                                                                                               |
| **Cancella righe del rendiconto di storno** | Creare i criteri per specificare la modalità di eliminazione delle righe del rendiconto di storno dalla pagina **Foglio di lavoro riconciliazione estratti conto** quando la regola di abbinamento viene eseguita. Questa opzione viene utilizzata quando un errore della banca causa la presenza di due righe del rendiconto bancario elencate nel rendiconto bancario importato e le righe devono essere riconciliate. | **Passaggio 1**:**Trovare le righe del rendiconto di storno** Aggiunge criteri di selezione per selezionare righe del rendiconto bancario di storno. Ad esempio, per selezionare solo gli assegni, selezionare **Codice transazione bancaria** nel campo Campo, selezionare il segno più (+) nel campo **Operatore**, quindi immettere **Assegni** nel campo Valore. **Passaggio 2: Trovare le righe del rendiconto originale** È possibile aggiungere criteri di selezione per abbinare le righe del documento bancario alle righe del rendiconto bancario. **Passaggio 3: Trovare transazioni bancarie di Finance** È possibile aggiungere criteri di selezione per abbinare le transazioni bancarie di Finance alle righe del rendiconto bancario. |
| **Contrassegna nuove transazioni**          | Creare i criteri per specificare la modalità di contrassegno delle nuove transazioni nella pagina **Foglio di lavoro riconciliazione estratti conto** quando la regola di abbinamento viene eseguita.                                                                                                                                                                 | **Passaggio 1: Trovare le righe del rendiconto** Aggiungere i campi di i per specificare le righe del rendiconto bancario che devono essere selezionate nella pagina **Foglio di lavoro riconciliazione estratti conto**. **Passaggio 2: trovare Finance and Operations** - È possibile aggiungere criteri di selezione per cercare le righe del documento bancario. Se non viene trovato alcun documento bancario, una riga del rendiconto verrà contrassegnata come nuova transazione.                                                                                                                                                                                                                                             |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]