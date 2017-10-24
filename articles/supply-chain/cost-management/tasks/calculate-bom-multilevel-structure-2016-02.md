--- 
title: "Calcolare una DBA utilizzando una struttura a più livelli (solo febbraio 2016)"
description: In questa procedura viene illustrato come calcolare il costo di un prodotto finito utilizzando la esplosione multilivello basata sulla scheda di determinazione costi.
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 16c2cacaf70df5455c3ed49b8dcb5756e89f8cb8
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016-only"></a>Calcolare una DBA utilizzando una struttura a più livelli (solo febbraio 2016)

[!include[task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come calcolare il costo di un prodotto finito utilizzando la esplosione multilivello basata sulla scheda di determinazione costi. Corrisponde alla settima attività della serie di calcoli DBA. La società di dati dimostrativi utilizzata per creare questa attività è USMF.

1. Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.
2. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare la BOM_1 del prodotto.  
3. Nel riquadro azioni, fare clic su Gestisci costi.
4. Fare clic su Prezzo articolo.
5. Fare clic su Calcola costo articolo.
    * Può essere necessario fare clic sull'ellissi (...) per visualizzare l'opzione nel menu superiore.  
6. Nel campo Versione determinazione costi immettere o selezionare un valore.
    * Selezionare Versione determinazione costi 20 perché il tipo Costo pianificato e Modalità esplosione è Multilivello.   La modalità di esplosione Multilivello è per i costi pianificati e le simulazioni. Non viene utilizzata per i costi standard.  
7. Fare clic su OK.
8. Fare clic su Visualizza dettagli calcolo.
    * Può essere necessario fare clic sull'ellissi (...) per visualizzare l'opzione nel menu superiore.  In questo caso, si noti come BOM_2 è stato calcolata considerando le materie prime, il processo e i costi generali con un totale di 29,40 anziché il costo standard di 10 che è stato attivato nella guida attività iniziale nella serie.  
9. Fare clic sulla Scheda di determinazione costi.
    * Passando alla Scheda di determinazione costi, i totali per gruppo di costi sono diversi rispetto al calcolo effettuato nella guida attività precedente.  
10. Nel campo Livello selezionare 'Multiplo'.
    * Quando si seleziona Multiplo, i costi vengono classificati in base alla composizione di BOM_2, dove 10 deriva dal gruppo di costi M1 (ITEM_C) e 15,60 deriva dalla fabbricazione dove il gruppo di costi è L2. Anche i costi indiretti variano.  
11. Chiudere la pagina.
12. Chiudere la pagina.


