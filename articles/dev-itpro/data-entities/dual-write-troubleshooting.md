---
title: Guida alla risoluzione dei problemi di integrazione dei dati
description: In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione dei dati tra Microsoft Dynamics 365 for Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: ca62a6b3aa64ec2383ee3ded3b7bbf4650a41166
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797277"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Guida alla risoluzione dei problemi di integrazione dei dati

## <a name="enable-plugin-trace-in-common-data-service-and-check-the-dual-write-plugin-error-details"></a>Abilitare Traccia plug-in in Common Data Service e controllare i dettagli degli errori del plug-in di doppia scrittura

Se si verifica un problema o errore con la sincronizzazione della doppia scrittura, è possibile analizzare gli errori nel Registro di traccia:

1. Prima di poter analizzare gli errori, è necessario abilitare Traccia plug-in usando le istruzioni in [Registrare il plug-in](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs). A questo punto è possibile analizzare gli errori.
2. Accedere a Dynamics 365 for Sales
3. Fare clic sull'icona delle impostazioni (ingranaggio) e selezionare **Impostazioni avanzate**.
4. Nel menu **Impostazioni**, scegliere **Personalizzazione > Registro di traccia plug-in**.
5. Fare clic sul nome del tipo **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** per visualizzare i dettagli di errore.

## <a name="check-dual-write-synchronization-errors-in-finance-and-operations"></a>Controllare gli errori di doppia scrittura in Finance and Operations

È possibile controllare gli errori durante il test seguendo queste operazioni:

+ Accedere a Lifecycle Services (LCS).
+ Apri progetto LCS su cui si è scelto di eseguire il test di doppia scrittura.
+ Andare a Distribuzione ambienti ospitati nel cloud.
+ Desktop remoto in VM Finance and Operations utilizzando l'account locale visualizzato in LCS.
+ Apri il visualizzatore eventi. 
+ Spostarsi a **Registri applicazioni e servizi > Microsoft > Dynamics > > AX- DualWriteSync > Operativo**. Gli errori e i dettagli vengono visualizzati.

## <a name="how-to-unlink-and-link-another-common-data-service-environment-from-finance-and-operations"></a>Come scollegare e collegare un altro ambiente Common Data Service da Finance and Operations

È possibile aggiornare i collegamenti effettuando le seguenti operazioni:

+ Passare all'ambiente Finance and Operations.
+ Aprire Gestione dati.
+ Fare clic su **Collega a CDS per le app**.
+ Selezionare tutti i mapping in esecuzione e fare clic su **Interrompi**. 
+ Selezionare tutti i mapping e fare clic su **Elimina**.

    > [!NOTE]
    > L'opzione **Elimina** non verrà visualizzato se il modello **CustomerV3-Account** è selezionato. Deselezionarlo se necessario. **CustomerV3-Account** è un modello meno recente fornito e funziona con la soluzione Prospect to Cash. Poiché è rilasciato globalmente, appare sotto tutti i modelli.

+ Scegliere **Scollega ambiente**.
+ Fare clic su **Sì** per la conferma.
+ Per collegare il nuovo ambiente, seguire i passaggi nella [guida all'installazione](https://aka.ms/dualwrite-docs).

