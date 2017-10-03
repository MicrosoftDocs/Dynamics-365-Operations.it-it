--- 
title: Dividere un cespite
description: "Questa guida attività suddividerà una percentuale di un libro cespiti in un nuovo libro cespiti."
author: saraschi2
manager: AnnBe
ms.date: 10/19/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5aea1aab9f6b084bd0c5bd2119639bff3555bb8a
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="split-a-fixed-asset"></a>Dividere un cespite

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa guida attività suddividerà una percentuale di un libro cespiti in un nuovo libro cespiti.  Utilizza il ruolo Ragioniere e i dati dimostrativi USMF.


## <a name="create-a-new-fixed-asset"></a>Crea un nuovo cespite
1. Passare a Cespiti > Cespiti > Cespiti.
2. Fare clic su Nuovo.
3. Nel campo Cespiti immettere o selezionare un valore.
4. Si noti il numero cespite da utilizzare successivamente nel processo di divisione.
5. Digitare un valore nel campo Nome.
6. Chiudere il modulo.

## <a name="split-a-fixed-asset"></a>Dividere un cespite
1. Nell'elenco, individuare e selezionare il cespite da dividere.
2. Nell'elenco fare clic sul collegamento nella riga selezionata.
3. Fare clic su Libri.
    * Selezionare il libro per la divisione in base al nuovo cespite.  
4. Fare clic su Funzioni.
5. Fare clic su Dividi cespite.
6. Nel campo A cespite immettere o selezionare un valore.
7. Nel campo Al libro fare clic sul pulsante a discesa per aprire la ricerca.
8. Nel campo Data della transazione immettere una data.
9. Nel campo Percentuale immettere un numero.
10. Nel campo Nome giornale di registrazione immettere o selezionare un valore.
11. Fare clic su OK.

## <a name="post-the-journal-transaction"></a>Registrare la transazione del giornale di registrazione
1. Andare a Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti.
2. Nell'elenco, selezionare il giornale di registrazione creato con il processo di divisione.
3. Fare clic su Righe.
    * Verificare le righe del giornale di registrazione create.  Una transazione di rettifica acquisizione viene creata per il cespite originario per diminuire il valore della percentuale specificata durante il processo di divisione.  Una transazione di acquisizione viene creata per il nuovo cespite per lo stesso importo.  
4. Fare clic su Registra.


