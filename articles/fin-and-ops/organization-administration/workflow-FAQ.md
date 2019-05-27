---
title: Domande frequenti sui flussi di lavoro
description: In questo argomento vengono fornite le risposte alle domande frequenti relative al sistema del flusso di lavoro di Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 05/07/2019
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
ms.openlocfilehash: f6240b1b5136937aa47f455547fed6f0c7c08e2c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509293"
---
# <a name="workflow-system"></a>Sistema del flusso di lavoro

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite le risposte alle domande frequenti relative al sistema del flusso di lavoro di Microsoft Dynamics 365 for Finance and Operations.

## <a name="notifications"></a>Notifiche

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Perché si ricevono molteplici notifiche quando un elemento di lavoro viene rifiutato?
Quando un elemento di lavoro viene rifiutato, questo viene completato come rifiutato. Un altro elemento di lavoro viene creato e assegnato all'iniziatore. Ciò significa che non si ha una notifica all'iniziatore per l'elemento di lavoro rifiutato e una notifica distinta all'utente assegnato al nuovo elemento di lavoro "modifica richiesta". 

Ogni notifica è per un articolo di lavoro differente, ma le analogie possono creare confusione. Questo inconveniente verrà migliorato in una versione successiva.

### <a name="why-are-my-workflow-exports-failing"></a>Perché le esportazioni del flusso di lavoro non funzionano?
Attualmente, esiste una limitazione nella funzionalità di esportazione del flusso di lavoro che impedisce ai nomi del flusso di lavoro di superare i 48 caratteri. L'utilizzo di un nome superiore ai 48 caratteri può comportare l'errore di autenticazione del server e/o impedire l'esportazione di un file senza un tipo di file. Il seguente post di blog sulla [risoluzione dei problemi di esportazione del flusso di lavoro](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting) fornisce ulteriori dettagli.
