---
title: Gestire i metadati SEO
description: In questo argomento viene descritto come gestire i metadati per l'ottimizzazione del motore di ricerca (SEO) in Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3d6f56968e9adfe90142955cba8e6c7ecc50fc92
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644761"
---
# <a name="manage-seo-metadata"></a>Gestire i metadati SEO

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

In questo argomento viene descritto come gestire i metadati per l'ottimizzazione del motore di ricerca (SEO) in Microsoft Dynamics 365 Commerce.

I metadati SEO per un sito possono essere gestiti utilizzando mappe del sito e metadati delle pagine.
    
## <a name="site-maps"></a>Mappe del sito

Una mappa del sito è un elenco leggibile al computer, in formato XML, delle pagine del sito Web. È utilizzato dai motori di ricerca, di modo che possano fornire risultati di ricerca migliori nel sito. Le mappe del sito possono essere inserite dai motori di ricerca o pubblicate in un file robots.txt.

Dynamics 365 Commerce supporta la generazione automatica di mappe del sito. Le mappe del sito sono aggiornate automaticamente quando si pubblicano le pagine o se ne annulla la pubblicazione.

### <a name="turn-on-site-map-generation"></a>Attivare la generazione della mappa del sito

1. Accedere allo strumento di creazione.
1. In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).
1. Selezionare **Gestione sito** nel pannello di navigazione a sinistra.
1. Verificare che l'opzione **Mappe del sito abilitate** sia attivata.

## <a name="page-metadata"></a>Metadati delle pagine

Dynamics 365 Commerce consente di gestire i metadati SEO di singole pagine. È possibile visualizzare e modificare queste informazioni nella sezione **Proprietà SEO** di un contenitore pagina. Sono supportate le seguenti proprietà dei metadati SEO:

- Funzione
- Descrizione
- Parole chiave SEO
- Etichette Aria
- noindex
- nofollow
- noarchive
- nocache
- noOpenDirectoryProject
- nosnippet
- noImageIndex
- unavailableAfter

### <a name="modify-page-metadata"></a>Modificare i metadati della pagina

Per modificare i metadati della pagina, effettuare le operazioni seguenti.
1. In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).
1. Nel pannello di navigazione a sinistra, selezionare **Pagine**.
1. Selezionare la home page per aprirla nell'editor di pagine.
1. Nella barra dei comandi, selezionare **Modifica**.
1. Nell'editor di pagina, nella parte superiore del controllo struttura della pagina a sinistra, seleziona **Opzione modalità struttura** (simbolo dell'ingranaggio), quindi seleziona **Vista struttura avanzata**.
1. Nella vista struttura, espandi i controlli ad albero per mostrare il contenuto dell'alloggiamento **intestazione HTML**.
1. Nell'alloggiamento **intestazione HTML** seleziona il modulo SEO desiderato (ad esempio, **Riepilogo della pagina**, **Riepilogo della pagina del prodotto**, **Riepilogo della pagina della categoria**, o **Metatag**).
1. Nel riquadro delle proprietà a destra, modifica i dati SEO desiderati per il modulo SEO selezionato (ad esempio, **Titolo**, **Descrizione**, o **Condivisione dell'immagine**).
1. Selezionare **Salva** e quindi selezionare **Fine modifica**.
1. Nel campo **Commenti**, immetti **Dati SEO aggiornati** e seleziona **OK**.
1. Selezionare **Anteprima** per visualizzare l'anteprima della pagina. Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.
1. Selezionare **Pubblica**

> [!TIP]
> Gli autori possono utilizzare **Opzione modalità struttura** (simbolo dell'ingranaggio) nella parte superiore del controllo di struttura a sinistra nell'editor di pagine per passare tra la **Vista struttura di base** e la **Vista struttura avanzata**. **Vista struttura di base** è l'impostazione predefinita e filtra la struttura in modo che mostri solo i moduli nell'alloggiamento HTML **Corpo** per una pagina. **Vista struttura avanzata** mostra l'intero modulo della pagina, inclusi gli alloggiamenti **Intestazione HTML**, **Inizio corpo**, e **Fine corpo**. Questa visualizzazione è utile quando gli autori devono modificare specifiche impostazioni SEO o moduli di script per una pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modificare una pagina del sito esistente](modify-existing-page.md)

[Aggiungere una nuova pagina del sito](add-new-page.md)

[Selezionare layout di pagina](select-page-layouts.md)

[Salvare, visualizzare in anteprima e pubblicare una pagina](save-preview-publish-page.md)

[Migliorare una pagina prodotto](enrich-product-page.md)

[Migliorare una pagina di destinazione di categoria](enrich-category-page.md)

[Verificare l'accessibilità del contenuto della pagina](verify-accessibility.md)

[Creare pagine di e-commerce dinamiche in base ai parametri URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
