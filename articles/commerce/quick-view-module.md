---
title: Modulo visualizzazione rapida
description: In questo argomento vengono descritti i moduli visualizzazione rapida e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-01-08
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: d7e88163fd9b8dc4f5636ed29e2c4248aece52bf
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792173"
---
# <a name="quick-view-module"></a>Modulo di visualizzazione rapida

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli visualizzazione rapida e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

Il modulo di visualizzazione rapida consente agli utenti di visualizzare rapidamente le informazioni sui prodotti quando esplorano i prodotti in una pagina di elenco e di aggiungere uno o più prodotti al carrello dalla pagina di elenco, senza dover andare alla pagina dei dettagli del prodotto (PDP). Il modulo di visualizzazione rapida fornisce una panoramica delle informazioni sul prodotto richieste dagli utenti per prendere la decisione "aggiungi al carrello". Fornisce inoltre un collegamento al PDP, in modo che gli utenti possano visualizzare ulteriori dettagli del prodotto e opzioni di acquisto.

Il modulo di visualizzazione rapida è supportato dai moduli [raccolta di prodotti](product-collection-module-overview.md) e [risultati di ricerca](search-result-module.md).

> [!IMPORTANT]
> Il modulo di visualizzazione rapida è disponibile a partire dalla versione Commerce 10.0.17.

L'immagine seguente mostra un esempio di modulo di visualizzazione rapida in una pagina elenco di prodotti.

![Esempio di un modulo di visualizzazione rapida su una pagina elenco di prodotti](./media/ecommerce-quickview.PNG)

## <a name="module-properties"></a>Proprietà del modulo

Il modulo di visualizzazione rapida supporta alcune delle stesse funzioni del modulo Buy box. Pertanto, le proprietà di un modulo di visualizzazione rapida assomigliano alle proprietà di un modulo buy box.

| Proprietà | Valori | Descrizione |
|----------------|--------|-------------|
| Tag intestazione | **H1**, **H2**, **H3**, **H4**, **H5** o **H6** | Questa proprietà definisce il tag di intestazione per il titolo del prodotto. Se il modulo visualizzazione rapida si trova nella parte superiore della pagina, questa proprietà deve essere impostata su **H1** per soddisfare gli standard di accessibilità. |
| Consenti prezzo personalizzato | **True** o **False** | Se questa proprietà è impostata su **True**, l'utente può inserire un prezzo personalizzato. |
| Prezzo minimo | Integer | Questa proprietà è applicabile solo se la proprietà **Consenti prezzo personalizzato** è impostata su **True**. Definisce il prezzo minimo che l'utente può inserire (ad esempio, $ 1). |
| Prezzo massimo | Integer | Questa proprietà è applicabile solo se la proprietà **Consenti prezzo personalizzato** è impostata su **True**. Definisce il prezzo massimo che l'utente può inserire (ad esempio, $ 1.000). |

## <a name="commerce-site-builder-settings"></a>Impostazioni di Creazione di siti di Commerce

Come il modulo Buy box, il modulo di visualizzazione rapida rispetta le impostazioni in **Impostazioni sito \> Estensioni \> Aggiungi prodotto al carrello**. Comunque, l'impostazione **Vai a pagina carrello** viene ignorata, perché non è coerente con lo scopo del modulo di visualizzazione rapida, che è quello di consentire agli utenti di sfogliare più prodotti in una pagina di elenco e aggiungerli al carrello senza uscire dalla pagina elenco.

## <a name="add-a-quick-view-module-to-a-product-collection-module"></a>Aggiungere un modulo visualizzazione rapida a un modulo di raccolta prodotti

Un modulo di visualizzazione rapida può essere aggiunto ai moduli raccolta di prodotti e risultati di ricerca.

Per aggiungere un modulo visualizzazione prodotti a un modulo di raccolta prodotti in Creazione di siti Web di Commerce, effettua le seguenti operazioni.

1. Vai a **Pagine** e seleziona la home page per il sito Fabrikam.
1. Vai un modulo di **raccolta prodotti** nella home page, seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** seleziona il modulo **Visualizzazione rapida** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo **visualizzazione rapida** seleziona **Intestazione**. Nella finestra di dialogo **Intestazione** imposta il campo **Livello di intestazione** su **H2** e quindi seleziona **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Modulo casella acquisti](add-buy-box.md)

[Modulo Raccolta prodotti](product-collection-module-overview.md)

[Modulo dei risultati di ricerca](search-result-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
