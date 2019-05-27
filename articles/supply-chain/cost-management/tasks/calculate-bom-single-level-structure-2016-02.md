---
title: Calcolare una DBA utilizzando una struttura a livello singolo (febbraio 2016)
description: In questa procedura viene illustrato come calcolare il costo di un prodotto finito utilizzando la esplosione a livello singolo basata sulla scheda di determinazione costi.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f74f8e4efc4474693f0a5b543c1300c3b64ecda0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563229"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a>Calcolare una DBA utilizzando una struttura a livello singolo (febbraio 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come calcolare il costo di un prodotto finito utilizzando la esplosione a livello singolo basata sulla scheda di determinazione costi. Corrisponde alla sesta attività della serie di calcoli DBA. La società di dati dimostrativi utilizzata per creare questa attività è USMF.

1. Fare clic su Prodotti rilasciati.
2. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare la BOM_1 del prodotto.  
3. Nel riquadro azioni, fare clic su Gestisci costi.
4. Fare clic su Prezzo articolo.
5. Fare clic su Calcola costo articolo.
    * Può essere necessario fare clic sull'ellissi (...) per visualizzare l'opzione nel menu superiore.  
6. Nel campo Versione determinazione costi fare clic sul pulsante a discesa per aprire la ricerca.
    * Per questa dimostrazione, selezionare 10. Si tratta della versione di determinazione costi utilizzata per l'aggiunta del prezzo di costo ai componenti.  
7. Fare clic su OK.
8. Fare clic su Visualizza dettagli calcolo.
    * Può essere necessario fare clic sull'ellissi (...) per visualizzare l'opzione nel menu superiore.    La composizione del costo è come segue:  •    10 è derivato da ITEM_A, 10 da ITEM_B 10, 10 da BOM_2. In questo caso non sono presenti dettagli per BOM_2 perché è stato immesso come costo standard di 10 ma non è stato calcolato.  •  7 è derivato dal tempo di attrezzaggio, ovvero un costo costante e il 7 aggiuntivo è derivato dall'operazione del tempo di esecuzione (processo).  •   Sono previsti anche altri importi corrispondenti ai costi indiretti.  
9. @SysTaskRecorder:_RequestClose

