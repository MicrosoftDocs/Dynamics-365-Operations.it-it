---
title: Tipi di richieste di intervento di manutenzione
description: In questo argomento viene illustrato come impostare i tipi di richieste di intervento di manutenzione in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
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
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d353f084e0d3e056f1b5ff5af6437ba211def8ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431260"
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

![Pagina Tipi di richieste di intervento di manutenzione](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]