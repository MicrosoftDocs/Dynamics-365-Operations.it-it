---
title: Domande frequenti sulla creazione di report finanziari
description: In questo argomento vengono riportate le domande relative alla creazione di report finanziari poste da altri utenti.
author: jiwo
manager: tfehr
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2d49213ea18e09f04b026559bdca49fee1de0ef7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249307"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="7bede-103">Domande frequenti sulla creazione di report finanziari</span><span class="sxs-lookup"><span data-stu-id="7bede-103">Financial reporting FAQ</span></span> 

<span data-ttu-id="7bede-104">In questo argomento vengono riportate le domande relative alla creazione di report finanziari poste da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="7bede-104">This topic lists questions related to financial reporting that other users have had.</span></span> 


## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a><span data-ttu-id="7bede-105">Come si limita l'accesso a un report utilizzando la sicurezza dell'albero?</span><span class="sxs-lookup"><span data-stu-id="7bede-105">How do I restrict access to a report using Tree security?</span></span>

<span data-ttu-id="7bede-106">Scenario: la società dimostrativa USMF dispone di un report stato patrimoniale che non desidera rendere visibile a tutti gli utenti dei report finanziari in D365.</span><span class="sxs-lookup"><span data-stu-id="7bede-106">Scenario: The USMF demo company has a Balance sheet report that it doesn’t want all Financial reporting users to be able to view in D365.</span></span> <span data-ttu-id="7bede-107">Soluzione: è possibile utilizzare la sicurezza dell'albero per limitare l'accesso a un singolo report in modo che solo determinati utenti possano utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="7bede-107">Solution: You can utilize Tree security to restrict access to a single report so that only certain users can access the report.</span></span> 

1.  <span data-ttu-id="7bede-108">Accedere a Progettazione report dello strumento di creazione report finanziari</span><span class="sxs-lookup"><span data-stu-id="7bede-108">Log into Financial Reporter Report Designer</span></span>

2.  <span data-ttu-id="7bede-109">Creare una nuova definizione dell'albero (File | Nuovo | Definizione di albero) a.</span><span class="sxs-lookup"><span data-stu-id="7bede-109">Create a new Tree Definition (File | New | Tree Definition) a.</span></span>    <span data-ttu-id="7bede-110">Fare doppio clic sulla riga **Riepilogo** nella colonna **Sicurezza unità**.</span><span class="sxs-lookup"><span data-stu-id="7bede-110">Double-click the **Summary** line in the **Unit Security** column.</span></span>
  <span data-ttu-id="7bede-111">i.</span><span class="sxs-lookup"><span data-stu-id="7bede-111">i.</span></span>    <span data-ttu-id="7bede-112">Fare clic su Utenti e gruppi.</span><span class="sxs-lookup"><span data-stu-id="7bede-112">Click Users and Groups.</span></span>  
          <span data-ttu-id="7bede-113">1. Selezionare il gruppo o gli utenti che possono accedere a questo report.</span><span class="sxs-lookup"><span data-stu-id="7bede-113">1.    Select the User(s) or Group that would like to access this report.</span></span> 
          
<span data-ttu-id="7bede-114">[![Schermata dell'utente](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)</span><span class="sxs-lookup"><span data-stu-id="7bede-114">[![user screen](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)</span></span>

<span data-ttu-id="7bede-115">[![Schermata della sicurezza](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)</span><span class="sxs-lookup"><span data-stu-id="7bede-115">[![security screen](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)</span></span>

  <span data-ttu-id="7bede-116">b.</span><span class="sxs-lookup"><span data-stu-id="7bede-116">b.</span></span>    <span data-ttu-id="7bede-117">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7bede-117">Click **Save**.</span></span>
  
<span data-ttu-id="7bede-118">[![Pulsante salva](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)</span><span class="sxs-lookup"><span data-stu-id="7bede-118">[![save button](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)</span></span>

3.  <span data-ttu-id="7bede-119">Nella definizione del report, aggiungere la nuova definizione di albero</span><span class="sxs-lookup"><span data-stu-id="7bede-119">In your Report Definition add your new Tree Definition</span></span>

<span data-ttu-id="7bede-120">[![Modulo di definizione di albero](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)</span><span class="sxs-lookup"><span data-stu-id="7bede-120">[![tree definition form](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)</span></span>

<span data-ttu-id="7bede-121">A.</span><span class="sxs-lookup"><span data-stu-id="7bede-121">A.</span></span>  <span data-ttu-id="7bede-122">Nella definizione di albero, fare clic su Impostazioni e in "Selezione unità gerarchica" selezionare "Includi tutte le unità"</span><span class="sxs-lookup"><span data-stu-id="7bede-122">While in the Tree Definition click on Setting and under “Reporting unit selection” check “Include all units”</span></span>

<span data-ttu-id="7bede-123">[![Modulo di selezione dell'unità gerarchica](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)</span><span class="sxs-lookup"><span data-stu-id="7bede-123">[![reporting unit selection form](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)</span></span>

<span data-ttu-id="7bede-124">**Prima:** [![Screenshot della schermata prima](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)</span><span class="sxs-lookup"><span data-stu-id="7bede-124">**Before:** [![before screenshot](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)</span></span>

<span data-ttu-id="7bede-125">**Dopo:** [![Screenshot della schermata dopo](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)</span><span class="sxs-lookup"><span data-stu-id="7bede-125">**After:** [![after screenshot](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)</span></span>

<span data-ttu-id="7bede-126">Nota: il motivo del messaggio precedente è che l'utente non ha accesso al report dopo l'applicazione di Sicurezza unità</span><span class="sxs-lookup"><span data-stu-id="7bede-126">Note: Reason for the above message is my user does not have access to that report after applying Unit Security</span></span>



## <a name="how-do-i-determine-which-accounts-do-not-matching-my-balances-in-d365"></a><span data-ttu-id="7bede-127">Come si determina quali conti non corrispondono ai saldi in D365?</span><span class="sxs-lookup"><span data-stu-id="7bede-127">How do I determine which account(s) do not matching my balances in D365?</span></span>

<span data-ttu-id="7bede-128">Quando si dispone di un report che non corrisponde a quello che ci si aspetterebbe in D365, ecco alcuni passaggi che è possibile eseguire per identificare i conti e gli scostamenti.</span><span class="sxs-lookup"><span data-stu-id="7bede-128">When you have a report that doesn't match what you would expect in D365, here are some steps you could take to identify those accounts and the variances.</span></span> 

### <a name="in-financial-reporter-report-designer"></a><span data-ttu-id="7bede-129">In Progettazione report dello strumento di creazione report finanziari</span><span class="sxs-lookup"><span data-stu-id="7bede-129">In Financial Reporter Report Designer</span></span>

1.  <span data-ttu-id="7bede-130">Creare una nuova definizione di riga a.</span><span class="sxs-lookup"><span data-stu-id="7bede-130">Create a new Row Definition a.</span></span>    <span data-ttu-id="7bede-131">Fare clic su Modifica | Inserisci righe da dimensioni i.</span><span class="sxs-lookup"><span data-stu-id="7bede-131">Click Edit | Insert Rows from Dimensions i.</span></span>  <span data-ttu-id="7bede-132">Seleziona MainAccount [![Schermata della selezione di Conto principale_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)</span><span class="sxs-lookup"><span data-stu-id="7bede-132">Select MainAccount [![Select Main screen_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)</span></span>
    
    <span data-ttu-id="7bede-133">ii.</span><span class="sxs-lookup"><span data-stu-id="7bede-133">ii.</span></span> <span data-ttu-id="7bede-134">Fare clic su OK b.</span><span class="sxs-lookup"><span data-stu-id="7bede-134">Click Ok b.</span></span>    <span data-ttu-id="7bede-135">Salvare la definizione di riga</span><span class="sxs-lookup"><span data-stu-id="7bede-135">Save the Row Definition</span></span>

2.  <span data-ttu-id="7bede-136">Creare una nuova definizione di colonna     [![Creare una nuova definizione di colonna](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)</span><span class="sxs-lookup"><span data-stu-id="7bede-136">Create a new Column Definition     [![Create a new column definition](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)</span></span>

3.  <span data-ttu-id="7bede-137">Creare una nuova definizione di report a.</span><span class="sxs-lookup"><span data-stu-id="7bede-137">Create a new Report Definition a.</span></span>    <span data-ttu-id="7bede-138">Fare clic su Impostazioni e deselezionare [![Modulo Impostazioni](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)</span><span class="sxs-lookup"><span data-stu-id="7bede-138">Click Settings and uncheck [![Settings form](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)</span></span>
   
4.  <span data-ttu-id="7bede-139">Generare il report.</span><span class="sxs-lookup"><span data-stu-id="7bede-139">Generate the Report.</span></span> 

5.  <span data-ttu-id="7bede-140">Esportare il report in Excel.</span><span class="sxs-lookup"><span data-stu-id="7bede-140">Export the Report to Excel.</span></span>

### <a name="in-d365"></a><span data-ttu-id="7bede-141">In D365:</span><span class="sxs-lookup"><span data-stu-id="7bede-141">In D365:</span></span> 
1.  <span data-ttu-id="7bede-142">Fare clic su Contabilità generale | Richieste di informazioni e report | Bilancio di verifica a.</span><span class="sxs-lookup"><span data-stu-id="7bede-142">Click General Ledger | Inquiries and Reports | Trial Balance a.</span></span>    <span data-ttu-id="7bede-143">Parametri i.</span><span class="sxs-lookup"><span data-stu-id="7bede-143">Parameters i.</span></span>  <span data-ttu-id="7bede-144">Dal: inizio dell'anno fiscale ii.</span><span class="sxs-lookup"><span data-stu-id="7bede-144">From Date: Start of Fiscal Year ii.</span></span> <span data-ttu-id="7bede-145">Al: data per cui è stato generato il report iii.</span><span class="sxs-lookup"><span data-stu-id="7bede-145">To Date: Date you generated the report for iii.</span></span>    <span data-ttu-id="7bede-146">Set di dimensioni finanziarie "Set di conti principali" [![Modulo conto principale](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)</span><span class="sxs-lookup"><span data-stu-id="7bede-146">Financial Dimension Set “Main Account set” [![Main Account Form](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)</span></span>
      
  <span data-ttu-id="7bede-147">b.</span><span class="sxs-lookup"><span data-stu-id="7bede-147">b.</span></span>    <span data-ttu-id="7bede-148">Fare clic su Calcola</span><span class="sxs-lookup"><span data-stu-id="7bede-148">Click Calculate</span></span>

2.  <span data-ttu-id="7bede-149">Esportare il report in Excel</span><span class="sxs-lookup"><span data-stu-id="7bede-149">Export the report to Excel</span></span>

<span data-ttu-id="7bede-150">Ora si possono copiare i dati dal report di Excel della creazione di report finanziari e nel report D365 Bilancio di verifica e confrontare le colonne "Saldo finale".</span><span class="sxs-lookup"><span data-stu-id="7bede-150">You should now be able to copy the data from the FR Excel Report and to the D365 Trial Balance report and compare the “Closing Balance” columns.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]