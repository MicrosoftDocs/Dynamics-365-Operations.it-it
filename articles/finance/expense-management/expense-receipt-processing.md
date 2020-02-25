---
title: Elaborazione delle ricevute spese
description: Questo argomento fornisce informazioni sull'elaborazione OCR (riconoscimento ottico dei caratteri) per le ricevute. Questa funzionalità è progettata per migliorare l'esperienza utente quando vengono create note spese in Microsoft Dynamics 365 Finance.
author: stevensporen
manager: AnnBe
ms.date: 11/20/2019
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
ms.openlocfilehash: 1ead9039de63e2cf4f3a7faddd1702b9614d7f99
ms.sourcegitcommit: 6aceca43c53c4dde46954c0b6b855d488eb44ed2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027905"
---
# <a name="public-preview-expense-receipt-processing"></a><span data-ttu-id="00f00-104">Anteprima pubblica: elaborazione delle ricevute spese</span><span class="sxs-lookup"><span data-stu-id="00f00-104">Public Preview: Expense receipt processing</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


<span data-ttu-id="00f00-105">L'inserimento delle spese è stata migliorato con l'introduzione dell'elaborazione OCR (riconoscimento ottico dei caratteri) per le ricevute.</span><span class="sxs-lookup"><span data-stu-id="00f00-105">Expense entry has been enhanced through the introduction of optical character recognition (OCR) processing for receipts.</span></span> <span data-ttu-id="00f00-106">Questa funzionalità è progettata per migliorare l'esperienza utente quando vengono create note spese.</span><span class="sxs-lookup"><span data-stu-id="00f00-106">This feature is designed to improve the user experience when expense reports are created.</span></span>

## <a name="key-features"></a><span data-ttu-id="00f00-107">Funzionalità principali</span><span class="sxs-lookup"><span data-stu-id="00f00-107">Key features</span></span>

- <span data-ttu-id="00f00-108">Il nome del commerciante, la data e l'importo totale vengono estratti dalle ricevute.</span><span class="sxs-lookup"><span data-stu-id="00f00-108">The merchant name, date, and total amount are extracted from receipts.</span></span>
- <span data-ttu-id="00f00-109">La funzione tenta di associare le ricevute non collegate alle transazioni di spesa non collegate.</span><span class="sxs-lookup"><span data-stu-id="00f00-109">The feature tries to match unattached receipts to unattached expense transactions.</span></span>
- <span data-ttu-id="00f00-110">Gli utenti possono creare transazioni di spesa inserite manualmente dalle ricevute.</span><span class="sxs-lookup"><span data-stu-id="00f00-110">Users can create manually entered expense transactions from receipts.</span></span>

## <a name="usage-examples"></a><span data-ttu-id="00f00-111">Esempi di utilizzo</span><span class="sxs-lookup"><span data-stu-id="00f00-111">Usage examples</span></span>

- <span data-ttu-id="00f00-112">**Collegare automaticamente le ricevute che includono transazioni con carta di credito quando viene creata una nota spese.**</span><span class="sxs-lookup"><span data-stu-id="00f00-112">**Automatically attach receipts that include credit card transactions when an expense report is created.**</span></span>

    1. <span data-ttu-id="00f00-113">Aprire l'area di lavoro **Gestione spese**.</span><span class="sxs-lookup"><span data-stu-id="00f00-113">Open the **Expense management** workspace.</span></span>
    2. <span data-ttu-id="00f00-114">Nella scheda **Ricevute**, verificare l'esistenza di ricevute non collegate.</span><span class="sxs-lookup"><span data-stu-id="00f00-114">On the **Receipts** tab, verify that unattached receipts exist.</span></span> <span data-ttu-id="00f00-115">È anche possibile caricare ricevute nella scheda **Ricevute**.</span><span class="sxs-lookup"><span data-stu-id="00f00-115">You can also upload receipts on the **Receipts** tab.</span></span>
    3. <span data-ttu-id="00f00-116">Nella scheda **Spese**, verificare l'esistenza di spese non collegate.</span><span class="sxs-lookup"><span data-stu-id="00f00-116">On the **Expenses** tab, verify that unattached expenses exist.</span></span> <span data-ttu-id="00f00-117">In genere, l'amministratore spese importa queste spese dal fornitore della carta di credito.</span><span class="sxs-lookup"><span data-stu-id="00f00-117">Typically, the expense administrator imports these expenses from the credit card provider.</span></span>
    4. <span data-ttu-id="00f00-118">Selezionare **Nuova nota spese**.</span><span class="sxs-lookup"><span data-stu-id="00f00-118">Select **New expense report**.</span></span> <span data-ttu-id="00f00-119">Si noti che ora è possibile includere spese e ricevute quando si crea una nota spese.</span><span class="sxs-lookup"><span data-stu-id="00f00-119">Notice that you can include expenses, and receipts, now as well, when you create an expense report.</span></span> <span data-ttu-id="00f00-120">Se si aggiungono le spese e ricevute, viene attivata l'associazione automatica delle ricevute con le spese.</span><span class="sxs-lookup"><span data-stu-id="00f00-120">If you add both expenses and receipts, automatic matching of the receipts against the expenses is triggered.</span></span>

- <span data-ttu-id="00f00-121">**Creare una spesa o associare una spesa di una ricevuta.**</span><span class="sxs-lookup"><span data-stu-id="00f00-121">**Create an expense, or match an expense from a receipt.**</span></span>

    1. <span data-ttu-id="00f00-122">In una nota spese, nella scheda **Ricevute**, collegare una ricevuta selezionando **Aggiungi ricevute**.</span><span class="sxs-lookup"><span data-stu-id="00f00-122">On an expense report, on the **Receipts** tab, attach a receipt by selecting **Add receipts**.</span></span>
    2. <span data-ttu-id="00f00-123">Sotto l'immagine della ricevuta caricata, notare le opzioni **Crea** e **Associa**.</span><span class="sxs-lookup"><span data-stu-id="00f00-123">Under the uploaded image of the receipt, notice the **Create** and **Match** options.</span></span>

        - <span data-ttu-id="00f00-124">Selezionare **Crea** per creare una transazione di spesa immessa manualmente e immettere i valori estratti dalla ricevuta.</span><span class="sxs-lookup"><span data-stu-id="00f00-124">Select **Create** to create a manually entered expense transaction and fill in the values that are extracted from the receipt.</span></span>
        - <span data-ttu-id="00f00-125">Se si seleziona **Associa**, il sistema tenta di associare una spesa esistente alla ricevuta.</span><span class="sxs-lookup"><span data-stu-id="00f00-125">If you select **Match**, the system tries to match an existing expense to the receipt.</span></span>

## <a name="installation"></a><span data-ttu-id="00f00-126">Installazione</span><span class="sxs-lookup"><span data-stu-id="00f00-126">Installation</span></span>

<span data-ttu-id="00f00-127">Questa funzionalità viene utilizzata con la funzionalità **Note spese rinnovate** per semplificare l'esperienza di spesa.</span><span class="sxs-lookup"><span data-stu-id="00f00-127">This feature works in combination with the **Expense reports re-imagined** feature to help simplify the expense experience.</span></span>

<span data-ttu-id="00f00-128">Per utilizzare queste funzionalità di spesa avanzate, installare il componente aggiuntivo Servizio gestione spese per Microsoft Dynamics 365 Finance e attivare le funzionalità nella propria istanza.</span><span class="sxs-lookup"><span data-stu-id="00f00-128">To use these advanced expense capabilities, install the Expense Management Service add-in for Microsoft Dynamics 365 Finance, and turn on the features in your instance.</span></span> <span data-ttu-id="00f00-129">È possibile accedere al componente aggiuntivo dal progetto in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="00f00-129">You can access the add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="00f00-130">Accedere a LCS e aprire l'ambiente desiderato.</span><span class="sxs-lookup"><span data-stu-id="00f00-130">Sign in to LCS, and open the desired environment.</span></span>
2. <span data-ttu-id="00f00-131">Andare a **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="00f00-131">Go to **Full details**.</span></span>
3. <span data-ttu-id="00f00-132">Selezionare **Gestisci** oppure scorrere verso il basso la scheda dettaglio **Componenti aggiuntivi dell'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="00f00-132">Select **Maintain**, or scroll down to the **Environment add-ins** FastTab.</span></span>
4. <span data-ttu-id="00f00-133">Selezionare **Installare un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="00f00-133">Select **Install a new add-in**.</span></span>
5. <span data-ttu-id="00f00-134">Selezionare **Servizio gestione spese**.</span><span class="sxs-lookup"><span data-stu-id="00f00-134">Select **Expense Management Service**.</span></span>
6. <span data-ttu-id="00f00-135">Seguire la guida all'installazione e accettare le condizioni.</span><span class="sxs-lookup"><span data-stu-id="00f00-135">Follow the installation guide, and agree to the terms and conditions.</span></span>
7. <span data-ttu-id="00f00-136">Selezionare **Installa**.</span><span class="sxs-lookup"><span data-stu-id="00f00-136">Select **Install**.</span></span>

<span data-ttu-id="00f00-137">Nell'area di lavoro **Gestione funzionalità**, attivare le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="00f00-137">In the **Feature management** workspace, turn on the following features:</span></span>

- <span data-ttu-id="00f00-138">Note spese rinnovate</span><span class="sxs-lookup"><span data-stu-id="00f00-138">Expense reports re-imagined</span></span>
- <span data-ttu-id="00f00-139">Esegui la corrispondenza automatica e crea le spese dalla ricevuta</span><span class="sxs-lookup"><span data-stu-id="00f00-139">Auto-match and create expense from receipt</span></span>

<span data-ttu-id="00f00-140">Quando vengono attivate questa funzionalità, si verificano le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="00f00-140">When you turn on these features the following actions occur:</span></span>

- <span data-ttu-id="00f00-141">L'area di lavoro **Gestione spese** esistente viene sostituita con la nuova area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="00f00-141">The existing **Expense management** workspace is replaced with the new workspace.</span></span>
- <span data-ttu-id="00f00-142">Viene aggiunta una nuova voce di menu per la visibilità del campo delle spese.</span><span class="sxs-lookup"><span data-stu-id="00f00-142">A new menu item for expense field visibility is added.</span></span>
- <span data-ttu-id="00f00-143">È sempre possibile aprire la pagina **Note spese** precedente selezionando **Gestione spese > Spese personali > Note spese**.</span><span class="sxs-lookup"><span data-stu-id="00f00-143">You can still open the former **Expense reports** page by going to **Expense management > My expenses > Expense reports**.</span></span>
- <span data-ttu-id="00f00-144">I flussi di lavoro e le eventuali approvazioni portano ancora alla pagina delle note spese esistente.</span><span class="sxs-lookup"><span data-stu-id="00f00-144">Workflows and any approvals still take you to the existing expense reports page.</span></span>
- <span data-ttu-id="00f00-145">Le ricevute verranno elaborate tramite Microsoft Azure Cognitive Services e i metadati verranno estratti e aggiunti.</span><span class="sxs-lookup"><span data-stu-id="00f00-145">Receipts will be processed through Microsoft Azure Cognitive Services, and metadata will be extracted and added.</span></span>
- <span data-ttu-id="00f00-146">Viene aggiunta un'opzione che consente di creare una nota spese che include le ricevute non collegate associate.</span><span class="sxs-lookup"><span data-stu-id="00f00-146">An option is added that lets you create an expense report that includes matched unattached receipts.</span></span>
- <span data-ttu-id="00f00-147">Un'opzione che viene aggiunta alle note spese consente di creare una riga spese da una ricevuta o tenta di associare una ricevuta esistente a una riga spese esistente.</span><span class="sxs-lookup"><span data-stu-id="00f00-147">An option that is added to expense reports lets you create an expense line from a receipt, or attempts to match an existing receipt to an existing expense line.</span></span>

<span data-ttu-id="00f00-148">Per ulteriori informazioni sulla funzionalità Note spese rinnovate, vedere [Note spese rinnovate](ExpenseWorkspaceNew.md).</span><span class="sxs-lookup"><span data-stu-id="00f00-148">For more information about the Expense reports re-imagined feature, see [Expense reports reimagined](ExpenseWorkspaceNew.md).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="00f00-149">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="00f00-149">Frequently asked questions</span></span>

<span data-ttu-id="00f00-150">**Microsoft utilizza i dati personali per i propri modelli?**</span><span class="sxs-lookup"><span data-stu-id="00f00-150">**Does Microsoft use my data for its models?**</span></span>

<span data-ttu-id="00f00-151">No, Microsoft ha creato un modello generale di machine learning per il proprio servizio di elaborazione delle ricevute.</span><span class="sxs-lookup"><span data-stu-id="00f00-151">No, Microsoft has built a general machine learning model for its receipt processing service.</span></span> <span data-ttu-id="00f00-152">Questo modello non si basa sulle ricevute caricate.</span><span class="sxs-lookup"><span data-stu-id="00f00-152">This model isn't based on the receipts that you upload.</span></span>

<span data-ttu-id="00f00-153">**Dove è disponibile e viene elaborata questa funzione?**</span><span class="sxs-lookup"><span data-stu-id="00f00-153">**Where is this feature available and processed?**</span></span>

<span data-ttu-id="00f00-154">Attualmente negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="00f00-154">Currently, the United States is supported.</span></span>

<span data-ttu-id="00f00-155">**Dove vanno a finire le ricevute?**</span><span class="sxs-lookup"><span data-stu-id="00f00-155">**Where do my receipts go?**</span></span>

<span data-ttu-id="00f00-156">Finance contatterà i servizi cognitivi per estrarre i dati del campo.</span><span class="sxs-lookup"><span data-stu-id="00f00-156">Finance will contact Cognitive Services to extract the field data.</span></span> <span data-ttu-id="00f00-157">I servizi cognitivi conserveranno una copia della ricevuta per un massimo di 24 ore durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="00f00-157">Cognitive Services will retain a copy of your receipt for up to 24 hours while processing occurs.</span></span> <span data-ttu-id="00f00-158">Al termine dell'elaborazione, i servizi cognitivi rimuoveranno la ricevuta.</span><span class="sxs-lookup"><span data-stu-id="00f00-158">After processing is completed, Cognitive Services will remove the receipt.</span></span> <span data-ttu-id="00f00-159">Le ricevute sono ancora archiviate in Finance.</span><span class="sxs-lookup"><span data-stu-id="00f00-159">Receipts are still stored in Finance.</span></span>

<span data-ttu-id="00f00-160">Per ulteriori informazioni, vedere [Abilitare la comprensione delle ricevute con la nuova funzionalità di Form Recognizer](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).</span><span class="sxs-lookup"><span data-stu-id="00f00-160">For more information, see [Enable receipt understanding with Form Recognizer's new capability](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).</span></span>
