---
title: Documenti di motivazione per la pianificazione del budget
description: "I documenti di motivazione forniscono una descrizione per chi richiede un budget per spiegare perché un budget specifico è necessario."
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2e711b14b202d477bd3f4bda09977fd33979fc94
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="budget-planning-justification-documents"></a><span data-ttu-id="620a5-103">Documenti di motivazione per la pianificazione del budget</span><span class="sxs-lookup"><span data-stu-id="620a5-103">Budget planning justification documents</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="620a5-104">I documenti di motivazione forniscono una descrizione per chi richiede un budget per spiegare perché un budget specifico è necessario.</span><span class="sxs-lookup"><span data-stu-id="620a5-104">Justification documents provide a narrative for those requesting a budget to explain why a specific budget is necessary.</span></span> 

<span data-ttu-id="620a5-105">Un modello di piano di budget viene creato dal responsabile budget in Microsoft Word e viene assegnato al processo di pianificazione del budget corrente.</span><span class="sxs-lookup"><span data-stu-id="620a5-105">A budget plan template is created by the budget manager in Microsoft Word and assigned to the current budget planning process.</span></span> <span data-ttu-id="620a5-106">I proprietari del budget potranno quindi aprire il modello e i dati verranno inseriti automaticamente in Word in base alla relativa richiesta di budget.</span><span class="sxs-lookup"><span data-stu-id="620a5-106">Budget owners can then open the template and have data automatically populated in Word based on their budget request.</span></span> <span data-ttu-id="620a5-107">I proprietari possono quindi aggiungere testo o dati aggiuntivi prima di salvare e allegare il proprio documento di motivazione personale al piano di budget.</span><span class="sxs-lookup"><span data-stu-id="620a5-107">They can then add additional text or data prior to saving and attaching their personalized justification document to their budget plan.</span></span>

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a><span data-ttu-id="620a5-108">Impostare il componente aggiuntivo di Microsoft Dynamics Office per Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="620a5-108">Set up Microsoft Dynamics Office Add-in for Microsoft Word</span></span>

1.  <span data-ttu-id="620a5-109">Aprire un nuovo documento di Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="620a5-109">Open a new Microsoft Word document.</span></span>
2.  <span data-ttu-id="620a5-110">Fare clic su **Inserisci** sulla barra multifunzione e fare clic su **Punto vendita**.</span><span class="sxs-lookup"><span data-stu-id="620a5-110">Click **Insert** on the ribbon, and click **Store**.</span></span>
3.  <span data-ttu-id="620a5-111">Ricerca di un componente aggiuntivo di Microsoft Dynamics Office e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="620a5-111">Search for Microsoft Dynamics Office Add-in and click **Add**.</span></span>
4.  <span data-ttu-id="620a5-112">In Word, nel riquadro destro, fare clic su **Aggiungi informazioni sul server**.</span><span class="sxs-lookup"><span data-stu-id="620a5-112">In Word, in the right pane, click **Add server information**.</span></span>
5.  <span data-ttu-id="620a5-113">Digitare o incollare l'URL del server e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="620a5-113">Type or paste the server URL and click **OK**.</span></span>

##### <a name="define-the-justification-template-in-microsoft-word"></a><span data-ttu-id="620a5-114">Definire il modello Motivazione in Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="620a5-114">Define the Justification template in Microsoft Word</span></span>

1.  <span data-ttu-id="620a5-115">Fare clic su **Progetto** nel componente aggiuntivo di Office di Microsoft Dynamics Office dopo aver effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="620a5-115">Click **Design** in the Microsoft Dynamics Office Add-in after you’ve logged in.</span></span>
2.  <span data-ttu-id="620a5-116">Per informazioni sull'intestazione, utilizzare il pulsante **Aggiungi campi**.</span><span class="sxs-lookup"><span data-stu-id="620a5-116">For header information, use the **Add fields** button.</span></span>
3.  <span data-ttu-id="620a5-117">Selezionare l'origine dati dell'entità di BudgetPlanJustification, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="620a5-117">Select the entity data source of BudgetPlanJustification, and click **Next**.</span></span> <span data-ttu-id="620a5-118">**Nota:** l'entità è necessaria per qualsiasi documento di motivazione.</span><span class="sxs-lookup"><span data-stu-id="620a5-118">**Note:** This entity is required for any justification document.</span></span> <span data-ttu-id="620a5-119">È possibile utilizzare altre entità ma il caricamento di nuovo su Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition avrà esito negativo se questa entità non verrà inclusa.</span><span class="sxs-lookup"><span data-stu-id="620a5-119">Other entities can be used but the upload back to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition will fail if this entity isn’t included.</span></span>
4.  <span data-ttu-id="620a5-120">Aggiungere i valori e le etichette BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter e DocumentNumber nel documento Word.</span><span class="sxs-lookup"><span data-stu-id="620a5-120">Add the BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter, and DocumentNumber labels and values in the Word document.</span></span> <span data-ttu-id="620a5-121">**Nota:** è possibile utilizzare le proprie etichette personalizzate anziché le etichette standard, se necessario.</span><span class="sxs-lookup"><span data-stu-id="620a5-121">**Note:** You can use your own custom labels, rather than the standard labels, if needed.</span></span>
5.  <span data-ttu-id="620a5-122">Fare clic su **Fine** per completare la sezione dell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="620a5-122">Click **Done** to complete the header section.</span></span>
6.  <span data-ttu-id="620a5-123">Per il dettaglio del livello di riga degli importi del piano di budget, fare clic su **Aggiungi tabella**.</span><span class="sxs-lookup"><span data-stu-id="620a5-123">For line level detail of budget plan amounts, click **Add table**.</span></span>
7.  <span data-ttu-id="620a5-124">Di nuovo, selezionare l'origine dati dell'entità di BudgetPlanJustification, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="620a5-124">Again, select the entity data source of BudgetPlanJustification, and click **Next**.</span></span>
8.  <span data-ttu-id="620a5-125">Aggiungere i campi per EffectiveDate, ScenarioName, AccountDisplayValue e AccountingCurrencyExpenseAmount.</span><span class="sxs-lookup"><span data-stu-id="620a5-125">Add fields for EffectiveDate, ScenarioName, AccountDisplayValue, and AccountingCurrencyExpenseAmount.</span></span> <span data-ttu-id="620a5-126">**Nota:** se è possibile aggiungere commenti all'interno di singole righe del piano di budget, questi possono essere aggiunti alla tabella corrispondente.</span><span class="sxs-lookup"><span data-stu-id="620a5-126">**Note:** If comments are available to add within individual budget plan lines, those can be added to the table here.</span></span>
9.  <span data-ttu-id="620a5-127">Aggiungere eventuali istruzioni aggiuntive da fornire all'utente finale ed eseguire eventuali formattazioni necessarie o modifiche allo stile del documento.</span><span class="sxs-lookup"><span data-stu-id="620a5-127">Add any additional instructions to provide to the end user, and perform any necessary formatting or styling to the document.</span></span>
10. <span data-ttu-id="620a5-128">Salvare il documento sul computer locale e chiudere il file prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="620a5-128">Save the document to your local computer and close the file before continuing.</span></span>

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a><span data-ttu-id="620a5-129">Configurare il processo di pianificazione del budget per utilizzare per il modello Motivazione</span><span class="sxs-lookup"><span data-stu-id="620a5-129">Set up the Budget planning process to use the Justification template</span></span>

1.  <span data-ttu-id="620a5-130">In Finance and Operations, passare a **Impostazione budget** &gt; **Impostazioni** &gt; **Pianificazione del budget** &gt; **Modelli documento di motivazione**.</span><span class="sxs-lookup"><span data-stu-id="620a5-130">In Finance and Operations, go to **Budgeting** &gt; **Setup** &gt; **Budget planning** &gt; **Justification document templates**.</span></span>
2.  <span data-ttu-id="620a5-131">Fare clic su **Nuovo** e individuare il documento di Microsoft Word appena creato.</span><span class="sxs-lookup"><span data-stu-id="620a5-131">Click **New** and browse to your newly created Microsoft Word document.</span></span>
3.  <span data-ttu-id="620a5-132">Immettere un nome di visualizzazione e una descrizione del modello.</span><span class="sxs-lookup"><span data-stu-id="620a5-132">Enter a template display name and description.</span></span> <span data-ttu-id="620a5-133">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="620a5-133">Click **OK**.</span></span>
4.  <span data-ttu-id="620a5-134">Accedere a **Impostazione budget** &gt; **Impostazioni** &gt; **Pianificazione** del **budget** &gt; **Processo di pianificazione del budget**.</span><span class="sxs-lookup"><span data-stu-id="620a5-134">Go to **Budgeting** &gt; **Setup** &gt; **Budget** **planning** &gt; **Budget planning process**.</span></span>
5.  <span data-ttu-id="620a5-135">Selezionare il processo in cui il modello di motivazione deve essere utilizzato e fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="620a5-135">Select the process where the justification template should be used, and click **Edit**.</span></span>
6.  <span data-ttu-id="620a5-136">Nel campo **Modello documento di motivazione**, selezionare il modello appropriato e salvare.</span><span class="sxs-lookup"><span data-stu-id="620a5-136">In the **Justification document template** field, select the appropriate template and save.</span></span>

##### <a name="edit-and-save-personalized-justification-documents"></a><span data-ttu-id="620a5-137">Modificare e salvare documenti di motivazione personalizzati</span><span class="sxs-lookup"><span data-stu-id="620a5-137">Edit and save personalized justification documents</span></span>

1.  <span data-ttu-id="620a5-138">In Finance and Operations, creare un nuovo piano di budget o aprire un piano di budget esistente.</span><span class="sxs-lookup"><span data-stu-id="620a5-138">In Finance and Operations, create a new budget plan or open an existing budget plan.</span></span>
2.  <span data-ttu-id="620a5-139">Dal menu a discesa **Motivazione**, selezionare **Crea nuova motivazione**.</span><span class="sxs-lookup"><span data-stu-id="620a5-139">In the **Justification** drop-down menu, select **Create new justification**.</span></span>
3.  <span data-ttu-id="620a5-140">Dopo aver inserito i dettagli, selezionare per caricare il documento personalizzato dal menu a discesa **Motivazione**.</span><span class="sxs-lookup"><span data-stu-id="620a5-140">After filling in the details, select to upload the personalized document from the **Justification** drop-down menu.</span></span>





