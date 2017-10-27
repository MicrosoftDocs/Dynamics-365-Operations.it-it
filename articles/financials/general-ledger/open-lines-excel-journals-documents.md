---
title: Pubblicare documenti e righe di giornale di registrazione da Excel
description: "In questo argomento viene descritto come immettere e pubblicare righe dei giornali di registrazione generale da Microsoft Excel. Sono riportate informazioni sui diversi modelli che è possibile utilizzare, a seconda del tipo di transazioni che si sta immettendo."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: a4f9e2c5203881f3faeebe4d33e72c7b3bcaa591
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="publish-journal-lines-and-documents-from-excel"></a>Pubblicare documenti e righe di giornale di registrazione da Excel

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto come immettere e pubblicare righe dei giornali di registrazione generale da Microsoft Excel. Sono riportate informazioni sui diversi modelli che è possibile utilizzare, a seconda del tipo di transazioni che si sta immettendo.

Gli utenti possono immettere e pubblicare righe per i giornali di registrazione finanziari da Microsoft Excel. Dopo che un utente ha creato un giornale di registrazione, il pulsante **Apri righe in Excel** visualizza i modelli disponibili. I modelli sono progettati per supportare scenari specifici, tuttavia non tutte le combinazioni di tipo di conto sono supportate nel giornale di registrazione. La tabella seguente mostra i modelli disponibili e i tipi di conto supportati.
|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Modello**             | **Tipi di conto supportati**                                                                                             | **Come accedere al modello**                                                          |
| Righe giornale di registrazione contabile     | Conto: contabilità generale, cliente, fornitore, il conto di contropartita bancario: contabilità generale, cliente, fornitore, interaziendale bancario è supportato.       | Giornale di registrazione generale                                                                         |
| Registro fatture         | Conto: Conto di contropartita fornitore: il sistema di gestione interaziendale di contabilità generale non è supportato.                                                    | Registro fatture contabilità fornitori                                                                     |
| Giornale di registrazione fatture          | Conti: Conto di contropartita fornitore: il sistema di gestione interaziendale di contabilità generale è supportato.                                                      | Giornale di registrazione fatture contabilità fornitori                                                                      |
| Fattura fornitore           |                                                                                                                         | Fattura fornitore                                                                          |
| Giornale di registrazione fatture cliente | Conto: Conto di contropartita cliente: il sistema di gestione interaziendale di contabilità generale è supportato.                                                     | Giornale di registrazione generale                                                                         |
| Fattura a testo libero        |                                                                                                                         | Nella pagina **Fattura a testo libero** fare clic su **Apri in Excel** (icona Microsoft Office). |
| Giornale di registrazione cespiti     | Cespite nella contabilità generale, banca, cliente o fornitore. Interaziendale non è supportato.                                               | Giornale di registrazione cespiti                                                                     |
| Giornale di registrazione pagamenti fornitore   | Conto: Conto di contropartita fornitore: contabilità generale, il sistema di gestione interaziendale bancario è supportato.                                                 | Giornale di registrazione pagamenti fornitore                                                                  |
| Giornale di registrazione pagamenti cliente | Conto: Conto di contropartita cliente: contabilità generale, il sistema di gestione interaziendale bancario è supportato.                                               | Giornale di registrazione pagamenti cliente                                                                |
| Giornale di registrazione spese di progetto  | Conto: progetto, contabilità generale, cliente, conto di contropartita fornitore: progetto, contabilità generale, cliente, il sistema di gestione interaziendale fornitori è supportato. | Spese di giornale di registrazione generale (in Gestione progetti e contabilità)                       |

Quando le righe vengono pubblicate, vengono convalidate per assicurare che siano conformi alle regole impostate nei giornali di registrazione finanziari. Dopo che le righe sono state pubblicate, gli utenti possono modificare o registrare i giustificativi da Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. 

Per aggiungere le dimensioni finanziarie a un modello, sono richieste modifiche aggiuntive. Per ulteriori informazioni, vedere [Aggiungere dimensioni al modello di Microsoft Excel](../../dev-itpro/financial/add-dimensions-excel-templates.md). Dopo che le dimensioni vengono aggiunte all'entità, diventano disponibili nella finestra di progettazione per Excel e possono essere aggiunte al modello.






