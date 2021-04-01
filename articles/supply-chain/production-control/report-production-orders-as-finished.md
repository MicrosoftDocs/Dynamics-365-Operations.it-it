---
title: Dichiarare finiti gli ordini di produzione
description: Dichiara finito è una fase di produzione. In questa fase, un prodotto finito viene dichiarato e spostato dall'ordine di produzione all'inventario.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: kamaybac
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 40b2856e2495d2139664b75f747f023334a80d8c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235462"
---
# <a name="report-production-orders-as-finished"></a><span data-ttu-id="7c9dc-104">Dichiarare finiti gli ordini di produzione</span><span class="sxs-lookup"><span data-stu-id="7c9dc-104">Report production orders as finished</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7c9dc-105">Dichiara finito è una fase di produzione.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-105">Report as finished is a production stage.</span></span> <span data-ttu-id="7c9dc-106">In questa fase, un prodotto finito viene dichiarato e spostato dall'ordine di produzione all'inventario.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-106">At this stage, a finished product is reported and moved from the production order to the inventory.</span></span>

<span data-ttu-id="7c9dc-107">Quando una quantità di prodotti finiti viene dichiarata finita in un ordine di produzione, viene impostata su disponibile nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-107">When a quantity of the finished goods is reported as finished on a production order it is updated as on-hand in the inventory.</span></span> <span data-ttu-id="7c9dc-108">Quantità parziali della quantità dell'ordine originariamente pianificata possono essere dichiarate finite.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-108">Partial quantities of the originally planned order quantity can be reported as finished.</span></span> <span data-ttu-id="7c9dc-109">Quando si dichiarano finite delle quantità, è inoltre possibile dichiarare quantità di errore con una causale dell'errore associata.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-109">It is also possible to report error quantities with an associated error reason when reporting quantities as finished.</span></span> <span data-ttu-id="7c9dc-110">Quando l'ordine di produzione raggiunge la fase Dichiarato come finito significa che non vi sono più quantità da dichiarare nell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-110">When the production order reach the stage Reported as finished it indicates that no more quantity is going to be reported at the production  order.</span></span>
<span data-ttu-id="7c9dc-111">Anche le seguenti caratteristiche vengono associate al processo **Dichiara finito**:</span><span class="sxs-lookup"><span data-stu-id="7c9dc-111">The following characteristics are also associated with the **Report as finished** process:</span></span>
-   <span data-ttu-id="7c9dc-112">È possibile impostare il consumo di materie prime e di tempo che sono proporzionali alla quantità dichiarata (backflush)</span><span class="sxs-lookup"><span data-stu-id="7c9dc-112">It is possible to set up consumption of raw material and time that are proportional to the reported quantity (back-flushing)</span></span>
-   <span data-ttu-id="7c9dc-113">Il lavoro di stoccaggio può essere generato per articoli che sono abilitati per i processi di magazzino.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-113">Put-away work can be generated for items that are enabled for warehouse processes.</span></span>
-   <span data-ttu-id="7c9dc-114">Il valore di costo standard o pianificato dei prodotti finiti può essere configurato in modo da essere dichiarato nei conti CoGe.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-114">The planned or standard cost value of the finished goods can be set up to be reported to ledger accounts.</span></span>
-   <span data-ttu-id="7c9dc-115">Un ordine di controllo qualità può essere creato per la quantità dichiarata in base all'impostazione di un'associazione di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-115">A quality order can be created for the reported quantity based on the setup of a quality association.</span></span>

<span data-ttu-id="7c9dc-116">La quantità viene dichiarata nell'ubicazione di uscita.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-116">The quantity is reported to the output location.</span></span> <span data-ttu-id="7c9dc-117">Il lavoro magazzino viene quindi generato per spostare la quantità dall'ubicazione di output alla destinazione finale definita dalla direttiva di ubicazione per il lavoro di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-117">Warehouse work is then generated to move the quantity from the output location to its final destination defined by the location directive for the put-away work.</span></span>

-   <span data-ttu-id="7c9dc-118">Un ordine di controllo qualità può essere creato quando un ordine di produzione viene dichiarato finito se è stata impostata un'associazione di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-118">A quality order can be created when a production order is reported as finished if a quality association has been set up.</span></span>

## <a name="set-a-production-order-to-reporting-as-finished"></a><span data-ttu-id="7c9dc-119">Impostare un ordine di produzione su Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="7c9dc-119">Set a production order to Reporting as finished</span></span>
<span data-ttu-id="7c9dc-120">È possibile impostare un ordine di produzione su **Dichiara finito** attraverso la funzione di aggiornamento degli ordini di produzione standard o tramite i giornali di registrazione delle schede processo o delle schede cicli di lavorazione oppure attraverso il giornale **Dichiara finito**.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-120">You can set a production order to **Report as finished** through the standard production order update function, or through the route and job card journals, or through the journal **Report as finished**.</span></span> <span data-ttu-id="7c9dc-121">È inoltre possibile aggiornare la fase a **Dichiara finito** tramite le pagine Termina schede processi e Dispositivo schede processo, quando si dichiara l'ultimo processo dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-121">You can also update the stage to **Report as finished** through the job card terminal and job card device pages, when you report on the last job of the production order.</span></span> <span data-ttu-id="7c9dc-122">Infine, è possibile abilitare l'opzione **Dichiara finito** come processo per la soluzione del dispositivo di magazzino palmare.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-122">Finally, you can enable the **Report as finished** option as a process for the handheld warehouse device solution.</span></span>  





[!INCLUDE[footer-include](../../includes/footer-banner.md)]