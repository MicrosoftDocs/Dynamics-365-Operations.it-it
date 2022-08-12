---
title: Entità di fatture fornitore
description: Questo articolo fornisce informazioni sulle entità fattura fornitore, che consentono di configurare i codici del tipo di costo per i costi interni o per i costi derivati esternamente.
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
ms.openlocfilehash: f0371cf9862afaf3bc43a44def725c420e9aaf56
ms.sourcegitcommit: 5b34b41ae74269ba639e2876bc5862ef468da1cc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2022
ms.locfileid: "9166745"
---
# <a name="vendor-invoice-entities"></a>Entità di fatture fornitore

[!include [banner](../includes/banner.md)]

Il modulo **Costo di spedizione** consente di configurare i codici del tipo di costo per i costi interni o per i costi derivati esternamente. Se un costo è esterno a un'azienda, è prevista una fattura dal fornitore del servizio. Questa fattura viene elaborata come giornale di registrazione fatture che può essere associato a un viaggio e il valore della fattura può essere distribuito su uno o più costi del viaggio.

Le entità fattura fornitore consentono di allocare il valore di una riga del giornale di registrazione a uno o più costi di un viaggio che condividono lo stesso codice del tipo di costo.

È possibile allocare un costo solo se esistono l'intestazione del giornale di registrazione fattura e le righe del giornale di registrazione fattura.

## <a name="vendor-voyage-cost-allocations-itmledgerjournalcostlinesvoyagesentity"></a>Allocazioni dei costi di viaggio del fornitore (ITMLedgerJournalCostLinesVoyagesEntity)

L'entità di dati allocazioni dei costi di viaggio del fornitore consente di allocare una riga di fattura fornitore su uno o più costi applicati all'area dei costi di viaggio. Questa funzionalità è supportata dall'entità `ITMLedgerJournalCostLinesVoyagesEntity`. La tabella seguente elenca i campi e i mapping che compongono questa entità.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Importo allocato | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Numero | Numero |
| Numero riga transazione costo | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sì** | Numero |
| Numero riga giornale di registrazione | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sì** | Numero |
| Numero giornale di registrazione | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sì** | Numero |
| Viaggio | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sì** | Numero |

## <a name="vendor-shipping-container-cost-allocations-itmledgerjournalcostlinescontainersentity"></a>Allocazioni dei costi dei contenitori di spedizione del fornitore (ITMLedgerJournalCostLinesContainersEntity)

L'entità di dati allocazioni dei costi dei contenitori di spedizione del fornitore consente di allocare una riga di fattura fornitore su uno o più costi applicati all'area dei costi dei contenitori di spedizione. Questa funzionalità è supportata dall'entità `ITMLedgerJournalCostLinesContainersEntity`. La tabella seguente elenca i campi e i mapping che compongono questa entità.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Importo allocato | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Numero | Numero |
| Contenitore di spedizione | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sì** | Numero |
| Numero riga transazione costo | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sì** | Numero |
| Numero riga giornale di registrazione | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sì** | Numero |
| Numero giornale di registrazione | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sì** | Numero |
| Viaggio | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sì** | Numero |

## <a name="vendor-folio-cost-allocations-itmledgerjournalcostlinesfoliosentity"></a>Allocazioni dei costi di registrazione del fornitore (ITMLedgerJournalCostLinesFoliosEntity)

L'entità di dati allocazioni dei costi di registrazione del fornitore consente di allocare una riga di fattura fornitore su uno o più costi applicati all'area dei costi di registrazione. Questa funzionalità è supportata dall'entità `ITMLedgerJournalCostLinesFoliosEntity`. La tabella seguente elenca i campi e i mapping che compongono questa entità.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Importo allocato | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Numero | Numero |
| Numero riga transazione costo | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sì** | Numero |
| Registrazione | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sì** | Numero |
| Numero riga giornale di registrazione | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sì** | Numero |
| Numero giornale di registrazione | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sì** | Numero |

## <a name="vendor-purchase-order-cost-allocations-itmledgerjournalcostlinespurchtableentity"></a>Allocazioni dei costi degli ordini fornitore del fornitore (ITMLedgerJournalCostLinesPurchTableEntity)

L'entità di dati allocazioni dei costi dell'ordine fornitore del fornitore consente di allocare una riga di fattura fornitore su uno o più costi applicati all'area dei costi dell'ordine fornitore. Questa funzionalità è supportata dall'entità `ITMLedgerJournalCostLinesPurchTableEntity`. La tabella seguente elenca i campi e i mapping che compongono questa entità.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Importo allocato | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Numero | Numero |
| Numero riga transazione costo | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sì** | Numero |
| Numero riga giornale di registrazione | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sì** | Numero |
| Numero giornale di registrazione | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sì** | Numero |
| Ordine fornitore | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sì** | Numero |

## <a name="vendor-item-cost-allocations-itmledgerjournalcostlinespurchlineentity"></a>Allocazioni dei costi di articolo del fornitore (ITMLedgerJournalCostLinesPurchLineEntity)

L'entità di dati allocazioni dei costi di articolo del fornitore consente di allocare una riga di fattura fornitore su uno o più costi applicati all'area dei costi di articolo. L'area dei costi dell'articolo copre i costi nella riga dell'ordine fornitore. Questa funzionalità è supportata dall'entità `ITMLedgerJournalCostLinesPurchLineEntity`. La tabella seguente elenca i campi e i mapping che compongono questa entità.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Importo allocato | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Numero | Numero |
| Numero riga transazione costo | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sì** | Numero |
| Numero riga giornale di registrazione | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sì** | Numero |
| Numero giornale di registrazione | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sì** | Numero |
| Ordine fornitore | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sì** | Numero |
| Numero di riga ordine fornitore | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sì** | Numero |

## <a name="vendor-transfer-order-line-cost-allocations-itmledgerjournalcostlinestransferlineentity"></a>Allocazioni dei costi di riga ordine di trasferimento del fornitore (ITMLedgerJournalCostLinesTransferLineEntity)

L'entità di dati allocazioni dei costi di riga dell'ordine di trasferimento del fornitore consente di allocare una riga di fattura fornitore su uno o più costi applicati all'area dei costi di riga di trasferimento. Questa funzionalità è supportata dall'entità `ITMLedgerJournalCostLinesTransferLineEntity`. La tabella seguente elenca i campi e i mapping che compongono questa entità.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Importo allocato | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Numero | Numero |
| Numero riga transazione costo | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sì** | Numero |
| Numero riga giornale di registrazione | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sì** | Numero |
| Numero giornale di registrazione | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sì** | Numero |
| Ordine di trasferimento | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sì** | Numero |
| Numero di righe ordine di trasferimento | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sì** | Numero |

### <a name="reference-table"></a>Tabella riferimenti

Le righe dei costi di viaggio hanno un'associazione diretta con un record di transazione dei costi. Questo record include il valore **ID tabella di riferimento**. Questo valore è univoco per ciascuna area di costo (viaggio, contenitore di spedizione e così via). Quando si fa riferimento a numeri di tabella specifici per i dati creati utilizzando entità di dati, le entità vengono suddivise in base ai valori **ID tabella di riferimento**.

I valori per la tabella di riferimento (`RefTableId`) e il tipo di transazione (`TransType`) sono impliciti nella selezione dell'entità della riga di acquisto del costo d'acquisto o dell'entità della riga di trasferimento del costo d'acquisto.

## <a name="vendor-invoice-journal-lines-vendorinvoicejournallineentity"></a>Righe di giornale di registrazione fatture fornitore (VendorInvoiceJournalLineEntity)

Prima che un valore di riga del giornale di registrazione possa essere allocato a uno o più costi nel modulo **Costo di spedizione**, la riga del giornale di registrazione deve essere associata a un'area di costo. Per supportare questa funzionalità, il modulo **Costo di spedizione** aggiunge alcuni nuovi campi alla tabella delle righe del giornale di registrazione (`LedgerJournalTrans`).

### <a name="fields-added-to-the-vendor-invoice-journal-line-entity"></a>Campi aggiunti all'entità riga giornale di registrazione fatture fornitore

La tabella seguente elenca i campi che il modulo **Costo di spedizione** aggiunge all'entità riga di registrazione fatture fornitore (`VendorInvoiceJournalLineEntity`). Questi campi consentono al sistema di creare righe di giornale di registrazione e allocarvi i costi.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Area costi | LedgerJournalTrans.ITMCostArea | Int | Numero | Numero |
| Codice tipo di costo | LedgerJournalTrans.ITMCostTypeId | Nvarchar(20) | Numero | Numero |

### <a name="mainoffset-account"></a>Conto principale/contropartita

Il conto principale/contropartita per una riga di giornale di registrazione fatture associata a un viaggio a costi di spedizione è determinato dal codice del tipo di costo. Quando il codice del tipo di costo è incluso nella riga giornale di registrazione fatture, il conto di compensazione per il codice verrà utilizzato come conto principale o conto di contropartita, a seconda dello scenario:

- **Giornale di registrazione a riga singola** – Se viene definito un conto principale (in altre parole, il conto fornitore) e viene fornito un codice del tipo di costo, il valore del conto di compensazione per il codice del tipo di costo verrà inserito nel conto di contropartita.
- **Giornale di registrazione a più righe** – Se un conto principale non è definito, ma viene fornito un codice del tipo di costo, il valore del conto di compensazione per il codice del tipo di costo verrà inserito nel conto principale. La riga del giornale di registrazione che sta accreditando il fornitore non farà riferimento a un codice del tipo di costo.

## <a name="sequencing"></a>Sequenziamento

A causa delle dipendenze tra le tabelle giornale di registrazione e righe del giornale di registrazione, è necessario creare prima il record di viaggio. Le righe di viaggio possono essere create solo dopo aver creato il viaggio, il contenitore di spedizione e le registrazioni.

Per allocare una fattura di viaggio, il sistema deve elaborare le entità nel seguente ordine:

1. Intestazione giornale di registrazione fatture (`VendInvoiceJournalHeaderEntity`)
1. Riga giornale di registrazione fatture (`VendInvoiceJournalLineEntity`)
1. Allocazioni costi di spedizione (`ITMLedgerJournalEntities`)
