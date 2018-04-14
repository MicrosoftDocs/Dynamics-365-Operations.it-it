--- 
title: Chiusura in massa del periodo fiscale
description: "In questa procedura viene illustrato come mettere in sospeso un periodo o chiudere in modo permanente un periodo o più di una persona giuridica alla volta."
author: aprilolson
manager: AnnBe
ms.date: 10/25/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 83ecd06c1bb0b2179251fdccb3898fb3edbca51f
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="mass-financial-period-close"></a><span data-ttu-id="e1610-103">Chiusura in massa del periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="e1610-103">Mass financial period close</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e1610-104">In questa procedura viene illustrato come mettere in sospeso un periodo o chiudere in modo permanente un periodo o più di una persona giuridica alla volta.</span><span class="sxs-lookup"><span data-stu-id="e1610-104">This procedure shows how to place a period on hold or permanently close a period or more than one legal entity at a time.</span></span> <span data-ttu-id="e1610-105">Inoltre, l'attività mostrerà come limitare a moduli specifici la registrazione del gruppo utenti.</span><span class="sxs-lookup"><span data-stu-id="e1610-105">In addition, the task will show how to restrict user group posting to specific modules.</span></span>

1. <span data-ttu-id="e1610-106">Passare a Contabilità generale > Periodo chiuso > Calendari contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="e1610-106">Go to General ledger > Period close > Ledger calendars.</span></span>
    * <span data-ttu-id="e1610-107">Tenere presente che l'elenco delle persone giuridiche visualizzato dipende dal calendario fiscale selezionato nella pagina.</span><span class="sxs-lookup"><span data-stu-id="e1610-107">Note that the list of legal entities displayed is dependent on the fiscal calendar selected on the page.</span></span> <span data-ttu-id="e1610-108">Solo le persone giuridiche che usano il calendario fiscale selezionato vengono visualizzate.</span><span class="sxs-lookup"><span data-stu-id="e1610-108">Only legal entities using the selected fiscal calendar will display.</span></span>  
2. <span data-ttu-id="e1610-109">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="e1610-109">Click Edit.</span></span>
3. <span data-ttu-id="e1610-110">Selezionare il periodo per cui si desidera modificare lo stato.</span><span class="sxs-lookup"><span data-stu-id="e1610-110">Select the period for which you want to modify the status.</span></span>
4. <span data-ttu-id="e1610-111">Selezionare le persone giuridiche per cui si desidera aggiornare lo stato.</span><span class="sxs-lookup"><span data-stu-id="e1610-111">Select the legal entities for which you want to update the status.</span></span>
    * <span data-ttu-id="e1610-112">È possibile selezionare rapidamente tutte le persone giuridiche selezionando il segno di spunta sul lato in alto a sinistra della griglia.</span><span class="sxs-lookup"><span data-stu-id="e1610-112">You can quickly select all legal entities  by selecting the check mark on the upper left side of the grid.</span></span>  
5. <span data-ttu-id="e1610-113">Selezionare Aggiorna accesso al modulo per definire l'accesso di registrazione a un modulo selezionato.</span><span class="sxs-lookup"><span data-stu-id="e1610-113">Select Update module access to define the posting access to a selected module.</span></span>
    * <span data-ttu-id="e1610-114">Stato del modulo può anche essere aggiornato uno a uno modificando i record nella griglia.</span><span class="sxs-lookup"><span data-stu-id="e1610-114">The module status can also be updated one-by-one by editing the records in the grid.</span></span> <span data-ttu-id="e1610-115">Il pulsante è utile se si desidera aggiornare rapidamente i record di più persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="e1610-115">The button is useful when you want to quickly update multiple legal entity records.</span></span>  
6. <span data-ttu-id="e1610-116">Nel campo Modulo applicazione selezionare il modulo di cui si desidera aggiornare lo stato.</span><span class="sxs-lookup"><span data-stu-id="e1610-116">In the Application module, select the module that you want to update the status.</span></span> <span data-ttu-id="e1610-117">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="e1610-117">Click Select.</span></span>
7. <span data-ttu-id="e1610-118">In Livello di accesso, selezionare Tutti, Nessuno o un gruppo utenti specifico.</span><span class="sxs-lookup"><span data-stu-id="e1610-118">In the Access level, select All, None, or a specific user group.</span></span> <span data-ttu-id="e1610-119">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="e1610-119">Click Select.</span></span>
    * <span data-ttu-id="e1610-120">Tutti indica che tutti gli utenti con accesso in modifica nel modulo possono registrare se il periodo è aperto.</span><span class="sxs-lookup"><span data-stu-id="e1610-120">All indicates all users with edit access to the module can post if the period is open.</span></span> <span data-ttu-id="e1610-121">Nessuno indica che gli utente non possono registrare nel modulo se il periodo è aperto.</span><span class="sxs-lookup"><span data-stu-id="e1610-121">None indicates that users cannot post to the module if the period is open.</span></span> <span data-ttu-id="e1610-122">Un gruppo di utenti specifico indica che solo gli utenti nel gruppo possono effettuare registrazioni nel modulo se il periodo è aperto.</span><span class="sxs-lookup"><span data-stu-id="e1610-122">A specific user group indicates only users in the group are able to post to the module if the period is open.</span></span>  
8. <span data-ttu-id="e1610-123">Fare clic su Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="e1610-123">Click Update.</span></span>
9. <span data-ttu-id="e1610-124">Selezionare un altro periodo per aggiornare lo stato.</span><span class="sxs-lookup"><span data-stu-id="e1610-124">Select another period to update the status.</span></span>
10. <span data-ttu-id="e1610-125">Selezionare le persone giuridiche per cui si desidera aggiornare lo stato del periodo.</span><span class="sxs-lookup"><span data-stu-id="e1610-125">Select the legal entities for which you want to update the period status.</span></span>
11. <span data-ttu-id="e1610-126">Selezionare Aggiorna stato periodo e impostare lo stato su In attesa, Aperto o Chiuso in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="e1610-126">Select Update period status and set the status of On hold, Open, or Permanently closed.</span></span>
    * <span data-ttu-id="e1610-127">Aperto indica che nel periodo può essere registrato, se l'utente può accedere.</span><span class="sxs-lookup"><span data-stu-id="e1610-127">Open indicates the period can be posted to, provided the user has access.</span></span> <span data-ttu-id="e1610-128">In attesa significa che il periodo non può essere registrato, ma il periodo può essere riaperto.</span><span class="sxs-lookup"><span data-stu-id="e1610-128">On hold means the period cannot be posted to, but the period can be reopened.</span></span> <span data-ttu-id="e1610-129">Chiuso in modo permanente significa che il periodo è chiuso e non può mai essere aperto.</span><span class="sxs-lookup"><span data-stu-id="e1610-129">Permanently closed means the period is closed and can never be opened.</span></span> <span data-ttu-id="e1610-130">Non possono essere registrate rettifiche.</span><span class="sxs-lookup"><span data-stu-id="e1610-130">Adjustments cannot be posted.</span></span> <span data-ttu-id="e1610-131">Non si consiglia di impostare un periodo su Chiuso in modo permanente fino a che tutte le rettifiche e i controlli sono completi.</span><span class="sxs-lookup"><span data-stu-id="e1610-131">We do not recommend setting a period to Permanently closed until all adjustments and audits are complete.</span></span>  
12. <span data-ttu-id="e1610-132">Fare clic su Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="e1610-132">Click Update.</span></span>


