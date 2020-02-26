---
title: Configurare l'integrazione di Common Data Service
description: È possibile attivare o disattivare l'integrazione tra Common Data Service e un'istanza di Microsoft Dynamics 365 Human Resources. È inoltre possibile visualizzare i dettagli di sincronizzazione, cancellare i dati di tracciabilità e sincronizzare di nuovo un'entità per risolvere problemi relativi ai dati tra i due ambienti.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 042daf3fdf7a906086af726472da050467d217e3
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009516"
---
# <a name="configure-common-data-service-integration"></a>Configurare l'integrazione di Common Data Service

È possibile attivare o disattivare l'integrazione tra Common Data Service e un'istanza di Microsoft Dynamics 365 Human Resources. È inoltre possibile visualizzare i dettagli di sincronizzazione, cancellare i dati di tracciabilità e sincronizzare di nuovo un'entità per risolvere problemi relativi ai dati tra i due ambienti.

Quando si disattiva l'integrazione, gli utenti possono effettuare modifiche in Human Resources o Common Data Service, ma tali modifiche non sono sincronizzate tra i due ambienti.

Per impostazione predefinita, l'integrazione tra Human Resources e Common Data Service è disattivata o attivata, a seconda della presenza di dati dimostrativi negli ambienti:

- **Disattivata** per nuovi ambienti che non includono dati dimostrativi
- **Attivata** per nuovi ambienti che includono dati dimostrativi

I nuovi ambienti che includono dati dimostrativi inizieranno a sincronizzare i dati quando viene eseguito il provisioning degli stessi.

In tali casi è possibile che si voglia disattivare l'integrazione:

- Si specificano dati tramite Data Management Framework ed è necessario importarli più volte per riportarli a uno stato corretto.

- Esistono problemi con i dati in Human Resources o Common Data Service. Se si disattiva l'integrazione, è possibile eliminare un record in un ambiente senza eliminarlo nell'altro. Quando si riattiva l'integrazione, il record nell'ambiente in cui non è stato eliminato verrà sincronizzato di nuovo con l'ambiente in cui è stato eliminato. La sincronizzazione inizia alla successiva esecuzione del processo batch **Sincronizzazione richiesta non eseguita per integrazione di Common Data Service**.

> [!WARNING]
> Quando si disattiva l'integrazione dei dati, assicurarsi di non modificare lo stesso record in entrambi gli ambienti. Quando si riattiva l'integrazione, l'ultimo record modificato verrà sincronizzato. Pertanto, se non si apportano le stesse modifiche al record in entrambi gli ambienti, può verificarsi una perdita di dati.

## <a name="access-the-common-data-service-integration-page"></a>Accedere alla pagina Integrazione di Common Data Service

1. Nell'istanza di Human Resources in cui si desidera visualizzare o configurare le impostazioni per l'integrazione con Common Data Service, selezionare il riquadro **Amministrazione sistema**.

    [![Riquadro Amministrazione sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. Selezionare la scheda **Collegamenti**.

    [![Scheda Collegamenti](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. Sotto **Integrazioni**, selezionare **Configurazione di Common Data Service**.

    [![Collegamento Configurazione di Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a>Attivare o disattivare l'integrazione di dati tra Human Resources e Common Data Service

- Per attivare l'integrazione, impostare l'opzione **Abilita l'integrazione con Common Data Service** su **Sì**.

    > [!NOTE]
    > Quando si attiva l'integrazione, i dati verranno sincronizzati alla successiva esecuzione del processo batch **Sincronizzazione richiesta non eseguita per integrazione con Common Data Service**. Tutti i dati dovrebbero essere disponibili dopo il completamento del processo batch.

- Per disattivare l'integrazione, impostare l'opzione su **No**.

[![Attivare o disattivare l'integrazione con Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)

## <a name="view-data-integration-details"></a>Visualizzare i dettagli dell'integrazione dei dati

Nella Scheda dettaglio **Amministrazione** della pagina **Integrazione con Common Data Service**, è possibile vedere come i record sono collegati tra Human Resources e Common Data Service.

- Per visualizzare i record per un'entità, selezionare l'entità nel campo **Nome entità CDS**. La griglia mostra tutti i record collegati all'entità selezionata.

[![Visualizzare i record per un'entità](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)

> [!NOTE]
> Non tutte le entità di Common Data Service sono attualmente elencate. Nella griglia vengono visualizzate solo le entità che supportano l'uso di campi personalizzati. Le nuove entità diventano disponibili attraverso il rilascio continuo di Human Resources.

La griglia include i seguenti campi:

- **Nome entità CDS** - Il nome dell'entità in Common Data Service.
- **Riferimento entità CDS** - L'identificatore che Common Data Service utilizza per identificare un record. Questo valore equivale al valore **RecId** di Human Resources. È possibile trovare l'identificatore quando si apre l'entità di Common Data Service in Microsoft Excel.
- **Nome entità Human Resources** - L'entità che ha eseguito l'ultima sincronizzazione dei dati con Common Data Service. L'entità può avere il prefisso Common Data Service o un altro prefisso.
- **Riferimento Human Resources** - Il valore **RecId** associato al record in Human Resources.
- **È stato eliminato da CDS** - Un valore che indica se il record è stato eliminato da Common Data Service.

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a>Rimuovere l'associazione di un record in Human Resources da Common Data Service

In caso di problemi durante la sincronizzazione di dati tra Human Resources e Common Data Service, questi potrebbero essere risolti annullando la tracciabilità e consentendo una nuova sincronizzazione della tabella di tracciabilità. Se si rimuove l'associazione e si modifica o si elimina un record in Common Data Service, le modifiche non verranno sincronizzate con Human Resources. Se si apportano modifiche in Human Resources, viene creato un nuovo record di tracciabilità e il record viene aggiornato in Common Data Service.

- Per rimuovere l'associazione di un record tra Human Resources e Common Data Service, selezionare l'entità nel campo **Nome entità CDS**, quindi selezionare **Cancella informazioni di tracciabilità**.

[![Annullare le informazioni di tracciabilità](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)

Per eseguire una sincronizzazione completa sull'entità dopo aver annullato la tracciabilità, vedere la procedura successiva.

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a>Sincronizzare un'entità tra Human Resources e Common Data Service

Utilizzare questa procedura se la visualizzazione in Human Resources delle modifiche effettuate in Common Data Service richiede troppo tempo o se è necessario aggiornare la tabella di tracciabilità dopo aver annullato la tracciabilità.

- Per eseguire una sincronizzazione completa su un'entità tra Human Resources e Common Data Service, selezionare l'entità nel campo **Nome entità CDS**, quindi selezionare **Sincronizza ora**.

[![Eseguire una sincronizzazione completa](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)


