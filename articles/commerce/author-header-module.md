---
title: Modulo Intestazione
description: In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 99457b2c98eae0ddd898f852630d690140a5a4c5
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817012"
---
# <a name="header-module"></a>Modulo Intestazione

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

In Dynamics 365 Commerce, un'intestazione di pagina è configurata come un frammento di pagina che include l'intestazione, il banner promozionale e i moduli di consenso dei cookie. 

Il modulo intestazione include il logo di un sito, collegamenti alla gerarchia di navigazione, collegamenti ad altre pagine del sito, il modulo dell'icona del carrello, il simbolo dell'elenco preferenze, opzioni di accesso e la barra di ricerca. Un modulo Intestazione viene automaticamente ottimizzato per il dispositivo sul quale viene visualizzato il sito (in altre parole un dispositivo desktop o un dispositivo mobile). Ad esempio, in un dispositivo mobile, la barra di navigazione è compressa in un pulsante **Menu** (a volte definito *menu hamburger*).

L'immagine seguente mostra un esempio di modulo Intestazione in una home page.

![Esempio di modulo Intestazione](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a>Proprietà di un modulo Intestazione

Un modulo Intestazione supporta le proprietà **Immagine logo**, **Collegamento logo** e **Collegamenti account personale**. 

Le proprietà **Immagine logo** e **Collegamento logo** vengono utilizzate per definire un logo nella pagina. Per ulteriori informazioni, vedere [Aggiungere un logo](add-logo.md). 

La proprietà **Collegamenti account personale** può essere utilizzata per definire pagine dell'account per le quali il proprietario del sito desidera visualizzare collegamenti rapidi nell'intestazione.

## <a name="modules-that-are-available-within-a-header-module"></a>Moduli disponibili in un modulo intestazione

Di seguito sono elencati i moduli che possono essere utilizzati in un modulo Intestazione:

- **Menu di navigazione** - Il menu di navigazione rappresenta la gerarchia di navigazione del canale e altri collegamenti di navigazione statici. Per ulteriori informazioni, vedere [Modulo menu di spostamento](nav-menu-module.md).

- **Ricerca** - Il modulo Ricerca consente agli utenti di immettere termini di ricerca per cercare prodotti. L'URL della pagina di ricerca predefinita e i parametri della query di ricerca devono essere specificati in **Impostazioni sito \> Estensioni**. Il modulo Ricerca ha proprietà che consentono di sopprimere il pulsante o l'etichetta di ricerca. Il modulo Ricerca supporta anche opzioni di suggerimento automatico, come risultati di ricerca di prodotti, parola chiave e categorie.

- **Icona del carrello** - Il modulo Icona carrello rappresenta l'icona del carrello, che mostra in qualsiasi momento il numero di articoli presenti nel carrello. Per ulteriori informazioni, vedere [Modulo Icona carrello](cart-icon-module.md).

## <a name="create-a-header-fragment-for-a-page"></a>Creare un frammento Intestazione per una pagina

Per creare un frammento Intestazione, procedere come segue.

1. Andare a **Frammenti** e selezionare **Nuovo** per creare un nuovo frammento.
1. Nella finestra di dialogo **Nuovo frammento**, selezionare il modulo **Contenitore**, immettere un nome per il frammento e selezionare **OK**.
1. Selezionare lo slot **Contenitore predefinito** e nel riquadro delle proprietà a destra, impostare la proprietà **Larghezza** su **Riempi schermo**.
1. Nello slot **Contenitore predefinito** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare i moduli **Consenso per i cookie**, **Intestazione** e **Banner promozionale**, quindi selezionare **OK**.
1. Nel riquadro delle proprietà del modulo **Banner promozionale** selezionare **Aggiungi messaggio** e quindi **Messaggio** .
1. Nella finestra di dialogo **Messaggio**, aggiungere il testo e i collegamenti per il contenuto promozionale e selezionare **OK**.
1. Nel riquadro delle proprietà del modulo **Consenso per i cookie** aggiungere e configurare il testo e un collegamento alla pagina della privacy del sito.
1. Nello slot **Menu di navigazione** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Menu di navigazione** e quindi **OK**.
1. Nel riquadro delle proprietà per il modulo del menu di spostamento, sotto **Origine menu di spostamento**, selezionare **Retail Server** .
1. Nel riquadro delle proprietà per il modulo del menu di spostamento, sotto **Voci di menu statiche** selezionare **Aggiungi voce di menu** e quindi selezionare **Voce di menu** . 
1. Nella finestra di dialogo **Voce di menu**, sotto **Testo voce di menu** inserire "Contatto".
1. Nella finestra di dialogo **Voce di menu**, sotto **Destinazione collegamento voce di menu** selezionare **Aggiungi un collegamento** .
1. Nella finestra di dialogo **Aggiungi un collegamento**, selezionare l'URL per la pagina "Contatti" del sito, quindi selezionare **OK**.  
1. Nella finestra di dialogo **Voce di menu** selezionare **OK**.
1. Nello slot **Ricerca** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Ricerca** e quindi **OK**.
1. Nel riquadro delle proprietà per il modulo Ricerca, configurare le proprietà come necessario.
1. Nello slot **Icona carrello** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Icona carrello** e quindi **OK**.
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
