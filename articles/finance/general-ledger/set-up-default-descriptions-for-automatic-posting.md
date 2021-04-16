---
title: Impostare descrizioni predefinite per la registrazione automatica
description: Questo argomento spiega come impostare il testo predefinito utilizzato per descrivere le voci contabili registrate automaticamente nella contabilità generale. È possibile impostare il testo di descrizione predefinito utilizzando il testo libero o selezionando variabili fisse.
author: aprilolson
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3963b4ed63021dd3c84a0d87b768486dcb0f386d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837083"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a><span data-ttu-id="5242d-104">Impostare descrizioni predefinite per la registrazione automatica</span><span class="sxs-lookup"><span data-stu-id="5242d-104">Set up default descriptions for automatic posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5242d-105">Questo argomento spiega come impostare il testo predefinito utilizzato per descrivere le voci contabili registrate automaticamente nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="5242d-105">This topic explains how to set up default text that is used to describe accounting entries that are posted automatically to the general ledger.</span></span> <span data-ttu-id="5242d-106">È possibile impostare il testo di descrizione predefinito utilizzando il testo libero o selezionando variabili fisse.</span><span class="sxs-lookup"><span data-stu-id="5242d-106">You can set up default description text by using free-form text or by selecting fixed variables.</span></span>

> [!NOTE]
> <span data-ttu-id="5242d-107">Per alcuni tipi di transazioni, in alcuni paesi, è possibile includere anche il testo presente nei campi del database Microsoft Dynamics AX correlati a tali tipi di transazioni.</span><span class="sxs-lookup"><span data-stu-id="5242d-107">For some transaction types in some countries or regions, you can also include text from fields in the Microsoft Dynamics AX database that are related to those transaction types.</span></span> <span data-ttu-id="5242d-108">Per un elenco dei tipi di transazione, dei paesi e delle aree geografiche, vedere la sezione [Facoltativo: Aggiungere altro testo alle descrizioni predefinite](#optional-add-other-text-to-default-descriptions) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5242d-108">For a list of the transaction types, and the countries and regions, see the [Optional: Add other text to default descriptions](#optional-add-other-text-to-default-descriptions) section later in this topic.</span></span>

## <a name="set-up-default-descriptions"></a><span data-ttu-id="5242d-109">Impostare descrizioni predefinite</span><span class="sxs-lookup"><span data-stu-id="5242d-109">Set up default descriptions</span></span>

1. <span data-ttu-id="5242d-110">Passare ad **Amministrazione organizzazione** \> **Impostazioni** \> **Descrizioni predefinite**.</span><span class="sxs-lookup"><span data-stu-id="5242d-110">Go to **Organization administration** \> **Setup** \> **Default descriptions**.</span></span>
2. <span data-ttu-id="5242d-111">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5242d-111">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="5242d-112">Nel campo **Descrizione** selezionare il tipo di transazione per il quale creare una descrizione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5242d-112">In the **Description** field, select the type of transaction to create a default description for.</span></span>
4. <span data-ttu-id="5242d-113">Nel campo **Lingua** selezionare la lingua a cui si applica la descrizione.</span><span class="sxs-lookup"><span data-stu-id="5242d-113">In the **Language** field, select the language that the description applies to.</span></span>
5. <span data-ttu-id="5242d-114">Nel campo **Testo** immettere la descrizione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5242d-114">In the **Text** field, enter the default description.</span></span> <span data-ttu-id="5242d-115">È possibile immettere il testo nel campo oppure utilizzare una o più delle variabili di testo libero riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="5242d-115">You can type text in the field, or you can use one or more of the following free-text variables:</span></span>

    - <span data-ttu-id="5242d-116">**%1** - Aggiunge la data della transazione.</span><span class="sxs-lookup"><span data-stu-id="5242d-116">**%1** – Add the transaction date.</span></span>
    - <span data-ttu-id="5242d-117">**%2** - Aggiunge un identificatore corrispondente al tipo di documento in fase di registrazione nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="5242d-117">**%2** – Add an identifier that corresponds to the document type that is being posted to the general ledger.</span></span> <span data-ttu-id="5242d-118">Ad esempio, per i tipi di transazioni correlati alle fatture, la variabile **%2** aggiunge il numero della fattura.</span><span class="sxs-lookup"><span data-stu-id="5242d-118">For example, for transaction types that are related to invoices, the **%2** variable adds the invoice number.</span></span>
    - <span data-ttu-id="5242d-119">**%3** - Aggiunge un identificatore corrispondente al tipo di documento in fase di registrazione nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="5242d-119">**%3** – Add an identifier that is related to the document type that is being posted to the general ledger.</span></span> <span data-ttu-id="5242d-120">Ad esempio, per i tipi di transazioni correlati alle fatture, la variabile **%3** aggiunge il numero di conto del cliente.</span><span class="sxs-lookup"><span data-stu-id="5242d-120">For example, for transaction types that are related to invoices, the **%3** variable adds the customer account number.</span></span>

## <a name="optional-add-other-text-to-default-descriptions"></a><span data-ttu-id="5242d-121">Facoltativo: Aggiungere altro testo alle descrizioni predefinite</span><span class="sxs-lookup"><span data-stu-id="5242d-121">Optional: Add other text to default descriptions</span></span>

<span data-ttu-id="5242d-122">Per alcuni tipi di transazioni, in alcuni paesi o aree geografiche, è possibile includere il testo nelle descrizioni predefinite presenti nei campi dei dati correlati a tali tipi di transazioni.</span><span class="sxs-lookup"><span data-stu-id="5242d-122">For some transaction types in some countries or regions, default descriptions can include text that comes from fields in your data that are related to those transaction types.</span></span> <span data-ttu-id="5242d-123">Negli elenchi seguenti vengono illustrati i tipi di transazione e i paesi e le aree geografiche per cui questa opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="5242d-123">The following lists show the transaction types, and the countries and regions, that this option is available for.</span></span>

<span data-ttu-id="5242d-124">**Tipi di transazione**</span><span class="sxs-lookup"><span data-stu-id="5242d-124">**Transaction types**</span></span>

<span data-ttu-id="5242d-125">È possibile aggiungere un altro testo alle descrizioni predefinite per i tipi di transazione correlati ai seguenti tipi di documento:</span><span class="sxs-lookup"><span data-stu-id="5242d-125">You can add other text to default descriptions for transaction types that are related to the following document types:</span></span>

- <span data-ttu-id="5242d-126">Fatture cliente</span><span class="sxs-lookup"><span data-stu-id="5242d-126">Customer invoices</span></span>
- <span data-ttu-id="5242d-127">note di accredito cliente</span><span class="sxs-lookup"><span data-stu-id="5242d-127">Customer credit notes</span></span>
- <span data-ttu-id="5242d-128">pagamenti in contanti cliente</span><span class="sxs-lookup"><span data-stu-id="5242d-128">Customer cash payments</span></span>
- <span data-ttu-id="5242d-129">Pagamenti fornitore</span><span class="sxs-lookup"><span data-stu-id="5242d-129">Vendor payments</span></span>
- <span data-ttu-id="5242d-130">Ordini cliente</span><span class="sxs-lookup"><span data-stu-id="5242d-130">Sales orders</span></span>
- <span data-ttu-id="5242d-131">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="5242d-131">Purchase orders</span></span>
- <span data-ttu-id="5242d-132">Giornali di registrazione magazzino</span><span class="sxs-lookup"><span data-stu-id="5242d-132">Inventory journals</span></span>
- <span data-ttu-id="5242d-133">pianificazione generale (MRP)</span><span class="sxs-lookup"><span data-stu-id="5242d-133">Master planning (MRP)</span></span>
- <span data-ttu-id="5242d-134">Cespiti</span><span class="sxs-lookup"><span data-stu-id="5242d-134">Fixed assets</span></span>

<span data-ttu-id="5242d-135">**Paesi**</span><span class="sxs-lookup"><span data-stu-id="5242d-135">**Countries and regions**</span></span>

<span data-ttu-id="5242d-136">Questa opzione è disponibile per i seguenti paesi e le aree geografiche:</span><span class="sxs-lookup"><span data-stu-id="5242d-136">This option is available for the following countries and regions:</span></span>

- <span data-ttu-id="5242d-137">Brasile</span><span class="sxs-lookup"><span data-stu-id="5242d-137">Brazil</span></span>
- <span data-ttu-id="5242d-138">Cina</span><span class="sxs-lookup"><span data-stu-id="5242d-138">China</span></span>
- <span data-ttu-id="5242d-139">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="5242d-139">Czech Republic</span></span>
- <span data-ttu-id="5242d-140">Europa orientale</span><span class="sxs-lookup"><span data-stu-id="5242d-140">Eastern Europe</span></span>
- <span data-ttu-id="5242d-141">Ungheria</span><span class="sxs-lookup"><span data-stu-id="5242d-141">Hungary</span></span>
- <span data-ttu-id="5242d-142">India</span><span class="sxs-lookup"><span data-stu-id="5242d-142">India</span></span>
- <span data-ttu-id="5242d-143">Giappone</span><span class="sxs-lookup"><span data-stu-id="5242d-143">Japan</span></span>
- <span data-ttu-id="5242d-144">Lituania</span><span class="sxs-lookup"><span data-stu-id="5242d-144">Lithuania</span></span>
- <span data-ttu-id="5242d-145">Lettonia</span><span class="sxs-lookup"><span data-stu-id="5242d-145">Latvia</span></span>
- <span data-ttu-id="5242d-146">Polonia</span><span class="sxs-lookup"><span data-stu-id="5242d-146">Poland</span></span>
- <span data-ttu-id="5242d-147">Russia</span><span class="sxs-lookup"><span data-stu-id="5242d-147">Russia</span></span>

### <a name="add-text-to-default-descriptions"></a><span data-ttu-id="5242d-148">Aggiungere del testo alle descrizioni predefinite</span><span class="sxs-lookup"><span data-stu-id="5242d-148">Add text to default descriptions</span></span>

<span data-ttu-id="5242d-149">Dopo aver completato i passaggi descritti precedentemente in questo argomento nella sezione [Impostare descrizioni predefinite](#set-up-default-descriptions), seguire questi passaggi per aggiungere altro testo alle descrizioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="5242d-149">After you complete the steps in the [Set up default descriptions](#set-up-default-descriptions) section earlier in this topic, follow these steps to add other text to the default descriptions.</span></span>

1. <span data-ttu-id="5242d-150">Nella Scheda dettaglio **Parametri** selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5242d-150">On the **Parameters** FastTab, select **Add**.</span></span>
2. <span data-ttu-id="5242d-151">Nel campo **Tabella riferimenti** selezionare la tabella del database da cui aggiungere i dati dei parametri alla descrizione.</span><span class="sxs-lookup"><span data-stu-id="5242d-151">In the **Reference table** field, select the database table from which to add parameter data to the description.</span></span>
3. <span data-ttu-id="5242d-152">Nel campo **Campo riferimento** selezionare il campo da cui aggiungere i dati dei parametri alla descrizione.</span><span class="sxs-lookup"><span data-stu-id="5242d-152">In the **Reference field** field, select the field from which to add parameter data to the description.</span></span>
4. <span data-ttu-id="5242d-153">Ripetere i passaggi da 1 a 3 per aggiungere ulteriori parametri.</span><span class="sxs-lookup"><span data-stu-id="5242d-153">Repeat steps 1 through 3 to add more parameters.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]