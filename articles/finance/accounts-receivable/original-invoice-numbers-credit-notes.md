---
title: Riferimenti a fatture originali nelle note di credito
description: Questo argomento spiega come impostare e stampare i numeri di fattura originali nelle note di credito correlate.
author: ilkond
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 673288f04b33aa2a578f9e2e7913dbe7ac309644
ms.sourcegitcommit: 7cdec5469ff0da145ac4e01caf3287d0627ae2dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2021
ms.locfileid: "5100004"
---
# <a name="references-to-original-invoices-in-credit-notes"></a><span data-ttu-id="1bdcf-103">Riferimenti a fatture originali nelle note di credito</span><span class="sxs-lookup"><span data-stu-id="1bdcf-103">References to original invoices in credit notes</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="1bdcf-104">In alcuni paesi e regioni, esiste un requisito legale per cui le note di credito stampate devono includere i riferimenti alle fatture originali.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-104">In some countries and regions, there is a legal requirement that printed credit notes include references to the original invoices.</span></span> <span data-ttu-id="1bdcf-105">Questo argomento spiega come impostare e stampare i numeri di fattura originali nelle note di credito correlate.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-105">This topic explains how to set up and print the original invoice numbers in related credit notes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1bdcf-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1bdcf-106">Prerequisites</span></span>

- <span data-ttu-id="1bdcf-107">Nell'area di lavoro **Gestione funzionalità**, attiva la funzionalità **Layout fatturazione crediti per report fatture di vendita e progetto** caratteristica.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-107">In the **Feature management** workspace, turn on the **Credit invoicing layout for sales and project invoice reports** feature.</span></span> <span data-ttu-id="1bdcf-108">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1bdcf-108">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="1bdcf-109">I formati stampabili dei documenti richiesti devono essere configurati in Gestione stampa.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-109">The printable formats of the required documents must be configured in Print management.</span></span>

<span data-ttu-id="1bdcf-110">La funzionalità descritta in questo argomento si applica ai seguenti documenti:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-110">The functionality that is described in this topic applies to the following documents:</span></span>

<span data-ttu-id="1bdcf-111">**Contabilità clienti**</span><span class="sxs-lookup"><span data-stu-id="1bdcf-111">**Accounts receivable**</span></span>

- <span data-ttu-id="1bdcf-112">Nota di accredito a testo libero</span><span class="sxs-lookup"><span data-stu-id="1bdcf-112">Free text credit note</span></span>
- <span data-ttu-id="1bdcf-113">Nota di credito cliente</span><span class="sxs-lookup"><span data-stu-id="1bdcf-113">Customer credit note</span></span>

<span data-ttu-id="1bdcf-114">**Gestione progetti e contabilità**</span><span class="sxs-lookup"><span data-stu-id="1bdcf-114">**Project management and accounting**</span></span>

- <span data-ttu-id="1bdcf-115">Nota di accredito progetto</span><span class="sxs-lookup"><span data-stu-id="1bdcf-115">Project credit note</span></span>

## <a name="configure-accounts-receivable-parameters"></a><span data-ttu-id="1bdcf-116">Configurare i parametri di contabilità clienti</span><span class="sxs-lookup"><span data-stu-id="1bdcf-116">Configure Accounts receivable parameters</span></span>

<span data-ttu-id="1bdcf-117">Segui questi passaggi per impostare il parametro che controlla se i riferimenti alle fatture originali vengono stampati nelle note di credito correlate.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-117">Follow these steps to set the parameter that controls whether references to the original invoices are printed in related credit notes.</span></span>

1. <span data-ttu-id="1bdcf-118">Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-118">Go to **Accounts receivable** \> **Setup** \> **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="1bdcf-119">Nella scheda **Aggiornamenti** nella scheda dettaglio **Fattura** imposta l'opzione **Applica il layout di fatturazione delle note di accredito nei report delle fatture di vendita e di progetto** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-119">On the **Updates** tab, on the **Invoice** FastTab, set the **Apply the credit invoicing layout into sales and project invoice reports** option to **Yes**.</span></span>

![Configurazione dei parametri di contabilità clienti](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a><span data-ttu-id="1bdcf-121">Definire i riferimenti alle fatture originali</span><span class="sxs-lookup"><span data-stu-id="1bdcf-121">Define references to original invoices</span></span>

<span data-ttu-id="1bdcf-122">Utilizza le seguenti procedure per definire i riferimenti alle fatture originali, in base al tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-122">Use the following procedures to define references to original invoices, based on the document type.</span></span>

### <a name="free-text-credit-note"></a><span data-ttu-id="1bdcf-123">Nota di accredito a testo libero</span><span class="sxs-lookup"><span data-stu-id="1bdcf-123">Free text credit note</span></span>

1. <span data-ttu-id="1bdcf-124">Passare a **Contabilità clienti** \> **Fatture** \> **Tutte le fatture a testo libero**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-124">Go to **Accounts receivable** \> **Invoices** \> **All free text invoices**.</span></span>
2. <span data-ttu-id="1bdcf-125">Crea una nuova nota di credito o seleziona una nota di credito esistente.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-125">Create a new credit note, or select an existing credit note.</span></span>
3. <span data-ttu-id="1bdcf-126">Apri la fattura.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-126">Open the invoice.</span></span>
4. <span data-ttu-id="1bdcf-127">Nel riquadro azioni, nel gruppo **Genera** della scheda **Funzioni**, seleziona **Fatturazione note di accredito**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-127">On the Action Pane, on the **Invoice** tab, in the **Functions** group, select **Credit invoicing**.</span></span>
5. <span data-ttu-id="1bdcf-128">Immetti il riferimento alla fattura originale e seleziona il motivo della correzione.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-128">Enter the reference to the original invoice, and select the reason for the correction.</span></span>

![Definizione del riferimento per una fattura a testo libero](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a><span data-ttu-id="1bdcf-130">Nota di credito cliente</span><span class="sxs-lookup"><span data-stu-id="1bdcf-130">Customer credit note</span></span>

1. <span data-ttu-id="1bdcf-131">Andare a **Contabilità clienti** \> **Ordini** \> **Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-131">Go to **Accounts receivable** \> **Orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="1bdcf-132">Seleziona e apri l'ordine di vendita fatturato che deve essere corretto.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-132">Select and open the invoiced sales order that must be corrected.</span></span>
3. <span data-ttu-id="1bdcf-133">Nel riquadro azioni, nel gruppo **Nota di accredito** della scheda **Vendi** fai clic su **Nota di accredito**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-133">On the Action Pane, on the **Sell** tab, in the **Credit note** group, select **Credit note**.</span></span>
4. <span data-ttu-id="1bdcf-134">Immetti il motivo della correzione.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-134">Enter the reason for the correction.</span></span> <span data-ttu-id="1bdcf-135">Il riferimento alla fattura originale viene stabilito automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-135">The reference to the original invoice is automatically established.</span></span>

![Definizione del riferimento per un ordine cliente](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a><span data-ttu-id="1bdcf-137">Nota di accredito progetto</span><span class="sxs-lookup"><span data-stu-id="1bdcf-137">Project credit note</span></span>

1. <span data-ttu-id="1bdcf-138">Vai a **Gestione progetti e contabilità** \> **Fatture progetto** \> **Fatture progetto**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-138">Go to **Project management and accounting** \> **Project invoices** \> **Project invoices**.</span></span>
2. <span data-ttu-id="1bdcf-139">Seleziona e apri la fattura di progetto che deve essere corretta.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-139">Select and open the project invoice that must be corrected.</span></span>
3. <span data-ttu-id="1bdcf-140">Nel riquadro azioni, nel gruppo **Fattura progetto** della scheda **Funzioni**, seleziona **Seleziona per nota di accredito**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-140">On the Action Pane, on the **Project invoice** tab, in the **Functions** group, select **Select for credit note**.</span></span>
4. <span data-ttu-id="1bdcf-141">Seleziona **Fatturazione note di accredito**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-141">Select **Credit invoicing**.</span></span>
5. <span data-ttu-id="1bdcf-142">Immetti il motivo della correzione.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-142">Enter the reason for the correction.</span></span> <span data-ttu-id="1bdcf-143">Il riferimento alla fattura originale viene stabilito automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-143">The reference to the original invoice is automatically established.</span></span>

![Definizione del riferimento per una fattura di progetto](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a><span data-ttu-id="1bdcf-145">Stampa di note di accredito</span><span class="sxs-lookup"><span data-stu-id="1bdcf-145">Printing credit notes</span></span>

<span data-ttu-id="1bdcf-146">Quando stampi le note di credito di progetto, del cliente e testo libero, includeranno il riferimento alla fattura originale e il motivo della correzione.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-146">When you print free text, customer, and project credit notes, they will include the reference to the original invoice and the correction reason.</span></span>

![Nota di credito stampata](media/credit-note-FTI.jpg)

> [!NOTE]
> <span data-ttu-id="1bdcf-148">Assicurati che i formati stampabili dei documenti siano correttamente configurati, ipotizzando che vengano stampati i riferimenti alle fatture originali.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-148">Make sure that the printable formats of the documents are correctly configured, on the assumption that references to original invoices will be printed.</span></span>
