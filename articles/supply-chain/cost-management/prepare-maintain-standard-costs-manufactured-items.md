---
title: Eseguire le operazioni preliminari alla gestione dei costi standard per gli articoli prodotti
description: In questo argomento vengono descritti i passaggi per la gestione dei costi per gli articoli prodotti.
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fbd7344f3d542cbd46e3568d8a7911ab4ab53b17
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545950"
---
# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a>Eseguire le operazioni preliminari alla gestione dei costi standard per gli articoli prodotti

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritti i passaggi per la gestione dei costi per gli articoli prodotti. I passaggi per gli articoli prodotti sono leggermente diversi dai passaggi per gli articoli acquistati.

I criteri che vengono assegnati agli articoli prodotti possono incidere sui calcoli dei costi degli articoli prodotti principali. Per la preparazione alla gestione dei costi degli articoli prodotti effettuare le seguenti operazioni.

1. Assegnare un gruppo di modelli di articoli all'articolo prodotto. 

   Il gruppo di modelli di articoli identifica i costi standard che verranno utilizzati.

2. Assegnare un gruppo di articoli all'articolo prodotto. 

   Nel gruppo di articoli sono contenuti conti CoGe validi per l'articolo prodotto. Nei conti CoGe di un articolo prodotto associato a un modello inventariale Costo standard sono inclusi diversi scostamenti produzione, lo scostamento delle variazioni di costo e la rivalutazione del costo di magazzino.

3. Assegnare l'unità di misura di magazzino all'articolo. 

   I costi dell'articolo sono sempre espressi nell'unità di misura di magazzino dell'articolo.

4. Non assegnare un gruppo di costi all'articolo prodotto, a meno che l'articolo non debba essere gestito come articolo acquistato.

5. Assegnare un gruppo di calcolo distinta base (DBA) all'articolo prodotto. 

   Il gruppo di calcolo DBA dell'articolo definisce le condizioni di avviso applicabili. In questo modo, quando un calcolo DBA viene eseguito, i messaggi di avviso possono essere generati relativamente a possibili origini di errori di calcolo. In un messaggio di avviso ad esempio, può essere segnalato se non è presente una DBA o un ciclo di lavorazione attivo. Nel gruppo di calcolo DBA è contenuto un criterio di interruzione esplosione che indica quando deve essere gestito un articolo prodotto come articolo acquistato.

6. Se l'articolo prodotto ha dei costi costanti, assegnare una quantità ordine standard ad esso. 

   La quantità ordine standard rappresenta le dimensioni lotto di contabilità per ammortizzare i costi costanti, Esempi di costi costanti includono i tempi di impostazione nelle operazioni dei cicli di lavorazione e una quantità di componenti costante nella distinta base (DBA).

7. Definire la DBA per l'articolo prodotto. 

   È possibile definire una o più versioni DBA per l'articolo prodotto. Verificare che le versioni desiderate siano state contrassegnate come approvate e attive e che le date di validità siano quelle desiderate. La versione DBA può essere a livello aziendale o specifica di un sito.

8. Definire il ciclo di lavorazione dell'articolo prodotto. 

   È possibile definire una o più versioni di cicli di lavorazione per l'articolo prodotto. Verificare che le versioni desiderate siano state contrassegnate come approvate e attive e che le date di validità siano quelle desiderate. La versione del ciclo di lavorazione deve essere specifica di un sito.

Se si desidera utilizzare informazioni del ciclo di lavorazione per la determinazione costi sono necessari ulteriori operazioni di preparazione. Le categorie di costo assegnate alle operazioni dei cicli di lavorazione ad esempio devono essere corrette e complete.

<a name="related-topics"></a>Argomenti correlati
--------

[Ammortamento dei costi costanti per un articolo prodotto](amortize-constant-costs-manufactured-item.md)

[Impostare prodotti che possono essere prodotti o ottenuti](manufactured-items-treated-as-purchased-items.md)

