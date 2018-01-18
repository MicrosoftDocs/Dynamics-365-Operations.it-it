--- 
title: " Registrare vendite e pagamenti online"
description: In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di creare ordini cliente e pagamenti per le transazioni punto vendita online.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: ddcee5b2ccb5337f2ef4c7fb4c66b2208c231d2a
ms.contentlocale: it-it
ms.lasthandoff: 01/17/2018

---
# <a name="post-online-sales-and-payments"></a><span data-ttu-id="9c74f-103"> Registrare vendite e pagamenti online</span><span class="sxs-lookup"><span data-stu-id="9c74f-103">Post online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="9c74f-104">In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di creare ordini cliente e pagamenti per le transazioni punto vendita online.</span><span class="sxs-lookup"><span data-stu-id="9c74f-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="9c74f-105">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="9c74f-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="9c74f-106">Passare a Tutte le aree di lavoro > Dati finanziari punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="9c74f-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="9c74f-107">Fare clic su Sincronizza ordini.</span><span class="sxs-lookup"><span data-stu-id="9c74f-107">Click Synchronize orders.</span></span>
3. <span data-ttu-id="9c74f-108">Nel campo Gerarchia organizzativa, selezionare "Punti vendita al dettaglio per area"</span><span class="sxs-lookup"><span data-stu-id="9c74f-108">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="9c74f-109">Selezionare un punto vendita online specifico o un nodo se si desidera creare il processo batch per un gruppo di punti vendita.</span><span class="sxs-lookup"><span data-stu-id="9c74f-109">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="9c74f-110">Fare clic sulla freccia per aggiungere la selezione.</span><span class="sxs-lookup"><span data-stu-id="9c74f-110">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="9c74f-111">Fare clic sulla scheda Esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="9c74f-111">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="9c74f-112">Selezionare o deselezionare la casella di controllo Elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="9c74f-112">Check or uncheck the Batch processing checkbox.</span></span>
6. <span data-ttu-id="9c74f-113">Fare clic su Ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="9c74f-113">Click Recurrence.</span></span>
7. <span data-ttu-id="9c74f-114">Selezionare l'opzione Nessuna data di fine.</span><span class="sxs-lookup"><span data-stu-id="9c74f-114">Select the No end date option.</span></span>
8. <span data-ttu-id="9c74f-115">Nel campo Conteggio immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="9c74f-115">In the Count field, enter a number.</span></span>
9. <span data-ttu-id="9c74f-116">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9c74f-116">Click OK.</span></span>
10. <span data-ttu-id="9c74f-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9c74f-117">Click OK.</span></span>


