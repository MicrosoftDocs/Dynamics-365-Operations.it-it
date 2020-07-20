---
title: Panoramica della pagina di destinazione di categoria e della pagina dei risultati della ricerca predefinite
description: In questo argomento viene fornita una panoramica della pagina di destinazione di categoria predefinita e della pagina dei risultati della ricerca in Dynamics 365 Commerce.
author: ashishmsft
manager: annbe
ms.date: 06/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e85449c10fa4a768a144ce423a77bd1fc2c94352
ms.sourcegitcommit: ce397c2759f642c595e30fef58a770b50360b2bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "3527470"
---
# <a name="default-category-landing-page-and-search-results-page-overview"></a>Panoramica della pagina di destinazione di categoria e della pagina dei risultati della ricerca predefinite

[!include [banner](includes/banner.md)]

In questo argomento viene fornita una panoramica della pagina di destinazione di categoria predefinita e della pagina dei risultati della ricerca in Microsoft Dynamics 365 Commerce e-Commerce.

## <a name="default-category-landing-page"></a>Pagina di destinazione di categoria predefinita

La pagina di destinazione di categoria predefinita è la pagina che viene in genere visualizzata quando gli utenti del sito Web selezionano una categoria nella gerarchia di navigazione. La pagina di categoria consente di esaminare i prodotti categorizzati nonché di ordinarli e filtrarli.

![Pagina di destinazione di categoria predefinita](./media/SimpleCategoryLandingDressCategory.png)

La parte superiore della pagina è un'intestazione che mostra tutte le categorie di prodotti e altre pagine che il responsabile merchandising ha categorizzato. La configurazione viene effettuata durante quella della gerarchia di navigazione del canale. La parte inferiore della pagina è un piè di pagina che include collegamenti rapidi a vari argomenti a cui un acquirente potrebbe essere interessato.

I seguenti componenti sono essenziali per una categoria:

- I **riquadri di posizionamento dei prodotti** mostrano i prodotti che il responsabile merchandising ha definito in una categoria durante la configurazione della gerarchia di navigazione.
- I **criteri di affinamento e il riepilogo delle scelte** sono filtri che forniscono conteggi e che possono essere utilizzati per filtrare gli articoli. Il responsabile merchandising li configura durante la configurazione dei metadati correlati alle categorie del canale e agli attributi dei prodotti.
- Le **opzioni di ordinamento** sono utilizzate dai visitatori del sito Web per ordinare i prodotti. Per impostazione predefinita, sono disponibili le seguenti opzioni di ordinamento:

    - Prezzo: dal più basso al più alto
    - Prezzo: dal più alto al più basso
    - Nome prodotto: \[A-Z\]
    - Nome prodotto: \[Z-A\]
    - Valutazioni: dalla più bassa alla più alta
    - Valutazioni: dalla più alta alla più bassa

- La **paginazione** consente ai visitatori del sito Web di passare da una pagina di risultati di prodotti categorizzati a un'altra pagina.
- Il **conteggio totale** fornisce il numero totale di prodotti definiti in una categoria.

## <a name="enrich-a-category-landing-page"></a>Migliorare una pagina di destinazione di categoria

Se una pagina di destinazione di categoria deve includere un'esperienza più personalizzata per una specifica categoria, è possibile "arricchire" la pagina di destinazione per quella categoria. Ad esempio, è possibile aggiungere un video marketing per catturare l'attenzione dell'acquirente. Per ulteriori informazioni, vedere [Migliorare una pagina di destinazione di categoria](enrich-category-page.md).

![Pagina di destinazione di categoria migliorata](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a>Pagine di suggerimenti automatici e dei risultati della ricerca

Gli utenti di siti Web possono esplorare un sito accedendo a una categoria dalla gerarchia di navigazione o immettendo un termine di ricerca nel campo di ricerca.

Non appena gli utenti iniziano a digitare nel campo di ricerca, viene utilizzata la funzionalità di suggerimenti automatici immersivi che suggerisce i termini di ricerca.

Di seguito sono riportati alcuni tipi di suggerimenti che potrebbero essere visualizzati:

- Le **parole chiave** sono utilizzate per trovare articoli in tutti i prodotti assortiti nel canale.
- I **prodotti** forniscono collegamenti diretti alla pagina dettagli prodotto.
- I **suggerimenti di ricerca in categorie con ambito** elencano varie categorie e consentono agli utenti di cercare la parola chiave in una specifica categoria.

![Suggerimenti automatici immersivi](./media/ImmersiveAutoSuggestUX.png)

Quando gli utenti selezionano una delle parole chiave o i suggerimenti di ricerca in categorie per ambito, oppure quando non vi sono suggerimenti per il termine di ricerca che hanno immesso, viene visualizzata una pagina dei risultati della ricerca. Gli utenti possono quindi esplorare, ordinare e affinare l'elenco dei risultati della ricerca per trovare l'articolo desiderato.

![Pagina di destinazione della ricerca](./media/SearchLanding.png)

I seguenti componenti sono essenziali per una pagina dei risultati della ricerca:

- I **riquadri di posizionamento dei prodotti** mostrano i prodotti per la ricerca dell'utente. Per impostazione predefinita, questi riquadri sono ordinati per punteggio di pertinenza della ricerca basata su cloud.
- I **criteri di affinamento e il riepilogo delle scelte** sono filtri che forniscono conteggi e che possono essere utilizzati per filtrare gli articoli. Il responsabile merchandising li configura durante la configurazione dei metadati correlati alle categorie del canale e agli attributi dei prodotti.
- Le **opzioni di ordinamento** sono utilizzate dai visitatori del sito Web per ordinare i prodotti. Per impostazione predefinita, sono disponibili le seguenti opzioni di ordinamento:

    - Prezzo: dal più basso al più alto
    - Prezzo: dal più alto al più basso
    - Nome prodotto: \[A-Z\]
    - Nome prodotto: \[Z-A\]
    - Valutazioni: dalla più bassa alla più alta
    - Valutazioni: dalla più alta alla più bassa
    - Valore predefinito

- La **paginazione** consente ai visitatori del sito Web di passare da una pagina di risultati di prodotti categorizzati a un'altra pagina.
- Il **conteggio totale** fornisce il numero totale di prodotti definiti in una categoria e corrispondenti ai criteri di ricerca.

>[!NOTE]
>Queste funzionalità di ricerca basate su cloud sono disponibili a partire dalla versione 10.0.8. Verifica che in **Parametri di commercio > Parametri di configurazione** c'è una voce per "ProductSearch.UseAzureSearch impostata su 'true'". 
![Parametri di configurazione per la ricerca basata su cloud](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della ricerca basata su cloud](cloud-powered-search-overview.md)

[Panoramica della home page](quick-tour-home-page.md)

[Panoramica delle pagine dei dettagli del prodotto](quick-tour-pdp.md)

[Panoramica delle pagine del checkout e del carrello](quick-tour-cart-checkout.md)

[Panoramica delle pagine della gestione del conto](quick-tour-account-management.md)

