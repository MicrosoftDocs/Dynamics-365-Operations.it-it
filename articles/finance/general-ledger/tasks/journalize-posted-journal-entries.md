---
title: Inserire voci registrate nel giornale di registrazione
description: Questa procedura descrive come effettuare inserimenti nel giornale di registrazione.
author: aprilolson
manager: AnnBe
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f50ee568df492bcd811d2fefb1784bb55b50384b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444713"
---
# <a name="journalize-posted-journal-entries"></a>Inserire voci registrate nel giornale di registrazione

[!include [banner](../../includes/banner.md)]

Questa procedura descrive come effettuare inserimenti nel giornale di registrazione. Questa procedura utilizza la società di dati dimostrativi USMF.

1. Nel **pannello di navigazione** andare a **Moduli > Contabilità generale > Impostazione contabilità generale > Parametri di contabilità generale**.
2. Il campo **Giornale di registrazione contabile esteso** può essere impostato su Sì o No. Se Sì, l'output del report verrà diverso.
3. Selezionare se il periodo può essere chiuso se il processo di inserimento nel giornale di registrazione non è stato eseguito. Se l'opzione è impostata su Sì, il periodo non può essere chiuso fino al completamento del processo di inserimento nel giornale do registrazione per il periodo.  
4. Chiudere la pagina.
5. Nel **pannello di navigazione** andare a **Moduli > Contabilità generale > Attività periodiche > Inserimento nel giornale di registrazione**.
6. Fare clic su **Filtro**.
7. Evidenziare la riga con i criteri di filtro da definire.
8. Nel campo **Criteri** immettere o selezionare i criteri di filtro.
9. Scegliere **OK** per la pagina del filtro.
10. Scegliere **OK** per avviare il processo di inserimento nel giornale di registrazione. Un report verrà generato dopo che il processo è completato.  

