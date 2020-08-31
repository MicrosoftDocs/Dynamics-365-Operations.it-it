---
title: Modulo Casella acquisti
description: In questo argomento vengono descritti i moduli Casella acquisti e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 07/31/2020
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
ms.openlocfilehash: 3fe5c1eb5808ef778aeda29442fa884556671296
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686672"
---
# <a name="buy-box-module"></a>Modulo Casella acquisti

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

In questo argomento vengono descritti i moduli Casella acquisti e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Il termine *casella acquisti* si riferisce in genere all'area di una pagina dettagli prodotto che si trova "in primo piano" e che ospita le informazioni più importanti necessarie per effettuare un acquisto (un'area "in primo piano" è visibile quando la pagina viene caricata la prima volta, di modo che gli utenti non devono scorrere per vederla).

Un modulo Casella acquisti è un contenitore speciale utilizzato per l'hosting di tutti i moduli visualizzati nell'area Casella acquisti di una pagina dettagli prodotto.

L'URL di una pagina dettagli prodotto include l'ID prodotto. Tutte le informazioni necessarie per eseguire il rendering di un modulo Casella acquisti derivano da questo ID prodotto. Se un ID prodotto non viene fornito, il rendering del modulo Casella acquisti non verrà eseguito correttamente in una pagina. Pertanto, un modulo Casella acquisti può essere utilizzato solo in pagine con contesto del prodotto. Per utilizzarlo in una pagina senza contesto del prodotto (ad esempio, una home page o una pagina di marketing) è necessario eseguire ulteriori personalizzazioni.

L'immagine seguente mostra un esempio di modulo Casella acquisti in una pagina dettagli prodotto.

![Esempio di modulo Casella acquisti](./media/ecommerce-pdp-buybox.PNG)

## <a name="buy-box-module-properties-and-slots"></a>Proprietà e slot del modulo Casella acquisti 

In una pagina dettagli prodotto, una casella acquisti è suddivisa in due aree: un'area multimediale a sinistra e un'area contenuto a destra. Per impostazione predefinita, la proporzione in termini di larghezza delle colonne dell'area multimediale e dell'area contenuto è 2:1. Nei dispositivi mobili, le due are sono impilate, di modo che un'area appaia sotto l'altra. I temi possono essere utilizzati per personalizzare la larghezza delle colonne e la classificazione dello stack.

Un modulo Casella acquisti esegue il rendering di titolo, descrizione, prezzo e valutazioni di un prodotto. Consente inoltre ai clienti di selezionare varianti di prodotto con attributi di prodotto diversi, come dimensioni, stile e colore. Quando si seleziona una variante prodotto, altre proprietà nella casella acquisti (ad esempio la descrizione e le immagini del prodotto) vengono aggiornate per riflettere le informazioni relative alla variante. 

Viene fornito un selettore della quantità, di modo che i clienti possano specificare la quantità di articoli da acquistare. La quantità massima che può essere acquistata può essere definita nelle impostazioni del sito.

Dalla casella acquisti, i clienti possono anche eseguire azioni come aggiungere un prodotto al carrello, aggiungere un prodotto all'elenco preferenze e selezionare un luogo di ritiro. Queste azioni possono essere eseguite per un prodotto o una variante di prodotto. Per aggiungere un prodotto a un elenco preferenze, il cliente deve aver effettuato l'accesso.

I temi possono essere utilizzati per rimuovere o modificare l'ordine delle proprietà della casella acquisti e i controlli delle azioni. 

## <a name="module-properties"></a>Proprietà del modulo

- **Tag di intestazione** - Questa proprietà definisce il tag di intestazione per il titolo del prodotto. Se la casella acquisti si trova nella parte superiore della pagina, questa proprietà deve essere impostata su **h1** per soddisfare gli standard di accessibilità. 

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Moduli che è possibile utilizzare in un modulo Casella acquisti

- **Galleria multimediale** - Questo modulo viene utilizzato per visualizzare immagini di un prodotto in una pagina dettagli prodotto. Per ulteriori informazioni su questo modulo, vedere [Modulo Galleria multimediale](media-gallery-module.md).
- **Selettore punto vendita** - Questo modulo visualizza un elenco dei punti vendita vicini in cui un articolo è disponibile per il ritiro. Consente agli utenti di immettere un'ubicazione per trovare punti vendita nelle vicinanze. Per ulteriori informazioni su questo modulo, vedere [Modulo Selettore punto vendita](store-selector.md).

## <a name="buy-box-module-settings"></a>Impostazioni del modulo Casella acquisti

Le seguenti impostazioni relative al modulo Casella acquisti possono essere configurate in **Impostazioni sito \> Estensioni**:

- **Limite quantità voci carrello** - Questa proprietà viene utilizzata per specificare il numero massimo di pezzi di ogni articolo che possono essere aggiunti al carrello. Ad esempio, un rivenditore potrebbe decidere che solo 10 pezzi di ogni prodotto possono essere venduti in una singola transazione.
- **Scorte** - Per informazioni su come applicare le impostazioni relative alle scorte, vedere [Applicare le impostazioni relative alle scorte](inventory-settings.md).
- **Aggiungi al carrello** - Questa proprietà viene utilizzata per specificare il comportamento dopo l'aggiunta di un articolo al carrello. I valori possibili sono **Vai al carrello**, **Non andare al carrello** e **Mostra notifiche**. Quando il valore è impostato su **Vai al carrello**, gli utenti accedono alla pagina del carrello dopo aver aggiunto un articolo. Quando il valore è impostato su **Non andare al carrello**, gli utenti non accedono alla pagina del carrello dopo aver aggiunto un articolo. Quando il valore è impostato su **Mostra notifiche**, agli utenti viene mostrata una notifica di conferma e possono continuare a navigare nella pagina dettagli prodotto. 

    L'immagine seguente mostra un esempio di notifica di conferma "aggiunto al carrello" sul sito di Fabrikam.

    ![Esempio di modulo Notifica](./media/ecommerce-addtocart-notifications.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interazione con Commerce Scale Unit

Il modulo Casella acquisti recupera le informazioni sul prodotto utilizzando le API di Commerce Scale Unit. L'ID prodotto nella pagina dettagli prodotto è utilizzato per recuperare tutte le informazioni.

## <a name="add-a-buy-box-module-to-a-page"></a>Aggiungere un modulo Casella acquisti a una pagina

Per aggiungere un modulo Casella acquisti a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Frammenti** e selezionare **Nuovo** per creare un nuovo frammento.
1. Nella finestra di dialogo **Nuovo frammento pagina**, selezionare il modulo **Casella acquisti**.
1. In **Nome frammento pagina**, inserire il nome **Frammento casella acquisti**, quindi selezionare **OK**.
1. Nello slot **Galleria multimediale** del modulo Casella acquisti, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Galleria multimediale** e quindi selezionare **OK**.
1. Nello slot **Selettore punto vendita** del modulo Casella acquisti, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Selettore punto vendita** e quindi selezionare **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello PDP**, quindi selezionare **OK**.
1. Nello slot **Corpo** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Pagina predefinita** e quindi selezionare **OK**.
1. Nello slot **Principale** della pagina predefinita, selezionare il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi frammento pagina**.
1. Nella finestra di dialogo **Seleziona frammento pagina**, selezionare il frammento **Frammento casella acquisti** creato in precedenza, quindi selezionare **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Scegli un modello**, selezionare il modello **Modello PDP**. Sotto **Nome pagina**, Immettere **Pagina PDP** e selezionare **OK**.
1. Nello slot **Principale** della nuova pagina, selezionare il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi frammento pagina**.
1. Nella finestra di dialogo **Seleziona frammento pagina**, selezionare il frammento **Frammento casella acquisti** creato in precedenza, quindi selezionare **OK**.
1. Salvare la pagina e visualizzarne l'anteprima. Aggiungere il parametro della stringa di query **?productid=&lt;product id&gt;** all'URL della pagina di anteprima. In tal modo, il contesto del prodotto è utilizzato per caricare ed eseguire il rendering della pagina di anteprima.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla. Una casella acquisti deve essere visualizzata nella pagina dettagli prodotto.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Memorizzare il modulo di selezione](store-selector.md)

[Modulo Galleria multimediale](media-gallery-module.md)

[Modulo contenitore](add-container-module.md)

[Modulo carrello](add-cart-module.md)

[Modulo icona carrello](cart-icon-module.md)

[Modulo checkout](add-checkout-module.md)

[Modulo Conferma ordine](order-confirmation-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)

[Calcolare la disponibilità scorte per i canali di vendita al dettaglio](calculated-inventory-retail-channels.md)
