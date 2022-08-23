---
title: Modulo blocco testo
description: In questo articolo vengono descritti i moduli Blocco di testo e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 9e422c203d719b2e46620ce50b9d029e7ebd8d4c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270484"
---
# <a name="text-block-module"></a>Modulo blocco testo

[!include [banner](includes/banner.md)]

In questo articolo vengono descritti i moduli Blocco di testo e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

Un modulo Blocco di testo è un modulo utilizzato per aggiungere contenuto testuale. Questo contenuto può essere informativo o promozionale.

I moduli Blocco di testo sono basati sui dati del sistema di gestione dei contenuti e possono essere utilizzati in qualsiasi pagina. Sono moduli autonomi che non dipendono dal contesto della pagina o da qualsiasi altro modulo.

## <a name="examples-of-text-block-modules-in-e-commerce"></a>Esempi di moduli Blocco di testo in e-Commerce

I moduli Blocco di testo possono essere utilizzati nei seguenti modi:

* Per visualizzare caratteristiche dei prodotti in una pagina dettagli prodotto.
* Per scopi informativi in qualsiasi pagina. Ad esempio, possono spiegare i vantaggi dei programmi fedeltà, descrivere le condizioni di spedizione e reso, rispondere alle domande frequenti oppure fornire contenuto "chi siamo".
* Per aggiungere messaggi personalizzati in una pagina dettagli prodotto (ad esempio, "Spedizione gratuita per ordini superiori a 50 €").
* Per le dichiarazioni di non responsabilità e le informazioni di contatto nelle pagine dettagli prodotto, carrello, checkout e altre pagine (ad esempio "Spedizioni e resi sono soggetti alle politiche del punto vendita").

L'immagine seguente mostra un esempio di modulo Blocco di testo utilizzato in una home page.

![Esempio di un modulo Blocco di testo.](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a>Proprietà dei moduli Blocco di testo

| Nome proprietà     | Valore                                            | descrizione |
|-------------------|--------------------------------------------------|-------------|
| RTF         | RTF                                        | Testo di paragrafo. Alcune funzionalità RTF di base sono supportate, ad esempio testo in grassetto, sottolineato e in corsivo. |
| Nome classe personalizzato | Il nome di una classe Cascading Style Sheets (CSS)        | Il nome di una classe CSS personalizzata fornita da uno sviluppatore per formattare questo modulo. Il nome della classe deve essere definito nel pacchetto di temi. |
| Dimensione carattere         | **Piccolo**, **Medio**, **Grande** o **Grandissimo** | La dimensione del carattere del contenuto. |

## <a name="add-a-text-block-module-to-a-page"></a>Aggiungere un modulo Blocco di testo a una pagina

Per aggiungere un modulo Blocco di testo a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immetti **Modello contenuto**.
1. Nello slot **Corpo** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Pagina predefinita** e quindi seleziona **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Accedi a **Pagine** e quindi seleziona **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Crea una nuova pagina**, sotto **Nome pagina**, immetti **Pagina contenuto**, quindi seleziona **Avanti**.
1. In **Scegli un modello**, seleziona **Modello contenuto**, e seleziona **Avanti**.
1. Sotto **Scegli un layout**, seleziona un layout di pagina (ad esempio, **Layout flessibile**), quindi seleziona **Avanti**.
1. Sotto **Verifica e termina**, rivedi la configurazione della pagina. Se è necessario modificare le informazioni sulla pagina, seleziona **Indietro**. Se le informazioni sulla pagina sono corrette, seleziona **Crea pagina**. 
1. Nello slot **Principale** della nuova pagina, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo Contenitore, impostare la proprietà **Larghezza** su **Riempi contenitore**.
1. Nello slot **Contenitore** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Blocco testo** e quindi **OK**. 
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
