---
title: Tipi di richiesta di intervento di manutenzione
description: In questo articolo viene illustrato come impostare i tipi di richieste di intervento di manutenzione in Gestione cespiti.
author: johanhoffmann
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a2d707cc9c0aa4863968651a8434883cc1322eb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888703"
---
# <a name="maintenance-request-types"></a>Tipi di richieste di intervento di manutenzione

[!include [banner](../../includes/banner.md)]

 

I tipi di richieste di intervento di manutenzione vengono utilizzati per classificare le richieste di intervento di manutenzione. Ad esempio, potrebbero esserci tipi di richieste di intervento di manutenzione correlati alla manutenzione preventiva e alla manutenzione correttiva. Oppure avere un tipo particolare di richiesta di intervento di manutenzione utilizzato per gestire la riparazione cespiti (riparazione in deposito).

Un tipo di richiesta di intervento di manutenzione definisce il rapporto con un gruppo di stati del ciclo di vita delle richiesta di intervento di manutenzione (modello del ciclo di vita di manutenzione). I modelli del ciclo di vita delle richiesta di intervento di manutenzione definiscono gli stati del ciclo di vita che possono essere impostati per una richiesta di intervento di manutenzione. (Esempi degli stati del ciclo di vita delle richieste di intervento di manutenzione includono **Creato**, **Attivo** e **Finito**).

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Richieste di intervento di manutenzione** \> **Tipi di richieste di intervento di manutenzione**.
2. Selezionare **Nuovo** per creare un tipo di richiesta di intervento di manutenzione.
3. Nel campo **Tipo di richiesta di intervento di manutenzione**, immettere un ID per il tipo di richiesta di intervento di manutenzione.
4. Nel campo **Nome** immettere un nome.
5. Nella scheda Dettaglio **Generale** selezionare un modello del ciclo di vita delle richieste di intervento di manutenzione nel campo **Modello del ciclo di vita delle richieste di intervento di manutenzione**.
6. Nel campo **Tipo di ordine di lavoro** selezionare un tipo di ordine di lavoro. Quando una richiesta di intervento di manutenzione viene convertita in ordine di lavoro, l'ordine di lavoro assume automaticamente il tipo di ordine di lavoro correlato al tipo di richiesta di intervento di manutenzione.

Nella figura seguente è illustrato un esempio della pagina **Tipi di richieste di intervento di manutenzione**.

![Pagina Tipi di richieste di intervento di manutenzione.](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]