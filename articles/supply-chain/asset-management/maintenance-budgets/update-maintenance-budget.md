---
title: Aggiornare un budget di manutenzione
description: In questo argomento viene illustrato come aggiornare un budget di manutenzione in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f3b771319eeb602a371500fdc69c68f88afe341
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571739"
---
# <a name="update-maintenance-budgets"></a>Aggiornare un budget di manutenzione

[!include [banner](../../includes/banner.md)]

 

La pagina **Righe budget di manutenzione** visualizza tutte le righe di budget create per il budget selezionato nella pagina **Budget di manutenzione**. Per ulteriori informazioni, vedere [Creare budget di manutenzione](create-maintenance-budget.md). È possibile ricalcolare e rettificare le righe del budget di manutenzione fino a che il budget di manutenzione non viene approvato. Una volta trascorso il periodo di budget e dopo aver registrato i costi in Gestione cespiti, è possibile aggiornare anche le righe di budget con i costi effettivi.

## <a name="recalculate-a-maintenance-budget"></a>Ricalcolare un budget di manutenzione

È possibile ricalcolare un budget di manutenzione nella pagina **Righe budget di manutenzione**. Quando si ricalcola un budget di manutenzione, le righe di budget esistenti vengono eliminate e viene eseguito un nuovo calcolo.

1. Nella pagina **Righe budget di manutenzione**, selezionare **Ricalcola**.
2. Nella finestra di dialogo **Ricalcola budget**, apportare le modifiche necessarie per il nuovo calcolo e quindi selezionare **OK**.

Le nuove righe di budget vengono create in base ai valori impostati.

## <a name="adjust-budget-lines"></a>Modificare le righe di budget

Anziché ricalcolare l'intero budget di manutenzione, è possibile modificare le righe selezionate associate ai costi in budget.

1. Nella pagina **Righe budget di manutenzione**, selezionare le righe per le quali aggiornare i costi in budget.
2. Selezionare **Rettifica**.
3. Per aggiungere un importo alle righe selezionate, selezionare la casella di controllo **Aggiungi costo** e immettere il valore nel campo **Aggiungi valore**.
4. Per moltiplicare per un fattore il costo in budget nelle righe di budget selezionate, selezionare la casella di controllo **Moltiplica costo** e immettere il fattore nel campo **Valore di moltiplicazione**.

    Ad esempio, se si immette **1,2** nel campo **Valore di moltiplicazione**, i costi in budget nelle righe selezionate aumentano del 20%. Se si immette **0,7**, si riducono i costi in budget nelle righe selezionate del 30%.

5. Selezionare **OK**.

Le righe di budget selezionate vengono aggiornate in base al valori impostati nel passaggio 3 o 4.

## <a name="update-actual-costs"></a>Aggiornare i cosit effettivi

Una volta trascorse le date nelle righe di budget e dopo aver registrato i costi effettivi in Gestione cespiti, è possibile aggiornare i costi effettivi nel budget di manutenzione.

1. Nella pagina **Righe budget di manutenzione**, selezionare **Aggiorna costo**.
2. Nella finestra di dialogo **Calcola costo effettivo**, selezionare **OK**.

I campi **Costo effettivo** nelle righe di budget vengono aggiornati se i costi effettivi sono stati registrati. Nuove righe di budget potrebbero essere generate nel caso siano stati creati nuovi tipi di cespite a partire dalla creazione del budget e se questi tipi di cespite sono stati utilizzati nei cespiti per i quali sono stati creati gli ordini di lavoro e sono stati registrati i costi associati. Le nuove righe di budget mostrano solo i costi effettivi, poiché pet tali righe non sono stati calcolati costi in budget.

> [!NOTE]
> Per visualizzare una panoramica dei costi effettivi suddivisi in costi preventivi, correttivi e di investimento, è possibile eseguire un calcolo per lo stesso periodo nella pagina **Controllo costi cespiti**. 

## <a name="manually-add-budget-lines"></a>Aggiungere manualmente righe di budget.

Nella pagina **Righe budget di manutenzione**, è possibile aggiungere manualmente una nuova riga di budget selezionando **Nuova** e quindi effettuando selezioni nella riga. Di seguito sono riportati alcuni esempi di situazioni in cui tale approccio può risultare utile:

- Il rifornimento di alcuni cespiti è in fase di pianificazione, ma i processi correlati non sono ancora stati creati in Gestione cespiti. Tuttavia, si desidera includere i costi in budget per quei processi nel budget di manutenzione.
- Nuovi cespiti o tipi di cespite sono stati creati a partire dalla creazione del budget di manutenzione, ma i piani di manutenzione non sono ancora stati impostati in tali cespiti o tipi di cespite. Tuttavia, si desidera includere i costi in budget per quei tipi di cespite nel budget di manutenzione.
