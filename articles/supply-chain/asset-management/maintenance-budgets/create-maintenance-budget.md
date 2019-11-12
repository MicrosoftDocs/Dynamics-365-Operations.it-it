---
title: Creare budget di manutenzione
description: In questo argomento viene illustrato come creare un budget di manutenzione in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 99f76c684150f154404cbb241daacb7a8d05f7f9
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571762"
---
# <a name="create-maintenance-budgets"></a>Creare budget di manutenzione

[!include [banner](../../includes/banner.md)]

 



I budget di manutenzione sono utilizzati per fornire una panoramica dei costi previsti per la manutenzione preventiva. Le righe di budget vengono calcolate in base alle righe di programma di manutenzione che hanno una data di inizio prevista durante il periodo di budget.

I budget di manutenzione sono basati sui tipi di costo utilizzati in Gestione cespiti: **Preventivo**, **Correttivo** e **Investimento**. I costi in budget della manutenzione degli investimenti sono inclusi per i cespiti attivi che hanno una data di sostituzione durante il periodo di budget e un valore di sostituzione correlato. I costi in budget per la manutenzione correttiva sono inclusi se una data correttiva passata è inclusa nel calcolo del budget. In tal caso, i costi correttivi di un periodo precedente vengono calcolati per lo stesso periodo futuro per il quale si calcola il budget di manutenzione.

## <a name="create-a-maintenance-budget"></a>Creare un budget di manutenzione

1. Selezionare **Gestione cespiti** \> **Richieste di informazioni** \> **Budget di manutenzione** \> **Budget**.
2. Selezionare **Crea budget**.
3. Nel campo **Budget di manutenzione** immettere un ID budget.
4. Nel campo **Descrizione** immettere una descrizione.
4. Nella Scheda dettaglio **Periodo**, nei campi **Dal** e **Al**, immettere le date di inizio e fine del periodo di budget.
5. Per includere i costi in budget correttivi calcolati in base ai costi effettivi di un periodo precedente, nel campo **Correttivo da data**, immettere la data di inizio del periodo a partire dal quale i costi devono essere inclusi.
6. A seconda del livello di dettagli necessario nel budget, impostare le opzioni pertinenti nelle cinque Schede dettaglio **Raggruppa per**.
7. Selezionare **OK**.
8. Selezionare **Righe budget** per aprire la pagina **Righe budget di manutenzione**, in cui è possibile visualizzare tutte le righe di budget create per il periodo.
9. Per approvare il budget, selezionarlo nella pagina **Budget di manutenzione** e quindi selezionare **Approva**. Quindi, nella finestra di dialogo **Approva budget** selezionare **OK**. Il nome dell'utente viene immesso nel campo **Approvato da** della pagina **Budget di manutenzione**.

    > [!NOTE]
    > Dopo aver approvato un budget di manutenzione, non è possibile ricalcolare o rettificare le righe correlate nella pagina **Righe budget di manutenzione** a meno che non si rimuova dapprima l'approvazione. Per rimuovere l'approvazione di un budget di manutenzione, selezionarlo nella pagina **Budget di manutenzione** e quindi selezionare **Approva**. Quindi, nella finestra di dialogo **Approva budget** selezionare **OK**.

![Budget di manutenzione](media/01-maintenance-budgets.png)

È anche possibile creare un nuovo budget di manutenzione copiando un budget esistente. Nella pagina **Budget di manutenzione** selezionare il budget da copiare e quindi **Approva**. Questo approccio è utile se, ad esempio, è stato creato un budget per un mese e si desidera copiarlo in altri mesi.

> [!NOTE]
> Il budget di manutenzione calcola solo i costi in budget basati sulle righe di programma di manutenzione. Per calcolare i costi effettivi per lo stesso periodo, è possibile effettuare tale calcolo nella pagina **Controllo costo dei cespiti**. 
