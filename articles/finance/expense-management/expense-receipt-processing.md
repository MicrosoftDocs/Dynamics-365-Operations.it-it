---
title: Elaborazione delle ricevute spese
description: Questo argomento fornisce informazioni sull'elaborazione OCR (riconoscimento ottico dei caratteri) per le ricevute. Questa funzionalità è progettata per migliorare l'esperienza utente quando vengono create note spese in Microsoft Dynamics 365 Finance.
author: stsporen
manager: AnnBe
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: stsporen
ms.search.validFrom: 2019-11-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 31c08ea264e6caec3217f4b424275495f39123e3
ms.sourcegitcommit: 15c5ec742d648c5f3506d031a2ab6150dcbae348
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "3378233"
---
# <a name="expense-receipt-processing"></a><span data-ttu-id="c1f22-104">Elaborazione ricevuta spese</span><span class="sxs-lookup"><span data-stu-id="c1f22-104">Expense receipt processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1f22-105">L'inserimento delle spese è stata migliorato con l'introduzione dell'elaborazione OCR (riconoscimento ottico dei caratteri) per le ricevute.</span><span class="sxs-lookup"><span data-stu-id="c1f22-105">Expense entry has been enhanced through the introduction of optical character recognition (OCR) processing for receipts.</span></span> <span data-ttu-id="c1f22-106">Questa funzionalità è progettata per migliorare l'esperienza utente quando vengono create note spese.</span><span class="sxs-lookup"><span data-stu-id="c1f22-106">This feature is designed to improve the user experience when expense reports are created.</span></span>

## <a name="key-features"></a><span data-ttu-id="c1f22-107">Funzionalità principali</span><span class="sxs-lookup"><span data-stu-id="c1f22-107">Key features</span></span>

- <span data-ttu-id="c1f22-108">Il nome del commerciante, la data e l'importo totale vengono estratti dalle ricevute.</span><span class="sxs-lookup"><span data-stu-id="c1f22-108">The merchant name, date, and total amount are extracted from receipts.</span></span>
- <span data-ttu-id="c1f22-109">La funzione tenta di associare le ricevute non collegate alle transazioni di spesa non collegate.</span><span class="sxs-lookup"><span data-stu-id="c1f22-109">The feature tries to match unattached receipts to unattached expense transactions.</span></span>
- <span data-ttu-id="c1f22-110">Gli utenti possono creare transazioni di spesa inserite manualmente dalle ricevute.</span><span class="sxs-lookup"><span data-stu-id="c1f22-110">Users can create manually entered expense transactions from receipts.</span></span>

## <a name="usage-examples"></a><span data-ttu-id="c1f22-111">Esempi di utilizzo</span><span class="sxs-lookup"><span data-stu-id="c1f22-111">Usage examples</span></span>

<span data-ttu-id="c1f22-112">Per collegare automaticamente le ricevute che includono transazioni con carta di credito quando viene creata una nota spese, eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="c1f22-112">To automatically attach receipts that include credit card transactions when an expense report is created, do the following:</span></span>

  1. <span data-ttu-id="c1f22-113">Aprire l'area di lavoro **Gestione spese**.</span><span class="sxs-lookup"><span data-stu-id="c1f22-113">Open the **Expense management** workspace.</span></span>
  2. <span data-ttu-id="c1f22-114">Nella scheda **Ricevute**, verificare l'esistenza di ricevute non collegate.</span><span class="sxs-lookup"><span data-stu-id="c1f22-114">On the **Receipts** tab, verify that unattached receipts exist.</span></span> <span data-ttu-id="c1f22-115">È anche possibile caricare ricevute nella scheda **Ricevute**.</span><span class="sxs-lookup"><span data-stu-id="c1f22-115">You can also upload receipts on the **Receipts** tab.</span></span>
  3. <span data-ttu-id="c1f22-116">Nella scheda **Spese**, verificare l'esistenza di spese non collegate.</span><span class="sxs-lookup"><span data-stu-id="c1f22-116">On the **Expenses** tab, verify that unattached expenses exist.</span></span> <span data-ttu-id="c1f22-117">In genere, l'amministratore spese importa queste spese dal fornitore della carta di credito.</span><span class="sxs-lookup"><span data-stu-id="c1f22-117">Typically, the expense administrator imports these expenses from the credit card provider.</span></span>
  4. <span data-ttu-id="c1f22-118">Selezionare **Nuova nota spese**.</span><span class="sxs-lookup"><span data-stu-id="c1f22-118">Select **New expense report**.</span></span> <span data-ttu-id="c1f22-119">Si noti che ora è possibile includere spese e ricevute quando si crea una nota spese.</span><span class="sxs-lookup"><span data-stu-id="c1f22-119">Notice that you can include expenses, and receipts, now as well, when you create an expense report.</span></span> <span data-ttu-id="c1f22-120">Se si aggiungono le spese e ricevute, viene attivata l'associazione automatica delle ricevute con le spese.</span><span class="sxs-lookup"><span data-stu-id="c1f22-120">If you add both expenses and receipts, automatic matching of the receipts against the expenses is triggered.</span></span>

<span data-ttu-id="c1f22-121">Per creare una spesa o associare una spesa di una ricevuta, eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="c1f22-121">To create an expense, or match an expense from a receipt, do the following:</span></span>

  1. <span data-ttu-id="c1f22-122">In una nota spese, nella scheda **Ricevute**, collegare una ricevuta selezionando **Aggiungi ricevute**.</span><span class="sxs-lookup"><span data-stu-id="c1f22-122">On an expense report, on the **Receipts** tab, attach a receipt by selecting **Add receipts**.</span></span>
  2. <span data-ttu-id="c1f22-123">Sotto l'immagine della ricevuta caricata, notare le opzioni **Crea** e **Associa**.</span><span class="sxs-lookup"><span data-stu-id="c1f22-123">Under the uploaded image of the receipt, notice the **Create** and **Match** options.</span></span>

      - <span data-ttu-id="c1f22-124">Selezionare **Crea** per creare una transazione di spesa immessa manualmente e immettere i valori estratti dalla ricevuta.</span><span class="sxs-lookup"><span data-stu-id="c1f22-124">Select **Create** to create a manually entered expense transaction and fill in the values that are extracted from the receipt.</span></span>
      - <span data-ttu-id="c1f22-125">Se si seleziona **Associa**, il sistema tenta di associare una spesa esistente alla ricevuta.</span><span class="sxs-lookup"><span data-stu-id="c1f22-125">If you select **Match**, the system tries to match an existing expense to the receipt.</span></span>

## <a name="installation"></a><span data-ttu-id="c1f22-126">Installazione</span><span class="sxs-lookup"><span data-stu-id="c1f22-126">Installation</span></span>

<span data-ttu-id="c1f22-127">Questa funzionalità viene utilizzata con la funzionalità **Note spese rinnovate** per semplificare l'esperienza di spesa.</span><span class="sxs-lookup"><span data-stu-id="c1f22-127">This feature works in combination with the **Expense reports re-imagined** feature to help simplify the expense experience.</span></span> <span data-ttu-id="c1f22-128">Questa funzionalità è disponibile solo per ambienti di livello 2+, che sono Sandbox e Production.</span><span class="sxs-lookup"><span data-stu-id="c1f22-128">This feature is only available for Tier 2+ environments, which are Sandbox and Production.</span></span>

<span data-ttu-id="c1f22-129">Per utilizzare queste funzionalità di spesa avanzate, installare il componente aggiuntivo Servizio gestione spese per Microsoft Dynamics 365 Finance e attivare le funzionalità nella propria istanza.</span><span class="sxs-lookup"><span data-stu-id="c1f22-129">To use these advanced expense capabilities, install the Expense Management Service add-in for Microsoft Dynamics 365 Finance, and turn on the features in your instance.</span></span> <span data-ttu-id="c1f22-130">È possibile accedere al componente aggiuntivo dal progetto in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c1f22-130">You can access the add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="c1f22-131">Accedere a LCS e aprire l'ambiente desiderato.</span><span class="sxs-lookup"><span data-stu-id="c1f22-131">Sign in to LCS, and open the desired environment.</span></span>
2. <span data-ttu-id="c1f22-132">Andare a **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="c1f22-132">Go to **Full details**.</span></span>
3. <span data-ttu-id="c1f22-133">Selezionare **Gestisci** oppure scorrere verso il basso la scheda dettaglio **Componenti aggiuntivi dell'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="c1f22-133">Select **Maintain**, or scroll down to the **Environment add-ins** FastTab.</span></span>
4. <span data-ttu-id="c1f22-134">Selezionare **Installare un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="c1f22-134">Select **Install a new add-in**.</span></span>
5. <span data-ttu-id="c1f22-135">Selezionare **Servizio gestione spese**.</span><span class="sxs-lookup"><span data-stu-id="c1f22-135">Select **Expense Management Service**.</span></span>
6. <span data-ttu-id="c1f22-136">Seguire la guida all'installazione e accettare le condizioni.</span><span class="sxs-lookup"><span data-stu-id="c1f22-136">Follow the installation guide, and agree to the terms and conditions.</span></span>
7. <span data-ttu-id="c1f22-137">Selezionare **Installa**.</span><span class="sxs-lookup"><span data-stu-id="c1f22-137">Select **Install**.</span></span>

<span data-ttu-id="c1f22-138">Nell'area di lavoro **Gestione funzionalità**, attivare le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="c1f22-138">In the **Feature management** workspace, turn on the following features:</span></span>

- <span data-ttu-id="c1f22-139">Note spese rinnovate</span><span class="sxs-lookup"><span data-stu-id="c1f22-139">Expense reports re-imagined</span></span>
- <span data-ttu-id="c1f22-140">Esegui la corrispondenza automatica e crea le spese dalla ricevuta</span><span class="sxs-lookup"><span data-stu-id="c1f22-140">Auto-match and create expense from receipt</span></span>

<span data-ttu-id="c1f22-141">Quando vengono attivate questa funzionalità, si verificano le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="c1f22-141">When you turn on these features the following actions occur:</span></span>

- <span data-ttu-id="c1f22-142">L'area di lavoro **Gestione spese** esistente viene sostituita con la nuova area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c1f22-142">The existing **Expense management** workspace is replaced with the new workspace.</span></span>
- <span data-ttu-id="c1f22-143">Viene aggiunta una nuova voce di menu per la visibilità del campo delle spese.</span><span class="sxs-lookup"><span data-stu-id="c1f22-143">A new menu item for expense field visibility is added.</span></span>
- <span data-ttu-id="c1f22-144">È sempre possibile aprire la pagina **Note spese** precedente selezionando **Gestione spese > Spese personali > Note spese**.</span><span class="sxs-lookup"><span data-stu-id="c1f22-144">You can still open the former **Expense reports** page by going to **Expense management > My expenses > Expense reports**.</span></span>
- <span data-ttu-id="c1f22-145">I flussi di lavoro e le eventuali approvazioni portano ancora alla pagina delle note spese esistente.</span><span class="sxs-lookup"><span data-stu-id="c1f22-145">Workflows and any approvals still take you to the existing expense reports page.</span></span>
- <span data-ttu-id="c1f22-146">Le ricevute verranno elaborate tramite Microsoft Azure Cognitive Services e i metadati verranno estratti e aggiunti.</span><span class="sxs-lookup"><span data-stu-id="c1f22-146">Receipts will be processed through Microsoft Azure Cognitive Services, and metadata will be extracted and added.</span></span>
- <span data-ttu-id="c1f22-147">Viene aggiunta un'opzione che consente di creare una nota spese che include le ricevute non collegate associate.</span><span class="sxs-lookup"><span data-stu-id="c1f22-147">An option is added that lets you create an expense report that includes matched unattached receipts.</span></span>
- <span data-ttu-id="c1f22-148">Un'opzione che viene aggiunta alle note spese consente di creare una riga spese da una ricevuta o tenta di associare una ricevuta esistente a una riga spese esistente.</span><span class="sxs-lookup"><span data-stu-id="c1f22-148">An option that is added to expense reports lets you create an expense line from a receipt, or attempts to match an existing receipt to an existing expense line.</span></span>

<span data-ttu-id="c1f22-149">Per ulteriori informazioni sulla funzionalità Note spese rinnovate, vedere [Note spese rinnovate](ExpenseWorkspaceNew.md).</span><span class="sxs-lookup"><span data-stu-id="c1f22-149">For more information about the Expense reports re-imagined feature, see [Expense reports reimagined](ExpenseWorkspaceNew.md).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c1f22-150">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="c1f22-150">Frequently asked questions</span></span>

<span data-ttu-id="c1f22-151">**Microsoft utilizza i dati personali per i propri modelli?**</span><span class="sxs-lookup"><span data-stu-id="c1f22-151">**Does Microsoft use my data for its models?**</span></span>

<span data-ttu-id="c1f22-152">No, Microsoft ha creato un modello generale di machine learning per il proprio servizio di elaborazione delle ricevute.</span><span class="sxs-lookup"><span data-stu-id="c1f22-152">No, Microsoft has built a general machine learning model for its receipt processing service.</span></span> <span data-ttu-id="c1f22-153">Questo modello non si basa sulle ricevute caricate.</span><span class="sxs-lookup"><span data-stu-id="c1f22-153">This model isn't based on the receipts that you upload.</span></span>

<span data-ttu-id="c1f22-154">**Dove è disponibile e viene elaborata questa funzione?**</span><span class="sxs-lookup"><span data-stu-id="c1f22-154">**Where is this feature available and processed?**</span></span>

<span data-ttu-id="c1f22-155">Attualmente negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="c1f22-155">Currently, the United States is supported.</span></span>

<span data-ttu-id="c1f22-156">**Dove vanno a finire le ricevute?**</span><span class="sxs-lookup"><span data-stu-id="c1f22-156">**Where do my receipts go?**</span></span>

<span data-ttu-id="c1f22-157">Finance contatterà i servizi cognitivi per estrarre i dati del campo.</span><span class="sxs-lookup"><span data-stu-id="c1f22-157">Finance will contact Cognitive Services to extract the field data.</span></span> <span data-ttu-id="c1f22-158">I servizi cognitivi conserveranno una copia della ricevuta per un massimo di 24 ore durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="c1f22-158">Cognitive Services will retain a copy of your receipt for up to 24 hours while processing occurs.</span></span> <span data-ttu-id="c1f22-159">Al termine dell'elaborazione, i servizi cognitivi rimuoveranno la ricevuta.</span><span class="sxs-lookup"><span data-stu-id="c1f22-159">After processing is completed, Cognitive Services will remove the receipt.</span></span> <span data-ttu-id="c1f22-160">Le ricevute sono ancora archiviate in Finance.</span><span class="sxs-lookup"><span data-stu-id="c1f22-160">Receipts are still stored in Finance.</span></span>

<span data-ttu-id="c1f22-161">Per ulteriori informazioni, vedere [Abilitare la comprensione delle ricevute con la nuova funzionalità di Form Recognizer](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).</span><span class="sxs-lookup"><span data-stu-id="c1f22-161">For more information, see [Enable receipt understanding with Form Recognizer's new capability](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).</span></span>
