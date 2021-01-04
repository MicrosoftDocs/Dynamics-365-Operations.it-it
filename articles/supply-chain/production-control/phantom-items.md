---
title: Articoli fittizi
description: Questo argomento descrive in dettaglio in che modo è possibile usare il tipo di riga Fittizio per le righe di una distinta base (DBA) e una formula in Dynamics 365 Supply Chain Management.
author: ShylaThompson
manager: tfehr
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: kamaybac
ms.search.validfrom: ''
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: b14bebadd7088c9bbcfb6b1c5df1fe1a3c98694d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431332"
---
# <a name="phantom-items"></a>Articoli fittizi

[!include [banner](../includes/banner.md)]

Questo argomento descrive in dettaglio in che modo è possibile usare il tipo di riga Fittizio per le righe di una distinta base (DBA) e una formula. Nella figura seguente, (a) è la DBA per il prodotto H e le parti F e G e (b) è la scheda cicli di lavorazione per i prodotti H e la parte F.

![Prodotto H e parte F](media/product-H-part-F.png)


Questa figura mostra un esempio di una struttura DBA a due livelli. Il prodotto finito H rappresenta un prodotto per l'assemblaggio di una macchina. L'assemblaggio della macchina consiste di due parti, un'unità elettrica (F) che ha due materiali (A e B) e un gruppo di materiali da imballaggio (G) che ha anch'esso due materiali (C e D). Un altro materiale (E) viene utilizzato durante l'assemblaggio generale della macchina.

![Prodotto H e parte F](media/product-H-part-B.png)

La figura precedente rappresenta la DBA progettazione per il prodotto H. Questa struttura offre una buona panoramica delle parti e dei componenti dell'intero assemblaggio della macchina. Tuttavia, sebbene i progettisti possano preferire di vedere la DBA rappresentata in questo modo, questa struttura potrebbe non rappresentare correttamente in modo in cui la macchina viene costruita nello shop floor. 

La DBA progettazione nella figura precedente, ad esempio, indica che l'unità elettrica F viene assemblata come parte separata in un ordine di lavoro separato. Tuttavia, nello shop floor potrebbe risultare più ottimale assemblare l'unità elettrica come parte dell'intero assemblaggio della macchina, non come ordine di lavoro separato.

Questa DBA progettazione indica anche che la parte G è una parte separata. Tuttavia, in questa struttura la parte G non rappresenta una parte fisica ma una raccolta di materiali da imballaggio. 

Di conseguenza, anche se una DBA progettazione ha immesso valore per la progettazione di un prodotto e la gestione di quel progetto, potrebbe non essere il modo più logico per supportare il processo di produzione del prodotto. Per contro, una DBA di produzione rappresenta il modo migliore per creare un prodotto.

La figura seguente mostra come la DBA progettazione precedente viene importata in una DBA di produzione. In questa illustrazione, (a) è la DBA per il prodotto H e (b) è la scheda cicli di lavorazione per il prodotto H.

In questa struttura, si noterà che non sono presenti nozioni delle parti F e G e i materiali di cui consistono queste parti sono stati elevati al livello successivo della DBA. 

A differenza della DBA progettazione, che ha due prospetti operativi, la DBA di produzione ha un solo prospetto operativo. Anche l'operazione di imballaggio che è stata associata alla parte G è stata elevata e ora fa parte del prospetto operativo per il prodotto H. L'assemblaggio dell'unità elettrica è la prima operazione. Questo ordine è logico perché questa unità viene utilizzata nell'operazione successiva che è l'assemblaggio della macchina. L'ultima operazione è l'operazione di imballaggio, che utilizza due materiali di imballaggio (C e D).

La transizione tra la DBA progettazione e la DBA di produzione viene abilitata attraverso il tipo di riga di DBA fittizio. Come indica il termine" fittizio", le parti F e G sono scomparse durante la transizione tra i due tipi di DBA. In questo esempio, il tipo di riga fittizio viene applicato alle righe DBA per le parti F e G nella DBA progettazione. Quando viene creato un ordine batch o di produzione, la DBA progettazione viene copiata nell'ordine batch o di produzione. In seguito, quando l'ordine viene stimato, viene eseguita la transizione dalla DBA progettazione alla DBA di produzione, come mostrato nelle illustrazioni precedenti. Dal prospetto operativo nella seconda illustrazione, i materiali di imballaggio C e D sono input per l'operazione. 

## <a name="multilevel-phantom-bom-structures"></a>Strutture DBA fittizie multilivello
È possibile utilizzare il tipo di riga fittizio nelle strutture DBA multilivello, come mostrato nell'illustrazione seguente. In questa illustrazione, (a) è la DBA per il prodotto G e (b) è la scheda cicli di lavorazione per le parti E e F e il prodotto G. 

![Prodotto G e parte F con le schede cicli di lavorazione](media/product-G-route-sheet-G.png)


La figura seguente mostra la DBA di produzione e la scheda cicli di produzione risultanti se la righe DBA per le parti E e F vengono configurate con il tipo di riga fittizio. In questa illustrazione, (a) è la DBA per il prodotto G e (b) è la scheda cicli di lavorazione per il prodotto G.

![Prodotto G](media/product-G.png)


## <a name="phantom-and-route-network"></a>Rete di cicli di lavorazione e fittizia
La DBA fittizia può essere utilizzata anche per una DBA con una rete di cicli di lavorazione. In una rete di cicli di lavorazione, una o più operazioni vengono eseguite in parallelo. La figura seguente mostra un esempio di una rete di cicli di lavorazione utilizzata in una distinta base multilivello. In questa illustrazione, (a) è la DBA per il prodotto G e la parte F e (b) è la scheda cicli di lavorazione per il prodotto G e la parte F, che ha una rete di cicli di lavorazione.

![Prodotto G e parte F](media/product-G-part-F.png)


Nella figura seguente, (a) è la DBA per il prodotto G e la parte F e (b) è la scheda cicli di lavorazione per il prodotto G e la parte F.

![Prodotto G e parte F con le schede cicli di lavorazione](media/product-G-part-F-with-route-sheet.png)
