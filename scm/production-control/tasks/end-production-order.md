--- 
title: Chiudere un ordine di produzione
description: Questa procedura indica come terminare un ordine di produzione.
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 75b91ea330258a5b57e9e58cb32539d57e458f28
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="end-a-production-order"></a><span data-ttu-id="3b758-103">Chiudere un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="3b758-103">End a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3b758-104">Questa procedura indica come terminare un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="3b758-104">This procedure shows how to end a production order.</span></span> <span data-ttu-id="3b758-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="3b758-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="3b758-106">Si tratta dell'ultima procedura su sette che spiega il ciclo di vita dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="3b758-106">This is the final procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="end-a-production-order"></a><span data-ttu-id="3b758-107">Chiudere un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="3b758-107">End a production order</span></span>
1. <span data-ttu-id="3b758-108">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="3b758-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="3b758-109">Selezionare un ordine di produzione con stato Dichiarato finito.</span><span class="sxs-lookup"><span data-stu-id="3b758-109">Select a production order that has the status Reported as finished.</span></span>  
2. <span data-ttu-id="3b758-110">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="3b758-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="3b758-111">Fare clic su Fine.</span><span class="sxs-lookup"><span data-stu-id="3b758-111">Click End.</span></span>
    * <span data-ttu-id="3b758-112">In questa pagina, è possibile confermare che si desidera terminare l'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="3b758-112">On this page, you can confirm that you want to end the production order.</span></span>  
4. <span data-ttu-id="3b758-113">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="3b758-113">Click the General tab.</span></span>
5. <span data-ttu-id="3b758-114">Nel campo Data immettere una data.</span><span class="sxs-lookup"><span data-stu-id="3b758-114">In the Date field, enter a date.</span></span>
6. <span data-ttu-id="3b758-115">Nel campo Metodo scarti selezionare 'Allocazione'.</span><span class="sxs-lookup"><span data-stu-id="3b758-115">In the Scrap method field, select 'Allocation'.</span></span>
    * <span data-ttu-id="3b758-116">Quando si seleziona il metodo di allocazione, i costi dei materiali scartati vengono aggiunti ai prodotti finiti.</span><span class="sxs-lookup"><span data-stu-id="3b758-116">When you select the Allocation method, costs from the scrapped materials are added to the finished goods.</span></span>  
7. <span data-ttu-id="3b758-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3b758-117">Click OK.</span></span>

## <a name="validate-calculation-results"></a><span data-ttu-id="3b758-118">Convalidare i risultati del calcolo</span><span class="sxs-lookup"><span data-stu-id="3b758-118">Validate calculation results</span></span>
1. <span data-ttu-id="3b758-119">Nel riquadro azioni, fare clic su Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="3b758-119">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="3b758-120">Fare clic su Visualizza confronto costi.</span><span class="sxs-lookup"><span data-stu-id="3b758-120">Click View cost comparison.</span></span>
    * <span data-ttu-id="3b758-121">Dopo aver terminato l'ordine di produzione, è possibile comparare il prezzo di costo stimato al prezzo di costo realizzato per ottenere una panoramica degli scostamenti di produzione.</span><span class="sxs-lookup"><span data-stu-id="3b758-121">After you have ended the production order, you can compare the estimated cost price against the realized cost price to get an overview of the production variances.</span></span>  

