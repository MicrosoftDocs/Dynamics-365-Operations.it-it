---
title: Sincronizzare le fatture del contratto in Field Service con le fatture a testo libero in Supply Chain Management
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le fatture di contratto in Dynamics 365 Field Service con le fatture a testo libero in Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 04/10/2018
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
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 21a77a0289055285f47323803a484c012e662e3a
ms.sourcegitcommit: 0cc89dd42c1924ca0ec735c6566bc56b39cc5f7d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2021
ms.locfileid: "6102736"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a><span data-ttu-id="e3322-103">Sincronizzare le fatture del contratto in Field Service con le fatture a testo libero in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e3322-103">Synchronize agreement invoices in Field Service to free text invoices in Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="e3322-104">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le fatture di contratto in Dynamics 365 Field Service con le fatture a testo libero in Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e3322-104">This topic discusses the templates and underlying tasks that are used to synchronize agreement invoices in Dynamics 365 Field Service to free text invoices in Dynamics 365 Supply Chain Management.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="e3322-105">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="e3322-105">Templates and tasks</span></span>

<span data-ttu-id="e3322-106">Il seguente modello e le attività sottostanti vengono utilizzati per eseguire la sincronizzazione delle fatture di contratto da Field Service con le fatture a testo libero in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e3322-106">The following template and underlying tasks are used to run synchronization of agreement invoices from Field Service to free text invoices in Supply Chain Management.</span></span>

<span data-ttu-id="e3322-107">**Nome del modello in Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="e3322-107">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="e3322-108">Fatture di contratto (da Field Service a Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="e3322-108">Agreement invoices (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="e3322-109">**Nomi delle attività nel progetto di Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="e3322-109">**Names of the tasks in the Data integration project**</span></span>

- <span data-ttu-id="e3322-110">Intestazioni fattura</span><span class="sxs-lookup"><span data-stu-id="e3322-110">Invoice headers</span></span>
- <span data-ttu-id="e3322-111">Righe di fattura</span><span class="sxs-lookup"><span data-stu-id="e3322-111">Invoice lines</span></span>

<span data-ttu-id="e3322-112">La sincronizzazione seguente è necessaria prima di eseguire la sincronizzazione delle fatture di contratto:</span><span class="sxs-lookup"><span data-stu-id="e3322-112">The following synchronization is required before synchronization of agreement invoices can occur:</span></span>

- <span data-ttu-id="e3322-113">Conti (da Sales a Supply Chain Management) - Diretti</span><span class="sxs-lookup"><span data-stu-id="e3322-113">Accounts (Sales to Supply Chain Management) – Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="e3322-114">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="e3322-114">Entity set</span></span>

| <span data-ttu-id="e3322-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="e3322-115">Field Service</span></span>  | <span data-ttu-id="e3322-116">Gestione della supply chain</span><span class="sxs-lookup"><span data-stu-id="e3322-116">Supply Chain Management</span></span>                 |
|----------------|----------------------------------------|
| <span data-ttu-id="e3322-117">fatture</span><span class="sxs-lookup"><span data-stu-id="e3322-117">invoices</span></span>       | <span data-ttu-id="e3322-118">Intestazioni fattura a testo libero dei clienti Dataverse</span><span class="sxs-lookup"><span data-stu-id="e3322-118">Dataverse customer free text invoice headers</span></span> |
| <span data-ttu-id="e3322-119">invoicedetails</span><span class="sxs-lookup"><span data-stu-id="e3322-119">invoicedetails</span></span> | <span data-ttu-id="e3322-120">Righe fattura a testo libero dei clienti Dataverse</span><span class="sxs-lookup"><span data-stu-id="e3322-120">Dataverse customer free text invoice lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="e3322-121">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="e3322-121">Entity flow</span></span>

<span data-ttu-id="e3322-122">Le fatture create da un contratto di Field Service possono essere sincronizzate in Supply Chain Management tramite un progetto di integrazione dei dati Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e3322-122">Invoices that are created from an agreement in Field Service can be synchronized to Supply Chain Management via a Microsoft Dataverse Data integration project.</span></span> <span data-ttu-id="e3322-123">Gli aggiornamenti a queste fatture verranno sincronizzati con le fatture a testo libero in Supply Chain Management se lo stato di contabilità delle fatture a testo libero è **In corso**.</span><span class="sxs-lookup"><span data-stu-id="e3322-123">Updates to these invoices will be synchronized to the free text invoices in Supply Chain Management if the accounting status of the free text invoices is **In process**.</span></span> <span data-ttu-id="e3322-124">Dopo che le fatture a testo libero vengono registrate in Supply Chain Management e lo stato di contabilità viene aggiornato a **Completato**, non è più possibile sincronizzare gli aggiornamenti da Field Service.</span><span class="sxs-lookup"><span data-stu-id="e3322-124">After the free text invoices are posted in Supply Chain Management, and the accounting status is updated to **Completed**, you can no longer synchronize updates from Field Service.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="e3322-125">Soluzione CRM Field Service</span><span class="sxs-lookup"><span data-stu-id="e3322-125">Field Service CRM solution</span></span>

<span data-ttu-id="e3322-126">La colonna **Con righe con origine contratto** è stata aggiunta alla tabella **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="e3322-126">The **Has Lines With Agreement Origin** column has been added to the **Invoice** table.</span></span> <span data-ttu-id="e3322-127">Questa colonna assicura che solo le fatture create da un contratto vengano sincronizzate.</span><span class="sxs-lookup"><span data-stu-id="e3322-127">This column helps guarantee that only invoices that are created from an agreement are synchronized.</span></span> <span data-ttu-id="e3322-128">Il valore è **true** se la fattura contiene almeno una riga di fattura che ha origine da un contratto.</span><span class="sxs-lookup"><span data-stu-id="e3322-128">The value is **true** if the invoice contains at least one invoice line that originates from an agreement.</span></span>

<span data-ttu-id="e3322-129">La colonna **Con origine contratto** è stata aggiunta alla tabella **Riga fattura**.</span><span class="sxs-lookup"><span data-stu-id="e3322-129">The **Has Agreement Origin** column has been added to the **Invoice Line** table.</span></span> <span data-ttu-id="e3322-130">Questa colonna assicura che solo le righe fattura create da un contratto vengano sincronizzate.</span><span class="sxs-lookup"><span data-stu-id="e3322-130">This column helps guarantee that only invoice lines that are created from an agreement are synchronized.</span></span> <span data-ttu-id="e3322-131">Il valore è **true** se la riga di fattura ha origine da un contratto.</span><span class="sxs-lookup"><span data-stu-id="e3322-131">The value is **true** if the invoice line originates from an agreement.</span></span>

<span data-ttu-id="e3322-132">**Data fattura** è un campo obbligatorio in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e3322-132">**Invoice date** is a mandatory field in Supply Chain Management.</span></span> <span data-ttu-id="e3322-133">Di conseguenza, la colonna deve avere un valore in Field Service prima della sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="e3322-133">Therefore, the column must have a value in Field Service before synchronization occurs.</span></span> <span data-ttu-id="e3322-134">Per soddisfare questo requisito, viene aggiunta la logica seguente:</span><span class="sxs-lookup"><span data-stu-id="e3322-134">To meet this requirement, the following logic is added:</span></span>

- <span data-ttu-id="e3322-135">Se la colonna **Data fattura** è vuoto nella tabella **Fattura** (vale a dire che non include alcun valore), viene impostato sulla data corrente quando si aggiunge una riga di fattura che ha origine da un contratto.</span><span class="sxs-lookup"><span data-stu-id="e3322-135">If the **Invoice Date** column is blank on the **Invoice** table (that is, if it has no value), it's set to the current date when an invoice line that originates from an agreement is added.</span></span>
- <span data-ttu-id="e3322-136">L'utente può modificare la colonna **Data fattura**.</span><span class="sxs-lookup"><span data-stu-id="e3322-136">The user can change the **Invoice Date** column.</span></span> <span data-ttu-id="e3322-137">Tuttavia, quando l'utente tenta di salvare una fattura derivante da un contratto, riceverà un errore di processo aziendale se nella fattura la colonna **Data fattura** è vuoto.</span><span class="sxs-lookup"><span data-stu-id="e3322-137">However, when the user tries to save an invoice that originates from an agreement, they receive a business process error if the **Invoice Date** column is blank on the invoice.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="e3322-138">Prerequisiti e impostazione del mapping</span><span class="sxs-lookup"><span data-stu-id="e3322-138">Prerequisites and mapping setup</span></span>

### <a name="in-supply-chain-management"></a><span data-ttu-id="e3322-139">In Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e3322-139">In Supply Chain Management</span></span>

<span data-ttu-id="e3322-140">È necessario impostare un'origine di fattura per l'integrazione, per distinguere le fatture a testo libero di Supply Chain Management che sono create da fatture di contratto in Field Service.</span><span class="sxs-lookup"><span data-stu-id="e3322-140">An invoice origin must be set up for the integration, to distinguish the free text invoices in Supply Chain Management that are created from agreement invoices in Field Service.</span></span> <span data-ttu-id="e3322-141">Quando una fattura ha un'origine fattura di tipo **Integrazione fattura contratto**, viene visualizzato il campo **Numero fattura esterna** nell'intestazione **Fattura di vendita**.</span><span class="sxs-lookup"><span data-stu-id="e3322-141">When an invoice has an invoice origin of the **Agreement invoice integration** type, the **External invoice number** field is shown on the **Sales invoice** header.</span></span>

<span data-ttu-id="e3322-142">Oltre a essere presente nell'intestazione della fattura, il **Numero di fattura esterno** può essere utilizzato per garantire che le fatture create da fatture di contratto in Field Service vengano filtrate durante la sincronizzazione delle fatture da Supply Chain Management a Field Service.</span><span class="sxs-lookup"><span data-stu-id="e3322-142">Besides appearing on the invoice header, the **External invoice number** information can be used to help guarantee that invoices that are created from Field Service agreement invoices are filtered out during invoice synchronization from Supply Chain Management to Field Service.</span></span>

1. <span data-ttu-id="e3322-143">Passare a **Contabilità clienti** \> **Impostazioni** \> **Codici origine fattura**.</span><span class="sxs-lookup"><span data-stu-id="e3322-143">Go to **Accounts receivable** \> **Setup** \> **Invoice origin codes**.</span></span>
2. <span data-ttu-id="e3322-144">Selezionare **Nuovo** per creare una nuova origine di fattura.</span><span class="sxs-lookup"><span data-stu-id="e3322-144">Select **New** to create a new invoice origin.</span></span>
3. <span data-ttu-id="e3322-145">Nel campo **Origine fattura** immettere un nome per l'origine fattura, ad esempio **FS**.</span><span class="sxs-lookup"><span data-stu-id="e3322-145">In the **Invoice origin** field, enter a name for the invoice origin, such as **FS**.</span></span>
4. <span data-ttu-id="e3322-146">Nel campo **Descrizione** immettere una descrizione, ad esempio **Fattura di contratto Field Service**.</span><span class="sxs-lookup"><span data-stu-id="e3322-146">In the **Description** field, enter a description, such as **Field Service Agreement Invoice**.</span></span>
5. <span data-ttu-id="e3322-147">Selezionare la casella di controllo **Assegnazione tipo di origine**.</span><span class="sxs-lookup"><span data-stu-id="e3322-147">Select the **Origin type assignment** check box.</span></span>
6. <span data-ttu-id="e3322-148">Impostare il campo **Tipo di origine fattura** su **Integrazione fattura contratto**.</span><span class="sxs-lookup"><span data-stu-id="e3322-148">Set the **Invoice origin type** field to **Agreement invoice integration**.</span></span>
7. <span data-ttu-id="e3322-149">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e3322-149">Select **Save**.</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="e3322-150">Nel progetto di Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="e3322-150">In the Data Integration project</span></span>

<span data-ttu-id="e3322-151">Attività: **Righe fattura**</span><span class="sxs-lookup"><span data-stu-id="e3322-151">Task: **Invoice lines**</span></span>  

<span data-ttu-id="e3322-152">Assicurarsi che il valore predefinito per il campo **Valore di visualizzazione del conto principale** di Supply Chain Management venga aggiornato in modo da corrispondere al valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="e3322-152">Make sure that the default value for the Supply Chain Management field **Main Account Display Value** is updated to match the desired value.</span></span>

<span data-ttu-id="e3322-153">Il valore del modello predefinito è **401100**.</span><span class="sxs-lookup"><span data-stu-id="e3322-153">The default template value is **401100**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="e3322-154">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="e3322-154">Template mapping in Data integration</span></span>

<span data-ttu-id="e3322-155">Nelle figure seguenti viene illustrato il mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="e3322-155">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a><span data-ttu-id="e3322-156">Fatture di contratto (da Field Service a Supply Chain Management): Intestazioni fattura</span><span class="sxs-lookup"><span data-stu-id="e3322-156">Agreement invoices (Field Service to Supply Chain Management): Invoice headers</span></span>

<span data-ttu-id="e3322-157">[![Mapping dei modelli in Integrazione dati per le intestazioni delle fatture](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span><span class="sxs-lookup"><span data-stu-id="e3322-157">[![Template mapping in Data integration for invoice headers](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a><span data-ttu-id="e3322-158">Fatture di contratto (da Field Service a Supply Chain Management): Righe fattura</span><span class="sxs-lookup"><span data-stu-id="e3322-158">Agreement invoices (Field Service to Supply Chain Management): Invoice lines</span></span>

<span data-ttu-id="e3322-159">[![Mapping dei modelli in Integrazione dati per le righe delle fatture](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span><span class="sxs-lookup"><span data-stu-id="e3322-159">[![Template mapping in Data integration for invoice lines](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]