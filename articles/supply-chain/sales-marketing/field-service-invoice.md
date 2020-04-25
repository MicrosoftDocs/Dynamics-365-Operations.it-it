---
title: Sincronizzare le fatture del contratto in Field Service con le fatture a testo libero in Supply Chain Management
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le fatture di contratto in Dynamics 365 Field Service con le fatture a testo libero in Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 04/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 943bf04378a8202d676cbabb282a0a6208a92ef3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210002"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a>Sincronizzare le fatture del contratto in Field Service con le fatture a testo libero in Supply Chain Management

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le fatture di contratto in Dynamics 365 Field Service con le fatture a testo libero in Dynamics 365 Supply Chain Management.

## <a name="templates-and-tasks"></a>Modelli e attività

Il seguente modello e le attività sottostanti vengono utilizzati per eseguire la sincronizzazione delle fatture di contratto da Field Service con le fatture a testo libero in Supply Chain Management.

**Nome del modello in Integrazione dati**

- Fatture di contratto (da Field Service a Supply Chain Management)

**Nomi delle attività nel progetto di Integrazione dati**

- Intestazioni fattura
- Righe di fattura

La sincronizzazione seguente è necessaria prima di eseguire la sincronizzazione delle fatture di contratto:

- Conti (da Sales a Supply Chain Management) - Diretti

## <a name="entity-set"></a>Insieme di entità

| Field Service  | Gestione della supply chain                 |
|----------------|----------------------------------------|
| fatture       | Intestazioni fattura a testo libero dei clienti CDS |
| invoicedetails | Righe fattura a testo libero dei clienti CDS   |

## <a name="entity-flow"></a>Flusso di entità

Le fatture create da un contratto di Field Service possono essere sincronizzate in Supply Chain Management tramite un progetto di integrazione dei dati Common Data Service. Gli aggiornamenti a queste fatture verranno sincronizzati con le fatture a testo libero in Supply Chain Management se lo stato di contabilità delle fatture a testo libero è **In corso**. Dopo che le fatture a testo libero vengono registrate in Supply Chain Management e lo stato di contabilità viene aggiornato a **Completato**, non è più possibile sincronizzare gli aggiornamenti da Field Service.

## <a name="field-service-crm-solution"></a>Soluzione CRM Field Service

Il campo **Con righe con origine contratto** è stato aggiunto all'entità **Fattura**. Questo campo assicura che solo le fatture create da un contratto vengano sincronizzate. Il valore è **true** se la fattura contiene almeno una riga di fattura che ha origine da un contratto.

Il campo **Con origine contratto** è stato aggiunto all'entità **Riga fattura**. Questo campo assicura che solo le righe di fattura create da un contratto vengano sincronizzate. Il valore è **true** se la riga di fattura ha origine da un contratto.

**Data fattura** è un campo obbligatorio in Supply Chain Management. Di conseguenza, il campo deve avere un valore in Field Service prima della sincronizzazione. Per soddisfare questo requisito, viene aggiunta la logica seguente:

- Se il campo **Data fattura** è vuoto nell'entità **Fattura** (vale a dire che non include alcun valore), viene impostato sulla data corrente quando si aggiunge una riga di fattura che ha origine da un contratto.
- L'utente può modificare il campo **Data fattura**. Tuttavia, quando l'utente tenta di salvare una fattura derivante da un contratto, riceverà un errore di processo aziendale se nella fattura il campo **Data fattura** è vuoto.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping

### <a name="in-supply-chain-management"></a>In Supply Chain Management

È necessario impostare un'origine di fattura per l'integrazione, per distinguere le fatture a testo libero di Supply Chain Management che sono create da fatture di contratto in Field Service. Quando una fattura ha un'origine fattura di tipo **Integrazione fattura contratto**, viene visualizzato il campo **Numero fattura esterna** nell'intestazione **Fattura di vendita**.

Oltre a essere presente nell'intestazione della fattura, il **Numero di fattura esterno** può essere utilizzato per garantire che le fatture create da fatture di contratto in Field Service vengano filtrate durante la sincronizzazione delle fatture da Supply Chain Management a Field Service.

1. Passare a **Contabilità clienti** \> **Impostazioni** \> **Codici origine fattura**.
2. Selezionare **Nuovo** per creare una nuova origine di fattura.
3. Nel campo **Origine fattura** immettere un nome per l'origine fattura, ad esempio **FS**.
4. Nel campo **Descrizione** immettere una descrizione, ad esempio **Fattura di contratto Field Service**.
5. Selezionare la casella di controllo **Assegnazione tipo di origine**.
6. Impostare il campo **Tipo di origine fattura** su **Integrazione fattura contratto**.
7. Selezionare **Salva**.

### <a name="in-the-data-integration-project"></a>Nel progetto di Integrazione dati

Attività: **Righe fattura**  

Assicurarsi che il valore predefinito per il campo **Valore di visualizzazione del conto principale** di Supply Chain Management venga aggiornato in modo da corrispondere al valore desiderato.

Il valore del modello predefinito è **401100**.

## <a name="template-mapping-in-data-integration"></a>Mapping dei modelli in Integrazione dati

Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a>Fatture di contratto (da Field Service a Supply Chain Management): Intestazioni fattura

[![Mapping dei modelli in Integrazione dati](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a>Fatture di contratto (da Field Service a Supply Chain Management): Righe fattura

[![Mapping dei modelli in Integrazione dati](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)
