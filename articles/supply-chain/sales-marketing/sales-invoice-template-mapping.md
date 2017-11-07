---
title: Sincronizzare intestazioni e righe di fatture di vendita da Finance and Operations in Sales
description: "L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle fatture di vendita da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: fb5ba099911deda5308daf92d82cd6b3489995bf
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-from-finance-and-operations-to-sales"></a>Sincronizzare intestazioni e righe di fatture di vendita da Finance and Operations in Sales

[!include[banner](../includes/banner.md)]

L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle fatture di vendita da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales. 

## <a name="templates-and-tasks"></a>Modelli e attività

I seguenti modelli e attività sottostanti vengono utilizzati per sincronizzare le intestazioni e le righe delle fatture di vendita da Finance and Operations in Sales:

- **Nome del modello in Integrazione dati** 

     - Fatture di vendita (da Fin and Ops in Sales)

- **Nomi delle attività nel progetto di Integrazione dati**

    - SalesInvoiceHeader
    - SalesInvoiceLine

Le attività di sincronizzazione necessarie prima di sincronizzare righe e intestazione della fattura di vendita:
-   Prodotti (da Fin and Ops in Sales)
-   Conti (da Sales in Fin and Ops) (se utilizzata)
-   Contatti (da Sales in Fin and Ops) (se utilizzata)
-   Intestazione e righe dell'ordine cliente (da Fin and Ops in Sales)

## <a name="entity-set"></a>Insieme di entità

| Finance and Operations                               | Common Data Service (CDS)              | Vendite          |
|------------------------------------------------------|------------------|----------------|
| Intestazioni fatture di vendita cliente gestite esternamente | SalesInvoice     | Fatture       |
| Righe fatture di vendita cliente gestite esternamente   | SalesInvoiceLine | InvoiceDetails |

## <a name="entity-flow"></a>Flusso di entità

Le fatture di vendita vengono create in Finance and Operations e sincronizzate in Sales.

> [!NOTE]
> L'imposta relativa alle spese nell'**intestazione della fattura di vendita** non è attualmente inclusa nella sincronizzazione da Finance and Operations in Sales. Questo perché Sales non supporta le informazioni fiscali a livello di intestazione. È inclusa l'imposta relativa alle spese a livello di riga.

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

-  Un **campo per il numero di fattura** viene aggiunto all'entità **Fattura** e visualizzato nella pagina.
 
-  Il pulsante **Crea fattura** nella pagina **Ordine cliente** è nascosto perché le fatture verranno create in Finance and Operations e sincronizzate in Sales. La pagina **Fattura** non è modificabile poiché le fatture verranno sincronizzate da Finance and Operations.
 
-  Lo **stato dell'ordine cliente** diventa automaticamente **Fatturato** dopo la sincronizzazione della fattura correlata da Finance and Operations in Sales. Inoltre, il proprietario dell'ordine cliente da cui la fattura è stata creata viene assegnato come proprietario della fattura. Il proprietario dell'ordine cliente ha quindi la possibilità di visualizzare la fattura.
 
## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

Prima di sincronizzare le fatture di vendita, è importante aggiornare i sistemi con la seguente impostazione:

### <a name="setup-in-sales"></a>Impostazione in Sales

- In **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite**, verificare che **Usa sistema di calcolo prezzi sistema** sia impostato su **Sì**. 

- In **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite**, verificare che **Metodo di calcolo sconto** sia impostato su **Voce**. 

### <a name="setup-in-the-data-integration-project"></a>Impostazione nel progetto di Integrazione dati

#### <a name="salesinvoiceheader-task"></a>Attività SalesInvoiceHeader

- Aggiornare il mapping per **ID organizzazione CDS** in **Origine** > **CDS**. 

    -  Il valore del modello predefinito per **SalesOrder_Organization_OrganizationId** è ORG001.
    -  Il valore del modello predefinito per **Account_Organization_OrganizationId** è ORG001.
    -  Il valore del modello predefinito per **Organization_OrganizationId** è ORG001.

- Verificare che il mapping necessario esista in **Origine** > **CDS per InvoiceCountryRegionId** a **BillingAddress_Country**.

    -  Il valore del modello è **ValueMap** con un numero di paesi mappati.

- Il **listino prezzi** è necessario per creare fatture in Sales. Aggiornare **ValueMap** in **CDS** > **Destinazione per pricelevelid.name [nome listino prezzi]** al **listino prezzi** utilizzato in Sales per la valuta. È possibile utilizzare il **listino prezzi** predefinito per una singola valuta oppure **ValueMap** se si hanno **listini prezzi** in molteplici valute.

    -  Il valore del modello per **pricelevelid.name [nome listino prezzi]** è **ValueMap** basato su **Valuta**.
    -  usd: Servizio CRM USA (esempio). 

#### <a name="salesinvoiceline-task"></a>Attività SalesInvoiceLine

- Verificare che il mapping necessario esista in **Origine** > **CDS per unità di misura**.

- Assicurarsi che **ValueMap** per **SalesUnitSymbol** in Finance and Operations sia presente in **Origine** > **Mapping CDS**. 
    
    - Il valore del modello con **ValueMap** è definito per **SalesUnitSymbol a Quantity_UOM**.
    
-  Aggiornare il mapping per **ID organizzazione CDS in Origine** > **CDS**. 

    -  Il valore del modello predefinito per **SalesInvoicer_Organization_OrganizationId** è ORG001.
    -  Il valore del modello predefinito per **Product_Organization_OrganizationId** è ORG001.
 
## <a name="template-mapping-in-data-integrator"></a>Mapping dei modelli nell'integratore di dati

> [!NOTE]
> I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non sono inclusi nei mapping predefiniti. Il mapping di questi campi richiede l'impostazione di un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.

Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.

![Mapping dei modelli nell'integratore di dati](./media/sales-invoice-template-mapping-data-integrator-1.png)

![Mapping dei modelli nell'integratore di dati](./media/sales-invoice-template-mapping-data-integrator-2.png)

![Mapping dei modelli nell'integratore di dati](./media/sales-invoice-template-mapping-data-integrator-3.png)

![Mapping dei modelli nell'integratore di dati](./media/sales-invoice-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Argomenti correlati

[Sincronizzare i prodotti da Finance and Operations ai prodotti in Sales](products-template-mapping.md)

[Sincronizzare conti da Sales con clienti in Finance and Operations](accounts-template-mapping.md)

[Sincronizzare contatti da Sales con contatti o clienti in Finance and Operations](contacts-template-mapping.md)

[Sincronizzare intestazioni e righe di offerte di vendita da Sales in Finance and Operations](sales-quotation-template-mapping.md)

[Sincronizzare intestazioni e righe di ordini di vendita da Finance and Operations in Sales](sales-order-template-mapping.md)


