---
title: Tipi di ordine di lavoro
description: In questo articolo vengono descritti i tipi di ordine di lavoro in Gestione cespiti.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 12745960f903ebc14208f2c8a01f076ed27a38d3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891178"
---
# <a name="work-order-types"></a>Tipi di ordine di lavoro

[!include [banner](../../includes/banner.md)]

 

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

![Tipi di ordine di lavoro.](media/16-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]