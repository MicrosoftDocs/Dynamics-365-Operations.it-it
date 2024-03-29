---
title: Moduli e pagine gestione conti
description: In questo articolo vengono descritti le pagine e i moduli di gestione account in Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 2db9a1218802234297e9d027691e5887d6a5c808
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274457"
---
# <a name="account-management-pages-and-modules"></a>Moduli e pagine gestione conti

[!include [banner](includes/banner.md)]

In questo articolo vengono descritti le pagine e i moduli di gestione account in Microsoft Dynamics 365 Commerce.

La gestione account fa riferimento a un gruppo di pagine utilizzate per gestire informazioni correlate all'account utente in Dynamics 365 Commerce. Le pagine di gestione account includono la pagina di destinazione di gestione account e le pagine Profilo utente, Indirizzi utente, Storico ordini, Dettagli ordine, Programma fedeltà e Elenco preferenze.

### <a name="account-management-landing-page"></a>Pagina di destinazione di gestione account

La pagina di destinazione di gestione account utilizza i seguenti moduli:

- **Contenitore** - Tutti i moduli della pagina di destinazione della gestione di account devono essere inseriti in un contenitore. 
- **Riquadro messaggio di benvenuto account** - Questo modulo viene utilizzato per fornire un messaggio di benvenuto nella pagina di gestione account. Include proprietà per l'intestazione.
- **Riquadro generico account** - Questo modulo può essere utilizzato per fornire intestazioni e collegamenti a pagine di gestione degli account, come le pagine "Storico ordini" o "Profilo". Il modulo riquadro generico può essere utilizzato per configurare un riquadro per qualsiasi pagina. In Fabrikam, questo modulo viene utilizzato per i collegamenti delle pagine "Storico ordini" e "Profilo" nella pagina di destinazione della gestione dell'account.
- **Riquadro elenco preferenze account** - Questo modulo viene utilizzato per fornire un riepilogo degli articoli nell'elenco preferenze del cliente. Ad esempio, potrebbe indicare "L'elenco preferenze contiene 10 articoli". Include le proprietà per l'intestazione e il collegamento "Visualizza dettagli". Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Elenco preferenze. 
- **Riquadro indirizzi account** - Questo modulo viene utilizzato per fornire un riepilogo degli indirizzi dell'utente. Ad esempio, potrebbe indicare "2 indirizzi sono stati aggiunti all'account". Include le proprietà per l'intestazione e il collegamento "Visualizza dettagli". Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Indirizzi utente.
- **Riquadro programma fedeltà account** - Questo modulo viene utilizzato per visualizzare e collegare informazioni sul programma fedeltà. Questo riquadro ha due stati: uno mostra i collegamenti per iscriversi a un programma fedeltà se l'utente non è già membro. L'altro stato mostra i collegamenti per visualizzare la pagina dei dettagli del programma fedeltà quando l'utente è già membro. Le proprietà includono l'intestazione, il collegamento "Iscrizione" e il link "Visualizza programma fedeltà". Il collegamento "Visualizza programma fedeltà" deve essere configurato per reindirizzare alla pagina Programma fedeltà. Il collegamento "Iscrizione" deve essere configurato per reindirizzare a una pagina in cui gli utenti possono iscriversi al programma fedeltà. 

### <a name="order-history-page"></a>Pagina Storico ordini

La pagina Storico ordini utilizza il modulo Storico ordini per visualizzare tutti gli ordini recenti effettuati dall'utente.

### <a name="order-details-page"></a>Pagina Dettagli ordine

La pagina Dettagli ordine fornisce informazioni dettagliate per ogni ordine ed è accessibile dalla pagina Storico ordini. Utilizza il modulo Dettagli ordine, che richiede l'ID vendita o l'ID transazione per recuperare i dettagli dell'ordine.

### <a name="my-profile-page"></a>Pagina profilo

La pagina Profilo personale mostra i dettagli del profilo dell'account utente utilizzando il modulo del profilo dell'account. La pagina mostra l'indirizzo e-mail associato all'account utente, nonché le preferenze impostate per l'account. Se si impostano attributi cliente personalizzati, anche la sezione "Informazioni aggiuntive" visualizzerà tali attributi. Gli utenti possono modificare il proprio nome, le preferenze o le informazioni aggiuntive (se disponibili).

### <a name="user-address-page"></a>Pagina Indirizzi utente

La pagina Indirizzi utente visualizza l'elenco degli indirizzi associati all'account utente. L'utente ha fornito tali indirizzi durante il checkout o li ha aggiunti direttamente in questa pagina. Il modulo Indirizzi utente viene utilizzato per aggiungere e modificare gli indirizzi, impostare l'indirizzo principale ed eseguire il rendering degli indirizzi esistenti nella pagina.

### <a name="wish-list-page"></a>Pagina Elenco preferenze

La pagina Elenco preferenze visualizza gli articoli aggiunti all'elenco preferenze del cliente. Utilizza il modulo Elenco preferenze per eseguire il rendering degli articoli dell'elenco preferenze.

### <a name="loyalty-page"></a>Pagina fedeltà

La pagina Programma fedeltà consente ai clienti di visualizzare i dettagli sul programma fedeltà se questi sono già membri di tale programma. Possono inoltre visualizzare i punti che hanno guadagnato e utilizzato nelle ultime transazioni. La pagina utilizza il modulo dettagli programma fedeltà per visualizzare i dettagli del programma fedeltà. 

Per iscriversi al programma fedeltà, è possibile creare una pagina di marketing con il modulo per l'iscrizione al programma fedeltà e il modulo con i termini di tale programma. Se l'utente non è membro di un programma fedeltà, questi moduli consentiranno all'utente di iscriversi.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo casella acquisti](add-buy-box.md)

[Modulo carrello](add-cart-module.md)

[Modulo checkout](add-checkout-module.md)

[Modulo Conferma ordine](order-confirmation-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
