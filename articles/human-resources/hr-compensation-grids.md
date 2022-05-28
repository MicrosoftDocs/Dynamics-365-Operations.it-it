---
title: Impostare le griglie retributive
description: Le griglie retributive vengono utilizzate per definire e gestire le strutture di pagamento per i piani di retribuzione fissa.
author: twheeloc
ms.date: 01/03/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView, HcmCompensationWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9119c15cf80b9ebb9bed83ac438f24249aa4aa2f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691675"
---
# <a name="set-up-compensation-grids"></a>Impostare le griglie retributive


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Le griglie retributive vengono utilizzate per definire e gestire le strutture di pagamento per i piani di retribuzione fissa. Le griglie retributive possono essere condivise tra più piani o essere copiate quando si crea un nuovo piano di retribuzione.  Prima della creazione della griglia retributiva, i livelli e i punti di riferimento devono essere impostati. In questo esempio si crea un nuovo tipo di grado di griglia retributiva utilizzando i dati dimostrativi per i livelli e i punti di riferimento. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="set-up-information-about-the-compensation-grid"></a>Impostare le informazioni sulla griglia retributiva
1. Vai a **Risorse umane** > **Retribuzione** > **Retribuzione fissa** > **Griglie retributive**.
2. Fare clic su **Nuovo**.
3. Digita un valore nel campo **Griglia**.
4. Digitare un valore nel campo **Descrizione**
5. Selezionare un'opzione nel campo **Tipo**.
6. Nel campo **Impostazione riferimenti** immetti o seleziona un valore.
7. Nel campo **Valuta** immettere o selezionare un valore.
8. Nel campo **Data di validità**, immettere una data.

## <a name="add-levels-to-the-compensation-structure"></a>Aggiungere livelli alla struttura retributiva
1. Fai clic su **Struttura retributiva**.
2. Nell'elenco contrassegnare la riga selezionata.
3. Nel campo **Livello** immetti o seleziona un valore.
4. Fare clic su **Nuovo**.
5. Nell'elenco contrassegnare la riga selezionata.
6. Nel campo **Livello** immetti o seleziona un valore.
7. Fare clic su **Nuovo**.
8. Nell'elenco contrassegnare la riga selezionata.
9. Nel campo **Livello** immetti o seleziona un valore.
10. Fare clic su **Nuovo**.
11. Nell'elenco contrassegnare la riga selezionata.
12. Nel campo **Livello** immetti o seleziona un valore.
13. Fare clic su **Nuovo**.
14. Nell'elenco contrassegnare la riga selezionata.
15. Nel campo **Livello** immetti o seleziona un valore.

## <a name="fill-in-the-compensation-structure-with-values"></a>Compilare la struttura retributiva con valori
1. Nell'elenco contrassegnare la riga selezionata.
    * In questa fase, i valori di retribuzione possono essere immessi manualmente in ogni campo della tabella o la funzionalità di modifica di massa può essere utilizzata per completare facilmente più campi ed eseguire calcoli di base.  
2. Fai clic su **Modifica in massa**.
    * Per la griglia, è necessario applicare prima il valore del punto intermedio di primo livello a tutti i campi della tabella. Si tratta della base della matrice di retribuzione.  
3. Nel campo **Tipo di rettifica** seleziona un'opzione.
4. Nel campo **Importo di rettifica** immettere un numero.
5. Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.
6. Fare clic su **Applica alla griglia**.
    * Ora verrà utilizzata la funzione di modifica di massa per incrementare gli importi in ogni livello successivo di una percentuale o un importo determinato. In questo esempio, ogni grado avrà una distribuzione del 12,5% tra i punti intermedi.  
7. Nel campo **Tipo di rettifica** seleziona un'opzione.
8. Nel campo **Importo di rettifica** immettere un numero.
9. Nell'elenco trovare e selezionare il record desiderato.
10. Fare clic su **Applica alla griglia**.
    * Ora verrà utilizzata la funzione di modifica di massa per rettificare i punti di riferimento minimo e massimo di ciascun livello. In questo esempio si utilizza una distribuzione del 50% in modo che il punto di riferimento minimo verrà rettificato a -20% e il massimo verrà rettificato a +20%.  
11. Nel campo **Importo di rettifica** immettere un numero.
12. Nel campo **Punto di riferimento** immetti o seleziona un valore.
13. Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.
14. Fare clic su **Applica alla griglia**.
15. Nel campo **Importo di rettifica** immettere un numero.
16. Nel campo **Punto di riferimento** immetti o seleziona un valore.
17. Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.
18. Fare clic su **Applica alla griglia**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
