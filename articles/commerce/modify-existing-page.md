---
title: Modificare una pagina di sito esistente
description: In questo argomento viene descritto come modificare una pagina di sito esistente in Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: 8ca23dcf568cb0df6934f0d6201e4aafba5f9ba1
ms.sourcegitcommit: f16db76c1c235dfa445b50614bcee9219782d6dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2020
ms.locfileid: "3961636"
---
# <a name="modify-an-existing-site-page"></a>Modificare una pagina di sito esistente


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come modificare una pagina di sito esistente in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Quando si deve modificare una pagina, è necessario innanzi tutto aprirla nell'editor di pagine. Accedere al sito che contiene la pagina, quindi nell'elenco delle pagine, trovare la pagina desiderata. Se non è possibile trovare la pagina, utilizzare la funzionalità di ricerca avanzata dello strumento di creazione. Digitare il nome esatto della pagina oppure le prime lettere dello stesso e quindi un asterisco (\*). Viene visualizzato un elenco filtrato delle pagine. È possibile utilizzare questo elenco per trovare la pagina desiderata. Una volta trovata la pagina corretta, selezionare il nome della pagina per aprirla nell'editor di pagine.

> [!TIP]
> Se la pagina è visibile nel controllo pagina, è possibile selezionare **Modifica** e controllare la pagina prima di aprirla nell'editor delle pagine. In questo modo, è possibile estrarre più pagine contemporaneamente.

Dopo l'apertura della pagina nell'editor di pagine, è necessario verificare che sia stata estratta. La barra dei comandi nello strumento di creazione è dinamica, sensibile al contesto e allo stato. Di conseguenza, mostra solo le azioni che è possibile eseguire attualmente nella pagina. Ad esempio, se la pagina non è stata estratta da te, i pulsanti **Salvare** e **Fine modifica** non verranno visualizzati nella barra dei comandi. Lo stato della pagina è inoltre visualizzato sul lato destro della pagina.

Se la pagina non è ancora stata estratta, selezionare **Modificare** nella barra dei comandi. La barra dei comandi cambia per riflettere il nuovo stato della pagina. Viene inoltre visualizzata una notifica indicante che la pagina è stata estratta.

L'operazione successiva consiste nell'apportare le modifiche effettive. In genere, si utilizza l'albero delle pagine a sinistra per trovare e selezionare il modulo che si desidera modificare e quindi si apportano le modifiche nel riquadro delle proprietà a destra. 

Tuttavia, la modifica può talvolta comportare l'aggiunta o la rimozione di modelli o frammenti. Per aggiungere un frammento o un modulo, trovare lo slot a cui si desidera aggiungere il modulo o il frammento utilizzando l'albero delle pagine, quindi selezionare il pulsante con i puntini di sospensione (**...**) per quello slot. Viene visualizzato un menu che include i comandi per aggiungere un modulo o un frammento. Per rimuovere un modulo o un frammento, trovarlo e selezionarlo nell'albero delle pagine, selezionare il pulsante con i puntini di sospensione e quindi selezionare il comando per eseguire la rimozione.

> [!TIP]
> È anche possibile visualizzare e modificare le proprietà di qualsiasi modulo visibile nell'anteprima del generatore di pagine visivo selezionando il modulo direttamente.

Dopo aver finito di apportare le modifiche e visualizzare in anteprima il loro effetto, è consigliabile archiviare la pagina selezionando **Fine modifica** nella barra dei comandi. 

Per pubblicare immediatamente le modifiche, selezionare **Pubblica** nella barra dei comandi. L'ultima versione archiviata della pagina modificata viene pubblicata e diventa disponibile per gli utenti esterni che visualizzano il sito. 

## <a name="example-change-the-video-on-the-home-page"></a>Esempio: modificare il video nella home page

Nell'esempio seguente viene descritto come modificare la home page cambiando il video nel modulo Lettore video.

1. In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).
1. Nel pannello di navigazione a sinistra, selezionare **Pagine**.
1. Trovare e selezionare la home page per aprirla nell'editor di pagine.
1. Nella barra dei comandi, selezionare **Modifica**.
1. Nella struttura delle pagine, selezionare lo slot **Principale**.
1. Sotto lo slot **Principale**, espandere tutti i moduli contenitore fluidi.
1. Trovare e selezionare il modulo Lettore video.
1. Nel riquadro delle proprietà a destra, selezionare la proprietà **Video**. Viene visualizzato lo strumento di selezione di asset.
1. Nello strumento, selezionare un asset video disponibile oppure selezionare **Carica nuovo asset** per caricare un nuovo asset video.
1. Selezionare **OK**.
1. Selezionare **Salva** e quindi selezionare **Fine modifica**.
1. Nel campo **Commenti**, immettere **Modificato il video** e selezionare **OK**.
1. Selezionare **Anteprima** per visualizzare l'anteprima della pagina caricata. Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.
1. Selezionare **Pubblica**

## <a name="additional-resources"></a>Risorse aggiuntive

[Aggiungere una nuova pagina del sito](add-new-page.md)

[Selezionare layout di pagina](select-page-layouts.md)

[Gestire i metadati SEO](manage-seo-metadata.md)

[Salvare, visualizzare in anteprima e pubblicare una pagina](save-preview-publish-page.md)

[Migliorare una pagina prodotto](enrich-product-page.md)

[Migliorare una pagina di destinazione di categoria](enrich-category-page.md)

[Verificare l'accessibilità del contenuto della pagina](verify-accessibility.md)
