---
title: Creare gerarchie di modellazione per le organizzazioni B2B
description: Questo argomento descrive come creare gerarchie di modellazione organizzative per le organizzazioni business-to-business (B2B).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 91cb01637faa69bd3c7fefefae69c60cb948510e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211227"
---
# <a name="create-org-modeling-hierarchies-for-b2b-organizations"></a>Creare gerarchie di modellazione per le organizzazioni B2B

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come creare gerarchie di modellazione organizzative per le organizzazioni business-to-business (B2B) in Microsoft Dynamics 365 Commerce.

In Commerce Headquarters, le organizzazioni dei partner commerciali sono rappresentate da clienti ed entità gerarchiche di clienti. L'organizzazione del partner commerciale e i suoi utenti sono rappresentati come clienti e le gerarchie dei clienti vengono utilizzate per associare questi clienti tra loro.

Quando la richiesta di un partner commerciale di partecipare a un sito di e-commerce B2B viene approvata, vengono eseguite le seguenti azioni:

- Due nuovi record cliente vengono creati nel sistema: un record cliente **Digita organizzazione** per l'organizzazione del partner commerciale e un record del cliente **Digita persona** per il richiedente (ovvero, l'utente del partner commerciale che ha inoltrato la richiesta).
- Un nuovo record della gerarchia del cliente viene creato in **Cliente \> Gerarchia dei clienti**. Questo record ha le seguenti proprietà di intestazione:

    - **ID gerarchia cliente**: un ID univoco per la gerarchia del cliente. Questo ID utilizza la sequenza numerica definita nei parametri condivisi di Commerce in Commerce Headquarters.
    - **Nome**: il nome dell'organizzazione del partner commerciale, come specificato nella richiesta di onboarding.
    - **Scopo**: questa proprietà è impostata sul valore predefinito **Organizzazione B2B**.
    - **Organizzazione**: l'ID cliente del partner commerciale.

Di seguito sono riportati i dettagli del record della gerarchia del cliente:

- Il record del cliente del richiedente è associato alla gerarchia del cliente.
- Il ruolo di amministratore è associato al richiedente.

Quando l'amministratore aggiunge più utenti all'organizzazione del partner commerciale su un sito B2B, viene creato un nuovo record cliente per ogni utente nella sede in Commerce Headquarters. Questo record del cliente viene inoltre aggiunto anche al record della gerarchia del cliente rilevante per il partner commerciale e ha il ruolo di "utente".

> [!NOTE]
> Nella maggior parte dei casi, i valori delle proprietà corrispondenti di tutti i record dei clienti in una gerarchia dovrebbero corrispondere. Ad esempio, poiché tutti gli utenti dei partner commerciali dovrebbero ottenere prezzi simili per i prodotti, il loro gruppo di prezzi e le configurazioni associate dovrebbero corrispondere. Tuttavia, il sistema non applica questa coerenza. Pertanto, gli utenti di Commerce Headquarters pertinenti sono responsabili di garantire che i valori e le configurazioni delle proprietà corrispondano per tutti i clienti in una data gerarchia.

Gli utenti di Commerce Headquarters possono esaminare i valori delle proprietà per tutti i record dei clienti nella gerarchia in una vista affiancata. Seleziona le proprietà del record del cliente rilevanti selezionando i nomi delle schede nel menu a discesa. Gli utenti possono visualizzare e modificare direttamente i valori delle proprietà da questa vista. In alternativa, se desideri applicare tutti i valori dal record cliente amministratore a tutti i record cliente utente, seleziona **Sovrascrivi** nei dettagli della gerarchia dei clienti.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un sito di e-commerce B2B](set-up-b2b-site.md)

[Gestisci gli utenti dei partner commerciali sui siti di e-commerce B2B](manage-b2b-users.md)

[Configura il metodo di pagamento dell'account cliente per i siti Web di e-commerce B2B](payment-method.md)

[Impostare limiti di quantità di prodotti per i siti di e-commerce B2B](quantity-limits.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]