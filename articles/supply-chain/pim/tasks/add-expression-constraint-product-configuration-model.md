--- 
title: Aggiungere un vincolo di espressione a un modello di configurazione prodotto
description: In questa procedura vengono descritti i passaggi per aggiungere una nuova espressione di vincolo a un modello di configurazione prodotto.
author: YuyuScheller
manager: AnnBe
ms.date: 10/27/2016
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
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: b8286eba5c799789ebba9a501a5a0b06ccdaabb1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Aggiungere un vincolo di espressione a un modello di configurazione prodotto

[!include[task guide banner](../../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per aggiungere una nuova espressione di vincolo a un modello di configurazione prodotto. Indica come è possibile impostare come obbligatorio che la protezione angolare deve essere applicata a un altoparlante se l'utente ha selezionato che la griglia anteriore è in metallo. La procedura utilizza il componente High end speaker nella società di dati dimostrativi USMF.


## <a name="create-an-expression-constraint"></a>Creare un vincolo di espressione
1. Fare clic su Definizione modello di variante prodotto.
2. Fare clic su Modelli di configurazione prodotto.
3. Nell'elenco trovare e selezionare il record desiderato.
    * In questo esempio viene utilizzato il modello High end speaker.  
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Espandere la sezione Vincoli.
6. Scegliere Aggiungi.
7. Fare clic su Crea.
8. Digitare un valore nel campo Nome.

## <a name="enter-expression"></a>Immetti espressione
1. Fare clic su Modifica espressione.
    * Se si sblocca l'interfaccia utente nella registrazione attività in questa fase, è possibile utilizzare IntelliSense e l'elenco dei simboli per creare l'espressione del vincolo.  
2. Nel campo ConstraintBody, immettere 'Implies[FrontGrill=="Metal", CornerProtection] '.
    * La logica dell'espressione dice: se la griglia anteriore è in metallo, è necessario selezionare l'opzione di protezione angolare.  
3. Fare clic su Convalida.
    * La funzione di convalida viene eseguita tramite l'espressione di vincolo e controllata per la presenza di errori di sintassi.  
4. Fare clic su Chiudi.
5. Fare clic su OK.


