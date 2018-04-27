---
title: Sincronizzare le fatture di contratto in Field Service con le fatture a testo libero in Finance and Operations
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le fatture di contratto in Microsoft Dynamics 365 for Field Service con le fatture a testo libero in Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2018
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
ms.sourcegitcommit: 08cfd2cfa24bef0f0c92126f5d1052a12ceba37a
ms.openlocfilehash: 1863814d6dd645da8602495858d024fbad2e7149
ms.contentlocale: it-it
ms.lasthandoff: 04/11/2018

---

# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-finance-and-operations"></a>Sincronizzare le fatture di contratto in Field Service con le fatture a testo libero in Finance and Operations

[!include[banner](../includes/banner.md)]

Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le fatture di contratto in Microsoft Dynamics 365 for Field Service con le fatture a testo libero in Microsoft Dynamics 365 for Finance and Operations.

## <a name="templates-and-tasks"></a>Modelli e attività

Il seguente modello e le attività sottostanti vengono utilizzati per eseguire la sincronizzazione delle fatture di contratto da Field Service con le fatture a testo libero in Finance and Operation.

**Nome del modello in Integrazione dati:**

- Fatture di contratto (da Field Service a Finance and Operations)

**Nomi delle attività nel progetto di Integrazione dati:**

- Intestazioni fattura
- Righe fattura

La sincronizzazione seguente è necessaria prima di eseguire la sincronizzazione delle fatture di contratto:

- Conti (da Sales a Fin and Ops) - Diretti

## <a name="entity-set"></a>Insieme di entità

| Field Service  | Finance and Operations                 |
|----------------|----------------------------------------|
| fatture       | Intestazioni fattura a testo libero dei clienti CDS |
| invoicedetails | Righe fattura a testo libero dei clienti CDS   |

## <a name="entity-flow"></a>Flusso di entità

Le fatture create da un contratto di Field Service possono essere sincronizzate in Finance and Operations tramite un progetto di integrazione dei dati CDS (Common Data Service). Gli aggiornamenti a queste fatture verranno sincronizzati con le fatture a testo libero in Finance and Operations se lo stato di contabilità delle fatture a testo libero è **In corso**. Dopo che le fatture a testo libero vengono registrate in Finance and Operations e lo stato di contabilità viene aggiornato a **Completato**, non è più possibile sincronizzare gli aggiornamenti da Field Service.

## <a name="field-service-crm-solution"></a>Soluzione CRM Field Service

Il campo **Con righe con origine contratto** è stato aggiunto all'entità **Fattura**. Questo campo assicura che solo le fatture create da un contratto vengano sincronizzate. Il valore è **true** se la fattura contiene almeno una riga di fattura che ha origine da un contratto.

Il campo **Con origine contratto** è stato aggiunto all'entità **Riga fattura**. Questo campo assicura che solo le righe di fattura create da un contratto vengano sincronizzate. Il valore è **true** se la riga di fattura ha origine da un contratto.

**Data fattura** è un campo obbligatorio in Finance and Operations. Di conseguenza, il campo deve avere un valore in Field Service prima della sincronizzazione. Per soddisfare questo requisito, viene aggiunta la logica seguente:

- Se il campo **Data fattura** è vuoto nell'entità **Fattura** (vale a dire che non include alcun valore), viene impostato sulla data corrente quando si aggiunge una riga di fattura che ha origine da un contratto.
- L'utente può modificare il campo **Data fattura**. Tuttavia, quando l'utente tenta di salvare una fattura derivante da un contratto, riceverà un errore di processo aziendale se nella fattura il campo **Data fattura** è vuoto.

## <a name="prerequisites-and-mapping-setup"></a>Prerequisiti e impostazione del mapping

### <a name="in-finance-and-operations"></a>In Finance and Operations

È necessario impostare un'origine di fattura per l'integrazione, per distinguere le fatture a testo libero di Finance and Operations che sono create da fatture di contratto in Field Service. Quando una fattura ha un'origine fattura di tipo **Integrazione fattura contratto**, viene visualizzato il campo **Numero fattura esterna** nell'intestazione **Fattura di vendita**.

Oltre a essere presente nell'intestazione della fattura, il **Numero di fattura esterno** può essere utilizzato per garantire che le fatture create da fatture di contratto in Field Service vengano filtrate durante la sincronizzazione delle fatture da Finance and Operations a Field Service.

1. Passare a **Contabilità clienti** \> **Impostazioni** \> **Codici origine fattura**.
2. Selezionare **Nuovo** per creare una nuova origine di fattura.
3. Nel campo **Origine fattura** immettere un nome per l'origine fattura, ad esempio **FS**.
4. Nel campo **Descrizione** immettere una descrizione, ad esempio **Fattura di contratto Field Service**.
5. Selezionare la casella di controllo **Assegnazione tipo di origine**.
6. Impostare il campo **Tipo di origine fattura** su **Integrazione fattura contratto**.
7. Selezionare **Salva**.

### <a name="in-the-data-integration-project"></a>Nel progetto di Integrazione dati

Attività: **Righe fattura**  

Assicurarsi che il valore predefinito per il campo **Valore di visualizzazione del conto principale** di Finance and Operations venga aggiornato in modo da corrispondere al valore desiderato.

Il valore del modello predefinito è **401100**.

