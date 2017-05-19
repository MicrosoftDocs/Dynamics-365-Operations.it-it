---
title: Utilizzare Importazione/esportazione rapida
description: "Lo scopo di Importazione/esportazione rapida è consentire di importare ed esportare con meno passaggi."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 2012 R3 CU8
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: f35e7b7d987d6caa19a32460259f07322f2b85cb
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="run-the-test-data-transfer-tool-beta-for-dynamics-ax-ax-2012"></a>Eseguire lo strumento di trasferimento di dati di test (beta) per Dynamics AX (AX 2012)

[!include[banner](../../includes/banner.md)]


Lo scopo di Importazione/esportazione rapida è consentire di importare ed esportare con meno passaggi.

Abbiamo aggiunto la funzionalità Importazione/esportazione rapida per consentire agli utenti di importare o esportare processi semplici che desiderano eseguire rapidamente. Idealmente, questa funzionalità viene utilizzata in scenari in cui un file viene automaticamente mappato al sistema e l'utente non deve eseguire mapping avanzati o creare ripetuti processi di importazione o esportazione.

-   Questa funzionalità supporta l'utilizzo sia di entità predefinite che personalizzate.
-   È possibile importare da file e, se si utilizza un'origine dati ODBC, è possibile selezionare una query da utilizzare per definire l'importazione.
-   È necessario avere precedentemente definito i formati di origine dati per AX o File e sapere dove si trovano.
-   Non è necessario creare un gruppo di elaborazione per l'utilizzo di Importazione/esportazione rapida, ne verrà automaticamente creato uno dal sistema quando viene eseguito il processo di importazione o esportazione. È inoltre possibile scegliere di mantenere lo storico dei dati importati da Importazione/esportazione rapida.

  Notare che Importazione/esportazione rapida presuppone che si abbia familiarità con i concetti di DIXF.




