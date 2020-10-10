---
title: Gestione note avanzate
description: Questo argomento spiega come impostare e stampare note predefinite per clienti, fornitori e prodotti.
author: ilkond
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCROrderNotes
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-29
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 5a7bd58f66c4ff8df59ca6027861d235c36c2ace
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830321"
---
# <a name="advanced-notes-management"></a><span data-ttu-id="da526-103">Gestione note avanzate</span><span class="sxs-lookup"><span data-stu-id="da526-103">Advanced notes management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="da526-104">La funzione di gestione avanzata delle note ti consente di impostare note predefinite che si applicano a tutti o a specifici clienti, fornitori e prodotti.</span><span class="sxs-lookup"><span data-stu-id="da526-104">The Advanced notes management feature lets you set up predefined notes that apply to all or specific customers, vendors, and products.</span></span> <span data-ttu-id="da526-105">È quindi possibile aggiungere queste note a documenti aziendali specifici.</span><span class="sxs-lookup"><span data-stu-id="da526-105">You can then add these notes to specific business documents.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="da526-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="da526-106">Prerequisites</span></span>

<span data-ttu-id="da526-107">Prima di iniziare la configurazione, è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="da526-107">Before you begin the setup, the following prerequisites must be met:</span></span>

- <span data-ttu-id="da526-108">La funzionalità **Gestione avanzata delle note** deve essere attivata nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="da526-108">The **Advanced notes management** feature must be turned on in the **Feature management** workspace.</span></span> <span data-ttu-id="da526-109">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da526-109">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="advanced-notes-setup"></a><span data-ttu-id="da526-110">Impostazioni note libere</span><span class="sxs-lookup"><span data-stu-id="da526-110">Advanced notes setup</span></span>

<span data-ttu-id="da526-111">Se è necessario stampare note simili su documenti per gruppi di clienti, è possibile definire nuovi gruppi appositamente per le note avanzate.</span><span class="sxs-lookup"><span data-stu-id="da526-111">If similar notes must be printed on documents for groups of customers, you can define new groups specifically for advanced notes.</span></span> 

### <a name="define-group-codes-and-descriptions"></a><span data-ttu-id="da526-112">Definire codici e descrizioni di gruppi</span><span class="sxs-lookup"><span data-stu-id="da526-112">Define group codes and descriptions</span></span>

1. <span data-ttu-id="da526-113">Andare a **Contabilità clienti** \> **Impostazioni** \> **Note avanzate** \> **Gruppi note avanzate clienti**.</span><span class="sxs-lookup"><span data-stu-id="da526-113">Go to **Accounts receivable** \> **Setup** \> **Advanced notes** \> **Customers advanced notes groups**.</span></span>

![Configurazione di gruppi di note avanzate dei clienti](media/emea-ita-exil-notes-groups.jpg)

2. <span data-ttu-id="da526-115">Dopo aver creato i gruppi, andare a **Contabilità clienti**\>**Clienti**\>**Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="da526-115">After you create the groups, go to **Accounts receivable** \> **Customers** \> **All customers**.</span></span> 
3. <span data-ttu-id="da526-116">Nella Scheda dettaglio **Impostazioni predefinite ordine cliente**, nella sezione **Note avanzate** assegnare i riferimenti per i clienti richiesti ai nuovi gruppi.</span><span class="sxs-lookup"><span data-stu-id="da526-116">On the **Sales orders defaults** FastTab, in the **Advanced notes** section, assign the references for the required customers to the new groups.</span></span>

![Assegnazione del gruppo clienti](media/emea-ita-exil-notes-cust-groups.jpg)

### <a name="set-up-advanced-notes-groups-for-vendors"></a><span data-ttu-id="da526-118">Impostare gruppi di note avanzate per fornitori</span><span class="sxs-lookup"><span data-stu-id="da526-118">Set up advanced notes groups for vendors</span></span>

1. <span data-ttu-id="da526-119">Andare a **Contabilità fornitori** \> **Impostazioni** \> **Note avanzate** \> **Gruppi note avanzate fornitori**.</span><span class="sxs-lookup"><span data-stu-id="da526-119">Go to **Accounts payable** \> **Setup** \> **Advanced notes** \> **Vendors advanced notes groups**.</span></span>
2. <span data-ttu-id="da526-120">Dopo aver creato i gruppi per i fornitori, andare a **Contabilità fornitori** \> **Fornitori** \> **Tutti i fornitori**.</span><span class="sxs-lookup"><span data-stu-id="da526-120">After you create the groups for vendors, go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span> 
3. <span data-ttu-id="da526-121">Nella Scheda dettaglio **Impostazioni predefinite ordine fornitore**, nella sezione **Note avanzate** assegnare i riferimenti per i fornitori richiesti ai nuovi gruppi.</span><span class="sxs-lookup"><span data-stu-id="da526-121">On the **Purchase orders defaults** FastTab, in the **Advanced notes** section, assign the references for the required vendors to the new groups.</span></span>

### <a name="set-up-advanced-notes-groups-for-products"></a><span data-ttu-id="da526-122">Impostare gruppi di note avanzate per prodotti</span><span class="sxs-lookup"><span data-stu-id="da526-122">Set up advanced notes groups for products</span></span> 

1. <span data-ttu-id="da526-123">Andare a **Gestione informazioni sul prodotto** \> **Impostazioni** \> **Note avanzate** \> **Gruppi note avanzate prodotti**.</span><span class="sxs-lookup"><span data-stu-id="da526-123">Go to **Product information management** \> **Setup** \> **Advanced notes** \> **Products advanced notes groups**.</span></span>
2. <span data-ttu-id="da526-124">Dopo aver creato i gruppi per i prodotti, andare a **Gestione informazioni sul prodotto** \> **Prodotti** \> **Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="da526-124">After you create the groups for products, go to **Product information management** \> **Products** \> **Released products**.</span></span> 
3. <span data-ttu-id="da526-125">Nella Scheda dettaglio **Generale**, nella sezione **Amministrazione** assegnare i riferimenti per i prodotti richiesti ai nuovi gruppi.</span><span class="sxs-lookup"><span data-stu-id="da526-125">On the **General** FastTab, in the **Administration** section, assign the references for the required products to the new groups.</span></span>

### <a name="set-up-advanced-notes-for-customers-and-vendors"></a><span data-ttu-id="da526-126">Impostare note avanzate per clienti e fornitori</span><span class="sxs-lookup"><span data-stu-id="da526-126">Set up advanced notes for customers and vendors</span></span>

1. <span data-ttu-id="da526-127">Per inserire il testo delle note avanzate per i clienti e impostare l'applicabilità delle note, andare a **Contabilità clienti**\>**Impostazioni**\>**Note avanzate**\>**Impostazione note avanzate clienti**.</span><span class="sxs-lookup"><span data-stu-id="da526-127">To enter the text of advanced notes for customers and set up the applicability of the notes, go to **Accounts receivable** \> **Setup** \> **Advanced notes** \> **Customers advanced notes setup**.</span></span>

![Configurazione di note avanzate dei clienti](media/emea-ita-exil-notes-setup.jpg)

2. <span data-ttu-id="da526-129">Nella parte inferiore della pagina è possibile inserire il testo della nota nella lingua predefinita dell'utente.</span><span class="sxs-lookup"><span data-stu-id="da526-129">In the lower part of the page, you can enter the note text in the user's default language.</span></span> <span data-ttu-id="da526-130">Per inserire il testo della nota in altre lingue, selezionare **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="da526-130">To enter the note text in other languages, select **Translations**.</span></span>

3. <span data-ttu-id="da526-131">Nella parte superiore della pagina **Impostazione note avanzate**, è possibile impostare l'applicabilità alle note avanzate.</span><span class="sxs-lookup"><span data-stu-id="da526-131">In the upper part of the **Advanced notes setup** page, you can set up the applicability of the advanced notes.</span></span> <span data-ttu-id="da526-132">Selezionare le caselle di controllo appropriate per attivare le note per i vari documenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="da526-132">Select the appropriate check boxes to turn on notes for the various available documents.</span></span> <span data-ttu-id="da526-133">Sulla scheda **Intestazione**, è possibile definire note per tutti i clienti, i singoli clienti o i gruppi di clienti.</span><span class="sxs-lookup"><span data-stu-id="da526-133">On the **Header** tab, you can define notes for all customers, individual customers, or customer groups.</span></span> <span data-ttu-id="da526-134">Sulla scheda **Righe**, è possibile definire le note per tutti gli elementi o per singoli elementi.</span><span class="sxs-lookup"><span data-stu-id="da526-134">On the **Lines** tab, you can define notes for all items or individual items.</span></span>

![Configurazione di righe di note avanzate dei clienti](media/emea-ita-exil-notes-setup-item.jpg)

4. <span data-ttu-id="da526-136">Per impostare le note avanzate per i fornitori, andare a **Contabilità fornitori**\>**Impostazioni**\>**Note avanzate**\>**Impostazione note avanzate fornitori**.</span><span class="sxs-lookup"><span data-stu-id="da526-136">To set up advanced notes for vendors, go to **Accounts payable** \> **Setup** \> **Advanced notes** \> **Vendors advanced notes setup**.</span></span>

> [!NOTE]
> <span data-ttu-id="da526-137">Per le note avanzate dei fornitori, **Ordine fornitore**è l'unico documento disponibile.</span><span class="sxs-lookup"><span data-stu-id="da526-137">For vendor advanced notes, **Purchase order** is the only document that is available.</span></span>

### <a name="set-up-document-types"></a><span data-ttu-id="da526-138">Imposta i tipi di documenti</span><span class="sxs-lookup"><span data-stu-id="da526-138">Set up document types</span></span>

<span data-ttu-id="da526-139">Andare a **Amministrazione organizzazione**\>**Gestione documenti**\>**Tipi di documenti** per definire i tipi di documenti che vengono utilizzati quando vengono creati gli allegati di documenti correlati.</span><span class="sxs-lookup"><span data-stu-id="da526-139">Go to **Organization administration** \> **Document management** \> **Document types** to define the document types that are used when the related document attachments are created.</span></span> <span data-ttu-id="da526-140">Nel campo **Classe**, selezionare **Nota semplice**.</span><span class="sxs-lookup"><span data-stu-id="da526-140">In the **Class** field, select **Simple note**.</span></span>

![Configurazione dei tipi di documenti](media/emea-ita-exil-notes-document-type.jpg)

### <a name="set-up-forms"></a><span data-ttu-id="da526-142">Imposta i moduli</span><span class="sxs-lookup"><span data-stu-id="da526-142">Set up forms</span></span>

<span data-ttu-id="da526-143">Andare a **Contabilità clienti**\>**Impostazioni**\>**Moduli**\>**Impostazione moduli** per impostare i riferimenti ai tipi di documenti per i documenti correlati.</span><span class="sxs-lookup"><span data-stu-id="da526-143">Go to **Accounts receivable** \> **Setup** \> **Forms** \> **Forms setup** to set up the references to document types for the related documents.</span></span> <span data-ttu-id="da526-144">Inoltre, è possibile definire se le note sono applicabili all'intestazione, alle righe o a entrambe le cose di un documento.</span><span class="sxs-lookup"><span data-stu-id="da526-144">Additionally, you can define whether the notes are applicable to a document's header, lines, or both.</span></span>

![Impostazione dei moduli](media/emea-ita-exil-notes-setup-forms.jpg)

### <a name="direct-attachment-to-documents"></a><span data-ttu-id="da526-146">Allegato diretto ai documenti</span><span class="sxs-lookup"><span data-stu-id="da526-146">Direct attachment to documents</span></span>
<span data-ttu-id="da526-147">Le note avanzate possono essere direttamente collegate automaticamente alle conferme degli ordini di vendita, alle liste di prelievo, ai documenti di trasporto e alle fatture senza allegato preliminare agli ordini di vendita.</span><span class="sxs-lookup"><span data-stu-id="da526-147">Advanced notes can be directly attached automatically to sales order confirmations, picking lists, packing slips, and invoices without preliminary attachment to sales orders.</span></span> <span data-ttu-id="da526-148">Per abilitare l'allegato diretto, completare i seguenti passaggi.</span><span class="sxs-lookup"><span data-stu-id="da526-148">To enable direct attachment, complete the following steps.</span></span> 
1. <span data-ttu-id="da526-149">Passare a **Contabilità clienti** \> **Impostazioni** \> **Moduli** \> **Impostazione moduli**.</span><span class="sxs-lookup"><span data-stu-id="da526-149">Go to **Accounts receivable** \> **Setup** \> **Forms** \> **Forms setup**.</span></span>
2. <span data-ttu-id="da526-150">Nella scheda dettaglio **Generale**, nella sezione **Note avanzate** abilitare il parametro **Allegato diretto ai documenti**.</span><span class="sxs-lookup"><span data-stu-id="da526-150">On the **General** FastTab, in the **Advanced notes** section, enable the **Direct attachment to documents** parameter.</span></span>

  ![Pagina di configurazione dei moduli, evidenziazione del parametro Allegato diretto ai documenti](media/attach-documents.jpg)

## <a name="advanced-notes-processing"></a><span data-ttu-id="da526-152">Elaborazione delle note avanzate</span><span class="sxs-lookup"><span data-stu-id="da526-152">Advanced notes processing</span></span>

### <a name="generating-advanced-notes"></a><span data-ttu-id="da526-153">Generazione delle note avanzate</span><span class="sxs-lookup"><span data-stu-id="da526-153">Generating advanced notes</span></span>

<span data-ttu-id="da526-154">In Contabilità clienti, le note per conferme, distinte di prelievo, documenti di trasporto e fatture vengono generate automaticamente come allegati agli ordini cliente generati per clienti e prodotti selezionati.</span><span class="sxs-lookup"><span data-stu-id="da526-154">In Accounts receivable, the notes for confirmations, picking lists, packing slips, and invoices are automatically generated as attachments to the sales orders that are generated for selected customers and products.</span></span>

![Note degli ordini cliente](media/emea-ita-exil-notes-order.jpg)

<span data-ttu-id="da526-156">Le note per offerte e fatture a testo libero sono generate automaticamente nei documenti appropriati.</span><span class="sxs-lookup"><span data-stu-id="da526-156">The notes for quotations and free text invoices are automatically generated in the appropriate documents.</span></span>

<span data-ttu-id="da526-157">In Contabilità fornitori, le note vengono generate automaticamente come allegati a nuovi ordini fornitore per fornitori e prodotti applicabili.</span><span class="sxs-lookup"><span data-stu-id="da526-157">In Accounts payable, notes are automatically generated as attachments to new purchase orders for applicable vendors and products.</span></span>

### <a name="printing-advanced-notes"></a><span data-ttu-id="da526-158">Stampa delle note avanzate</span><span class="sxs-lookup"><span data-stu-id="da526-158">Printing advanced notes</span></span>

<span data-ttu-id="da526-159">Note avanzate definite come **Esterne**sono stampate nei relativi documenti commerciali a seconda delle impostazioni di **Impostazione moduli**</span><span class="sxs-lookup"><span data-stu-id="da526-159">Advanced notes which are defined as **External** are printed in the related business documents depending on the settings on the **Form setup**</span></span>

![Impostazione della stampa delle note avanzate](media/emea-ita-exil-notes-printing.jpg)
