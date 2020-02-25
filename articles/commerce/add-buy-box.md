---
title: Modulo Casella acquisti
description: In questo argomento vengono descritti i moduli Casella acquisti e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 13d044a150651dd18c3a09c4db6a783fe8f42287
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025461"
---
# <a name="buy-box-module"></a>Modulo Casella acquisti


[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Casella acquisti e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Il termine *casella acquisti* si riferisce in genere all'area di una pagina dettagli prodotto che si trova "in primo piano" e che ospita le informazioni più importanti necessarie per effettuare un acquisto (un'area "in primo piano" è visibile quando la pagina viene caricata la prima volta, di modo che gli utenti non devono scorrere per vederla).

Un modulo Casella acquisti è un contenitore speciale utilizzato per l'hosting di tutti i moduli visualizzati nell'area Casella acquisti di una pagina dettagli prodotto.

L'URL di una pagina dettagli prodotto include l'ID prodotto. Tutte le informazioni necessarie per eseguire il rendering di un modulo Casella acquisti derivano da questo ID prodotto. Se un ID prodotto non viene fornito, il rendering del modulo Casella acquisti non verrà eseguito correttamente in una pagina. Pertanto, un modulo Casella acquisti può essere utilizzato solo in pagine con contesto del prodotto. Per utilizzarlo in una pagina senza contesto del prodotto (ad esempio, una home page o una pagina di marketing), è necessario eseguire ulteriori personalizzazioni.

## <a name="buy-box-module-properties-and-slots"></a>Proprietà e slot del modulo Casella acquisti 

In una pagina dettagli prodotto, una casella acquisti è suddivisa in due aree: un'area multimediale a sinistra e un'area contenuto a destra. Per impostazione predefinita, la proporzione in termini di larghezza delle colonne dell'area multimediale e dell'area contenuto è 2:1. Nei dispositivi mobili, le due are sono impilate, di modo che un'area appaia sotto l'altra. I temi possono essere utilizzati per personalizzare la larghezza delle colonne e la classificazione dello stack.

Un modulo Casella acquisti esegue il rendering di titolo, descrizione, prezzo e valutazioni di un prodotto. Consente inoltre ai clienti di selezionare varianti di prodotto con attributi di prodotto diversi, come dimensioni, stile e colore. Quando si seleziona una variante prodotto, altre proprietà nella casella acquisti (ad esempio la descrizione e le immagini del prodotto) vengono aggiornate per riflettere le informazioni relative alla variante. 

Viene fornito un selettore della quantità, di modo che i clienti possano specificare la quantità di articoli da acquistare. La quantità massima che può essere acquistata può essere definita nelle impostazioni del sito.
 
Dalla casella acquisti, i clienti possono anche eseguire azioni come aggiungere un prodotto al carrello, aggiungere un prodotto all'elenco preferenze e selezionare un luogo di ritiro. Queste azioni possono essere eseguite per un prodotto o una variante di prodotto. Per aggiungere un prodotto a un elenco preferenze, il cliente deve aver effettuato l'accesso.

I temi possono essere utilizzati per rimuovere o modificare l'ordine delle proprietà della casella acquisti e i controlli delle azioni. 

## <a name="module-properties"></a>Proprietà del modulo

- **Tag di intestazione** - Questa proprietà definisce il tag di intestazione per il titolo del prodotto. Se la casella acquisti si trova nella parte superiore della pagina, questa proprietà deve essere impostata su **h1** per soddisfare gli standard di accessibilità. 

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Moduli che è possibile utilizzare in un modulo Casella acquisti

- **Galleria multimediale** - Questo modulo viene utilizzato per visualizzare immagini di un prodotto in una pagina dettagli prodotto. Può supportare numerose immagini nonché immagini di anteprima. Le immagini di anteprima possono essere disposte orizzontalmente (come riga sotto l'immagine) o verticalmente (come colonna accanto all'immagine). Il modulo Galleria multimediale può essere aggiunto allo slot **Multimedia** nel modulo Casella acquisti. Attualmente supporta solo immagini. 
- **Selettore punto vendita** - Questo modulo visualizza un elenco dei punti vendita vicini in cui un articolo è disponibile per il ritiro. Consente agli utenti di immettere un'ubicazione per trovare punti vendita nelle vicinanze. Il modulo Selettore punto vendita è integrato nell'API di geocodifica di Bing Maps per convertire l'ubicazione in una latitudine e una longitudine. È richiesta una chiave API di Bing Maps che deve essere aggiunta alla pagina Parametri condivisi di vendita al dettaglio in Dynamics 365 Retail. Questo modulo supporta due proprietà, **Raggio di ricerca** e **Collegamento Condizioni d'utilizzo**. La proprietà **Raggio di ricerca** definisce il raggio di ricerca dei punti vendita in miglia. Se non viene specificato alcun valore, viene utilizzato il raggio di ricerca predefinito, ovvero 50 miglia. Se si utilizzano Bings Maps o qualsiasi altro servizio esterno, il **Collegamento Condizioni d'utilizzo** può essere utilizzato per fornire un collegamento alle condizioni d'utilizzo. Un collegamento alle condizioni d'utilizzo è necessario per il servizio Bing Maps. 

## <a name="buy-box-module-settings"></a>Impostazioni del modulo Casella acquisti

I moduli Casella acquisti hanno tre impostazioni che è possibile configurare in **Impostazioni sito \> Estensioni**:

- **Quantità massima** - Questa proprietà viene utilizzata per specificare il numero massimo di pezzi di ogni articolo che possono essere aggiunti al carrello. Ad esempio, un rivenditore potrebbe decidere che solo 10 pezzi di ogni prodotto possono essere venduti in una singola transazione.
- **Verifica scorte** - Quando il valore è impostato su **True**, un articolo viene aggiunto al carrello solo dopo che il modulo Casella acquisti verifica che è disponibile. La verifica delle scorte viene effettuata per gli scenari in cui l'articolo verrà spedito e per quelli in cui verrà prelevato presso il punto vendita. Se il valore è impostato su **False**, non viene eseguita alcuna verifica delle scorte prima di aggiungere un articolo al carrello e di effettuare l'ordine.
- **Buffer scorte** - Questa proprietà viene utilizzata per specificare un numero di buffer per le scorte. Le scorte sono gestite in tempo reale e quando molti clienti effettuano ordini, può essere difficile mantenere un conteggio accurato delle stesse. Quando viene eseguita una verifica delle scorte, se queste sono inferiori alla quantità buffer, il prodotto viene considerato come non disponibile. Pertanto, quando si verificano rapidamente delle vendite tramite vari canali e il conteggio delle scorte non è completamente sincronizzato, il rischio che un articolo non disponibile venga venduto è minore.

## <a name="commerce-scale-unit-interaction"></a>Interazione con Commerce Scale Unit

Il modulo Casella acquisti recupera le informazioni sul prodotto utilizzando le API di Commerce Scale Unit. L'ID prodotto nella pagina dettagli prodotto è utilizzato per recuperare tutte le informazioni.

## <a name="add-a-buy-box-module-to-a-page"></a>Aggiungere un modulo Casella acquisti a una pagina

Per aggiungere un modulo Casella acquisti a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Creare un frammento denominato **Frammento casella acquisti** e aggiungervi un modulo Casella acquisti.
1. Aggiungere un modulo Galleria multimediale allo slot **Multimedia** del modulo Casella acquisti.
1. Nello slot **Selettore punto vendita** del modulo Casella acquisti, aggiungere un modulo Selettore punto vendita.
1. Archiviare la pagina e pubblicarla.
1. Creare un modello per una pagina dettagli prodotto (PDP) e denominarlo **Modello PDP**.
1. Aggiungere una pagina predefinita.
1. Nello slot **Principale** della pagina predefinita, aggiungere un frammento casella acquisti.
1. Salvare il modello, finalizzare la modifica e pubblicarlo.
1. Utilizzare il modello appena creato per creare una pagina denominata **Pagina PDP**.
1. Nello slot **Principale** della nuova pagina, aggiungere un frammento casella acquisti.
1. Salvare la pagina e visualizzarne l'anteprima. Aggiungere il parametro della stringa di query **?productid=&lt;product id&gt;** all'URL della pagina di anteprima. In tal modo, il contesto del prodotto è utilizzato per caricare ed eseguire il rendering della pagina di anteprima.
1. Salvare la pagina, finalizzare la modifica e pubblicarla. Una casella acquisti deve essere visualizzata nella pagina dettagli prodotto.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo Carrello](add-cart-module.md)

[Modulo Checkout](add-checkout-module.md)

[Modulo Conferma ordine](order-confirmation-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)
