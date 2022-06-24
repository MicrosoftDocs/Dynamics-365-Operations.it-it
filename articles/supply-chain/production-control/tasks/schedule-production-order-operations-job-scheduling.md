---
title: Programmare un ordine di produzione con programmazione di operazioni e processi
description: In questo articolo viene descritta la programmazione di un ordine di produzione con la programmazione delle operazioni e la programmazione dei processi.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d82d5439e57c02ddc9db4222a946bd15f4ed67e4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903929"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Programmare un ordine di produzione con programmazione di operazioni e processi

[!include [banner](../../includes/banner.md)]

In questo articolo viene descritta la programmazione di un ordine di produzione con la programmazione delle operazioni e la programmazione dei processi. Nessun processo viene creato con la programmazione delle operazioni, mentre i processi vengono creati con la programmazione dei processi. La società di dati dimostrativi utilizzata per creare questa attività è USMF. Questa procedura è destinata al responsabile di produzione, al responsabile della pianificazione della produzione o al supervisore di reparto in un ambiente di produzione discreta.


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