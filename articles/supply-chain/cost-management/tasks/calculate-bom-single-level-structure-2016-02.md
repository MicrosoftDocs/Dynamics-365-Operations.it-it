---
title: Calcolare una DBA utilizzando una struttura a livello singolo (febbraio 2016)
description: In questa procedura viene illustrato come calcolare il costo di un prodotto finito utilizzando la esplosione a livello singolo basata sulla scheda di determinazione costi.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 22ed277d6f4dca3ab0a5be4ddba8982350c7e05ccbb6ade7313ac22b45fbecb1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772546"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a>Calcolare una DBA utilizzando una struttura a livello singolo (febbraio 2016)

[!include [banner](../../includes/banner.md)]

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
    * Può essere necessario fare clic sull'ellissi (...) per visualizzare l'opzione nel menu superiore.    La composizione del costo è come segue:  *    10 è derivato da ITEM_A, 10 da ITEM_B 10, 10 da BOM_2. In questo caso non sono presenti dettagli per BOM_2 perché è stato immesso come costo standard di 10 ma non è stato calcolato.  *    7 è derivato dal tempo di attrezzaggio, ovvero un costo costante e il 7 aggiuntivo è derivato dall'operazione del tempo di esecuzione (processo).  *    Sono previsti anche altri importi corrispondenti ai costi indiretti.  
9. @SysTaskRecorder:_RequestClose



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]