--- 
title: Aggiungere un vincolo di espressione a un modello di configurazione prodotto
description: In questa procedura vengono descritti i passaggi per aggiungere una nuova espressione di vincolo a un modello di configurazione prodotto.
author: YuyuScheller
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8db46c5b8361c96745b440c0d0684e18c06a6c6f
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="ac235-103">Aggiungere un vincolo di espressione a un modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="ac235-103">Add an expression constraint to a product configuration model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ac235-104">In questa procedura vengono descritti i passaggi per aggiungere una nuova espressione di vincolo a un modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="ac235-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="ac235-105">Indica come è possibile impostare come obbligatorio che la protezione angolare deve essere applicata a un altoparlante se l'utente ha selezionato che la griglia anteriore è in metallo.</span><span class="sxs-lookup"><span data-stu-id="ac235-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="ac235-106">La procedura utilizza il componente High end speaker nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="ac235-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="create-an-expression-constraint"></a><span data-ttu-id="ac235-107">Creare un vincolo di espressione</span><span class="sxs-lookup"><span data-stu-id="ac235-107">Create an expression constraint</span></span>
1. <span data-ttu-id="ac235-108">Fare clic su Definizione modello di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="ac235-108">Click Product variant model definition.</span></span>
2. <span data-ttu-id="ac235-109">Fare clic su Modelli di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="ac235-109">Click Product configuration models.</span></span>
3. <span data-ttu-id="ac235-110">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ac235-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ac235-111">In questo esempio viene utilizzato il modello High end speaker.</span><span class="sxs-lookup"><span data-stu-id="ac235-111">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="ac235-112">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ac235-112">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="ac235-113">Espandere la sezione Vincoli.</span><span class="sxs-lookup"><span data-stu-id="ac235-113">Expand the Constraints section.</span></span>
6. <span data-ttu-id="ac235-114">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="ac235-114">Click Add.</span></span>
7. <span data-ttu-id="ac235-115">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="ac235-115">Click Create.</span></span>
8. <span data-ttu-id="ac235-116">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="ac235-116">In the Name field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="ac235-117">Immetti espressione</span><span class="sxs-lookup"><span data-stu-id="ac235-117">Enter expression</span></span>
1. <span data-ttu-id="ac235-118">Fare clic su Modifica espressione.</span><span class="sxs-lookup"><span data-stu-id="ac235-118">Click Edit expression.</span></span>
    * <span data-ttu-id="ac235-119">Se si sblocca l'interfaccia utente nella registrazione attività in questa fase, è possibile utilizzare IntelliSense e l'elenco dei simboli per creare l'espressione del vincolo.</span><span class="sxs-lookup"><span data-stu-id="ac235-119">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="ac235-120">Nel campo ConstraintBody, immettere 'Implies[FrontGrill=="Metal", CornerProtection] '.</span><span class="sxs-lookup"><span data-stu-id="ac235-120">In the ConstraintBody field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="ac235-121">La logica dell'espressione dice: se la griglia anteriore è in metallo, è necessario selezionare l'opzione di protezione angolare.</span><span class="sxs-lookup"><span data-stu-id="ac235-121">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="ac235-122">Fare clic su Convalida.</span><span class="sxs-lookup"><span data-stu-id="ac235-122">Click Validate.</span></span>
    * <span data-ttu-id="ac235-123">La funzione di convalida viene eseguita tramite l'espressione di vincolo e controllata per la presenza di errori di sintassi.</span><span class="sxs-lookup"><span data-stu-id="ac235-123">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="ac235-124">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="ac235-124">Click Close.</span></span>
5. <span data-ttu-id="ac235-125">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ac235-125">Click OK.</span></span>


