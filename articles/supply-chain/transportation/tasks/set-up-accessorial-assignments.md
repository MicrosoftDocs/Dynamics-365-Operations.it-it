---
title: Impostare assegnazioni spese accessorie
description: Questa procedura mostra come impostare un'assegnazione delle spese accessorie.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9c86461f980112e2d759dfd0c905ae2ef05e7041
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214989"
---
# <a name="set-up-accessorial-assignments"></a><span data-ttu-id="1b6ac-103">Impostare assegnazioni spese accessorie</span><span class="sxs-lookup"><span data-stu-id="1b6ac-103">Set up accessorial assignments</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1b6ac-104">Questa procedura mostra come impostare un'assegnazione delle spese accessorie.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-104">This procedure shows how to set up an accessorial assignment.</span></span> <span data-ttu-id="1b6ac-105">La procedura viene in genere eseguita dal coordinatore dei trasporti.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="1b6ac-106">Prima di utilizzare questa guida, è necessario eseguire la procedura "Impostare le spese accessorie per l'hub e le spese accessorie principali".</span><span class="sxs-lookup"><span data-stu-id="1b6ac-106">Before you use this guide you need to run the "Set up hub accessorial charges and accessorial masters" guide.</span></span>


## <a name="set-up-accessorial-assignment"></a><span data-ttu-id="1b6ac-107">Impostare un'assegnazione di spese accessorie</span><span class="sxs-lookup"><span data-stu-id="1b6ac-107">Set up Accessorial assignment</span></span>
1. <span data-ttu-id="1b6ac-108">Andare a Gestione trasporto > Impostazioni > Valutazione > Assegnazioni spese accessorie.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-108">Go to Transportation management > Setup > Rating > Accessorial assignments.</span></span>
2. <span data-ttu-id="1b6ac-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-109">Click New.</span></span>
3. <span data-ttu-id="1b6ac-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="1b6ac-111">Attivare/disattivare l'espansione della sezione Dettagli.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-111">Toggle the expansion of the Details section.</span></span>
5. <span data-ttu-id="1b6ac-112">Nel campo Hub fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-112">In the Hub field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="1b6ac-113">Nell'elenco selezionare l'hub per cui sono state create spese accessorie principali quando è stata eseguita la guida "Impostare le spese accessorie per l'hub e le spese accessorie principali".</span><span class="sxs-lookup"><span data-stu-id="1b6ac-113">In the list, select the Hub that you created an accessorial master for when you ran the "Set up hub accessorial charges and accessorial masters" guide.</span></span> 
7. <span data-ttu-id="1b6ac-114">Nel campo ID spese accessorie hub fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-114">In the Hub accessorial ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="1b6ac-115">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="1b6ac-116">Attivare/disattivare l'espansione della sezione Criteri.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-116">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="1b6ac-117">Nella sezione Criteri è possibile selezionare i criteri esatti per il momento in cui applicare la spesa, in base ai valori diversi offerti in questo campo.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-117">In the Criteria section you can choose the exact criteria for when the charge should apply, based on the different values offered here.</span></span>  
10. <span data-ttu-id="1b6ac-118">Impostare l'opzione Applica sempre su Sì.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-118">Set the Always apply option to Yes.</span></span>
11. <span data-ttu-id="1b6ac-119">Selezionare un'opzione nel campo Livello di assegnazione spese accessorie.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-119">In the Accessorial assignment level field, select an option.</span></span>
12. <span data-ttu-id="1b6ac-120">Attivare/disattivare l'espansione della sezione Calcolo.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-120">Toggle the expansion of the Calculation section.</span></span>
13. <span data-ttu-id="1b6ac-121">Nel campo per il tipo di commissioni per le spese accessorie selezionare "Forfettario".</span><span class="sxs-lookup"><span data-stu-id="1b6ac-121">In the Accessorial fee type field, select 'Flat'.</span></span>
    * <span data-ttu-id="1b6ac-122">Il tipo di commissioni per le spese accessorie determina la modalità di calcolo dell'addebito effettivo.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-122">The Accessorial fee type determines how to calculate the actual charge.</span></span> <span data-ttu-id="1b6ac-123">In questo esempio si tratta di un addebito forfettario.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-123">In this example it's a flat charge.</span></span>  
14. <span data-ttu-id="1b6ac-124">Nel campo Commissioni accessorie immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-124">In the Accessorial fee field, enter a number.</span></span>
15. <span data-ttu-id="1b6ac-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-125">Click Save.</span></span>

