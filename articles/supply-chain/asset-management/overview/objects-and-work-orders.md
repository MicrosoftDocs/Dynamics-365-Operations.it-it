---
title: Cespiti e ordini di lavoro
description: Questo articolo illustra cespiti e ordini di lavoro in Gestione cespiti.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df2d0fcc5162900ad2ad67f2629d14015f694bd4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869693"
---
# <a name="assets-and-work-orders"></a>Cespiti e ordini di lavoro

[!include [banner](../../includes/banner.md)]

 

Questo articolo illustra cespiti e ordini di lavoro in Gestione cespiti. I cespiti e gli ordini di lavoro sono le parti centrali di Gestione cespiti. Un *cespite* è una macchina o parte di macchina che richiede manutenzione e assistenza regolari. I cespiti possono essere creati in una struttura gerarchica e possono essere correlati alle unità funzionali. I processi di manutenzione possono essere pianificati a tutti i livelli della struttura di cespiti.

I vari dati, ad esempio informazioni sul prodotto e specifica del cespite, e i piani di manutenzione necessari sono impostati su ciascun cespite. Nella seguente figura è illustrata una panoramica dei dati dei cespiti e del rapporto tra cespiti e tipi di processo. Il rosso testo viene utilizzato per alcuni esempi relativi a ereditarietà e dipendenze.

![Diagramma che mostra i dati dei cespiti relativi ai tipi di processo.](media/05-overview-image.png)

Ogni ordine di lavoro ha un tipo di ordine di lavoro, ad esempio manutenzione preventiva, manutenzione correttiva o ispezione. L'ordine di lavoro contiene uno o più processi dell'ordine di lavoro. Ogni processo dell'ordine di lavoro definisce un processo che deve essere eseguito su un cespite e un tipo di processo correlato. Esempi di tipi di processo correlati sono l'ispezione a 10.000 km, a 50.000 km, la revisione dopo un anno e l'ispezione di sicurezza. Un solo ordine di lavoro può essere correlato a più cespiti.

Nella seguente figura è illustrata una panoramica dei dati importanti in un ordine di lavoro.

![Diagramma che mostra i dati chiave in un ordine di lavoro.](media/06-overview-image.png)

Un ordine di lavoro può essere correlato a un altro ordine di lavoro e i tipi di processo possono contenere i successivi processi che creano un ordine di lavoro. In generale non ci sono dipendenze tra gli ordini di lavoro. Di conseguenza, possono modificare il loro stato del ciclo di vita e possono essere programmati indipendentemente l'uno dall'altro.

Gli ordini di lavoro possono essere creati in vari modi correlati alla manutenzione correttiva, preventiva o reattiva. È inoltre possibile creare ordini di lavoro manualmente. Nella seguente figura è illustrata una panoramica del processo per la creazione automatica o manuale degli ordini di lavoro.

![Diagramma che mostra la creazione automatica o manuale degli ordini di lavoro.](media/07-overview-image.png)

Diversi passaggi devono essere completati quando si desidera programmare ed eseguire un processo di manutenzione in un ordine di lavoro. Nella seguente figura è illustrata una panoramica dell'elaborazione di un ordine di lavoro.

![Diagramma che mostra una panoramica dell'elaborazione di un ordine di lavoro.](media/08-overview-image.png)

> [!NOTE]
> In genere quando si lavora in Dynamics 365 Supply Chain Management e nel modulo **Gestione cespiti**, si seleziona **Nuovo** per creare un nuovo record, **Modifica** per aggiornare un record esistente e si seleziona **Salva** per salvare i dati nuovi o modificati.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]