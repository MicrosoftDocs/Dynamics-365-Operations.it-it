---
title: Attivare il processo di retribuzione per orario e presenze
description: In questa procedura viene illustrato come abilitare il processo di retribuzione per orario e presenze.
author: johanhoffmann
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 16d8fc2120dfb7b356b238957019a29d05963f9a
ms.contentlocale: it-it
ms.lasthandoff: 02/06/2018

---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a>Attivare il processo di retribuzione per orario e presenze

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come abilitare il processo di retribuzione per orario e presenze. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-a-pay-type-with-a-related-pay-rate"></a>Crea un tipo di retribuzione con una tariffa retributiva correlata
1. Orario e presenze > Impostazioni > Retribuzioni > Tipi di retribuzione
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Tipo di retribuzione.
4. Nel campo Descrizione digitare un valore.
5. Fare clic su Salva.
6. Fare clic su Tariffe.
    * Le tariffe per i tipi di retribuzione vengono impostate per intervalli di tempo specifici ed è possibile definire tariffe specifiche per i lavoratori. Non è sempre necessario creare le tariffe per i tipi di retribuzione in Orario e presenze. È possibile infatti che questa informazione sia già disponibile nel sistema di gestione utilizzato per generare le retribuzioni.  
7. Fare clic su Nuovo.
8. Nell'elenco contrassegnare la riga selezionata.
9. Nel campo Tariffa immettere un numero.
10. Fare clic su Salva.

## <a name="create-a-pay-agreement"></a>Creare un accordo salariale
1. Chiudere la pagina.
2. Chiudere la pagina.
3. Fare clic su Accordi salariali.
    * Orario e presenze > Impostazioni > Accordi salariali  
4. Fare clic su Nuovo.
5. Nel campo Accordo salariale digitare un valore.
6. Nel campo Descrizione digitare un valore.
7. Fare clic su Salva.
8. Fare clic su Righe accordo.
9. Fare clic su Nuovo.
10. Nell'elenco contrassegnare la riga selezionata.
11. Nel campo Tipo profilo immettere o selezionare un valore.
12. Nel campo Tipo di retribuzione immettere o selezionare un valore.

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a>Impostare l'accordo salariale per il lavoratore per la registrazione e le ore
1. Chiudere la pagina.
2. Chiudere la pagina.
3. Fare clic su Lavoratori per registrazione ore.
    * Orario e presenze > Impostazioni > Lavoratori per registrazione ore  
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Fare clic sulla scheda Impiego.
6. Espandere la sezione Registrazione ore.
7. Fare clic su Modifica.
8. Nel campo Accordo salariale immettere o selezionare un valore.

