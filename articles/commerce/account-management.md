---
title: Pagine e moduli di gestione account
description: In questo argomento vengono descritti le pagine e i moduli di gestione account in Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3986505a7e0e8d33d5b8ff2c06f493335731a8d9
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785384"
---
# <a name="account-management-pages-and-modules"></a>Pagine e moduli di gestione account

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritti le pagine e i moduli di gestione account in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

La gestione account fa riferimento a un gruppo di pagine utilizzate per gestire informazioni correlate all'account utente in Dynamics 365 Commerce. Le pagine di gestione account includono la pagina di destinazione di gestione account e le pagine Profilo utente, Indirizzi utente, Storico ordini, Dettagli ordine, Programma fedeltà e Elenco preferenze.

### <a name="account-management-landing-page"></a>Pagina di destinazione di gestione account

La pagina di destinazione di gestione account utilizza i seguenti moduli:

- **Posizionamento contenuti** - Questo modulo è un modulo contenitore che include tutti i moduli nella pagina di destinazione di gestione account.
- **Elemento messaggio di benvenuto account** - Questo modulo viene utilizzato per fornire un messaggio di benvenuto nella pagina di gestione account. Include proprietà per l'intestazione e le dimensioni dei riquadri. La proprietà **Dimensioni riquadro** definisce la larghezza del modulo nel modulo Posizionamento contenuti. I valori vanno da **1** a **12**, dove **12** rappresenta l'intera larghezza del contenitore Posizionamento contenuti.
- **Elemento esecuzione ordini account** - Questo modulo viene utilizzato per fornire un riepilogo del numero di ordini effettuati dall'account utente. Include le proprietà per l'intestazione, le dimensioni dei riquadri e il collegamento "Visualizza dettagli". Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Storico ordini.
- **Elemento posizionamento profilo account** - Questo modulo viene utilizzato per fornire un riepilogo del profilo utente. Include le proprietà per l'intestazione, le dimensioni dei riquadri e il collegamento "Visualizza dettagli". Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Profilo utente.
- **Elemento elenco preferenze account** - Questo modulo viene utilizzato per fornire un riepilogo degli articoli nell'elenco preferenze del cliente. Ad esempio, potrebbe indicare "L'elenco preferenze contiene 10 articoli". Include le proprietà per l'intestazione, le dimensioni dei riquadri e il collegamento "Visualizza dettagli". Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Elenco preferenze.
- **Elemento indirizzi account** - Questo modulo viene utilizzato per fornire un riepilogo degli indirizzi dell'utente. Ad esempio, potrebbe indicare "2 indirizzi sono stati aggiunti all'account". Include le proprietà per l'intestazione, le dimensioni dei riquadri e il collegamento "Visualizza dettagli". Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Indirizzi utente.
- **Elemento programma fedeltà account** - Questo modulo viene utilizzato per visualizzare e collegare le informazioni sul programma fedeltà. Include proprietà per l'intestazione, le dimensioni dei riquadri, il collegamento "Visualizza dettagli" e il collegamento "Diventa membro". Il collegamento "Visualizza dettagli" deve essere configurato per reindirizzare alla pagina Programma fedeltà. Il collegamento "Diventa membro" deve essere configurato per reindirizzare a una pagina in cui gli utenti possono iscriversi al programma fedeltà.

### <a name="order-history-page"></a>Pagina Storico ordini

La pagina Storico ordini utilizza il modulo Storico ordini per visualizzare tutti gli ordini recenti effettuati dall'utente.

### <a name="order-details-page"></a>Pagina Dettagli ordine

La pagina Dettagli ordine fornisce informazioni dettagliate per ogni ordine ed è accessibile dalla pagina Storico ordini. Utilizza il modulo Dettagli ordine, che richiede l'ID vendita o l'ID transazione per recuperare i dettagli dell'ordine.

### <a name="user-profile-page"></a>Pagina Profilo utente

La pagina Profilo utente visualizza i dettagli sull'account utente, ad esempio il nome e l'indirizzo di posta elettronica dell'utente. Utilizza il modulo Profilo utente. L'indirizzo di posta elettronica non può essere rimosso, ma può essere modificato.

### <a name="user-address-page"></a>Pagina Indirizzi utente

La pagina Indirizzi utente visualizza l'elenco degli indirizzi associati all'account utente. L'utente ha fornito tali indirizzi durante il checkout o li ha aggiunti direttamente in questa pagina. Il modulo Indirizzi utente viene utilizzato per aggiungere e modificare gli indirizzi, impostare l'indirizzo principale ed eseguire il rendering degli indirizzi esistenti nella pagina.

### <a name="wish-list-page"></a>Pagina Elenco preferenze

La pagina Elenco preferenze visualizza gli articoli aggiunti all'elenco preferenze del cliente. Utilizza il modulo Elenco preferenze per eseguire il rendering degli articoli dell'elenco preferenze.

### <a name="loyalty-page"></a>Pagina Programma fedeltà

La pagina Programma fedeltà consente ai clienti di iscriversi a un programma fedeltà oppure, se sono già membri di tale programma, di visualizzare dettagli relativi al programma. Possono inoltre visualizzare i punti che hanno guadagnato e utilizzato nelle ultime transazioni.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo Casella acquisti](add-buy-box.md)

[Modulo Carrello](add-cart-module.md)

[Modulo Checkout](add-checkout-module.md)

[Modulo Conferma ordine](order-confirmation-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)
