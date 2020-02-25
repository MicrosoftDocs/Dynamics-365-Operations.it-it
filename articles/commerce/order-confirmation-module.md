---
title: Modulo Dettagli ordini
description: In questo argomento vengono descritti i moduli Dettagli ordine e la procedura per utilizzarli in Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: cb09a0b6ce1e48707f96021e9fad0006d9c1c55c
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026019"
---
# <a name="order-details-module"></a>Modulo Dettagli ordini


[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Dettagli ordine e la procedura per utilizzarli in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Il modulo Dettagli ordine viene utilizzato per visualizzare i dettagli di conferma di un ordine dopo l'esecuzione dell'ordine. Mostra l'ID di conferma dell'ordine, le informazioni di contatto dell'ordine e altri dettagli, come gli articoli acquistati, le informazioni di pagamento e il metodo di spedizione.

## <a name="order-confirmation-module-properties"></a>Proprietà del modulo Conferma ordine

| Nome proprietà  | Valori | Descrizione |
|----------------|--------|-------------|
| Intestazione        | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**), | Il modulo Conferma ordine può avere un'intestazione. Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione. Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità. |
| Numero contatto | Text | È possibile fornire un numero di contatto per domande relative all'ordine. |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a>Moduli che possono essere utilizzati in una pagina Dettagli ordine

Quando si crea una pagina Dettagli ordine, è possibile aggiungere altri moduli pertinenti oltre al modulo Dettagli ordine. Di seguito sono riportati alcuni esempi.

- **Modulo Suggerimenti** - Il modulo Suggerimenti può essere aggiunto alla pagina Dettagli ordine per suggerire altri prodotti al cliente.
- **Moduli Marketing** - È possibile aggiungere qualsiasi modulo Marketing alla pagina Dettagli ordine per visualizzare contenuti di marketing.

## <a name="create-an-order-details-page-module"></a>Creare un modulo per la pagina Dettagli ordine

1. Creare un modello di pagina denominato **Modello Dettagli ordine**.
1. Nello slot **Principale** della pagina predefinita, aggiungere un modulo Dettagli ordine.
1. Nel modulo Dettagli ordine, aggiungere un modulo Suggerimenti.
1. Salvare il modello e visualizzarne l'anteprima. Il rendering del modulo Dettagli ordine non verrà eseguito in quanto richiede il contesto del numero di conferma ordine.
1. Completare la modifica del modello e pubblicarlo.
1. Utilizzare il modello Dettagli ordine appena creato per creare una pagina denominata **Pagina Dettagli ordine**.
1. Aggiungere la pagina predefinita alla struttura delle pagine.
1. Nello slot **Intestazione**, aggiungere un frammento intestazione.
1. Nello slot **Piè di pagina**, aggiungere un frammento piè di pagina.
1. Nello slot **Principale**, aggiungere un modulo Dettagli ordine.
1. Nel riquadro delle proprietà del modulo Dettagli ordine, aggiungere l'intestazione **Dettagli ordine**.
1. Sotto il modulo Dettagli ordine, aggiungere un modulo Suggerimenti e configurarlo di modo che utilizzi le impostazioni **Novità** e **Più venduti**.
1. Salvare la pagina e visualizzarne l'anteprima.
1. Completare la modifica della pagina e pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo Casella acquisti](add-buy-box.md)

[Modulo Carrello](add-cart-module.md)

[Modulo Checkout](add-checkout-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)
