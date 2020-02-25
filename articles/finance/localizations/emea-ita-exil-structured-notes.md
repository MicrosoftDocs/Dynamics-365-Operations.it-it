---
title: Gestione note avanzate
description: Questo argomento spiega come impostare e stampare note predefinite per clienti, fornitori e prodotti.
author: ilkond
manager: AnnBe
ms.date: 12/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-29
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 767330d85242012640d7bd4a3c088c132b234fbe
ms.sourcegitcommit: 4c60f5dccdf0b94ed110a657ef331546adc5424a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2020
ms.locfileid: "2982295"
---
# <a name="advanced-notes-management"></a><span data-ttu-id="08eb4-103">Gestione note avanzate</span><span class="sxs-lookup"><span data-stu-id="08eb4-103">Advanced notes management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="08eb4-104">La funzione di gestione avanzata delle note ti consente di impostare note predefinite che si applicano a tutti o a specifici clienti, fornitori e prodotti.</span><span class="sxs-lookup"><span data-stu-id="08eb4-104">The Advanced notes management feature lets you set up predefined notes that apply to all or specific customers, vendors, and products.</span></span> <span data-ttu-id="08eb4-105">È quindi possibile aggiungere queste note a documenti aziendali specifici.</span><span class="sxs-lookup"><span data-stu-id="08eb4-105">You can then add these notes to specific business documents.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="08eb4-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="08eb4-106">Prerequisites</span></span>

<span data-ttu-id="08eb4-107">Prima di iniziare la configurazione, è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="08eb4-107">Before you begin the setup, the following prerequisites must be met:</span></span>

- <span data-ttu-id="08eb4-108">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="08eb4-108">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="08eb4-109">La funzionalità **Gestione avanzata delle note** deve essere attivata nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="08eb4-109">The **Advanced notes management** feature must be turned on in the **Feature management** workspace.</span></span> <span data-ttu-id="08eb4-110">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="08eb4-110">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="advanced-notes-setup"></a><span data-ttu-id="08eb4-111">Impostazioni note libere</span><span class="sxs-lookup"><span data-stu-id="08eb4-111">Advanced notes setup</span></span>

### <a name="set-up-customer-and-vendor-groups-for-advanced-notes"></a><span data-ttu-id="08eb4-112">Impostare gruppi di clienti e fornitori per le note avanzate</span><span class="sxs-lookup"><span data-stu-id="08eb4-112">Set up customer and vendor groups for advanced notes</span></span>

<span data-ttu-id="08eb4-113">Se è necessario stampare note simili su documenti per gruppi di clienti, è possibile definire nuovi gruppi appositamente per le note avanzate.</span><span class="sxs-lookup"><span data-stu-id="08eb4-113">If similar notes must be printed on documents for groups of customers, you can define new groups specifically for advanced notes.</span></span> <span data-ttu-id="08eb4-114">Per definire codici e descrizioni di gruppo, andare a **Contabilità clienti**\>**Impostazioni**\>**Note avanzate**\>**Gruppi note avanzate clienti**.</span><span class="sxs-lookup"><span data-stu-id="08eb4-114">To define group codes and descriptions, go to **Accounts receivable** \> **Setup** \> **Advanced notes** \> **Customers advanced notes groups**.</span></span>

![Configurazione di gruppi di note avanzate dei clienti](media/emea-ita-exil-notes-groups.jpg)

<span data-ttu-id="08eb4-116">Dopo aver creato i gruppi, andare a **Contabilità clienti**\>**Clienti**\>**Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="08eb4-116">After you create the groups, go to **Accounts receivable** \> **Customers** \> **All customers**.</span></span> <span data-ttu-id="08eb4-117">Quindi, sulla Scheda dettaglio **Impostazioni predefinite ordine cliente**, nella sezione **Note avanzate** assegnare i riferimenti per i clienti richiesti ai nuovi gruppi.</span><span class="sxs-lookup"><span data-stu-id="08eb4-117">Then, on the **Sales orders defaults** FastTab, in the **Advanced notes** section, assign the references for the required customers to the new groups.</span></span>

![Assegnazione del gruppo clienti](media/emea-ita-exil-notes-cust-groups.jpg)

<span data-ttu-id="08eb4-119">Per impostare gruppi di note avanzate per i fornitori, andare a **Contabilità fornitori**\>**Impostazioni**\>**Note avanzate**\>**Gruppi note avanzate fornitori**.</span><span class="sxs-lookup"><span data-stu-id="08eb4-119">To set up advanced notes groups for vendors, go to **Accounts payable** \> **Setup** \> **Advanced notes** \> **Vendors advanced notes groups**.</span></span>

### <a name="set-up-advanced-notes-for-customers-and-vendors"></a><span data-ttu-id="08eb4-120">Impostare note avanzate per clienti e fornitori</span><span class="sxs-lookup"><span data-stu-id="08eb4-120">Set up advanced notes for customers and vendors</span></span>

<span data-ttu-id="08eb4-121">Per inserire il testo delle note avanzate per i clienti e impostare l'applicabilità delle note, andare a **Contabilità clienti**\>**Impostazioni**\>**Note avanzate**\>**Impostazione note avanzate clienti**.</span><span class="sxs-lookup"><span data-stu-id="08eb4-121">To enter the text of advanced notes for customers and set up the applicability of the notes, go to **Accounts receivable** \> **Setup** \> **Advanced notes** \> **Customers advanced notes setup**.</span></span>

![Configurazione di note avanzate dei clienti](media/emea-ita-exil-notes-setup.jpg)

<span data-ttu-id="08eb4-123">Nella parte inferiore della pagina è possibile inserire il testo della nota nella lingua predefinita dell'utente.</span><span class="sxs-lookup"><span data-stu-id="08eb4-123">In the lower part of the page, you can enter the note text in the user's default language.</span></span> <span data-ttu-id="08eb4-124">Per inserire il testo della nota in altre lingue, selezionare **Traduzioni**.</span><span class="sxs-lookup"><span data-stu-id="08eb4-124">To enter the note text in other languages, select **Translations**.</span></span>

<span data-ttu-id="08eb4-125">Nella parte superiore della pagina **Impostazione note avanzate**, è possibile impostare l'applicabilità alle note avanzate.</span><span class="sxs-lookup"><span data-stu-id="08eb4-125">In the upper part of the **Advanced notes setup** page, you can set up the applicability of the advanced notes.</span></span> <span data-ttu-id="08eb4-126">Selezionare le caselle di controllo appropriate per attivare le note per i vari documenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="08eb4-126">Select the appropriate check boxes to turn on notes for the various available documents.</span></span> <span data-ttu-id="08eb4-127">Sulla scheda **Intestazione**, è possibile definire note per tutti i clienti, i singoli clienti o i gruppi di clienti.</span><span class="sxs-lookup"><span data-stu-id="08eb4-127">On the **Header** tab, you can define notes for all customers, individual customers, or customer groups.</span></span> <span data-ttu-id="08eb4-128">Sulla scheda **Righe**, è possibile definire le note per tutti gli elementi o per singoli elementi.</span><span class="sxs-lookup"><span data-stu-id="08eb4-128">On the **Lines** tab, you can define notes for all items or individual items.</span></span>

![Configurazione di righe di note avanzate dei clienti](media/emea-ita-exil-notes-setup-item.jpg)

<span data-ttu-id="08eb4-130">Per impostare le note avanzate per i fornitori, andare a **Contabilità fornitori**\>**Impostazioni**\>**Note avanzate**\>**Impostazione note avanzate fornitori**.</span><span class="sxs-lookup"><span data-stu-id="08eb4-130">To set up advanced notes for vendors, go to **Accounts payable** \> **Setup** \> **Advanced notes** \> **Vendors advanced notes setup**.</span></span>

> [!NOTE]
> <span data-ttu-id="08eb4-131">Per le note avanzate dei fornitori, **Ordine fornitore**è l'unico documento disponibile.</span><span class="sxs-lookup"><span data-stu-id="08eb4-131">For vendor advanced notes, **Purchase order** is the only document that is available.</span></span>

### <a name="set-up-document-types"></a><span data-ttu-id="08eb4-132">Imposta i tipi di documenti</span><span class="sxs-lookup"><span data-stu-id="08eb4-132">Set up document types</span></span>

<span data-ttu-id="08eb4-133">Andare a **Amministrazione organizzazione**\>**Gestione documenti**\>**Tipi di documenti** per definire i tipi di documenti che vengono utilizzati quando vengono creati gli allegati di documenti correlati.</span><span class="sxs-lookup"><span data-stu-id="08eb4-133">Go to **Organization administration** \> **Document management** \> **Document types** to define the document types that are used when the related document attachments are created.</span></span> <span data-ttu-id="08eb4-134">Nel campo **Classe**, selezionare **Nota semplice**.</span><span class="sxs-lookup"><span data-stu-id="08eb4-134">In the **Class** field, select **Simple note**.</span></span>

![Configurazione dei tipi di documenti](media/emea-ita-exil-notes-document-type.jpg)

### <a name="set-up-forms"></a><span data-ttu-id="08eb4-136">Imposta i moduli</span><span class="sxs-lookup"><span data-stu-id="08eb4-136">Set up forms</span></span>

<span data-ttu-id="08eb4-137">Andare a **Contabilità clienti**\>**Impostazioni**\>**Moduli**\>**Impostazione moduli** per impostare i riferimenti ai tipi di documenti per i documenti correlati.</span><span class="sxs-lookup"><span data-stu-id="08eb4-137">Go to **Accounts receivable** \> **Setup** \> **Forms** \> **Forms setup** to set up the references to document types for the related documents.</span></span> <span data-ttu-id="08eb4-138">Inoltre, è possibile definire se le note sono applicabili all'intestazione, alle righe o a entrambe le cose di un documento.</span><span class="sxs-lookup"><span data-stu-id="08eb4-138">Additionally, you can define whether the notes are applicable to a document's header, lines, or both.</span></span>

![Impostazione dei moduli](media/emea-ita-exil-notes-setup-forms.jpg)

## <a name="advanced-notes-processing"></a><span data-ttu-id="08eb4-140">Elaborazione delle note avanzate</span><span class="sxs-lookup"><span data-stu-id="08eb4-140">Advanced notes processing</span></span>

### <a name="generating-advanced-notes"></a><span data-ttu-id="08eb4-141">Generazione delle note avanzate</span><span class="sxs-lookup"><span data-stu-id="08eb4-141">Generating advanced notes</span></span>

<span data-ttu-id="08eb4-142">In Contabilità clienti, le note per conferme, distinte di prelievo, documenti di trasporto e fatture vengono generate automaticamente come allegati agli ordini cliente generati per clienti e prodotti selezionati.</span><span class="sxs-lookup"><span data-stu-id="08eb4-142">In Accounts receivable, the notes for confirmations, picking lists, packing slips, and invoices are automatically generated as attachments to the sales orders that are generated for selected customers and products.</span></span>

![Note degli ordini cliente](media/emea-ita-exil-notes-order.jpg)

<span data-ttu-id="08eb4-144">Le note per offerte e fatture a testo libero sono generate automaticamente nei documenti appropriati.</span><span class="sxs-lookup"><span data-stu-id="08eb4-144">The notes for quotations and free text invoices are automatically generated in the appropriate documents.</span></span>

<span data-ttu-id="08eb4-145">In Contabilità fornitori, le note vengono generate automaticamente come allegati a nuovi ordini fornitore per fornitori e prodotti applicabili.</span><span class="sxs-lookup"><span data-stu-id="08eb4-145">In Accounts payable, notes are automatically generated as attachments to new purchase orders for applicable vendors and products.</span></span>

### <a name="printing-advanced-notes"></a><span data-ttu-id="08eb4-146">Stampa delle note avanzate</span><span class="sxs-lookup"><span data-stu-id="08eb4-146">Printing advanced notes</span></span>

<span data-ttu-id="08eb4-147">Note avanzate definite come **Esterne**sono stampate nei relativi documenti commerciali a seconda delle impostazioni di **Impostazione moduli**</span><span class="sxs-lookup"><span data-stu-id="08eb4-147">Advanced notes which are defined as **External** are printed in the related business documents depending on the settings on the **Form setup**</span></span>

![Impostazione della stampa delle note avanzate](media/emea-ita-exil-notes-printing.jpg)
