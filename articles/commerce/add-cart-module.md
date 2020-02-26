---
title: Modulo Carrello
description: In questo argomento vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f6dd8fb56f7342eb9c877eda503a92f4a31e5863
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025438"
---
# <a name="cart-module"></a>Modulo Carrello


[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Carrello e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo Carrello viene utilizzato per mostrare gli articoli che sono stati aggiunti al carrello prima che il cliente proceda al checkout. Ad esempio, include tutti gli articoli aggiunti al carrello e un riepilogo dell'ordine. Inoltre, consente al cliente di applicare o rimuovere codici promozionali.

Il modulo Carrello supporta il checkout come utente connesso e il checkout come guest. Supporta inoltre il collegamento **Continua gli acquisti**. È possibile configurare la route per questo collegamento in **Impostazioni sito \> Estensioni \> Route**.

Il modulo Carrello esegue il rendering dei dati in base all'ID carrello. L'ID carrello è un cookie del browser disponibile in tutto il sito.

## <a name="cart-module-properties-and-slots"></a>Proprietà e slot del modulo Carrello

Il modulo Carrello ha una proprietà **Intestazione** che può essere impostata su valori come **Carrello della spesa** e **Articoli nel carrello**. 

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Moduli che è possibile utilizzare in un modulo Carrello

- **Blocco di testo** - Questo modulo supporta messaggistica personalizzata nel modulo Carrello. I messaggi sono gestiti dal sistema di gestione dei contenuti. È possibile aggiungere un messaggio qualsiasi, ad esempio "Per problemi relativi all'ordine, contattare il numero verde di Fabrikam".
- **Selettore punto vendita** - Questo modulo visualizza un elenco dei punti vendita vicini in cui un articolo è disponibile per il ritiro. Consente agli utenti di immettere un'ubicazione per trovare punti vendita nelle vicinanze. Il modulo Selettore punto vendita è integrato nell'API di geocodifica di Bing Maps per convertire l'ubicazione in una latitudine e una longitudine. È richiesta una chiave API di Bing Maps che deve essere aggiunta alla pagina Parametri condivisi di vendita al dettaglio in Dynamics 365 Retail. Questo modulo supporta due proprietà, **Raggio di ricerca** e **Collegamento Condizioni d'utilizzo**. La proprietà **Raggio di ricerca** definisce il raggio di ricerca dei punti vendita in miglia. Se non viene specificato alcun valore, viene utilizzato il raggio di ricerca predefinito, ovvero 50 miglia. Se si utilizzano Bings Maps o qualsiasi altro servizio esterno, il **Collegamento Condizioni d'utilizzo** può essere utilizzato per fornire un collegamento alle condizioni d'utilizzo. Un collegamento alle condizioni d'utilizzo è necessario per il servizio Bing Maps. 

## <a name="cart-module-settings"></a>Impostazioni del modulo Carrello

I moduli Carrello hanno le seguenti impostazioni che è possibile configurare in **Impostazioni sito \> Estensioni**:

- **Quantità massima** - Questa proprietà viene utilizzata per specificare il numero massimo di pezzi di ogni articolo che possono essere aggiunti al carrello. Ad esempio, un rivenditore potrebbe decidere che solo 10 pezzi di ogni prodotto possono essere venduti in una singola transazione.
- **Verifica scorte** - Quando il valore è impostato su **True**, un articolo viene aggiunto al carrello solo dopo che il modulo Casella acquisti verifica che è disponibile. La verifica delle scorte viene effettuata per gli scenari in cui l'articolo verrà spedito e per quelli in cui verrà prelevato presso il punto vendita. Se il valore è impostato su **False**, non viene eseguita alcuna verifica delle scorte prima di aggiungere un articolo al carrello e di effettuare l'ordine.
- **Buffer scorte** - Questa proprietà viene utilizzata per specificare un numero di buffer per le scorte. Le scorte sono gestite in tempo reale e quando molti clienti effettuano ordini, può essere difficile mantenere un conteggio accurato delle stesse. Quando viene eseguita una verifica delle scorte, se queste sono inferiori alla quantità buffer, il prodotto viene considerato come non disponibile. Pertanto, quando si verificano rapidamente delle vendite tramite vari canali e il conteggio delle scorte non è completamente sincronizzato, il rischio che un articolo non disponibile venga venduto è minore.
- **Continua gli acquisti** - Questa proprietà viene utilizzata per specificare la route per il collegamento **Continua gli acquisti**. Questa route può essere configurata a livello di sito. Questa configurazione consente ai rivenditori di riportare il cliente alla home page o qualsiasi altra pagina del sito.

## <a name="commerce-scale-unit-interaction"></a>Interazione con Commerce Scale Unit

Il modulo Carrello recupera le informazioni sul prodotto utilizzando le API di Commerce Scale Unit. L'ID carrello del cookie del browser viene utilizzato per recuperare tutte le informazioni sui prodotti da Commerce Scale Unit.

## <a name="add-a-cart-module-to-a-page"></a>Aggiungere un modulo Carrello a una pagina

Per aggiungere un modulo Carrello a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Creare un frammento denominato **Frammento carrello** e aggiungervi un modulo Carrello.
1. Aggiungere un'intestazione al modulo Carrello.
1. Aggiungere un modulo Selettore punto vendita al modulo Carrello.
1. Salvare il frammento, finalizzare la modifica e pubblicarlo.
1. Creare un modello denominato **Modello carrello** e aggiungervi il frammento carrello appena creato.
1. Salvare il modello, finalizzare la modifica e pubblicarlo.
1. Creare una pagina che utilizza il nuovo modello.
1. Salvare la pagina e visualizzarne l'anteprima.
1. Completare la modifica della pagina e pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo Casella acquisti](add-buy-box.md)

[Modulo Checkout](add-checkout-module.md)

[Modulo Conferma ordine](order-confirmation-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)
