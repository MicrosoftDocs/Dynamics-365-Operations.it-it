---
title: Reimposta sincronizzazione Dataverse
description: Questo argomento descrive come risolvere i problemi dei record che non si sincronizzano correttamente tra Microsoft Dynamics 365 Human Resources e la soluzione Gestione risorse umane (HCM) comune in Microsoft Dataverse.
author: jaredha
ms.date: 09/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-27
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 8bfcd51b023c02590919155abbb836326408d298
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8696237"
---
# <a name="reset-dataverse-synchronization"></a>Reimposta sincronizzazione Dataverse


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>Problema

I record non sono sincronizzati tra Microsoft Dynamics 365 Human Resources e le entità nella soluzione Gestione risorse umane (HCM) comune in Microsoft Dataverse. Per ulteriori informazioni sulla sincronizzazione, andare a [Configura integrazione Dataverse](hr-admin-integration-common-data-service.md). La mancata sincronizzazione corretta può verificarsi quando i processi batch **Nuovo tentativo di integrazione Dataverse** o **Sincronizzazione richiesta non eseguita per integrazione di Dataverse** sono bloccati in uno stato **In esecuzione**.

## <a name="resolution"></a>Risoluzione

Quando i processi batch **Nuovo tentativo di integrazione Dataverse** o **Sincronizzazione richiesta non eseguita per integrazione di Dataverse** sono bloccati in uno stato **In esecuzione** o **Annullamento**, è possibile reimpostare lo stato. Questa operazione può essere eseguita annullando il processo batch seguendo le indicazioni in [Reimpostare i processi batch bloccati](hr-admin-troubleshooting-batch-execution.md). Dopo aver annullato il processo batch, è possibile ripristinare il processo batch impostandolo su uno stato **In attesa**. Il processo batch verrà quindi eseguito durante la successiva fase di esecuzione programmata.

1. Se non è stato già fatto, abilitare la funzionalità **Interruzione batch avanzata** in **Gestione funzionalità**.
   1. Andare alla pagina **Gestione funzionalità** (**Amministrazione sistema** > **Riepilogo** > **Gestione funzionalità**).
   2. Selezionare la scheda **Tutto**.
   3. Selezionare la colonna **Nome funzionalità** e filtrare per **Interruzione batch avanzata**.
   4. Selezionare l'azione **Abilita** se non è già abilitata.

2. Disattivare l'integrazione di Dataverse.
   1. Andare alla pagina **Integrazione Microsoft Dataverse** (**Amministrazione sistema** andare a **Collegamenti** > **Integrazioni** > **Configurazione Dataverse**).
   2. Impostare **Abilita integrazione di Dataverse** su **No**.

3. Annullare il processo batch **Nuovo tentativo di integrazione Dataverse**.
   1. Andare alla pagina **Processi batch** (**Amministrazione sistema** andare a **Collegamenti** > **Processi batch** > **Processi batch**).
   2. Filtrare la colonna **Descrizione mansione** per **Integrazione**.
   3. Selezionare il processo batch **Nuovo tentativo di integrazione Dataverse**.
   4. Sulla barra multifunzione, selezionare **Processo batch**, **Forza annullamento**, quindi selezionare **Sì** per confermare.

   > [!NOTE]
   > A seconda di quando l'integrazione è stata abilitata per la prima volta, il processo batch potrebbe avere la descrizione **Nuovo tentativo di integrazione Common Data Service**. Selezionare questo processo batch se è elencato, anziché il processo batch **Nuovo tentativo di integrazione Dataverse**.

4. Eliminare tutti i processi batch di integrazione Dataverse.
   1. Nella pagina **Processi batch**, selezionare i processi batch **Sincronizzazione richiesta non eseguita per integrazione di Dataverse**, **Nuovo tentativo di integrazione Dataverse** e **Sincronizzazione iniziale integrazione Dataverse**.
   2. Sulla barra multifunzione, selezionare l'azione **Cambia stato**. 
   3. Selezionare **Trattenuto**, quindi **OK**.
   4. Sulla barra multifunzione, selezionare l'azione **Elimina**, quindi **Sì** per confermare l'azione.

5. Attivare i processi batch di integrazione Dataverse.
   1. Andare alla pagina **Integrazione Microsoft Dataverse** (**Amministrazione sistema** > **Collegamenti** > **Integrazione** > **Configurazione Dataverse**).
   2. Impostare **Abilita integrazione di Dataverse** su **Sì**.

6. Andare alla pagina **Processi batch** e confermare che i processi batch **Nuovo tentativo di integrazione Dataverse** e **Sincronizzazione richiesta non eseguita per integrazione di Dataverse** siano stati creati.

Con i processi batch ricreati, è ora possibile monitorare il processo batch **Nuovo tentativo di integrazione Dataverse** per vedere quanto tempo richiede l'esecuzione del processo. È quindi possibile verificare che i record si stiano sincronizzando correttamente con la soluzione HCM comune in Microsoft Dataverse.

## <a name="see-also"></a>Vedere anche

[Configurare l'integrazione di Dataverse](hr-admin-integration-common-data-service.md)<br>
[Reimpostare i processi batch bloccati](hr-admin-troubleshooting-batch-execution.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
