---
title: Creare calendari e generare orari di lavoro
description: I calendari descrivono la capacità e gli orari di lavoro delle risorse operative. Questo articolo spiega come definire un calendario di lavoro in base a un modello di orario di lavoro.
author: andreabichsel
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate, HcmPersonnelManagementWorkspace, WrkCtrGroupDateCalendar, WrkCtrDateCalendar
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af2675468dcc1f1891d24d988c32115ae57e1d2b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465464"
---
# <a name="create-calendars-and-generate-working-times"></a><span data-ttu-id="5f2c2-104">Creare calendari e generare orari di lavoro</span><span class="sxs-lookup"><span data-stu-id="5f2c2-104">Create calendars and generate working times</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="5f2c2-105">I calendari descrivono la capacità e gli orari di lavoro delle risorse operative.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-105">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="5f2c2-106">Questo articolo spiega come definire un calendario di lavoro in base a un modello di orario di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-106">This article explains how to define a work calendar based on a working time template.</span></span> <span data-ttu-id="5f2c2-107">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-107">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="5f2c2-108">Nella home page, selezionare **Gestione ciclo di vita risorse**.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-108">On the home page, select **Resource lifecycle management**.</span></span>
2. <span data-ttu-id="5f2c2-109">Selezionare **Calendari**.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-109">Select **Calendars**.</span></span>
3. <span data-ttu-id="5f2c2-110">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-110">Select **New**.</span></span>
4. <span data-ttu-id="5f2c2-111">Nel campo **Calendario**, classificare il calendario.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-111">In the **Calendar** field, classify your calendar.</span></span> <span data-ttu-id="5f2c2-112">Si tratta dell'ID del calendario, utilizzato come riferimento quando si assegnano i calendari, ad esempio a una risorsa operativa o un gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-112">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="5f2c2-113">Nel campo **Nome** immettere un nome per il calendario.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-113">In the **Name** field, name your calendar.</span></span>
6. <span data-ttu-id="5f2c2-114">Nel campo **Giorno lavorativo standard in ore**, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-114">In the **Standard work day in hours** field, enter a number.</span></span>
7. <span data-ttu-id="5f2c2-115">Verificare che la riga è selezionato, quindi selezionare **Orari di lavoro** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-115">Make sure the row is selected, then select **Working times** from the Action Pane.</span></span>
8. <span data-ttu-id="5f2c2-116">Selezionare **Componi orari di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-116">Select **Compose working times**.</span></span> <span data-ttu-id="5f2c2-117">Generare le ore lavorative per ogni giorno del periodo in cui si desidera poter programmare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="5f2c2-118">Col passare al tempo, è possibile generare gli orari di lavoro per periodi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-118">As time goes by, you can generate working times for additional periods.</span></span>  
9. <span data-ttu-id="5f2c2-119">Immettere una data nel campo **Dal**.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-119">In the **From date** field, enter a date.</span></span> <span data-ttu-id="5f2c2-120">Questo è il primo giorno in cui il calendario deve essere aperto.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-120">This is the first day that this calendar must be open.</span></span>  
10. <span data-ttu-id="5f2c2-121">Nel campo **Al** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-121">In the **To date field**, enter a date.</span></span> <span data-ttu-id="5f2c2-122">Questo è l'ultimo giorno in cui il calendario è aperto.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-122">This is the last day that this calendar is open.</span></span>  
11. <span data-ttu-id="5f2c2-123">Nel campo **Modello di orario di lavoro** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-123">In the **Working time template** field, enter or select a value.</span></span> <span data-ttu-id="5f2c2-124">Il modello di orario di lavoro definisce le ore lavorative per ogni giorno della settimana.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-124">The working time template defines the working hours for each day of the week.</span></span>  
12. <span data-ttu-id="5f2c2-125">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-125">Select **OK**.</span></span>
13. <span data-ttu-id="5f2c2-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-126">Close the page.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]