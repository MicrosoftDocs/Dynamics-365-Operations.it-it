---
title: Modulo Intestazione
description: In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 05/28/2020
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a5f7ad7d9c5ff63c3c3a8fe38275eec0d138891d
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411214"
---
# <a name="header-module"></a>Modulo Intestazione

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

In Dynamics 365 Commerce, un'intestazione di pagina comprende più moduli, come i moduli Intestazione, Menu di navigazione, Ricerca, Banner promozionale e Consenso per i cookie. 

Il modulo Intestazione include il logo di un sito, collegamenti alla gerarchia di navigazione, collegamenti ad altre pagine del sito, il simbolo del carrello, il simbolo dell'elenco preferenze, opzioni di accesso e la barra di ricerca. Un modulo Intestazione viene automaticamente ottimizzato per il dispositivo sul quale viene visualizzato il sito (in altre parole un dispositivo desktop o un dispositivo mobile). Ad esempio, in un dispositivo mobile, la barra di navigazione è compressa in un pulsante **Menu** (a volte definito *menu hamburger*).

L'immagine seguente mostra un esempio di modulo Intestazione in una home page.

![Esempio di modulo Intestazione](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a>Proprietà di un modulo Intestazione

Un modulo Intestazione supporta le proprietà **Immagine logo**, **Collegamento logo** e **Collegamenti account personale**. 

Le proprietà **Immagine logo** e **Collegamento logo** vengono utilizzate per definire un logo nella pagina. Per ulteriori informazioni, vedere [Aggiungere un logo](add-logo.md). 

La proprietà **Collegamenti account personale** può essere utilizzata per definire pagine dell'account per le quali il proprietario del sito desidera visualizzare collegamenti rapidi nell'intestazione.

## <a name="modules-that-are-available-in-a-header-module"></a>Moduli disponibili in un modulo Intestazione

Di seguito sono elencati i moduli che possono essere utilizzati in un modulo Intestazione:

- **Menu di navigazione** - Il menu di navigazione rappresenta la gerarchia di navigazione del canale e altri collegamenti di navigazione statici. La gerarchia di navigazione del canale può essere configurata in Dynamics 365 Commerce. Il menu di navigazione presenta una proprietà **Origine navigazione** utilizzata per specificare le voci di menu di navigazione di Retail Server e le voci di menu statico come origine. Se le voci di menu statico vengono specificate come origine, è possibile fornire collegamenti relativi ad altre pagine del sito. Gli elementi configurati vengono quindi visualizzati come navigazione intestazione. 

- **Ricerca** - Il modulo Ricerca consente agli utenti di immettere termini di ricerca per cercare prodotti. L'URL della pagina di ricerca predefinita e i parametri della query di ricerca devono essere specificati in **Impostazioni sito \> Estensioni**. Il modulo Ricerca ha proprietà che consentono di sopprimere il pulsante o l'etichetta di ricerca. Il modulo Ricerca supporta anche opzioni di suggerimento automatico, come risultati di ricerca di prodotti, parola chiave e categorie.

- **Icona del carrello** - Il modulo Icona carrello rappresenta l'icona del carrello, che mostra in qualsiasi momento il numero di articoli presenti nel carrello. Per ulteriori informazioni, vedere [Modulo Icona carrello](cart-icon-module.md).

## <a name="create-a-header-module-for-a-page"></a>Creare un modulo Intestazione per una pagina

Per creare un modulo Intestazione, procedere come segue.

1. Andare a **Frammenti pagina** e selezionare **Nuovo** per creare un nuovo frammento.
1. Nella finestra di dialogo **Nuovo frammento pagina**, selezionare il modulo **Contenitore**, immettere un nome per il frammento e selezionare **OK**.
1. Selezionare lo slot **Contenitore predefinito** e nel riquadro delle proprietà a destra, impostare la proprietà **Larghezza** su **Riempi contenitore**.
1. Nello slot **Contenitore predefinito** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare i moduli **Banner promozionale** e **Consenso per i cookie**, quindi selezionare **OK**.
1. Nello slot **Contenitore predefinito** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.
1. Selezionare lo slot **Contenitore** e nel riquadro delle proprietà a destra, impostare la proprietà **Larghezza** su **Riempi contenitore**.
1. Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Intestazione** e quindi **OK**.
1. Nello slot **Menu di navigazione** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Menu di navigazione** e quindi **OK**.
1. Nel riquadro delle proprietà per il modulo Menu di navigazione, configurare le proprietà come necessario.
1. Nello slot **Ricerca** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Ricerca** e quindi **OK**.
1. Nel riquadro delle proprietà per il modulo Ricerca, configurare le proprietà come necessario.
1. Nello slot **Icona carrello** del modulo Intestazione, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Icona carrello** e quindi **OK**.
1. Nel riquadro delle proprietà per il modulo Icona carrello, configurare le proprietà come necessario. Se l'icona del carrello deve visualizzare un riepilogo del carrello (noto anche come mini carrello) quando il puntatore del mouse si trova sull'icona, selezionare **Mostra mini carrello**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.

Per garantire che un'intestazione sia visualizzata in ogni pagina, effettuare le seguenti operazioni in ogni modello di pagina creato per il sito.

1. Nello slot **Intestazione** del modulo **Pagina predefinita**, aggiungere il frammento piè di pagina creato.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo Contenitore](add-container-module.md)

[Modulo Casella acquisti](add-buy-box.md)

[Modulo Carrello](add-cart-module.md)

[Modulo Icona carrello](cart-icon-module.md)

[Modulo Checkout](add-checkout-module.md)

[Modulo Conferma ordine](order-confirmation-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)
