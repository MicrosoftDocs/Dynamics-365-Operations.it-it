---
title: Oggetti di costo
description: "Questo articolo fornisce le informazioni sugli oggetti di costo e illustra come i costi e le quantità sono accumulati. Un oggetto di costo è un'entità per cui costi e quantità sono accumulati. Un'entità oggetto di costo può essere un prodotto o varianti prodotto, ad esempio varianti per stile e colore."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d35d7971806e2f711d84f172bfacd60edf9f9225
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="cost-objects"></a>Oggetti di costo

[!include [banner](../includes/banner.md)]

Questo articolo fornisce le informazioni sugli oggetti di costo e illustra come i costi e le quantità sono accumulati. Un oggetto di costo è un'entità per cui costi e quantità sono accumulati. Un'entità oggetto di costo può essere un prodotto o varianti prodotto, ad esempio varianti per stile e colore.  

## <a name="cost-objects"></a>Oggetti di costo

Nella pagina **Oggetti di costo** sono elencati tutti gli oggetti di costo registrati in un prodotto. Gli oggetti di costo vengono definiti dai dati delle seguenti origini:

-   Prodotto
-   Gruppo di dimensioni prodotto
-   Gruppo di dimensioni di immagazzinamento
-   Gruppo di dimensioni di tracciabilità

**Nota:** un oggetto di costo rappresenta un elemento di costo solo di tipo **Materiale diretto**. Un oggetto di costo e un oggetto di magazzino differiscono nel modo in cui un oggetto di costo è definito dalle dimensioni inventariali selezionate per il rendiconto finanziario. Ad esempio, un articolo ha la configurazione indicata di seguito:

-   **Sito:** Inventario fisico = Sì, Inventario finanziario = Sì
-   **Magazzino:** Inventario fisico = Sì, Inventario finanziario = No
-   **Batch n.:** Inventario fisico = Sì, Inventario finanziario = No

Nella seguente tabella vengono illustrate le definizioni di oggetto di costo e di oggetto di magazzino.

| Tipo oggetto      | Numero articolo | Sito | Magazzino | Batch n. |
|------------------|-------------|------|-----------|-----------|
| Oggetto di costo      |  interno            |  interno     |           |           |
| Oggetto di magazzino |  interno            |  interno     |   interno         |  interno          |

## <a name="accumulation-of-costs-and-quantities"></a>Accumulo di costi e quantità
-   Il valore nel campo **Valore** è una somma dei valori seguenti:
    -   Importo costi fisico
    -   Importo costi finanziario
    -   Rettifiche
-   Il valore nel campo **Quantità** è una somma dei valori seguenti:
    -   Ricevuto
    -   Detratto
    -   Quantità registrata
-   Il campo **Costo unitario medio** è un campo calcolato. Il valore viene calcolato dividendo il valore di **Valore** per il valore di **Quantità**.

**Nota:** Il parametro **Includi valore fisico** non ha alcun effetto sui calcoli precedenti.

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Gruppo di dimensioni prodotto](https://technet.microsoft.com/en-us/library/aa499382.aspx)

[Gruppo di dimensioni di immagazzinamento](https://technet.microsoft.com/en-us/library/hh209317.aspx)

[Gruppo di dimensioni di tracciabilità](https://technet.microsoft.com/en-us/library/hh209465.aspx)

[Novità o modifiche](../../fin-and-ops/get-started/whats-new-changed.md)

[Voci di costo](cost-entries.md)




