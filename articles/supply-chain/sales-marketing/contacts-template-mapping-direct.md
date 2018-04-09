---
title: Sincronizzare contatti direttamente da Sales con contatti o clienti in Finance and Operations
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le entità Contatto (Contatti) e Contatto (Clienti) direttamente da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 021a43c78cec83b23aff5dcc40db1a4be81aefc3
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a>Sincronizzare contatti direttamente da Sales con contatti o clienti in Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrazione dati di Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le entità Contatto (Contatti) e Contatto (Clienti) direttamente da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations.

## <a name="data-flow-in-prospect-to-cash"></a>Flusso di dati in Prospect to cash

La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Finance and Operations e Sales. I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Finance and Operations e Sales. La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Finance and Operations e Sales.

[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelli e attività

Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di PowerApps](https://preview.admin.powerapps.com/dataintegration). Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.

I seguenti modelli e attività sottostanti vengono utilizzati per sincronizzare entità Contatto (Contatti) in Sales a entità Contatto (Clienti) in Finance and Operations:

- **Nomi dei modelli in Integrazione dati:**

    - Contatti (da Sales in Fin and Ops) - Diretto
    - Da Contatti a Cliente (da Sales in Fin and Ops) - Diretto

- **Nomi delle attività nel progetto di Integrazione dati:**

    - Contatti
    - ContactToCustomer

La seguente attività di sincronizzazione è necessaria prima della sincronizzazione dei contatti: Conti (da Sales in Fin and Ops)

## <a name="entity-sets"></a>Insiemi di entità

| Vendite    | Finance and Operations |
|----------|------------------------|
| Contatti | Contatti CDS           |
| Contatti | Clienti V2           |

## <a name="entity-flow"></a>Flusso di entità

I contatti vengono gestiti in Sales e sincronizzati in Finance and Operations.

Un contatto in Sales può diventare un contatto o un cliente in Finance and Operations. Per stabilire se un contatto in Sales deve essere sincronizzato in Finance and Operations come contatto o cliente, il sistema esamina le seguenti proprietà del contatto in Sales:

- **Sincronizzazione a un cliente in Finance and Operations:** Contatti dove l'opzione **Si tratta del cliente attivo** è impostata su **Sì**
- **Sincronizzazione a un contatto in Finance and Operations:** Contatti dove l'opzione **Si tratta del cliente attivo** è impostata su **No** e **Società** (conto/contatto principale) punta a un conto (non a un contatto)

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

Un nuovo campo **Si tratta del cliente attivo** è stato aggiunto al contatto. Questo campo viene utilizzato per distinguere i contatti che hanno attività di vendita dai contatti che non ne hanno. L'opzione **Si tratta del cliente attivo** è impostata su **Sì** solo per i contatti con offerte, ordini o fatture correlate. Solo tali contatti vengono sincronizzati in Finance and Operations come clienti.

Un nuovo campo **IsCompanyAnAccount** è stato aggiunto al contatto. Questo campo indica se un contatto è collegato a una società (conto/contatto principale) di tipo **Conto**. Queste informazioni vengono utilizzate per identificare i contatti che devono essere sincronizzati in Finance and Operations come contatti.

Un nuovo campo **Numero del contatto** è stato aggiunto al contatto per assicurare una chiave naturale e univoca per l'integrazione. Quando si crea un nuovo contatto, viene generato automaticamente un valore **Numero del contatto** utilizzando una sequenza numerica. Il valore consiste di **CON**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri. Ecco un esempio: **CON-01000-BVRCPS**

Quando la soluzione di integrazione per Sales viene applicata, uno script di aggiornamento imposta il campo **Numero del contatto** per i contatti esistenti utilizzando la sequenza numerica menzionata in precedenza. Lo script di aggiornamento imposta inoltre il campo **Si tratta del cliente attivo** su **Sì** per qualsiasi contatto con attività di vendita.

## <a name="in-finance-and-operations"></a>In Finance and Operations

AI Contatti vengono assegnati tag tramite l'utilizzo della proprietà **IsContactPersonExternallyMaintained**. Questa proprietà indica che un contatto specifico viene gestito esternamente. In questo caso, i contatti gestiti esternamente vengono gestiti in Sales.

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

### <a name="contact-to-customer"></a>Da contatto a cliente

- **CustomerGroup** è obbligatorio in Finance and Operations. Per prevenire errori di sincronizzazione, è possibile specificare un valore predefinito nel mapping. Tale valore predefinito viene quindi utilizzato se il campo viene lasciato vuoto in Sales.

    Il valore del modello predefinito è **10**.

- Aggiungendo i seguenti mapping, è possibile consentire una riduzione del numero degli aggiornamenti manuali necessari in Finance and Operations. È possibile utilizzare un valore predefinito o una mappa di valori da, ad esempio, **Paese** o **Città**.

    - **SiteId** - Un sito predefinito può inoltre essere definito per i prodotti in Finance and Operations. Un sito è obbligatorio per la generazione di offerte e ordini cliente in Finance and Operations.

        Un modello di valore per **SiteId** non è definito.

    - **WarehouseId** - Un magazzino predefinito può inoltre essere definito per i prodotti in Finance and Operations. Un magazzino è obbligatorio per la generazione di offerte e ordini cliente in Finance and Operations.

        Un modello di valore per **WarehouseId** non è definito.

    - **LanguageId** - Una lingua è obbligatoria per la generazione di offerte e ordini cliente in Finance and Operations.
    
        Il valore di modello predefinito è **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene illustrato un esempio di mapping di modelli in Integrazione dati. 

> [!NOTE]
> Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Finance and Operations.

### <a name="contact-to-contact"></a>Da contatto a contatto

![Mapping dei modelli nell'integratore di dati](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a>Da contatto a cliente

![Mapping dei modelli nell'integratore di dati](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>Argomenti correlati

[Prospect to cash](prospect-to-cash.md)

[Sincronizzare conti direttamente da Sales con clienti in Finance and Operations](accounts-template-mapping-direct.md)

[Sincronizzare prodotti direttamente da Finance and Operations con prodotti in Sales](products-template-mapping-direct.md)

[Sincronizzare intestazioni e righe di ordini cliente direttamente da Finance and Operations in Sales](sales-order-template-mapping-direct-two-ways.md)

[Sincronizzare intestazioni e righe di fatture di vendita direttamente da Finance and Operations in Sales](sales-invoice-template-mapping-direct.md)



