---
title: Modulo Casella acquisti
description: In questo argomento vengono descritti i moduli Casella acquisti e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/11/2019
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
ms.openlocfilehash: e86b1881e6829ccc33f36ada453af20c1815a2fa
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811143"
---
# <a name="buy-box-module"></a>Modulo Casella acquisti

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Casella acquisti e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Il termine *casella acquisti* si riferisce in genere all'area di una pagina dettagli prodotto che si trova "in primo piano" e che ospita le informazioni più importanti necessarie per effettuare un acquisto (un'area "in primo piano" è visibile quando la pagina viene caricata la prima volta, di modo che gli utenti non devono scorrere per vederla).

Un modulo Casella acquisti è un contenitore speciale utilizzato per l'hosting di tutti i moduli visualizzati nell'area Casella acquisti di una pagina dettagli prodotto.

L'URL di una pagina dettagli prodotto include l'ID prodotto. Tutte le informazioni necessarie per eseguire il rendering di un modulo Casella acquisti derivano da questo ID prodotto. Se un ID prodotto non viene fornito, il rendering del modulo Casella acquisti non verrà eseguito correttamente in una pagina. Di conseguenza, un modulo Casella acquisti non può essere utilizzato in una pagina senza contesto del prodotto (ad esempio una home page o una pagina marketing).

## <a name="buy-box-module-properties-and-slots"></a>Proprietà e slot del modulo Casella acquisti 

Come contenitore, un modulo Casella acquisti controlla alcune proprietà di base, ad esempio la larghezza. L'impostazione della larghezza determina se i moduli nel contenitore devono rientrare in quel contenitore oppure se possono riempire lo schermo.

In una pagina dettagli prodotto, una casella acquisti è suddivisa in due aree: un'area multimediale a sinistra e un'area contenuto a destra. Queste due aree sono rappresentate da slot nel modulo Casella acquisti. Ogni slot è preconfigurato per accettare solo moduli specifici supportati dallo slot. Ad esempio, uno slot **Multimedia** supporta solo il modulo Galleria multimediale.

Per impostazione predefinita, la proporzione in termini di larghezza delle colonne per l'area multimediale e l'area contenuto è 2:1. Tuttavia, la larghezza delle colonne può essere sostituita dal tema. Inoltre, nei dispositivi mobili, le due are sono impilate, di modo che un'area appaia sotto l'altra.

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Moduli che è possibile utilizzare in un modulo Casella acquisti

- **Galleria multimediale** - Questo modulo viene utilizzato per visualizzare immagini di un prodotto in una pagina dettagli prodotto. Può supportare numerose immagini nonché immagini di anteprima. Le immagini di anteprima possono essere disposte orizzontalmente (come riga sotto l'immagine) o verticalmente (come colonna accanto all'immagine). Il modulo Galleria multimediale può essere aggiunto allo slot **Multimedia** nel modulo Casella acquisti. Supporta attualmente solo immagini e video.
- **Titolo prodotto** - Questo modulo visualizza il titolo del prodotto in una pagina dettagli prodotto. Per impostazione predefinita, **H1** viene utilizzato come tag di intestazione, ma questa impostazione può essere modificata come necessario.
- **Valutazione prodotto** - Questo modulo visualizza le valutazioni con stelle, in base alle valutazioni dei clienti su un prodotto. Il modulo Casella acquisti recupera le valutazioni di ogni prodotto dal servizio Valutazioni e recensioni.
- **Prezzo prodotto** - Questo modulo visualizza il prezzo del prodotto. Il prezzo include i prezzi barrati e gli sconti.
- **Descrizione prodotto** - Questo modulo visualizza la descrizione del prodotto.
- **Configurazione prodotto** - Questo modulo visualizza le dimensioni, lo stile e il formato del prodotto. I selettori delle dimensioni possono essere impilati verticalmente oppure affiancati. Quando si seleziona una variante prodotto, altre proprietà nella casella acquisti (ad esempio la descrizione e le immagini del prodotto) vengono aggiornate per riflettere le informazioni relative alla variante.
- **Quantità prodotto** - Questo modulo è utilizzato per configurare la quantità del prodotto. Un'impostazione limita la quantità di prodotto o di una variante che può essere aggiunta al carrello.
- **Aggiungi al carrello** - Questo modulo è utilizzato per eseguire l'azione "aggiungi al carrello". È possibile aggiungere solo un prodotto o una variante al carrello. In altre parole, un prodotto master non può essere aggiunto al carrello. Il modulo presenta la proprietà **Vai al carrello** che l'autore del sito può impostare. Quando questa proprietà è impostata su **True**, viene visualizzata la pagina carrello ogni volta che viene eseguita l'azione "aggiungi al carrello". Se è impostata su **False**, il cliente può continuare a esaminare la pagina dettagli prodotto dopo l'aggiunta di articoli al carrello.
- **Aggiungi a elenco preferenze** - Questo modulo è utilizzato per aggiungere un articolo all'elenco preferenze del cliente. È possibile aggiungere solo un prodotto o una variante all'elenco preferenze. Inoltre, il cliente deve aver eseguito l'accesso al sito. Il modulo include la logica di gestione degli errori per assicurarsi che entrambe le condizioni siano soddisfatte.
- **Cerca nel punto vendita** - Questo modulo attiva il flusso "acquista online e preleva nel punto vendita".
- **Preleva nel punto vendita** - Questo modulo visualizza un elenco dei punti vendita vicini in cui un articolo è disponibile per il ritiro. Per impostazione predefinita, questo modulo visualizza i punti vendita entro un raggio di 80 km dall'ubicazione del cliente. Tuttavia, il raggio di ricerca può essere personalizzato nel modulo. Per ogni punto vendita, viene effettuato un controllo delle scorte, se la funzionalità di verifica delle scorte è attivata, e viene visualizzato un messaggio articolo disponibile/non disponibile appropriato.
- **Ricerca punto vendita con Bing Maps** - Questo modulo può essere utilizzato nel modulo Preleva nel punto vendita. Consente ai clienti di cercare punti vendita immettendo un'ubicazione. L'API di geocodifica di Bing Maps viene utilizzata per convertire la posizione specificata in una latitudine e una longitudine. Se questo modulo è utilizzato, sono visualizzati solo i punti vendita vicini alla posizione corrente del cliente e il cliente non può cercare una posizione differente.
- **Blocco ricco di contenuti** - Questo modulo può visualizzare un messaggio che l'autore del sito o il rivenditore intende promuovere nella casella acquisti, ad esempio "Per problemi relativi all'ordine, contattare il numero verde di Fabrikam" o "Spedizione gratuita per ordini superiori a 100 €". I messaggi sono gestiti dal sistema di gestione dei contenuti.

## <a name="buy-box-module-settings"></a>Impostazioni del modulo Casella acquisti

I moduli Casella acquisti hanno tre impostazioni che è possibile configurare:

- **Quantità massima** - Il numero massimo di pezzi per ogni articolo che possono essere aggiunti al carrello. Ad esempio, un rivenditore potrebbe decidere che solo 10 pezzi di ogni prodotto possono essere venduti in una singola transazione.
- **Verifica scorte** - Quando il valore è impostato su **True**, un articolo viene aggiunto al carrello solo dopo che il modulo Casella acquisti verifica che è disponibile. La verifica delle scorte viene effettuata per gli scenari in cui l'articolo verrà spedito e per quelli in cui verrà prelevato presso il punto vendita. Se il valore è impostato su **False**, non viene eseguita alcuna verifica delle scorte prima di aggiungere un articolo al carrello e di effettuare l'ordine.
- **Buffer scorte** - Le scorte sono gestite in tempo reale e quando molti clienti effettuano ordini, può essere difficile mantenere un conteggio accurato delle stesse. Di conseguenza, un buffer può essere definito per le scorte. Quando viene eseguita una verifica delle scorte, se queste sono inferiori alla quantità buffer, il prodotto viene considerato come non disponibile. Pertanto, quando si verificano rapidamente delle vendite tramite vari canali e il conteggio delle scorte non è completamente sincronizzato, il rischio che un articolo non disponibile venga venduto è minore.

## <a name="retail-server-interaction"></a>Interazione con Retail Server

Il modulo Casella acquisti recupera le informazioni sul prodotto utilizzando le API di Retail Server. L'ID prodotto nella pagina dettagli prodotto è utilizzato per recuperare tutte le informazioni.

## <a name="add-a-buy-box-module-to-a-page"></a>Aggiungere un modulo Casella acquisti a una pagina

Per aggiungere un modulo Casella acquisti a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Creare un frammento denominato **Frammento casella acquisti** e aggiungervi un modulo Casella acquisti.
1. Aggiungere un modulo Galleria multimediale allo slot **Multimedia** del modulo Casella acquisti.
1. Nello slot **Contenuto** del modulo Casella acquisti, aggiungere i seguenti moduli: Titolo prodotto, Valutazione prodotto, Prezzo prodotto, Descrizione prodotto, Configurazione prodotto, Aggiungi al carrello, Aggiungi a elenco preferenze e Cerca nel punto vendita. È possibile ridisporre i moduli nello slot **Contenuto** per ottenere il layout desiderato.
1. Selezionare il modulo Cerca nel punto vendita. Nello slot in questo modulo, aggiungere un modulo Preleva nel punto vendita.
1. Nello slot del modulo Preleva nel punto vendita, aggiungere un modulo Ricerca punto vendita con Bing Maps.
1. Archiviare la pagina e pubblicarla.
1. Creare un modello per una pagina dettagli prodotto (PDP) e denominarlo **Modello PDP**.
1. Aggiungere una pagina predefinita.
1. Nello slot **Principale** della pagina predefinita, aggiungere un frammento casella acquisti.
1. Salvare il modello, archiviarlo e pubblicarlo.
1. Utilizzare il modello appena creato per creare una pagina denominata **Pagina PDP**.
1. Nello slot **Principale** della nuova pagina, aggiungere un frammento casella acquisti.
1. Salvare la pagina e visualizzarne l'anteprima. Aggiungere il parametro della stringa di query **?productid=&lt;product id&gt;** all'URL della pagina di anteprima. In tal modo, il contesto del prodotto è utilizzato per caricare ed eseguire il rendering della pagina di anteprima.
1. Archiviare la pagina e pubblicarla. Una casella acquisti deve essere visualizzata nella pagina dettagli prodotto.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo Carrello](add-cart-module.md)

[Modulo Checkout](add-checkout-module.md)

[Modulo Conferma ordine](order-confirmation-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)
