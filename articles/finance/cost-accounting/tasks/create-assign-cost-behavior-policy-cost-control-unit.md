---
title: Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi
description: Il comportamento costo è la classificazione del costo come fisso o variabile.
author: twheeloc
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostBehaviorRule
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 653bfb69c4ca118c700755cb95a6b349d2c6bbad
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735144"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a>Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi

[!include [banner](../../includes/banner.md)]

Il comportamento costo è la classificazione del costo come fisso o variabile. Affinché i criteri diventino effettivi, i criteri e le regole corrispondenti devono essere assegnati a un'unità di controllo costi. Utilizzare questa procedura per creare i criteri e quindi per assegnarli a un'unità di controllo costi.


## <a name="create-a-cost-behavior-hierarchy"></a>Creare una gerarchia di comportamento costo
1. Andare a **Contabilità industriale > Dimensioni > Gerarchie di dimensioni**.
2. Fare clic su **Nuovo**.
3. Fare clic su **Crea**.
4. Nel campo **Nome gerarchia dimensioni** digitare "Gerarchia di comportamenti costo".
5. Nel campo **Dimensione** immettere o selezionare un valore.
    * Selezionare Elementi di costo.  
6. Fare clic su **Salva**.
7. Fare clic su **Visualizza gerarchia**.
8. Fare clic su **Nuovo**.
9. Nel campo **Nome nodo** digitare un valore.
    * Immettere il costo fisso.  
10. Nella struttura selezionare "Cost behavior hierarchy".
11. Fare clic su **Nuovo**.
12. Nel campo **Nome nodo** digitare un valore.
    * Immettere il costo variabile.  
13. Fare clic su **Salva**.
14. Nella struttura selezionare "Gerarchia di comportamenti costo\Costo fisso".
15. Fare clic su **Nuovo**.
16. Nell'elenco contrassegnare la riga selezionata.
17. Nel campo **Membro di dimensione di inizio** immettere o selezionare un valore.
    * L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.  
18. Nel campo **Membro di dimensione di fine** immettere o selezionare un valore.
    * L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.  
19. Nella struttura selezionare "Gerarchia di comportamenti costo\Costo variabile".
20. Fare clic su **Nuovo**.
21. Nell'elenco contrassegnare la riga selezionata.
22. Nel campo **Membro di dimensione di inizio** immettere o selezionare un valore.
    * L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.  
23. Nel campo **Membro di dimensione di fine** immettere o selezionare un valore.
    * L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.  
24. Fare clic su **Salva**.

## <a name="create-the-policy-and-rules"></a>Creare i criteri e le regole.
1. Andare a **Contabilità industriale > Criteri > Criteri di comportamento costo**.
2. Fare clic su **Nuovo**.
3. Nel campo **Nome criteri** digitare un valore.
4. Nel campo **Gerarchia dimensioni di elemento di costo** immettere o selezionare un valore.
    * Selezionare la gerarchia di criteri creata.  
5. Nel campo **Gerarchia dimensioni di oggetto di costo** immettere o selezionare un valore.
    * Selezionare Organizzazione.  
6. Fare clic su **Salva**.
7. Fare clic su **Nuovo**.
8. Nell'elenco contrassegnare la riga selezionata.
9. Nel campo **Nodo gerarchia dimensioni di elemento di costo** immettere o selezionare un valore.
    * Espande la gerarchia per selezionare il costo variabile.  
10. Nel campo **Nodo gerarchia dimensioni di oggetto di costo** immettere o selezionare un valore.
    * Per impostazione predefinita, la percentuale variabile è pari al 100%.  
11. Fare clic su **Assegnazioni criteri per unità di controllo costi**.
12. Fare clic su **Nuovo**.
13. Nell'elenco contrassegnare la riga selezionata.
14. Nel campo **Valido dalla data di registrazione** immettere una data.
    * Le regole hanno una data di validità e un utente o il sistema può farle scadere se ne viene creata una nuova versione.  
15. Nel campo **Unità di controllo costi** immettere o selezionare un valore.
16. Fare clic su **Salva**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
