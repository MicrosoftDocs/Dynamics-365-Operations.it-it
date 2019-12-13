---
title: Modulo Piè di pagina
description: In questo argomento vengono descritti i moduli Piè di pagina e la procedura per crearli in Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7c253cd9620180b09f2f5cae232e46d236deabdd
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697315"
---
# <a name="footer-module"></a>Modulo Piè di pagina  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Piè di pagina e la procedura per crearli in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Il modulo Piè di pagina è un contenitore speciale utilizzato per l'hosting dei moduli visualizzati nel piè di pagina. Ad esempio, può includere collegamenti a varie pagine del sito, ad esempio le pagine **Politiche del punto vendita** e **Contattaci**.

## <a name="footer-module-properties"></a>Proprietà del modulo Piè di pagina 

Come la maggior parte dei contenitori, un modulo Piè di pagina supporta le proprietà per l'intestazione e la larghezza. Supporta inoltre l'aggiunta di molteplici moduli categoria Piè di pagina. Per ogni modulo Categoria piè di pagina aggiunto viene eseguito il rendering come colonna nel modulo Piè di pagina.

## <a name="modules-available-in-a-footer-module"></a>Moduli disponibili in un modulo Piè di pagina

**Elementi piè di pagina** - Un modulo Elementi piè di pagina può contenere un'intestazione, un'immagine e un collegamento. L'intestazione può essere utilizzata da sola o in combinazione con un'immagine e un collegamento. Ogni collegamento nel piè di pagina può essere configurato di modo che abbia solo testo (ad esempio i collegamenti "Contattaci" e "Privacy") oppure del testo e un'immagine (ad esempio collegamenti ai social media).

**Torna all'inizio** - Un modulo Torna all'inizio fornisce un collegamento per spostarsi rapidamente all'inizio della pagina. È necessaria una destinazione. Il valore di destinazione predefinito è #, che porta l'utente all'inizio della pagina.

## <a name="author-a-footer-module"></a>Creare un modello piè di pagina

1. Nel pannello di navigazione, selezionare **Frammenti** e quindi **Nuovo frammento pagina**.
1. Nella finestra di dialogo **Nuovo frammento pagina**, selezionare il modulo Piè di pagina, immettere un nome per il frammento e selezionare **OK**.
1. Nell'albero a sinistra, selezionare il pulsante con i puntini di sospensione (**...**) per il modulo Piè di pagina e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo Categoria piè di pagina e quindi **OK**.
1. Nell'albero, selezionare il pulsante con i puntini di sospensione per il modulo Categoria piè di pagina e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo Elemento piè di pagina e quindi **OK**.
1. Nell'albero, selezionare il modulo Elemento piè di pagina. Quindi, nel riquadro delle proprietà a destra, configurare l'intestazione, il collegamento, il testo del collegamento e l'immagine come necessario.
1. Per aggiungere ulteriori elementi piè di pagina, ripetere i passaggi da 5 a 7.
1. Per aggiungere un collegamento "torna all'inizio" al piè di pagina, selezionare il pulsante con i puntini di sospensione per il modulo Categoria piè di pagina e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo Torna all'inizio e quindi **OK**.
1. Nell'albero, selezionare il modulo Torna all'inizio. Quindi, nel riquadro delle proprietà a destra, configurare il modulo Torna all'inizio come necessario.
1. Salvare il frammento, archiviarlo e pubblicarlo.

In ogni modello di pagina creato per il sito, procedere come segue.

1. Nello slot **Principale** della pagina predefinita, nel modulo Piè di pagina, aggiungere il frammento piè di pagina creato.
1. Salvare il modello, archiviarlo e pubblicarlo.

Aggiungendo il frammento pagina ai modelli di pagina, si assicura il rendering del piè di pagina in ogni pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo Casella acquisti](add-buy-box.md)

[Modulo Carrello](add-cart-module.md)

[Modulo Checkout](add-checkout-module.md)

[Modulo Conferma ordine](order-confirmation-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)
