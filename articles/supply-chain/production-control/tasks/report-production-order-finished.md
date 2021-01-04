---
title: Dichiarazione di un ordine di produzione come finito
description: Questa procedura indica come dichiarare un ordine di produzione come finito.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd, ProdSetupReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 93193e6365bcf82fbbf93af81e2581a358899fa1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430841"
---
# <a name="report-a-production-order-as-finished"></a><span data-ttu-id="48e72-103">Dichiarazione di un ordine di produzione come finito</span><span class="sxs-lookup"><span data-stu-id="48e72-103">Report a production order as finished</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="48e72-104">Questa procedura indica come dichiarare un ordine di produzione come finito.</span><span class="sxs-lookup"><span data-stu-id="48e72-104">This procedure shows how to report a production order as finished.</span></span> <span data-ttu-id="48e72-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="48e72-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="48e72-106">Si tratta della sesta procedura su sette che spiega il ciclo di vita dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="48e72-106">This is the sixth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="report-a-production-order-as-finished"></a><span data-ttu-id="48e72-107">Dichiarazione di un ordine di produzione come finito</span><span class="sxs-lookup"><span data-stu-id="48e72-107">Report a production order as finished</span></span>
1. <span data-ttu-id="48e72-108">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="48e72-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="48e72-109">Selezionare un ordine di produzione con stato Avviato.</span><span class="sxs-lookup"><span data-stu-id="48e72-109">Select a production order that has the Started status.</span></span>  
2. <span data-ttu-id="48e72-110">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="48e72-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="48e72-111">Fare clic su Dichiarazione di finito.</span><span class="sxs-lookup"><span data-stu-id="48e72-111">Click Report as finished.</span></span>
    * <span data-ttu-id="48e72-112">In questa pagina, è possibile confermare la quantità di prodotto finito da dichiarare come finita.</span><span class="sxs-lookup"><span data-stu-id="48e72-112">On this page, you can confirm the quantity of the finished product to be reported as finished.</span></span>  
4. <span data-ttu-id="48e72-113">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="48e72-113">Click the General tab.</span></span>
5. <span data-ttu-id="48e72-114">Impostare Quantità idonea su '18'.</span><span class="sxs-lookup"><span data-stu-id="48e72-114">Set Good quantity to '18'.</span></span>
6. <span data-ttu-id="48e72-115">Impostare Quantità difettosa su '2'.</span><span class="sxs-lookup"><span data-stu-id="48e72-115">Set Error quantity to '2'.</span></span>
7. <span data-ttu-id="48e72-116">Nel campo Causa dell'errore, selezionare 'Materiale'.</span><span class="sxs-lookup"><span data-stu-id="48e72-116">In the Error cause field, select 'Material'.</span></span>
8. <span data-ttu-id="48e72-117">Selezionare o deselezionare la casella di controllo Processo finale.</span><span class="sxs-lookup"><span data-stu-id="48e72-117">Select or clear the End job check box.</span></span>
9. <span data-ttu-id="48e72-118">Selezionare o deselezionare la casella di controllo Accetta errore.</span><span class="sxs-lookup"><span data-stu-id="48e72-118">Select or clear the Accept error check box.</span></span>
10. <span data-ttu-id="48e72-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="48e72-119">Click OK.</span></span>

## <a name="verify-the-report-as-finished-journal"></a><span data-ttu-id="48e72-120">Verificare il giornale di registrazione dichiarazioni di finito</span><span class="sxs-lookup"><span data-stu-id="48e72-120">Verify the Report as finished journal</span></span>
1. <span data-ttu-id="48e72-121">Nel riquadro azioni fare clic su Visualizza.</span><span class="sxs-lookup"><span data-stu-id="48e72-121">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="48e72-122">Fare clic su Dichiarato finito.</span><span class="sxs-lookup"><span data-stu-id="48e72-122">Click Reported as finished.</span></span>
3. <span data-ttu-id="48e72-123">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="48e72-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="48e72-124">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="48e72-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="48e72-125">Il giornale di registrazione dichiarazioni di finito è stato registrato.</span><span class="sxs-lookup"><span data-stu-id="48e72-125">The Report as finished journal is posted.</span></span> <span data-ttu-id="48e72-126">Se si desidera apportare rettifiche al giornale di registrazione, è possibile creare manualmente un nuovo giornale di registrazione in cui è possibile apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="48e72-126">If you want to make adjustments to the journal, you can manually create  a new journal where you can make changes.</span></span>  

