--- 
title: Creare un calendario e generare orari di lavoro
description: "I calendari descrivono la capacità e gli orari di lavoro delle risorse operative."
author: kherr75
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d65fe0363e418f9c2e78bd78e802a4b0ea98599c
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-calendar-and-generate-working-times"></a><span data-ttu-id="b9e12-103">Creare un calendario e generare orari di lavoro</span><span class="sxs-lookup"><span data-stu-id="b9e12-103">Create a calendar and generate working times</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b9e12-104">I calendari descrivono la capacità e gli orari di lavoro delle risorse operative.</span><span class="sxs-lookup"><span data-stu-id="b9e12-104">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="b9e12-105">Questa procedura consente di definire un calendario di lavoro in base a un modello di orario di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b9e12-105">This procedure will help you define a work calendar based on a working time template.</span></span> <span data-ttu-id="b9e12-106">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.</span><span class="sxs-lookup"><span data-stu-id="b9e12-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="b9e12-107">Andare a Tutte le aree di lavoro > Gestione ciclo di vita risorse.</span><span class="sxs-lookup"><span data-stu-id="b9e12-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="b9e12-108">Fare clic su Calendari.</span><span class="sxs-lookup"><span data-stu-id="b9e12-108">Click Calendars.</span></span>
3. <span data-ttu-id="b9e12-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b9e12-109">Click New.</span></span>
4. <span data-ttu-id="b9e12-110">Digitare un valore nel campo Calendario.</span><span class="sxs-lookup"><span data-stu-id="b9e12-110">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="b9e12-111">Si tratta dell'ID del calendario, utilizzato come riferimento quando si assegnano i calendari, ad esempio a una risorsa operativa o un gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="b9e12-111">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="b9e12-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="b9e12-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="b9e12-113">Nel campo Giorno lavorativo standard in ore, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="b9e12-113">In the Standard work day in hours field, enter a number.</span></span>
7. <span data-ttu-id="b9e12-114">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b9e12-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="b9e12-115">Fare clic su Orari di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b9e12-115">Click Working times.</span></span>
9. <span data-ttu-id="b9e12-116">Fare clic su Componi orari di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b9e12-116">Click Compose working times.</span></span>
    * <span data-ttu-id="b9e12-117">Generare le ore lavorative per ogni giorno del periodo in cui si desidera poter programmare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="b9e12-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="b9e12-118">Col passare al tempo, è possibile generare gli orari di lavoro per periodi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="b9e12-118">As time goes by, you can generate working times for additional periods.</span></span>  
10. <span data-ttu-id="b9e12-119">Immettere una data nel campo Dal.</span><span class="sxs-lookup"><span data-stu-id="b9e12-119">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="b9e12-120">Questo è il primo giorno in cui il calendario deve essere aperto.</span><span class="sxs-lookup"><span data-stu-id="b9e12-120">This is the first day that this calendar must be open.</span></span>  
11. <span data-ttu-id="b9e12-121">Nel campo Data finale immettere una data.</span><span class="sxs-lookup"><span data-stu-id="b9e12-121">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="b9e12-122">Questo è l'ultimo giorno in cui il calendario è aperto.</span><span class="sxs-lookup"><span data-stu-id="b9e12-122">This is the last day that this calendar is open.</span></span>  
12. <span data-ttu-id="b9e12-123">Nel campo Modello di orario di lavoro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b9e12-123">In the Working time template field, enter or select a value.</span></span>
    * <span data-ttu-id="b9e12-124">Il modello di orario di lavoro definisce le ore lavorative per ogni giorno della settimana.</span><span class="sxs-lookup"><span data-stu-id="b9e12-124">The working time template defines the working hours for each day of the week.</span></span>  
13. <span data-ttu-id="b9e12-125">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b9e12-125">Click OK.</span></span>
14. <span data-ttu-id="b9e12-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b9e12-126">Close the page.</span></span>

