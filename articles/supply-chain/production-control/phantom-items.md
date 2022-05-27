---
title: Articoli fittizi
description: Questo argomento descrive in che modo è possibile usare il tipo di riga Fittizio per le righe di una distinta base (DBA) e una formula in Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 05/05/2022
ms.topic: article
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-05-05
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5c9768381d35709611e4bec3d2b7793a4d896b34
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713249"
---
# <a name="phantom-items"></a>Articoli fittizi

[!include [banner](../includes/banner.md)]

Questo argomento descrive in dettaglio in che modo è possibile usare il tipo di riga Fittizio per le righe di una distinta base (DBA) e una formula.

Nella figura 1 (a) è la DBA per il prodotto H e le parti F e G e (b) è la scheda cicli di lavorazione per i prodotti H e la parte F.

![Figura 1: distinta base di progettazione.](media/product-H-part-F.png)
*Figura 1: distinta base di progettazione*

La figura 1 mostra un esempio di una struttura DBA a due livelli. Il prodotto finito H rappresenta un prodotto per l'assemblaggio di una macchina. L'assemblaggio della macchina consiste di due parti, un'unità elettrica (F) che ha due materiali (A e B) e un gruppo di materiali da imballaggio (G) che ha anch'esso due materiali (C e D). Un altro materiale (E) viene utilizzato durante l'assemblaggio generale della macchina.

La figura 1 rappresenta la DBA progettazione per il prodotto H. Questa struttura offre una buona panoramica delle parti e dei componenti dell'intero assemblaggio della macchina. Tuttavia, sebbene i progettisti possano preferire di vedere la DBA rappresentata in questo modo, questa struttura potrebbe non rappresentare correttamente in modo in cui la macchina viene costruita nello shop floor.

La DBA progettazione nella figura 1, ad esempio, indica che l'unità elettrica F viene assemblata come parte separata in un ordine di lavoro separato. Tuttavia, nello shop floor potrebbe risultare più ottimale assemblare l'unità elettrica come parte dell'intero assemblaggio della macchina, non come ordine di lavoro separato.

Questa DBA progettazione indica anche che la parte G è una parte separata. Tuttavia, in questa struttura la parte G non rappresenta una parte fisica ma una raccolta di materiali da imballaggio.

Di conseguenza, anche se una DBA progettazione ha immesso valore per la progettazione di un prodotto e la gestione di quel progetto, potrebbe non essere il modo più logico per supportare il processo di produzione del prodotto. Per contro, una DBA di produzione rappresenta il modo migliore per creare un prodotto.

La figura 2 mostra come la DBA progettazione precedente viene importata in una DBA di produzione. Nella figura 2, (a) è la DBA per il prodotto H e (b) è la scheda cicli di lavorazione per il prodotto H.

![Figura 2: distinta base di produzione.](media/product-H-part-B.png)
*Figura 2: distinta base di produzione*

In questa struttura, si noterà che non sono presenti nozioni delle parti F e G e i materiali di cui consistono queste parti sono stati elevati al livello successivo della DBA.

A differenza della DBA progettazione, che ha due prospetti operativi, la DBA di produzione ha un solo prospetto operativo. Anche l'operazione di imballaggio che è stata associata alla parte G è stata elevata e ora fa parte del prospetto operativo per il prodotto H. L'assemblaggio dell'unità elettrica è la prima operazione. Questo ordine è logico perché questa unità viene utilizzata nell'operazione successiva che è l'assemblaggio della macchina. L'ultima operazione è l'operazione di imballaggio, che utilizza due materiali di imballaggio (C e D).

La transizione tra la DBA progettazione e la DBA di produzione viene abilitata attraverso il tipo di riga di DBA fittizio. Come indica il termine" fittizio", le parti F e G sono scomparse durante la transizione tra i due tipi di DBA. In questo esempio, il tipo di riga fittizio viene applicato alle righe DBA per le parti F e G nella DBA progettazione. Quando viene creato un ordine batch o di produzione, la DBA progettazione viene copiata nell'ordine batch o di produzione. In seguito, quando l'ordine viene stimato, viene eseguita la transizione dalla DBA progettazione alla DBA di produzione, come mostrato nella figura 2. Dal prospetto operativo nella figura 2, i materiali di imballaggio C e D sono input per l'operazione.

## <a name="multilevel-phantom-bom-structures"></a>Strutture DBA fittizie multilivello

È possibile utilizzare il tipo di riga fittizio nelle strutture DBA multilivello, come mostrato nella figura 3. Nella figura 3, (a) è la DBA per il prodotto G e (b) è la scheda cicli di lavorazione per le parti E e F e il prodotto G.

![Figura 3: distinta base di progettazione parte G.](media/product-G.png)
*Figura 3: distinta base di progettazione parte G*

La figura 4 mostra la DBA di produzione e la scheda cicli di produzione risultanti se la righe DBA per le parti E e F vengono configurate con il tipo di riga fittizio. Nella figura 4, (a) è la DBA per il prodotto G e (b) è la scheda cicli di lavorazione per il prodotto G.

![Figura 4: distinta base di produzione parte G.](media/product-G-route-sheet-G.png)
*Figura 4: distinta base di produzione parte G*

## <a name="phantom-and-route-network"></a>Rete di cicli di lavorazione e fittizia

La DBA fittizia può essere utilizzata anche per una DBA con una rete di cicli di lavorazione. In una rete di cicli di lavorazione, una o più operazioni vengono eseguite in parallelo. La figura 5 mostra un esempio di una rete di cicli di lavorazione utilizzata in una distinta base multilivello. Nella figura 5, (a) è la DBA per il prodotto G e la parte F e (b) è la scheda cicli di lavorazione per il prodotto G e la parte F, che ha una rete di cicli di lavorazione.

![Figura 5: distinta base di progettazione parte G, rete di cicli.](media/product-G-part-F.png)
*Figura 5: distinta base di progettazione parte G, rete di cicli*

Nella figura 6, (a) è la DBA per il prodotto G e parte F (b) è la scheda cicli di lavorazione per il prodotto G e la parte di F.

![Figura 6: distinta base di produzione parte G, rete di cicli.](media/product-G-part-F-with-route-sheet.png)
*Figura 6: distinta base di produzione parte G, rete di cicli*


[!INCLUDE[footer-include](../../includes/footer-banner.md)]