---
title: Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi
description: Le regole di distribuzione costi vengono utilizzate per distribuire i costi conteggiati finanziariamente in un centro di costo collettivo.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostDistributionRule
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e581ca4d5c06e015ef815c78f49f8c731e43c160
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2022
ms.locfileid: "8565791"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a>Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi

[!include [banner](../../includes/banner.md)]

Le regole di distribuzione costi vengono utilizzate per distribuire i costi conteggiati finanziariamente in un centro di costo collettivo. Il contabile deve verificare che il costo sia distribuito ai centri di costo a seconda della base di allocazione selezionata. I criteri e le regole corrispondenti vengono assegnati a un'unità di controllo dei costi. In questa guida attività viene utilizzato un esempio per mostrare come creare criteri di distribuzione dei costi e le regole corrispondenti.


## <a name="create-a-policy"></a>Creare un criterio
1. Andare a Contabilità industriale > Criteri > Criteri di distribuzione costi.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome criteri.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
    * Selezionare Organizzazione.  
6. Nel campo Gerarchia dimensioni di elemento di costo immettere o selezionare un valore.
    * Selezionare CDS P/L.  
7. Nel campo Dimensione statistica immettere o selezionare un valore.
    * Selezionare Elementi statistici.  
8. Fare clic su Salva.

## <a name="create-rules-for-the-policy"></a>Creare regole per i criteri
1. Fare clic su Nuovo.
2. Nell'elenco contrassegnare la riga selezionata.
3. Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
    * Espande la gerarchia per selezionare 094.  
4. Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.
    * Selezionare Altri costi operativi, quindi selezionare 605110 Pulizia.  
5. Nel campo Comportamento costo selezionare un'opzione.
    * Selezionare Costo fisso  
6. Nel campo Base di allocazione immettere o selezionare un valore.
7. Fare clic su Nuovo.
8. Nell'elenco contrassegnare la riga selezionata.
9. Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
    * Espande la gerarchia per selezionare 094.  
10. Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.
    * Selezionare Altri costi operativi, quindi selezionare 605150 Affitto.  
11. Nel campo Comportamento costo selezionare un'opzione.
    * Selezionare Costo fisso  
12. Nel campo Base di allocazione immettere o selezionare un valore.
13. Fare clic su Salva.

## <a name="assign-rules-to-a-cost-control-unit"></a>Assegnare regole a un'unità di controllo costi
1. Fare clic su Assegnazioni criteri per unità di controllo costi.
2. Fare clic su Nuovo.
3. Nell'elenco contrassegnare la riga selezionata.
4. Immettere una data nel campo Valido dalla data di registrazione.
    * Selezionare il 1° settembre nell'anno fiscale valido.  
5. Nel campo Unità di controllo costi immettere o selezionare un valore.
6. Fare clic su Salva.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]