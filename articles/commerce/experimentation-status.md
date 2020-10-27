---
title: Esaminare lo stato di un esperimento
description: In questo argomento viene descritto lo stato di un esperimento nel ciclo di vita della sperimentazione in Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 097206c0aa487e14499bdf3907465e17b7d337e2
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930225"
---
# <a name="review-the-status-of-an-experiment"></a>Esaminare lo stato di un esperimento
La configurazione e l'esecuzione di un esperimento in Dynamics 365 Commerce comportano molti passaggi. Per informazioni sul ciclo di vita della sperimentazione, vedi [Sperimentazione in Dynamics 365 Commerce](experimentation-overview.md).

Per sapere dove si trova un esperimento nel ciclo di vita, vai alla scheda **Esperimenti** in Creazione di siti Web. Viene visualizzato un elenco di esperimenti con lo stato di ogni esperimento sia in Commerce che nel servizio di terze parti utilizzato per consentire la creazione di esperimenti, assegnare varianti e analizzare dati.

Nella colonna **Stato Commerce**, possono essere visualizzati i seguenti valori. 
- **Bozza** - L'esperimento è collegato a una pagina o a un frammento in Commerce ed è in fase di modifica.
- **Pubblicato** - Le varianti dell'esperimento sono pronte per essere visualizzate sul sito web. Se l'esperimento è in esecuzione nel servizio di terze parti, gli utenti del sito web vedranno una variante della pagina o del frammento come selezionato dal servizio di terze parti.
- **Non pubblicato** - L'esperimento non è più disponibile sul sito web. Se l'esperimento è in esecuzione nel servizio di terze parti, gli utenti del sito web vedranno una variante predefinita della pagina o del frammento.
- **Completato** - L'esperimento è stato completato e la variante è ora live per tutti gli utenti del sito web.

Allo stesso modo, nella colonna **Stato terze parti**, i seguenti valori potrebbero essere visualizzati per indicare lo stato degli esperimenti nel servizio di terze parti.
- **Bozza** - L'esperimento è configurato nel servizio di terze parti ma non è stato avviato.
- **In esecuzione** - L'esperimento è stato avviato nel servizio di terze parti e sta raccogliendo dati.
- **In sospeso** - L'esperimento è sospeso e non raccoglie dati. Devi riprendere l'esperimento affinché raccolga nuovamente i dati.
- **Archiviato** - L'esperimento è stato completato ed è stato catalogato nel servizio di terze parti per riferimento futuro.

Il diagramma seguente mostra entrambi i gruppi di stati e il modo in cui si relazionano tra loro.

[ ![Stati della sperimentazione](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)
