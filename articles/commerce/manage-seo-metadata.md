---
title: Gestire i metadati SEO
description: In questo argomento viene descritto come gestire i metadati per l'ottimizzazione del motore di ricerca (SEO) in Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1e7da7bf5c473746413e92babfa943f546b7724d
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003466"
---
# <a name="manage-seo-metadata"></a>Gestire i metadati SEO


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come gestire i metadati per l'ottimizzazione del motore di ricerca (SEO) in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

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
1. Nel riquadro azioni selezionare **Estrai**.
1. Nel riquadro delle proprietà a destra, espandere **Metatag predefiniti**.
1. Per aggiungere un nuovo metatag, selezionare **Aggiungi** e immettere il tag nel campo.

    Per rimuovere un metatag esistente, selezionare il cestino a destra dello stesso.

1. Selezionare **Salva** e quindi selezionare **Archivia**.
1. Nel campo **Commenti**, immettere **Metatag aggiornati** e selezionare **OK**.
1. Selezionare **Anteprima** per visualizzare l'anteprima della pagina. Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.
1. Selezionare **Pubblica**

## <a name="additional-resources"></a>Risorse aggiuntive

[Modificare una pagina di sito esistente](modify-existing-page.md)

[Aggiungere una nuova pagina del sito](add-new-page.md)

[Selezionare layout di pagina](select-page-layouts.md)

[Salvare, visualizzare in anteprima e pubblicare una pagina](save-preview-publish-page.md)

[Migliorare una pagina prodotto](enrich-product-page.md)

[Migliorare una pagina di destinazione di categoria](enrich-category-page.md)

[Verificare l'accessibilità del contenuto della pagina](verify-accessibility.md)
