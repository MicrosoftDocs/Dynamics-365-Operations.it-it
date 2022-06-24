---
title: Gestione fatture per siti Web di e-commerce B2B
description: Questo articolo descrive le funzionalità di gestione delle fatture dei siti Web di e-commerce business-to-business (B2B) di Microsoft Dynamics 365 Commerce.
author: shajain
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: fa6b81187481a6b7f47ea02291e5a581052d6c7b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854928"
---
# <a name="invoice-management-for-b2b-e-commerce-websites"></a>Gestione fatture per siti Web di e-commerce B2B

[!include [banner](../../includes/banner.md)]

Questo articolo descrive le funzionalità di gestione delle fatture dei siti Web di e-commerce business-to-business (B2B) di Microsoft Dynamics 365 Commerce.

È prassi comune per le aziende che gestiscono transazioni B2B accettare ordini con credito cliente e quindi inviare una fattura ai clienti dopo che hanno evaso l'ordine. I termini di pagamento sono definiti per i clienti e potrebbero esserci sconti per motivare i clienti a pagare in tempo o prima del tempo. Per aumentare la probabilità che i pagamenti vengano ricevuti in tempo, i siti di e-commerce B2B consentono ai clienti di visualizzare tutte le fatture. Il cliente può filtrare facilmente le fatture per visualizzare quelle pagate, non pagate e parzialmente pagate insieme alle date di scadenza.

![Pagina Fatture su un sito Web B2B.](../media/ViewInvoices.png)

> [!NOTE]
> Un utente registrato può visualizzare e pagare solo le proprie fatture. Se un conto dell'organizzazione è configurato nel menu a discesa **Conto fattura** della Scheda dettaglio **Fattura e consegna** del record cliente in Commerce headquarters, l'utente potrà visualizzare e pagare le fatture per il conto dell'organizzazione.

Nella pagina **Fatture** di un sito Web B2B, un utente può selezionare una fattura non pagata o parzialmente pagata e quindi selezionare **Paga fattura**. La fattura selezionata viene aggiunta al carrello e l'utente può procedere con il pagamento. L'utente può quindi decidere se pagare l'intero importo della fattura o un importo parziale. L'utente non può utilizzare il metodo di pagamento del conto per pagare le fatture.

> [!NOTE]
> Le fatture possono essere aggiunte al carrello solo se in questo non sono presenti articoli. Viceversa, gli articoli possono essere aggiunti al carrello solo se in questo non sono presenti fatture. Microsoft prevede di rimuovere questa restrizione nelle versioni future di Commerce.

![Pagina del carrello in un sito Web B2B.](../media/PayInvoice.png)

Nella pagina **Fatture**, un utente può anche selezionare **Richiedi fattura** accanto a una fattura. In questo modo, l'utente può richiedere l'invio dei dettagli della fattura al proprio indirizzo di posta elettronica registrato.

![Finestra di dialogo Richiedi fattura.](../media/RequestInvoice2.png)

Dopo che un utente ha richiesto una fattura, la richiesta viene spostata nella sezione **Richieste B2B** della pagina **Account personale**. Quindi, dopo l'esecuzione dei processi **P-0001** e **Sincronizza ordini e richieste del canale** in Commerce headquarters, l'indirizzo e-mail di fatturazione viene attivato e lo stato della richiesta B2B viene contrassegnato come completato.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
