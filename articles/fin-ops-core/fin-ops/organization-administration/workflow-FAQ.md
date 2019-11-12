---
title: Domande frequenti sui flussi di lavoro
description: In questo argomento vengono fornite le risposte alle domande frequenti relative al sistema del flusso di lavoro.
author: ChrisGarty
manager: AnnBe
ms.date: 06/19/2019
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
ms.openlocfilehash: 14aa9b56da005e8e3ca121589d0e22c60f34343b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189777"
---
# <a name="workflow-faq"></a>Domande frequenti sul flusso di lavoro

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite le risposte alle domande frequenti relative al sistema del flusso di lavoro.

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Perché si ricevono molteplici notifiche quando un elemento di lavoro viene rifiutato?
Quando un elemento di lavoro viene rifiutato, questo viene completato come rifiutato. Un altro elemento di lavoro viene creato e assegnato all'iniziatore. Ciò significa che non si ha una notifica all'iniziatore per l'elemento di lavoro rifiutato e una notifica distinta all'utente assegnato al nuovo elemento di lavoro "modifica richiesta". 

Ogni notifica è per un articolo di lavoro differente, ma le analogie possono creare confusione. Questo inconveniente verrà migliorato in una versione successiva.

## <a name="why-are-my-workflow-exports-failing"></a>Perché le esportazioni del flusso di lavoro non funzionano?
Attualmente, esiste una limitazione nella funzionalità di esportazione del flusso di lavoro che impedisce ai nomi del flusso di lavoro di superare i 48 caratteri. L'utilizzo di un nome superiore ai 48 caratteri può comportare l'errore di autenticazione del server e/o impedire l'esportazione di un file senza un tipo di file. Il seguente post di blog sulla [risoluzione dei problemi di esportazione del flusso di lavoro](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting) fornisce ulteriori dettagli.

## <a name="can-the-submitter-of-a-workflow-also-approve-the-workflow"></a>L'autore dell'invio di un flusso di lavoro può anche approvare il flusso di lavoro?
Sì, l'autore dell'invio di un flusso di lavoro può anche approvare il flusso di lavoro se è configurato in tal modo. Per evitare questo comportamento, impostare **Parametri del flusso di lavoro > Generale > Approvatore > Non consentire l'approvazione da parte dell'autore dell'invio** su **Sì**.

## <a name="can-i-add-alerts-to-workflows-to-provide-notifications-to-users"></a>È possibile aggiungere avvisi ai flussi di lavoro per fornire notifiche agli utenti?
Di seguito sono descritte alcune aree chiave da prendere in considerazione in relazione all'aggiunta di avvisi ai flussi di lavoro per fornire notifiche:
- Avvici e meccanismi di notifica per flussi di lavoro
    - Gli avvisi possono essere impostati per le modifiche ai record. I flussi di lavoro modificano i record, pertanto è possibile impostare un avviso relativo a una modifica di record generata da un flusso di lavoro. Tuttavia, poiché i flussi di lavoro hanno varie opzioni di notifica incorporate, l'utilizzo di avvisi non è ideale.
- Notifiche standard da flussi di lavoro 
    - I flussi di lavoro presentano notifiche di posta elettronica incorporate. Un cliente può configurare le notifiche di modo che agli utenti siano inviati messaggi di posta elettronica. Queste notifiche non generano messaggi del Centro azioni per gli utenti.
    - In un aggiornamento futuro aggiungeremo un messaggio del Centro azioni di modo che a un utente sia assegnato un elemento del flusso di lavoro. 
- Aggiunta di notifiche a flussi di lavoro
    - I messaggi del Centro azioni possono essere creati per utenti specifici, ad esempio un messaggio creato da un flusso di lavoro in X++.
    - [I flussi di lavoro dispongono di eventi aziendali](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) che il cliente può utilizzare affinché i flussi di lavoro abbiano le notifiche di cui necessitano.   

Riassumendo, se un utente non riceve la notifica appropriata dal Centro azioni quando gli viene assegnato un elemento del flusso di lavoro, utilizzare gli [Eventi aziendali del flusso di lavoro](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) con Microsoft Flow per fornire notifiche aggiuntive o differenti.