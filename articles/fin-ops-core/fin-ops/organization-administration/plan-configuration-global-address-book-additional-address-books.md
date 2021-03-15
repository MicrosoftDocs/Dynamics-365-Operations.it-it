---
title: Pianificare la rubrica globale e altre rubriche
description: Questo argomento descrive le considerazioni e le decisioni che è necessario prendere durante il processo di pianificazione prima di impostare e configurare la Rubrica globale ed eventuali rubriche aggiuntive.
author: msftbrking
manager: AnnBe
ms.date: 01/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f0a53e1f9b378759e0c5adbe0612a5fa8cddc82
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796948"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a>Piano per la rubrica globale e altre rubriche

[!include [banner](../includes/banner.md)]

Questo argomento descrive le considerazioni e le decisioni che è necessario prendere durante il processo di pianificazione prima di impostare e configurare la Rubrica globale ed eventuali rubriche aggiuntive. Alcune decisioni richiederanno la conferma delle decisioni che sono state prese per altre aree del prodotto, ad esempio la gerarchia organizzativa.

## <a name="global-address-book"></a>Rubrica globale

Prima di iniziare a utilizzare la Rubrica globale, è necessario determinarne i valori predefiniti. Questi valori predefiniti vengono utilizzati per tutte le Rubriche aggiuntive create.

**Decisioni**

- Qual è la sequenza di visualizzazione desiderata per i record di parti di tipo **Persona**? Ad esempio, una sequenza è nome, secondo nome e cognome.
- I record di parti devono essere eliminati dalla Rubrica quando il record di ruolo viene eliminato? Ad esempio, se un record cliente viene eliminato, anche il record parte deve essere eliminato?
- Quando un nuovo record viene creato, gli utenti devono essere notificati se un record duplicato viene trovato nella Rubrica globale?
- Il numero DUNS (Data Universal Numbering System) deve essere incluso nelle informazioni di un record parte?
- Se il numero DUNS viene incluso in un record parte, l'univocità del numero essere controllata?
- Quando un record parte viene creato nella Rubrica globale, si desidera un tipo, una persona o un'organizzazione predefinita della parte?
- Quali ruoli utente possono accedere alle informazioni private sull'indirizzo e sul contatto mediante i record di parti?

## <a name="additional-address-books"></a>Rubriche aggiuntive

Dopo aver creato la Rubrica globale, è possibile creare Rubriche aggiuntive in base alle esigenze, ad esempio una Rubrica separata per ogni società nell'organizzazione o per ogni linea di business. Ad esempio, Fabrikam è un'organizzazione internazionale con più società e più linee di business. Fabrikam prevede di creare una rubrica per ogni linea di business. Per le linee di business che si trovano in più sedi, ad esempio la propria società di strumenti pneumatici, Fabrikam pianifica di creare una rubrica per ogni sede. Chris, il manager IT di Fabrikam, ha creato il seguente elenco di Rubriche necessarie. Questo elenco descrive anche i record di parti che ogni Rubrica deve includere.

- **Contratti settore pubblico (PubSC):** record di tutte le parti impegnate con i contratti del settore pubblico gestiti da Fabrikam.
- **Contratti settore privato (PriSC):** record di tutte le parti impegnate con i contratti del settore privato gestiti da Fabrikam.
- **Strumenti elettronici (ET):** record di tutte le parti impegnate nell'acquisto o nella vendita di strumenti elettronici o che interagiscono con gli strumenti elettronici forniti da Fabrikam o acquistati per la stessa nella società Fabrikam-Giappone.
- **Strumenti pneumatici (PTJPN)**: record di tutte le parti impegnate nell'acquisto o nella vendita di strumenti pneumatici o che interagiscono con gli strumenti pneumatici forniti da Fabrikam o acquistati per la stessa nella società Fabrikam-Giappone.
- **Strumenti pneumatici (PTUSA):** record di tutte le parti impegnate nell'acquisto o nella vendita di strumenti pneumatici o che interagiscono con gli strumenti pneumatici forniti da Fabrikam o acquistati per la stessa nella società Fabrikam-USA.

**Decisione:**

- Quante Rubriche aggiuntive verranno create?


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]