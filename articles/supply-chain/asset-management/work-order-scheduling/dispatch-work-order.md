---
title: Distribuire un ordine di lavoro
description: Nell'argomento viene descritto come distribuire un ordine di lavoro in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetScheduledExecution
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cd9965ec8f3c3ff58f16b53abc8b9b114444946d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215012"
---
# <a name="dispatch-work-order"></a>Distribuire un ordine di lavoro

[!include [banner](../../includes/banner.md)]

 

È possibile programmare un ordine di lavoro o processi di ordine di lavoro utilizzando la funzionalità **Spedisci**.

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro nell'elenco.

3. Nella scheda **Generale** fare clic su **Spedisci**.

4. Nella finestra dialogo **Programma ordine di lavoro**, selezionare il lavoratore nel campo **Lavoratore**.

5. Nel campo **Programma ore**, è possibile inserire le ore di lavoro previste nel caso differiscano dalle ore previste.

6. Nel campo **Inizio programmato**, è possibile modificare la data e l'ora di inizio, se necessario.

7. Se il processo di programmazione deve rispettare i limiti di capacità in relazione alle risorse già programmate in altri processi, assicurarsi che gli interruttori **Cespite**, **Strumento** e **Lavoratore** siano impostati su **Sì**. Se si desidera visualizzare informazioni dettagliate sul processo di programmazione, impostare l'interruttore **Dettagli** su **Sì**. Ciò significa che le informazioni dettagliate sui punteggi calcolati nell'ordine di lavoro sono visualizzati nel Registro informazioni.

8. Impostare l'interruttore **Ignora programmazione** su **Sì** per ignorare i giorni chiusi nel calendario (si applica a cespite, lavoratore e strumenti). Impostare l'interruttore **Ignora esecuzione programmata** su **Sì** per ignorare le limitazioni eventualmente selezionate nell'ordine di lavoro relativo alla programmazione. 

    Per informazioni sull'impostazione dell'esecuzione programmata fare riferimento alla sezione [Esecuzione programmata](../setup-for-work-orders/scheduled-execution.md).

9. Fare clic su **OK**. Lo stato del ciclo di vita di ordine di lavoro viene aggiornato automaticamente allo stato del ciclo di vita **Programmato** specificato in **Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Modelli del ciclo di vita**.

Nella figura seguente è illustrato un esempio di selezioni di distribuzione nella finestra di dialogo **Programma ordine di lavoro**.

![Figura 1](media/04-work-order-scheduling.png)

[!NOTE]
Se si desidera eliminare la programmazione in un ordine di lavoro, selezionare l'ordine di lavoro **Tutti gli ordini di lavoro** e fare clic su **Elimina programmazione** nella scheda **Generale**. Aggiornare manualmente lo stato del ciclo di vita di ordine di lavoro se si elimina la programmazione.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]