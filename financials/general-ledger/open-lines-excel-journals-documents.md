---
title: Pubblica righe e documenti del giornale di registrazione da Excel
description: In questo argomento viene descritto come immettere ed emettere le righe dei giornali di registrazione generali da Microsoft Excel. Sono riportate informazioni sui diversi modelli da utilizzare, a seconda del tipo di transazioni che si sta immettendo.
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 087339cb3002b42bcb985c2ccfc2d97c752a817c
ms.lasthandoff: 03/31/2017


---

# <a name="publish-journal-lines-and-documents-from-excel"></a>Pubblica righe e documenti del giornale di registrazione da Excel

In questo argomento viene descritto come immettere ed emettere le righe dei giornali di registrazione generali da Microsoft Excel. Sono riportate informazioni sui diversi modelli da utilizzare, a seconda del tipo di transazioni che si sta immettendo.

Gli utenti possono immettere ed emettere le righe per i giornali di registrazione finanziari da Microsoft Excel. Dopo che un utente crea un giornale di registrazione, ** righe aperte in Excel ** il pulsante contenente i modelli disponibili. I modelli sono progettati per supportare gli scenari specifici, ma non ciascuna combinazione di tipo di conto è supportata nel giornale di registrazione. Nella seguente tabella sono riportati i modelli disponibili e i tipi di conto il supporto.
|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Template**             | ** Tipi di supporto di conto **                                                                                             | ** Come accedere al modello **                                                          |
| Righe giornale di registrazione contabile     | Conto: Contabilità generale, cliente, fornitore, il conto di contropartita: Conto CoGe, cliente, fornitore interaziendale, Gestione banche è supportata.       | Giornale di registrazione generale                                                                         |
| Registro fatture         | Conto: Conto di contropartita fornitore: Il sistema di gestione interaziendale di contabilità generale non è supportato.                                                    | Registro fatture contabilità fornitori                                                                     |
| Giornale di registrazione fatture          | Conti: Conto di contropartita fornitore: Il sistema di gestione interaziendale di contabilità generale è supportato.                                                      | Giornale di registrazione fatture contabilità fornitori                                                                      |
| Fattura fornitore           |                                                                                                                         | Fattura fornitore                                                                          |
| Giornale di registrazione fatture cliente | Conto: Conto di contropartita del cliente: Il sistema di gestione interaziendale di contabilità generale è supportato.                                                     | Giornale di registrazione generale                                                                         |
| Fattura a testo libero        |                                                                                                                         | ** Fattura a testo libero ** alla pagina, fare clic su ** aprire in Excel (** l'icona di Microsoft Office). |
| Giornale di registrazione cespiti     | Cespite nella contabilità generale, alla banca, al cliente, o al fornitore. Non è supportato.                                               | Giornale di registrazione cespiti                                                                     |
| Giornale di registrazione pagamenti fornitore   | Conto: Conto di contropartita fornitore: La contabilità generale interaziendale, Gestione banche è supportata.                                                 | Giornale di registrazione pagamenti fornitore                                                                  |
| Giornale di registrazione pagamenti cliente | Conto: Conto di contropartita del cliente: La contabilità generale interaziendale, Gestione banche è supportata.                                               | Giornale di registrazione pagamenti cliente                                                                |
| Giornale di registrazione spese di progetto  | Conto: Progetto, CoGe, cliente, il conto di contropartita fornitore: Il progetto, CoGe, cliente, fornitore interaziendale è supportato. | Spese di giornale di registrazione generale (in Gestione progetti e contabilità)                       |

Se le righe vengono generati, vengono convalidate per assicurarsi che siano conformi alle regole impostate in giornali di registrazione finanziari. Dopo che le righe vengono generati, gli utenti potranno modificare o registrare i giustificativi da Microsoft Dynamics 365 per le operazioni. 

Per aggiungere le dimensioni finanziarie a un modello, le modifiche aggiuntive necessarie. Per ulteriori informazioni, vedere [aggiungere dimensioni al modello di Microsoft Excel] (\ gli sviluppatori di itpro dimensioni finanziarie \ \ aggiungere-dimensione-Excel- modelli). Dopo che le dimensioni vengono aggiunte all'entità, sono disponibili in Designer Excel e possono essere aggiunti al modello.




