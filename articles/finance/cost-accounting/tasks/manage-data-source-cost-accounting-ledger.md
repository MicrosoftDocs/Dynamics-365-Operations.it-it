---
title: Gestire un'origine dati per un movimento CoGe di contabilità industriale
description: Utilizzare questa procedura per gestire l'origine dati della contabilità generale per un movimento CoGe di contabilità industriale.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMAXGeneralLedgerEntryProviderConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da4d351f4bce6494a107a55895866e4d3d43953f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841071"
---
# <a name="manage-a-data-source-for-the-cost-accounting-ledger"></a><span data-ttu-id="ba6fb-103">Gestire un'origine dati per un movimento CoGe di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="ba6fb-103">Manage a data source for the cost accounting ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ba6fb-104">Utilizzare questa procedura per gestire l'origine dati della contabilità generale per un movimento CoGe di contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-104">Use this procedure to manage the general ledger data source for a cost accounting ledger.</span></span> <span data-ttu-id="ba6fb-105">Prima di completare questa attività, verificare di aver eseguito le guide attività "Creare un movimento CoGe di contabilità industriale" e "Definire unità di controllo costi".</span><span class="sxs-lookup"><span data-stu-id="ba6fb-105">Before you complete this task, make sure that you play the "Create a cost accounting ledger" and "Define cost control units" task guides.</span></span> <span data-ttu-id="ba6fb-106">Questa registrazione utilizza i dati dimostrativi della società USP2.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="ba6fb-107">Andare a Contabilità industriale > Impostazione contabilità generale > Movimenti CoGe di contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-107">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="ba6fb-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ba6fb-109">Fare clic su Versioni effettive.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-109">Click Actual versions.</span></span>
4. <span data-ttu-id="ba6fb-110">Nel riquadro azioni, fare clic su Gestisci.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-110">On the Action Pane, click Manage.</span></span>
5. <span data-ttu-id="ba6fb-111">Fare clic su Contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-111">Click General ledger.</span></span>
6. <span data-ttu-id="ba6fb-112">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-112">Click New.</span></span>
7. <span data-ttu-id="ba6fb-113">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="ba6fb-114">Nel campo Provider dati immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-114">In the Data provider field, enter or select a value.</span></span>
    * <span data-ttu-id="ba6fb-115">Per questo esempio, selezionare Dynamics 365 Finance - Voci di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-115">For this example, select Dynamics 365 Finance - General ledger entries.</span></span>  
9. <span data-ttu-id="ba6fb-116">Nel campo Dimensione elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-116">In the Cost element dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="ba6fb-117">Per questo esempio, selezionare Elementi di costo.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-117">For this example, select Cost elements.</span></span>  
10. <span data-ttu-id="ba6fb-118">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-118">Click Save.</span></span>
11. <span data-ttu-id="ba6fb-119">Fare clic su Configurare provider dati.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-119">Click Configure data provider.</span></span>
12. <span data-ttu-id="ba6fb-120">Nel campo Persona giuridica immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-120">In the Legal entity field, enter or select a value.</span></span>
    * <span data-ttu-id="ba6fb-121">Per questo esempio, selezionare USP2.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-121">For this example, select USP2.</span></span>  
13. <span data-ttu-id="ba6fb-122">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-122">Click New.</span></span>
14. <span data-ttu-id="ba6fb-123">Nel campo Livello di registrazione selezionare Corrente.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-123">In the Posting layer field, select Current.</span></span>
15. <span data-ttu-id="ba6fb-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ba6fb-124">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]