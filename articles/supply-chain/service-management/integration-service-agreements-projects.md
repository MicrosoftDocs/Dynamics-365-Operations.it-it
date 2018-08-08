---
title: Integrazione per contratti e progetti di servizio
description: "Quando si gestiscono contratti di assistenza e righe dei contratti di assistenza, vengono utilizzati i dati impostati nelle aree di Gestione progetti e contabilità."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 6bd2fb1f54a3decb77f019db6b2016cebdcaddb9
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="integration-for-service-agreements-and-projects"></a><span data-ttu-id="751af-103">Integrazione per contratti e progetti di servizio</span><span class="sxs-lookup"><span data-stu-id="751af-103">Integration for service agreements and projects</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="751af-104">Quando si gestiscono contratti di assistenza e righe dei contratti di assistenza, vengono utilizzati i dati impostati nelle aree di **Gestione progetti e contabilità** riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="751af-104">When you work with service agreements and service agreement lines, you use data that is set up in the following areas in **Project management and accounting**.</span></span>

## <a name="project-prices"></a><span data-ttu-id="751af-105">Prezzi progetto</span><span class="sxs-lookup"><span data-stu-id="751af-105">Project prices</span></span>

<span data-ttu-id="751af-106">Il prezzo di costo e di vendita per una transazione di contratto di assistenza derivano dall'impostazione del prezzo di costo applicata al progetto collegato al contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="751af-106">The cost and the sales price for a service agreement transaction are derived from the cost price setup that applies to the project that is attached to the service agreement.</span></span> <span data-ttu-id="751af-107">I prezzi di costo e di vendita possono essere impostati per progetto, per dipendente e per categoria.</span><span class="sxs-lookup"><span data-stu-id="751af-107">Cost and sales prices can be set up by project, employee, and category.</span></span> 

## <a name="project-validation"></a><span data-ttu-id="751af-108">Convalida progetto</span><span class="sxs-lookup"><span data-stu-id="751af-108">Project validation</span></span>

<span data-ttu-id="751af-109">I progetti, i dipendenti e le categorie disponibili per la selezione in una riga del contratto di assistenza possono essere limitati dall'impostazione di convalida in **Gestione progetti e contabilità**.</span><span class="sxs-lookup"><span data-stu-id="751af-109">The projects, employees, and categories that are available for selection on a service agreement line can be limited by the validation setup in **Project management and accounting**.</span></span> <span data-ttu-id="751af-110">Utilizzando l'impostazione di convalida è possibile combinare dipendenti, progetti e categorie per l'accesso del controllo.</span><span class="sxs-lookup"><span data-stu-id="751af-110">By using the validation setup, you can combine employees, projects, and categories for control access.</span></span> 

## <a name="project-line-properties"></a><span data-ttu-id="751af-111">Proprietà di riga del progetto</span><span class="sxs-lookup"><span data-stu-id="751af-111">Project line properties</span></span>

<span data-ttu-id="751af-112">Per una riga del contratto di assistenza viene immessa automaticamente una proprietà di riga.</span><span class="sxs-lookup"><span data-stu-id="751af-112">A line property is entered automatically for a service agreement line.</span></span>

<span data-ttu-id="751af-113">Le proprietà di riga vengono create nel modulo **Proprietà riga** in **Gestione progetti e contabilità**.</span><span class="sxs-lookup"><span data-stu-id="751af-113">Line properties are created in the **Line properties** form in **Project management and accounting**.</span></span> <span data-ttu-id="751af-114">La proprietà di riga immessa in un contratto di assistenza è collegata al progetto selezionato per il contratto di assistenza e successivamente ereditata dalla riga del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="751af-114">The line property that is entered on a service agreement is attached to the project that is selected for the service agreement and inherited subsequently by the service agreement line.</span></span> 

## <a name="default-offset-accounts"></a><span data-ttu-id="751af-115">Conti di contropartita predefiniti</span><span class="sxs-lookup"><span data-stu-id="751af-115">Default offset accounts</span></span>

<span data-ttu-id="751af-116">Se si immette una transazione di spesa, per la transazione viene selezionato automaticamente un conto spese di contropartita predefinito.</span><span class="sxs-lookup"><span data-stu-id="751af-116">If you enter an expense transaction, a default expense offset account is selected automatically for the transaction.</span></span> <span data-ttu-id="751af-117">Il conto spese di contropartita predefinito viene impostato per il progetto collegato al contratto di assistenza corrente.</span><span class="sxs-lookup"><span data-stu-id="751af-117">The default expense account is set up for the project that is attached to the current service agreement.</span></span>

## <a name="project-categories"></a><span data-ttu-id="751af-118">Categorie di progetti</span><span class="sxs-lookup"><span data-stu-id="751af-118">Project categories</span></span>

<span data-ttu-id="751af-119">Le categorie disponibili per le righe del contratto di assistenza vengono impostate nel modulo **Categorie di progetto** in **Gestione progetti e contabilità**.</span><span class="sxs-lookup"><span data-stu-id="751af-119">The categories that are available for service agreement lines are set up in the **Project categories** form in **Project management and accounting**.</span></span> 

> [!NOTE]
> <P><span data-ttu-id="751af-120">Sono disponibili per la selezione le categorie con la casella di controllo <STRONG>Attivo nei giornali di registrazione</STRONG> selezionata nella scheda <STRONG>Progetto</STRONG> del modulo <STRONG>Categorie di progetto</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="751af-120">Categories that have the <STRONG>Active in journals</STRONG> check box selected on the <STRONG>Project</STRONG> tab in the <STRONG>Project categories</STRONG> form are available for selection.</span></span> <span data-ttu-id="751af-121">Se la casella di controllo <STRONG>Categorie inattive</STRONG> nella scheda <STRONG>Giornali di registrazione</STRONG> del modulo <STRONG>Parametri Gestione progetti e contabilità</STRONG> è selezionata, tuttavia, tutte le categorie sono disponibili per la selezione.</span><span class="sxs-lookup"><span data-stu-id="751af-121">However, if the <STRONG>Inactive categories</STRONG> check box is selected on the <STRONG>Journals</STRONG> tab in the <STRONG>Project management and accounting parameters</STRONG> form, all categories are available for selection.</span></span></P>

## <a name="project-parameters"></a><span data-ttu-id="751af-122">Parametri progetto</span><span class="sxs-lookup"><span data-stu-id="751af-122">Project parameters</span></span>

<span data-ttu-id="751af-123">Se il campo **Lavoratori con rapporto chiuso** della scheda **Giornali di registrazione** del modulo **Parametri Gestione progetti e contabilità** è selezionata, è possibile selezionare i dipendenti inattivi e quelli attivi nei moduli **Ordini di assistenza** e **Contratti di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="751af-123">If the **Terminated workers** field on the **Journals** tab in the **Project management and accounting parameters** form is selected, you can select inactive employees and active employees in the **Service agreements** and **Service orders** forms.</span></span>

<span data-ttu-id="751af-124">È inoltre possibile attivare i campi **Ora di inizio** e **Ora di fine** della scheda **Progetto** nel modulo **Ordini di assistenza** per immettere le ore di inizio e di fine nelle righe dell'ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="751af-124">Also, you can enable the **Start time** and **End time** fields on the **Project** tab in the **Service orders** form to enter starting and ending times on service order lines.</span></span>

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a><span data-ttu-id="751af-125">Attivare la funzionalità delle ore di inizio e di fine per gli ordini di assistenza</span><span class="sxs-lookup"><span data-stu-id="751af-125">Enable the starting and ending time feature for service orders</span></span>

1.  <span data-ttu-id="751af-126">Fare clic su **Gestione progetti e contabilità** \> **Impostazione** \> **Parametri Gestione progetti e contabilità**.</span><span class="sxs-lookup"><span data-stu-id="751af-126">Click **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>

2.  <span data-ttu-id="751af-127">Fare clic sulla scheda **Giornali di registrazione** e selezionare la casella di controllo **Mostra ora di inizio/fine**.</span><span class="sxs-lookup"><span data-stu-id="751af-127">Click the **Journals** tab, and then select the **Show start/end times** check box.</span></span>

3.  <span data-ttu-id="751af-128">Fare clic su **Gestione progetti e contabilità** \> **Impostazione** \> **Giornali di registrazione** \> **Nomi giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="751af-128">Click **Project management and accounting** \> **Setup** \> **Journals** \> **Journal names**.</span></span>

4.  <span data-ttu-id="751af-129">Selezionare il nome di giornale di registrazione collegato all'ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="751af-129">Select the journal name that is attached to the service order.</span></span>

5.  <span data-ttu-id="751af-130">Fare clic sulla scheda **Generale** e selezionare la casella di controllo **Mostra ora di inizio/fine**.</span><span class="sxs-lookup"><span data-stu-id="751af-130">Click the **General** tab, and then select the **Show start/end times** check box.</span></span>


> [!NOTE]
> <P><span data-ttu-id="751af-131">Selezionare il nome di giornale di registrazione per l'ordine di assistenza nel campo <STRONG>Ora</STRONG> della scheda <STRONG>Giornali di registrazione</STRONG> nel modulo <STRONG>Parametri di gestione assistenza</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="751af-131">Select the journal name for the service order in the <STRONG>Hour</STRONG> field on the <STRONG>Journals</STRONG> tab in the <STRONG>Service management parameters</STRONG> form.</span></span></P>






