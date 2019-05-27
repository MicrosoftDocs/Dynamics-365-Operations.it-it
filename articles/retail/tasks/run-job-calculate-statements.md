---
title: Configurare ed eseguire il processo per calcolare i rendiconti
description: In questa procedura vengono descritti i passaggi per configurare ed eseguire i processi batch ricorrenti al fine di creare e calcolare i rendiconti per un punto vendita o un gruppo di punti vendita selezionato.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f52603672e95d0ae4973844851c4ed260484e5f0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550164"
---
# <a name="configure-and-run-job-to-calculate-statements"></a><span data-ttu-id="69e31-103">Configurare ed eseguire il processo per calcolare i rendiconti</span><span class="sxs-lookup"><span data-stu-id="69e31-103">Configure and run job to calculate statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="69e31-104">In questa procedura vengono descritti i passaggi per configurare ed eseguire i processi batch ricorrenti al fine di creare e calcolare i rendiconti per un punto vendita o un gruppo di punti vendita selezionato.</span><span class="sxs-lookup"><span data-stu-id="69e31-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="69e31-105">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="69e31-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="69e31-106">Passare a Tutte le aree di lavoro > Dati finanziari punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="69e31-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="69e31-107">Fare clic su Calcola rendiconti.</span><span class="sxs-lookup"><span data-stu-id="69e31-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="69e31-108">Selezionare un punto vendita specifico o un nodo se si desidera creare il processo batch per un gruppo di punti vendita.</span><span class="sxs-lookup"><span data-stu-id="69e31-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="69e31-109">Fare clic sulla freccia per aggiungere la selezione.</span><span class="sxs-lookup"><span data-stu-id="69e31-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="69e31-110">Fare clic sulla scheda Esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="69e31-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="69e31-111">In Elaborazione batch, selezionare 'Sì'.</span><span class="sxs-lookup"><span data-stu-id="69e31-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="69e31-112">Fare clic su Ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="69e31-112">Click Recurrence.</span></span>
6. <span data-ttu-id="69e31-113">Nel campo Data di inizio, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="69e31-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="69e31-114">Immettere l'ora nel campo Ora di inizio.</span><span class="sxs-lookup"><span data-stu-id="69e31-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="69e31-115">Selezionare l'opzione Nessuna data di fine.</span><span class="sxs-lookup"><span data-stu-id="69e31-115">Select the No end date option.</span></span>
9. <span data-ttu-id="69e31-116">Nel campo PatternUnit immettere 'Giorni'.</span><span class="sxs-lookup"><span data-stu-id="69e31-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="69e31-117">Nel campo Per immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="69e31-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="69e31-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="69e31-118">Click OK.</span></span>
12. <span data-ttu-id="69e31-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="69e31-119">Click OK.</span></span>

