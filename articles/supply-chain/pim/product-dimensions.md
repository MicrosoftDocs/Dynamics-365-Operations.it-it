---
title: Dimensioni prodotto
description: 'Esistono quattro dimensioni prodotto: Colore, Configurazione, Dimensioni e Stile. Le dimensioni prodotto si combinano nei gruppi di dimensioni che si assegnano alle rappresentazioni generali prodotto. Le combinazioni di dimensioni prodotto determinano come si definiscono le varianti prodotto.'
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 105324f146f28bc61e87dff1089b367958ff9062
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="product-dimensions"></a>Dimensioni prodotto

[!include[banner](../includes/banner.md)]

[!include[Retail name](../includes/retail-name.md)]


Esistono quattro dimensioni prodotto: Colore, Configurazione, Dimensioni e Stile. Le dimensioni prodotto si combinano nei gruppi di dimensioni che si assegnano alle rappresentazioni generali prodotto. Le combinazioni di dimensioni prodotto determinano come si definiscono le varianti prodotto.

Le dimensioni prodotto sono caratteristiche che servono a identificare una variante prodotto. È possibile utilizzare combinazioni di dimensioni prodotto per definire le varianti prodotto. Per creare una variante prodotto, è necessario definire almeno una dimensione prodotto per una rappresentazione generale prodotto.
Varianti prodotto
----------------

Le varianti prodotto vengono indicate anche con il termine articoli. Un articolo è un prodotto tangibile, non corrisponde a un servizio. È anche possibile definire una rappresentazione generale prodotto con il tipo Servizio. Utilizzando il tipo di servizio, è possibile specificare varianti prodotto che includono servizi. Ad esempio, è possibile specificare una rappresentazione generale prodotto per le varianti prodotto e consulenza per il lavoro che viene eseguito da consulenti senior e junior.

## <a name="product-dimensions"></a>Dimensioni prodotto
Le seguenti dimensioni prodotto sono disponibili: Colore, Configurazione, Dimensioni e Stile. Una variante prodotto può essere generata in base ai valori delle dimensioni prodotto.

I valori di dimensioni prodotto, ad esempio Dimensione, Colore e Stile, possono essere creati nelle pagine **Dimensioni**, **Colore** e **Stile**, a cui è possibile accedere dai seguenti percorsi: **Gestione delle informazioni sul prodotto** &gt; **Impostazioni** &gt; **Gruppi di varianti e di dimensione** &gt; **Dimensioni/colori/stili**. I valori di dimensione prodotto per la dimensione di configurazione in genere vengono creati utilizzando il configuratore prodotto o il configuratore basato su dimensioni. Le dimensioni prodotto possono essere create e gestite anche nella pagina **Dimensioni prodotto** alla quale è possibile accedere dalle posizioni seguenti:
-   Fare clic su **Gestione informazioni sul prodotto** &gt; **Prodotti** &gt; **Rappresentazioni generali prodotto**. Nel **riquadro azioni**, fare clic su **Dimensioni prodotto**.
-   Fare clic su **Gestione informazioni sul prodotto** &gt; **Prodotti** &gt; **Tutti i prodotti e tutte le rappresentazioni generali prodotto**. Selezionare una rappresentazione generale prodotto. Nel **riquadro azioni**, fare clic su **Dimensioni prodotto**.
-   Fare clic su **Gestione informazioni sul prodotto** &gt; **Prodotti rilasciati**. Selezionare una rappresentazione generale prodotto. Nel **riquadro azioni**, fare clic su **Prodotto**. Nel gruppo **Rappresentazione generale prodotto**, fare clic su **Dimensioni prodotto**.

Il numero di varianti che è possibile creare per un articolo è limitato al numero di combinazioni possibili di dimensione prodotto.
| **Suggerimento**                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Quando, ad esempio, si utilizza un prodotto in una riga ordine, selezionare le dimensioni prodotto per identificare la variante prodotto che si desidera utilizzare. |

## <a name="example"></a>Esempio
Una società vende jeans denim. L'articolo, i jeans, utilizza le dimensioni prodotto Colore e Dimensione. I jeans vengono venduti in tre diversi colori e sei taglie diverse. Colori: Blu, Nero, Marrone Dimensioni: XS, S, M, XL, XXL Non tutte le dimensioni sono disponibili in tutti i tre colori. Se tutte le combinazioni fossero disponibili, risulterebbero 18 tipi di jeans diversi. In questo esempio, vengono prodotte solo le seguenti nove combinazioni di varianti prodotto.

| Colore | Dimensione |
|-------|------|
| Blu  | XS   |
| Blu  | D    |
| Blu  | L    |
| Nero | L    |
| Nero | L    |
| Nero | XL   |
| Marrone | L    |
| Marrone | XL   |
| Marrone | XXL  |






