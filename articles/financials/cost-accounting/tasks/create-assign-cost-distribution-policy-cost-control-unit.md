--- 
title: "Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi"
description: Le regole di distribuzione costi vengono utilizzate per distribuire i costi conteggiati finanziariamente in un centro di costo collettivo.
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 492e4a94ec0caef8c51a691043a1ffb9e6a04758
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a>Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


