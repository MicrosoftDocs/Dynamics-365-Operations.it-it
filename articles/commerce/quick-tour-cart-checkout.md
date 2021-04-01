---
title: Panoramica delle pagine del checkout e del carrello
description: Questo argomento fornisce una panoramica delle pagine carrello e checkout in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4f7c708aa7f1a858e78cdbda809b90b944606022
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244793"
---
# <a name="cart-and-checkout-pages-overview"></a>Panoramica delle pagine di checkout e del carrello

[!include [banner](includes/banner.md)]

Questo argomento fornisce una panoramica delle pagine carrello e checkout in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

La pagina carrello di un sito Web di e-Commerce visualizza tutti gli articoli che un cliente ha aggiunto al carrello. La pagina carrello viene generata utilizzando il modulo Carrello. Il modulo Carrello è un contenitore che ospita tutti i moduli necessari per visualizzare gli articoli nel carrello. Il modulo Carrello può anche utilizzare altri moduli per visualizzare un riepilogo dell'ordine ed eventuali codici promozionali applicati all'ordine cliente.

La pagina checkout di un sito Web di e-Commerce presenta un flusso dettagliato che i clienti seguono per immettere tutte le informazioni necessarie per effettuare un ordine. Un modulo Checkout può includere moduli che gestiscono l'indirizzo di spedizione, i metodi di spedizione, le informazioni di fatturazione, il riepilogo dell'ordine e altre informazioni correlate agli ordini cliente.

## <a name="cart-page"></a>Pagina carrello

La pagina carrello funge da carrello della spesa e include tutti gli articoli aggiunti al carrello.

Nella figura seguente è illustrato un esempio di pagina carrello creata utilizzando la libreria di moduli e il tema "Fabrikam".

![Esempio di pagina carrello](./media/cart2.PNG)

La parte principale della pagina carrello visualizza tutti gli articoli che il cliente ha aggiunto al carrello. Tutti gli sconti applicabili sono visualizzati. Tali sconti includono sconti complessi. Ad esempio "Sconto del 10% per 3 articoli acquistati" o "Sconto del 10% per l'acquisto di una borraccia e uno zaino". Il modulo Riepilogo ordine visualizza l'importo dovuto dopo l'applicazione di sconti, costi di spedizione e così via. Esiste anche un modulo Codici promozionali che consente al cliente di applicare o rimuovere codici promozionali.

Un cliente può effettuare acquisti in modo anonimo o come utente connesso. Se un cliente è connesso, gli articoli nel carrello vengono conservati tra una sessione e l'altra. In questo modo, il cliente può continuare ad acquistare da più dispositivi.

Dal carrello, il cliente può passare al checkout. Un cliente può iniziare il checkout come utente guest o come utente connesso.

Per informazioni su come creare una pagina carrello, vedere [Aggiungere un modulo Carrello a una pagina](add-cart-module.md).

## <a name="checkout-page"></a>Pagina checkout

La pagina checkout consente ai clienti di immettere le informazioni necessarie per effettuare un ordine.

Nella figura seguente è illustrato un esempio di pagina checkout creata utilizzando la libreria di moduli.

![Esempio di pagina checkout](./media/Checkout.PNG)

La parte principale della pagina checkout è l'area in cui vengono raccolte tutte le informazioni dell'ordine. Queste informazioni includono l'indirizzo di spedizione, le opzioni di consegna e le informazioni di pagamento. Il checkout presenta un flusso dettagliato, poiché le informazioni devono essere immesse in un determinato ordine per essere elaborate. Ad esempio, è necessario immettere l'indirizzo di spedizione per poter calcolare i costi di spedizione e autorizzare il pagamento.

### <a name="shipping-address"></a>Indirizzo di spedizione

Un indirizzo di spedizione è necessario se gli articoli devono essere spediti. Il formato degli indirizzi di spedizione può essere configurato in Dynamics 365 Commerce. Ad esempio, se gli articoli sono spediti negli Stati Uniti, l'indirizzo di spedizione deve includere un indirizzo di recapito e il codice postale. I campi dell'indirizzo di spedizione richiedono una convalida input di base, ad esempio la convalida di caratteri alfanumerici, lunghezza massima e numeri. Sebbene la validità dell'indirizzo non venga verificata, questa verifica può essere effettuata utilizzando servizi di terze parti personalizzati.

L'indirizzo di spedizione si applica a tutti gli articoli nel carrello per i quali l'opzione "spedizione" è selezionata. Se si utilizza il flusso di checkout fornito nella libreria di moduli, i singoli articoli del carrello non possono essere spediti a indirizzi diversi. Se si richiede questa funzionalità, può essere implementata mediante la personalizzazione dei moduli Checkout.

Dopo aver immesso l'indirizzo di spedizione, vengono visualizzati i metodi di spedizione disponibili nel punto vendita online in Dynamics 365 Commerce. I metodi di spedizione e gli indirizzi che supportano possono essere configurati in Commerce.

### <a name="payment"></a>Pagamento

Il passaggio successivo nel flusso di check out è il pagamento. Nell'e-Commerce, è possibile utilizzare molteplici metodi di pagamento per effettuare ordini, ad esempio carte di credito, gift card e punti fedeltà. È anche possibile utilizzare una combinazione di questi metodi di pagamento. A seconda dei metodi di pagamento utilizzati, è possibile che siano necessarie ulteriori informazioni. Ad esempio, un pagamento con carta di credito richiede un indirizzo di fatturazione. I pagamenti tramite carta di credito vengono elaborati utilizzando il connettore di pagamento Adyen.

#### <a name="loyalty-points"></a>Punti programma fedeltà

Durante il flusso di checkout, un cliente che è membro di un programma fedeltà e che ha maturato punti fedeltà può utilizzarli per un ordine. Il modulo Punti fedeltà è visualizzato solo se il cliente è membro di un programma fedeltà. Per i non membri e gli utenti guest, questo modulo è nascosto.

#### <a name="gift-cards"></a>Gift card

La libreria di moduli consente l'utilizzo di gift card interne per un ordine. Per applicare una gift card interna, il cliente deve essere connesso. Per un'ulteriore sicurezza, si consiglia di personalizzare il flusso utilizzando un codice PIN (numero di identificazione personale) per le gift card interne.

### <a name="signed-in-and-guest-users"></a>Utenti connessi e utenti guest

Il cliente può completare il processo di checkout come utente guest o come utente connesso. Se il cliente esegue l'accesso, le informazioni sull'account come gli indirizzi di spedizione salvati e i dettagli delle carte di credito salvati vengono recuperati automaticamente.

### <a name="order-summary"></a>Riepilogo ordine

La pagina checkout visualizza un riepilogo degli articoli nel carrello, di modo che il cliente possa verificare l'ordine prima di eseguirlo. Gli articoli non possono essere modificati durante il flusso di checkout. Un collegamento al carrello viene tuttavia fornito nel caso in cui l'utente intenda modificare gli articoli.

Dopo che il cliente fornisce le informazioni di spedizione e fatturazione, il riepilogo dell'ordine riflette l'importo dovuto dopo l'applicazione di punti fedeltà, gift card e altri pagamenti.

### <a name="order-confirmation-and-email"></a>E-mail di conferma dell'ordine

Quando il cliente effettua un ordine, viene fornito un numero di conferma. A questo punto, il pagamento è stato autorizzato ma non addebitato. Il pagamento verrà addebitato solo quando l'ordine viene evaso (ovvero quando viene spedito o prelevato).

Dopo la creazione di un ordine, un'e-mail di conferma dell'ordine viene inviato al cliente.

Per ulteriori informazioni su come creare una pagina checkout, vedere [Aggiungere un modulo Checkout a una pagina](add-checkout-module.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della home page](quick-tour-home-page.md)

[Panoramica delle pagine dei dettagli del prodotto](quick-tour-pdp.md)

[Panoramica delle pagine della gestione del conto](quick-tour-account-management.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]