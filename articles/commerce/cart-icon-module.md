---
title: Modulo Icona carrello
description: In questo argomento viene descritto il modulo Icona carrello e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 138c256b56593c4fafb20050a97e614fa584597c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997827"
---
# <a name="cart-icon-module"></a>Modulo Icona carrello

[!include [banner](includes/banner.md)]

In questo argomento viene descritto il modulo Icona carrello e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Il modulo Icona carrello rappresenta il carrello nel modulo Intestazione della pagina e mostra in qualsiasi momento il numero di articoli presenti nel carrello. Il modulo Icona carrello mostra anche un riepilogo del carrello (noto anche come mini carrello) quando si passa con il mouse sull'icona del carrello. Il mini carrello fornisce all'utente un riepilogo degli articoli nel carrello senza dover accedere alla pagina del carrello. Inoltre, consente all'utente di accedere direttamente alla pagina di pagamento se è soddisfatto del riepilogo. Ciò riduce il numero di navigazioni della pagina e velocizza il checkout. 

> [!NOTE]
> Il supporto per l'utilizzo del modulo dell'icona del carrello è disponibile in Dynamics 365 Commerce versione 10.0.11.

L'immagine seguente mostra un esempio di un modulo Icona carrello che visualizza un mini carrello nell'intestazione Fabrikam.

![Esempio di modulo Icona carrello](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Proprietà del modulo

- **Mostra mini carrello** - Se impostata su vero, questa proprietà consente di visualizzare un riepilogo del carrello (mini carrello) quando si passa con il mouse sull'icona del carrello. Questa funzionalità è supportata solo per le porte di visualizzazione desktop.

## <a name="add-a-cart-icon-module-to-a-page"></a>Aggiungere un modulo Icona carrello a una pagina

Per aggiungere un modulo Icona carrello, vedere [Modulo Intestazione](author-header-module.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo carrello](add-cart-module.md)

[Modulo checkout](add-checkout-module.md)

[Modulo pagamento](payment-module.md)

[Modulo indirizzo di spedizione](ship-address-module.md)

[Modulo opzioni di consegna](delivery-options-module.md)

[Modulo di informazioni sul ritiro](pickup-info-module.md)

[Modulo Dettagli ordini](order-confirmation-module.md)

[Modulo gift card](add-giftcard.md)
