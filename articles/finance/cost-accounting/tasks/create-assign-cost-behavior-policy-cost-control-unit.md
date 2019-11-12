---
title: Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi
description: Il comportamento costo è la classificazione del costo come fisso o variabile.
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
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16d9dceb4c2a22eab9a5ecb8501393444f20498b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187822"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a>Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi

[!include [task guide banner](../../includes/task-guide-banner.md)]

Il comportamento costo è la classificazione del costo come fisso o variabile. Affinché i criteri diventino effettivi, i criteri e le regole corrispondenti devono essere assegnati a un'unità di controllo costi. Utilizzare questa procedura per creare i criteri e quindi per assegnarli a un'unità di controllo costi.


## <a name="create-a-cost-behavior-hierarchy"></a>Creare una gerarchia di comportamento costo
1. Andare a Contabilità industriale > Dimensioni > Gerarchie di dimensioni.
2. Fare clic su Nuovo.
3. Fare clic su Crea.
4. Nel campo Nome gerarchia dimensioni digitare "Gerarchia di comportamenti costo".
5. Nel campo Dimensione immettere o selezionare un valore.
    * Selezionare Elementi di costo.  
6. Fare clic su Salva.
7. Fare clic su Visualizza gerarchia.
8. Fare clic su Nuovo.
9. Digitare un valore nel campo Nome nodo.
    * Immettere il costo fisso.  
10. Nella struttura selezionare "Cost behavior hierarchy".
11. Fare clic su Nuovo.
12. Digitare un valore nel campo Nome nodo.
    * Immettere il costo variabile.  
13. Fare clic su Salva.
14. Nella struttura selezionare "Gerarchia di comportamenti costo\Costo fisso".
15. Fare clic su Nuovo.
16. Nell'elenco contrassegnare la riga selezionata.
17. Nel campo Membro di dimensione di inizio immettere o selezionare un valore.
    * L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.  
18. Nel campo Membro di dimensione di fine immettere o selezionare un valore.
    * L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.  
19. Nella struttura selezionare "Gerarchia di comportamenti costo\Costo variabile".
20. Fare clic su Nuovo.
21. Nell'elenco contrassegnare la riga selezionata.
22. Nel campo Membro di dimensione di inizio immettere o selezionare un valore.
    * L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.  
23. Nel campo Membro di dimensione di fine immettere o selezionare un valore.
    * L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.  
24. Fare clic su Salva.

## <a name="create-the-policy-and-rules"></a>Creare i criteri e le regole.
1. Andare a Contabilità industriale > Criteri > Criteri di comportamento costo.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome criteri.
4. Nel campo Gerarchia dimensioni di elemento di costo immettere o selezionare un valore.
    * Selezionare la gerarchia di criteri creata.  
5. Nel campo Gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
    * Selezionare Organizzazione.  
6. Fare clic su Salva.
7. Fare clic su Nuovo.
8. Nell'elenco contrassegnare la riga selezionata.
9. Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.
    * Espande la gerarchia per selezionare il costo variabile.  
10. Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
    * Per impostazione predefinita, la percentuale variabile è pari al 100%.  
11. Fare clic su Assegnazioni criteri per unità di controllo costi.
12. Fare clic su Nuovo.
13. Nell'elenco contrassegnare la riga selezionata.
14. Immettere una data nel campo Valido dalla data di registrazione.
    * Le regole hanno una data di validità e un utente o il sistema può farle scadere se ne viene creata una nuova versione.  
15. Nel campo Unità di controllo costi immettere o selezionare un valore.
16. Fare clic su Salva.
