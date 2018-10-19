--- 
title: Registrazione di vendite e pagamenti online
description: In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di creare ordini cliente e pagamenti per le transazioni punto vendita online.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 13839bbe6ca03f3cfc7036fce87477bf7d5af2a7
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="9d87d-103">Registrazione di vendite e pagamenti online</span><span class="sxs-lookup"><span data-stu-id="9d87d-103">Posting of online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="9d87d-104">In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di creare ordini cliente e pagamenti per le transazioni punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="9d87d-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="9d87d-105">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="9d87d-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="9d87d-106">Passare a Tutte le aree di lavoro > Dati finanziari punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="9d87d-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="9d87d-107">Fare clic su Sincronizza ordini.</span><span class="sxs-lookup"><span data-stu-id="9d87d-107">Click Synchronize orders.</span></span>
3. <span data-ttu-id="9d87d-108">Nel campo Gerarchia organizzativa, selezionare "Punti vendita al dettaglio per area"</span><span class="sxs-lookup"><span data-stu-id="9d87d-108">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="9d87d-109">Selezionare un punto vendita online specifico o un nodo se si desidera creare il processo batch per un gruppo di punti vendita.</span><span class="sxs-lookup"><span data-stu-id="9d87d-109">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="9d87d-110">Fare clic sulla freccia per aggiungere la selezione.</span><span class="sxs-lookup"><span data-stu-id="9d87d-110">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="9d87d-111">Fare clic sulla scheda Esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="9d87d-111">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="9d87d-112">Selezionare o deselezionare la casella di controllo Elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="9d87d-112">Check or uncheck the Batch processing checkbox.</span></span>
6. <span data-ttu-id="9d87d-113">Fare clic su Ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="9d87d-113">Click Recurrence.</span></span>
7. <span data-ttu-id="9d87d-114">Selezionare l'opzione Nessuna data di fine.</span><span class="sxs-lookup"><span data-stu-id="9d87d-114">Select the No end date option.</span></span>
8. <span data-ttu-id="9d87d-115">Nel campo Conteggio immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="9d87d-115">In the Count field, enter a number.</span></span>
9. <span data-ttu-id="9d87d-116">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9d87d-116">Click OK.</span></span>
10. <span data-ttu-id="9d87d-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9d87d-117">Click OK.</span></span>


