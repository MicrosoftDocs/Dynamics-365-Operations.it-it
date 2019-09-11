---
title: Modificare una previsione della domanda manualmente
description: Questa procedura illustra come modificare la previsione per un articolo.
author: ShylaThompson
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1ec1edb861619bae2ae3c211720b55e170b83ec9
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916624"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="785f8-103">Modificare una previsione della domanda manualmente</span><span class="sxs-lookup"><span data-stu-id="785f8-103">Modify a demand forecast manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="785f8-104">Questa procedura illustra come modificare la previsione per un articolo.</span><span class="sxs-lookup"><span data-stu-id="785f8-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="785f8-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="785f8-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="785f8-106">La procedura è destinata al responsabile di pianificazione della produzione.</span><span class="sxs-lookup"><span data-stu-id="785f8-106">This recording is intended for the production planner.</span></span> 


## <a name="modify-the-forecast-for-an-item"></a><span data-ttu-id="785f8-107">Modificare la previsione per un articolo</span><span class="sxs-lookup"><span data-stu-id="785f8-107">Modify the forecast for an item</span></span>
1. <span data-ttu-id="785f8-108">Nel **pannello di navigazione** andare a **Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="785f8-108">In the **Navigation pane**, go to **Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="785f8-109">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="785f8-109">In the list, find and select the desired record.</span></span> <span data-ttu-id="785f8-110">Selezionare l'articolo per cui si desidera modificare la previsione.</span><span class="sxs-lookup"><span data-stu-id="785f8-110">Select the item for which you want to modify the forecast.</span></span> <span data-ttu-id="785f8-111">Ad esempio, è possibile selezionare l'articolo D0001.</span><span class="sxs-lookup"><span data-stu-id="785f8-111">For example, you can select item D0001.</span></span>  
3. <span data-ttu-id="785f8-112">Nel **riquadro azioni**, fare clic su **Piano**.</span><span class="sxs-lookup"><span data-stu-id="785f8-112">On the **Action Pane**, click **Plan**.</span></span>
4. <span data-ttu-id="785f8-113">Fare clic su **Previsione della domanda**.</span><span class="sxs-lookup"><span data-stu-id="785f8-113">Click **Demand forecast**.</span></span>
5. <span data-ttu-id="785f8-114">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="785f8-114">In the list, mark the selected row.</span></span> <span data-ttu-id="785f8-115">Se non sono presenti righe di previsione, creare una nuova riga facendo clic su Nuova sulla barra dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="785f8-115">If there are no forecast lines, create a new line by clicking New on the app bar.</span></span>  
6. <span data-ttu-id="785f8-116">Nel campo **Quantità di vendita** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="785f8-116">In the **Sales quantity** field, enter a number.</span></span> <span data-ttu-id="785f8-117">Questo numero rappresenta la quantità prevista per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="785f8-117">This number represents the forecasted quantity for the item.</span></span>  
7. <span data-ttu-id="785f8-118">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="785f8-118">Click Save.</span></span>

## <a name="modify-the-forecast-in-excel"></a><span data-ttu-id="785f8-119">Modificare la previsione in Excel</span><span class="sxs-lookup"><span data-stu-id="785f8-119">Modify the forecast in Excel</span></span>
1. <span data-ttu-id="785f8-120">Fare clic su **Apri** in Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="785f8-120">Click **Open** in Microsoft Office.</span></span>
2. <span data-ttu-id="785f8-121">Fare clic sull'opzione per **modificare una previsione della domanda** in Excel.</span><span class="sxs-lookup"><span data-stu-id="785f8-121">Click **Edit Demand forecast** in Excel.</span></span> <span data-ttu-id="785f8-122">In Excel, è possibile aggiungere, eliminare e modificare le righe di previsione della domanda.</span><span class="sxs-lookup"><span data-stu-id="785f8-122">In Excel, you can add, delete and edit demand forecast lines.</span></span> <span data-ttu-id="785f8-123">Se non è possibile visualizzare i dati in Excel, è necessario accedere a Microsoft Dynamics 365 for Finance and Operations, edizione Enterprise, con l'opzione "Mantieni l'accesso" selezionata e consentire l'esecuzione dell'applicazione di connessione ai dati.</span><span class="sxs-lookup"><span data-stu-id="785f8-123">If you are not able to see the data in Excel, you need to sign in to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition with the "Keep me signed in" option enabled and you need to trust the data connection app.</span></span>  

