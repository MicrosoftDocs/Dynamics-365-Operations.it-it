---
title: Programmare un ordine di produzione con programmazione di operazioni e processi
description: In questo argomento viene descritta la programmazione di un ordine di produzione con la programmazione delle operazioni e la programmazione dei processi.
author: ChristianRytt
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8c27611d7b0c8e4e180ff14d1bd1ca8e36bc82d79d3849494e4de44202bd642b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774032"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Programmare un ordine di produzione con programmazione di operazioni e processi

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritta la programmazione di un ordine di produzione con la programmazione delle operazioni e la programmazione dei processi. Nessun processo viene creato con la programmazione delle operazioni, mentre i processi vengono creati con la programmazione dei processi. La società di dati dimostrativi utilizzata per creare questa attività è USMF. Questa procedura è destinata al responsabile di produzione, al responsabile della pianificazione della produzione o al supervisore di reparto in un ambiente di produzione discreta.


## <a name="create-a-production-order"></a>Creare un ordine di produzione
1. Nel pannello di navigazione, andare a **Moduli > Controllo produzione > Comune > Ordini di produzione > Tutti gli ordini di produzione**.
2. Selezionare **Nuovo ordine di produzione**.
3. Nel campo **Numero articolo** immettere o selezionare un valore. Selezionare il numero articolo **D0001**.  
4. Selezionare **Crea**.

## <a name="schedule-operations-for-the-production-order"></a>Programmare operazioni per l'ordine di produzione
1. Selezionare la riga appena creata.      
2. Nel riquadro azioni selezionare **Programma**.
3. Selezionare **Programma operazioni**.
4. Nel campo **Direzione programmazione**, selezionare **Avanti da data programmazione**.
5. Immettere una data nel campo **Data di programmazione**. Selezionare una data futura, ad esempio, oggi più una settimana. Con la direzione di programmazione selezionata, l'ordine di produzione verrà programmato in avanti da questa data.  
6. Selezionare **OK**.
7. Nell'elenco contrassegnare la riga selezionata. Notare che lo stato viene modificato in **Programmato**. 
8. Selezionare **Tutti i processi**. Si noti che nessun processo viene creato con la programmazione delle operazioni.  
9. Chiudere la pagina.

## <a name="schedule-jobs-for-the-production-order"></a>Programmare processi per l'ordine di produzione
1. Nel riquadro azioni selezionare **Programma**.
2. Selezionare **Programma processi**.
3. Nel campo **Direzione programmazione**, selezionare **Avanti da data programmazione**.
4. Immettere una data nel campo **Data di programmazione**. Selezionare una data futura, ad esempio, oggi più una settimana. Con la direzione di programmazione selezionata, l'ordine di produzione verrà programmato in avanti da questa data.  
5. Selezionare **OK**.
6. Nel riquadro azioni, selezionare **Ordine di produzione**.
7. Selezionare **Tutti i processi**. Si noti che in base al ciclo di lavorazione attivo, 5 processi vengono creati con la programmazione dei processi.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]