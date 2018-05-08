--- 
title: Monitorare un'esecuzione di pianificazione generale
description: "Il pianificatore di produzione desidera verificare se è in esecuzione una pianificazione generale."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1e08d9fd3388561563e6fb982416186a652b4ce2
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="monitor-a-master-planning-run"></a>Monitorare un'esecuzione di pianificazione generale

[!include [task guide banner](../../includes/task-guide-banner.md)]

Il pianificatore di produzione desidera verificare se è in esecuzione una pianificazione generale. Per completare questa procedura utilizzare la società di dati dimostrativi USMF.


## <a name="run-master-planning"></a>Eseguire la pianificazione generale
1. Fare clic su Pianificazione generale.
    * Apparirà sul dashboard predefinito.  
2. Nel campo Piano immettere o selezionare un valore.
    * Esempio: StaticPlan  
3. Fare clic su Esegui.
4. Selezionare Sì nel campo Traccia ora di elaborazione.
    * Se il campo è già selezionato, ignorare questo passaggio.  
5. Nel campo Numero di thread immettere un numero.
6. Espandere la sezione Record da includere.
7. Fare clic su Filtro.
8. Nell'elenco contrassegnare la riga selezionata.
    * Contrassegnare la riga con Campo = Numero articolo.  
9. Nel campo Criteri immettere o selezionare un valore.
    * Esempio: T0001  
10. Fare clic su OK.
11. Fare clic su OK.

## <a name="monitor-the-master-planning-run"></a>Monitorare l'esecuzione di pianificazione generale
1. Fare clic su Storico.
2. Fare clic su Richieste di informazioni.
3. Fare clic su Durata attività di processo.
4. Nell'elenco trovare e selezionare il record desiderato.
    * Per ogni articolo è possibile ottenere una panoramica del tempo necessario per completare ogni fase di pianificazione.  


