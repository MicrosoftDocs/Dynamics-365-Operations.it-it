---
title: Salvare, visualizzare in anteprima e pubblicare una pagina
description: In questo argomento viene descritto come salvare, visualizzare in anteprima e pubblicare una pagina in Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
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
ms.openlocfilehash: f1eff0edeb630628057bd0a90e2dadc4857600f1
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791825"
---
# <a name="save-preview-and-publish-a-page"></a>Salvare, visualizzare in anteprima e pubblicare una pagina

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come salvare, visualizzare in anteprima e pubblicare una pagina in Microsoft Dynamics 365 Commerce.

## <a name="save-a-page"></a>Salvare una pagina

Per salvare una pagina, è necessario che questa sia estratta e aperta nell'editor di pagine. Per estrarre una pagina, selezionare **Modifica** sulla barra comandi. Dopo aver terminato la modifica di una pagina, è necessario salvarla immediatamente per assicurarsi che le modifiche siano memorizzate.

Quando si salva una pagina, le modifiche sono visibili solo all'utente corrente. Lo scopo principale dell'operazione di salvataggio è l'archiviazione delle modifiche quando la pagina non è ancora pronta per essere archiviata. Al termine della modifica della pagina, si consiglia di archiviarla, di modo che le modifiche siano visibili anche agli altri utenti. La pagina può quindi essere estratta anche da altri utenti che devono modificarla.

## <a name="preview-a-page"></a>Visualizzare l'anteprima di una pagina

Lo strumento di creazione offre due tipi di funzionalità di anteprima: il generatore di pagine visivo, che è un riquadro di anteprima WYSIWYG nell'editor di pagine, e una finestra di anteprima distinta.

Quando si utilizza l'editor di pagine, un'anteprima WYSIWYG viene visualizzata nel riquadro centrale. Questa anteprima viene automaticamente aggiornata ogni volta che si salva la pagina. È anche possibile aggiornarla manualmente selezionando **Aggiorna** nella barra dei comandi. L'anteprima visualizza la pagina esattamente come sarà visibile agli utenti del sito, ma con gli helper di creazione nella parte superiore.

Al termine della modifica della pagina, è possibile visualizzarne l'anteprima per stabilire quali clienti la vedranno. Per visualizzare l'anteprima di una pagina, selezionare **Anteprima** nella barra dei comandi. L'anteprima sarà visualizzata in una finestra del browser distinta. La pagina nella finestra di anteprima appare esattamente come risulterà visibile agli utenti del sito. È possibile ridimensionare la finestra per assicurare il corretto rendering di moduli reattivi in tutte le porte di visualizzazione.

> [!NOTE]
> Per visualizzare l'anteprima di contenuto non pubblicato, è necessario disporre di autorizzazioni di autenticazione appropriate. Di conseguenza, se si condivide l'URL dell'anteprima con qualcuno, quella persona deve disporre delle autorizzazioni appropriate per accedere al contenuto.

## <a name="publish-a-page"></a>Pubblicare una pagina

Una volta che la pagina è pronta, è necessario pubblicarla, di modo che gli utenti esterni possano visualizzare il contenuto. Prima di poter pubblicare una pagina, è necessario archiviarla selezionando **Fine modifica** sulla barra dei comandi.

È possibile pubblicare le pagine e annullarne la pubblicazione mediante il controllo pagina o l'editor di pagine. Il controllo pagina visualizza un elenco di pagine e consente operazioni in blocco. L'editor di pagine può essere utilizzato per pubblicare o annullare la pubblicazione della pagina he visualizza.

Per pubblicare una o più pagine mediante il controllo pagina, selezionare le pagine, assicurarsi che siano state archiviate e quindi selezionare **Pubblica** nella barra dei comandi. Le pagine vengono pubblicate e si riceve una notifica sull'operazione nello strumento di creazione.

Per pubblicare una singola pagina mediante l'editor di pagine, la procedura è analoga. Quando la pagina è aperta nell'editor di pagine, assicurarsi che sia stata archiviata e quindi selezionare **Pubblica** nella barra dei comandi. La pagina viene pubblicata e si riceve una notifica sull'operazione.

Quando si pubblica una pagina, viene pubblicato solo il contenuto della stessa. Gli utenti possono accedere alla pagina e visualizzarla solo quando si ha un URL ad esso associato. L'URL deve essere pubblicato separatamente.

> [!IMPORTANT]
> Prima di pubblicare una pagina, tutte le immagini o i frammenti a cui la pagina fa riferimento devono già essere pubblicati.

## <a name="save-preview-and-publish-a-home-page"></a>Salvare, visualizzare in anteprima e pubblicare una home page

Per salvare, visualizzare in anteprima e pubblicare una home page, effettuare le seguenti operazioni.

1. In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).
1. Nel pannello di navigazione a sinistra, selezionare **Pagine**.
1. Trovare e selezionare la home page per aprirla nell'editor di pagine.
1. Selezionare **Modifica**.
1. Modificare la pagina come necessario.
1. Selezionare **Salva** e quindi selezionare **Fine modifica**.
1. Nel campo **Commenti**, immettere una nota sulle modifiche apportate e selezionare **OK**.
1. Selezionare **Anteprima** per visualizzare l'anteprima della pagina. Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.
1. Selezionare **Pubblica**

## <a name="publish-a-url"></a>Pubblicare un URL

Per pubblicare un URL, procedere come segue.

1. In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).
1. Nel pannello di navigazione a sinistra, selezionare **URL**.
1. Trovare e selezionare l'URL da pubblicare.
1. Nella barra dei comandi, selezionare **Pubblica**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modificare una pagina di sito esistente](modify-existing-page.md)

[Aggiungere una nuova pagina del sito](add-new-page.md)

[Selezionare layout di pagina](select-page-layouts.md)

[Gestire i metadati SEO](manage-seo-metadata.md)

[Migliorare una pagina prodotto](enrich-product-page.md)

[Migliorare una pagina di destinazione di categoria](enrich-category-page.md)

[Verificare l'accessibilità del contenuto della pagina](verify-accessibility.md)

[Creare pagine di e-commerce dinamiche in base ai parametri URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]