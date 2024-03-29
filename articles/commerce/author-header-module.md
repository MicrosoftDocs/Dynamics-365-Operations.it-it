---
title: Modulo intestazione
description: In questo articolo vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 63c298f36f64f2e107d3df3c0c5f3b6445546aa1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275787"
---
# <a name="header-module"></a>Modulo intestazione

[!include [banner](includes/banner.md)]

In questo articolo vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.

In Dynamics 365 Commerce, un'intestazione di pagina è configurata come un frammento di pagina che include l'intestazione, il banner promozionale e i moduli di consenso dei cookie. 

Il modulo intestazione include il logo di un sito, collegamenti alla gerarchia di navigazione, collegamenti ad altre pagine del sito, il modulo dell'icona del carrello, il simbolo dell'elenco preferenze, opzioni di accesso e la barra di ricerca. Un modulo Intestazione viene automaticamente ottimizzato per il dispositivo sul quale viene visualizzato il sito (in altre parole un dispositivo desktop o un dispositivo mobile). Ad esempio, in un dispositivo mobile, la barra di navigazione è compressa in un pulsante **Menu** (a volte definito *menu hamburger*).

L'immagine seguente mostra un esempio di modulo Intestazione in una home page.

![Esempio di modulo Intestazione.](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a>Proprietà di un modulo Intestazione

Un modulo Intestazione supporta le proprietà **Immagine logo**, **Collegamento logo** e **Collegamenti account personale**. 

Le proprietà **Immagine logo** e **Collegamento logo** vengono utilizzate per definire un logo nella pagina. Per ulteriori informazioni, vedere [Aggiungere un logo](add-logo.md). 

La proprietà **Collegamenti account personale** può essere utilizzata per definire pagine dell'account per le quali il proprietario del sito desidera visualizzare collegamenti rapidi nell'intestazione.

## <a name="modules-that-are-available-within-a-header-module"></a>Moduli disponibili in un modulo intestazione

Di seguito sono elencati i moduli che possono essere utilizzati in un modulo Intestazione:

- **Menu di navigazione** - Il menu di navigazione rappresenta la gerarchia di navigazione del canale e altri collegamenti di navigazione statici. Per ulteriori informazioni, vedere [Modulo menu di spostamento](nav-menu-module.md).

- **Ricerca** - Il modulo Ricerca consente agli utenti di immettere termini di ricerca per cercare prodotti. L'URL della pagina di ricerca predefinita e i parametri della query di ricerca devono essere specificati in **Impostazioni sito \> Estensioni**. Il modulo Ricerca ha proprietà che consentono di sopprimere il pulsante o l'etichetta di ricerca. Il modulo Ricerca supporta anche opzioni di suggerimento automatico, come risultati di ricerca di prodotti, parola chiave e categorie.

- **Icona del carrello** - Il modulo Icona carrello rappresenta l'icona del carrello, che mostra in qualsiasi momento il numero di articoli presenti nel carrello. Per ulteriori informazioni, vedere [Modulo Icona carrello](cart-icon-module.md).

- **Selettore sito** - Il modulo di selezione sito consente agli utenti di spostarsi in diversi siti predefiniti, in base al mercato, alle regioni e alle impostazioni locali. Per ulteriori informazioni, vedere [Modulo Selettore sito](site-selector.md).

- **Selettore punto vendita** - Il modulo di selezione punto vendita può essere incluso nello slot di selezione del punto vendita del modulo di intestazione. Consente agli utenti di spostarsi e trovare i punti vendita nelle vicinanze. Gli utenti possono anche specificare un punto vendita preferito. Quel punto vendita verrà quindi mostrato nell'intestazione. Quando il modulo di selezione punto vendita è incluso nel modulo di intestazione, la proprietà **Modalità** deve essere impostata su **Trova punti vendita**. Per ulteriori informazioni, vedere [Modulo Selettore punto vendita](store-selector.md).

> [!NOTE]
> - Il supporto per l'utilizzo del modulo dell'icona del carrello nei moduli di intestazione è disponibile a partire da Dynamics 365 Commerce, versione 10.0.11.
> - Il supporto per l'utilizzo del modulo di selezione sito nei moduli di intestazione è disponibile a partire da Dynamics 365 Commerce, versione 10.0.14.
> - Il supporto per l'utilizzo del modulo di selezione del punto vendita nei moduli di intestazione è disponibile a partire da Dynamics 365 Commerce, versione 10.0.15.

## <a name="header-module-in-the-adventure-works-theme"></a>Modulo di intestazione nel tema Adventure Works

Nel tema Adventure Works il modulo di intestazione supporta la proprietà **Logo mobile**. Questa proprietà consente di specificare un logo per i riquadri di visualizzazione dei dispositivi mobili. La proprietà **Logo mobile** è disponibile come estensione della definizione del modulo.

> [!IMPORTANT]
> Il tema Adventure Works è disponibile a partire dalla versione Dynamics 365 Commerce 10.0.20.

## <a name="create-a-header-fragment-for-a-page"></a>Creare un frammento Intestazione per una pagina

Per creare un frammento Intestazione, procedere come segue.

1. Andare a **Frammenti** e selezionare **Nuovo** per creare un nuovo frammento.
1. Nella finestra di dialogo **Seleziona un frammento**, seleziona il modulo **Contenitore**, immetti un nome per il frammento e seleziona **OK**.
1. Selezionare lo slot **Contenitore predefinito** e nel riquadro delle proprietà a destra, impostare la proprietà **Larghezza** su **Riempi schermo**.
1. Nello slot **Contenitore predefinito** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona i moduli **Consenso per i cookie**, **Intestazione** e **Banner promozionale**, quindi seleziona **OK**.
1. Nel riquadro delle proprietà del modulo **Banner promozionale** selezionare **Aggiungi messaggio** e quindi **Messaggio** .
1. Nella finestra di dialogo **Messaggio**, aggiungere il testo e i collegamenti per il contenuto promozionale e selezionare **OK**.
1. Nel riquadro delle proprietà del modulo **Consenso per i cookie** aggiungere e configurare il testo e un collegamento alla pagina della privacy del sito.
1. Nello slot **Menu di navigazione** del modulo Intestazione, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli**, seleziona il modulo **Menu di navigazione** e quindi **OK**.
1. Nel riquadro delle proprietà per il modulo del menu di spostamento, sotto **Origine menu di spostamento**, selezionare **Retail Server** .
1. Nel riquadro delle proprietà per il modulo del menu di spostamento, sotto **Voci di menu statiche** selezionare **Aggiungi voce di menu** e quindi selezionare **Voce di menu** . 
1. Nella finestra di dialogo **Voce di menu**, sotto **Testo voce di menu** inserire "Contatto".
1. Nella finestra di dialogo **Voce di menu**, sotto **Destinazione collegamento voce di menu** selezionare **Aggiungi un collegamento** .
1. Nella finestra di dialogo **Aggiungi un collegamento**, selezionare l'URL per la pagina "Contatti" del sito, quindi selezionare **OK**.  
1. Nella finestra di dialogo **Voce di menu** selezionare **OK**.
1. Nello slot **Ricerca** del modulo Intestazione, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Ricerca** e quindi **OK**.
1. Nel riquadro delle proprietà per il modulo Ricerca, configurare le proprietà come necessario.
1. Nello slot **Icona carrello** del modulo Intestazione, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Icona carrello** e quindi **OK**.
1. Nel riquadro delle proprietà per il modulo Icona carrello, configurare le proprietà come necessario. Se l'icona del carrello deve visualizzare un riepilogo del carrello (noto anche come mini carrello) quando il puntatore del mouse si trova sull'icona, selezionare **Mostra mini carrello**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.

Per assicurare che un'intestazione sia visualizzata in ogni pagina, effettuare le seguenti operazioni in ogni modello di pagina creato per il sito.

1. Nello slot **Intestazione** del modulo **Pagina predefinita**, aggiungere il frammento piè di pagina creato.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo icona carrello](cart-icon-module.md)

[Modulo banner promozionale](add-alert.md)

[Modulo menu di spostamento](nav-menu-module.md) 

[Consenso cookie](cookie-consent-module.md)

[Modulo piè di pagina](author-footer-module.md)

[Modulo di selezione sito](site-selector.md)

[Memorizzare il modulo di selezione](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
