--- 
title: Creare un ordine fornitore disciplinato dal budget
description: Utilizzare questa procedura per creare un ordine fornitore controllato in relazione al budget disponibile.
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: f9b82db94d98fb19c67888a1f8a35b2fe62c98fe
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-purchase-order-governed-by-budget"></a>Creare un ordine fornitore disciplinato dal budget

[!include[task guide banner](../../includes/task-guide-banner.md)]

Utilizzare questa procedura per creare un ordine fornitore controllato in relazione al budget disponibile. Questa registrazione utilizza i dati dimostrativi della società USMF.


## <a name="review-the-budget-control-configuration"></a>Esaminare la configurazione di controllo del budget
1. Andare a Impostazioni budget > Setup > Controllo del budget > Configurazione controllo del budget.
2. Fare clic sulla scheda Fondi budget disponibili.
3. Fare clic sulla scheda Documenti e giornali di registrazione.
4. Fare clic sulla scheda Definisci regole di controllo del budget.
5. Fare clic sulla scheda Definisci i gruppi di budget.
6. Chiudere la pagina.

## <a name="create-the-purchase-order-header"></a>Creare l'intestazione ordine fornitore
1. Andare ad Approvvigionamento > Ordini fornitore> Tutti gli ordini fornitore.
2. Fare clic su Nuovo.
3. Nel campo Conto fornitore, immettere o selezionare un valore.
4. Espandere la sezione Generale.
5. Nel campo Data di registrazione impostare la data '2016-01-01'.
6. Fare clic su OK.

## <a name="add-a-purchase-order-line"></a>Aggiungere una riga ordine fornitore
1. Nel campo Categoria di approvvigionamento immettere o selezionare un valore.
2. Imposta la quantità su '2'.
3. Nel campo Unità immettere o selezionare un valore.
4. Impostare il prezzo unitario su '10000'.
5. Fare clic su Dati finanziari.
6. Fare clic su Distribuisci importi.
7. Nel campo Conto CoGe specificare il valore '601300-001-023--'.
8. Chiudere la pagina.

## <a name="perform-budget-checking"></a>Esegui verifica budget
1. Fare clic su Dati finanziari.
2. Fare clic su Esegui verifica budget.
3. Fare clic su Dati finanziari.
4. Fare clic su Errori o avvisi verifica budget.
5. Fare clic su Chiudi.


