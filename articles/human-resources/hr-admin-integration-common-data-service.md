---
title: Configurare l'integrazione di Dataverse
description: È possibile attivare o disattivare l'integrazione tra Microsoft Dataverse e Dynamics 365 Human Resources. È inoltre possibile visualizzare i dettagli di sincronizzazione, cancellare i dati di tracciabilità e sincronizzare di nuovo una tabella per risolvere problemi relativi ai dati tra i due ambienti.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
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
ms.openlocfilehash: 38c42469e62bf5457d0281540325a6c56a5f930f
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113158"
---
# <a name="configure-dataverse-integration"></a>Configurare l'integrazione di Dataverse

È possibile attivare o disattivare l'integrazione tra Microsoft Dataverse e Dynamics 365 Human Resources. È inoltre possibile visualizzare i dettagli di sincronizzazione, cancellare i dati di tracciabilità e sincronizzare di nuovo una tabella per risolvere problemi relativi ai dati tra i due ambienti.

> [!NOTE]
> Per ulteriori informazioni su Dataverse (in precedenza Common Data Service) e aggiornamenti terminologici, vedi [ Cosa è Microsoft Dataverse ?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)

Quando si disattiva l'integrazione, gli utenti possono effettuare modifiche in Human Resources o Dataverse, ma tali modifiche non sono sincronizzate tra i due ambienti.

Per impostazione predefinita, l'integrazione di dati tra Human Resources e Dataverse è disattivata.

In tali casi è possibile che si voglia disattivare l'integrazione:

- Si specificano dati tramite Data Management Framework ed è necessario importarli più volte per riportarli a uno stato corretto.

- Esistono problemi con i dati in Human Resources o Dataverse. Se si disattiva l'integrazione, è possibile eliminare un record in un ambiente senza eliminarlo nell'altro. Quando si riattiva l'integrazione, il record nell'ambiente in cui non è stato eliminato viene sincronizzato con l'ambiente in cui è stato eliminato. La sincronizzazione inizia alla successiva esecuzione del processo batch **Sincronizzazione richiesta non eseguita per integrazione di Dataverse**.

> [!WARNING]
> Quando si disattiva l'integrazione dei dati, assicurarsi di non modificare lo stesso record in entrambi gli ambienti. Quando si riattiva l'integrazione, l'ultimo record modificato verrà sincronizzato. Pertanto, se non si apportano le stesse modifiche al record in entrambi gli ambienti, può verificarsi una perdita di dati.

## <a name="access-the-dataverse-integration-page"></a>Accedere alla pagina Integrazione di Dataverse

1. Nell'istanza di Human Resources in cui si desidera visualizzare o configurare le impostazioni per l'integrazione con Dataverse, selezionare il riquadro **Amministrazione sistema**.

    [![Riquadro Amministrazione sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. Selezionare la scheda **Collegamenti**.

    [![Scheda Collegamenti](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. Sotto **Integrazioni**, selezionare **Configurazione di Dataverse**.

    [![Collegamento Configurazione di Dataverse](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a>Attivare o disattivare l'integrazione di dati tra Human Resources e Dataverse

- Per attivare l'integrazione, impostare l'opzione **Abilita integrazione Dataverse** su **Sì** nella pagina **Integrazione di Microsoft Dataverse**.

    > [!NOTE]
    > Quando si attiva l'integrazione, i dati verranno sincronizzati alla successiva esecuzione del processo batch **Sincronizzazione richiesta non eseguita per integrazione con Dataverse**. Tutti i dati dovrebbero essere disponibili dopo il completamento del processo batch.

- Per disattivare l'integrazione, impostare l'opzione su **No**.

[![Attivare o disattivare l'integrazione con Dataverse](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)

> [!WARNING]
> Si consiglia vivamente di disattivare l'integrazione Dataverse durante l'esecuzione di attività di migrazione dei dati. Caricamenti di dati di grandi dimensioni possono influire in modo significativo sulle prestazioni. Ad esempio, il caricamento di 2000 lavoratori può richiedere diverse ore quando l'integrazione è abilitata e meno di un'ora quando è disabilitata. I numeri forniti in questo esempio sono a puro scopo dimostrativo. Il tempo esatto necessario per importare i record può variare notevolmente in base a molti fattori.

## <a name="view-data-integration-details"></a>Visualizzare i dettagli dell'integrazione dei dati

Nella Scheda dettaglio **Amministrazione** della pagina **Integrazione di Microsoft Dataverse**, puoi vedere come le righe sono collegate tra Human Resources e Dataverse.

- Per visualizzare le righe di una tabella, seleziona la tabella nel campo **Tabella Dataverse**. La griglia mostra tutte le righe collegate alla tabella selezionata.

> [!NOTE]
> Non tutte le tabelle di Dataverse sono attualmente elencate. Nella griglia vengono visualizzate solo le tabelle che supportano l'uso di campi personalizzati. Le nuove tabelle diventano disponibili attraverso il rilascio continuo di Human Resources.

La griglia include i seguenti campi:

- **Tabella Dataverse**: il nome della tabella in Dataverse.
- **Riferimento tabella Dataverse**: l'identificatore utilizzato da Dataverse per identificare un record. Questo valore equivale al valore **RecId** di Human Resources. Puoi trovare l'identificatore quando si apre la tabella di Dataverse in Microsoft Excel.
- **Nome entità Human Resources**: l'entità Human Resources che ha eseguito l'ultima sincronizzazione dei dati con Dataverse. L'entità può avere il prefisso Dataverse o un altro prefisso.
- **Riferimento Human Resources** - Il valore **RecId** associato al record in Human Resources.
- **Eliminato da Dataverse**: un valore che indica se la riga è stata eliminata da Dataverse.

> [!NOTE]
> I record in Human Resources corrispondono alle righe in Dataverse.

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a>Rimuovere l'associazione di un record in Human Resources da una riga Dataverse

In caso di problemi durante la sincronizzazione di dati tra Human Resources e Dataverse, questi potrebbero essere risolti annullando la tracciabilità e consentendo una nuova sincronizzazione della tabella di tracciabilità. Se si rimuove l'associazione e si modifica o si elimina una riga in Dataverse, le modifiche non verranno sincronizzate con Human Resources. Se si apportano modifiche in Human Resources, viene creato un nuovo record di tracciabilità e la riga viene aggiornata in Dataverse.

- Per rimuovere l'associazione di un record tra Human Resources e una riga Dataverse, seleziona la tabella nel campo **Tabella Dataverse**, quindi seleziona **Cancella informazioni di tracciabilità**.

[![Annullare le informazioni di tracciabilità](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)

Per eseguire una sincronizzazione completa sulla tabella dopo aver annullato la tracciabilità, vedere la procedura successiva.

## <a name="sync-a-table-between-human-resources-and-dataverse"></a>Sincronizzare una tabella tra Human Resources e Dataverse

Utilizzare questa procedura quando:

- Le modifiche da Dataverse impiegano troppo tempo ad apparire in Human Resources.

- È necessario aggiornare la tabella di monitoraggio dopo aver cancellato il rilevamento.

Per eseguire una sincronizzazione completa su una tabella tra Human Resources e Dataverse:

1. Selezionare la tabella nel campo **Tabella Dataverse**.

2. Selezionare **Sincronizza ora**.

[![Eseguire una sincronizzazione completa](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)

## <a name="see-also"></a>Vedere anche

[Tabelle Dataverse](hr-developer-entities.md)<br>
[Configurare tabelle virtuali in Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Domande frequenti sulle tabelle virtuali in Human Resources](hr-admin-virtual-entity-faq.md)<br>
[Che cos'è Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[Aggiornamenti terminologici](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]