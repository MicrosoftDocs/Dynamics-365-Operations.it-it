---
title: Domande frequenti sui flussi di lavoro
description: In questo argomento vengono fornite le risposte alle domande frequenti relative al sistema del flusso di lavoro.
author: ChrisGarty
manager: AnnBe
ms.date: 09/21/2020
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
ms.openlocfilehash: 4ba60c832b1f1ac5f514baef4cc0a9c36dd85af9
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826192"
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
Sì, l'autore dell'invio di un flusso di lavoro può anche approvare il flusso di lavoro se è configurato in tal modo. Per evitare questo comportamento, impostare **Amministrazione sistema > Flusso di lavoro > Parametri del flusso di lavoro > Generale > Approvatore > Non consentire l'approvazione da parte dell'autore dell'invio** su **Sì**.

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

Riassumendo, se un utente non riceve la notifica appropriata dal Centro azioni quando gli viene assegnato un elemento del flusso di lavoro, utilizzare gli [Eventi aziendali del flusso di lavoro](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) con Microsoft Power Automate per fornire notifiche aggiuntive o differenti.

## <a name="why-is-workflow-editor-not-able-to-start-under-ad-fs"></a>Perché l'editor flusso di lavoro non è in grado di avviarsi in ADFS?
Durante l'esecuzione in Active Directory Federation Services (ADFS) in un ambiente aggiornato, l'editor del flusso di lavoro potrebbe avere problemi ad avviarsi. In tal caso, assicurarsi che l'URL "https://dynamicsaxworkfloweditor/" venga aggiunto alla proprietà **Microsoft Dynamics 365 for Operations locale - Flusso di lavoro - Applicazione nativa** nelle impostazioni ADFS.

## <a name="why-am-i-getting-sql-deadlocks-on-workflow-processing"></a>Perché si ricevono blocchi critici SQL per l'elaborazione del flusso di lavoro? 
Il valore predefinito per **Numero di elementi del flusso di lavoro per batch** nella pagina **Parametri del flusso di lavoro** è 0. Un valore pari a 0 fa sì che il valore predefinito cambi in 20 elementi per batch. Prestare attenzione quando si regola questo valore perché un numero elevato di elementi per batch (> 40) può causare blocchi critici SQL.

## <a name="what-is-the-workflow-enhanced-error-feature"></a>Che cos'è la funzionalità di errore avanzato del flusso di lavoro?
La funzionalità di errore avanzato del flusso di lavoro nella versione 10.0.13 aggiunge codici di errore per differenziare classi diverse di errori del flusso di lavoro. I messaggi di errore riportati saranno per lo più simili con piccole differenze per renderli più chiari.
