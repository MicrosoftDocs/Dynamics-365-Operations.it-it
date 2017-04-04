---
title: Dimensioni prodotto
description: Sono disponibili quattro dimensioni prodotto - configurazione, ID colore e dimensione, stile. Le dimensioni prodotto si combinano nei gruppi di dimensioni che si assegnano alle rappresentazioni generali prodotto. Le combinazioni di dimensioni prodotto determinano come si definiscono le varianti prodotto.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8854ab94a71cc363bcd073d2df47bc01a243b6cd
ms.lasthandoff: 03/31/2017


---

# <a name="product-dimensions"></a>Dimensioni prodotto

Sono disponibili quattro dimensioni prodotto - configurazione, ID colore e dimensione, stile. Le dimensioni prodotto si combinano nei gruppi di dimensioni che si assegnano alle rappresentazioni generali prodotto. Le combinazioni di dimensioni prodotto determinano come si definiscono le varianti prodotto.

Le dimensioni prodotto sono caratteristiche che servono a identificare una variante prodotto. È possibile utilizzare combinazioni di dimensioni prodotto per definire le varianti prodotto. Per creare una variante prodotto, è necessario definire almeno una dimensione prodotto per una rappresentazione generale prodotto.
Varianti prodotto
----------------

Le varianti prodotto vengono indicate anche con il termine articoli. Un articolo è un prodotto tangibile, non corrisponde a un servizio. È inoltre possibile definire una rappresentazione generale prodotto con il tipo di servizio. Utilizzando il tipo di servizio, è possibile specificare varianti prodotto che includono servizi. Ad esempio, è possibile specificare una rappresentazione generale prodotto per le varianti prodotto e consulenza per il lavoro che viene eseguito da consulenti senior e junior.

## <a name="product-dimensions"></a>Dimensioni prodotto
Nelle dimensioni prodotto sono disponibili: Configurazione, colore e dimensione, stile. Un variante prodotto può essere generato in base ai valori di dimensione prodotto.

I valori di dimensioni prodotto quali Dimensione, Colore e Stile possibile creare ** ** dimensione, colore ** ** e ** stile ** pagine, a cui è possibile accedere dalle seguenti posizioni: ** Gestione delle informazioni sul prodotto ** &gt; ** impostazione ** &gt; ** gruppi di varianti e Dimension ** &gt; ** dimensioni/colori o stili **. I valori di dimensione prodotto per la dimensione di configurazione in genere vengono creati utilizzando il configuratore prodotto o il configuratore basato su dimensioni. Le dimensioni prodotto possono essere create e gestite anche nella pagina **Dimensioni prodotto** alla quale è possibile accedere dalle posizioni seguenti:
-   ** Fare clic su Gestione delle informazioni sul prodotto ** &gt; ** prodotti ** &gt; ** rappresentazioni generali prodotto **. ** Nel riquadro azioni, fare clic su ** ** dimensioni prodotto **.
-   ** Fare clic su Gestione delle informazioni sul prodotto ** &gt; ** prodotti ** &gt; ** tutti i prodotti e rappresentazioni generali prodotto **. Selezionare una rappresentazione generale prodotto. ** Nel riquadro azioni, fare clic su ** ** dimensioni prodotto **.
-   ** Fare clic su Gestione delle informazioni sul prodotto ** &gt; ** prodotti rilasciati **. Selezionare una rappresentazione generale prodotto. ** Nel riquadro azioni, fare clic su ** ** ** prodotto. Nel gruppo **Rappresentazione generale prodotto**, fare clic su **Dimensioni prodotto**.

Il numero di varianti che è possibile creare per un articolo è limitato al numero di combinazioni possibili di dimensione prodotto.
| **Suggerimento **                                                                                                                                              |
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




