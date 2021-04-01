---
title: Sincronizzare intestazioni e righe di fatture di vendita direttamente da Supply Chain Management in Sales
description: L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle fatture di vendita direttamente da Dynamics 365 Supply Chain Management a Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: e12b2ca0fd5df3b2acf6b84d7ff51967e1acc93e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231770"
---
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Sincronizzare intestazioni e righe di fatture di vendita direttamente da Finance and Operations in Sales

[!include [banner](../includes/banner.md)]

L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle fatture di vendita direttamente da Dynamics 365 Supply Chain Management a Dynamics 365 Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Flusso di dati in Prospect to cash

La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Supply Chain Management e Sales. I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Supply Chain Management e Sales. La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Supply Chain Management e Sales.

[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelli e attività

Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di Power Apps](https://preview.admin.powerapps.com/dataintegration). Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.

Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare le intestazioni e le righe delle fatture di vendita da Supply Chain Management in Sales:

- **Nome del modello in Integrazione dati:** Fatture di vendita (da Fin and Ops in Sales) - Diretto
- **Nomi delle attività nel progetto di Integrazione dati:**

    - SalesInvoiceHeader
    - SalesInvoiceLine

Le attività di sincronizzazione seguenti sono necessarie prima di eseguire la sincronizzazione delle intestazioni e delle righe di fatture di vendita:

- Prodotti (da Supply Chain Management in Sales) - Diretto
- Conti (da Sales in Supply Chain Management) - Diretto (se utilizzato)
- Contatti (da Sales in Supply Chain Management) - Diretto (se utilizzato)
- Intestazione e righe ordine cliente (da Supply Chain Management a Sales) - Diretto

## <a name="entity-set"></a>Insieme di entità

| Gestione della supply chain                              | Vendite          |
|------------------------------------------------------|----------------|
| Intestazioni fatture di vendita cliente gestite esternamente | Fatture       |
| Righe fatture di vendita cliente gestite esternamente   | InvoiceDetails |

## <a name="entity-flow"></a>Flusso di entità

Le fatture di vendita vengono create in Supply Chain Management e sincronizzate in Sales.

> [!NOTE]
> L'imposta relativa alle spese nell'intestazione della fattura di vendita non è attualmente inclusa nella sincronizzazione da Supply Chain Management in Sales. Sales non supporta le informazioni fiscali a livello di intestazione. Tuttavia, l'imposta relativa alle spese a livello di riga è inclusa nella sincronizzazione.

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

- Un campo **Numero fattura** è stato aggiunto all'entità **Fattura** ed è visualizzato nella pagina.
- Il pulsante **Crea fattura** nella pagina **Ordine cliente** è nascosto perché le fatture verranno create in Supply Chain Management e sincronizzate in Sales. La pagina **Fattura** non è modificabile poiché le fatture verranno sincronizzate da Supply Chain Management.
- Il valore **Stato dell'ordine cliente** diventa automaticamente **Fatturato** dopo la sincronizzazione della fattura correlata da Supply Chain Management in Sales. Inoltre, il proprietario dell'ordine cliente da cui la fattura è stata creata viene assegnato come proprietario della fattura. Di conseguenza, il proprietario dell'ordine cliente può visualizzare la fattura.

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

Prima di sincronizzare le fatture di vendita, è importante aggiornare le seguenti impostazioni nei sistemi:

### <a name="setup-in-sales"></a>Impostazione in Sales

Andare a **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite** e assicurarsi che:

- L'opzione **Usa sistema di calcolo prezzi sistema** sia impostata su **Sì**.
- Il campo **Metodo di calcolo sconto** sia impostato su **Voce**.

### <a name="setup-in-the-data-integration-project"></a>Impostazione nel progetto di Integrazione dati

#### <a name="salesinvoiceheader-task"></a>Attività SalesInvoiceHeader

- Assicurarsi che il mapping richiesto esista per **InvoiceCountryRegionId** a **BillingAddress\_Country**.

    Il valore di modello è una mappa di valori dove vari paesi sono mappati.

- Un listino prezzi è necessario per creare fatture in Sales. Aggiornare la mappa di valori per **pricelevelid.name \[nome listino prezzi\]** al listino prezzi utilizzato in Sales per la valuta. È possibile utilizzare il listino prezzi predefinito per una singola valuta. In alternativa, se si hanno listini prezzi in più valute, è possibile utilizzare una mappa di valori.

    Il valore di modello per **pricelevelid.name \[nome listino prezzi\]** è una mappa di valori basata sulla valuta con USD = Servizio CRM USA (esempio).  
    
#### <a name="salesinvoiceline-task"></a>Attività SalesInvoiceLine

- Assicurarsi che il mapping necessario esista per **Unità di misura**.
- Assicurarsi che la mappa valori richiesta esista per **SalesUnitSymbol** in Supply Chain Management.

    Un valore di modello con una mappa di valori viene definito per **SalesUnitSymbol** a **Quantity\_UOM**.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

> [!NOTE]
> I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non vengono inclusi nei mapping predefiniti. Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.

Nelle figure seguenti viene illustrato un esempio di mapping di modelli in Integrazione dati. 

> [!NOTE]
> Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Supply Chain Management.

### <a name="salesinvoiceheader"></a>SalesInvoiceHeader

![Mapping dei modelli in Integrazione dati](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a>SalesInvoiceLine

![Mapping dei modelli in Integrazione dati](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Argomenti correlati

[Prospect per uno scenario di liquidazione](prospect-to-cash.md)

[Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management](accounts-template-mapping-direct.md)

[Sincronizzare prodotti direttamente da Supply Chain Management con prodotti in Sales](products-template-mapping-direct.md)

[Sincronizzare contatti direttamente da Sales con contatti o clienti in Supply Chain Management](contacts-template-mapping-direct.md)

[Sincronizzazione degli ordini cliente direttamente tra Sales e Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]