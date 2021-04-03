---
title: Stimare un ordine di produzione
description: È possibile eseguire questa procedura utilizzando la società di dati dimostrativi USMF oppure il proprio set di dati.
author: johanhoffmann
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 58a0f8e9247e5885b1f148b3b28b7e67b1fa292d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5240319"
---
# <a name="estimate-a-production-order"></a><span data-ttu-id="feaba-103">Stimare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="feaba-103">Estimate a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="feaba-104">È possibile eseguire questa procedura utilizzando la società di dati dimostrativi USMF oppure il proprio set di dati.</span><span class="sxs-lookup"><span data-stu-id="feaba-104">You can run this procedure by using the USMF demo data company or your own data set.</span></span> <span data-ttu-id="feaba-105">In entrambi i casi, è necessario disporre di un ordine di produzione aperto con lo stato Creato.</span><span class="sxs-lookup"><span data-stu-id="feaba-105">In both cases, you need to have an open production order that has the Created status.</span></span> <span data-ttu-id="feaba-106">Si tratta della seconda procedura su sette che spiega il ciclo di vita dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="feaba-106">This is the second procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="estimate-a-production-order"></a><span data-ttu-id="feaba-107">Stimare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="feaba-107">Estimate a production order</span></span>
1. <span data-ttu-id="feaba-108">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="feaba-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="feaba-109">Selezionare un ordine con lo stato Creato nella griglia.</span><span class="sxs-lookup"><span data-stu-id="feaba-109">Select an order that has the Created status in the grid.</span></span>
3. <span data-ttu-id="feaba-110">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="feaba-110">On the Action Pane, click Production order.</span></span>
4. <span data-ttu-id="feaba-111">Fare clic su Stima.</span><span class="sxs-lookup"><span data-stu-id="feaba-111">Click Estimate.</span></span>
    * <span data-ttu-id="feaba-112">In questo passaggio, i costi stimati di un singolo ordine di produzione vengono calcolati.</span><span class="sxs-lookup"><span data-stu-id="feaba-112">In this step, the estimated costs of a single production order is calculated.</span></span>   
5. <span data-ttu-id="feaba-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="feaba-113">Click OK.</span></span>

## <a name="view-the-calculation-details"></a><span data-ttu-id="feaba-114">Visualizzare i dettagli calcolo</span><span class="sxs-lookup"><span data-stu-id="feaba-114">View the calculation details</span></span>
1. <span data-ttu-id="feaba-115">Nel riquadro azioni, fare clic su Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="feaba-115">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="feaba-116">Fare clic su Visualizza dettagli calcolo.</span><span class="sxs-lookup"><span data-stu-id="feaba-116">Click View calculation details.</span></span>
    * <span data-ttu-id="feaba-117">Questa pagina visualizza la scomposizione dei costi.</span><span class="sxs-lookup"><span data-stu-id="feaba-117">This page displays the cost breakdown.</span></span> <span data-ttu-id="feaba-118">Ad esempio, è possibile visualizzare il prezzo di costo totale per unità per il prodotto finito nella prima riga.</span><span class="sxs-lookup"><span data-stu-id="feaba-118">For example, you can view the total cost price per unit for the finished product in the first row.</span></span> <span data-ttu-id="feaba-119">Le righe successive contengono i costi in base alla distinta base, al ciclo di lavorazione produzione e ai costi indiretti.</span><span class="sxs-lookup"><span data-stu-id="feaba-119">The subsequent rows contain costs according to the bill of materials, production route, and indirect costs.</span></span>  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]