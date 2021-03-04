---
title: Creare criteri di rollup costi
description: In questa procedura viene illustrato come creare i criteri di rollup dei costi e le regole per i criteri.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b6d32cc2c1844c6c334dd00b249c736e153f13d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444921"
---
# <a name="create-a-cost-rollup-policy"></a>Creare criteri di rollup costi

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come creare i criteri di rollup dei costi e le regole per i criteri. La società di dati dimostrativi utilizzata per creare questa procedura è USP2.


## <a name="create-a-policy"></a>Creare un criterio
1. Andare a Contabilità industriale > Criteri > Criteri rollup costi.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome criteri.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
    * Selezionare Rollup costi CC.  
6. Nel campo Gerarchia dimensioni di elemento di costo immettere o selezionare un valore.
    * Selezionare Rollup costi CC.  
7. Fare clic su Salva.

## <a name="create-rules-for-the-cost-rollup-policy"></a>Creare regole per i criteri di rollup costi
1. Fare clic su Nuovo.
2. Nell'elenco contrassegnare la riga selezionata.
3. Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
    * Selezionare 007.  
4. Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.
    * Selezionare Rollup costi CE.  
5. Nel campo Elemento di costo secondario immettere o selezionare un valore.
    * Per questo esempio, mappare l'elemento di costo secondario CC-007 al centro di costo.  
6. Fare clic su Nuovo.
7. Nell'elenco contrassegnare la riga selezionata.
8. Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
    * Selezionare 008.  
9. Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.
    * Selezionare Rollup costi CE.  
10. Nel campo Elemento di costo secondario immettere o selezionare un valore.
    * Per questo esempio, mappare l'elemento di costo secondario CC-008 al centro di costo.  
11. Fare clic su Nuovo.
12. Nell'elenco contrassegnare la riga selezionata.
13. Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
    * Selezionare 009.  
14. Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.
    * Selezionare Rollup costi CE.  
15. Nel campo Elemento di costo secondario immettere o selezionare un valore.
    * Per questo esempio, mappare l'elemento di costo secondario CC-009 al centro di costo.  
    * Continuare finché tutti i centri di costo sono mappati agli elementi di costo secondari corrispondenti.  
16. Fare clic su Salva.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]