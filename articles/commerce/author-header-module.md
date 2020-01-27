---
title: Modulo Intestazione
description: In questo argomento vengono descritti i moduli Intestazione e la procedura per crearli in Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: cc98419077f6f563ea2265d4e68ba809971cfbd6
ms.sourcegitcommit: ff93b8f6a11993f2cd00be2da7aa77ef0d950ab8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885480"
---
# <a name="header-module"></a>Modulo intestazione

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Intestazione e la procedura per crearli in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo Intestazione è un contenitore speciale utilizzato per l'hosting di tutti i moduli che verranno visualizzati nell'intestazione di una pagina. Ad esempio, può includere il logo del sito, collegamenti alla gerarchia di navigazione, collegamenti ad altre pagine del sito e la barra di ricerca.

Un modulo Intestazione viene automaticamente ottimizzato per il dispositivo sul quale viene visualizzato il sito (ovvero un dispositivo desktop o un dispositivo mobile). Ad esempio, in un dispositivo mobile, la barra di navigazione è compressa in un pulsante **Menu** (a volte definito *menu hamburger*).

## <a name="properties-of-a-header"></a>Proprietà di un'intestazione

Come i contenitori generici, un modulo Intestazione supporta le proprietà **intestazione** e **larghezza**.

Un modulo Intestazione ha molteplici slot. Ad esempio, sono presenti slot per un messaggio informativo, un menu di navigazione, il logo, una barra di ricerca, l'icona del carrello, l'icona dell'elenco preferenze e informazioni sull'account. Ogni slot supporta uno specifico set di moduli.

## <a name="modules-that-are-available-in-a-header-module"></a>Moduli disponibili in un modulo Intestazione

Di seguito sono elencati i moduli che possono essere utilizzati in un modulo Intestazione:

- **Menu di navigazione** - Il menu di navigazione rappresenta la gerarchia di navigazione del canale e altri collegamenti di navigazione statici. La gerarchia di navigazione del canale può essere configurata in Dynamics 365 Retail. Gli elementi configurati vengono quindi visualizzati come navigazione intestazione. Inoltre, è possibile configurare i collegamenti di navigazione statici e possono essere forniti i collegamenti ad altre pagine nel sito di e-Commerce. L'intestazione stessa può essere allineata a sinistra, a destra o al centro.
- **Icona del carrello** - L'icona del carrello è un'icona speciale che rappresenta il carrello. È visualizzata nell'intestazione e indica il numero di articoli nel carrello. Un collegamento alla pagina carrello deve accompagnare l'icona del carrello, di modo che i clienti possano essere reindirizzati alla pagina carrello quando interagiscono con l'icona.
- **Icona dell'elenco preferenze** - L'icona dell'elenco preferenze è visualizzata nell'intestazione e indica il numero di articoli aggiunti all'elenco preferenze del cliente. Un collegamento alla pagina dell'elenco preferenze deve accompagnare questa icona, di modo che i clienti possano essere reindirizzati alla pagina dell'elenco preferenze quando interagiscono con l'icona.
- **Modulo Accesso** - Il modulo Accesso è visualizzato nell'intestazione. Consente ai clienti di accedere al proprio account o di registrarsi per averne uno. Se il cliente è già registrato, il modulo può essere configurato per visualizzare collegamenti alla pagina dell'account, alla pagina dello storico ordini o a un'altra pagina.
- **Modulo Logo** - Questo modulo mostra il logo che rappresenta il rivenditore e il marchio. È un'immagine con un collegamento. Il collegamento è in genere configurato di modo che reindirizzi alla home page. Di conseguenza, i clienti possono tornare rapidamente alla home page da qualsiasi pagina del sito.
- **Avviso** - Un avviso viene visualizzato nell'intestazione ed è utilizzato per visualizzare un messaggio inline valido per tutte le pagine del sito. Ad esempio, un avviso può visualizzare un messaggio come "La vendita annuale termina tra 2 giorni".
- **Barra di ricerca** - La barra di ricerca consente agli utenti di immettere i termini di ricerca per cercare i prodotti. Il modulo deve essere configurato con l'URL della pagina dei risultati della ricerca. Il parametro della stringa di query può essere configurato (il valore predefinito è **"q"**). La barra di ricerca ha uno slot di suggerimento automatico in cui deve essere aggiunto il modulo Suggerimento automatico.
- **Suggerimento automatico** - Il modulo Suggerimento automatico visualizza i risultati suggeriti automaticamente. Questi risultati possono essere parole chiave, prodotti o categorie in cui viene trovato il termine di ricerca.

## <a name="create-a-header-module"></a>Creare un modulo Intestazione

Per creare un modulo Intestazione, procedere come segue.

1. Creare un frammento pagina che include un modulo Intestazione.
1. Aggiungere moduli agli slot nel modulo Intestazione.
1. Aggiornare le impostazioni di ciascun modulo.
1. Salvare il frammento pagina. 
1. Archiviare la pagina e pubblicarla.

Per garantire che un'intestazione sia visualizzata in ogni pagina, effettuare le seguenti operazioni in ogni modello di pagina creato per il sito.

1. Nella pagina predefinita, aggiungere il frammento pagina contenente il modulo Intestazione all'intestazione nello slot principale.
1. Salvare il modello. 
1. Archiviare il modello e pubblicarlo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo Casella acquisti](add-buy-box.md)

[Modulo Carrello](add-cart-module.md)

[Modulo Checkout](add-checkout-module.md)

[Modulo Conferma ordine](order-confirmation-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)
