---
title: Creare e applicare termini di ritenuta per pagamenti fornitore
description: In questo argomento vengono fornite informazioni sull'impostazione e la gestione dei termini di ritenuta per pagamenti fornitore.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410237"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a><span data-ttu-id="7afe3-103">Creare e applicare termini di ritenuta per pagamenti fornitore</span><span class="sxs-lookup"><span data-stu-id="7afe3-103">Create and apply vendor payment retention terms</span></span>

[!include [banner](../includes/banner.md)] 

<span data-ttu-id="7afe3-104">L'impostazione dei termini di ritenuta per pagamenti fornitore per un progetto è utile quando l'organizzazione desidera trattenere una parte dei pagamenti effettuati a un fornitore.</span><span class="sxs-lookup"><span data-stu-id="7afe3-104">Setting up vendor payment retention terms for a project is useful when your organization wants to retain part of the payments made to a vendor.</span></span> <span data-ttu-id="7afe3-105">Ad esempio, nel caso in cui si desidera trattenere il pagamento a un fornitore fino a quando i prodotti consegnati soddisfano le proprie aspettative.</span><span class="sxs-lookup"><span data-stu-id="7afe3-105">For example, when you want to hold payment to a vendor until the products delivered meet your expectations.</span></span> <span data-ttu-id="7afe3-106">I termini di ritenuta per pagamenti fornitore possono essere specificati durante la negoziazione di un contratto fornitore.</span><span class="sxs-lookup"><span data-stu-id="7afe3-106">Vendor payment retention terms can be specified when you negotiate a vendor contract.</span></span>

## <a name="create-vendor-payment-retention-terms"></a><span data-ttu-id="7afe3-107">Creare termini di ritenuta per pagamenti fornitore</span><span class="sxs-lookup"><span data-stu-id="7afe3-107">Create vendor payment retention terms</span></span>

<span data-ttu-id="7afe3-108">È possibile immettere la percentuale di ritenuta per un pagamento fornitore e la percentuale degli importi di ritenute precedenti da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="7afe3-108">You can enter the percentage of vendor payment for retention and the percentage of the previously retained amounts to be released.</span></span> <span data-ttu-id="7afe3-109">Gli importi vengono automaticamente considerati come ritenuta nelle fatture fornitore fino al raggiungimento dello stato di completamento specificato per il contratto.</span><span class="sxs-lookup"><span data-stu-id="7afe3-109">Amounts are automatically retained on vendor invoices until the contract reaches the specified state of completion.</span></span> <span data-ttu-id="7afe3-110">Dopo aver impostato i termini di ritenuta, è possibile applicarli a qualsiasi progetto per quel fornitore.</span><span class="sxs-lookup"><span data-stu-id="7afe3-110">After you set up the retention terms, you can apply them to any project for that vendor.</span></span>

<span data-ttu-id="7afe3-111">Utilizzare i passaggi seguenti per impostare e gestire i termini di ritenuta per pagamenti fornitori.</span><span class="sxs-lookup"><span data-stu-id="7afe3-111">Use the following steps to set up and maintain retention terms for vendor payments.</span></span> 

1. <span data-ttu-id="7afe3-112">Andare a **Gestione progetti e contabilità** > **Ritenuta** > **Termini ritenuta pagamento fornitore**.</span><span class="sxs-lookup"><span data-stu-id="7afe3-112">Go to **Project management and accounting** > **Retention** > **Vendor payment retention terms**.</span></span>
2. <span data-ttu-id="7afe3-113">Selezionare **Nuovo** per aggiungere termini di ritenuta fornitore.</span><span class="sxs-lookup"><span data-stu-id="7afe3-113">Select **New** to add a new vendor retention term.</span></span> <span data-ttu-id="7afe3-114">Viene automaticamente immesso il valore **ID regola** per il nuovo termine.</span><span class="sxs-lookup"><span data-stu-id="7afe3-114">The **Rule ID** value for the new term is automatically entered.</span></span> 
3. <span data-ttu-id="7afe3-115">Immettere una breve descrizione nel campo **Descrizione** e nella Scheda dettaglio **Termini**, selezionare **Aggiungi riga** per inserire i seguenti valori relativi ai termini:</span><span class="sxs-lookup"><span data-stu-id="7afe3-115">Enter a brief description in the **Description** field, and on the **Terms** FastTab, select **Add line** to enter term values for the following:</span></span>

   - <span data-ttu-id="7afe3-116">**Percentuale di unità consegnate**: immettere una percentuale di completamento per i termini.</span><span class="sxs-lookup"><span data-stu-id="7afe3-116">**Percentage of units delivered**: Enter a percentage of completion for the term.</span></span> <span data-ttu-id="7afe3-117">Gli importi vengono automaticamente trattenuti nelle fatture fornitore fino a quando la fase di completamento del progetto non è uguale alla percentuale specificata.</span><span class="sxs-lookup"><span data-stu-id="7afe3-117">Amounts are automatically retained on vendor invoices until the project stage of completion is equal to the specified percentage.</span></span> <span data-ttu-id="7afe3-118">Ad esempio, se viene immesso il valore 50,00, gli importi vengono trattenuti finché il progetto non viene completato al 50%.</span><span class="sxs-lookup"><span data-stu-id="7afe3-118">For example, if you enter 50.00, amounts are retained until the project is 50 percent completed.</span></span>
   - <span data-ttu-id="7afe3-119">**Percentuale da trattenere**: immettere una percentuale dell'importo della fattura fornitore da trattenere.</span><span class="sxs-lookup"><span data-stu-id="7afe3-119">**Percentage to retain**: Enter a percentage of the vendor invoice amount to be retained.</span></span> <span data-ttu-id="7afe3-120">Ad esempio, se si immette 10,00, viene trattenuto il 10% dell'importo in una fattura fornitore finché il progetto non raggiunge la percentuale di completamento impostata nel campo **Percentuale di unità consegnate**.</span><span class="sxs-lookup"><span data-stu-id="7afe3-120">For example, if you enter 10.00, then 10 percent of the amount on a vendor invoice is retained until the project reaches the percentage of completion as set in the **Percentage of units delivered field**.</span></span>
   - <span data-ttu-id="7afe3-121">**Percentuale da rilasciare**: selezionare **Aggiungi riga** per immettere una percentuale di qualsiasi importo di ritenuta precedente da rilasciare al raggiungimento del livello di completamento selezionato del progetto.</span><span class="sxs-lookup"><span data-stu-id="7afe3-121">**Percentage to release**: Select **Add line** to enter a percentage of any previously retained amounts to be released for the selected level of project completion.</span></span>

> [!NOTE]
> <span data-ttu-id="7afe3-122">Se vi sono più punti cardine per diversi livelli di completamento del progetto, immettere una riga di termini di ritenuta fornitore separata per ogni regola di ritenuta.</span><span class="sxs-lookup"><span data-stu-id="7afe3-122">If you have more than one milestone for different levels of project completion, enter a separate vendor retention term line for each retention rule.</span></span> <span data-ttu-id="7afe3-123">In ogni riga è possibile specificare una percentuale di ritenuta differente e una percentuale di rilascio differente per ogni livello specificato di completamento del progetto.</span><span class="sxs-lookup"><span data-stu-id="7afe3-123">Each line can specify a different retention percentage and a different release percentage for each designated level of project completion.</span></span>

<span data-ttu-id="7afe3-124">Dopo la creazione dei termini di ritenuta fornitore per un fornitore, è possibile applicarli a qualsiasi progetto.</span><span class="sxs-lookup"><span data-stu-id="7afe3-124">After you create vendor retention terms for a vendor, you can apply the terms to a project.</span></span>

## <a name="apply-vendor-retention-terms-to-a-project"></a><span data-ttu-id="7afe3-125">Applicare i termini di ritenuta fornitore a un progetto</span><span class="sxs-lookup"><span data-stu-id="7afe3-125">Apply vendor retention terms to a project</span></span>

1. <span data-ttu-id="7afe3-126">Passare a **Gestione progetti e contabilità** > **Progetti** > **Tutti i progetti** e aprire il progetto dall'elenco dei progetti.</span><span class="sxs-lookup"><span data-stu-id="7afe3-126">Go to **Project management and accounting** > **Projects** > **All projects** and open a project from the project list page.</span></span>
2. <span data-ttu-id="7afe3-127">Nella Scheda dettaglio **Contratti fornitore** fare clic su **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="7afe3-127">On the **Vendor agreements** FastTab, select **Add line**.</span></span>
3. <span data-ttu-id="7afe3-128">Nel campo **Codice conto** selezionare una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="7afe3-128">In the **Account code field**, select one of the following options:</span></span> 

   - <span data-ttu-id="7afe3-129">**Tabella**: i termini di ritenuta fornitore vengono applicati a un unico venditore.</span><span class="sxs-lookup"><span data-stu-id="7afe3-129">**Table**: The vendor retention terms apply to a single vendor.</span></span>
   - <span data-ttu-id="7afe3-130">**Gruppo**: i termini di ritenuta fornitore vengono applicati a tutti i fornitori in un gruppo di fornitori.</span><span class="sxs-lookup"><span data-stu-id="7afe3-130">**Group**: The vendor retention terms apply to all vendors in a vendor group.</span></span>
   - <span data-ttu-id="7afe3-131">**Tutti**: i termini di ritenuta fornitore vengono applicati a tutti i fornitori.</span><span class="sxs-lookup"><span data-stu-id="7afe3-131">**All**: The vendor retention terms apply to all vendors.</span></span>

4. <span data-ttu-id="7afe3-132">Nel campo **Fornitore/gruppo fornitori** selezionare il fornitore o il gruppo di fornitori a cui sono applicabili i termini di ritenuta fornitore.</span><span class="sxs-lookup"><span data-stu-id="7afe3-132">In the **Vendor/Vendor group field**, select the vendor or vendor group to which the vendor retention terms apply.</span></span> <span data-ttu-id="7afe3-133">Se è stata selezionata l'opzione **Tutti** nel passaggio precedente, questo campo non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="7afe3-133">If you selected **All** in the previous step, this field is unavailable.</span></span>
5. <span data-ttu-id="7afe3-134">Nel campo **Termini di ritenuta fornitore**, selezionare i termini di ritenuta creati nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="7afe3-134">In the **Vendor retention terms** field, select the retention terms that you created in the previous procedure.</span></span>
6. <span data-ttu-id="7afe3-135">Se nel progetto per il fornitore sono impostati anche i termini Retribuisci su retribuzione, immettere la percentuale di soglia per il progetto nel campo **Percentuale soglia opzione Retribuisci su retribuzione**.</span><span class="sxs-lookup"><span data-stu-id="7afe3-135">If the project also has pay-when-paid (PWP) terms set up for the vendor, enter the threshold percentage for the project in the **PWP threshold percentage** field.</span></span>

<span data-ttu-id="7afe3-136">I termini di ritenuta fornitore vengono inoltre visualizzati negli ordini fornitore creati per il fornitore.</span><span class="sxs-lookup"><span data-stu-id="7afe3-136">The vendor retention terms are also displayed on purchase orders that you create for the vendor.</span></span>
