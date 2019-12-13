---
title: Modulo Conferma ordine
description: In questo argomento vengono descritti i moduli Conferma ordine e la procedura per crearli in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: e339ce02bb646d0d9a68c22b24fde9b72071de6f
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698328"
---
# <a name="order-confirmation-module"></a>Modulo Conferma ordine

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Conferma ordine e la procedura per crearli in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo Conferma ordine viene utilizzato per visualizzare un messaggio di conferma in una pagina di conferma ordine dopo che l'ordine è stato piazzato. Il modulo Conferma ordine mostra il numero di conferma ordine e l'indirizzo di posta elettronica del cliente fornito durante il checkout.

Quando si effettua un ordine durante il checkout, il numero di conferma ordine e l'indirizzo di posta elettronica del cliente vengono passati alla pagina di conferma ordine come stringa di query nell'URL della pagina. Il modulo Conferma ordine riceve queste informazioni ed esegue il rendering dello stato dell'ordine nella pagina di conferma ordine. Il modulo Conferma ordine richiede questo contesto di pagina per fornire lo stato dell'ordine.

## <a name="order-confirmation-module-properties"></a>Proprietà del modulo Conferma ordine

| Nome proprietà | Valori | Descrizione |
|---------------|--------|-------------|
| Intestazione       | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**), | Il modulo Conferma ordine può avere un'intestazione. Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione. Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità. |

## <a name="modules-that-can-be-used-in-an-order-confirmation-page-module"></a>Moduli che possono essere utilizzati in un modulo Pagina di conferma ordine 

- **Suggerimenti** - Il modulo Suggerimenti può essere inserito nella pagina di conferma ordine per suggerire altri prodotti al cliente.
- **Marketing** - Il modulo Marketing può aggiungere contenuto marketing alla pagina di conferma ordine.

## <a name="create-an-order-confirmation-page-module"></a>Creare un modulo Pagina di conferma ordine

1. Creare un modello di pagina denominato **Modello conferma ordine**.
1. Nello slot **Principale** della pagina predefinita, aggiungere un modulo Conferma ordine.
1. Nel modulo Conferma ordine, aggiungere un modulo Suggerimenti.
1. Salvare il modello e visualizzarne l'anteprima. Non si deve eseguire il rendering del modulo Conferma ordine in quanto richiede il contesto del numero di conferma ordine.
1. Archiviare il modello e pubblicarlo.
1. Utilizzare il modello di conferma ordine appena creato per creare una pagina denominata **Pagina conferma ordine**.
1. Aggiungere la pagina predefinita alla struttura delle pagine.
1. Nello slot **Intestazione**, aggiungere un frammento intestazione.
1. Nello slot **Piè di pagina**, aggiungere un frammento piè di pagina.
1. Nello slot **Principale**, aggiungere un modulo Conferma ordine.
1. Nel riquadro delle proprietà del modulo Conferma ordine, aggiungere l'intestazione **Conferma ordine**.
1. Sotto il modulo Conferma ordine, aggiungere un modulo Suggerimenti e configurarlo di modo che utilizzi le impostazioni **Novità** e **Più venduti**.
1. Salvare la pagina e visualizzarne l'anteprima, quindi archiviare e pubblicare la pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo Casella acquisti](add-buy-box.md)

[Modulo Carrello](add-cart-module.md)

[Modulo Checkout](add-checkout-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)
