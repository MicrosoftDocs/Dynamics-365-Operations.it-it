---
title: Aggiungere dimensioni finanziarie all'area di lavoro Responsabile finanziario
description: "In questo argomento viene descritto come aggiungere dimensioni finanziarie all'area di lavoro Responsabile finanziario, in modo da utilizzarle per la contabilità generale e i report relativi al budget."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9e674948f642ab7525f96092a9a1f3adaae66974
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="add-financial-dimensions-to-the-cfo-workspace"></a>Aggiungere dimensioni finanziarie all'area di lavoro Responsabile finanziario

[!include[banner](../includes/banner.md)]

In questo argomento viene descritto come aggiungere dimensioni finanziarie all'area di lavoro Responsabile finanziario, in modo da utilizzarle per la contabilità generale e i report relativi al budget. L'area di lavoro Responsabile finanziario include la scheda **Panoramica** e la scheda **Finanziario**. I report in queste due schede sono supportati da due misure: LedgerActivityMeasure e BudgetActivityMeasure. L'aggiornamento di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017) include una relazione tra queste due misure e l'entità DimensionCombinationEntity. È quindi possibile selezionare le dimensioni.

1. In Finance and Operations, nella pagina **Archivio entità**, aggiornare le misure **LedgerActivityMeasure** e **BudgetActivityMeasure**.
2. In Microsoft Visual Studio, aprire Application Explorer e cercare **LedgerCFO**.
3. In **Risorse**, aprire **LedgerCFOWorkspacePBIX**.
4. Quando la risorsa viene aperta in Microsoft Power BI Desktop, selezionare **Recupera dati**, quindi **Database SQL Server** e infine **Connetti**.
5. Immettere il nome del server e **AxDW** come database. Selezionare **DirectQuery** e quindi **OK**.
6. Cercare e selezionare **LedgerActivityMeasure\_DimensionCombination** e quindi selezionare **Carica**.

    > [!TIP]
    > Nell'elenco **Campi**, rinominare la tabella **Dimensioni finanziarie** per un'agevole identificazione.

7. Selezionare **Gestisci relazioni** e quindi selezionare **Nuova**.
8. Nel primo campo, selezionare **Attività di contabilità generale** e quindi selezionare **LedgerDimension**.
9. Nel secondo campo, selezionare **LedgerActivityMeasure\_DimensionCombination** (o **Dimensioni finanziarie** se la tabella è stata rinominata). Selezionare l'intestazione **DimensionCombinationRECID**.
10. Nel campo **Cardinalità**, selezionare **Molti a uno**.
11. Impostare **Direzione filtro incrociato** su **Singola**.
12. Selezionare **Imposta come relazione attiva** e **Considera integrità referenziale**, selezionare **OK** e quindi **Chiudi**.

    [![Creare una relazione](./media/Create-relationship.png)](./media/Create-relationship.png)

13. Nell'elenco **Campi**, dovrebbe essere visualizzate la tabella e le dimensioni finanziarie disponibili. Trascinare le dimensioni finanziarie desiderate nei filtri a livello di report.
14. Salvare le modifiche.
15. Nella struttura a oggetti applicativi (AOT), fare clic con il pulsante destro del mouse sul progetto e scegliere **Sincronizza**.
16. Generare il progetto, quindi aprire l'applicazione per visualizzare i risultati.

    [![Area di lavoro completata](./media/workspace.png)](./media/workspace.png)

