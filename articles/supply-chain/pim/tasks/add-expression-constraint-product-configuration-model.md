---
title: Aggiungere un vincolo di espressione a un modello di configurazione prodotto
description: In questa procedura vengono descritti i passaggi per aggiungere una nuova espressione di vincolo a un modello di configurazione prodotto.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cd5475e48cbcd8dcee6b228297f58e364ac503d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920883"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="62f91-103">Aggiungere un vincolo di espressione a un modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="62f91-103">Add an expression constraint to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="62f91-104">In questa procedura vengono descritti i passaggi per aggiungere una nuova espressione di vincolo a un modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="62f91-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="62f91-105">Indica come è possibile impostare come obbligatorio che la protezione angolare deve essere applicata a un altoparlante se l'utente ha selezionato che la griglia anteriore è in metallo.</span><span class="sxs-lookup"><span data-stu-id="62f91-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="62f91-106">La procedura utilizza il componente High end speaker nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="62f91-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>

## <a name="create-an-expression-constraint"></a><span data-ttu-id="62f91-107">Creare un vincolo di espressione</span><span class="sxs-lookup"><span data-stu-id="62f91-107">Create an expression constraint</span></span>

1. <span data-ttu-id="62f91-108">Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.</span><span class="sxs-lookup"><span data-stu-id="62f91-108">Go to **Product information management \> Products \> Product configuration models**.</span></span>
3. <span data-ttu-id="62f91-109">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="62f91-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="62f91-110">In questo esempio viene utilizzato il modello High end speaker.</span><span class="sxs-lookup"><span data-stu-id="62f91-110">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="62f91-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="62f91-111">In the list, select the link in the selected row.</span></span>
5. <span data-ttu-id="62f91-112">Espandere la sezione **Vincoli**.</span><span class="sxs-lookup"><span data-stu-id="62f91-112">Expand the **Constraints** section.</span></span>
6. <span data-ttu-id="62f91-113">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="62f91-113">Select **Add**.</span></span>
7. <span data-ttu-id="62f91-114">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="62f91-114">Select **Create**.</span></span>
8. <span data-ttu-id="62f91-115">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="62f91-115">In the **Name** field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="62f91-116">Immetti espressione</span><span class="sxs-lookup"><span data-stu-id="62f91-116">Enter expression</span></span>

1. <span data-ttu-id="62f91-117">Seleziona **Modifica espressione**.</span><span class="sxs-lookup"><span data-stu-id="62f91-117">Select **Edit expression**.</span></span>
    * <span data-ttu-id="62f91-118">Se si sblocca l'interfaccia utente nella registrazione attività in questa fase, è possibile utilizzare IntelliSense e l'elenco dei simboli per creare l'espressione del vincolo.</span><span class="sxs-lookup"><span data-stu-id="62f91-118">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="62f91-119">Nel campo **ConstraintBody**, immettere 'Implies[FrontGrill=="Metal", CornerProtection] '.</span><span class="sxs-lookup"><span data-stu-id="62f91-119">In the **ConstraintBody** field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="62f91-120">La logica dell'espressione dice: se la griglia anteriore è in metallo, è necessario selezionare l'opzione di protezione angolare.</span><span class="sxs-lookup"><span data-stu-id="62f91-120">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="62f91-121">Selezionare **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="62f91-121">Select **Validate**.</span></span>
    * <span data-ttu-id="62f91-122">La funzione di convalida viene eseguita tramite l'espressione di vincolo e controllata per la presenza di errori di sintassi.</span><span class="sxs-lookup"><span data-stu-id="62f91-122">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="62f91-123">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="62f91-123">Select **Close**.</span></span>
5. <span data-ttu-id="62f91-124">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="62f91-124">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]