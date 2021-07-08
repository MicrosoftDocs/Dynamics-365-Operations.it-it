---
title: Domande frequenti sulla creazione di report finanziari
description: In questo argomento vengono fornite alcune risposte alle domande frequenti sulla creazione di report finanziari.
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
ms.openlocfilehash: e1b67f86446403933005008a9a1e2cc6739dc516
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266635"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="e92de-103">Domande frequenti sulla creazione di report finanziari</span><span class="sxs-lookup"><span data-stu-id="e92de-103">Financial reporting FAQ</span></span>

<span data-ttu-id="e92de-104">In questo argomento vengono fornite risposte alle domande frequenti sulla creazione di report finanziari.</span><span class="sxs-lookup"><span data-stu-id="e92de-104">This topic provides answers to frequently asked questions about Financial reporting.</span></span>

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a><span data-ttu-id="e92de-105">Come si limita l'accesso a un report utilizzando la sicurezza dell'albero?</span><span class="sxs-lookup"><span data-stu-id="e92de-105">How do I restrict access to a report by using tree security?</span></span>

<span data-ttu-id="e92de-106">L'esempio seguente mostra come limitare l'accesso a un report utilizzando la sicurezza dell'albero.</span><span class="sxs-lookup"><span data-stu-id="e92de-106">The following example shows how to restrict access to a report by using tree security.</span></span>

<span data-ttu-id="e92de-107">La società dimostrativa USMF dispone di un report **stato patrimoniale** che non desidera rendere accessibile a tutti gli utenti dei report finanziari.</span><span class="sxs-lookup"><span data-stu-id="e92de-107">The USMF demo company has a **Balance sheet** report that not all Financial reporting users should have access to.</span></span> <span data-ttu-id="e92de-108">È possibile utilizzare la sicurezza dell'albero per limitare l'accesso a un singolo report in modo che solo specifici utenti possano accedervi.</span><span class="sxs-lookup"><span data-stu-id="e92de-108">You can use tree security to restrict access to a single report so that only specific users can access it.</span></span>

1. <span data-ttu-id="e92de-109">Accedere a Financial Reporter Report Designer.</span><span class="sxs-lookup"><span data-stu-id="e92de-109">Sign in to Financial Reporter Report Designer.</span></span>
2. <span data-ttu-id="e92de-110">Selezionare **File \> Nuovo \> Definizione di albero** per creare una nuova definizione di albero.</span><span class="sxs-lookup"><span data-stu-id="e92de-110">Select **File \> New \> Tree Definition** to create a new tree definition.</span></span>
3. <span data-ttu-id="e92de-111">Fare doppio tocco o doppio clic sulla riga **Riepilogo** nella colonna **Sicurezza unità**.</span><span class="sxs-lookup"><span data-stu-id="e92de-111">Double-tap (or double-click) the **Summary** line in the **Unit Security** column.</span></span>
4. <span data-ttu-id="e92de-112">Selezionare **Utenti e gruppi**.</span><span class="sxs-lookup"><span data-stu-id="e92de-112">Select **Users and Groups**.</span></span>
5. <span data-ttu-id="e92de-113">Selezionare gli utenti o i gruppi che devono accedere al report.</span><span class="sxs-lookup"><span data-stu-id="e92de-113">Select the users or groups that require access to the report.</span></span>
6. <span data-ttu-id="e92de-114">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e92de-114">Select **Save**.</span></span>
7. <span data-ttu-id="e92de-115">Nella definizione di report, aggiungere la nuova definizione di albero.</span><span class="sxs-lookup"><span data-stu-id="e92de-115">In the report definition, add your new tree definition.</span></span>
8. <span data-ttu-id="e92de-116">Nella definizione di albero, selezionare **Impostazione**.</span><span class="sxs-lookup"><span data-stu-id="e92de-116">In the tree definition, select **Setting**.</span></span> <span data-ttu-id="e92de-117">Quindi, in **Selezione unità gerarchica** selezionare **Includi tutte le unità**.</span><span class="sxs-lookup"><span data-stu-id="e92de-117">Then, under **Reporting unit selection**, select **Include all units**.</span></span>

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a><span data-ttu-id="e92de-118">Come identificare quali conti non corrispondono ai saldi?</span><span class="sxs-lookup"><span data-stu-id="e92de-118">How do I identify which accounts don't match my balances?</span></span>

<span data-ttu-id="e92de-119">Se si dispone di un report che non corrisponde ai saldi, utilizzare le seguenti procedure per identificare ciascun conto e scostamento.</span><span class="sxs-lookup"><span data-stu-id="e92de-119">If you have a report that doesn't have matching balances, use the following procedures to identify each account and variance.</span></span>

### <a name="in-financial-reporter-report-designer"></a><span data-ttu-id="e92de-120">In Financial Reporter Report Designer</span><span class="sxs-lookup"><span data-stu-id="e92de-120">In Financial Reporter Report Designer</span></span>

1. <span data-ttu-id="e92de-121">Creare una nuova definizione di riga.</span><span class="sxs-lookup"><span data-stu-id="e92de-121">Create a new row definition.</span></span>
2. <span data-ttu-id="e92de-122">Selezionare **Modifica \> Inserisci righe da dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="e92de-122">Select **Edit \> Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="e92de-123">Selezionare **MainAccount**.</span><span class="sxs-lookup"><span data-stu-id="e92de-123">Select **MainAccount**.</span></span>
4. <span data-ttu-id="e92de-124">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e92de-124">Select **OK**.</span></span>
5. <span data-ttu-id="e92de-125">Salvare la definizione di riga.</span><span class="sxs-lookup"><span data-stu-id="e92de-125">Save the row definition.</span></span>
6. <span data-ttu-id="e92de-126">Creare una nuova definizione di colonna.</span><span class="sxs-lookup"><span data-stu-id="e92de-126">Create a new column definition.</span></span>
7. <span data-ttu-id="e92de-127">Creare una nuova definizione di report.</span><span class="sxs-lookup"><span data-stu-id="e92de-127">Create a new report definition.</span></span>
8. <span data-ttu-id="e92de-128">Selezionare **Impostazioni** e deselezionare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="e92de-128">Select **Settings** and unmark this option.</span></span>
9. <span data-ttu-id="e92de-129">Generare il report.</span><span class="sxs-lookup"><span data-stu-id="e92de-129">Generate the report.</span></span> 
10. <span data-ttu-id="e92de-130">Esportare il report in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="e92de-130">Export the report to Microsoft Excel.</span></span>

### <a name="in-dynamics-365-finance"></a><span data-ttu-id="e92de-131">In Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="e92de-131">In Dynamics 365 Finance</span></span>

1. <span data-ttu-id="e92de-132">Andare a **Contabilità generale \> Richieste di informazioni e report \> Bilancio di verifica**.</span><span class="sxs-lookup"><span data-stu-id="e92de-132">Go to **General ledger \> Inquiries and reports \> Trial balance**.</span></span>
2. <span data-ttu-id="e92de-133">Impostare i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="e92de-133">Set the following fields:</span></span>

    - <span data-ttu-id="e92de-134">**Dal** - Immettere la data di inizio dell'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="e92de-134">**From Date** – Enter the start date of the fiscal year.</span></span>
    - <span data-ttu-id="e92de-135">**Al** - Immettere la data per la quale si sta generando il report.</span><span class="sxs-lookup"><span data-stu-id="e92de-135">**To Date** – Enter the date that you're generating the report for.</span></span>
    - <span data-ttu-id="e92de-136">**Dimensione finanziaria** - Impostare questo campo su **Set di conti principali**.</span><span class="sxs-lookup"><span data-stu-id="e92de-136">**Financial Dimension** – Set this field to **Main Account set**.</span></span>

3. <span data-ttu-id="e92de-137">Selezionare **Calcola**.</span><span class="sxs-lookup"><span data-stu-id="e92de-137">Select **Calculate**.</span></span>
4. <span data-ttu-id="e92de-138">Esportare il report in Excel.</span><span class="sxs-lookup"><span data-stu-id="e92de-138">Export the report to Excel.</span></span>

<span data-ttu-id="e92de-139">Ora si possono copiare i dati dal report di Excel di Financial Reporter nel report **Bilancio di verifica** per confrontare le colonne **Saldo di chiusura**.</span><span class="sxs-lookup"><span data-stu-id="e92de-139">You should now be able to copy the data from the Financial Reporter Excel report to the **Trial Balance** report, so that you can compare the **Closing Balance** columns.</span></span>

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a><span data-ttu-id="e92de-140">Quando si progetta un report in Report Designer o quando si genera un report finanziario, viene visualizzato il seguente messaggio: "Impossibile completare l'operazione a causa di un problema nel framework del provider di dati".</span><span class="sxs-lookup"><span data-stu-id="e92de-140">When I design a report in Report Designer, or when I generate a financial report, I received the following message: "The operation could not be completed due to a problem in the data provider framework."</span></span> <span data-ttu-id="e92de-141">Come si deve rispondere?</span><span class="sxs-lookup"><span data-stu-id="e92de-141">How should I respond?</span></span>

<span data-ttu-id="e92de-142">Il messaggio indica che si è verificato un problema quando il sistema ha tentato di recuperare i metadati finanziari dal data mart mentre veniva utilizzato il report finanziario.</span><span class="sxs-lookup"><span data-stu-id="e92de-142">The message indicates that an issue occurred when the system tried to retrieve financial metadata from the data mart while you were using Financial reporting.</span></span> <span data-ttu-id="e92de-143">Ci sono due modi per rispondere a questo problema:</span><span class="sxs-lookup"><span data-stu-id="e92de-143">There are two ways to respond to this issue:</span></span>

- <span data-ttu-id="e92de-144">Rivedere lo stato di integrazione dei dati andando su **Strumenti \> Stato di integrazione** in Report Designer.</span><span class="sxs-lookup"><span data-stu-id="e92de-144">Review the integration status of the data by going to **Tools \> Integration status** in Report Designer.</span></span> <span data-ttu-id="e92de-145">Se l'integrazione è incompleta, attendere che venga completata.</span><span class="sxs-lookup"><span data-stu-id="e92de-145">If the integration is incomplete, wait for it to be completed.</span></span> <span data-ttu-id="e92de-146">Quindi ripetere l'operazione che si stava facendo quando è stato visualizzato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="e92de-146">Then retry what you were doing when you received the message.</span></span>
- <span data-ttu-id="e92de-147">Contattare l'assistenza per identificare e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="e92de-147">Contact Support to identify and work through the issue.</span></span> <span data-ttu-id="e92de-148">È possibile che siano presenti dati incoerenti nel sistema.</span><span class="sxs-lookup"><span data-stu-id="e92de-148">There might be inconsistent data in the system.</span></span> <span data-ttu-id="e92de-149">I tecnici dell'assistenza possono aiutare a identificare il problema sul server e a trovare i dati specifici che potrebbero richiedere un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="e92de-149">Support engineers can help you identify that issue on the server and find the specific data that might require an update.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
