---
title: Configurare l'integrazione di Common Data Service
description: È possibile attivare o disattivare l'integrazione tra Common Data Service e Dynamics 365 Human Resources. È inoltre possibile visualizzare i dettagli di sincronizzazione, cancellare i dati di tracciabilità e sincronizzare di nuovo un'entità per risolvere problemi relativi ai dati tra i due ambienti.
author: andreabichsel
manager: AnnBe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d9ee4715526e18b33ae4b7e90b081ed5868bb19c
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527928"
---
# <a name="configure-common-data-service-integration"></a>Configurare l'integrazione di Common Data Service

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

È possibile attivare o disattivare l'integrazione tra Common Data Service e Dynamics 365 Human Resources. È inoltre possibile visualizzare i dettagli di sincronizzazione, cancellare i dati di tracciabilità e sincronizzare di nuovo un'entità per risolvere problemi relativi ai dati tra i due ambienti.

Quando si disattiva l'integrazione, gli utenti possono effettuare modifiche in Human Resources o Common Data Service, ma tali modifiche non sono sincronizzate tra i due ambienti.

Per impostazione predefinita, l'integrazione di dati tra Human Resources e Common Data Service è disattivata.

In tali casi è possibile che si voglia disattivare l'integrazione:

- Si specificano dati tramite Data Management Framework ed è necessario importarli più volte per riportarli a uno stato corretto.

- Esistono problemi con i dati in Human Resources o Common Data Service. Se si disattiva l'integrazione, è possibile eliminare un record in un ambiente senza eliminarlo nell'altro. Quando si riattiva l'integrazione, il record nell'ambiente in cui non è stato eliminato viene sincronizzato con l'ambiente in cui è stato eliminato. La sincronizzazione inizia alla successiva esecuzione del processo batch **Sincronizzazione richiesta non eseguita per integrazione di Common Data Service**.

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

> [!WARNING]
> Si consiglia vivamente di disattivare l'integrazione Common Data Service durante l'esecuzione di attività di migrazione dei dati. Caricamenti di dati di grandi dimensioni possono influire in modo significativo sulle prestazioni. Ad esempio, il caricamento di 2000 lavoratori può richiedere diverse ore quando l'integrazione è abilitata e meno di un'ora quando è disabilitata. I numeri forniti in questo esempio sono a puro scopo dimostrativo. Il tempo esatto necessario per importare i record può variare notevolmente in base a molti fattori.

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

Utilizzare questa procedura quando:

- Le modifiche da Common Data Service impiegano troppo tempo ad apparire in Human Resources.

- È necessario aggiornare la tabella di monitoraggio dopo aver cancellato il rilevamento.

Per eseguire una sincronizzazione completa su un'entità tra Human Resources e Common Data Service:

1. Selezionare l'entità nel campo **Nome entità CDS**.

2. Selezionare **Sincronizza ora**.

[![Eseguire una sincronizzazione completa](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)




[!INCLUDE[footer-include](../includes/footer-banner.md)]