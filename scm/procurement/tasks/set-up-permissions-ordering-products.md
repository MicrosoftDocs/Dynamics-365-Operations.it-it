--- 
title: Impostare le autorizzazioni per ordinare prodotti per conto di altri
description: Questa procedura mostra come concedere ai lavoratori l'autorizzazione a preparare richieste di acquisto per conto di altri lavoratori.
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 9e003f953c05facd5516e2bfa6d1c83ba6381c15
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a><span data-ttu-id="48579-103">Impostare le autorizzazioni per ordinare prodotti per conto di altri</span><span class="sxs-lookup"><span data-stu-id="48579-103">Set up permissions for ordering products on behalf of someone else</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="48579-104">Questa procedura mostra come concedere ai lavoratori l'autorizzazione a preparare richieste di acquisto per conto di altri lavoratori.</span><span class="sxs-lookup"><span data-stu-id="48579-104">This procedure shows how to grant workers permission to prepare purchase requisitions on behalf of other workers.</span></span> <span data-ttu-id="48579-105">In altre parole, un "preparatore" di richieste di acquisto può creare una richiesta per un altro "richiedente".</span><span class="sxs-lookup"><span data-stu-id="48579-105">In other words, a purchase requisition “preparer” can create a requisition for another “requester.”</span></span> <span data-ttu-id="48579-106">La procedura inoltre mostra come concedere a un lavoratore l'autorizzazione a ordinare articoli e servizi in persone giuridiche o unità operative differenti.</span><span class="sxs-lookup"><span data-stu-id="48579-106">The procedure also shows how to grant a worker permission to order items and services in different legal entities or operating units.</span></span> <span data-ttu-id="48579-107">Queste attività vengono in genere svolte da un responsabile degli acquisti.</span><span class="sxs-lookup"><span data-stu-id="48579-107">Typically, these tasks are performed by a purchasing manager.</span></span> <span data-ttu-id="48579-108">È possibile utilizzare questa procedura sui dati della società di dati dimostrativi USMF oppure sui propri dati.</span><span class="sxs-lookup"><span data-stu-id="48579-108">You can use this procedure either on data for the USMF demo company or on your own data.</span></span>


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a><span data-ttu-id="48579-109">Concedere l'autorizzazione a immettere richieste di acquisto per conto di un altro lavoratore</span><span class="sxs-lookup"><span data-stu-id="48579-109">Grant permission to enter purchase requisitions on behalf of another worker</span></span>
1. <span data-ttu-id="48579-110">Andare ad Approvvigionamento > Impostazioni > Criteri > Autorizzazioni richiesta di acquisto.</span><span class="sxs-lookup"><span data-stu-id="48579-110">Go to Procurement and sourcing > Setup > Policies > Purchase requisition permissions.</span></span>
    * <span data-ttu-id="48579-111">Assicurarsi che il campo Visualizzazione corrente sia impostato su Per preparatore.</span><span class="sxs-lookup"><span data-stu-id="48579-111">Make sure that the Current view field is set to By preparer.</span></span>  <span data-ttu-id="48579-112">L'elenco nel riquadro sinistro mostra le persone a cui è possibile concedere l'autorizzazione a preparare le richieste per conto di altre persone.</span><span class="sxs-lookup"><span data-stu-id="48579-112">The list in the left pane shows the people who can be granted permission to prepare requisitions on behalf of other people.</span></span>  
2. <span data-ttu-id="48579-113">Selezionare la persona a cui concedere l'autorizzazione (il preparatore).</span><span class="sxs-lookup"><span data-stu-id="48579-113">Select the person to grant permission to (the preparer).</span></span>
3. <span data-ttu-id="48579-114">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="48579-114">Click Add.</span></span>
4. <span data-ttu-id="48579-115">Trovare e selezionare la persona da aggiungere come richiedente.</span><span class="sxs-lookup"><span data-stu-id="48579-115">Find and select the person to add as a requester.</span></span>
    * <span data-ttu-id="48579-116">Il richiedente è la persona per conto della quale il preparatore può creare le richieste.</span><span class="sxs-lookup"><span data-stu-id="48579-116">The requester is the person that the preparer can create requisitions on behalf of.</span></span>  
    * <span data-ttu-id="48579-117">Nel campo Autorizzazione, selezionare Specifico se il preparatore deve essere in grado di creare le richieste di acquisto per conto del lavoratore selezionato.</span><span class="sxs-lookup"><span data-stu-id="48579-117">In the Authorization field, select Specific if the preparer should be able to create purchase requisitions on behalf of the selected worker.</span></span> <span data-ttu-id="48579-118">Selezionare Report se il preparatore deve anche essere in grado di creare le richieste di acquisto a nome di tutti i lavoratori subordinati a quel lavoratore.</span><span class="sxs-lookup"><span data-stu-id="48579-118">Select Reporting if the preparer should also be able to create purchase requisitions on behalf of all workers who report to that worker.</span></span>  
5. <span data-ttu-id="48579-119">Nel campo Validità immettere una data.</span><span class="sxs-lookup"><span data-stu-id="48579-119">In the Effective field, enter a date.</span></span>
6. <span data-ttu-id="48579-120">Nel campo Scadenza immettere una data.</span><span class="sxs-lookup"><span data-stu-id="48579-120">In the Expiration field, enter a date.</span></span>

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a><span data-ttu-id="48579-121">Visualizzare i preparatori che hanno l'autorizzazione a creare le richieste di acquisto per un lavoratore selezionato</span><span class="sxs-lookup"><span data-stu-id="48579-121">View preparers who have permission to create purchase requisitions for a selected worker</span></span>
1. <span data-ttu-id="48579-122">Nel campo Visualizzazione corrente, selezionare 'Per richiedente'.</span><span class="sxs-lookup"><span data-stu-id="48579-122">In the Current view field, select 'By requester'.</span></span>
    * <span data-ttu-id="48579-123">Questa visualizzazione mostra un elenco dei preparatori a cui sono state concesse autorizzazioni per creare richieste di acquisto per conto di un lavoratore selezionato.</span><span class="sxs-lookup"><span data-stu-id="48579-123">This view shows a list of preparers who have been granted permission to create purchase requisitions on behalf of a selected worker.</span></span>  
2. <span data-ttu-id="48579-124">Utilizzare il filtro rapido per trovare il lavoratore appena aggiunto come richiedente.</span><span class="sxs-lookup"><span data-stu-id="48579-124">Use the Quick Filter to find the worker that you just added as the requester.</span></span>
3. <span data-ttu-id="48579-125">Selezionare il richiedente.</span><span class="sxs-lookup"><span data-stu-id="48579-125">Select the requester.</span></span>
    * <span data-ttu-id="48579-126">L'elenco Preparatore mostra le persone che hanno l'autorizzazione a ordinare articoli per conto del richiedente che è selezionato nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="48579-126">The Preparer list shows the people who have permission to order items on behalf of the requester who is selected in the left pane.</span></span>   <span data-ttu-id="48579-127">Potete aggiungere preparatori supplementari qui.</span><span class="sxs-lookup"><span data-stu-id="48579-127">You can add additional preparers here.</span></span>   <span data-ttu-id="48579-128">Questa visualizzazione inoltre vi consente di concedere al richiedente l'autorizzazione a creare le richieste in persone giuridiche e unità operative che non sono la persona giuridica o l'unità operativa primaria di quella persona.</span><span class="sxs-lookup"><span data-stu-id="48579-128">This view also lets you grant the requester permission to create requisitions in legal entities and operating units that aren't that person's primary legal entity or operating unit.</span></span>  

