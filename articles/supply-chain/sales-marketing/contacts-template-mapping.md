---
title: Sincronizzare contatti da Sales a contatti o clienti in Finance and Operations
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare Contatto (Contatti) e Contatto (Clienti) da Microsoft Dynamics 365 for Sales a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
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
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: 41e27776b94df059ada13efb9a3dbf6a29d67f36
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a>Sincronizzare contatti da Sales a contatti o clienti in Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Prima di utilizzare la soluzione Prospect to cash, acquisisci familiarità con [Integrazione dei dati di Microsoft Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration). 

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le entità Contatto (Contatti) e Contatto (Clienti) da Microsoft Dynamics 365 for Sales (Sales) a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (Finance and Operations).

## <a name="templates-and-tasks"></a>Modelli e attività

I modelli e le attività sottostanti che seguono vengono utilizzati per sincronizzare da Contatto (Contatti) in Sales a Contatto (Clienti) in Finance and Operations:

- **Nomi dei modelli:**

    - Contatti (da Sales a Fin and Ops)
    - Da Contatti a Cliente (da Sales a Fin and Ops)

- **Nomi delle attività del progetto:**

    - Contatti
    - ContactToCustomer

La seguente attività di sincronizzazione è richiesta prima della sincronizzazione di Contatto: Conti (da Sales a Fin and Ops)

## <a name="entity-sets"></a>Insiemi di entità

| Vendite    | CDS     | Finance and Operations |
|----------|---------|------------------------|
| Contatti | Contatto | Contatti CDS           |
| Contatti | Conto | Clienti V2           |

## <a name="entity-flow"></a>Flusso di entità

I Contatti vengono gestiti in Sales e vengono sincronizzati con Common Data Service (CDS) e Finance and Operations.

Un contatto in Sales può diventare un Contatto in CDS e Finance and Operations. In alternativa, può diventare un Conto in CDS e un Cliente in Finance and Operations. Per stabilire se un contatto deve essere prelevato in Sales per la sincronizzazione con CDS e Finance and Operations (ad esempio Contatti in Sales &gt; Contatto in CDS &gt; Contatti in Finance and Operations), il sistema rivede le seguenti proprietà di Contatto in Sales:

- **Sincronizzazione con Conto in CDS e Cliente in Finance and Operations:** Contatti dove l'opzione **Si tratta del cliente attivo** è impostata su **Sì**
- **Sincronizzazione con Contatti in CDS e Contatto in Finance and Operations:** Contatti dove l'opzione **Si tratta del cliente attivo** è impostata su **No** e **Società** (Conto/Contatto principale) punta a un Conto (non a un Contatto)

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales 

Un nuovo campo **Si tratta del cliente attivo** è stato aggiunto al Contatto. Questo campo viene utilizzato per distinguere i Contatti con attività di vendita dai Contatti privi di attività di vendita. L'opzione **Si tratta del cliente attivo** è impostata su **Sì** solo per i Contatti con offerte, ordini o fatture correlate. Solo tali Contatti vengono sincronizzati con Finance and Operations come Clienti.

Un nuovo campo **IsCompanyAnAccount** è stato aggiunto al Contatto. Questo campo viene utilizzato per indicare se un Contatto è collegato a una Società (Conto o Contatto principale) del tipo **Conto**. Queste informazioni vengono utilizzate per identificare i Contatti che devono essere sincronizzati con Finance and Operations come Contatti.

Un nuovo campo **Numero del contatto** è stato aggiunto al Contatto per garantire una chiave naturale e univoca per l'integrazione. Quando si crea un nuovo Contatto, viene generato automaticamente un valore **Numero del contatto** utilizzando una sequenza numerica. Il valore consiste di **CON**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri. Ecco un esempio: **CON-01000-BVRCPS**

Quando la soluzione di integrazione per Sales viene aggiunta a Sales, uno script di aggiornamento imposta il campo **Numero del contatto** per i Contatti esistenti utilizzando la sequenza numerica che è stata illustrata in precedenza. Lo script di aggiornamento consente inoltre di impostare il campo **Si tratta del cliente attivo** su **Sì** per tutti i Contatti con attività di vendita.

## <a name="in-finance-and-operations"></a>In Finance and Operations 

AI Contatti vengono assegnati tag tramite l'utilizzo della proprietà **IsContactPersonExternallyMaintained**. Questa proprietà indica che un contatto specifico viene gestito esternamente. In questo caso, i Contatti gestiti esternamente vengono gestiti in Sales.

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

### <a name="contact-to-contact"></a>Da Contatto a Contatto

- Aggiornare **ID organizzazione CDS** nel mapping **Origine &gt; CDS**.

    - Il valore del modello predefinito per **Organization_OrganizationId [ID organizzazione]** è **ORG001**.
    - Il valore del modello predefinito per **PrimaryAccount_Organization_OrganizationId [ID organizzazione]** è **ORG001**.

- Il **Codice paese-regione indirizzo** è obbligatorio in Finance and Operations. Per evitare errori di sincronizzazione, è possibile specificare un valore predefinito nel mapping **CDS &gt; Operazioni**. Tale valore predefinito viene quindi utilizzato se il campo viene lasciato vuoto in Sales. Il valore del modello predefinito per **PrimaryAddressCountryRegionISOCode** è **Stati Uniti.**
- Assicurarsi che un valore per il campo successivo esista in Finance and Operations. Se le informazioni non sono necessarie in Finance and Operations, è possibile rimuovere il mapping dal mapping **CDS &gt; Destinazione**.

    - **Nome campo in Finance and Operations:** Decisione
    - **Mapping:** PrimaryAccountRole = DecisionMakingRole

### <a name="contact-to-customer"></a>Da Contatto a Cliente

- Aggiornare **ID organizzazione CDS** nel mapping **Origine &gt; CDS**. Il valore del modello predefinito per **Organization_OrganizationId [ID organizzazione]** è **ORG001**.
- Il **Codice paese-regione indirizzo** è obbligatorio in Finance and Operations. Per evitare errori di sincronizzazione, è possibile specificare un valore predefinito nel mapping **CDS &gt; Destinazione**. Tale valore predefinito viene quindi utilizzato se il campo viene lasciato vuoto in Sales. Il valore del modello predefinito per **PrimaryAddressCountryRegionISOCode** è **Stati Uniti.**
- **CustomerGroup** è obbligatorio in Finance and Operations. Per evitare errori di sincronizzazione, è possibile specificare un valore predefinito nel mapping **CDS &gt; Destinazione**. Tale valore predefinito viene quindi utilizzato se il campo viene lasciato vuoto in Sales. Il valore del modello predefinito per **CustomerGroupId** è **10**.
- Aggiungendo i seguenti mapping da **CDS &gt; Destinazione**, è possibile consentire una riduzione del numero degli aggiornamenti manuali che sono in Finance and Operations. È possibile utilizzare un valore predefinito o una mappa di valori da, ad esempio, **Paese** o **Città**.

    - **SiteId**: un sito predefinito può inoltre essere definito per i prodotti in Finance and Operations. Un sito è obbligatorio per la generazione di offerte e ordini cliente in Finance and Operations. Un modello di valore per **SiteId** non è definito.
    - **WarehouseId**: un magazzino predefinito può inoltre essere definito per i prodotti in Finance and Operations. Un magazzino è obbligatorio per la generazione di offerte e ordini cliente in Finance and Operations. Un modello di valore per **WarehouseId** non è definito.
    - **LanguageId**: una lingua è obbligatoria per la generazione di offerte e ordini cliente in Finance and Operations. Il valore del modello predefinito per **LanguageId** è **en-us**.

## <a name="template-mapping-in-data-integrator"></a>Mapping dei modelli nell'integratore di dati

Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.

### <a name="contact-to-contact"></a>Da Contatto a Contatto

![Mapping dei modelli nell'integratore di dati](./media/contacts-template-mapping-data-integrator-1.png)

![Mapping dei modelli per i Contatti nell'integratore di dati](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a>Da Contatto a Cliente

![Mapping dei modelli nell'integratore di dati](./media/contacts-template-mapping-data-integrator-3.png)

![Mapping dei modelli per i Contatti nell'integratore di dati](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Argomenti correlati

[Sincronizzare i prodotti da Finance and Operations ai prodotti in Sales](products-template-mapping.md)

[Sincronizzare conti da Sales a clienti in Finance and Operations](accounts-template-mapping.md)

[Sincronizzare intestazioni e righe di offerte di vendita da Sales in Finance and Operations](sales-quotation-template-mapping.md)

[Sincronizzare intestazioni e righe di ordini di vendita da Finance and Operations in Sales](sales-order-template-mapping.md)

[Sincronizzare intestazioni e righe di fatture di vendita da Finance and Operations in Sales](sales-invoice-template-mapping.md)

