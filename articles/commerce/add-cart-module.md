---
title: Modulo Carrello
description: In questo argomento vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1c910f08e5999ec586b5cb656d5769e9d4abd069
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696763"
---
# <a name="cart-module"></a>Modulo Carrello

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo Carrello è un contenitore utilizzato come host di tutti i moduli necessari per visualizzare gli articoli nel carrello. Ad esempio, include tutti gli articoli aggiunti al carrello, il riepilogo dell'ordine e i codici promozionali.

Il modulo Carrello esegue il rendering dei dati in base all'ID carrello. L'ID carrello è un cookie del browser disponibile in tutto il sito.

## <a name="cart-module-properties-and-slots"></a>Proprietà e slot del modulo Carrello

Come contenitore, un modulo Carrello controlla alcune proprietà di base, ad esempio l'intestazione e la larghezza. L'intestazione è in genere del testo come **Carrello della spesa**, **Carrello** o **Articoli nel carrello**. L'impostazione della larghezza determina se i moduli nel contenitore devono rientrare in quel contenitore oppure se possono riempire lo schermo.

La pagina carrello include più aree: voci carrello, riepilogo ordine e checkout nonché la funzionalità "Cerca nel punto vendita". Ogni area è mappata a uno slot nel modulo Carrello e ogni slot accetta un set predefinito di moduli.

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Moduli che è possibile utilizzare in un modulo Carrello

- **Voci carrello** - Questo modulo visualizza un riepilogo di ciascun articolo aggiunto al carrello. Queste informazioni includono il titolo del prodotto, le dimensioni selezionate, il prezzo, la quantità e gli sconti. Questo modulo supporta inoltre azioni come "rimuovi dal carrello" e "aggiungi a elenco preferenze" Per ogni voce, è disponibile un'opzione per spedire l'articolo oppure ritirarlo presso il punto vendita. Questa opzione deve essere configurata separatamente nel modulo Preleva nel punto vendita.
- **Riepilogo ordine** - Questo modulo visualizza un riepilogo dell'ordine. Le informazioni includono il subtotale, la spedizione, l'IVA e la somma risparmiata. Un'intestazione può essere configurata per questo modulo.
- **Codice promozione** - Questo modulo consente al cliente di utilizzare codici promozionali. Un codice promozionale può essere applicato o rimosso.
- **Checkout** - Questo modulo avvia l'azione di checkout e reindirizza l'utente alla pagina checkout. Tre collegamenti devono essere configurati per questo modulo:

    - **Checkout** - Questo collegamento obbliga i clienti ad eseguire l'accesso se non lo hanno ancora fatto.
    - **Checkout guest** - Questo collegamento consente ai clienti anonimi di effettuare ordini. È visualizzato solo quando i clienti non sono connessi.
    - **Continua gli acquisti** - Questo collegamento consente ai clienti di accedere alla home page o a qualsiasi altra pagina, di modo che possano continuare a fare acquisti.

- **Blocco ricco di contenuti** - Questo modulo supporta messaggistica personalizzata nel modulo Carrello. I messaggi sono gestiti dal sistema di gestione dei contenuti. È possibile aggiungere un messaggio qualsiasi, ad esempio "Per problemi relativi all'ordine, contattare il numero verde di Fabrikam".
- **Preleva nel punto vendita** - Questo modulo visualizza un elenco dei punti vendita vicini in cui un articolo è disponibile per il ritiro. Per impostazione predefinita, questo modulo visualizza i punti vendita entro un raggio di 80 km dall'ubicazione del cliente. Tuttavia, il raggio di ricerca può essere personalizzato nel modulo. Per ogni punto vendita, viene effettuato un controllo delle scorte, se la funzionalità di verifica delle scorte è attivata, e viene visualizzato un messaggio articolo disponibile/non disponibile appropriato.
- **Ricerca punto vendita con Bing Maps** - Questo modulo può essere utilizzato nel modulo Preleva nel punto vendita. Consente ai clienti di cercare punti vendita immettendo un'ubicazione. L'API di geocodifica di Bing Maps viene utilizzata per convertire l'ubicazione immessa dal cliente in una latitudine e una longitudine. Se questo modulo non è utilizzato, sono visualizzati solo i punti vendita vicini all'ubicazione corrente del cliente e il cliente non può cercare una posizione differente.

## <a name="cart-module-settings"></a>Impostazioni del modulo Carrello

I moduli Carrello hanno tre impostazioni che è possibile configurare:

- **Quantità massima** - Il numero massimo di pezzi per ogni articolo che possono essere aggiunti al carrello. Ad esempio, un rivenditore potrebbe decidere che solo 10 pezzi di ogni prodotto possono essere venduti in una singola transazione.
- **Verifica scorte** - Quando il valore è impostato su **True**, un articolo viene aggiunto al carrello solo dopo che il modulo Casella acquisti verifica che è disponibile. La verifica delle scorte viene effettuata per gli scenari in cui l'articolo verrà spedito e per quelli in cui verrà prelevato presso il punto vendita. Se il valore è impostato su **False**, non viene eseguita alcuna verifica delle scorte prima di aggiungere un articolo al carrello e di effettuare l'ordine.
- **Buffer scorte** - Le scorte sono gestite in tempo reale e quando molti clienti effettuano ordini, può essere difficile mantenere un conteggio accurato delle stesse. Di conseguenza, un buffer può essere definito per le scorte. Quando viene eseguita una verifica delle scorte, se queste sono inferiori alla quantità buffer, il prodotto viene considerato come non disponibile. Pertanto, quando si verificano rapidamente delle vendite tramite vari canali e il conteggio delle scorte non è completamente sincronizzato, il rischio che un articolo non disponibile venga venduto è minore.

## <a name="retail-server-interaction"></a>Interazione con Retail Server

Il modulo Carrello recupera le informazioni sui prodotti utilizzando le API di Retail Server. L'ID carrello del cookie del browser viene utilizzato per recuperare tutte le informazioni sui prodotti da Retail Server.

## <a name="add-a-cart-module-to-a-page"></a>Aggiungere un modulo Carrello a una pagina

Per aggiungere un modulo Carrello a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Creare un frammento denominato **Frammento carrello** e aggiungervi un modulo Carrello.
1. Nello slot **Voci carrello** del modulo Carrello, aggiungere un modulo Voci carrello.
1. Nello slot **Riepilogo ordine**, aggiungere un modulo Riepilogo ordine.
1. Nello slot **Codice promozionale**, aggiungere un modulo Codice promozionale.
1. Nello slot **Checkout**, aggiungere un modulo Checkout.
1. Nello slot **Cerca nel punto vendita**, aggiungere un modulo Preleva nel punto vendita.
1. Nel modulo Preleva nel punto vendita, selezionare lo slot **Ricerca punto vendita** e aggiungere un modulo Ricerca punto vendita con Bing Maps.
1. Archiviare il frammento e pubblicarlo.
1. Creare un modello denominato **Modello carrello** e aggiungervi il frammento carrello appena creato.
1. Salvare il modello, archiviarlo e pubblicarlo.
1. Creare una pagina che utilizza il nuovo modello.
1. Salvare la pagina e visualizzarne l'anteprima.
1. Archiviare la pagina e pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo Casella acquisti](add-buy-box.md)

[Modulo Checkout](add-checkout-module.md)

[Modulo Conferma ordine](order-confirmation-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)
