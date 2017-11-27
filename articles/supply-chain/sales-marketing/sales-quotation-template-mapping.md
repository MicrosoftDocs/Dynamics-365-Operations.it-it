---
title: Sincronizzare le intestazioni e le righe di offerte di vendita da Sales in Finance and Operations
description: "L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle offerte di vendita da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
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
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c8cfc484eed02423dbf0c7caaf8ac2337b6ac38d
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a>Sincronizzare le intestazioni e le righe di offerte di vendita da Sales in Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Prima di utilizzare la soluzione Prospect to cash, acquisisci familiarità con [Integrazione dei dati di Microsoft Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration). 

L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle offerte di vendita da Microsoft Dynamics 365 for Sales (Sales) in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations). 

## <a name="template-and-tasks"></a>Modello e attività

I seguenti modelli e le attività sottostanti vengono utilizzati per sincronizzare le intestazioni e le righe delle offerte di vendita da Sales in Finance and Operations:

- **Nome del modello:** Offerte di vendita (da Sales in Fin and Ops)
- **Nomi delle attività del progetto:**

    - QuoteHeader
    - QuoteLine

Le attività di sincronizzazione seguenti sono necessarie prima di eseguire la sincronizzazione delle intestazioni e delle righe di un'offerta di vendita:

- Prodotti (da Fin and Ops in Sales)
- Conti (da Sales in Fin and Ops) (se utilizzata)
- Da Contatti a Clienti (da Sales in Fin and Ops) (se utilizzata)

## <a name="entity-set"></a>Insieme di entità

| Vendite        | CDS           | Finance and Operations    |
|--------------|---------------|---------------------------|
| Citazioni       | Offerta     | Intestazioni offerta di vendita   |
| QuoteDetails | QuotationLine | Righe di offerta di vendita CDS |

## <a name="entity-flow"></a>Flusso di entità

Le offerte di vendita vengono create in Sales e sincronizzate in Finance and Operations.

Le offerte di vendita da Sales vengono sincronizzate solo se vengono soddisfatte le condizioni seguenti:

- Tutti i prodotti nelle righe dell'offerta di vendita sono gestiti esternamente.
- L'offerta di vendita è attiva o attivata.

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

È stato aggiunto il campo **Solo prodotti gestiti esternamente** all'entità Offerta per rilevare in modo coerente se l'offerta di vendita consiste interamente di prodotti gestiti esternamente. Se un'offerta di vendita include solo prodotti gestiti esternamente, i prodotti vengono gestiti in Finance and Operations. Questo comportamento offre la garanzia di non provare a sincronizzare righe di offerta di vendita con prodotti che sono sconosciuti in Finance and Operations.

Tutti i prodotti e le righe nell'offerta vengono aggiornati con le informazioni **Solo prodotti gestiti esternamente** derivate dall'intestazione dell'offerta. Queste informazioni sono disponibili nel campo **La quota ha solo prodotti gestiti esternamente** nell'entità riga dell'offerta.

I campi relativi a **Sconto**, **Spese** e **Imposta** sono controllati da un'impostazione complessa in Finance and Operations. Questa impostazione al momento non supporta il mapping di integrazione. Nella progettazione attuale, i campi relativi a **Prezzo**, **Sconto**, **Spese** e **Imposta** sono dei master e sono gestiti da Finance and Operations.

In Sales, la soluzione rende i campi seguenti di sola lettura, perché i valori non vengono sincronizzati con Finance and Operations:

- **Campi di sola lettura nell'intestazione dell'offerta di vendita:** % sconto, Sconto, Importo trasporto
- **Campi di sola lettura nelle righe dell'offerta di vendita:** Imposta

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

Prima di sincronizzare gli ordini cliente, è importante aggiornare i sistemi con la seguente impostazione:

### <a name="setup-in-sales"></a>Impostazione in Sales

- Passare a **Impostazioni** &gt; **Amministrazione** &gt; **Impostazioni di sistema** &gt; **Vendite** e verificare che il campo **Metodo di calcolo sconto** sia impostato su **Per unità**. Questa impostazione assicura che lo sconto della voce da Sales corrisponda all'impostazione in Finance and Operations. In caso contrario, lo sconto non risulterà corretto in Finance and Operations, poiché Finance and Operations lo leggerà come sconto unitario anche se in Sales è uno sconto per riga di vendita.

### <a name="setup-in-finance-and-operations"></a>Impostazione in Finance and Operations

- Passare a **Contabilità clienti** &gt; **Impostazioni** &gt; **Parametri contabilità clienti**. Nella scheda **Sequenza numerica** selezionare la sequenza per le offerte di vendita e quindi fare clic su **Visualizza dettagli**. In **Impostazione generale** impostare il campo **Manuale** su **Sì**.
- Passare a **Contabilità clienti** &gt; **Impostazioni** &gt; **Parametri contabilità clienti**. Nella scheda **Spedizioni** impostare il campo **Controllo data di consegna** su **Nessuno**. Questa impostazione aiuta a evitare errori di sincronizzazione per le offerte di vendita.

### <a name="setup-in-the-data-integration-project"></a>Impostazione nel progetto di Integrazione dati

#### <a name="quoteheader"></a>QuoteHeader

- Il campo **Data di consegna richiesta** è obbligatorio in Finance and Operations e la sincronizzazione avrà esito negativo se il campo è lasciato vuoto. Per evitare questo problema, se il campo è vuoto, viene automaticamente compilato con una data predefinita derivante da **Origine &gt; CDS**. È consigliabile aggiornare il campo con una data preferita. Al momento non è possibile immettere un valore come **Oggi** per rappresentare la data corrente. È necessario immettere una data specifica. Il valore del modello predefinito per **Data di consegna richiesta** è **1/1/2020**.
- Il campo **Indirizzo Codice paese** è obbligatorio in Finance and Operations. Per evitare errori durante la sincronizzazione, è possibile specificare un valore predefinito che viene utilizzato se il campo viene lasciato vuoto in Sales. Il valore predefinito è anche utile, in quanto non è necessario immettere manualmente un valore nel campo **Paese** per gli indirizzi locali. Non è disponibile alcun valore di modello predefinito per **DeliveryAddressCountryRegionISOCode**.
- Aggiornare il mapping per il campo relativo all'**ID organizzazione CDS** in **Origine &gt; CDS** in modo che corrisponda all'**organizzazione CDS** nell'entità Organizzazione:

    - Il valore del modello predefinito per **Organization_OrganizationId** è **ORG001**.
    - Il valore del modello predefinito per **Account_Organization_OrganizationId** è **ORG001**.
    - Il valore del modello predefinito per **InvoiceAccount_OrganizationId** è **ORG001**.

#### <a name="quoteline"></a>QuoteLine

- Aggiornare il mapping per il campo relativo all'**ID organizzazione CDS** in **Origine &gt; CDS** in modo che corrisponda all'**organizzazione CDS** nell'entità Organizzazione:

    - Il valore del modello predefinito per **Organization_OrganizationId** è **ORG001**.
    - Il valore del modello predefinito per **Product_Organization_Organization_OrganizationId** è **ORG001**.
    - Il valore del modello predefinito per **Quotation_Organization_Organization_OrganizationId** è **ORG001**.

- Il campo **Data di consegna richiesta** è obbligatorio in Finance and Operations e la sincronizzazione avrà esito negativo se il campo è lasciato vuoto. Per evitare questo problema, se il campo è vuoto, viene automaticamente compilato con una data predefinita derivante da **Origine &gt; CDS**. È consigliabile aggiornare il campo con una data preferita. Al momento non è possibile immettere un valore come **Oggi** per rappresentare la data corrente. È necessario immettere una data specifica. Il valore del modello predefinito per **Data di consegna richiesta** è **1/1/2020**.
- È possibile aggiungere i mapping seguenti da **CDS &gt; Destinazione** in modo da garantire che le righe di offerta vengano importate in Finance and Operations se non sono disponibili informazioni predefinite dal cliente o dal prodotto:

    - **SiteId** - Un sito è obbligatorio per la generazione di offerte e righe di ordine cliente in Finance and Operations. Non è disponibile alcun valore del modello predefinito per **SiteId**.
    - **WarehouseId** - Un magazzino è obbligatorio per l'elaborazione di offerte e righe di ordine cliente in Finance and Operations. Non è disponibile alcun valore del modello predefinito per **WarehouseId**.

- Assicurarsi che la mappa dei valori richiesti per le unità di misura (UdM) di vendita in Finance and Operations sia presente nel mapping **CDS &gt; Destinazione** per **Quantity_UOM** su **SALESUNITSYMBOL**.

## <a name="template-mapping-in-data-integrator"></a>Mapping dei modelli nell'integratore di dati

> [!NOTE]
> - I campi relativi a **Sconto**, **Spese** e **Imposta** sono controllati da un'impostazione complessa in Finance and Operations. Questa impostazione al momento non supporta il mapping di integrazione. Nella progettazione attuale, i campi relativi a **Prezzo**, **Sconto**, **Spese** e **Imposta** sono gestiti da Finance and Operations.
> - I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non sono inclusi nei mapping predefiniti. Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.

Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.

### <a name="quoteheader"></a>QuoteHeader

![Mapping dei modelli nell'integratore di dati](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Mapping dei modelli nell'integratore di dati](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a>QuoteLine

![Mapping dei modelli nell'integratore di dati](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Mapping dei modelli nell'integratore di dati](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Argomenti correlati

[Sincronizzare i prodotti da Finance and Operations ai prodotti in Sales](products-template-mapping.md)

[Sincronizzare conti da Sales con clienti in Finance and Operations](accounts-template-mapping.md)

[Sincronizzare i contatti da Sales ai contatti o ai clienti in Finance and Operations](contacts-template-mapping.md)



