---
title: Inserire voci registrate nel giornale di registrazione
description: Questa procedura descrive come effettuare inserimenti nel giornale di registrazione.
author: aprilolson
ms.date: 03/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8fca167563b14c825ebe29874c6488ddfb4d9a
ms.sourcegitcommit: 06acdfbccd7bd213a2397ea7b85d104f01914437
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2022
ms.locfileid: "8400877"
---
# <a name="journalize-posted-journal-entries"></a>Inserire voci registrate nel giornale di registrazione

[!include [banner](../../includes/banner.md)]

Il processo di inserimento nel giornale di registrazione nella contabilità generale fornisce una modalità di raggruppamento e report sui giustificativi registrati per la contabilità generale. In base ai criteri forniti, l'elaborazione genera un elenco di giustificativi che usa una sequenza con numeri univoci e che ha un valore di contabilità generale **Numero del giornale di registrazione** come riferimento.

Attenersi alla seguente procedura per effettuare inserimenti nel giornale di registrazione. Questa procedura utilizza la società di dati dimostrativi **USMF**.

1. Selezionare **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**.
2. Immettere o selezionare un valore nel campo **Giornale di registrazione contabile esteso**. Se selezioni **Sì**, l'output del report sarà differente.
3. Selezionare se il periodo può essere chiuso se il processo di inserimento nel giornale di registrazione non è stato eseguito. Se selezioni **Sì**, il periodo non può essere chiuso fino al completamento del processo di inserimento nel giornale di registrazione per il periodo.
4. Chiudi la pagina.
5. Vai a **Contabilità generale** \> **Attività periodiche** \> **Inserimento nel giornale di registrazione** e seleziona **Filtro**.
6. Seleziona la riga per il criterio dei filtri che desideri definire.
7. Nel campo **Criteri** immettere o selezionare i criteri di filtro.
8. Selezionare **OK** per chiudere la pagina.
9. Seleziona **OK** per avviare il processo di inserimento nel giornale di registrazione. Un report verrà generato dopo che il processo è completato.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
