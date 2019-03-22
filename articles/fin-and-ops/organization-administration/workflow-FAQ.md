---
title: Domande frequenti sui flussi di lavoro
description: In questo argomento vengono fornite le risposte alle domande frequenti relative al sistema del flusso di lavoro di Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f058a450eb18e688efbc5306a42b4efef6aa91e7
ms.sourcegitcommit: 9a723737565ac78c884e40f7129d0f5aad747524
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "773217"
---
# <a name="workflow-system"></a>Sistema del flusso di lavoro

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite le risposte alle domande frequenti relative al sistema del flusso di lavoro di Microsoft Dynamics 365 for Finance and Operations.

## <a name="notifications"></a>Notifiche

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Perché si ricevono molteplici notifiche quando un elemento di lavoro viene rifiutato?
Quando un elemento di lavoro viene rifiutato, questo viene completato come rifiutato. Un altro elemento di lavoro viene creato e assegnato all'iniziatore. Ciò significa che non si ha una notifica all'iniziatore per l'elemento di lavoro rifiutato e una notifica distinta all'utente assegnato al nuovo elemento di lavoro "modifica richiesta". 

Ogni notifica è per un articolo di lavoro differente, ma le analogie possono creare confusione. Questo inconveniente verrà migliorato in una versione successiva.
