---
title: Gestire un'origine dati per un movimento CoGe di contabilità industriale
description: Utilizzare questa procedura per gestire l'origine dati della contabilità generale per un movimento CoGe di contabilità industriale.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMAXGeneralLedgerEntryProviderConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88f5170610ea9b5634c4bf5da7079cacccdafe04
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444917"
---
# <a name="manage-a-data-source-for-the-cost-accounting-ledger"></a><span data-ttu-id="47a16-103">Gestire un'origine dati per un movimento CoGe di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="47a16-103">Manage a data source for the cost accounting ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="47a16-104">Utilizzare questa procedura per gestire l'origine dati della contabilità generale per un movimento CoGe di contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="47a16-104">Use this procedure to manage the general ledger data source for a cost accounting ledger.</span></span> <span data-ttu-id="47a16-105">Prima di completare questa attività, verificare di aver eseguito le guide attività "Creare un movimento CoGe di contabilità industriale" e "Definire unità di controllo costi".</span><span class="sxs-lookup"><span data-stu-id="47a16-105">Before you complete this task, make sure that you play the "Create a cost accounting ledger" and "Define cost control units" task guides.</span></span> <span data-ttu-id="47a16-106">Questa registrazione utilizza i dati dimostrativi della società USP2.</span><span class="sxs-lookup"><span data-stu-id="47a16-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="47a16-107">Andare a Contabilità industriale > Impostazione contabilità generale > Movimenti CoGe di contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="47a16-107">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="47a16-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="47a16-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="47a16-109">Fare clic su Versioni effettive.</span><span class="sxs-lookup"><span data-stu-id="47a16-109">Click Actual versions.</span></span>
4. <span data-ttu-id="47a16-110">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="47a16-110">On the Action Pane, click Manage.</span></span>
5. <span data-ttu-id="47a16-111">Fare clic su Contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="47a16-111">Click General ledger.</span></span>
6. <span data-ttu-id="47a16-112">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="47a16-112">Click New.</span></span>
7. <span data-ttu-id="47a16-113">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="47a16-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="47a16-114">Nel campo Provider dati immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="47a16-114">In the Data provider field, enter or select a value.</span></span>
    * <span data-ttu-id="47a16-115">Per questo esempio, selezionare Dynamics 365 Finance - Voci di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="47a16-115">For this example, select Dynamics 365 Finance - General ledger entries.</span></span>  
9. <span data-ttu-id="47a16-116">Nel campo Dimensione elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="47a16-116">In the Cost element dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="47a16-117">Per questo esempio, selezionare Elementi di costo.</span><span class="sxs-lookup"><span data-stu-id="47a16-117">For this example, select Cost elements.</span></span>  
10. <span data-ttu-id="47a16-118">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="47a16-118">Click Save.</span></span>
11. <span data-ttu-id="47a16-119">Fare clic su Configurare provider dati.</span><span class="sxs-lookup"><span data-stu-id="47a16-119">Click Configure data provider.</span></span>
12. <span data-ttu-id="47a16-120">Nel campo Persona giuridica immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="47a16-120">In the Legal entity field, enter or select a value.</span></span>
    * <span data-ttu-id="47a16-121">Per questo esempio, selezionare USP2.</span><span class="sxs-lookup"><span data-stu-id="47a16-121">For this example, select USP2.</span></span>  
13. <span data-ttu-id="47a16-122">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="47a16-122">Click New.</span></span>
14. <span data-ttu-id="47a16-123">Nel campo Livello di registrazione selezionare Corrente.</span><span class="sxs-lookup"><span data-stu-id="47a16-123">In the Posting layer field, select Current.</span></span>
15. <span data-ttu-id="47a16-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="47a16-124">Click OK.</span></span>

