---
title: Assegnare icone e titoli dei passaggi per l'app per dispositivi mobili Warehouse Management
description: In questo argomento viene descritto come assegnare icone e titoli dei passaggi per flussi di attività nuovi o personalizzati per l'app per dispositivi mobili Warehouse Management.
author: MarkusFogelberg
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: d1d595e7f8ae3cf344c891844845738a4592328eecc326f11e9a2aa0e303785a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733350"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a>Assegnare icone e titoli dei passaggi per l'app per dispositivi mobili Warehouse Management

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come assegnare icone e titoli dei passaggi per flussi di attività nuovi o personalizzati per l'app per dispositivi mobili Warehouse Management.

Le seguenti illustrazioni mostrano come vengono visualizzati i titoli e le icone dei passaggi nell'app per dispositivi mobili Warehouse Management.

![Esempio di un'icona di passaggio e un titolo di passaggio nell'app per dispositivi mobili Warehouse Management.](media/step-icon-example.png "Esempio di un'icona di passaggio e un titolo di passaggio nell'app per dispositivi mobili Warehouse Management")

## <a name="turn-on-this-feature-in-your-system"></a>Attivare la funzionalità nel tuo sistema

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione magazzino*
- **Nome funzionalità:** *Impostazioni utente, icone e titoli dei passaggi per la nuova app di magazzino*

## <a name="standard-step-ids-classes-and-icons"></a>ID, classi e icone del passaggio standard

Ogni passaggio in un flusso di attività è identificato da un ID passaggio e ogni ID passaggio ha una classe di passaggio corrispondente. L'icona e il titolo del passaggio sono specificati in ciascuna classe di passaggio.

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a>ID passaggio e classi di passaggio

La tabella seguente elenca tutti gli ID passaggio attualmente disponibili e la classe di passaggio corrispondente. Il nome di controllo del campo di input principale viene utilizzato come ID passaggio.

Per un esempio che mostra come vengono utilizzati questi ID e classi di passaggio, vedi l'implementazione del metodo `WHSMobileAppStepInfoBuilder.stepId()` nella sezione [ Esempio: assegnare icone e titoli dei passaggi per un flusso personalizzato](#example) più avanti in questo argomento.

| ID fase | Classe di passaggio |
|-|-|
| BatchDisposition | WHSMobileAppStepBatchDisposition |
| Vettore | WHSMobileAppStepCarrier |
| CatchWeight | WHSMobileAppStepCatchWeight |
| CatchWeightQtyOutboundWeight | WHSMobileAppStepCatchWeight |
| CatchWeightTag | WHSMobileAppStepCatchWeightTag |
| CatchWeightTagWeight | WHSMobileAppStepCatchWeightTagWeight |
| ChangeWarehouseSuccess | WHSMobileAppStepChangeWarehouseSuccess |
| CheckDigit | WHSMobileAppStepCheckDigit |
| ClusterId | WHSMobileAppStepClusterId |
| ClusterPickQtyVerification | WHSMobileAppStepQtyVerification |
| ClusterPosition | WHSMobileAppStepClusterPosition |
| ConfigId | WHSMobileAppStepConfigId |
| Conferma | WHSMobileAppStepConfirmation |
| ConsolidateFromLicensePlateId | WHSMobileAppStepConsolidateFromLicensePlateId |
| ConsolidateLPConfirmation | WHSMobileAppStepConsolidateLPConfirmation |
| ConsolidateToLicensePlateId | WHSMobileAppStepConsolidateToLicensePlateId |
| ContainerType | WHSMobileAppStepContainerType |
| CountingReasonCode | WHSMobileAppStepCountingReasonCode |
| CycleCountingAddLPOrFinish | WHSMobileAppStepCycleCountingAddLPOrFinish |
| CycleCountQty1 | WHSMobileAppStepCycleCountQty |
| CycleCountQty2 | WHSMobileAppStepCycleCountQty |
| CycleCountQty3 | WHSMobileAppStepCycleCountQty |
| CycleCountQty4 | WHSMobileAppStepCycleCountQty |
| Disposition | WHSMobileAppStepDisposition |
| DriverCheckInConfirmation | WHSMobileAppStepDriverCheckInConfirmation |
| DriverCheckInId | WHSMobileAppStepDriverCheckInId |
| DriverCheckOutConfirmation | WHSMobileAppStepDriverCheckOutConfirmation |
| DriverCheckOutId | WHSMobileAppStepDriverCheckOutId |
| ExpDate | WHSMobileAppStepExpDate |
| FromBatchDisposition | WHSMobileAppStepFromBatchDisposition |
| FromInventoryStatus | WHSMobileAppStepInventoryStatusFrom |
| FullQty | WHSMobileAppStepFullQty |
| InboundPut | WHSMobileAppStepInboundPut |
| InventBatchId | WHSMobileAppStepBatch |
| InventColorId | WHSMobileAppStepInventColorId |
| InventLocation | WHSMobileAppStepInventLocation |
| InventLocationId | WHSMobileAppStepWarehouse |
| InventSerialId | WHSMobileAppStepInventSerialId |
| InventSizeId | WHSMobileAppStepInventSizeId |
| InventStatusId | WHSMobileAppStepInventStatus |
| InventStyleId | WHSMobileAppStepInventStyleId |
| InventVersionId | WHSMobileAppStepInventVersionId |
| ItemId | WHSMobileAppStepItem |
| ITMContainerID | ITMMobileAppStepContainerId |
| ITMShipmentID | ITMMobileAppStepShipmentId |
| KanbanCardId | WHSMobileAppStepKanbanCard |
| KanbanCardToEmpty | WHSMobileAppStepKanbanCardToEmpty |
| KanbanOrCardId | WHSMobileAppStepKanbanCard |
| LicensePlateId | WHSMobileAppStepLicensePlate |
| LoadId | WHSMobileAppStepLoadId |
| LocationLicensePlatePosition | WHSMobileAppStepLocationLicensePlatePosition |
| LocOrLP | WHSMobileAppStepLocOrLP |
| LocOrLP_From | WHSMobileAppStepLocOrLPFrom |
| LocOrLP_To | WHSMobileAppStepLocOrLPTo |
| LocOrLPCheck | WHSMobileAppStepLocOrLPCheck |
| LocVerification | WHSMobileAppStepLocVerification |
| LPAdjustIn | WHSMobileAppStepLPAdjustIn |
| LPBreakChildLP | WHSMobileAppStepLPBreakChildLP |
| LPBreakParentLP | WHSMobileAppStepLPBreakParentLP |
| LPBuildChildLP | WHSMobileAppStepLPBuildChildLP |
| LPBuildParentLP | WHSMobileAppStepLPBuildParentLP |
| LPVerification | WHSMobileAppStepLPVerification |
| MergeContainerId | WHSMobileAppStepMergeContainerId |
| MixedLPLineNum | WHSMobileAppStepMixedLPLineNum |
| MobileDeviceQueueMessageCollectionIdentifierId | WHSMobileAppStepSelectOrder |
| MovementConfirmCancel | WHSMobileAppStepMovementConfirmCancel |
| NewCaptureWeight | WHSMobileAppStepCatchWeight |
| NewQty | WHSMobileAppStepNewQty |
| OutboundCatchWeightTag | WHSMobileAppStepCatchWeightTag |
| OutboundPut | WHSMobileAppStepOutboundPut |
| OutboundWeight | WHSMobileAppStepCatchWeight |
| OverridePutNewLocation | WHSMobileAppStepOverridePutNewLocation |
| PieceByPieceConfirmation | WHSMobileAppStepQtyVerification |
| POLineNum | WHSMobileAppStepPOLineNum |
| Numero ordine fornitore | WHSMobileAppStepPONum |
| PositionFull | WHSMobileAppStepPositionFull |
| PositionFullQty | WHSMobileAppStepPositionFullQty |
| Potenza | WHSMobileAppStepPotency |
| PrinterName | WHSMobileAppStepPrinterName |
| ProdId | WHSMobileAppStepProdId |
| ProdLastPalletConfirmation | WHSMobileAppStepProdLastPalletConfirmation |
| ProductConfirmation | WHSMobileAppStepProductConfirmation |
| ProductionScrapConfirmation | WHSMobileAppStepProductionScrapConfirmation |
| Inserisci | WHSMobileAppStepPut |
| PutawayClusterId | WHSMobileAppStepPutawayClusterId |
| Quantità | WHSMobileAppStepQty |
| QtyAdjust | WHSMobileAppStepQtyAdjust |
| QtyShort | WHSMobileAppStepQtyShort |
| QtyToConsume | WHSMobileAppStepQtyToConsume |
| QtyToPick | WHSMobileAppStepQtyToPick |
| QtyToPut | WHSMobileAppStepQtyToPut |
| QtyToScrap | WHSMobileAppStepQtyToScrap |
| QtyVerification | WHSMobileAppStepQtyVerification |
| QtyWithScanningLimit | WHSMobileAppStepQtyAdjust |
| ReasonString | WHSMobileAppStepReasonString |
| RecvLocationId | WHSMobileAppStepRecvLocationId |
| RemoveContainerId | WHSMobileAppStepRemoveContainerId |
| ReprintLabelConfirmation | WHSMobileAppStepReprintLabelConfirmation |
| RMANum | WHSMobileAppStepRMANum |
| ShortPickReason | WHSMobileAppStepShortPickReason |
| SortConOrLP | WHSMobileAppStepSortConOrLP |
| SortLicensePlateId | WHSMobileAppStepSortLicensePlateId |
| SortPositionId | WHSMobileAppStepSortPositionId |
| SortVerification | WHSMobileAppStepSortVerification |
| StartLocationId | WHSMobileAppStepStartLocationId |
| StartProdOrderConfirmation | WHSMobileAppStepStartProdOrderConfirmation |
| TargetLicensePlateId | WHSMobileAppStepTargetLicensePlateId |
| TOLineNum | WHSMobileAppStepTOLineNum |
| ToLocation | WHSMobileAppStepToLocation |
| N. OT | WHSMobileAppStepTONum |
| ToWarehouse | WHSMobileAppStepWarehouseTo |
| TransportLoadId | WHSMobileAppStepTransportLoadId |
| WaveLabelId | WHSMobileAppStepWaveLabelId |
| WaveLblQty | WHSMobileAppStepWaveLblQty |
| Peso | WHSMobileAppStepWeight |
| WeightToConsume | WHSMobileAppStepWeightToConsume |
| WHSAdjustmentType | WHSMobileAppStepWHSAdjustmentType |
| WHSReceivingException | WHSMobileAppStepWHSReceivingException |
| WHSWorkException | WHSMobileAppStepWHSWorkException |
| WHSWorkLicensePlateId | WHSMobileAppStepWorkLicensePlateId |
| WMSLocationId | WHSMobileAppStepLocation |
| WorkId | WHSMobileAppStepWorkId |
| WorkIdToCancel | WHSMobileAppStepWorkIdToCancel |
| WorkLPIdPutawayCluster | WHSMobileAppStepWorkLPIdPutawayCluster |
| WorkPoolId | WHSMobileAppStepWorkPoolId |
| ZoneId | WHSMobileAppStepZoneId |

### <a name="available-step-icons"></a><a name="step-icons"></a>Icone dei passaggi disponibili

Il sistema include una raccolta di icone dei passaggi standard che è possibile utilizzare anche per i passaggi personalizzati. Al momento non puoi caricare icone di passaggio personalizzate. Pertanto, è sempre necessario selezionare una delle icone dei passaggi standard.

La tabella seguente mostra tutte le icone dei passaggi standard attualmente disponibili e il relativo nome.

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="Informazioni sull'icona di passaggio"><br>Informazioni</td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="Aggiungere la targa o icona passaggio dell'articolo"><br>AddLpOrItem</td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="Icona del passaggio di smaltimento batch"><br>BatchDisposition</td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Icona del passaggio del vettore"><br>Vettore</td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="Icona del passaggio dell'etichetta di peso variabile"><br>CatchWeightTag</td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="Icona del passaggio del peso dell'etichetta di peso variabile"><br>CatchWeightTagWeight</td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="Icona del passaggio della cifra di controllo"><br>CheckDigit</td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="Icona del passaggiodi controllo dell'ID di entrata o di uscita"><br>CheckInOutId</td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="Icona del passaggio della targa figlio"><br>ChildLP</td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="Icona del passaggio ID cluster"><br>ClusterId</td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="Icona del passaggio posizione cluster"><br>ClusterPosition</td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="Icona del passaggio ID configurazione"><br>ConfigId</td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="Icona del passaggio del campo configurato"><br>ConfiguredField</td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Icona del passaggio configurazione o targa"><br>ConOrLP</td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="Icona del passaggio di consolidamento dall'ID targa"><br>ConsolidateFromLicensePlateID</td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="Icona del passaggio di consolidamento sull'ID targa"><br>ConsolidateToLicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="Icona del passaggio del tipo di contenitore"><br>ContainerType</td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="Icona del passaggio di conteggio"><br>Conteggio</td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="Icona del passagio di conteggio del codice motivo"><br>CountingReasonCode</td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="Icona del passaggio del codice del paese di origine"><br>CountryOfOrigin</td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="Icona del passaggio di smaltimento"><br>Disposition</td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="Icona del passaggio Fatto"><br>Fatto</td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="Icona del passaggio di conferma del check in del conducente"><br>DriverCheckInConfirmation</td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="Icona del passaggio dell'ID di check in del conducente"><br>DriverCheckInId</td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="Icona del passaggio dell'ID di check out del conducente"><br>DriverCheckOutId</td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="Icona del passaggio della data di scadenza"><br>ExpDate</td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="Icona del passaggio del campo"><br>Campo</td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="Icona del passaggio da smaltimento batch"><br>FromBatchDisposition</td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="Icona del passaggio da stato inventario"><br>FromInventoryStatus</td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="Icona del passaggio attributo ID"><br>IdAttribute</td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="Icona del passaggio dell'ID batch dell'inventario"><br>InventBatchID</td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="Icona del passaggio dell'ID colore inventario"><br>InventColorID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="Icona del passaggio posizione inventario"><br>InventLocation</td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="Icona del passaggio dell'ID seriale inventario"><br>InventSerialID</td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="Icona del passaggio ID dimensioni inventario"><br>InventSizeID</td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="Icona del passaggio ID stato inventario"><br>InventStatusID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="Icona del passaggio ID stile inventario"><br>InventStyleID</td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="Icona del passaggio ID versione inventario"><br>InventVersionID</td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="Icona del passaggio ID articolo"><br>ItemID</td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="Icona del passaggio ID contenitore ITM"><br>ITMContainerID</td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="Icona del passaggio ID spedizione ITM"><br>ITMShipmentID</td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="Icona del passaggio ID scheda kanban"><br>KanbanCardID</td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="Icona del passaggio ID scheda o kanban"><br>KanbanOrCardID</td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="Icona del passaggio ID targa"><br>LicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="Icona del passaggio ID carico"><br>LoadId</td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="Icona del passaggio posizionamento targa ubicazione"><br>LocationLicensePlatePosition</td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="Icona del passaggio targa o ubicazione"><br>LocOrLP</td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="Icona del passaggio di controllo della targa o dell'ubicazione"><br>LocOrLPCheck</td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="Icona del passaggio dalla targa o ubicazione"><br>LocOrLPFrom</td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="Icona del passaggio a targa o ubicazione"><br>LocOrLPTo</td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="Icona del passaggio di processo lungo completato"><br>LongProcessCompleted</td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="Icona del passaggio targa padre di interruzione targa"><br>LPBreakParentLP</td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="Icona del passaggio ID contenitore unione"><br>MergeContainerId</td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="Icona del passaggio del numero di riga di targa mista"><br>MixedLPLineNum</td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="Icona del passo di peso in uscita"><br>OutboundWeight</td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="Icona del passaggio del proprietario"><br>Proprietario</td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="Icona del passaggio della targa padre"><br>ParentLP</td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="Icona del passaggio Conferma"><br>PleaseConfirm</td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="Icona del passaggio numero di riga ordine fornitore"><br>POLineNum</td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="Icona del passaggio numero ordine fornitore"><br>Numero ordine fornitore</td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="Icona del passaggio Posizione piena"><br>PositionFull</td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="Icona del passaggio di potenza"><br>Potenza</td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="Icona del passaggio del nome della stampante"><br>PrinterName</td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="Icona del passaggio ID produzione"><br>ProdId</td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="Icona del passaggio di conferma del prodotto"><br>ProductConfirmation</td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="Icona del passaggio Put"><br>Inserisci</td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="Icona del passaggio ID cluster stoccaggio"><br>PutawayClusterId</td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="Icona del passaggio di quantità"><br>Quantità</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="Icona del passaggio regolazione della quantità in entrata"><br>QtyAdjustIn</td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="Icona del passaggio di quantità scarsa"><br>QtyShort</td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="Icona del passaggio Quantità da consumare"><br>QtyToConsume</td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="Icona del passaggio Quantità da stoccare"><br>QtyToPut</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="Icona del passaggio Quantità da scartare"><br>QtyToScrap</td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="Icona del passaggio di conferma della quantità"><br>QuantityConfirmation</td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="Icona del passaggio Segnala come processo finito"><br>RAFEndJob</td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="Icona del passaggio ID della posizione di ricevimento"><br>RecvLocationID</td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="Icona del passaggio rimuovi ID contenitore"><br>RemoveContainerID</td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="Icona del passaggio del numero RMA"><br>RMANum</td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="Icona del passaggio Seleziona ordine"><br>SelectOrder</td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="Icona del passaggio del motivo del prelievo in difetto"><br>ShortPickReason</td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="Icona del passaggio ID posizione ordinamento"><br>SortPositionId</td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="Icona del passaggio ID targa di destinazione"><br>TargetLicensePlateId</td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="Icona del passaggio numero di riga di destinazione"><br>ToLineNum</td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="Icona del passaggio posizione destinazione"><br>ToLocation</td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="Icona del passaggio del numero destinazione"><br>ToNum</td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="Icona del passaggio Al magazzino"><br>ToWarehouse</td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="Icona del passaggio ID carico trasporto"><br>TransportLoadId</td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="Icona del passaggio dell'ID batch fornitore"><br>VendBatchId</td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="Icona del passaggio ID etichetta ondata"><br>WaveLabelId</td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="Icona del passaggio quantità etichetta ondata"><br>WaveLblQty</td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="Icona del passo del peso"><br>Peso</td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="Icona del passaggio Peso da consumare"><br>WeightToConsume</td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="Icona del passaggio del tipo di rettifica magazzino"><br>WHSAdjustmentType</td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="Icona del passaggio di eccezione ricezione magazzino"><br>WHSReceivingException</td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="Icona del passaggio ID ubicazione magazzino"><br>WMSLocationID</td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="Icona del passaggio ID lavoro"><br>WorkId</td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="Icona del passaggio ID lavoro da annullare"><br>WorkIdToCancel</td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="Icona del passaggio ID targa lavoro"><br>WorkLicensePlateId</td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="Icona del passaggio cluster di stocccaggio ID targa lavoro"><br>WorkLPIDPutawayCluster</td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="Icona del passaggio ID pool lavoro"><br>WorkPoolID</td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="Icona del passaggio ID zona"><br>ZoneID</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a>Esempio: assegnare icone e titoli dei passaggi per un flusso personalizzato

Questo esempio spiega come configurare le icone e i titoli dei passaggi per un flusso di attività personalizzato. Lo scenario si basa su un esempio di un flusso di attività personalizzato che viene presentato ed esplorato in modo più dettagliato nel seguente post del blog: [Personalizzazione dell'app per dispositivi mobili Warehousing](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app). Il flusso delle attività funziona nel modo seguente:

1. L'app mostra una pagina che richiede al lavoratore di fornire un ID contenitore (ad esempio, effettuando la scansione di un codice a barre).
1. Se l'ID contenitore è valido, l'app apre una nuova pagina che richiede al lavoratore il peso. (Se l'ID contenitore non è valido, il lavoratore viene indirizzato nuovamente alla prima pagina.)
1. Quando il lavoratore immette un peso valido, il sistema memorizza il peso e riporta il lavoratore alla prima pagina.

Nella figura seguente viene illustrato questo flusso di attività.

![Diagramma del flusso di attività.](media/step-icons-example-task-flow.png "Diagramma del flusso di attività")

### <a name="create-a-step-class-for-the-container-input-page"></a>Creare una classe di passaggio per la pagina di input del contenitore

La pagina di input del contenitore consente all'operatore di eseguire la scansione o di inserire un ID contenitore.

![Pagina di input del contenitore.](media/step-icons-example-container-input.png "Pagina di input del contenitore")

Nella pagina di input del contenitore, il nome del controllo del campo di input è `ContainerId`. Poiché questo nome di controllo non è nell'[elenco di ID passaggio](#step-ids-classes), non troverai un passaggio esistente basato su di esso. Pertanto, è necessario creare una classe di passaggio che rappresenti il passaggio. Ecco un esempio.

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

L'identificatore dell'icona del passaggio è archiviato nel membro della classe `defaultStepIcon` e il titolo del passaggio viene archiviato nel membro della classe `defaultStepTitle`.

Per assegnare un'icona di passaggio, imposta `defaultStepIcon` su uno degli ID icona elencati nella sezione [Icone dei passaggi disponibili](#step-icons) precedente in questo argomento.

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a>Utilizzare un'icona di passaggio standard o personalizzata e un titolo per l'immissione del peso

La pagina di input del peso consente al lavoratore di inserire un peso.

![Pagina di input del peso.](media/step-icons-example-weight-input.png "Pagina di input del peso")

Nella pagina di input del peso, il nome del controllo del campo di input è `Weight`, che si trova nell'[elenco di ID di passaggio](#step-ids-classes). Pertanto, se l'icona e il titolo del passaggio definiti nella classe `WHSMobileAppStepWeight` sono accettabili per te, non devi cambiare nulla per questo passaggio.

Tuttavia, se preferisci utilizzare un'icona o un titolo diverso per questo passaggio, è possibile sostituire il metodo `stepId()` o il metodo `stepInfo()` nella classe builder. Ogni flusso di attività ha il proprio generatore di informazioni sui passaggi.

#### <a name="override-the-stepid-method"></a>Sostituire il metodo stepId()

L'esempio seguente mostra un modo in cui è possibile modificare una classe builder sovrascrivendo il metodo `stepId()`.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

Quindi crei una classe di passaggi per il passaggio `NewWeight`. Il codice dovrebbe essere simile al codice per l'esempio `ContainerId` mostrato in precedenza in questo argomento.

#### <a name="override-the-stepinfo-method"></a>Sostituire il metodo stepInfo()

L'esempio seguente mostra un modo in cui è possibile modificare una classe builder sovrascrivendo il metodo `stepInfo()`.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

Quindi costruisci un oggetto `WHSMobileAppStepInfo` e imposti direttamente l'icona e/o il titolo.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Installare e connettere l'app per dispositivi mobili Gestione magazzino](install-configure-warehouse-management-app.md)
- [Impostazioni utente dispositivo mobile](mobile-device-user-settings.md)
