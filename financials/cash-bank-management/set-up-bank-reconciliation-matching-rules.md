---
title: Impostare le regole di abbinamento della riconciliazione estratti conto
description: Questo articolo spiega come impostare le regole di abbinamento della riconciliazione e i set di regole di abbinamento della riconciliazione per agevolare il processo di riconciliazione estratti conto. Le regole di abbinamento della riconciliazione sono un set di criteri utilizzati per filtrare le righe del rendiconto bancario e le righe del documento bancario durante il processo di riconciliazione.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: e4c07a6afb90535c57f372d5b850919b5b34aaa4
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bank-reconciliation-matching-rules"></a>Impostare le regole di abbinamento della riconciliazione estratti conto

Questo articolo spiega come impostare le regole di abbinamento della riconciliazione e i set di regole di abbinamento della riconciliazione per agevolare il processo di riconciliazione estratti conto. Le regole di abbinamento della riconciliazione sono un set di criteri utilizzati per filtrare le righe del rendiconto bancario e le righe del documento bancario durante il processo di riconciliazione.

È possibile impostare le regole di abbinamento della riconciliazione e i set di regole di abbinamento della riconciliazione per agevolare il processo di riconciliazione estratti conto. Regola di abbinamento di riconciliazione è un insieme di criteri utilizzati per filtrare le righe di rendiconto bancario e Microsoft Dynamics 365 per le righe di transazione bancaria delle operazioni durante il processo di riconciliazione. Utilizzare la pagina **Regole di abbinamento della riconciliazione** per impostare le regole di abbinamento della riconciliazione. È possibile impostare più regole di abbinamento e quindi creare un set di regole di abbinamento della riconciliazione nella pagina **Set di regole di abbinamento della riconciliazione**. 

> [!NOTE] 
> Le regole di corrispondenza di riconciliazione estratti conto vengono utilizzate se riconciliate un rendiconto bancario elettronico tramite la riconciliazione degli estratti conto di anticipo. 

Nella pagina **Regole di abbinamento della riconciliazione** è possibile selezionare le azioni e i criteri di selezione utilizzati quando la regola di abbinamento viene eseguita. ** Azioni ** nel gruppo di campi, selezionare l'azione che verrà eseguita alla regola di corrispondenza viene eseguita durante il processo di riconciliazione.  

> [!NOTE] 
> L'opzione selezionata determina i campi visualizzati.

|                                    |                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Azione**                         |                                                                                                                                                                                                                                                                                                               | **Criteri di selezione disponibili quando l'azione viene selezionata**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Abbina con documento bancario **       | Creare i criteri per specificare la modalità di abbinamento dei documenti bancari e delle righe del rendiconto bancario quando la regola di abbinamento viene eseguita dalla pagina **Foglio di lavoro riconciliazione estratti conto**. Le righe di transazione vengono selezionate in base ai criteri aggiuntivi impostati nelle Schede dettaglio.                                | ** Passaggio 1: Definire la regola di corrispondenza ** - criteri selezionati per specificare i rendiconti bancari devono essere confrontati con Dynamics 365 per le transazioni bancarie delle operazioni. **Passaggio 2 (facoltativo): selezionare le righe del rendiconto bancario per eseguire le regole di corrispondenza:** Applicare un filtro nella riga del rendiconto bancario per eseguire le regole.                                                                                                                                                                                                                                                                                                               |
| **Cancella righe del rendiconto di storno ** | Creare i criteri per specificare la modalità di eliminazione delle righe del rendiconto di storno dalla pagina **Foglio di lavoro riconciliazione estratti conto** quando la regola di abbinamento viene eseguita. Questa opzione viene utilizzata quando un errore della banca causa la presenza di due righe del rendiconto bancario elencate nel rendiconto bancario importato e le righe devono essere riconciliate. | **Passaggio 1**:** Trovare le righe del rendiconto di storno** Aggiunge criteri di selezione per selezionare righe del rendiconto bancario di storno. Ad esempio, per selezionare solo gli assegni, selezionare **Codice transazione bancaria** nel campo Campo, selezionare il segno più (+) nel campo **Operatore**, quindi immettere **Assegni** nel campo Valore. **Passaggio 2: Trovare le righe del rendiconto originale** È possibile aggiungere criteri di selezione per abbinare le righe del documento bancario alle righe del rendiconto bancario. ** Passaggio 3: Trova Dynamics 365 per le transazioni bancarie delle operazioni ** possibile aggiungere criteri di selezione per abbinare Dynamics 365 per le transazioni bancarie delle operazioni alle righe di rendiconto bancario. |
| **Mark new transactions**          | Creare i criteri per specificare la modalità di contrassegno delle nuove transazioni nella pagina **Foglio di lavoro riconciliazione estratti conto** quando la regola di abbinamento viene eseguita.                                                                                                                                                                 | **Passaggio 1: Trovare le righe del rendiconto** Aggiungere i campi di i per specificare le righe del rendiconto bancario che devono essere selezionate nella pagina **Foglio di lavoro riconciliazione estratti conto**. ** Passaggio 2: Trova Dynamics 365 per le transazioni bancarie delle operazioni ** possibile aggiungere criteri di selezione alle righe di documenti bancari di ricerca. Se non viene trovato alcun documento bancario, una riga del rendiconto verrà contrassegnata come nuova transazione.                                                                                                                                                                                                                                             |

 




