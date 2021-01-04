---
title: Regole di configurazione
description: Questo articolo fornisce informazioni generali sulle regole di configurazione. Le regole di configurazione definiscono le relazioni tra gli articoli in una distinta base (DBA) per i prodotti che utilizzano la tecnologia di configurazione in base alle dimensioni.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e70713fb25584e26f97bcb7c769da6954aa36b81
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430811"
---
# <a name="configuration-rules"></a>Regole di configurazione

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni generali sulle regole di configurazione. Le regole di configurazione definiscono le relazioni tra gli articoli in una distinta base (DBA) per i prodotti che utilizzano la tecnologia di configurazione in base alle dimensioni.

Le regole di configurazione sono disponibili quando si definiscono i modelli di configurazione basata su dimensioni. Le regole di configurazione vengono utilizzate per applicare o proibire combinazioni di articoli specifici in una distinta base (DBA). Dopo che una DBA è stata creata e gli articoli rilevanti sono stati assegnati ai rispettivi gruppi di configurazioni, una o più regole di configurazione possono essere definite. Se due articoli appartengono l'uno all'altro, l'operatore **Seleziona** viene utilizzato per garantire l'inclusione. Se due articoli si escludono reciprocamente, l'operatore **Deseleziona** viene utilizzato per garantire l'esclusione.  

**Nota:** queste informazioni si applicano solo a rappresentazioni generali prodotto che utilizzano la tecnologia di configurazione basata su dimensioni.  

Le modifiche apportate successivamente alle regole di configurazione non interessano le configurazioni esistenti. È pertanto importante impostare le regole prima di definire una nuova configurazione e verificarle se si ritiene che siano state modificate.  

**Nota:** il metodo **Seleziona** determina la selezione automatica del gruppo di configurazione derivato, del numero di articolo e della configurazione, mentre se si utilizza il metodo **Deseleziona** il gruppo di configurazione derivato, il numero di articolo e la configurazione non possono essere selezionati.

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Panoramica della configurazione dei prodotti basati su dimensioni](dimension-based-product-configuration.md)



