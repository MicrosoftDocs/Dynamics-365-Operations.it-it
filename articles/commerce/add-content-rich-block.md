---
title: Modulo Blocco di testo
description: In questo argomento vengono descritti i moduli Blocco di testo e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7dbeb8785641960cc2680335436aea10775759d3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797769"
---
# <a name="text-block-module"></a>Modulo blocco testo

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Blocco di testo e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

Un modulo Blocco di testo è un modulo utilizzato per aggiungere contenuto testuale. Questo contenuto può essere informativo o promozionale.

I moduli Blocco di testo sono basati sui dati del sistema di gestione dei contenuti e possono essere utilizzati in qualsiasi pagina. Sono moduli autonomi che non dipendono dal contesto della pagina o da qualsiasi altro modulo.

## <a name="examples-of-text-block-modules-in-e-commerce"></a>Esempi di moduli Blocco di testo in e-Commerce

I moduli Blocco di testo possono essere utilizzati nei seguenti modi:

* Per visualizzare caratteristiche dei prodotti in una pagina dettagli prodotto.
* Per scopi informativi in qualsiasi pagina. Ad esempio, possono spiegare i vantaggi dei programmi fedeltà, descrivere le condizioni di spedizione e reso, rispondere alle domande frequenti oppure fornire contenuto "chi siamo".
* Per aggiungere messaggi personalizzati in una pagina dettagli prodotto (ad esempio, "Spedizione gratuita per ordini superiori a 50 €").
* Per le dichiarazioni di non responsabilità e le informazioni di contatto nelle pagine dettagli prodotto, carrello, checkout e altre pagine (ad esempio "Spedizioni e resi sono soggetti alle politiche del punto vendita").

L'immagine seguente mostra un esempio di modulo Blocco di testo utilizzato in una home page.

![Esempio di un modulo Blocco di testo](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a>Proprietà dei moduli Blocco di testo

| Nome proprietà     | Valore                                            | Descrizione |
|-------------------|--------------------------------------------------|-------------|
| RTF         | RTF                                        | Testo di paragrafo. Alcune funzionalità RTF di base sono supportate, ad esempio testo in grassetto, sottolineato e in corsivo. |
| Nome classe personalizzato | Il nome di una classe Cascading Style Sheets (CSS)        | Il nome di una classe CSS personalizzata fornita da uno sviluppatore per formattare questo modulo. Il nome della classe deve essere definito nel pacchetto di temi. |
| Dimensione carattere         | **Piccolo**, **Medio**, **Grande** o **Grandissimo** | La dimensione del carattere del contenuto. |

## <a name="add-a-text-block-module-to-a-page"></a>Aggiungere un modulo Blocco di testo a una pagina

Per aggiungere un modulo Blocco di testo a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello contenuto**.
1. Nello slot **Corpo** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Pagina predefinita** e quindi selezionare **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Scegli un modello**, selezionare **Modello contenuto**. Sotto **Nome pagina**, Immettere **Pagina contenuto** e selezionare **OK**.
1. Nello slot **Principale** della nuova pagina, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo Contenitore, impostare la proprietà **Larghezza** su **Riempi contenitore**.
1. Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Blocco di testo** e quindi selezionare **OK**. 
1. Nel riquadro delle proprietà del modulo Blocco di testo, aggiungere testo al campo **RTF**.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo banner promozionale](add-alert.md)

[Modulo sequenza](add-carousel.md)

[Modulo blocco contenuto](add-hero-module.md)

[Modulo Lettore video](add-video-player.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]