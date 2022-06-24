---
title: Entità di creazione viaggi
description: Questo articolo fornisce informazioni sulle entità di dati di creazione del viaggio, che raggruppano le entità di dati necessarie per creare un viaggio di lavoro.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: cb2e2f53942015caf9462692515f24deb9689aed
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873900"
---
# <a name="voyage-creation-entities"></a>Entità di creazione viaggi

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

Le entità di dati di creazione del viaggio raggruppano le entità di dati necessarie per creare un viaggio di lavoro. Tu o il tuo spedizioniere potete utilizzare queste entità di dati per creare record di viaggio, contenitori di spedizione, registrazione e righe di viaggio che facciano riferimento all'ordine acquirente esistente o alle righe dell'ordine di trasferimento.

## <a name="voyages-itmtableentity"></a>Viaggi (ITMTableEntity)

Il viaggio rappresenta il viaggio delle merci in entrata e funge da area di costo di livello più alto in Costo di spedizione. Contiene informazioni a livello di intestazione relative alla nave, al porto di origine e al porto di destinazione. Questa funzionalità è supportata dall'entità `ITMTableEntity`. La tabella seguente elenca i campi e i mapping che compongono questa entità.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Modalità di consegna | ITMTable.DlvModeId | Nvarchar(10) | Numero | Numero |
| Broker consigliato | ITMTable.ITMBrokerAdvised | Data/Ora | Numero | Numero |
| Appuntamento cliente | ITMTable.ITMCustomerAppointment | Data/Ora | Numero | Numero |
| Consegnato al magazzino | ITMTable.ITMDelAtWarehouse | Data/Ora | Numero | Numero |
| Istruzioni di consegna | ITMTable.ITMDeliveryInstructions | Data/Ora | Numero | Numero |
| Data di partenza | ITMTable.ITMDepartureDate | Data/Ora | Numero | Numero |
| Merci rilasciate | ITMTable.ITMGoodsReleased | Data/Ora | Numero | Numero |
| Data trasporto locale | ITMTable.ITMLocalTransportDate | Data/Ora | Numero | Numero |
| Ora trasporto locale | ITMTable.ITMLocalTransportTime | Int | Numero | Numero |
| Polizza di carico originale inviata | ITMTable.ITMOriginalBOLSebt | Data/Ora | Numero | Numero |
| Documenti originali ricevuti | ITMTable.ITMOriginalDocsReceived | Data/Ora | Numero | Numero |
| Stato ordine fornitore | ITMTable.ITMPurchStatus | Int | Numero | Numero |
| Data di verifica | ITMTable.ITMVerificationDate | Data/Ora | Numero | Numero |
| Identificatore voce doganale | ITMTable.ShipCustomsEntryId | Nvarchar(20) | Numero | Numero |
| Data di spedizione | ITMTable.ShipDate | Data/Ora | Numero | Numero |
| Description | ITMTable.ShipDescription | Nvarchar(60) | Numero | Numero |
| Documenti ricevuti | ITMTable.ShipDocReceived | Int | Numero | Numero |
| Data di consegna stimata | ITMTable.ShipEstDlvDate | Data/Ora | Numero | Numero |
| Data/ora di arrivo stimata al porto di spedizione | ITMTable.ShipEstPortDate | Data/Ora | Numero | Numero |
| Porto di origine | ITMTable.ShipFromPort | Nvarchar(20) | Numero | Numero |
| Lettera di vettura aerea/Polizza di carico | ITMTable.ShipHAWB | Nvarchar(20) | Numero | Numero |
| Viaggio | ITMTable.ShipId | Nvarchar(20) | **Sì** | **Sì** |
| Riferimento prenotazione | ITMTable.ShipIdExternal | Nvarchar(20) | Numero | Numero |
| Modello di percorso | ITMTable.ShipJourneyId | Nvarchar(20) | Numero | Numero |
| Spedizioniere locale | ITMTable.ShipLocalForwarder | Nvarchar(20) | Numero | Numero |
| Lettera di vettura aerea generale/Polizza di carico | ITMTable.ShipMAWB | Nvarchar(20) | Numero | Numero |
| Misura | ITMTable.ShipMeasurement | Numeric(32, 6) | Numero | Numero |
| Unità di misura | ITMTable.ShipMeasurementUnit | Int | Numero | Numero |
| Numero di pallet | ITMTable.ShipNoOfPallets | Int | Numero | Numero |
| Viaggio in sospeso | ITMTable.ShipPending | Int | Numero | Numero |
| Note | ITMTable.ShipRemarks | Nvarchar(MAX) | Numero | Numero |
| Noleggio | ITMTable.ShipRental | Int | Numero | Numero |
| Stato viaggio | ITMTable.ShipStatusId | Nvarchar(20) | Numero | Numero |
| Conteggio in numero | ITMTable.ShipTallyInNumber | Nvarchar(20) | Numero | Numero |
| Porto di destinazione | ITMTable.ShipToPort | Nvarchar(20) | Numero | Numero |
| Data valutazione | ITMTable.ShipValuationDate | Data/Ora | Numero | Numero |
| Società di spedizione | ITMTable.ShipVendAccount | Nvarchar(20) | Numero | Numero |
| Imbarcazione | ITMTable.ShipVesselId | Nvarchar(20) | Numero | **Sì** |
| ID viaggio esterno | ITMTable.ShipVoyage | Nvarchar(20) | Numero | Numero |

### <a name="number-sequences-for-voyages"></a>Sequenze numeriche per i viaggi

La sequenza numerica condivisa per i viaggi controlla l'assegnazione degli ID viaggio.

Il valore che viene passato all'entità di dati come **ID viaggio** (`ShipId`) viene utilizzato per identificare un record esistente per l'aggiornamento. Se quel record non esiste, il comportamento dipende dal fatto che la sequenza numerica assegnata sia configurata per consentire l'immissione manuale:

- Se l'immissione manuale è abilitata, viene creato un nuovo record che utilizza il valore passato.
- Se l'immissione manuale non è abilitata, viene utilizzato il numero successivo nella sequenza numerica assegnata al posto del valore passato.

Durante la sessione di importazione, il valore segnaposto importato come ID viaggio viene mantenuto. Questo comportamento garantisce che il contenitore di spedizione e le righe di viaggio che fanno riferimento al segnaposto siano inclusi nel viaggio e che vengano aggiornati per riflettere il valore assegnato dalla sequenza numerica.

### <a name="automatic-cost-transactions"></a>Transazioni costo automatico

I costi automatici possono essere aggiunti a un viaggio dalla pagina **Costi automatici** in Microsoft Dynamics 365 Supply Chain Management (**Costo di spedizione \> Impostazione determinazione costi \> Costi automatici**). I record per i costi automatici possono anche essere creati utilizzando le entità di dati di transazione dei costi per ciascuna area di costo supportata da Costo di spedizione.

I costi automatici configurati in Supply Chain Management vengono applicati al viaggio quando viene creata una riga di viaggio. Nessun costo sarà visibile rispetto al record fino a quando il record di intestazione non sarà associato alle informazioni sulla riga.

## <a name="shipping-containers-itmcontainersentity"></a>Contenitori di spedizione (ITMContainersEntity)

Un contenitore di spedizione rappresenta un contenitore fisico in cui vengono trasportate le merci. Questo contenitore fisico potrebbe essere un contenitore di spedizione per il trasporto marittimo o un singolo pallet per il trasporto aereo. Il contenitore di spedizione include informazioni a livello di intestazione correlate all'ID del contenitore di spedizione, al numero del sigillo e al tipo di contenitore di spedizione. (Il tipo di contenitore di spedizione fornisce informazioni sulle dimensioni.) Questa funzionalità è supportata dall'entità `ITMContainersEntity`. La tabella seguente elenca i campi e i mapping che compongono questa entità.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Data di partenza | ITMContainers.ITMDepartureDate | Data/Ora | Numero | Numero |
| Data trasporto locale | ITMContainers.ITMLocalTransportDate | Data/Ora | Numero | Numero |
| Ora trasporto locale | ITMContainers.ITMLocalTransportTime | Int | Numero | Numero |
| Viaggio originale | ITMContainers.OrigShipId | Nvarchar(20) | Numero | Numero |
| Peso effettivo | ITMContainers.ShipActualWeight | Numeric(32, 6) | Numero | Numero |
| Broker consigliato | ITMContainers.ShipBrokerAdvised | Data/Ora | Numero | Numero |
| Contenitore di spedizione | ITMContainers.ShipContainerId | Nvarchar(20) | **Sì** | **Sì** |
| Tipo di contenitore di spedizione | ITMContainers.ShipContainerTypeId | Nvarchar(20) | Numero | Numero |
| Tipo di unità | ITMContainers.ShipContainerUnitTypeId | Nvarchar(10) | Numero | Numero |
| Convertito in noleggio | ITMContainers.ShipConvertedToRental | Int | Numero | Numero |
| Appuntamento cliente | ITMContainers.ShipCustomerAppointment | Data/Ora | Numero | Numero |
| Data di spedizione | ITMContainers.ShipDate | Data/Ora | Numero | Numero |
| Consegnato al magazzino | ITMContainers.ShipDelAtWarehouse | Data/Ora | Numero | Numero |
| Istruzioni di consegna | ITMContainers.ShipDeliveryInstructions | Data/Ora | Numero | Numero |
| Data di applicazione certificato di esame | ITMContainers.ShipECAppliedDate | Data/Ora | Numero | Numero |
| Data di scadenza certificato di esame | ITMContainers.ShipECExpiryDate | Data/Ora | Numero | Numero |
| Numero certificato di esame | ITMContainers.ShipECNum | Nvarchar(20) | Numero | Numero |
| Data di ricevimento certificato di esame | ITMContainers.ShipECReceivedDate | Data/Ora | Numero | Numero |
| Data di consegna stimata | ITMContainers.ShipEstDlvDate | Data/Ora | Numero | Numero |
| Data/ora di arrivo stimata al porto di spedizione | ITMContainers.ShipEstPortDate | Data/Ora | Numero | Numero |
| Data di carico prevista | ITMContainers.ShipExpectedLoadingDate | Data/Ora | Numero | Numero |
| Porto di origine | ITMContainers.ShipFromPort | Nvarchar(20) | Numero | Numero |
| Descrizione delle merci | ITMContainers.ShipGoodsDesc | Nvarchar(60) | Numero | Numero |
| Merci rilasciate | ITMContainers.ShipGoodsReleased | Data/Ora | Numero | Numero |
| Unità funzione GPS | ITMContainers.ShipGPSUnit | Nvarchar(30) | Numero | Numero |
| Lettera di vettura aerea/Polizza di carico | ITMContainers.ShipHAWB | Nvarchar(20) | Numero | Numero |
| Viaggio | ITMContainers.ShipId | Nvarchar(20) | **Sì** | **Sì** |
| Modello di percorso | ITMContainers.ShipJourneyId | Nvarchar(20) | Numero | Numero |
| Spedizioniere locale | ITMContainers.ShipLocalForwarder | Nvarchar(20) | Numero | Numero |
| Misura | ITMContainers.ShipMeasurement | Numeric(32, 6) | Numero | Numero |
| Unità di misura | ITMContainers.ShipMeasurementUnit | Int | Numero | Numero |
| Numero di cartoni | ITMContainers.ShipNoOfCartons | Numeric(32, 6) | Numero | Numero |
| Polizza di carico originale inviata | ITMContainers.ShipOriginalBOLSebt | Data/Ora | Numero | Numero |
| Documenti originali ricevuti | ITMContainers.ShipOriginalDocsReceived | Data/Ora | Numero | Numero |
| Ns numero sigillo | ITMContainers.ShipOurSealNum | Nvarchar(20) | Numero | Numero |
| Utilizzato | ITMContainers.ShipPendingUsed | Int | Numero | Numero |
| Stato ordine fornitore | ITMContainers.ShipPurchStatus | Int | Numero | Numero |
| Tipo di refrigerazione | ITMContainers.ShipRefrigerationTypeId | Nvarchar(10) | Numero | Numero |
| Note | ITMContainers.ShipRemarks | Nvarchar(MAX) | Numero | Numero |
| Noleggio | ITMContainers.ShipRental | Int | Numero | Numero |
| A rendere | ITMContainers.ShipReturnable | Int | Numero | Numero |
| Stato viaggio | ITMContainers.ShipStatusId | Nvarchar(20) | Numero | Numero |
| Numero sigillo società di spedizione | ITMContainers.ShipTheirSealNum | Nvarchar(20) | Numero | Numero |
| Porto di destinazione | ITMContainers.ShipToPort | Nvarchar(20) | Numero | Numero |
| Data di verifica | ITMContainers.ShipVerificationDate | Data/Ora | Numero | Numero |
| Imbarcazione | ITMContainers.ShipVesselId | Nvarchar(20) | Numero | **Sì** |

### <a name="voyage-id-validation"></a>Convalida ID viaggio

L'ID del contenitore di spedizione non è controllato da una sequenza numerica. È univoco solo nel contesto del viaggio in cui viene utilizzato.

Se l'entità del contenitore di spedizione (`ITMContainersEntity`) è utilizzata indipendentemente dall'entità di viaggio (`ITMTableEntity`), il valore **ID viaggio** (`ShipId`) deve corrispondere a un record esistente nella tabella di viaggio. In caso contrario, l'importazione avrà esito negativo.

Se l'entità del contenitore di spedizione (`ITMContainersEntity`) e l'entità di viaggio (`ITMTableEntity`) sono utilizzati nell'ambito della stessa sessione di importazione, l'entità di viaggio deve precedere la creazione di un contenitore di spedizione. In caso contrario, il valore **ID viaggio** (`ShipId`) non può essere convalidato correttamente. Se viene utilizzato un valore segnaposto per **ID viaggio** (`ShipId`), l'associazione può essere creata solo se viene utilizzato lo stesso segnaposto del valore **ID viaggio** (`ShipId`) nell'entità contenitore di spedizione.

### <a name="other-field-validations"></a>Altre convalide di campo

La tabella seguente mostra i campi nella tabella del contenitore di spedizione (`ITMContainers`) che vengono convalidati rispetto alle tabelle di impostazione dei costi di spedizione. Mostra anche le entità dei dati sui costi di spedizione che uno spedizioniere può utilizzare per leggere i valori esistenti e garantire che i valori validi vengano ricevuti nell'ambiente.

| Campo nella tabella ITMContainers | Entità di dati costi di spedizione |
|---|---|
| Tipo di contenitore di spedizione | ITMShippingContainerTypeEntity |
| Descrizione delle merci | ITMGoodsDescriptionEntity |
| Tipo di refrigerazione | ITMShippingContainerRefrigerationTypeEntity |

## <a name="folios-itmfolioentity"></a>Folio (ITMFolioEntity)

Una registrazione rappresenta un raggruppamento di articoli in un contenitore ai fini delle dichiarazioni doganali. La registrazione include informazioni a livello di intestazione relative allo spedizioniere doganale e una descrizione delle merci. Questa funzionalità è supportata dall'entità `ITMFolioEntity`. La tabella seguente elenca i campi e i mapping che compongono questa entità.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Broker consigliato | ITMFolioTable.ShipBrokerAdvised | Data/Ora | Numero | Numero |
| Numero di controllo cargo | ITMFolioTable.ShipCargoControlNumber | Nvarchar(20) | Numero | Numero |
| Appuntamento cliente | ITMFolioTable.ShipCustomerAppointment | Data/Ora | Numero | Numero |
| Broker doganale | ITMFolioTable.ShipCustomsBroker | Nvarchar(20) | Numero | Numero |
| ID dogana | ITMFolioTable.ShipCustomsId | Nvarchar(60) | Numero | Numero |
| Società | ITMFolioTable.ShipDataArea | Nvarchar(4) | Numero | **Sì** |
| Consegnato al magazzino | ITMFolioTable.ShipDelAtWarehouse | Data/Ora | Numero | Numero |
| Istruzioni di consegna | ITMFolioTable.ShipDeliveryInstructions | Data/Ora | Numero | Numero |
| Documenti ricevuti | ITMFolioTable.ShipDocReceived | Int | Numero | Numero |
| Data di consegna stimata | ITMFolioTable.ShipEstDlvDate | Data/Ora | Numero | Numero |
| Data/ora di arrivo stimata al porto di spedizione | ITMFolioTable.ShipEstPortDate | Data/Ora | Numero | Numero |
| Esportatore | ITMFolioTable.ShipExporterId | Nvarchar(20) | Numero | Numero |
| Name | ITMFolioTable.ShipExporterName | Nvarchar(60) | Numero | Numero |
| Data registrazione | ITMFolioTable.ShipFolioDate | Data/Ora | Numero | Numero |
| Registrazione | ITMFolioTable.ShipFolioId | Nvarchar(20) | **Sì** | **Sì** |
| Porto di origine | ITMFolioTable.ShipFromPort | Nvarchar(20) | Numero | Numero |
| Descrizione delle merci | ITMFolioTable.ShipGoodsDesc | Nvarchar(60) | Numero | Numero |
| Merci rilasciate | ITMFolioTable.ShipGoodsReleased | Data/Ora | Numero | Numero |
| Lettera di vettura aerea/Polizza di carico | ITMFolioTable.ShipHAWB | Nvarchar(20) | Numero | Numero |
| Viaggio | ITMFolioTable.ShipId | Nvarchar(20) | Numero | **Sì** |
| Misura | ITMFolioTable.ShipMeasurement | Numeric(32, 6) | Numero | Numero |
| Unità di misura | ITMFolioTable.ShipMeasurementUnit | Int | Numero | Numero |
| Numero di cartoni | ITMFolioTable.ShipNoOfCartons | Numeric(32, 6) | Numero | Numero |
| Polizza di carico originale inviata | ITMFolioTable.ShipOriginalBOLSebt | Data/Ora | Numero | Numero |
| Documenti originali ricevuti | ITMFolioTable.ShipOriginalDocsReceived | Data/Ora | Numero | Numero |
| Stato ordine fornitore | ITMFolioTable.ShipPurchStatus | Int | Numero | Numero |
| Note | ITMFolioTable.ShipRemarks | Nvarchar(MAX) | Numero | Numero |
| Stato viaggio | ITMFolioTable.ShipStatusId | Nvarchar(20) | Numero | Numero |
| Codice tariffa | ITMFolioTable.ShipTariffCode | Nvarchar(10) | Numero | Numero |
| Porto di destinazione | ITMFolioTable.ShipToPort | Nvarchar(20) | Numero | Numero |
| Data valutazione | ITMFolioTable.ShipValuationDate | Data/Ora | Numero | Numero |
| Data di verifica | ITMFolioTable.ShipVerificationDate | Data/Ora | Numero | Numero |
| Account fornitore | ITMFolioTable.VendAccount | Nvarchar(20) | Numero | Numero |

### <a name="number-sequences-for-folios"></a>Sequenze numeriche per registrazioni

La sequenza numerica per le registrazioni controlla l'assegnazione degli ID registrazione.

Il valore che viene passato all'entità di dati come **ID registrazione** (`FolioId`) viene utilizzato per identificare un record esistente per l'aggiornamento. Se quel record non esiste, il comportamento dipende dal fatto che la sequenza numerica assegnata sia configurata per consentire l'immissione manuale:

- Se l'immissione manuale è abilitata, viene creato un nuovo record che utilizza il valore passato.
- Se l'immissione manuale non è abilitata, viene utilizzato il numero successivo nella sequenza numerica assegnata al posto del valore passato.

Durante la sessione di importazione, il valore segnaposto importato come ID registrazione viene mantenuto. Questo comportamento garantisce che le righe di viaggio che fanno riferimento al segnaposto siano correttamente associate e che vengano aggiornate per riflettere il valore assegnato dalla sequenza numerica.

### <a name="field-validations"></a>Convalide del campo

Il campo **Descrizione delle merci** nella tabella registrazioni (`ITMFolioTable`) viene convalidato rispetto all'omonima tabella di impostazione dei costi di spedizione. Uno spedizioniere può utilizzare l'entità di dati dei costi di spedizione `ITMGoodsDescriptionEntity` per leggere i valori esistenti e garantire che i valori validi vengano ricevuti nell'ambiente.

## <a name="voyage-lines-for-purchase-orders-itmpurchaselineentity"></a>Righe di viaggio per ordini fornitore (ITMPurchaseLineEntity)

La riga del viaggio rappresenta una singola riga dell'ordine fornitore inclusa nel viaggio. Questo rapporto si instaura attraverso i campi **Numero ordine fornitore** e **Numero riga di acquisto**. La riga del viaggio fa riferimento a ogni record precedente creato per il viaggio, il contenitore di spedizione e la registrazione. Questa funzionalità è supportata dall'entità `ITMPurchaseLineEntity`. La tabella seguente elenca i campi e i mapping che compongono questa entità.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Valuta | ITMLine.CurrencyCode | Nvarchar(3) | Numero | Numero |
| Importo netto | ITMLine.LineAmountMST | Numeric(32, 6) | Numero | Numero |
| Numero di riga acquisto | ITMLine.RefRecId | Numeric(32, 6) | **Sì** | Numero |
| Contenitore di spedizione | ITMLine.ShipContainerId | Int | Numero | Numero |
| Società | ITMLine.ShipDataArea | Nvarchar(20) | **Sì** | Numero |
| Quantità dichiarata | ITMLine.ShipDeclaredQty | Nvarchar(4) | Numero | Numero |
| Registrazione | ITMLine.ShipFolioId | Numeric(32, 6) | Numero | Numero |
| Viaggio | ITMLine.ShipId | Nvarchar(20) | **Sì** | Numero |
| Numero articolo | ITMLine.ShipItemId | Nvarchar(20) | Numero | Numero |
| Misura | ITMLine.ShipMeasurement | Nvarchar(20) | Numero | Numero |
| Unità di misura | ITMLine.ShipMeasurementUnit | Numeric(32, 6) | Numero | Numero |
| Numero di cartoni | ITMLine.ShipNoOfCartons | Int | Numero | Numero |
| Posizione | ITMLine.ShipPosition | Numeric(32, 6) | Numero | Numero |
| Quantity | ITMLine.ShipQty | Int | Numero | Numero |
| Numero ordine fornitore | ITMLine.TransRefId | Numeric(32, 6) | **Sì** | Numero |
| Unità | ITMLine.UnitId | Int | Numero | Numero |
| Volume | ITMLine.Volume | Nvarchar(10) | Numero | Numero |
| Peso | ITMLine.Weight | Numeric(32, 6) | Numero | Numero |

## <a name="voyage-lines-for-transfer-orders-itmtransferlineentity"></a>Righe di viaggio per ordini di trasferimento (ITMTransferLineEntity)

La riga del viaggio rappresenta una singola riga dell'ordine di trasferimento inclusa nel viaggio. Questo rapporto si instaura attraverso i campi **Numero ordine di trasferimento** e **Numero riga di trasferimento**. La riga del viaggio fa riferimento a ogni record precedente creato per il viaggio, il contenitore di spedizione e la registrazione. Questa funzionalità è supportata dall'entità `ITMTransferLineEntity`. La tabella seguente elenca i campi e i mapping che compongono questa entità.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Valuta | ITMLine.CurrencyCode | Nvarchar(3) | Numero | Numero |
| Importo netto | ITMLine.LineAmountMST | Numeric(32, 6) | Numero | Numero |
| Contenitore di spedizione | ITMLine.ShipContainerId | Int | Numero | Numero |
| Società | ITMLine.ShipDataArea | Nvarchar(20) | **Sì** | Numero |
| Quantità dichiarata | ITMLine.ShipDeclaredQty | Nvarchar(4) | Numero | Numero |
| Registrazione | ITMLine.ShipFolioId | Numeric(32, 6) | Numero | Numero |
| Viaggio | ITMLine.ShipId | Nvarchar(20) | **Sì** | Numero |
| Numero articolo | ITMLine.ShipItemId | Nvarchar(20) | Numero | Numero |
| Misura | ITMLine.ShipMeasurement | Nvarchar(20) | Numero | Numero |
| Unità di misura | ITMLine.ShipMeasurementUnit | Numeric(32, 6) | Numero | Numero |
| Numero di cartoni | ITMLine.ShipNoOfCartons | Int | Numero | Numero |
| Posizione | ITMLine.ShipPosition | Numeric(32, 6) | Numero | Numero |
| Quantity | ITMLine.ShipQty | Int | Numero | Numero |
| Numero riga trasferimento | ITMLine.TransferLineNumber | Numeric(32, 6) | **Sì** | Numero |
| Numero ordine di trasferimento | ITMLine.TransRefId | Numeric(32, 6) | **Sì** | Numero |
| Unità | ITMLine.UnitId | Int | Numero | Numero |
| Volume | ITMLine.Volume | Nvarchar(10) | Numero | Numero |
| Peso | ITMLine.Weight | Numeric(32, 6) | Numero | Numero |

### <a name="reference-table"></a>Tabella riferimenti

Le righe di viaggio vengono create tramite un'associazione con una riga ordine in entrata aperta. Questa riga può essere su un ordine fornitore oppure può essere la transazione di entrata in un ordine di trasferimento. Il campo `RefTableId` nella tabella delle righe di viaggio (`ITMLine`) specifica a quale tipo di ordine è correlata la riga facendo riferimento al numero della tabella. Se nella tabella in cui vengono creati i dati viene fatto riferimento a numeri di tabella specifici, le entità vengono suddivise in base a tali valori.

I valori per la tabella di riferimento (`RefTableId`) e il tipo di transazione (`TransType`) sono impliciti nella selezione dell'entità della riga di acquisto del costo d'acquisto o dell'entità della riga di trasferimento del costo d'acquisto.

### <a name="validation"></a>Convalida

Una riga di viaggio fa riferimento direttamente a un record di viaggio, un record di contenitore di spedizione e un record di registrazione. Se l'entità della riga di acquisto (`ITMPurchaseLinesEntity`) o l'entità della riga di trasferimento (`ITMPurchaseLinesEntity`) viene utilizzata indipendentemente dalle entità utilizzate per creare questi record di riferimento, i valori **ID viaggio** (`ShipId`), **Contenitore** (`ShipContainerId`), e **Folio** (`ShipFolioId`) devono corrispondere a un record esistente nelle tabelle corrispondenti. In caso contrario, l'importazione avrà esito negativo.

Se una delle entità di riga viene utilizzata come parte della stessa sessione di importazione, le altre entità devono precedere la creazione di una riga di viaggio. In caso contrario, i valori non vengono convalidati correttamente. Se viene utilizzato un valore segnaposto per numero di viaggio o registrazione, l'associazione può essere creata solo se lo stesso segnaposto viene utilizzato per il numero di viaggio o registrazione nell'entità della riga di viaggio.

Se l'ordine fornitore o la riga dell'ordine di trasferimento sono già assegnati a una riga di viaggio esistente, la nuova riga di viaggio non verrà creata. Prima che la riga ordine possa essere assegnata a un nuovo viaggio, deve essere rimossa dal viaggio corrente.

### <a name="order-line-identification"></a>Identificazione riga ordine

Le righe di viaggio fanno riferimento direttamente ai valori di riferimento **ID record** (`RefRecId`), **ID dimensione inventario** (`InventDimId`), e **ID transazione inventario** (`InventTransId`). Questi valori non devono più essere inclusi quando viene utilizzata l'entità di dati. Al contrario, ora deve essere incluso il numero della riga dell'ordine. Insieme, il numero della riga dell'ordine e il numero dell'ordine consentono di identificare ciascuno di questi valori di riferimento.

### <a name="voyage-line-quantity"></a>Quantità riga di viaggio

Poiché una riga di viaggio è direttamente associata a una riga d'ordine, il valore **Quantità** (`ShipQty`) che viene immesso utilizzando l'entità richiede che i valori corrispondano. La convalida viene eseguita rispetto alla quantità nella riga dell'ordine fornitore o nella riga di trasferimento. Se la convalida non riesce, il record non verrà elaborato.

### <a name="calculated-fields"></a>Campi calcolati

I campi calcolati **Peso** e **Volume** accettano i valori ricevuti tramite l'entità di dati. Se non vengono forniti valori, i valori di sistema vengono utilizzati per aggiornare questi campi, se sono disponibili valori di sistema. Per il costo di spedizione, i valori sono calcolati nel modo seguente:

- *Peso* = *Quantità* × *Peso lordo articolo*
- *Volume* = *Quantità* × (*Profondità lorda articolo* × *Altezza lorda articolo* × *Larghezza lorda articolo*)

## <a name="sequencing"></a>Sequenziamento

A causa delle dipendenze tra le tabelle, è necessario creare prima il record di viaggio. La riga di viaggio può essere creata solo dopo aver creato il viaggio, il contenitore di spedizione e le registrazioni.

Per creare un viaggio senza avvisi di convalida, il sistema deve elaborare le entità nel seguente ordine:

1. Viaggi (`ITMTableEntity`)
1. Contenitori di spedizione (`ITMContainersEntity`)
1. Registrazioni (`ITMFolioTableEntity`)
1. Righe viaggio (`ITMPurchaseLinesEntity` o `ITMTransferLinesEntity`)
