---
title: Domande frequenti sulla creazione di report finanziari
description: In questo argomento vengono riportate le domande relative alla creazione di report finanziari poste da altri utenti.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 023354b0e2973f63411bf81cbeb0344333c49112
ms.sourcegitcommit: d63e7e0593084a61362a6cad3937b1fd956c384f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923027"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="e2fda-103">Domande frequenti sulla creazione di report finanziari</span><span class="sxs-lookup"><span data-stu-id="e2fda-103">Financial reporting FAQ</span></span> 

<span data-ttu-id="e2fda-104">In questo argomento vengono fornite risposte alle domande frequenti sulla creazione di report finanziari.</span><span class="sxs-lookup"><span data-stu-id="e2fda-104">This topic provides answers to frequently asked questions about financial reporting.</span></span> 

## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a><span data-ttu-id="e2fda-105">Come si limita l'accesso a un report utilizzando la sicurezza dell'albero?</span><span class="sxs-lookup"><span data-stu-id="e2fda-105">How do I restrict access to a report using tree security?</span></span>

<span data-ttu-id="e2fda-106">L'esempio seguente mostra come limitare l'accesso a un report utilizzando la sicurezza dell'albero.</span><span class="sxs-lookup"><span data-stu-id="e2fda-106">The following example shows how to restrict access to a report using tree security.</span></span>

<span data-ttu-id="e2fda-107">La società dimostrativa USMF dispone di un report stato patrimoniale che non desidera rendere accessibile a tutti gli utenti dei report finanziari.</span><span class="sxs-lookup"><span data-stu-id="e2fda-107">The USMF demo company has a Balance sheet report that not all Financial reporting users should have access to.</span></span> <span data-ttu-id="e2fda-108">È possibile utilizzare la sicurezza dell'albero per limitare l'accesso a un singolo report in modo che solo determinati utenti possano utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="e2fda-108">To restrict access, you can use tree security to restrict access to a single report so that only certain users can access the report.</span></span> <span data-ttu-id="e2fda-109">Per limitare l'accesso, seguire questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="e2fda-109">Follow these steps to restrict access:</span></span> 

1. <span data-ttu-id="e2fda-110">Accedere a Financial Reporter Report Designer.</span><span class="sxs-lookup"><span data-stu-id="e2fda-110">Sign in to Financial Reporter Report Designer.</span></span>
2. <span data-ttu-id="e2fda-111">Creare una nuova definizione di albero.</span><span class="sxs-lookup"><span data-stu-id="e2fda-111">Create a new tree definition.</span></span> <span data-ttu-id="e2fda-112">Andare a **File> Nuovo> Definizione di albero**.</span><span class="sxs-lookup"><span data-stu-id="e2fda-112">Go to **File > New > Tree Definition**.</span></span>
3. <span data-ttu-id="e2fda-113">Fare doppio clic sulla riga **Riepilogo** nella colonna **Sicurezza unità**.</span><span class="sxs-lookup"><span data-stu-id="e2fda-113">Double-click the **Summary** line in the **Unit Security** column.</span></span>
4. <span data-ttu-id="e2fda-114">Selezionare **Utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="e2fda-114">Select **Users and Groups**.</span></span>  
5. <span data-ttu-id="e2fda-115">Selezionare gli utenti o i gruppi che devono accedere a questo report.</span><span class="sxs-lookup"><span data-stu-id="e2fda-115">Select the users or groups that need access to this report.</span></span> 
6. <span data-ttu-id="e2fda-116">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e2fda-116">Select **Save**.</span></span>
7. <span data-ttu-id="e2fda-117">Nella definizione di report, aggiungere la nuova definizione di albero.</span><span class="sxs-lookup"><span data-stu-id="e2fda-117">In the report definition, add your new tree definition.</span></span>
8. <span data-ttu-id="e2fda-118">Nella definizione di albero, selezionare **Impostazione**.</span><span class="sxs-lookup"><span data-stu-id="e2fda-118">In the tree definition, select **Setting**.</span></span> <span data-ttu-id="e2fda-119">In **Selezione unità gerarchica** selezionare **Includi tutte le unità**.</span><span class="sxs-lookup"><span data-stu-id="e2fda-119">Under **Reporting unit selection**, select **Include all units**.</span></span>

## <a name="how-do-i-identify-which-accounts-do-not-match-my-balances"></a><span data-ttu-id="e2fda-120">Come identificare quali conti non corrispondono ai saldi?</span><span class="sxs-lookup"><span data-stu-id="e2fda-120">How do I identify which accounts do not match my balances?</span></span>

<span data-ttu-id="e2fda-121">Se si dispone di un report che non corrisponde ai saldi, ecco alcuni passaggi che è possibile eseguire per identificare ognuno dei conti e degli scostamenti.</span><span class="sxs-lookup"><span data-stu-id="e2fda-121">If you have a report that doesn't have matching balances, here are some steps you can take to identify each of the accounts and variances.</span></span> 

<span data-ttu-id="e2fda-122">**Financial Reporter Report Designer**</span><span class="sxs-lookup"><span data-stu-id="e2fda-122">**Financial Reporter Report Designer**</span></span>
1. <span data-ttu-id="e2fda-123">In Financial Reporter Report Designer creare una nuova definizione di riga.</span><span class="sxs-lookup"><span data-stu-id="e2fda-123">In Financial Reporter Report Designer, create a new row definition.</span></span> 
2. <span data-ttu-id="e2fda-124">Selezionare **Modifica > Inserisci righe da dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="e2fda-124">Select **Edit > Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="e2fda-125">Selezionare **MainAccount**.</span><span class="sxs-lookup"><span data-stu-id="e2fda-125">Select **MainAccount**.</span></span>  
4. <span data-ttu-id="e2fda-126">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2fda-126">Select **OK**.</span></span>
5. <span data-ttu-id="e2fda-127">Salvare la definizione di riga.</span><span class="sxs-lookup"><span data-stu-id="e2fda-127">Save the row definition.</span></span>
6. <span data-ttu-id="e2fda-128">Creare una nuova definizione di colonna</span><span class="sxs-lookup"><span data-stu-id="e2fda-128">Create a new column definition</span></span>
7. <span data-ttu-id="e2fda-129">Creare una nuova definizione di report.</span><span class="sxs-lookup"><span data-stu-id="e2fda-129">Create a new report definition.</span></span>
8. <span data-ttu-id="e2fda-130">Selezionare **Impostazioni** e deselezionare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="e2fda-130">Select **Settings** and unmark this option.</span></span>  
9. <span data-ttu-id="e2fda-131">Generare il report.</span><span class="sxs-lookup"><span data-stu-id="e2fda-131">Generate the report.</span></span> 
10. <span data-ttu-id="e2fda-132">Esportare il report in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="e2fda-132">Export the report to Microsoft Excel.</span></span>

<span data-ttu-id="e2fda-133">**Dynamics 365 Finance**</span><span class="sxs-lookup"><span data-stu-id="e2fda-133">**Dynamics 365 Finance**</span></span> 
1. <span data-ttu-id="e2fda-134">In Dynamics 365 Finance andare a **Contabilità generale > Richieste di informazioni e report > Bilancio di verifica**.</span><span class="sxs-lookup"><span data-stu-id="e2fda-134">In Dynamics 365 Finance, go to **General Ledger > Inquiries and Reports > Trial Balance**.</span></span>
2. <span data-ttu-id="e2fda-135">Impostare i parametri riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="e2fda-135">Set the following parameters:</span></span>
   - <span data-ttu-id="e2fda-136">**Dal** - Immettere l'inizio dell'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="e2fda-136">**From Date** - Enter the start of the fiscal year.</span></span>
   - <span data-ttu-id="e2fda-137">**Al** - Immettere la data per la quale si sta generando il report.</span><span class="sxs-lookup"><span data-stu-id="e2fda-137">**To Date** - Enter the date you are generating the report for.</span></span>
   - <span data-ttu-id="e2fda-138">**Dimensione finanziaria** - Imposta questo campo su **Set di conti principali**.</span><span class="sxs-lookup"><span data-stu-id="e2fda-138">**Financial Dimension** - Set this field to **Main Account set**.</span></span>
 3. <span data-ttu-id="e2fda-139">Selezionare **Calcola**.</span><span class="sxs-lookup"><span data-stu-id="e2fda-139">Select **Calculate**.</span></span>
 4. <span data-ttu-id="e2fda-140">Esportare il report in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="e2fda-140">Export the report to Microsoft Excel.</span></span>

<span data-ttu-id="e2fda-141">Ora si possono copiare i dati dal report di Excel dello strumento di creazione report finanziari nel report Bilancio di verifica per confrontare le colonne **Saldo finale**.</span><span class="sxs-lookup"><span data-stu-id="e2fda-141">You should now be able to copy the data from the Financial Reporter Excel report to the Trial Balance report, so you can compare the **Closing Balance** columns.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]