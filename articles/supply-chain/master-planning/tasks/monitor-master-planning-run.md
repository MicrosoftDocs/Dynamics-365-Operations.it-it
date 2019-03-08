---
title: Monitorare un'esecuzione di pianificazione generale
description: Il pianificatore di produzione desidera verificare se è in esecuzione una pianificazione generale.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c2e158d8cbad1f5d4f377f6a8eb43487b34ffdc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "367503"
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

