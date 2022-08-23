---
title: Migliorare una pagina prodotto
description: In questo articolo viene descritto come migliorare una pagina prodotto in Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: f01dcc2518fe861339b4984522582ed3de7aa6ad
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282136"
---
# <a name="enrich-a-product-page"></a>Migliorare una pagina prodotto

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come migliorare una pagina prodotto in Microsoft Dynamics 365 Commerce.

Per impostazione predefinita, il sito utilizza una pagina generica per visualizzare i dati del prodotto. Questa pagina include le informazioni di base sul prodotto e i controlli necessari per venderlo. Tuttavia, è possibile aggiungere ulteriori immagini o testo per un prodotto specifico alle informazioni di Commerce Scale Unit. Questo processo è noto come miglioramento della pagina prodotto.

In molti casi, si intende utilizzare ulteriore contenuto specifico per i prodotti. Quando si accede a **Retail e Commerce** nello strumento di creazione, è visibile un elenco di prodotti del canale assegnato al sito. Nell'elenco, la colonna **Migliorata** indica se la pagina prodotto di un prodotto è stata migliorata. Se un segno di spunta è visualizzato nella colonna, una pagina prodotto migliorata esiste per il prodotto. Se nessun segno di spunta è visualizzato, il contenuto e la pagina prodotto predefiniti vengono utilizzati per il prodotto. È possibile visualizzare l'anteprima delle pagine prodotto migliorate e non migliorate selezionando un nome di prodotto nell'elenco.

## <a name="enrich-a-product-page"></a>Migliorare una pagina prodotto

Per migliorare una pagina prodotto, attenersi alla procedura riportata di seguito.

1. In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).
1. Selezionare **Prodotti** nel pannello di navigazione a sinistra.
1. Selezionare un prodotto qualsiasi che non dispone di una pagina prodotto migliorata.
1. Nel riquadro azioni selezionare **Migliora pagina prodotto**.
1. Selezionare **Modello PDP** e quindi **OK**.
1. Nell'albero delle pagine a sinistra espandere, lo slot **Principale**.
1. Selezionare il pulsante con i puntini di sospensione (**...**) per lo slot **Principale** e quindi selezionare **Aggiungi modulo**.
1. Selezionare **Contenitore 2** e quindi **OK**.
1. Selezionare il pulsante con i puntini di sospensione per lo slot **Contenitore 2** e quindi selezionare **Aggiungi modulo**.
1. Selezionare **Funzionalità** e quindi **OK**.
1. Nel riquadro delle proprietà a destra, nel campo **RTF**, immettere la descrizione aggiornata del prodotto.
1. Nel campo **Intestazione**, immettere il testo dell'intestazione e quindi selezionare **OK**.
1. Selezionare **Salva** e quindi selezionare **Fine modifica**.
1. Nel campo **Commenti**, immettere **Prodotto migliorato** e selezionare **OK**.
1. Selezionare **Anteprima** per eseguire l'anteprima della pagina prodotto migliorata. Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.
1. Selezionare **Pubblica**

## <a name="additional-resources"></a>Risorse aggiuntive

[Modificare una pagina di sito esistente](modify-existing-page.md)

[Aggiungere una nuova pagina del sito](add-new-page.md)

[Selezionare layout di pagina](select-page-layouts.md)

[Gestire i metadati SEO](manage-seo-metadata.md)

[Salvare, visualizzare in anteprima e pubblicare una pagina](save-preview-publish-page.md)

[Migliorare una pagina di destinazione di categoria](enrich-category-page.md)

[Verificare l'accessibilità del contenuto della pagina](verify-accessibility.md)

[Creare pagine di e-commerce dinamiche in base ai parametri URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
