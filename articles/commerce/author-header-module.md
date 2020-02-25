---
title: Modulo Intestazione
description: In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: efadd19681bbb21ea5b2b469e55bc6f4b0535046
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025669"
---
# <a name="header-module"></a>Modulo intestazione


[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Intestazione e la procedura per creare intestazioni di pagina in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

In Dynamics 365 Commerce, un'intestazione di pagina comprende più moduli, come i moduli intestazione, menu di navigazione, ricerca, banner promozionale e consenso per i cookie. 

Il modulo intestazione include il logo di un sito, collegamenti alla gerarchia di navigazione, collegamenti ad altre pagine del sito, il simbolo del carrello, il simbolo dell'elenco preferenze, opzioni di accesso e la barra di ricerca. Un modulo Intestazione viene automaticamente ottimizzato per il dispositivo sul quale viene visualizzato il sito (in altre parole un dispositivo desktop o un dispositivo mobile). Ad esempio, in un dispositivo mobile, la barra di navigazione è compressa in un pulsante **Menu** (a volte definito *menu hamburger*).

## <a name="properties-of-a-header-module"></a>Proprietà di un modulo intestazione

Un modulo intestazione supporta le proprietà **Immagine logo**, **Collegamento logo** e **Collegamenti account personale**. 

Le proprietà **Immagine logo** e **Collegamento logo** vengono utilizzate per definire un logo nella pagina. Per ulteriori informazioni, vedere [Aggiungere un logo](add-logo.md). 

La proprietà **Collegamenti account personale** può essere utilizzata per definire pagine dell'account per le quali il proprietario del sito desidera visualizzare collegamenti rapidi nell'intestazione.

## <a name="modules-that-are-available-in-a-header-module"></a>Moduli disponibili in un modulo Intestazione

Di seguito sono elencati i moduli che possono essere utilizzati in un modulo Intestazione:

- **Menu di navigazione** - Il menu di navigazione rappresenta la gerarchia di navigazione del canale e altri collegamenti di navigazione statici. La gerarchia di navigazione del canale può essere configurata in Dynamics 365 Commerce. Il menu di navigazione presenta una proprietà **Origine navigazione** utilizzata per specificare le voci di menu di navigazione di Retail Server e le voci di menu statico come origine. Se le voci di menu statico vengono specificate come origine, è possibile fornire collegamenti relativi ad altre pagine del sito. Gli elementi configurati vengono quindi visualizzati come navigazione intestazione. 
- **Cerca** - Il modulo Ricerca consente agli utenti di immettere termini di ricerca per cercare prodotti. L'URL della pagina di ricerca predefinita e i parametri della query di ricerca devono essere specificati in **Impostazioni sito \> Estensioni**. Il modulo Ricerca ha proprietà che consentono di sopprimere il pulsante o l'etichetta di ricerca. Il modulo Ricerca supporta anche opzioni di suggerimento automatico, come risultati di ricerca di prodotti, parola chiave e categorie.

## <a name="create-a-header-module-for-a-page"></a>Creare un modulo intestazione per una pagina

Per creare un modulo Intestazione, procedere come segue.

1. Creare un frammento denominato **Frammento intestazione** e aggiungervi un modulo contenitore.
1. Nel riquadro delle proprietà del modulo contenitore, impostare la proprietà **Larghezza** su **Riempi contenitore**.
1. Aggiungere i moduli banner e consenso per i cookie al modulo contenitore.
1. Aggiungere un altro modulo contenitore al frammento e impostare la proprietà **Larghezza** su **Riempi contenitore**.
1. Aggiungere un modulo intestazione al secondo modulo contenitore.
1. Nello slot **Menu di navigazione** del modulo intestazione, aggiungere un modulo menu di navigazione. 
1. Nel riquadro delle proprietà per il modulo menu di navigazione, configurare le proprietà del modulo menu di navigazione.
1. Nello slot **Cerca** del modulo intestazione, aggiungere un modulo ricerca. 
1. Nel riquadro delle proprietà per il modulo ricerca, configurare le proprietà del modulo ricerca. 
1. Salvare il frammento di pagina, finalizzare la modifica e pubblicarlo. 

Per garantire che un'intestazione sia visualizzata in ogni pagina, effettuare le seguenti operazioni in ogni modello di pagina creato per il sito.

1. Nello slot **Principale** della pagina predefinita, aggiungere il frammento di pagina intestazione contenente il modulo Intestazione all'intestazione.
1. Salvare il modello, finalizzare la modifica e pubblicarlo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo Casella acquisti](add-buy-box.md)

[Modulo Carrello](add-cart-module.md)

[Modulo Checkout](add-checkout-module.md)

[Modulo Conferma ordine](order-confirmation-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)
