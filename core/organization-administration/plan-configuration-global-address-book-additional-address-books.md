---
title: Configurare le rubriche globali
description: "Questo articolo descrive le considerazioni e le decisioni che è necessario prendere durante il processo di pianificazione prima di impostare e configurare la rubrica globale ed eventuali rubriche aggiuntive in Microsoft Dynamics 365 for Operations. Alcune decisioni richiederanno la conferma delle decisioni che sono state prese per altre aree del prodotto, ad esempio la gerarchia organizzativa."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: dabac8a899a07192d31f4a8f4f70b12ed5410093
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="configure-global-address-books"></a>Configurare le rubriche globali

[!include[banner](../includes/banner.md)]


Questo articolo descrive le considerazioni e le decisioni che è necessario prendere durante il processo di pianificazione prima di impostare e configurare la rubrica globale ed eventuali rubriche aggiuntive in Microsoft Dynamics 365 for Operations. Alcune decisioni richiederanno la conferma delle decisioni che sono state prese per altre aree del prodotto, ad esempio la gerarchia organizzativa.

<a name="global-address-book"></a>Rubrica globale
-------------------

Prima di iniziare a utilizzare la Rubrica globale, è necessario determinarne i valori predefiniti. Questi valori predefiniti vengono utilizzati per tutte le Rubriche aggiuntive create. **Decisioni:**

-   Qual è la sequenza di visualizzazione desiderata per i record di parti di tipo **Persona**? Ad esempio, una sequenza è nome, secondo nome e cognome.
-   I record di parti devono essere eliminati dalla Rubrica quando il record di ruolo viene eliminato? Ad esempio, se un record cliente viene eliminato, anche il record parte deve essere eliminato?
-   Quando un nuovo record viene creato, gli utenti devono essere notificati se un record duplicato viene trovato nella Rubrica globale?
-   Il numero DUNS (Data Universal Numbering System) deve essere incluso nelle informazioni di un record parte?
-   Se il numero DUNS viene incluso in un record parte, l'univocità del numero essere controllata?
-   Quando un record parte viene creato nella Rubrica globale, si desidera un tipo, una persona o un'organizzazione predefinita della parte?
-   Quali ruoli utente possono accedere alle informazioni private sull'indirizzo e sul contatto mediante i record di parti?

## <a name="additional-address-books"></a>Rubriche aggiuntive
Dopo aver creato la Rubrica globale, è possibile creare Rubriche aggiuntive in base alle esigenze, ad esempio una Rubrica separata per ogni società nell'organizzazione o per ogni linea di business. Ad esempio, Fabrikam è un'organizzazione internazionale con più società e più linee di business. Fabrikam prevede di creare una rubrica per ogni linea di business. Per le linee di business che si trovano in più sedi, ad esempio la propria società di strumenti pneumatici, Fabrikam pianifica di creare una rubrica per ogni sede. Chris, il manager IT di Fabrikam, ha creato il seguente elenco di Rubriche necessarie. Questo elenco descrive anche i record di parti che ogni Rubrica deve includere.

-   **Contratti settore pubblico (PubSC):** record di tutte le parti impegnate con i contratti del settore pubblico gestiti da Fabrikam.
-   **Contratti settore privato (PriSC):** record di tutte le parti impegnate con i contratti del settore privato gestiti da Fabrikam.
-   **Strumenti elettronici (ET):** record di tutte le parti impegnate nell'acquisto o nella vendita di strumenti elettronici o che interagiscono con gli strumenti elettronici forniti da Fabrikam o acquistati per la stessa nella società Fabrikam-Giappone.
-   **Strumenti pneumatici (PTJPN)**: record di tutte le parti impegnate nell'acquisto o nella vendita di strumenti pneumatici o che interagiscono con gli strumenti pneumatici forniti da Fabrikam o acquistati per la stessa nella società Fabrikam-Giappone.
-   **Strumenti pneumatici (PTUSA):** record di tutte le parti impegnate nell'acquisto o nella vendita di strumenti pneumatici o che interagiscono con gli strumenti pneumatici forniti da Fabrikam o acquistati per la stessa nella società Fabrikam-USA.

**Decisione:**

-   Quante Rubriche aggiuntive verranno create?

### <a name="address-book-security"></a>Sicurezza delle rubriche

In qualsiasi momento è possibile creare rubriche e impostare parametri di sicurezza per le rubriche. Non è necessario impostare i privilegi di sicurezza per una rubrica, me se non si fa, tutti i lavoratori all'interno dell'organizzazione potranno visualizzare tutti i record di parti nella rubrica. È possibile impostare privilegi di sicurezza per record di parti nelle rubriche. I privilegi di sicurezza sono basati sui team. Questo approccio garantisce che solo i lavoratori assegnati a un team con l'autorizzazione ad accedere a una rubrica possono visualizzare i record di parti nella rubrica. È necessario selezionare i team che hanno accesso a ogni rubrica. Per ogni rubrica è possibile impostare privilegi di sicurezza che consentono o negano l'accesso a specifici team. Se a un team vengono concessi privilegi per una rubrica, tutti i membri del team potranno visualizzare i record nella rubrica. Se a un team non viene concesso l'accesso a una rubrica, i membri del team non potranno visualizzare la rubrica o i suoi contenuti. **Decisione:**

-   Quali team devo avere accesso a ogni nuova rubrica creata?





