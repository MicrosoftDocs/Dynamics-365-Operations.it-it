---
title: Sincronizzare contatti direttamente da Sales con contatti o clienti in Supply Chain Management
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le entità Contatto (Contatti) e Contatto (Clienti) da Dynamics 365 Sales in Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 57a9c2a860e99855e841f0f4276ba2f92767c2b1
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062517"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a>Sincronizzare contatti direttamente da Sales con contatti o clienti in Supply Chain Management

[!include [banner](../includes/banner.md)]



> [!NOTE]
> Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrare i dati in Microsoft Dataverse per le app](/powerapps/administrator/data-integrator).

Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare direttamente le tabelle Contatto (Contatti) e Contatto (Clienti) da Dynamics 365 Sales in Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Flusso di dati in Prospect to cash

La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Supply Chain Management e Sales. I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Supply Chain Management e Sales. La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Supply Chain Management e Sales.

[![Flusso di dati in Prospect per uno scenario di liquidazione.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelli e attività

Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di PowerApps](https://preview.admin.powerapps.com/dataintegration). Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.

I seguenti modelli e attività sottostanti vengono utilizzati per sincronizzare tabelle Contatto (Contatti) in Sales a tabelle Contatto (Clienti) in Supply Chain Management:

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
| Contatti | Contatti Dataverse           |
| Contatti | Clienti V2           |

## <a name="entity-flow"></a>Flusso di entità

I contatti vengono gestiti in Sales e sincronizzati in Supply Chain Management.

Un contatto in Sales può diventare un contatto o un cliente in Supply Chain Management. Per stabilire se un contatto in Sales deve essere sincronizzato in Supply Chain Management come contatto o cliente, il sistema esamina le seguenti proprietà del contatto in Sales:

- **Sincronizzazione a un cliente in Supply Chain Management:** Contatti dove l'opzione **Si tratta del cliente attivo** è impostata su **Sì**
- **Sincronizzazione a un contatto in Supply Chain Management:** Contatti dove l'opzione **Si tratta del cliente attivo** è impostata su **No** e **Società** (conto/contatto principale) punta a un conto (non a un contatto)

## <a name="prospect-to-cash-solution-for-sales"></a>Soluzione Prospect to cash per Sales

Una nuova colonna **Si tratta del cliente attivo** è stato aggiunto al contatto. Questa colonna viene utilizzata per distinguere i contatti che hanno attività di vendita dai contatti che non ne hanno. L'opzione **Si tratta del cliente attivo** è impostata su **Sì** solo per i contatti con offerte, ordini o fatture correlate. Solo tali contatti vengono sincronizzati in Supply Chain Management come clienti.

Una nuova colonna **IsCompanyAnAccount** è stato aggiunto al contatto. Questa colonna indica se un contatto è collegato a una società (conto/contatto principale) di tipo **Conto**. Queste informazioni vengono utilizzate per identificare i contatti che devono essere sincronizzati in Supply Chain Management come contatti.

Una nuova colonna **Numero del contatto** è stata aggiunta al contatto per assicurare una chiave naturale e univoca per l'integrazione. Quando si crea un nuovo contatto, viene generato automaticamente un valore **Numero del contatto** utilizzando una sequenza numerica. Il valore consiste di **CON**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri. Ecco un esempio: **CON-01000-BVRCPS**

Quando la soluzione di integrazione per Sales viene applicata, uno script di aggiornamento imposta la colonna **Numero del contatto** per i contatti esistenti utilizzando la sequenza numerica menzionata in precedenza. Lo script di aggiornamento imposta inoltre la colonna **Si tratta del cliente attivo** su **Sì** per qualsiasi contatto con attività di vendita.

## <a name="in-supply-chain-management"></a>In Supply Chain Management

AI Contatti vengono assegnati tag tramite l'utilizzo della proprietà **IsContactPersonExternallyMaintained**. Questa proprietà indica che un contatto specifico viene gestito esternamente. In questo caso, i contatti gestiti esternamente vengono gestiti in Sales.

## <a name="preconditions-and-mapping-setup"></a>Prerequisiti e impostazioni di mapping

### <a name="contact-to-customer"></a>Da contatto a cliente

- **CustomerGroup** è obbligatorio in Supply Chain Management. Per prevenire errori di sincronizzazione, è possibile specificare un valore predefinito nel mapping. Tale valore predefinito viene quindi utilizzato se la colonna viene lasciata vuota in Sales.

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
> Il mapping mostra quali informazioni sulle colonne verranno sincronizzate da Sales in Supply Chain Management.

### <a name="contact-to-contact-example"></a>Esempio Da contatto a contatto

![Mapping dei modelli Da contatto a contatto nell'integratore di dati.](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer-example"></a>Esempio Da contatto a cliente

![Mapping dei modelli Da contatto a cliente nell'integratore di dati.](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>Argomenti correlati

[Prospect per uno scenario di liquidazione](prospect-to-cash.md)

[Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management](accounts-template-mapping-direct.md)

[Sincronizzare prodotti direttamente da Supply Chain Management con prodotti in Sales](products-template-mapping-direct.md)

[Sincronizzazione degli ordini cliente direttamente tra Sales e Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Sincronizzare intestazioni e righe di fatture di vendita direttamente da Supply Chain Management in Sales](sales-invoice-template-mapping-direct.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]