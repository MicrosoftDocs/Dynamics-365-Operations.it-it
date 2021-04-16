---
title: Riferimenti a fatture originali nelle note di credito
description: Questo argomento spiega come impostare e stampare i numeri di fattura originali nelle note di credito correlate.
author: ilkond
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ce06a0ce4f2a308e1917ac2c7cbc66f0494a2ec5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811512"
---
# <a name="references-to-original-invoices-in-credit-notes"></a><span data-ttu-id="0bc76-103">Riferimenti a fatture originali nelle note di credito</span><span class="sxs-lookup"><span data-stu-id="0bc76-103">References to original invoices in credit notes</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="0bc76-104">In alcuni paesi e regioni, esiste un requisito legale per cui le note di credito stampate devono includere i riferimenti alle fatture originali.</span><span class="sxs-lookup"><span data-stu-id="0bc76-104">In some countries and regions, there is a legal requirement that printed credit notes include references to the original invoices.</span></span> <span data-ttu-id="0bc76-105">Questo argomento spiega come impostare e stampare i numeri di fattura originali nelle note di credito correlate.</span><span class="sxs-lookup"><span data-stu-id="0bc76-105">This topic explains how to set up and print the original invoice numbers in related credit notes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0bc76-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0bc76-106">Prerequisites</span></span>

- <span data-ttu-id="0bc76-107">Nell'area di lavoro **Gestione funzionalità**, attiva la funzionalità **Layout fatturazione crediti per report fatture di vendita e progetto** caratteristica.</span><span class="sxs-lookup"><span data-stu-id="0bc76-107">In the **Feature management** workspace, turn on the **Credit invoicing layout for sales and project invoice reports** feature.</span></span> <span data-ttu-id="0bc76-108">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0bc76-108">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="0bc76-109">I formati stampabili dei documenti richiesti devono essere configurati in Gestione stampa.</span><span class="sxs-lookup"><span data-stu-id="0bc76-109">The printable formats of the required documents must be configured in Print management.</span></span>

<span data-ttu-id="0bc76-110">La funzionalità descritta in questo argomento si applica ai seguenti documenti:</span><span class="sxs-lookup"><span data-stu-id="0bc76-110">The functionality that is described in this topic applies to the following documents:</span></span>

<span data-ttu-id="0bc76-111">**Contabilità clienti**</span><span class="sxs-lookup"><span data-stu-id="0bc76-111">**Accounts receivable**</span></span>

- <span data-ttu-id="0bc76-112">Nota di accredito a testo libero</span><span class="sxs-lookup"><span data-stu-id="0bc76-112">Free text credit note</span></span>
- <span data-ttu-id="0bc76-113">Nota di credito cliente</span><span class="sxs-lookup"><span data-stu-id="0bc76-113">Customer credit note</span></span>

<span data-ttu-id="0bc76-114">**Gestione progetti e contabilità**</span><span class="sxs-lookup"><span data-stu-id="0bc76-114">**Project management and accounting**</span></span>

- <span data-ttu-id="0bc76-115">Nota di accredito progetto</span><span class="sxs-lookup"><span data-stu-id="0bc76-115">Project credit note</span></span>

## <a name="configure-accounts-receivable-parameters"></a><span data-ttu-id="0bc76-116">Configurare i parametri di contabilità clienti</span><span class="sxs-lookup"><span data-stu-id="0bc76-116">Configure Accounts receivable parameters</span></span>

<span data-ttu-id="0bc76-117">Segui questi passaggi per impostare il parametro che controlla se i riferimenti alle fatture originali vengono stampati nelle note di credito correlate.</span><span class="sxs-lookup"><span data-stu-id="0bc76-117">Follow these steps to set the parameter that controls whether references to the original invoices are printed in related credit notes.</span></span>

1. <span data-ttu-id="0bc76-118">Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="0bc76-118">Go to **Accounts receivable** \> **Setup** \> **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="0bc76-119">Nella scheda **Aggiornamenti** nella scheda dettaglio **Fattura** imposta l'opzione **Applica il layout di fatturazione delle note di accredito nei report delle fatture di vendita e di progetto** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="0bc76-119">On the **Updates** tab, on the **Invoice** FastTab, set the **Apply the credit invoicing layout into sales and project invoice reports** option to **Yes**.</span></span>

![Configurazione dei parametri di contabilità clienti](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a><span data-ttu-id="0bc76-121">Definire i riferimenti alle fatture originali</span><span class="sxs-lookup"><span data-stu-id="0bc76-121">Define references to original invoices</span></span>

<span data-ttu-id="0bc76-122">Utilizza le seguenti procedure per definire i riferimenti alle fatture originali, in base al tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="0bc76-122">Use the following procedures to define references to original invoices, based on the document type.</span></span>

### <a name="free-text-credit-note"></a><span data-ttu-id="0bc76-123">Nota di accredito a testo libero</span><span class="sxs-lookup"><span data-stu-id="0bc76-123">Free text credit note</span></span>

1. <span data-ttu-id="0bc76-124">Passare a **Contabilità clienti** \> **Fatture** \> **Tutte le fatture a testo libero**.</span><span class="sxs-lookup"><span data-stu-id="0bc76-124">Go to **Accounts receivable** \> **Invoices** \> **All free text invoices**.</span></span>
2. <span data-ttu-id="0bc76-125">Crea una nuova nota di credito o seleziona una nota di credito esistente.</span><span class="sxs-lookup"><span data-stu-id="0bc76-125">Create a new credit note, or select an existing credit note.</span></span>
3. <span data-ttu-id="0bc76-126">Apri la fattura.</span><span class="sxs-lookup"><span data-stu-id="0bc76-126">Open the invoice.</span></span>
4. <span data-ttu-id="0bc76-127">Nel riquadro azioni, nel gruppo **Genera** della scheda **Funzioni**, seleziona **Fatturazione note di accredito**.</span><span class="sxs-lookup"><span data-stu-id="0bc76-127">On the Action Pane, on the **Invoice** tab, in the **Functions** group, select **Credit invoicing**.</span></span>
5. <span data-ttu-id="0bc76-128">Immetti il riferimento alla fattura originale e seleziona il motivo della correzione.</span><span class="sxs-lookup"><span data-stu-id="0bc76-128">Enter the reference to the original invoice, and select the reason for the correction.</span></span>

![Definizione del riferimento per una fattura a testo libero](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a><span data-ttu-id="0bc76-130">Nota di credito cliente</span><span class="sxs-lookup"><span data-stu-id="0bc76-130">Customer credit note</span></span>

1. <span data-ttu-id="0bc76-131">Andare a **Contabilità clienti** \> **Ordini** \> **Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="0bc76-131">Go to **Accounts receivable** \> **Orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="0bc76-132">Seleziona e apri l'ordine di vendita fatturato che deve essere corretto.</span><span class="sxs-lookup"><span data-stu-id="0bc76-132">Select and open the invoiced sales order that must be corrected.</span></span>
3. <span data-ttu-id="0bc76-133">Nel riquadro azioni, nel gruppo **Nota di accredito** della scheda **Vendi** fai clic su **Nota di accredito**.</span><span class="sxs-lookup"><span data-stu-id="0bc76-133">On the Action Pane, on the **Sell** tab, in the **Credit note** group, select **Credit note**.</span></span>
4. <span data-ttu-id="0bc76-134">Immetti il motivo della correzione.</span><span class="sxs-lookup"><span data-stu-id="0bc76-134">Enter the reason for the correction.</span></span> <span data-ttu-id="0bc76-135">Il riferimento alla fattura originale viene stabilito automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0bc76-135">The reference to the original invoice is automatically established.</span></span>

![Definizione del riferimento per un ordine cliente](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a><span data-ttu-id="0bc76-137">Nota di accredito progetto</span><span class="sxs-lookup"><span data-stu-id="0bc76-137">Project credit note</span></span>

1. <span data-ttu-id="0bc76-138">Vai a **Gestione progetti e contabilità** \> **Fatture progetto** \> **Fatture progetto**.</span><span class="sxs-lookup"><span data-stu-id="0bc76-138">Go to **Project management and accounting** \> **Project invoices** \> **Project invoices**.</span></span>
2. <span data-ttu-id="0bc76-139">Seleziona e apri la fattura di progetto che deve essere corretta.</span><span class="sxs-lookup"><span data-stu-id="0bc76-139">Select and open the project invoice that must be corrected.</span></span>
3. <span data-ttu-id="0bc76-140">Nel riquadro azioni, nel gruppo **Fattura progetto** della scheda **Funzioni**, seleziona **Seleziona per nota di accredito**.</span><span class="sxs-lookup"><span data-stu-id="0bc76-140">On the Action Pane, on the **Project invoice** tab, in the **Functions** group, select **Select for credit note**.</span></span>
4. <span data-ttu-id="0bc76-141">Seleziona **Fatturazione note di accredito**.</span><span class="sxs-lookup"><span data-stu-id="0bc76-141">Select **Credit invoicing**.</span></span>
5. <span data-ttu-id="0bc76-142">Immetti il motivo della correzione.</span><span class="sxs-lookup"><span data-stu-id="0bc76-142">Enter the reason for the correction.</span></span> <span data-ttu-id="0bc76-143">Il riferimento alla fattura originale viene stabilito automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0bc76-143">The reference to the original invoice is automatically established.</span></span>

![Definizione del riferimento per una fattura di progetto](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a><span data-ttu-id="0bc76-145">Stampa di note di accredito</span><span class="sxs-lookup"><span data-stu-id="0bc76-145">Printing credit notes</span></span>

<span data-ttu-id="0bc76-146">Quando stampi le note di credito di progetto, del cliente e testo libero, includeranno il riferimento alla fattura originale e il motivo della correzione.</span><span class="sxs-lookup"><span data-stu-id="0bc76-146">When you print free text, customer, and project credit notes, they will include the reference to the original invoice and the correction reason.</span></span>

![Nota di credito stampata](media/credit-note-FTI.jpg)

> [!NOTE]
> <span data-ttu-id="0bc76-148">Assicurati che i formati stampabili dei documenti siano correttamente configurati, ipotizzando che vengano stampati i riferimenti alle fatture originali.</span><span class="sxs-lookup"><span data-stu-id="0bc76-148">Make sure that the printable formats of the documents are correctly configured, on the assumption that references to original invoices will be printed.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
