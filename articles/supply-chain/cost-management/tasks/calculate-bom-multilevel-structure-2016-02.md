---
title: Calcolare una DBA utilizzando una struttura a più livelli (febbraio 2016)
description: In questa procedura viene illustrato come calcolare il costo di un prodotto finito utilizzando la esplosione multilivello basata sulla scheda di determinazione costi.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog, BOMCalcTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f0ec28a20d32fc38cd6e77a76a02fc9544db3ca
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431227"
---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016"></a>Calcolare una DBA utilizzando una struttura a più livelli (febbraio 2016)

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]