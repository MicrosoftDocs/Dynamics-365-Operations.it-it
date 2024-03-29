---
title: Descrizione e livello del servizio
description: In questo articolo vengono descritti il livello e la descrizione del servizio in Gestione cespiti.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectServiceLevel, EntAssetWorkOrderStandardDescription, EntAssetWorkOrderServiceLevel, EntAssetServiceLevelLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 753ad36b1d01d1ce0594f477cf863ca0e4a1ac75
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879194"
---
# <a name="service-level-and-description"></a>Descrizione e livello del servizio

[!include [banner](../../includes/banner.md)]

 

Quando si crea un ordine di lavoro, è possibile che si voglia definire i relativi livelli del servizio e aggiungervi una descrizione generale. È possibile creare i livelli di servizio di ordine di lavoro nella pagina **Livelli di servizio ordine di lavoro** e le descrizioni nella pagina **Descrizione ordine di lavoro**.

## <a name="create-a-service-level"></a>Creare un livello del servizio

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Livello servizio**.
2. Selezionare **Nuovo**.
3. Nel campo **Livello servizio**, immettere il livello del servizio (ad esempio, un numero).
4. Nel campo **Nome** immettere un nome.

    Nella Scheda dettaglio **Ordini di lavoro**, è possibile definire la data e l'ora di inizio e fine previste. I campi di questa Scheda dettaglio definiscono il periodo durante il quale gli ordini di lavoro devono essere iniziati e terminati. Questi sono utilizzati per gli ordini di lavoro creati manualmente e gli ordini di lavoro creati in base alle richieste di intervento di manutenzione. 

5. Nel campo **Primo giorno**, immettere un numero di giorni per definire il periodo durante il quale l'ordine di lavoro deve iniziare. Il numero di giorni viene calcolato a partire dalla data di creazione dell'ordine di lavoro. Ad esempio, se l'ordine di lavoro deve iniziare alla data di creazione, immettere **0**. Se l'ordine di lavoro deve iniziare una settimana dopo la data di creazione, immettere **7**.
6. Per impostare un'ora di inizio per l'ordine di lavoro, oltre a una data di inizio, impostare l'opzione **Imposta ora di inizio** su **Sì**. Quindi immettere l'ora di inizio nel campo **Ora di inizio**. Se si imposta l'opzione su **No**, viene visualizzata l'ora del giorno corrente.
7. Nel campo **Ultimo giorno**, immettere un numero di giorni per definire il periodo durante il quale l'ordine di lavoro deve terminare. Il numero di giorni viene calcolato a partire dalla data di inizio dell'ordine di lavoro. Ad esempio, se l'ordine di lavoro deve terminare una settimana dopo la data di inizio, immettere **7**.
8. Per impostare un'ora di fine per l'ordine di lavoro, oltre a una data di fine, impostare l'opzione **Imposta ora di fine** su **Sì**. Quindi immettere l'ora di fine nel campo **Ora di fine**. Se si imposta l'opzione su **No**, viene visualizzata l'ora del giorno corrente.
9. Selezionare **Salva**.

![Pagina Livello del servizio di ordine di lavoro.](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a>Creare una descrizione

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Descrizioni**.
2. Selezionare **Nuovo**.
3. Nel campo **Descrizione** immettere la descrizione.
4. Selezionare **Salva**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]