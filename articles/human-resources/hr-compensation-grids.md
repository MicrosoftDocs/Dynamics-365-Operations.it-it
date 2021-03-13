---
title: Impostare le griglie retributive
description: Le griglie retributive vengono utilizzate per definire e gestire le strutture di pagamento per i piani di retribuzione fissa.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13415f68f41555f3e86cbe699cf921e9a2cf6d5c
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113048"
---
# <a name="set-up-compensation-grids"></a>Impostare le griglie retributive

Le griglie retributive vengono utilizzate per definire e gestire le strutture di pagamento per i piani di retribuzione fissa. Le griglie retributive possono essere condivise tra più piani o essere copiate quando si crea un nuovo piano di retribuzione.  Prima della creazione della griglia retributiva, i livelli e i punti di riferimento devono essere impostati. In questo esempio si crea un nuovo tipo di grado di griglia retributiva utilizzando i dati dimostrativi per i livelli e i punti di riferimento. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="set-up-information-about-the-compensation-grid"></a>Impostare le informazioni sulla griglia retributiva
1. Andare a Risorse umane > Compensation > Retribuzione fissa > Griglie retributive.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Griglia.
4. Nel campo Descrizione digitare un valore.
5. Selezionare un'opzione nel campo Tipo.
6. Nel campo Impostazione riferimenti immettere o selezionare un valore.
7. Nel campo Valuta immettere o selezionare un valore.
8. Digitare un valore nel campo Valuta.
9. Nel campo Data di validità, immettere una data.

## <a name="add-levels-to-the-compensation-structure"></a>Aggiungere livelli alla struttura retributiva
1. Fare clic su Struttura retributiva.
2. Nell'elenco contrassegnare la riga selezionata.
3. Nel campo Livello immettere o selezionare un valore.
4. Fare clic su Nuovo.
5. Nell'elenco contrassegnare la riga selezionata.
6. Nel campo Livello immettere o selezionare un valore.
7. Fare clic su Nuovo.
8. Nell'elenco contrassegnare la riga selezionata.
9. Nel campo Livello immettere o selezionare un valore.
10. Fare clic su Nuovo.
11. Nell'elenco contrassegnare la riga selezionata.
12. Nel campo Livello immettere o selezionare un valore.
13. Fare clic su Nuovo.
14. Nell'elenco contrassegnare la riga selezionata.
15. Nel campo Livello immettere o selezionare un valore.

## <a name="fill-in-the-compensation-structure-with-values"></a>Compilare la struttura retributiva con valori
1. Nell'elenco contrassegnare la riga selezionata.
    * In questa fase, i valori di retribuzione possono essere immessi manualmente in ogni campo della tabella o la funzionalità di modifica di massa può essere utilizzata per completare facilmente più campi ed eseguire calcoli di base.  
2. Fare clic su Modifica in massa.
    * Per la griglia, è necessario applicare prima il valore del punto intermedio di primo livello a tutti i campi della tabella. Si tratta della base della matrice di retribuzione.  
3. Nel campo Tipo di rettifica selezionare un'opzione.
4. Nel campo Importo di rettifica immettere un numero.
5. Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.
6. Fare clic su Applica alla griglia.
    * Ora verrà utilizzata la funzione di modifica di massa per incrementare gli importi in ogni livello successivo di una percentuale o un importo determinato. In questo esempio, ogni grado avrà una distribuzione del 12,5% tra i punti intermedi.  
7. Nel campo Tipo di rettifica selezionare un'opzione.
8. Nel campo Importo di rettifica immettere un numero.
9. Trovare e selezionare il record desiderato nell'elenco.
10. Trovare e selezionare il record desiderato nell'elenco.
11. Trovare e selezionare il record desiderato nell'elenco.
12. Trovare e selezionare il record desiderato nell'elenco.
13. Fare clic su Applica alla griglia.
14. Trovare e selezionare il record desiderato nell'elenco.
15. Trovare e selezionare il record desiderato nell'elenco.
16. Trovare e selezionare il record desiderato nell'elenco.
17. Fare clic su Applica alla griglia.
18. Trovare e selezionare il record desiderato nell'elenco.
19. Trovare e selezionare il record desiderato nell'elenco.
20. Fare clic su Applica alla griglia.
21. Nell'elenco trovare e selezionare il record desiderato.
22. Fare clic su Applica alla griglia.
    * Ora verrà utilizzata la funzione di modifica di massa per rettificare i punti di riferimento minimo e massimo di ciascun livello. In questo esempio si utilizza una distribuzione del 50% in modo che il punto di riferimento minimo verrà rettificato a -20% e il massimo verrà rettificato a +20%.  
23. Nel campo Importo di rettifica immettere un numero.
24. Nel campo Punto di riferimento immettere o selezionare un valore.
25. Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.
26. Fare clic su Applica alla griglia.
27. Nel campo Importo di rettifica immettere un numero.
28. Nel campo Punto di riferimento immettere o selezionare un valore.
29. Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.
30. Fare clic su Applica alla griglia.

