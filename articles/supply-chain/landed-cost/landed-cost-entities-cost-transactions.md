---
title: Entità di transazione costi
description: Questo articolo fornisce informazioni sulle entità di transazione dei costi, che consentono di dividere il valore di un costo tra i contenuti di un'area di costo tramite la selezione di un metodo di ripartizione.
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
ms.openlocfilehash: 3aabc1356eba27de797fa696dd928cb401d8501b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860814"
---
# <a name="cost-transaction-entities"></a>Entità di transazione costi

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

## <a name="apportionment"></a>Ripartizione

Il costo di spedizione consente di dividere il valore di un costo tra i contenuti di un'area di costo (viaggio, contenitore di spedizione e così via) tramite la selezione di un metodo di ripartizione. Il metodo di ripartizione è impostato nell'ambito della configurazione dei costi automatici basata su regole aziendali. Viene acquisito come parte del costo quando viene creata una riga di viaggio.

### <a name="configure-the-apportionment-mapping-for-use-with-data-entities"></a>Configurare il mapping della ripartizione per l'utilizzo con le entità di dati

Quando un costo viene creato da un'origine esterna come uno spedizioniere, tale origine esterna non può specificare il metodo preferito per la ripartizione del valore del costo. Il mapping della ripartizione definisce il metodo di ripartizione predefinito per ciascun codice del tipo di costo. Si accede alla tabella di mapping della ripartizione dalla pagina **Mapping ripartizione** in Microsoft Dynamics 365 Supply Chain Management (**Costo di spedizione \> Configurazione determinazione costi \> Mapping ripartizione**).

Se è stata definita una combinazione di mapping e viene creato un costo che corrisponde al codice del tipo di costo utilizzando un'entità transazione di costo, verrà utilizzato il metodo di ripartizione mappato anziché qualsiasi valore fornito all'entità.

Se non è presente alcun valore nella tabella di mapping, ma è stato fornito un valore all'entità, verrà utilizzato il valore fornito.

Se non esiste alcun valore né nella tabella di mapping né nel record che è stato inviato all'entità, la creazione avrà esito negativo.

### <a name="apportionment-mapping-itmapportionmentmapping"></a>Mapping di ripartizione (ITMApportionmentMapping)

L'entità di mapping di ripartizione (`ITMApportionmentMapping`) crea relazioni di mapping di ripartizione e consente agli utenti di creare o aggiornare i record.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Metodo di ripartizione | ITMApportionmentMapping.ApportionmentMethod | Int | Numero | Numero |
| Codice tipo di costo | ITMApportionmentMapping.ShipCostTypeId | Nvarchar(20) | **Sì** | Numero |

## <a name="voyage-costs-itmcosttransvoyageentity"></a>Costi di viaggio (ITMCostTransVoyageEntity)

L'entità dei costi di viaggio (`ITMCostTransVoyageEntity`) crea le transazioni relative ai costi di viaggio che vengono applicate a livello di viaggio. Durante il processo di importazione, il sistema utilizza i valori **Categoria** e **Metodo di ripartizione** che sono inclusi nell'entità per determinare come il valore del costo è ripartito tra i contenuti del viaggio.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Metodo di ripartizione | ITMCostTrans.ApportionmentMethod | Int | Numero | Numero |
| Valore di costo | ITMCostTrans.CostValue | Numeric(32, 6) | Numero | Numero |
| Valuta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Numero | **Sì** |
| Numero riga | ITMCostTrans.LineNum | Numeric(32, 16) | **Sì** | Numero |
| Tipo di costo collegato | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Numero | Numero |
| Costo minimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Numero | Numero |
| Categoria | ITMCostTrans.ShipCostCategory | Int | Numero | Numero |
| Codice tipo di costo | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Numero | Numero |
| Società | ITMCostTrans.ShipDataArea | Nvarchar(4) | Numero | **Sì** |
| Viaggio | ITMCostTrans.TransRecId | Nvarchar(20) | **Sì** | Numero |
| Fascia IVA articoli | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Numero | Numero |

## <a name="shipping-container-costs-itmcosttransshippingcontainerentity"></a>Costi del contenitore di spedizione (ITMCostTransShippingContainerEntity)

L'entità dei costi del contenitore di spedizione (`ITMCostTransShippingContainerEntity`) crea i costi del contenitore di spedizione che vengono applicati a livello di contenitore di spedizione. Durante il processo di importazione, il sistema utilizza i valori **Categoria** e **Metodo di ripartizione** che sono inclusi nell'entità per determinare come il valore del costo è ripartito tra i contenuti del contenitore di spedizione.

I campi **Aggregazione**, **Scalo**, e **Scalo collegato** sono specifici dei record in cui il valore **Area costi** è *Contenitore di spedizione*. Pertanto, non sono presenti nelle entità di dati per altre aree di costo.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Aggregazione | ITMCostTrans.AggregatedCost | Int | Numero | Numero |
| Metodo di ripartizione | ITMCostTrans.ApportionmentMethod | Int | Numero | Numero |
| Valore di costo | ITMCostTrans.CostValue | Numeric(32, 6) | Numero | Numero |
| Valuta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Numero | **Sì** |
| Numero riga | ITMCostTrans.LineNum | Numeric(32, 16) | **Sì** | Numero |
| Tipo di costo collegato | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Numero | Numero |
| Scalo collegato | ITMCostTrans.LinkLegId | Nvarchar(20) | Numero | Numero |
| Costo minimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Numero | Numero |
| Contenitore di spedizione | ITMCostTrans.TransRecId | Nvarchar(20) | **Sì** | Numero |
| Categoria | ITMCostTrans.ShipCostCategory | Int | Numero | Numero |
| Codice tipo di costo | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Numero | Numero |
| Società | ITMCostTrans.ShipDataArea | Nvarchar(4) | Numero | **Sì** |
| Viaggio | ITMCostTrans.TransRecId | Nvarchar(20) | **Sì** | Numero |
| Scalo | ITMCostTrans.ShipLegId | Nvarchar(20) | Numero | Numero |
| Fascia IVA articoli | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Numero | Numero |

## <a name="folio-costs-itmcosttransfolioentity"></a>Costi di registrazione (ITMCostTransFolioEntity)

L'entità costi di registrazione (`ITMCostTransFolioEntity`) crea record di transazione dei costi che si applicano al livello di registrazione. Durante il processo di importazione, il sistema utilizza i valori **Categoria** e **Metodo di ripartizione** che sono inclusi nell'entità per determinare come il valore del costo è ripartito tra i contenuti di ogni registrazione.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Metodo di ripartizione | ITMCostTrans.ApportionmentMethod | Int | Numero | Numero |
| Valore di costo | ITMCostTrans.CostValue | Numeric(32, 6) | Numero | Numero |
| Valuta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Numero | **Sì** |
| Numero riga | ITMCostTrans.LineNum | Numeric(32, 16) | **Sì** | Numero |
| Tipo di costo collegato | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Numero | Numero |
| Costo minimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Numero | Numero |
| Categoria | ITMCostTrans.ShipCostCategory | Int | Numero | Numero |
| Codice tipo di costo | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Numero | Numero |
| Società | ITMCostTrans.ShipDataArea | Nvarchar(4) | Numero | **Sì** |
| Registrazione | ITMCostTrans.TransRecId | Nvarchar(20) | **Sì** | Numero |
| Fascia IVA articoli | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Numero | Numero |

## <a name="purchase-order-costs-itmcosttranspurchaseentity"></a>Costi dell'ordine fornitore (ITMCostTransPurchaseEntity)

L'entità dei costi dell'ordine fornitore (`ITMCostTransPurchaseEntity`) crea le transazioni di costo che si applicano all'intestazione dell'ordine fornitore. Durante il processo di importazione, il sistema utilizza i valori **Categoria** e **Metodo di ripartizione** che sono inclusi nell'entità per determinare come il valore del costo è ripartito tra i contenuti di ogni registrazione.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Metodo di ripartizione | ITMCostTrans.ApportionmentMethod | Int | Numero | Numero |
| Valore di costo | ITMCostTrans.CostValue | Numeric(32, 6) | Numero | Numero |
| Valuta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Numero | **Sì** |
| Numero riga | ITMCostTrans.LineNum | Numeric(32, 16) | **Sì** | Numero |
| Tipo di costo collegato | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Numero | Numero |
| Costo minimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Numero | Numero |
| Ordine fornitore | ITMCostTrans.TransRecId | Nvarchar(20) | **Sì** | Numero |
| Categoria | ITMCostTrans.ShipCostCategory | Int | Numero | Numero |
| Codice tipo di costo | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Numero | Numero |
| Società | ITMCostTrans.ShipDataArea | Nvarchar(4) | Numero | **Sì** |
| Fascia IVA articoli | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Numero | Numero |

## <a name="item-costs-itmcosttransitementity"></a>Costi dell'articolo (ITMCostTransItemEntity)

L'entità costi dell'articolo (`ITMCostTransItemEntity`) crea le transazioni dei costi che si applicano al livello di articolo. Questa entità è specifica per gli articoli nelle righe ordine fornitore. Il valore del costo viene applicato integralmente alla riga.

I campi **Importo rettifica** e **Rettifica valore** sono specifici delle aree di costo a livello di riga. Pertanto, non sono presenti nelle entità di dati per altre aree di costo.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Importo di rettifica | ITMCostTrans.AdjustmentAmount | Numeric(32, 6) | Numero | Numero |
| Valore di costo | ITMCostTrans.CostValue | Numeric(32, 6) | Numero | Numero |
| Valuta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Numero | **Sì** |
| Numero riga | ITMCostTrans.LineNum | Numeric(32, 16) | **Sì** | Numero |
| Tipo di costo collegato | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Numero | Numero |
| Costo minimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Numero | Numero |
| Ordine fornitore | ITMCostTrans.TransRecId | Nvarchar(20) | **Sì** | Numero |
| Numero di riga ordine fornitore | ITMCostTrans.TransRecId | Nvarchar(20) | **Sì** | Numero |
| Categoria | ITMCostTrans.ShipCostCategory | Int | Numero | Numero |
| Codice tipo di costo | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Numero | Numero |
| Società | ITMCostTrans.ShipDataArea | Nvarchar(4) | Numero | **Sì** |
| Fascia IVA articoli | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Numero | Numero |
| Rettifica valore | ITMCostTrans.ValueAdjustmentMethod | Int | Numero | Numero |

## <a name="transfer-line-costs-itmcosttranstransferlineentity"></a>Costi della riga di trasferimento (ITMCostTransTransferLineEntity)

L'entità dei costi della riga di trasferimento (`ITMCostTransTransferLineEntity`) crea transazioni di costo che si applicano al livello di riga dell'ordine di trasferimento. Il valore dei costi viene applicato integralmente alla riga di ordine di trasferimento.

I campi **Importo rettifica** e **Rettifica valore** sono specifici delle aree di costo a livello di riga. Pertanto, non sono presenti nelle entità di dati per altre aree di costo.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Importo di rettifica | ITMCostTrans.AdjustmentAmount | Numeric(32, 6) | Numero | Numero |
| Valore di costo | ITMCostTrans.CostValue | Numeric(32, 6) | Numero | Numero |
| Valuta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Numero | **Sì** |
| Numero riga | ITMCostTrans.LineNum | Numeric(32, 16) | **Sì** | Numero |
| Tipo di costo collegato | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Numero | Numero |
| Costo minimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Numero | Numero |
| Categoria | ITMCostTrans.ShipCostCategory | Int | Numero | Numero |
| Codice tipo di costo | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Numero | Numero |
| Società | ITMCostTrans.ShipDataArea | Nvarchar(4) | Numero | **Sì** |
| Ordine di trasferimento | ITMCostTrans.TransRecId | Nvarchar(20) | **Sì** | Numero |
| Numero di righe ordine di trasferimento | ITMCostTrans.TransRecId | Nvarchar(20) | **Sì** | Numero |
| Fascia IVA articoli | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Numero | Numero |
| Rettifica valore | ITMCostTrans.ValueAdjustmentMethod | Int | Numero | Numero |

### <a name="transaction-table"></a>Tabella transazioni

Un record di transazione di costo è associato a un'area di costo tramite l'assegnazione di un numero di tabella di transazione (`TransTableId`). Quando sono richiesti numeri di identificazione della tabella specifici, le entità vengono suddivise in base a questi valori, in modo che esista un'entità per ciascuna area di costo.

Il valore per la tabella delle transazioni (`TransTableId`) è implicito nella selezione dell'entità della transazione di costo.

### <a name="calculated-fields"></a>Campi calcolati

I seguenti campi non sono disponibili per l'inserimento o l'aggiornamento quando viene utilizzata un'entità di transazione dei costi, poiché questi campi vengono impostati solo quando vengono intraprese azioni specifiche rispetto al record di viaggio:

- **Costo stimato** – Questo campo viene impostato quando viene registrata una fattura per il viaggio (ordine fornitore) o viene ricevuto un trasferimento.
- **Valuta costo stimato** – Questo campo viene impostato quando viene registrata una fattura per il viaggio (ordine fornitore) o viene ricevuto un trasferimento.
- **Costo effettivo** – Questo campo viene impostato quando viene registrata una fattura fornitore. È associato al costo.

### <a name="find-auto-costs"></a>Trova costi automatici

Un pulsante **Trova costi automatici** disponibile per ciascuna area di costo (viaggio, contenitore di spedizione e così via) consente di aggiornare le transazioni di costo per tale area di costo dalle informazioni nelle tabelle di configurazione. Quando si seleziona il pulsante per un'area di costo, il sistema cancella i costi esistenti per quell'area di costo e crea nuovi record, in base alla configurazione corrente delle tabelle di impostazione dei costi automatici.

I record di transazione dei costi creati utilizzando un'entità di dati vengono contrassegnati come importati. Questi record non vengono eliminati quando selezioni **Trova costi automatici**, perché non verranno ricreati dalle tabelle di impostazione dei costi automatici. Tuttavia, è ancora possibile eliminare un record di transazione dei costi contrassegnato come importato.

### <a name="linked-fields"></a>Campi collegati

Ciascuna transazione di costo può essere associata a un altro record nella stessa area di costo. Questa associazione è costituita attraverso il campo **Tipo di costo collegato**. Consente di calcolare un valore di costo come percentuale di un altro costo.

Il campo **Tipo di costo collegato** può essere convalidato solo se il record a cui si fa riferimento viene elaborato per primo o se esiste già nella tabella. Lo stesso requisito vale per il campo **Scalo collegato** utilizzato solo per i costi nell'area dei costi del contenitore di spedizione.
