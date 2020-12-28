---
title: Lettere di intento - Fatturazione di esportatori abituali
description: Questo argomento fornisce informazioni su come impostare lettere di intento e su come utilizzarle quando si emettono fatture.
author: ilkond
manager: AnnBe
ms.date: 03/17/2020
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
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 921041e142e2e3d5aceb1832c9189fc72a9238ab
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408118"
---
# <a name="intent-letters---invoicing-of-usual-exporters"></a><span data-ttu-id="a9514-103">Lettere di intento - Fatturazione di esportatori abituali</span><span class="sxs-lookup"><span data-stu-id="a9514-103">Intent letters - Invoicing of usual exporters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a9514-104">Per ricevere una fornitura di beni o servizi esente da IVA in Italia, le società classificate come esportatori abituali devono inviare una dichiarazione di intento (una lettera numerata e datata) agli uffici tributari italiani e agli agenti doganali delle società.</span><span class="sxs-lookup"><span data-stu-id="a9514-104">To receive a supply of goods or services free of sales tax in Italy, companies that are categorized as usual exporters must send an intent declaration (a numbered and dated letter) to the Italian tax authorities and to company counteragents.</span></span>
 
## <a name="prerequisites"></a><span data-ttu-id="a9514-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a9514-105">Prerequisites</span></span>

<span data-ttu-id="a9514-106">Prima di fatturare, è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="a9514-106">The following prerequisites must be met before you invoice:</span></span>

- <span data-ttu-id="a9514-107">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="a9514-107">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="a9514-108">La funzionalità **Lettere di intento - Fatturazione di esportatori usuali** deve essere attivata nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a9514-108">The **Intent letters - invoicing of usual exporters** feature must be turned on in the **Feature management** workspace.</span></span> <span data-ttu-id="a9514-109">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a9514-109">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="set-up-accounts-receivable-parameters"></a><span data-ttu-id="a9514-110">Impostazione dei parametri di Contabilità clienti</span><span class="sxs-lookup"><span data-stu-id="a9514-110">Set up Accounts receivable parameters</span></span>

1. <span data-ttu-id="a9514-111">Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="a9514-111">Go to **Accounts receivable** \> **Setup** \> **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="a9514-112">Nella scheda **Contabilità generale e IVA** nella scheda dettaglio **Esportatori abituali**, nel campo **Fascia IVA esportatori abituali**, definire una fascia IVA che viene utilizzata solo per gli esportatori abituali.</span><span class="sxs-lookup"><span data-stu-id="a9514-112">On the **Ledger and sales tax** tab, on **Usual exporters** FastTab, in **Usual exporter sales tax group** field, define a sales tax group that is used only for usual exporters.</span></span>
3. <span data-ttu-id="a9514-113">Impostare l'opzione **Assegnazione automatica lettera di intento** su **Sì** per attivare l'assegnazione automatica delle lettere di intento durante la fatturazione.</span><span class="sxs-lookup"><span data-stu-id="a9514-113">Set the **Automatic intent letter assignment** option to **Yes** to turn on the automatic assignment of intent letters during invoicing.</span></span>

![Impostazione dei parametri di Contabilità clienti](media/emea-ita-exil-intent-AR-parm.jpg)

## <a name="set-up-sales-tax-codes"></a><span data-ttu-id="a9514-115">Impostare i codici IVA</span><span class="sxs-lookup"><span data-stu-id="a9514-115">Set up sales tax codes</span></span>

1. <span data-ttu-id="a9514-116">Selezionare **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA**.</span><span class="sxs-lookup"><span data-stu-id="a9514-116">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax code**.</span></span>
2. <span data-ttu-id="a9514-117">Selezionare un codice IVA, quindi nella scheda dettaglio **Generale**, nella sezione **Fatturazione**, impostare l'opzione **Invia lettere di intento** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a9514-117">Select a sales tax code, and then, on the **General** FastTab, in the **Invoicing** section, set the **Affect intent letters** option to **Yes**.</span></span>

![Impostazione di un codice IVA](media/emea-ita-exil-intent-tax-setup.jpg)

## <a name="set-up-customers"></a><span data-ttu-id="a9514-119">Impostare i clienti</span><span class="sxs-lookup"><span data-stu-id="a9514-119">Set up customers</span></span>

1. <span data-ttu-id="a9514-120">Selezionare **Contabilità clienti** \> **Clienti** \> **Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="a9514-120">Go to **Accounts receivable** \> **Customers** \> **All customers**.</span></span>
2. <span data-ttu-id="a9514-121">Selezionare un cliente, quindi nella sezione **Fattura e consegna**, selezionare l'opzione **Esportatore abituale** per indicare che il cliente appartiene al gruppo di esportatori usuali.</span><span class="sxs-lookup"><span data-stu-id="a9514-121">Select a customer, and then, in the **Invoice and delivery** section, select the **Usual exporter** option to indicate that the customer belongs to the group of usual exporters.</span></span>

## <a name="set-up-a-number-sequence-for-intent-letters"></a><span data-ttu-id="a9514-122">Impostare una sequenza numerica per lettere di intento</span><span class="sxs-lookup"><span data-stu-id="a9514-122">Set up a number sequence for intent letters</span></span>

1. <span data-ttu-id="a9514-123">Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="a9514-123">Go to **Accounts receivable** \> **Setup** \> **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="a9514-124">Nella scheda **Sequenze numeriche**, nel campo **Numero di lettera di intento** specificare il riferimento alla sequenza numerica che verrà utilizzata per numerare le lettere di intento.</span><span class="sxs-lookup"><span data-stu-id="a9514-124">On the **Number sequences** tab, in **Internal letter number** field, specify the reference to the number sequence that will be used to number intent letters.</span></span>

## <a name="create-an-intent-letter"></a><span data-ttu-id="a9514-125">Creare una lettera di intento</span><span class="sxs-lookup"><span data-stu-id="a9514-125">Create an intent letter</span></span>

<span data-ttu-id="a9514-126">Seguire questi passaggi per creare una lettera di intento per un cliente selezionato.</span><span class="sxs-lookup"><span data-stu-id="a9514-126">Follow these steps to create an intent letter for a selected customer.</span></span>

1. <span data-ttu-id="a9514-127">Selezionare **Contabilità clienti** \> **Clienti** \> **Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="a9514-127">Go to **Accounts receivable** \> **Customers** \> **All customers**.</span></span>
2. <span data-ttu-id="a9514-128">Selezionare un cliente e quindi, nel riquadro azioni, nella scheda **Vendi**, nel gruppo **Impostazione** selezionare **Imposta** \> **Lettere di intento**.</span><span class="sxs-lookup"><span data-stu-id="a9514-128">Select a customer, and then, on the Action Pane, on the **Sell** tab, in the **Setup** group, select **Setup** \> **Intent letters**.</span></span>
3. <span data-ttu-id="a9514-129">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a9514-129">Select **New**.</span></span>
4. <span data-ttu-id="a9514-130">Immettere i dati per la nuova lettera di intento.</span><span class="sxs-lookup"><span data-stu-id="a9514-130">Enter the data for the new intent letter.</span></span>

<span data-ttu-id="a9514-131">In alternativa, puoi creare una lettera di intento per qualsiasi cliente applicabile selezionando **Contabilità clienti** \> **Lettere di intento** \> **Lettere di intento**.</span><span class="sxs-lookup"><span data-stu-id="a9514-131">Alternatively, you can create an intent letter for any applicable customer by going to **Accounts receivable** \> **Intent letters** \> **Intent letters**.</span></span>

<span data-ttu-id="a9514-132">Le seguenti azioni sono disponibili per lettere di intento esistenti:</span><span class="sxs-lookup"><span data-stu-id="a9514-132">The following actions are available for existing intent letters:</span></span>

- <span data-ttu-id="a9514-133">**Chiudi lettera di intento** - Chiude una lettera di intento aperta.</span><span class="sxs-lookup"><span data-stu-id="a9514-133">**Close intent letter** – Close an open intent letter.</span></span>
- <span data-ttu-id="a9514-134">**Annulla lettera di intento** - Annulla una lettera di intento.</span><span class="sxs-lookup"><span data-stu-id="a9514-134">**Cancel intent letter** – Cancel an intent letter.</span></span> <span data-ttu-id="a9514-135">È necessario specificare il motivo dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="a9514-135">This operation requires a reason for cancellation.</span></span>
- <span data-ttu-id="a9514-136">**Aggiorna ordini cliente** - Aggiorna gli ordini cliente applicabili con riferimento a una lettera di intento.</span><span class="sxs-lookup"><span data-stu-id="a9514-136">**Update sales orders** – Update existing applicable sales orders with the reference to an intent letter.</span></span>
- <span data-ttu-id="a9514-137">**Apri lettera di intento** - Apre una lettera di intento chiusa.</span><span class="sxs-lookup"><span data-stu-id="a9514-137">**Open intent letter** – Open an intent letter that was closed.</span></span>
- <span data-ttu-id="a9514-138">**IVA registrata** - Mostra le transazioni IVA relative alla lettera di intento selezionata.</span><span class="sxs-lookup"><span data-stu-id="a9514-138">**Posted sales tax** – Show the sales tax transactions that are related to the selected intent letter.</span></span>

## <a name="using-intent-letters"></a><span data-ttu-id="a9514-139">Utilizzare lettere di intento</span><span class="sxs-lookup"><span data-stu-id="a9514-139">Using intent letters</span></span>

<span data-ttu-id="a9514-140">Quando si crea un ordine cliente o una fattura a testo libero per un cliente classificato come esportatore usuale, se la data di creazione è nel periodo di validità della lettera di intento, il valore **Fascia IVA esportatori abituali** viene utilizzato nell'ordine o nella fattura.</span><span class="sxs-lookup"><span data-stu-id="a9514-140">When you create a sales order or a free text invoice for a customer who is categorized as a usual exporter, if the creation date is in the validity period of the intent letter, the **Usual exporter sales tax group** value is used in the order or invoice.</span></span> <span data-ttu-id="a9514-141">Inoltre, il numero della lettera di intento viene immesso se l'opzione **Assegnazione automatica lettera di intento** è impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a9514-141">Additionally, the intent letter number is entered if the **Automatic intent letter assignment** option is set to **Yes**.</span></span>

![Nuovo ordine cliente](media/emea-ita-exil-intent-new-order.jpg)

<span data-ttu-id="a9514-143">L'importo della transazione fattura sarà soggetto al calcolo dell'IVA solo se supera l'importo della lettera di intento.</span><span class="sxs-lookup"><span data-stu-id="a9514-143">The amount of the invoice transaction will be subject to sales tax calculation only if it exceeds the amount of the intent letter.</span></span>

<span data-ttu-id="a9514-144">I dettagli della lettera di intento saranno inclusi anche in un layout stampabile della fattura.</span><span class="sxs-lookup"><span data-stu-id="a9514-144">The details of the intent letter will be also included in a printable layout of the invoice.</span></span>

![Stampa fattura](media/emea-ita-exil-intent-inv-print.jpg)
