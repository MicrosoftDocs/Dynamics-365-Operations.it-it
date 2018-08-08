---
title: Gruppi di conti di consolidamento e conti di consolidamento aggiuntivi
description: In questo argomento vengono fornite informazioni sui gruppi di conti di consolidamento e sui conti di consolidamento aggiuntivi e viene illustrato come vengono utilizzati in Microsoft Dynamics 365 for Finance and Operations.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: f1c463ee54512b07f5e45c4df995aefed6110cb0
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a><span data-ttu-id="62a32-103">Gruppi di conti di consolidamento e conti di consolidamento aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="62a32-103">Consolidation account groups and additional consolidation accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62a32-104">In questo argomento vengono fornite informazioni sui gruppi di conti di consolidamento e sui conti di consolidamento aggiuntivi e viene illustrato come vengono utilizzati in Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="62a32-104">This topic provides information about consolidation account groups and additional consolidation accounts, and explains how they are used in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<a name="consolidation-account-groups"></a><span data-ttu-id="62a32-105">Gruppi di conti di consolidamento</span><span class="sxs-lookup"><span data-stu-id="62a32-105">Consolidation account groups</span></span>
----------------------------

<span data-ttu-id="62a32-106">I gruppi di conti di consolidamento consentono di creare gruppi di conti da utilizzare per consolidare i dati.</span><span class="sxs-lookup"><span data-stu-id="62a32-106">Consolidation account groups let you create groups of the accounts that you want to use to consolidate data.</span></span> <span data-ttu-id="62a32-107">In genere, un gruppo di conti di consolidamento rappresenta un piano dei conti definito dal Governo o mappa i conti a un gruppo definito dalla sede centrale della società.</span><span class="sxs-lookup"><span data-stu-id="62a32-107">Most often, a consolidation account group represents a government-mandated chart of accounts or maps accounts to a group that is defined by the company's headquarters.</span></span> <span data-ttu-id="62a32-108">I gruppi di conti di consolidamento sono disponibili nell'area **Impostazioni** del modulo **Consolidamenti**.</span><span class="sxs-lookup"><span data-stu-id="62a32-108">You can find consolidation account groups in the **Setup** area of the **Consolidations** module.</span></span> <span data-ttu-id="62a32-109">Quando si aggiunge un nuovo gruppo, si immette un identificatore univoco per il gruppo di conti e un nome.</span><span class="sxs-lookup"><span data-stu-id="62a32-109">When you add a new group, you enter a unique identifier for the account group and a name.</span></span>

## <a name="additional-consolidation-accounts"></a><span data-ttu-id="62a32-110">Conti di consolidamento aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="62a32-110">Additional consolidation accounts</span></span>
<span data-ttu-id="62a32-111">I conti di consolidamento aggiuntivi consentono di assegnare un conto da un piano dei conti esistente a un gruppo di conti di consolidamento.</span><span class="sxs-lookup"><span data-stu-id="62a32-111">Additional consolidation accounts let you assign an account from an existing chart of accounts to a consolidation account group.</span></span> <span data-ttu-id="62a32-112">Successivamente è possibile specificare un valore e un nome di conto di consolidamento.</span><span class="sxs-lookup"><span data-stu-id="62a32-112">You can then specify a consolidation account value and name.</span></span> 

<span data-ttu-id="62a32-113">I conti di consolidamento aggiuntivi sono disponibili nell'area **Impostazioni** del modulo **Consolidamenti**.</span><span class="sxs-lookup"><span data-stu-id="62a32-113">You can find additional consolidation accounts in the **Setup** area of the **Consolidations** module.</span></span> <span data-ttu-id="62a32-114">Quando si crea un nuovo conto di consolidamento, è necessario specificare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="62a32-114">When you create a new consolidation account, you must specify the following information:</span></span>

-   <span data-ttu-id="62a32-115">**Conto principale**: si tratta di un campo di ricerca che mostra tutti i conti principali basati sul piano dei conti selezionato nella pagina.</span><span class="sxs-lookup"><span data-stu-id="62a32-115">**Main account** – This field is a lookup that shows all the main accounts that are based on the chart of accounts that you selected on the page.</span></span> <span data-ttu-id="62a32-116">Quando si seleziona un conto, il relativo nome viene automaticamente inserito nel campo **Nome conto principale**.</span><span class="sxs-lookup"><span data-stu-id="62a32-116">When you select an account, the name is automatically entered in the **Main account name** field.</span></span>
-   <span data-ttu-id="62a32-117">**Gruppo di conti di consolidamento**: utilizzare questo campo per specificare il gruppo a cui assegnare il conto.</span><span class="sxs-lookup"><span data-stu-id="62a32-117">**Consolidation account group** – Use this field to specify the group to assign the account to.</span></span> <span data-ttu-id="62a32-118">Se si esegue il consolidamento in due modi diversi, è necessario aggiungere lo stesso conto a tutti e quattro i gruppi di conti di consolidamento.</span><span class="sxs-lookup"><span data-stu-id="62a32-118">If you consolidate in two different ways, you must add the same account to all four consolidation account groups.</span></span>
-   <span data-ttu-id="62a32-119">**Conto di consolidamento**: immettere il valore del conto di consolidamento.</span><span class="sxs-lookup"><span data-stu-id="62a32-119">**Consolidation account** – Enter the value of the consolidation account.</span></span> <span data-ttu-id="62a32-120">Questo valore non deve essere un conto di un piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="62a32-120">This value doesn't have to be an account from a chart of accounts.</span></span> <span data-ttu-id="62a32-121">È possibile immettere qualsiasi valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="62a32-121">It can be any value that you require.</span></span>
-   <span data-ttu-id="62a32-122">**Nome conto di consolidamento**: immettere il nome del conto che si desidera visualizzare le richieste di informazioni e nei report.</span><span class="sxs-lookup"><span data-stu-id="62a32-122">**Consolidation account name** – Enter the name of account as you want it to appear on inquiries and reports.</span></span>
-   <span data-ttu-id="62a32-123">**Livello SAT**: questo campo viene utilizzato per segnalare gli estratti conto agli uffici tributari messicani.</span><span class="sxs-lookup"><span data-stu-id="62a32-123">**SAT level** – This field is used to report account statements to the Mexican tax authorities.</span></span> 

<span data-ttu-id="62a32-124">Dopo aver creato i gruppi di conti di consolidamento e i conti di consolidamento aggiuntivi, è possibile selezionare il gruppo nel processo di consolidamento online.</span><span class="sxs-lookup"><span data-stu-id="62a32-124">When you've finished creating your consolidation account groups and additional consolidation accounts, you can select the group in the Consolidate online process.</span></span>


<span data-ttu-id="62a32-125">Per ulteriori informazioni, vedere [Creare gruppi di consolidamento e conti di consolidamento aggiuntivi](../general-ledger/tasks/create-consolidation-groups.md).</span><span class="sxs-lookup"><span data-stu-id="62a32-125">For more information, see [Create consolidation groups and additional consolidation accounts](../general-ledger/tasks/create-consolidation-groups.md).</span></span> 




