---
title: Sincronizzare contatti direttamente da Sales con contatti o clienti in Supply Chain Management
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le entità Contatto (Contatti) e Contatto (Clienti) da Dynamics 365 Sales in Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 7d3a4602a3d8462666dfcb26b97a4f652891f7bc
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249976"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a>Sincronizzare contatti direttamente da Sales con contatti o clienti in Supply Chain Management

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrare i dati in Common Data Service per le app](https://docs.microsoft.com/powerapps/administrator/data-integrator).

Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare direttamente le entità Contatto (Contatti) e Contatto (Clienti) da Dynamics 365 Sales in Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Flusso di dati in Prospect to cash

La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Supply Chain Management e Sales. I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Supply Chain Management e Sales. La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Supply Chain Management e Sales.

[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelli e attività

Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di PowerApps](https://preview.admin.powerapps.com/dataintegration). Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.

I seguenti modelli e attività sottostanti vengono utilizzati per sincronizzare entità Contatto (Contatti) in Sales a entità Contatto (Clienti) in Supply Chain Management:

- **Nomi dei modelli in Integrazione dati**

    - Contatti (da Sales in Supply Chain Management) - Diretto
    - Da Contatti a Cliente (da Sales in Supply Chain Management) - Diretto

- **Nomi delle attività nel progetto di Integrazione dati**

    - Contatti
    - ContactToCustomer

La seguente attività di sincronizzazione è necessaria prima della sincronizzazione dei contatti: Conti (da Sales in Supply Chain Management)

## <a name="entity-sets"></a>Insiemi di entità

| Vendite    | Gestione della supply chain |
|----------|------------------------|
| Contatti | Contatti CDS           |
| Contatti | Clienti V2           |

## <a name="entity-flow"></a>Flusso di entità

I contatti vengono gestiti in Sales e sincronizzati in Supply Chain Management.

Un contatto in Sales può diventare un contatto o un cliente in Supply Chain Management. Per stabilire se un contatto in Sales deve essere sincronizzato in Supply Chain Management come contatto o cliente, il sistema esamina le seguenti proprietà del contatto in Sales:

- **Sincronizzazione a un cliente in Supply Chain Management:** Contatti dove l'opzione **Si tratta del cliente attivo** è impostata su **Sì**
- **Sincronizzazione a un contatto in Supply Chain Management:** Contatti dove l'opzione **Si tratta del cliente attivo** è impostata su **No** e **Società** (conto/contatto principale) punta a un conto (non a un contatto)

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

Un nuovo campo **Si tratta del cliente attivo** è stato aggiunto al contatto. Questo campo viene utilizzato per distinguere i contatti che hanno attività di vendita dai contatti che non ne hanno. L'opzione **Si tratta del cliente attivo** è impostata su **Sì** solo per i contatti con offerte, ordini o fatture correlate. Solo tali contatti vengono sincronizzati in Supply Chain Management come clienti.

Un nuovo campo **IsCompanyAnAccount** è stato aggiunto al contatto. Questo campo indica se un contatto è collegato a una società (conto/contatto principale) di tipo **Conto**. Queste informazioni vengono utilizzate per identificare i contatti che devono essere sincronizzati in Supply Chain Management come contatti.

Un nuovo campo **Numero del contatto** è stato aggiunto al contatto per assicurare una chiave naturale e univoca per l'integrazione. Quando si crea un nuovo contatto, viene generato automaticamente un valore **Numero del contatto** utilizzando una sequenza numerica. Il valore consiste di **CON**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri. Ecco un esempio: **CON-01000-BVRCPS**

Quando la soluzione di integrazione per Sales viene applicata, uno script di aggiornamento imposta il campo **Numero del contatto** per i contatti esistenti utilizzando la sequenza numerica menzionata in precedenza. Lo script di aggiornamento imposta inoltre il campo **Si tratta del cliente attivo** su **Sì** per qualsiasi contatto con attività di vendita.

## <a name="in-supply-chain-management"></a>In Supply Chain Management

AI Contatti vengono assegnati tag tramite l'utilizzo della proprietà **IsContactPersonExternallyMaintained**. Questa proprietà indica che un contatto specifico viene gestito esternamente. In questo caso, i contatti gestiti esternamente vengono gestiti in Sales.

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

### <a name="contact-to-customer"></a>Da contatto a cliente

- **CustomerGroup** è obbligatorio in Supply Chain Management. Per prevenire errori di sincronizzazione, è possibile specificare un valore predefinito nel mapping. Tale valore predefinito viene quindi utilizzato se il campo viene lasciato vuoto in Sales.

    Il valore del modello predefinito è **10**.

- Aggiungendo i seguenti mapping, è possibile consentire una riduzione del numero degli aggiornamenti manuali necessari in Supply Chain Management. È possibile utilizzare un valore predefinito o una mappa di valori da, ad esempio, **Paese** o **Città**.

    - **SiteId** - Un sito predefinito può inoltre essere definito per i prodotti in Supply Chain Management. Un sito è obbligatorio per la generazione di offerte e ordini cliente in Supply Chain Management.

        Un modello di valore per **SiteId** non è definito.

    - **WarehouseId** - Un magazzino predefinito può inoltre essere definito per i prodotti in Supply Chain Management. Un magazzino è obbligatorio per la generazione di offerte e ordini cliente in Supply Chain Management.

        Un modello di valore per **WarehouseId** non è definito.

    - **LanguageId** - Una lingua è obbligatoria per la generazione di offerte e ordini cliente in Supply Chain Management.
    
        Il valore di modello predefinito è **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene illustrato un esempio di mapping di modelli in Integrazione dati. 

> [!NOTE]
> Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Supply Chain Management.

### <a name="contact-to-contact"></a>Da contatto a contatto

![Mapping dei modelli nell'integratore di dati](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a>Da contatto a cliente

![Mapping dei modelli nell'integratore di dati](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>Argomenti correlati

[Prospect per uno scenario di liquidazione](prospect-to-cash.md)

[Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management](accounts-template-mapping-direct.md)

[Sincronizzare prodotti direttamente da Supply Chain Management con prodotti in Sales](products-template-mapping-direct.md)

[Sincronizzare intestazioni e righe di ordini di vendita direttamente da Supply Chain Management in Sales](sales-order-template-mapping-direct-two-ways.md)

[Sincronizzare intestazioni e righe di fatture di vendita direttamente da Supply Chain Management in Sales](sales-invoice-template-mapping-direct.md)


