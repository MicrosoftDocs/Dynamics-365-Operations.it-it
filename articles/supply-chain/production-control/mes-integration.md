---
title: Eseguire l'integrazione con sistemi di esecuzione della produzione di terze parti
description: Questo articolo spiega come integrare Microsoft Dynamics 365 Supply Chain Management con un sistema di esecuzione della produzione di terze parti (MES).
author: johanhoffmann
ms.date: 10/01/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-10-01
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 208ed2d6c8b411d12888966d9c175730e828eb44
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860640"
---
# <a name="integrate-with-third-party-manufacturing-execution-systems"></a>Eseguire l'integrazione con sistemi di esecuzione della produzione di terze parti

[!include [banner](../includes/banner.md)]

Alcune organizzazioni di produzione che utilizzano Microsoft Dynamics 365 Supply Chain Management utilizzare la funzionalità nativa in Dynamics 365 per controllare le attività di produzione per macchine, attrezzature e personale. Tuttavia, altre organizzazioni di produzione, in particolare quelle che hanno requisiti di produzione avanzati, utilizzano invece un sistema di esecuzione della produzione (MES) di terze parti. Le organizzazioni potrebbero scegliere una soluzione MES di terze parti perché, ad esempio, è specificamente adattata al loro settore verticale.

Nella soluzione integrata, lo scambio di dati è completamente automatizzato e avviene quasi in tempo reale. Pertanto, i dati vengono mantenuti aggiornati in entrambi i sistemi e non è richiesta alcuna immissione manuale dei dati. Ad esempio, quando il consumo di materiale viene registrato nel MES, l'integrazione garantisce che lo stesso consumo sia registrato anche in Dynamics 365. Pertanto, i record di inventario aggiornati sono disponibili per altri processi importanti, come la pianificazione e le vendite.

La soluzione rende più veloce, più facile ed economico per gli utenti di Supply Chain Management l'integrazione con MES di terze parti. Offre le seguenti caratteristiche:

- Eventi aziendali e interfacce che supportano [processi chiave di esecuzione della produzione](#processes-available-for-mes-integration)
- Una dashboard centralizzata in cui è possibile tenere traccia della cronologia di elaborazione degli eventi e risolvere i problemi e correggere i processi che non riescono

La seguente illustrazione mostra una tipica raccolta di eventi aziendali, processi e messaggi scambiati in una soluzione integrata.

![Scenario di integrazione tipico.](media/3p-mes-scenario.png "Scenario di integrazione tipico.")

## <a name="turn-on-the-mes-integration-feature"></a>Attivare la funzione di integrazione MES

Prima di poter utilizzare questa funzione, un amministratore deve attivarla nel sistema come descritto nella procedura seguente.

1. Accedere a **Amministrazione sistema \> Imposta \> Configurazione licenza**.
1. Assicurati che la chiave di licenza **Orario e presenze** sia abilitata (mostra un segno di spunta). Questa chiave di licenza è necessaria perché controlla la funzionalità e i dati del sistema di esecuzione della produzione. Se non è abilitata, procedi nel seguente modo:
    1. Mettere il sistema in modalità di manutenzione come descritto in [Modalità di manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
    1. Nella pagina **Configurazione della licenza** seleziona la casella di controllo **Orario e presenze**.
    1. Disattiva la modalità di manutenzione come descritto in [Modalità di manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)
1. Vai ad **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**.
1. Attiva la funzione elencata nel modo seguente (vedi anche [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)):
    - **Modulo:** *Controllo produzione*
    - **Nome funzionalità:** *Integrazione del sistema di esecuzione della produzione*

## <a name="processes-available-for-mes-integration"></a>Processi disponibili per l'integrazione MES

È possibile abilitare uno o tutti i seguenti processi per l'integrazione.

| Nome processo | Description |
|---|---|
| Rilasciare gli ordini di produzione e gli eventi aziendali di modifica dello stato dell'ordine di produzione | Questo processo fornisce un evento aziendale che il MES può ascoltare, per ottenere informazioni sugli ordini di produzione che dovrebbero essere prodotti. I dati di riferimento relativi all'ordine di produzione dovrebbero essere condivisi da Supply Chain Management al MES tramite Open Data Protocol (OData) o entità di dati. |
| Avvia ordine di produzione | Questo processo fornisce a Supply Chain Management le informazioni sugli ordini di produzione che vengono avviati utilizzando il MES. Assicura che entrambi i sistemi abbiano una visione aggiornata di tutte le attività di produzione. |
| Report quantità prodotta o scartata | Questo processo fornisce a Supply Chain Management le informazioni sulle quantità di errore e i prodotti finiti segnalati su un processo di produzione utilizzando il MES. Garantisce che i supervisori dell'officina abbiano una visione aggiornata dell'avanzamento del piano di produzione. |
| Segnalare il consumo di materiali | Questo processo fornisce a Supply Chain Management le informazioni dal MES sulle quantità di materiali che vengono consumate. Pertanto, i record di inventario aggiornati sono disponibili per altri processi importanti, come la pianificazione e le vendite. |
| Segnalare il tempo impiegato per l'operazione | Questo processo fornisce a Supply Chain Management informazioni sul tempo utilizzato per un'operazione specifica. |
| Ordine di produzione finale | Questo processo informa Supply Chain Management che il MES ha aggiornato un ordine di produzione al suo stato finale di *Terminato*. Questo stato indica che non verranno più prodotte quantità nell'ordine di produzione. |

## <a name="monitor-incoming-messages"></a>Monitorare i messaggi in arrivo

Per monitorare i messaggi in arrivo al sistema, aprire la pagina **Integrazione dei sistemi di esecuzione della produzione**. Qui puoi visualizzare, elaborare e risolvere i problemi.

Tutti i messaggi per un ordine di produzione specifico vengono elaborati nella sequenza in cui vengono ricevuti. Tuttavia, i messaggi per ordini di produzione diversi potrebbero non essere elaborati nella sequenza ricevuta perché i lavori batch vengono elaborati in parallelo. In caso di errore, il processo batch tenterà di elaborare ciascun messaggio tre volte prima di impostarlo sullo stato *Non riuscito*.

## <a name="call-the-api"></a>Chiamare l'API

Per chiamare l'API di integrazione MES, inviare una richiesta `POST` al seguente URL dell'endpoint:

`/api/services/SysMessageServices/SysMessageService/SendMessage`

Il corpo della richiesta inviata dovrebbe essere simile all'esempio seguente. Sostituisci i valori per `_companyId`, `_messageType` e `_messageContent` come richiesto. Per informazioni sui vari tipi di messaggi supportati dall'API e su come progettare il loro contenuto, vedere la sezione successiva.

```json
{
    "_companyId": "USMF",
    "_messageQueue": "JmgMES3P",
    "_messageType": "ProdProductionOrderReportFinished",
    "_messageContent":
    "{\"ProductionOrderNumber\": \"P000123\", \"ReportFinishedLines\": [{\"ItemNumber\": \"A0001\", \"ReportedGoodQuantity\": 10, \"ReportAsFinishedDate\": \"2021-01-01\"}]}"
}
```

## <a name="api-message-types-and-content"></a>Tipi e contenuto dei messaggi API

Questa sezione descrive ogni tipo di messaggio che può essere scambiato tramite l'API di integrazione MES.

### <a name="start-production-order-message"></a>Messaggio Avvia ordine di produzione

Per il messaggio *Avvia ordine di produzione*, il valore `_messageType` è `ProdProductionOrderStart`. La tabella seguente mostra i campi supportati da questo messaggio.

| Nome campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obbligatorio | String |
| `StartedQuantity` | Facoltativo | Real |
| `StartedDate` | Facoltativo | Data |
| `AutomaticBOMConsumptionRule` | Facoltativo | Enum (FlushingPrincip \| Always \| Never) |

### <a name="report-as-finished-message"></a>Messaggio dichiarazione di finito

Per il messaggio *dichiara come finito*, il valore `_messageType` è `ProdProductionOrderReportFinished`. La tabella seguente mostra i campi supportati da questo messaggio.

| Nome campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obbligatorio | String |
| `ReportFinishedLines` | Obbligatorio | Un elenco di righe (almeno una), ognuna delle quali contiene il payload descritto nella tabella successiva |

La tabella seguente mostra i campi che ogni riga nella sezione `ReportFinishedLines` del messaggio `ProdProductionOrderReportFinished` supporta.

| Nome campo | Status | Tipo |
|---|---|---|
| `LineNumber` | Facoltativo | Real |
| `ItemNumber` | Facoltativo | String|
| `ProductionType` | Facoltativo | Enum (MainItem \| Formula \| BOM \| Co_Product \| By_Product \| None), extensible |
| `ReportedErrorQuantity` | Facoltativo | Real|
| `ReportedGoodQuantity` | Facoltativo | Real|
| `ReportedErrorCatchWeightQuantity` | Facoltativo | Real |
| `ReportedGoodCatchWeightQuantity` | Facoltativo | Real |
| `AcceptError` | Facoltativo | Enum (Sì \| No) |
| `ErrorCause` | Facoltativo | Enum (None \| Material \| Machine \| OperatingStaff), extensible |
| `ExecutedDateTime` | Facoltativo | Data/Ora |
| `ReportAsFinishedDate` | Facoltativo | Data |
| `AutomaticBOMConsumptionRule` | Facoltativo | Enum (FlushingPrincip \| Always \| Never) |
| `AutomaticRouteConsumptionRule` | Facoltativo |Enum (RouteDependent \| Always \| Never) |
| `RespectFlushingPrincipleDuringOverproduction` | Facoltativo | Enum (Sì \| No) |
| `ProductionJournalNameId` | Facoltativo | Stringa |
| `PickingListProductionJournalNameId` | Facoltativo | Stringa|
| `RouteCardProductionJournalNameId` | Facoltativo | Stringa |
| `FromOperationNumber` | Facoltativo | Numero intero|
| `ToOperationNumber` | Facoltativo | Numero intero|
| `InventoryLotId` | Facoltativo | Stringa |
| `BaseValue` | Facoltativo | Stringa |
| `EndJob` | Facoltativo | Enum (Sì \| No) |
| `EndPickingList` | Facoltativo | Enum (Sì \| No) |
| `EndRouteCard` | Facoltativo | Enum (Sì \| No) |
| `PostNow` | Facoltativo | Enum (Sì \| No) |
| `AutoUpdate` | Facoltativo | Enum (Sì \| No) |
| `ProductColorId` | Facoltativo | Stringa|
| `ProductConfigurationId` | Facoltativo | Stringa |
| `ProductSizeId` | Facoltativo | Stringa |
| `ProductStyleId` | Facoltativo | String |
| `ProductVersionId` | Facoltativo | String |
| `ItemBatchNumber` | Facoltativo | String |
| `ProductSerialNumber` | Facoltativo | String |
| `LicensePlateNumber` | Facoltativo | String |
| `InventoryStatusId` | Facoltativo | String |
| `ProductionWarehouseId` | Facoltativo | String |
| `ProductionSiteId` | Facoltativo | String |
| `ProductionWarehouseLocationId` | Facoltativo | String |
| da `InventoryDimension1` a `InventoryDimension12` | Facoltativo | String |

Le 12 dimensioni estensibili (`InventoryDimension1` attraverso `InventoryDimension12`) richiedono la personalizzazione e non vengono sempre utilizzati. Per ulteriori informazioni, vedere [Aggiungere nuove dimensioni di inventario tramite estensione](../../fin-ops-core/dev-itpro/extensibility/inventory-dimensions.md).

### <a name="material-consumption-picking-list-message"></a>Messaggio sul consumo di materiale (distinta di prelievo)

Per il messaggio sul *consumo di materiale (distinta di prelievo)*, il valore `_messageType` è `ProdProductionOrderPickingList`. La tabella seguente mostra i campi supportati da questo messaggio.

| Nome campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obbligatorio | String |
| `JournalNameId` | Facoltativo | String |
| `PickingListLines` | Obbligatorio | Un elenco di righe (almeno una), ognuna delle quali contiene il payload descritto nella tabella successiva |

La tabella seguente mostra i campi che ogni riga nella sezione `PickingListLines` del messaggio `ProdProductionOrderPickingList` supporta.

| Nome campo | Status | Tipo |
|---|---|---|
| `ItemNumber` | Obbligatorio | String |
| `ConsumptionBOMQuantity` | Facoltativo | Real |
| `ProposalBOMQuantity` | Facoltativo | Real |
| `ScrapBOMQuantity` | Facoltativo | Real |
| `BOMUnitSymbol` | Facoltativo | String |
| `ConsumptionInventoryQuantity` | Facoltativo | Real |
| `ProposalInventoryQuantity` | Facoltativo | Real |
| `ConsumptionCatchWeightQuantity` | Facoltativo | Real |
| `ProposalCatchWeightQuantity` | Facoltativo | Real |
| `ConsumptionDate` | Facoltativo | Data |
| `OperationNumber` | Facoltativo | Numero intero |
| `LineNumber` | Facoltativo | Real |
| `PositionNumber` | Facoltativo | Stringa |
| `IsConsumptionEnded` | Facoltativo | Enum (Sì \| No) |
| `ErrorCause` | Facoltativo | Enum (None \| Material \| Machine \| OperatingStaff), extensible |
| `InventoryLotId` | Facoltativo | Stringa |

### <a name="time-used-for-operation-route-card-message"></a>Messaggio di tempo impiegato per l'operazione (scheda di percorso)

Per il messaggio sul *tempo impiegato per l'operazione (scheda di percorso)*, il valore `_messageType` è `ProdProductionOrderRouteCard`. La tabella seguente mostra i campi supportati da questo messaggio.

| Nome campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obbligatorio | String |
| `JournalNameId` | Facoltativo | String |
| `RouteCardLines` | Obbligatorio | Un elenco di righe (almeno una), ognuna delle quali contiene il payload descritto nella tabella successiva |

La tabella seguente mostra i campi che ogni riga nella sezione `RouteCardLines` del messaggio `ProdProductionOrderRouteCard` supporta.

| Nome campo | Status | Tipo |
|---|---|---|
| `OperationNumber` | Obbligatorio | Numero intero |
| `OperationPriority` | Facoltativo | Enum (Primary \| Secondary1 \| Secondary2 \| ... \| Secondary20) |
| `OperationId` | Facoltativo | String |
| `OperationsResourceId` | Facoltativo | String |
| `Worker` | Facoltativo | String |
| `HoursRouteCostCategoryId` | Facoltativo | String |
| `QuantityRouteCostCategoryId` | Facoltativo | String |
| `HourlyRate` | Facoltativo | Real |
| `Hours` | Facoltativo | Real |
| `GoodQuantity` | Facoltativo | Real |
| `ErrorQuantity` | Facoltativo | Real |
| `CatchWeightGoodQuantity` | Facoltativo | Real |
| `CatchWeightErrorQuantity` | Facoltativo | Real |
| `QuantityPrice` | Facoltativo | Real |
| `ProcessingPercentage` | Facoltativo | Real |
| `ConsumptionDate` | Facoltativo | Data |
| `TaskType` | Facoltativo | Enum (QueueBefore \| Setup \| Process \| Overlap \| Transport \| QueueAfter \| Burden) |
| `ErrorCause` | Facoltativo | Enum (None \| Material \| Machine \| OperatingStaff), extensible |
| `OperationCompleted` | Facoltativo | Enum (Sì \| No) |
| `BOMConsumption` | Facoltativo | Enum (Sì \| No) |
| `ReportAsFinished` | Facoltativo | Enum (Sì \| No) |

### <a name="end-production-order-message"></a>Messaggio Termina ordine di produzione

Per il messaggio *Termina ordine di produzione*, il valore `_messageType` è `ProdProductionOrderEnd`. La tabella seguente mostra i campi supportati da questo messaggio.

| Nome campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obbligatorio | Stringa |
| `ExecutedDateTime` | Facoltativo | Data/Ora |
| `EndedDate` | Facoltativo | Data |
| `UseTimeAndAttendanceCost` | Facoltativo | Enum (Sì \| No) |
| `AutoReportAsFinished` | Facoltativo | Enum (Sì \| No) |
| `AutoUpdate` | Facoltativo | Enum (Sì \| No) |

## <a name="other-production-information"></a>Altre informazioni sulla produzione

I messaggi supportano azioni o eventi che si verificano nell'area di produzione. Vengono elaborati utilizzando il framework di integrazione MES descritto in questo articolo. Il progetto presuppone che altre informazioni di riferimento da condividere con il MES, come le informazioni relative al prodotto, o la distinta base o il percorso (con i suoi tempi di impostazione e configurazione specifici) utilizzate in uno specifico ordine di produzione vengano recuperate dal sistema usando le [entità di dati](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#data-entities) tramite trasferimento file oppure OData.

## <a name="receive-feedback-about-the-state-of-a-message"></a>Ricevere il feedback sullo stato di un messaggio

Dopo che il MES ha inviato un messaggio a Supply Chain Management, potrebbe essere importante per Supply Chain Management restituire un feedback sullo stato del messaggio. Di seguito sono riportati alcuni esempi di casi in cui tale comportamento può risultare utile:

- Non esiste una persona responsabile della supervisione costante dell'integrazione MES.
- La persona responsabile della supervisione dell'integrazione MES desidera essere informata via e-mail quando un messaggio non riesce, in modo che sappia che deve agire.
- Il MES deve mostrare un messaggio di errore per informare l'operatore dell'officina o qualcuno del reparto IT che devono agire.
- Il MES deve ricalcolare la pianificazione dell'ordine dopo aver ricevuto un messaggio di errore (ad esempio, perché un ordine di produzione non è stato avviato).

In questi casi, puoi sfruttare la funzionalità di avviso standard in Supply Chain Management. Per informazioni sul funzionamento degli avvisi standard, vedere le seguenti risorse:

- Articolo della guida: [Panoramica degli avvisi](../../fin-ops-core/fin-ops/get-started/alerts-overview.md)
- Video: [Opzioni per le regole di avviso in Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=cpzimwOjicM&ab_channel=MicrosoftDynamics365)

Ad esempio, potresti impostare i seguenti avvisi per fornire un feedback sullo stato di un messaggio:

- Crea un evento aziendale ("Invia esternamente") che viene utilizzato quando un messaggio è *Non riuscito*.
- Invia una notifica e un messaggio e-mail all'amministratore IT o al responsabile del piano di produzione.
