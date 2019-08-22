---
title: Cespiti e ordini di lavoro
description: Questo argomento illustra cespiti e ordini di lavoro in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bd55988578be2b0287b399549f17642bfb1693b
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783372"
---
# <a name="assets-and-work-orders"></a>Cespiti e ordini di lavoro

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Questo argomento illustra cespiti e ordini di lavoro in Gestione cespiti. I cespiti e gli ordini di lavoro sono le parti centrali di Gestione cespiti. Un *cespite* è una macchina o parte di macchina che richiede manutenzione e assistenza regolari. I cespiti possono essere creati in una struttura gerarchica e possono essere correlati alle unità funzionali. I processi di manutenzione possono essere pianificati a tutti i livelli della struttura di cespiti.

I vari dati, ad esempio informazioni sul prodotto e specifica del cespite, e i piani di manutenzione necessari sono impostati su ciascun cespite. Nella seguente figura è illustrata una panoramica dei dati dei cespiti e del rapporto tra cespiti e tipi di processo. Il rosso testo viene utilizzato per alcuni esempi relativi a ereditarietà e dipendenze.

![Figura 1](media/05-overview-image.png)

Ogni ordine di lavoro ha un tipo di ordine di lavoro, ad esempio manutenzione preventiva, manutenzione correttiva o ispezione. L'ordine di lavoro contiene uno o più processi dell'ordine di lavoro. Ogni processo dell'ordine di lavoro definisce un processo che deve essere eseguito su un cespite e un tipo di processo correlato. Esempi di tipi di processo correlati sono l'ispezione a 10.000 km, a 50.000 km, la revisione dopo un anno e l'ispezione di sicurezza. Un solo ordine di lavoro può essere correlato a più cespiti.

Nella seguente figura è illustrata una panoramica dei dati importanti in un ordine di lavoro.

![Figura 2](media/06-overview-image.png)

Un ordine di lavoro può essere correlato a un altro ordine di lavoro e i tipi di processo possono contenere i successivi processi che creano un ordine di lavoro. In generale non ci sono dipendenze tra gli ordini di lavoro. Di conseguenza, possono modificare il loro stato del ciclo di vita e possono essere programmati indipendentemente l'uno dall'altro.

Gli ordini di lavoro possono essere creati in vari modi correlati alla manutenzione correttiva, preventiva o reattiva. È inoltre possibile creare ordini di lavoro manualmente. Nella seguente figura è illustrata una panoramica del processo per la creazione automatica o manuale degli ordini di lavoro.

![Figura 3](media/07-overview-image.png)

Diversi passaggi devono essere completati quando si desidera programmare ed eseguire un processo di manutenzione in un ordine di lavoro. Nella seguente figura è illustrata una panoramica dell'elaborazione di un ordine di lavoro.

![Figura 4](media/08-overview-image.png)

> [!NOTE]
> In genere quando si lavora in Microsoft Dynamics 365 for Finance and Operations e nel modulo **Gestione cespiti**, si seleziona **Nuovo** per creare un nuovo record, **Modifica** per aggiornare un record esistente e si seleziona **Salva** per salvare i dati nuovi o modificati.
