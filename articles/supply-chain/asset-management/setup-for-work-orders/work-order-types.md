---
title: Tipi di ordine di lavoro
description: In questo argomento vengono descritti i tipi di ordine di lavoro in Gestione cespiti.
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
ms.openlocfilehash: 57120b51c069e49697f8ec4357265974a0d3afb4
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874580"
---
# <a name="work-order-types"></a>Tipi di ordine di lavoro

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

I tipi di ordine di lavoro sono utilizzati per classificare gli ordini di lavoro. Ad esempio, potrebbero esserci ordini di lavoro correlati alla manutenzione preventiva o alla manutenzione correttiva.

Un tipo di ordine di lavoro definisce un rapporto con un modello del ciclo di vita di ordine di lavoro. Un modello del ciclo di vita di ordine di lavoro definisce gli stati del ciclo di vita di ordine di lavoro che possono essere configurati in un ordine di lavoro (esempi di stati del ciclo di vita di ordine di lavoro includono **Creato**, **In corso** e **Completato**).

Per ulteriori informazioni sugli stati del ciclo di vita di ordine di lavoro e sulle fasi di progetto, vedere [Stati del ciclo di vita ordine di lavoro](work-order-lifecycle-states.md).

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Tipi di ordine di lavoro**.
2. Selezionare **Nuovo** per creare un tipo di ordine di lavoro.
3. Nel campo **Tipo di ordine di lavoro**, immettere un ID per il tipo di ordine di lavoro.
4. Nel campo **Nome** immettere un nome.
5. Nel campo **Modello del ciclo di vita ordine di lavoro**, selezionare un modello del ciclo di vita.
5. Impostare l'opzione **Un addetto alla manutenzione** su **Sì** se tutti i processi di ordine di lavoro correlati a un ordine di lavoro di questo tipo devono essere programmati per lo stesso addetto alla manutenzione.
6. Nel campo **Tipo di costo**, selezionare **Correttivo**, **Preventivo** o **Investimento**, a seconda delle esigenze. Tutti i processi di ordine di lavoro in un ordine di lavoro devono avere lo stesso tipo di costo.
7. Nella sezione **Obbligatorio**, impostare le opzioni pertinenti su **Sì** per specificare quali informazioni correlate agli errori o ai tempi di fermo per la manutenzione sono aggiunte a un ordine di lavoro di questo tipo.

    > [!NOTE]
    > Le opzioni nella sezione **Obbligatorio** sono correlate alle opzioni nella Scheda dettaglio **Convalida** della pagina **Stati del ciclo di vita ordine di lavoro** (**Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Stati del ciclo di vita**).

8. Selezionare **Salva**.

![Figura 1](media/16-setup-for-work-orders.png)
