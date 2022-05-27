---
title: Creare pagine di e-commerce dinamiche in base ai parametri URL
description: In questo argomento viene descritto come configurare una pagina di e-commerce Microsoft Dynamics 365 Commerce in grado di offrire contenuti dinamici, in base ai parametri URL.
author: StuHarg
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 348fdb30f4d0104e80bea5235c1e337b9f977311
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694342"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a>Creare pagine di e-commerce dinamiche in base ai parametri URL

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come configurare una pagina di e-commerce Microsoft Dynamics 365 Commerce in grado di offrire contenuti dinamici, in base ai parametri URL.

Una pagina di e-commerce può essere configurata per offrire contenuti diversi, in base a un segmento nel percorso dell'URL. Pertanto, la pagina è nota come pagina dinamica. Il segmento viene utilizzato come parametro per recuperare il contenuto della pagina. Ad esempio, una pagina denominata **blog\_viewer** viene creata e associata all'URL `https://fabrikam.com/blog`. Questa pagina può quindi essere utilizzata per mostrare contenuti diversi, in base all'ultimo segmento nel percorso dell'URL. Ad esempio, l'ultimo segmento nell'URL `https://fabrikam.com/blog/article-1` è **article-1**.

Le pagine personalizzate separate che sostituiscono la pagina dinamica possono anche essere associate a segmenti nel percorso dell'URL. Ad esempio, una pagina denominata **blog\_summary** viene creata e associata all'URL `https://fabrikam.com/blog/about-this-blog`. Quando viene richiesto questo URL, la pagina **blog\_summary** associata al parametro **/about-this-blog** viene restituita al posto della pagina **blog\_viewer**.

> [!NOTE]
> La funzionalità per l'hosting, il recupero e la visualizzazione del contenuto dinamico della pagina viene implementata utilizzando un modulo personalizzato. Per ulteriori informazioni, vedi [Estendibilità del canale online](e-commerce-extensibility/overview.md).

## <a name="set-up-a-dynamic-e-commerce-page"></a>Impostare una pagina di e-commerce dinamica

Per impostare una pagina di e-commerce dinamica, è necessario creare la pagina dinamica, creare l'URL di base e configurare il percorso della pagina dinamica.

### <a name="create-the-page-that-will-serve-dynamic-content"></a>Creare la pagina che offrirà il contenuto dinamico

Per creare una pagina che offrirà contenuto dinamico, segui i passaggi in [Aggiungere una nuova pagina del sito](add-new-page.md). La pagina che creerai richiederà l'implementazione di un modulo che utilizza l'ultimo segmento nel percorso dell'URL per recuperare il contenuto da un'origine dati esterna. Per ulteriori informazioni sullo sviluppo di moduli personalizzati, vedi [Estendibilità del canale online](e-commerce-extensibility/overview.md).

### <a name="create-the-base-url-for-the-dynamic-page"></a>Creare l'URL di base per la pagina dinamica

Per creare l'URL di base per la pagina dinamica in Creazione di siti di Commerce, segui questi passaggi.

1. Vai a **URL** e seleziona **Nuovo \> Nuovo URL**.
1. Nella finestra di dialogo **Crea nuovo URL**, seleziona **Pagina interna**. In **Percorso URL**, immetti il percorso che servirà da radice per la pagina dinamica (in questo esempio, **/blog**). Quindi seleziona **Avanti**.
1. Nella finestra di dialogo **Seleziona pagina**, seleziona la pagina creata come pagina dinamica, quindi seleziona **Salva**.
1. Selezionare **Pubblica**

### <a name="configure-the-route-to-the-dynamic-page"></a>Configurare il percorso della pagina dinamica

Per configurare il percorso della pagina dinamica in Creazione di siti di Commerce, segui questi passaggi.

1. Vai a **Impostazioni sito \> Estensioni**.
1. In **Percorsi URL con parametri**, seleziona **Aggiungi**, quindi immetti il percorso dell'URL immesso quando hai creato l'URL (in questo esempio, **/blog**).
1. Seleziona **Salva e pubblica**.

Dopo aver configurato il percorso, tutte le richieste del percorso dell'URL con parametri restituiranno la pagina associata a quell'URL. Se le richieste contengono un segmento aggiuntivo, verrà restituita la pagina associata e il contenuto della pagina verrà recuperato utilizzando il segmento come parametro. Per esempio, `https://fabrikam.com/blog/article-1` restituirà la pagina **blog\_summary** e il contenuto della pagina verrà recuperato utilizzando il parametro **/article-1**.

## <a name="override-a-parameterized-url-with-a-custom-page"></a>Sostituzione di un URL con parametri con una pagina personalizzata

Per sostituire un URL con parametri con una pagina personalizzata in Creazione di siti di Commerce, segui questi passaggi.

1. Vai a **URL** e seleziona **Nuovo \> Nuovo URL**.
1. Nella finestra di dialogo **Crea nuovo URL**, seleziona **Pagina interna**. In **Percorso URL**, immetti il percorso che include il segmento da sostituire (in questo esempio, **/blog/about-this-blog**). Quindi seleziona **Avanti**.
1. Nella finestra di dialogo **Seleziona pagina**, seleziona la pagina personalizzata e quindi seleziona **Salva**.
1. Selezionare **Pubblica**
1. Se la pagina personalizzata non è stata ancora pubblicata, vai a **Pagine**, seleziona la pagina personalizzata, quindi seleziona **Pubblica**.

Dopo la pubblicazione, la pagina personalizzata verrà offerta al posto della pagina dinamica con contenuto con parametri.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modificare una pagina del sito esistente](modify-existing-page.md)

[Aggiungere una nuova pagina del sito](add-new-page.md)

[Selezionare layout di pagina](select-page-layouts.md)

[Gestire i metadati SEO](manage-seo-metadata.md)

[Salvare, visualizzare in anteprima e pubblicare una pagina](save-preview-publish-page.md)

[Migliorare una pagina prodotto](enrich-product-page.md)

[Migliorare una pagina di destinazione di categoria](enrich-category-page.md)

[Verificare l'accessibilità del contenuto della pagina](verify-accessibility.md)

[Estendibilità del canale online](e-commerce-extensibility/overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
