---
title: Applicare le impostazioni delle unità di misura
description: In questo argomento vengono descritte le impostazioni relative alle unità di misura e il modo in cui applicarle in Microsoft Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7d338ba207c9a101f5e224ca66555b16a457bcbc
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271403"
---
# <a name="apply-unit-of-measure-settings"></a>Applicare le impostazioni delle unità di misura

[!include [banner](includes/banner.md)]

In questo argomento vengono descritte le impostazioni relative alle unità di misura e il modo in cui applicarle in Microsoft Microsoft Dynamics 365 Commerce.

Un prodotto può essere venduto in unità diverse, ad esempio "pezzo", "coppia" e "dozzina". In Commerce Headquarters è possibile definire l'unità di misura di vendita per un prodotto e visualizzarla su un sito e-commerce. Ad esempio, se un rivenditore vende un prodotto sia individualmente che in dozzine, le unità di misura disponibili possono essere visualizzate insieme ad altre informazioni sul prodotto.

Nell'esempio nella figura seguente, un'unità di misura di vendita al dettaglio di **pz** (pezzo) è stata configurata per un prodotto in Commerce Headquarters.

![Esempio di un prodotto configurato con un'unità di misura in Commerce Headquarters](./media/Productunit-headquarters.PNG)

> [!NOTE]
> Il supporto per l'applicazione e la visualizzazione dell'unità di misura è disponibile a partire dalla versione Commerce 10.0.19.

## <a name="unit-of-measure-settings"></a>Impostazioni delle unità di misura

Le impostazioni di visualizzazione delle unità di misura sono definite in Creazione di siti di Commerce, in **Impostazioni sito \> Estensioni \> Visualizza unità di misura per i prodotti**. Sono disponibili tre impostazioni supportate:

- **Non visualizzare** - Quando questa impostazione è selezionata, il sito di e-commerce non mostrerà l'unità di misura del prodotto. Questo è il comportamento predefinito.
- **Visualizza nell'esperienza di acquisto del prodotto** - Quando questa impostazione è selezionata, l'unità di misura viene visualizzata nelle pagine dei dettagli del prodotto, del carrello, del checkout, della cronologia degli ordini e dei dettagli dell'ordine.
- **Visualizzazione nell'esperienza di ricerca e acquisto del prodotto** - Quando questa impostazione è selezionata, l'unità di misura viene mostrata nelle pagine dell'esperienza di acquisto del prodotto e anche durante l'esperienza di ricerca del prodotto. Come parte di questo comportamento, le unità di misura vengono mostrate nei risultati della ricerca e nei moduli di raccolta dei prodotti.

> [!IMPORTANT]
> Le impostazioni di visualizzazione delle unità di misura sono disponibili a partire dalla versione Commerce 10.0.19. Se stai aggiornando da una versione precedente di Commerce, devi aggiornare manualmente il file appsettings.json. Per istruzioni, vedi [SDK e aggiornamenti della libreria moduli](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-unit-of-measure-settings"></a>Moduli che utilizzano le impostazioni delle unità di misura

I moduli che utilizzano le impostazioni delle unità di misura includono la casella di acquisto, la lista dei desideri, il carrello, l'icona del carrello, il contenitore dei risultati di ricerca, la raccolta di prodotti, il checkout e i dettagli dell'ordine.

Nell'esempio nella figura seguente, una pagina dei dettagli del prodotto (PDP) mostra l'unità di misura (**pz**) per un prodotto.

![Esempio di un PDP che mostra l'unità di misura](./media/Productunit-PDP.png)

Nell'esempio nella figura seguente, un modulo di raccolta di prodotti mostra l'unità di misura (**pz**) per un prodotto.

![Esempio di un modulo di raccolta prootti che mostra l'unità di misura](./media/Productunit-productcollection.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Modulo carrello](add-cart-module.md)

[Modulo casella acquisti](add-buy-box.md)

[Moduli e pagine gestione conti](account-management.md)

[SDK e aggiornamenti della libreria moduli](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
