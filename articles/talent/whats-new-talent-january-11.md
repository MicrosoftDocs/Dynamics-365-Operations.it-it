---
title: Novità o modifiche in Dynamics 365 Talent - Core HR (11 gennaio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d49a4aca368e3de10ae37b56c6d286d78f7f369a
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899176"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-january-11-2019"></a><span data-ttu-id="88107-103">Novità o modifiche in Dynamics 365 Talent - Core HR (11 gennaio 2019)</span><span class="sxs-lookup"><span data-stu-id="88107-103">What's new or changed in Dynamics 365 Talent - Core HR (January 11, 2019)</span></span>

<span data-ttu-id="88107-104">**Build 8.1.2100**</span><span class="sxs-lookup"><span data-stu-id="88107-104">**Build 8.1.2100**</span></span>

<span data-ttu-id="88107-105">Questo argomento descrive le funzionalità nuove o modificate di Core HR.</span><span class="sxs-lookup"><span data-stu-id="88107-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="88107-106">Modifiche</span><span class="sxs-lookup"><span data-stu-id="88107-106">Changes</span></span>

### <a name="validate-leave-requests-by-forecasting-available-balance"></a><span data-ttu-id="88107-107">Convalida delle richieste di congedo mediante previsione del saldo disponibile</span><span class="sxs-lookup"><span data-stu-id="88107-107">Validate leave requests by forecasting available balance</span></span>
<span data-ttu-id="88107-108">Le modifiche apportate in questa versione consentono ai dipendenti di richiedere congedi futuri senza sottrarli dal relativo saldo corrente.</span><span class="sxs-lookup"><span data-stu-id="88107-108">Changes made in this release allow employees to request future leave time without subtracting from their current balance.</span></span> <span data-ttu-id="88107-109">I flussi di lavoro standard saranno utilizzati per tutte le richieste future.</span><span class="sxs-lookup"><span data-stu-id="88107-109">Standard workflows will be used for any future requests made.</span></span> <span data-ttu-id="88107-110">Per ulteriori informazioni, leggere [Attribuire permessi in base alle ore lavorate](leave-accrue-hours-worked.md).</span><span class="sxs-lookup"><span data-stu-id="88107-110">For more information, read [Accrue time off based on hours worked](leave-accrue-hours-worked.md).</span></span>

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a><span data-ttu-id="88107-111">Visualizzazione del saldo di congedo previsto in Dipendente self-service e Persone</span><span class="sxs-lookup"><span data-stu-id="88107-111">View forecasted leave balance in ESS and People</span></span>
<span data-ttu-id="88107-112">Questa funzionalità consente la visualizzazione dei saldi per periodi di congedo futuri da parte del reparto risorse umane nonché da responsabili e dipendenti.</span><span class="sxs-lookup"><span data-stu-id="88107-112">This feature enables viewing of balances for future leave periods by HR, managers, and employees.</span></span> <span data-ttu-id="88107-113">I dipendenti possono visualizzare i saldi futuri nell'area di lavoro **Dipendente self-service** e il reparto risorse umane ha accesso alle stesse informazioni utilizzando l'area di lavoro **Persone**.</span><span class="sxs-lookup"><span data-stu-id="88107-113">Employees can view future balances in the **Employee Self-Service** workspace and HR has access to the same information using the **People** workspace.</span></span>

### <a name="notifications-for-changing-leave-balances"></a><span data-ttu-id="88107-114">Notifiche per la modifica dei saldi di congedo</span><span class="sxs-lookup"><span data-stu-id="88107-114">Notifications for changing leave balances</span></span>
<span data-ttu-id="88107-115">I saldi di congedo visualizzeranno il saldo corrente dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="88107-115">Leave balances will display the employees current balance.</span></span> <span data-ttu-id="88107-116">I saldi futuri sono disponibili nelle aree di lavoro **Dipendente self-service** e **Persone** immettendo una data iniziale per il calcolo del saldo previsto.</span><span class="sxs-lookup"><span data-stu-id="88107-116">Future balances are available on the **Employee Self-Service** and **People** workspaces by entering an “as of date” to calculate the forecasted balance.</span></span>

<span data-ttu-id="88107-117">Per visualizzare i saldi previsti, sono stati aggiunti degli elementi nelle seguenti aree:</span><span class="sxs-lookup"><span data-stu-id="88107-117">Navigation has been added to view forecasted balances in the following areas:</span></span>
  - <span data-ttu-id="88107-118">Scheda**Tempo libero** nell'area di lavoro **Dipendente self-service**.</span><span class="sxs-lookup"><span data-stu-id="88107-118">**Time off** card on the **Employee Self-Service** workspace.</span></span>
  - <span data-ttu-id="88107-119">Scheda**Congedo e assenza** nell'area di lavoro **Responsabile self-service**.</span><span class="sxs-lookup"><span data-stu-id="88107-119">**Leave and absence** card on the **Manager Self-Service** workspace.</span></span>
  - <span data-ttu-id="88107-120">Pagina**Congedo e assenza** nell'area di lavoro **Persone**.</span><span class="sxs-lookup"><span data-stu-id="88107-120">**Leave and absence** page on the **People** workspace.</span></span>

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a><span data-ttu-id="88107-121">Utilizzo dei decimali per i piani di retribuzione variabile (piani in contanti)</span><span class="sxs-lookup"><span data-stu-id="88107-121">Allow decimals for Variable compensation plans (Cash plans)</span></span>
<span data-ttu-id="88107-122">I piani e i premi in contanti variabili presentano ora la flessibilità per importi e sostituzioni di valori con importi decimali.</span><span class="sxs-lookup"><span data-stu-id="88107-122">Variable cash awards and plans now have the additional flexibility for amounts and overrides for values with decimal amounts.</span></span>

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a><span data-ttu-id="88107-123">Impossibile modificare le date nei piani di retribuzione variabili dopo il salvataggio del piano</span><span class="sxs-lookup"><span data-stu-id="88107-123">Unable to change the dates on Variable comp enrollments after the plan is saved</span></span>
<span data-ttu-id="88107-124">Questa modifica consente l'aggiornamento della data di fine del piano (estensione o scadenza) dopo che il piano è stato salvato.</span><span class="sxs-lookup"><span data-stu-id="88107-124">This change allows for the plan end date to be updated (extended or expired) after the plan has been saved.</span></span> <span data-ttu-id="88107-125">È sempre possibile attivare o disattivare i piani che non dipendono da date di inizio e di fine.</span><span class="sxs-lookup"><span data-stu-id="88107-125">You can still activate or de-activate plans independent of start and end dates.</span></span>

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a><span data-ttu-id="88107-126">Informazioni sulle retribuzioni disponibili all'assegnazione del ruolo di sicurezza Amministratore retribuzioni</span><span class="sxs-lookup"><span data-stu-id="88107-126">Payroll information available when assigned the Payroll admin security role</span></span>
<span data-ttu-id="88107-127">Il ruolo Amministratore retribuzioni è stato aggiornato per avere accesso alle informazioni sulle retribuzioni durante il processo di richiesta.</span><span class="sxs-lookup"><span data-stu-id="88107-127">The Payroll Administrator role has been updated to have access to the payroll information during the request process.</span></span>

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="88107-128">Dipendente self-service | Il drill-down della gerarchia delle posizioni non richiama il nodo padre</span><span class="sxs-lookup"><span data-stu-id="88107-128">Employee self-service | Position hierarchy drill-down from tile fails to get parent node</span></span>
<span data-ttu-id="88107-129">Sono state apportate delle modifiche per eliminare un errore che si verificava all'aggiunta della gerarchia delle posizioni a nuove aree di lavoro e lo spostamento nella struttura organizzativa.</span><span class="sxs-lookup"><span data-stu-id="88107-129">Changes have been made to eliminate an error that occurred when adding the position hierarchy to new workspaces and navigating within the organizational structure.</span></span>

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a><span data-ttu-id="88107-130">Nuovo messaggio di convalida quando il numero di dipendente successivo è in uso</span><span class="sxs-lookup"><span data-stu-id="88107-130">New validation message when personnel number sequence is in use</span></span>
<span data-ttu-id="88107-131">È stata apportata una modifica per determinare il problema quando si assume un dipendente e il numero di dipendente successivo è in uso.</span><span class="sxs-lookup"><span data-stu-id="88107-131">A change has been made to clarify what the issue is when you hire an employee and the next personnel number is in use.</span></span>

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a><span data-ttu-id="88107-132">Area di lavoro Dipendente self-service selezionata come pagina di avvio iniziale</span><span class="sxs-lookup"><span data-stu-id="88107-132">Employee self-service workspace selected as the initial startup page</span></span>
<span data-ttu-id="88107-133">Quando l'area di lavoro **Dipendente self-service** viene selezionata come pagina di avvio iniziale per un utente e a quell'utente non è assegnato il ruolo dipendente, il sistema visualizza il dashboard predefinito.</span><span class="sxs-lookup"><span data-stu-id="88107-133">When the **Employee self-service** workspace is selected as the initial startup page for a user and that user is not assigned the employee role, the system will redirect to the default dashboard.</span></span>

### <a name="termination-reason-code-updates-position-assignment-record"></a><span data-ttu-id="88107-134">Il codice del motivo di fine rapporto aggiorna il record di assegnazione della posizione</span><span class="sxs-lookup"><span data-stu-id="88107-134">Termination reason code updates position assignment record</span></span>
<span data-ttu-id="88107-135">Il codice del motivo di fine rapporto ora aggiorna l'assegnazione della posizione quando si chiude un rapporto dipendente e si termina la posizione.</span><span class="sxs-lookup"><span data-stu-id="88107-135">The termination reason code will now update the position assignment when terminating an employee and ending the position.</span></span> 
