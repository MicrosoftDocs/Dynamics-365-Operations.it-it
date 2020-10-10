---
title: Risolvere problemi relativi a entrate prodotti e fatturazione
description: Questo argomento descrive come risolvere i problemi che potrebbero verificarsi mentre lavori con entrate prodotti e fatturazione.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: d86fa3df1de13cc0e0fb94449207a326069da25b
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834382"
---
# <a name="troubleshoot-product-receipts-and-invoicing"></a>Risolvere problemi relativi a entrate prodotti e fatturazione

Questo argomento descrive come risolvere i problemi che potrebbero verificarsi mentre lavori con entrate prodotti e fatturazione.

## <a name="i-cant-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>Non riesco a registrare più di una fattura per una riga di ordine fornitore con articoli basati sulla categoria.

Una quantità è obbligatoria se si desidera registrare le fatture. Pertanto, se l'intera quantità di una riga è stata fatturata solo per un importo parziale, non sarà possibile fatturare l'importo rimanente su un'altra fattura.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>Ricevo un errore "Riferimento oggetto non impostato" durante la conferma dell'ordine fornitore o un'eccezione "È stata generata un'eccezione dalla destinazione di una chiamata" durante la registrazione della fattura fornitore.

Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.

Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza*, vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**. Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="i-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a>Non riesco a consolidare più entrate prodotto in un unico ordine fornitore.

Non è possibile consolidare più entrate prodotti in un unico ordine fornitore se le diverse righe di entrata prodotti hanno date contabili diverse.

Nelle versioni precedenti di Microsoft Dynamics 365 Supply Chain Management, il consolidamento era consentito in questa situazione. Tuttavia, la procedura è soggetta a errori. La data contabile nelle righe ordine fornitore create non deve essere diversa dalla data contabile nelle righe entrata prodotti da cui sono state create tali righe ordine fornitore. (La data contabile nelle righe dell'ordine fornitore corrisponde alla data contabile nell'intestazione dell'ordine fornitore). Pertanto, il consolidamento di più entrate prodotti in un unico ordine fornitore non è più consentito.

La data contabile viene utilizzata, ad esempio, per le prenotazioni di budget e gli impegni di spesa. Pertanto, deve essere conservata durante il passaggio dall'entrata del prodotto all'ordine fornitore.

## <a name="when-product-receipts-are-canceled-transactions-can-be-posted-to-a-suspended-ledger-account"></a>Quando le entrate prodotti vengono annullate, le transazioni possono essere registrate in un conto CoGe sospeso.

### <a name="issue-description"></a>Descrizione del problema

Se un'entrata prodotti viene annullata, il sistema consente la registrazione delle transazioni nei conti CoGe sospesi, anche se i conti principali sono sospesi.

### <a name="reproduce-the-issue"></a>Riprodurre il problema

La seguente procedura mostra un modo per riprodurre il problema.

1. Nella pagina **Parametri contabilità fornitori**, nella scheda **Generale**, assicurati che l'opzione **Registra entrata prodotti nella contabilità generale** sia impostata su *Sì*.
1. Crea un ordine fornitore e aggiungi una riga ordine con una quantità di *1.000* per un prodotto.
1. Conferma l'ordine fornitore.
1. Registra l'entrata del prodotto e controlla i giustificativi.
1. Sospendi i relativi conti principali, *200140* e *140200*.
1. Annulla l'entrata del prodotto registrata.
1. Si noti che le transazioni possono essere registrate nei conti CoGe sospesi.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Le transazioni possono essere registrate nei conti CoGe sospesi quando le entrate prodotti vengono annullate, poiché questo comportamento consente registrazioni corrette.

## <a name="a-product-receipt-voucher-number-is-consumed-even-if-no-financial-voucher-is-generated-during-product-receipt"></a>Un numero di giustificativo di entrata prodotti viene utilizzato anche se non viene generato alcun giustificativo finanziario durante l'entrata prodotti.

Se l'opzione **Passività ratei all'entrata prodotti** è impostata su *No* per il gruppo di modelli di articoli, non verranno effettuate registrazioni nella contabilità generale. Tuttavia, un evento fisico verrà registrato ai fini della contabilità in un giornale di registrazione secondario e tale evento richiede un numero di giustificativo. Questo numero di giustificativo è il numero di giustificativo a cui si fa riferimento nelle transazioni di magazzino.

Ti consigliamo di impostare l'opzione **Passività ratei all'entrata prodotti** su *Sì*, come descritto nel seguente post del blog: [Registrare le spese varie al momento dell'entrata del prodotto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).

## <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a>L'impostazione Registra nel conto di addebito nella contabilità generale non è attivata.

### <a name="issue-description"></a>Descrizione del problema

Questo problema si verifica quando viene fatturato un ordine fornitore, se l'opzione **Registra nel conto di addebito nella contabilità generale** è impostata su *Sì* nella scheda **Fattura** della pagina **Parametri contabilità fornitori**.

### <a name="reproduce-the-issue"></a>Riprodurre il problema

La seguente procedura mostra un modo per riprodurre il problema.

1. Passare a **Contabilità fornitori \> Impostazioni \> Parametri contabilità fornitori**.
1. Nella scheda **Fattura**, imposta l'opzione **Registra nel conto di addebito nella contabilità generale** su *Sì*.
1. Vai a **Gestione scorte \> Impostazione \> Registrazione \> Registrazione**.
1. Nella scheda **Ordine fornitore**, assicurati di aver eliminato tutte le righe nella spesa di acquisto del prodotto.
1. Vai a **Contabilità fornitori \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Creare un ordine fornitore. Nel campo **Conto fornitore**, seleziona *1001 Acme Office Supplies*.
1. Aggiungi una riga ordine fornitore con le seguenti impostazioni:

    - **Numero articolo:** *D0011 Laser Projector*
    - **Sito:** *1*
    - **Magazzino:** *11*
    - **Quantità:** *4*

1. Nel riquadro azioni, nella scheda **Acquisto**, nel gruppo **Azione**, seleziona **Conferma**.
1. Nel riquadro azioni, nella scheda **Ricevi**, nel gruppo **Genera**, seleziona **Entrata prodotto**.
1. Nella finestra di dialogo **Registrazione entrata prodotti**, nel campo **Entrata prodotti**, immetti un numero arbitrario, quindi seleziona **OK**.
1. Nel riquadro azioni, nel gruppo **Genera** della scheda **Fattura**, seleziona **Fattura**.
1. Nel campo **Numero**, immetti un numero arbitrario come numero di fattura.
1. Aggiorna lo stato di abbinamento e registra.
1. Si noti che ora viene visualizzato il seguente errore quando si genera una fattura da un ordine fornitore: "Numero di conto per il tipo di transazione spesa di acquisto per il prodotto inesistente".

### <a name="issue-resolution"></a>Risoluzione dei problemi

Ciò dipende dalle impostazioni dei parametri per le fatture e i gruppi di fatture. Per ulteriori informazioni, vedi il seguente post del blog: [Contabilizzazione per spese di acquisto e variazione delle scorte](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).
