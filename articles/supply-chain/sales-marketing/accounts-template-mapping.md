---
title: Sincronizzare i conti da Sales ai clienti in Finance and Operations
description: "L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i conti da Microsoft Dynamics 365 for Sales a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
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
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: f322c5b273c29d863c059092bf1a41c424c19a7d
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-accounts-from-sales-to-customers-in-finance-and-operations"></a>Sincronizzare i conti da Sales ai clienti in Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Prima di utilizzare la soluzione Prospect to cash, acquisisci familiarità con [Integrazione dei dati di Microsoft Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration). 

L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i conti da Microsoft Dynamics 365 for Sales (Sales) a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (Finance and Operations).

## <a name="template-and-task"></a>Modello e attività

I modelli e le attività sottostanti che seguono vengono utilizzati per sincronizzare i conti da Sales a Finance and Operations:

- **Nome del modello:** account (da Sales a Fin and Ops)
- **Nome dell'attività del progetto:** - Conti - Conto - Clienti

Attività di sincronizzazione richieste prima di sincronizzare Conto/Cliente: nessuna

## <a name="entity-set"></a>Insieme di entità

| Vendite    | CDS     | Finance and Operations |
|----------|---------|------------------------|
| Conti | Conto | Clienti              |

## <a name="entity-flow"></a>Flusso di entità

I conti vengono gestiti in Sales e sincronizzati in Finance and Operations come clienti. La proprietà **Gestito esternamente** per tali clienti è impostata su **Sì** per tenere traccia dei clienti che hanno origine da Sales. Durante la fatturazione queste informazioni vengono utilizzate per filtrare le fatture che vengono sincronizzate in Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

Il campo **Numero di conto** è disponibile nella pagina **Conto**. È stata creata una chiave naturale e univoca per supportare l'integrazione. Questa funzionalità di chiave naturale della soluzione Customer Relationship Management (CRM) potrebbe influire sui clienti che utilizzano già il campo **Numero di conto**, ma che non utilizzano i valori univoci **Numero di conto** per conto. Attualmente la soluzione di integrazione non supporta questo caso.

Quando un nuovo conto viene creato, se un valore **Numero di conto** non è già presente, viene generato automaticamente utilizzando una sequenza numerica. Il valore consiste di **ACC**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri. Ecco un esempio: **ACC-01000-BVRCPS**

Quando viene applicata la soluzione di integrazione per Sales, uno script di aggiornamento imposta il campo **Numero di conto** per i conti esistenti in Sales. Se non sono presenti i valori **Numero di conto**, la sequenza numerica che è stata descritta in precedenza viene utilizzata.

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

- Il mapping **CustomerGroupId** da **CDS &gt; Destinazione** deve essere aggiornato con un valore valido in Finance and Operations. È possibile specificare un valore predefinito oppure è possibile impostare il valore utilizzando una mappa di valori. Il valore del modello predefinito è **10**.
- **Codice paese-regione indirizzo** è obbligatorio in Finance and Operations. Per evitare errori di sincronizzazione, è possibile specificare un valore predefinito nel mapping da **CDS &gt; Destinazione**. Tale valore predefinito viene quindi utilizzato se il campo viene lasciato vuoto in Sales.

    - Il valore del modello predefinito per **AddressCountryRegionISOCode** è **Stati Uniti.**
    - Il valore del modello predefinito per **DeliveryAddressCountryRegionISOCode** è **Stati Uniti.**

- Aggiungendo i seguenti mapping da **CDS &gt; Destinazione**, è possibile consentire una riduzione del numero degli aggiornamenti manuali necessari in Finance and Operations. È possibile utilizzare un valore predefinito o una mappa di valori da, ad esempio, **Paese** o **Città**.

    - **SiteId** - Un sito è obbligatorio per la generazione di offerte e righe di ordine cliente in Finance and Operations. Un sito predefinito può essere preso sia dal prodotto che dall'intestazione ordine del cliente. Il valore del modello predefinito per **SiteId** è **1**.
    - **WarehouseId** - Un magazzino è obbligatorio per l'elaborazione di offerte e righe di ordine cliente in Finance and Operations. Un sito predefinito può essere preso sia dal prodotto che dall'intestazione ordine del cliente in Finance and Operations. Il valore del modello predefinito per **WarehouseId** è **13**.
    - **LanguageId** - Una lingua è obbligatoria per la generazione di offerte e ordini cliente in Finance and Operations. Per impostazione predefinita, viene utilizzata la lingua dell'intestazione ordine del cliente. Il valore del modello predefinito per **LanguageId** è **en-us**.

- Aggiornare l'ID dell'organizzazione CDS (**Organization_OrganizationId**) nel mapping **Origine &gt; CDS**. Il valore del modello predefinito è **ORG001**.

## <a name="template-mapping-in-data-integrator"></a>Mapping dei modelli nell'integratore di dati

> [!NOTE]
> I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non vengono inclusi nei mapping predefiniti. Per mappare questi campi, è necessario impostare un mapping di valori. I mapping di valori sono specifici dei dati delle organizzazioni tra le quali avviene la sincronizzazione dell'entità.

Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.

![Mapping dei modelli nell'integratore di dati](./media/accounts-template-mapping-data-integrator-1.png)

![Mapping dei modelli per i conti nell'integratore di dati](./media/accounts-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Argomenti correlati

[Sincronizzare i prodotti da Finance and Operations ai prodotti in Sales](products-template-mapping.md)

[Sincronizzare i contatti da Sales ai contatti o ai clienti in Finance and Operations](contacts-template-mapping.md)

[Sincronizzare intestazioni e righe di offerte di vendita da Sales in Finance and Operations](sales-quotation-template-mapping.md)

[Sincronizzare intestazioni e righe di ordini di vendita da Finance and Operations in Sales](sales-order-template-mapping.md)

[Sincronizzare intestazioni e righe di fatture di vendita da Finance and Operations in Sales](sales-invoice-template-mapping.md)




