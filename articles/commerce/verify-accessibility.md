---
title: Verificare l'accessibilità del contenuto della pagina
description: Questo articolo descrive come verificare l'accessibilità del contenuto della pagina in Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: caccb6085947193e4a5f8a8555722dd073f0c275
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884762"
---
# <a name="verify-page-content-accessibility"></a>Verificare l'accessibilità del contenuto della pagina

[!include [banner](includes/banner.md)]

Questo articolo descrive come verificare l'accessibilità del contenuto della pagina in Microsoft Dynamics 365 Commerce.

Al termine della modifica di una pagina, è necessario assicurarsi che il contenuto sia accessibile a tutti sul Web. Negli strumenti di creazione di Commerce, è possibile verificare facilmente l'accessibilità del contenuto della pagina utilizzando il servizio [Microsoft Accessibility Insights](https://accessibilityinsights.io/). Questo servizio verifica il contenuto della tua pagina rispetto alle ultime linee guida sull'[accessibilità al World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility).

L'integrazione di [Microsoft Accessibility Insights](https://accessibilityinsights.io/) deve essere attivata a livello di tenant o di sito prima di poterla utilizzare.

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a>Attivare Microsoft Accessibility Insights per tutti i siti nel tuo tenant

Per attivare l'integrazione di [Microsoft Accessibility Insights](https://accessibilityinsights.io/) per tutti i siti Commerce nel tenant, attenersi alla seguente procedura.

> [!NOTE]
> Per accedere alle impostazioni del tenant, è necessario effettuare l'accesso a Commerce come amministratore di sistema.

1. Accedere a Commerce come amministratore di sistema.
1. Nel riquadro di spostamento sinistro, selezionare **Impostazioni tenant** (accanto al simbolo dell'ingranaggio) per espanderlo.
1. In **Impostazioni tenant**, selezionare **Funzionalità**.
1. Impostare l'opzione **Verifica accessibilità** su **Attiva**.

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a>Attivare Microsoft Accessibility Insights per un singolo sito

Per attivare l'integrazione di [Microsoft Accessibility Insights](https://accessibilityinsights.io/) per un singolo sito di Commerce, attenersi alla seguente procedura.

1. In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).
1. Nel riquadro di spostamento sinistro, selezionare **Impostazioni sito** per espanderlo.
1. In **Impostazioni sito**, selezionare **Funzionalità**.
1. Impostare l'opzione **Verifica accessibilità** su **Attiva**.

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a>Verificare l'accessibilità del contenuto nella home page

Per utilizzare il servizio [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integrato per analizzare e verificare il contenuto della home page in Commerce, seguire questi passaggi.

1. In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).
1. Nel pannello di navigazione a sinistra, selezionare **Pagine**.
1. Trovare e selezionare la home page per aprirla nell'editor di pagine.
1. Nella barra dei comandi, selezionare **Verifica accessibilità**. Viene visualizzata la pagina **Verifica accessibilità**.
1. Al termine della scansione, rivedere il contenuto del report.
1. Se la verifica ha esito negativo, selezionare ciascun elemento della verifica non riuscito per espanderlo in modo da poter visualizzare ulteriori dettagli.
1. Per chiudere il report dopo averlo esaminato, scorrere fino alla fine della pagina **Verifica accessibilità** e selezionare **OK**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modificare una pagina del sito esistente](modify-existing-page.md)

[Aggiungere una nuova pagina del sito](add-new-page.md)

[Selezionare layout di pagina](select-page-layouts.md)

[Gestire i metadati SEO](manage-seo-metadata.md)

[Salvare, visualizzare in anteprima e pubblicare una pagina](save-preview-publish-page.md)

[Migliorare una pagina prodotto](enrich-product-page.md)

[Migliorare una pagina di destinazione di categoria](enrich-category-page.md)

[Creare pagine di e-commerce dinamiche in base ai parametri URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
