---
title: Creare ordini di lavoro delle richieste di intervento di manutenzione
description: In questo argomento viene illustrato come creare un ordine di lavoro da una richiesta di intervento di manutenzione in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b6bd98796140ab7aa3e7813ff1526413504554c5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431209"
---
# <a name="create-work-orders-from-maintenance-requests"></a>Creare ordini di lavoro delle richieste di intervento di manutenzione

[!include [banner](../../includes/banner.md)]

 


Dopo aver creato le richieste di intervento di manutenzione, è possibile convertirli facilmente in ordini di lavoro. In questo argomento viene descritto il modo più veloce di lavorare con le richieste di intervento di manutenzione, aggiornare più richieste di intervento di manutenzione contemporaneamente e creare un ordine di lavoro per più richieste di intervento di manutenzione contemporaneamente. Nella pagina **Richieste di intervento di manutenzione attive** o **Richieste di intervento di manutenzione delle unità funzionali personali**, è possibile anche utilizzare una richiesta di intervento di manutenzione alla volta e convertire una richiesta di intervento di manutenzione in un ordine di lavoro.

> [!NOTE]
> Ogni richiesta di intervento di manutenzione può essere correlata a un solo ordine di lavoro. Tuttavia, più richieste di intervento di manutenzione possono essere incluse in un ordine di lavoro, anche se le richieste di intervento di manutenzione hanno cespiti diversi.

1. Selezionare **Gestione cespiti** \> **Comune** \> **Richieste di intervento di manutenzione** \> **Tutte le richieste di intervento di manutenzione**.
2. Prima di creare un ordine di lavoro delle richieste di intervento di manutenzione, è necessario selezionare, al minimo, il tipo di processo di manutenzione per le richieste di intervento di manutenzione nonché una variante e una mansione qualificata per il tipo di processo di manutenzione, se queste informazioni sono rilevanti. Nella visualizzazione griglia, è possibile aggiornare facilmente le informazioni relative a una richiesta di intervento di manutenzione.
3. Quando si è pronti a creare un ordine di lavoro, selezionare le richieste intervento di manutenzione da includere.

    - Se si selezionano più richieste di intervento di manutenzione da convertire in ordine di lavoro, il campo **Cespite** e il campo **Tipo di processo di manutenzione** devono essere impostati prima di creare l'ordine di lavoro.
    - Se si seleziona una sola richiesta di intervento di manutenzione da convertire in ordine di lavoro, solo il campo **Cespite** deve essere impostato prima di creare l'ordine di lavoro. Tuttavia, quando si crea l'ordine di lavoro, è possibile selezionare un tipo di processo di manutenzione (e una variante e una mansione qualificata per il tipo di processo di manutenzione correlati, se queste informazioni sono pertinenti) nella finestra di dialogo **Crea ordine di lavoro**.

4. Selezionare **Ordine di lavoro**.
5. Nella finestra  dialogo **Crea ordine di lavoro**, impostare i campi e quindi selezionare **OK**.

    La barra dei messaggi può indicare che un nuovo ordine di lavoro è stato creato.

    Inoltre, quando si crea un ordine di lavoro basato su una richiesta di intervento di manutenzione, se il cespite correlato alla richiesta di intervento di manutenzione è incluso in un contratto di garanzia, una barra dei messaggi informa del contratto di garanzia.

6. Selezionare **Gestione cespiti** \> **Comune** \> **Ordini di lavoro** \> **Tutti gli ordini di lavoro** e aprire il nuovo ordine di lavoro.

    ![Aprire il nuovo ordine di lavoro](media/05-manage-maintenance-requests.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]