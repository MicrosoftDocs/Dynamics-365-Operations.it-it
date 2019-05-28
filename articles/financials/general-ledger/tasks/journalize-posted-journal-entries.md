---
title: Inserire voci registrate nel giornale di registrazione
description: Questa procedura descrive come effettuare inserimenti nel giornale di registrazione.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b50809cf9eb59475856f91d9f1ddfe28ecfd8de6
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547912"
---
# <a name="journalize-posted-journal-entries"></a>Inserire voci registrate nel giornale di registrazione

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura descrive come effettuare inserimenti nel giornale di registrazione. Questa procedura utilizza la società di dati dimostrativi USMF.

1. Convalidare le impostazioni per l'inserimento nel giornale di registrazione in Contabilità generale > Impostazione contabilità generale > Parametri di contabilità generale.
2. Il campo Giornale di registrazione contabile esteso può essere impostato su Sì o No. Se Sì, l'output del report verrà diverso.
3. Selezionare se il periodo può essere chiuso se il processo di inserimento nel giornale di registrazione non è stato eseguito.
    * Se l'opzione è impostata su Sì, il periodo non può essere chiuso fino al completamento del processo di inserimento nel giornale do registrazione per il periodo.  
4. Chiudere la pagina.
5. Passare a Contabilità > Attività periodiche > Inserimento nel giornale di registrazione.
6. Fare clic su Filtro.
7. Evidenziare la riga con i criteri di filtro da definire.
8. Nel campo Criteri immettere o selezionare i criteri di filtro.
9. Scegliere OK per la pagina del filtro.
10. Scegliere OK per avviare il processo di inserimento nel giornale di registrazione.
    * Un report verrà generato dopo che il processo è completato.  

