---
title: Visualizza una domanda interaziendale pianificata in uscita
description: In questa procedura viene descritto come visualizzare tutti gli ordini pianificati che verranno evasi da un fornitore interaziendale.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c45593fc36763e78ff186aeefdbf168bf168612
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835912"
---
# <a name="view-outbound-planned-intercompany-demand"></a><span data-ttu-id="784da-103">Visualizza una domanda interaziendale pianificata in uscita</span><span class="sxs-lookup"><span data-stu-id="784da-103">View outbound planned intercompany demand</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="784da-104">In questa procedura viene descritto come visualizzare tutti gli ordini pianificati che verranno evasi da un fornitore interaziendale.</span><span class="sxs-lookup"><span data-stu-id="784da-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="784da-105">La società di dati dimostrativi utilizzata per creare questa procedura è DEMF.</span><span class="sxs-lookup"><span data-stu-id="784da-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="784da-106">Fare clic su Pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="784da-106">Click Master planning.</span></span>
2. <span data-ttu-id="784da-107">Nel campo Piano immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="784da-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="784da-108">Selezionare il piano 10 nel campo Piano.</span><span class="sxs-lookup"><span data-stu-id="784da-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="784da-109">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="784da-109">Click Run.</span></span>
4. <span data-ttu-id="784da-110">Nel campo Numero di thread immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="784da-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="784da-111">Questo rappresenta il numero di thread paralleli da utilizzare per la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="784da-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="784da-112">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="784da-112">Click OK.</span></span>
    * <span data-ttu-id="784da-113">Questa operazione potrebbe richiedere tempo.</span><span class="sxs-lookup"><span data-stu-id="784da-113">This may take a while.</span></span>  
6. <span data-ttu-id="784da-114">Fare clic su Domanda interaziendale pianificata.</span><span class="sxs-lookup"><span data-stu-id="784da-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="784da-115">Fare clic su Domanda interaziendale pianificata in uscita.</span><span class="sxs-lookup"><span data-stu-id="784da-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="784da-116">In questa pagina è disponibile una panoramica di tutta la domanda pianificata che verrà evasa da un fornitore interno della supply chain.</span><span class="sxs-lookup"><span data-stu-id="784da-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="784da-117">Espandere la sezione Dettagli domanda a monte.</span><span class="sxs-lookup"><span data-stu-id="784da-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="784da-118">In questa sezione, è possibile visualizzare i dettagli su come la domanda verrà evasa.</span><span class="sxs-lookup"><span data-stu-id="784da-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="784da-119">Può essere necessario attendere l'esecuzione della pianificazione generale nella società di rifornimento per poter visualizzare informazioni aggiuntive qui.</span><span class="sxs-lookup"><span data-stu-id="784da-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  

