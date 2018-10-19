--- 
title: Impostare i registri beni ammortizzabili (maggio 2016)
description: "Questa guida attività creerà un nuovo registro beni ammortizzabili e lo assocerà a un gruppo cespite."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 1fd53ea1dff9b116d19c525c5d6967ece0993b6f
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="set-up-depreciation-books-may-2016"></a><span data-ttu-id="55c7b-103">Impostare i registri beni ammortizzabili (maggio 2016)</span><span class="sxs-lookup"><span data-stu-id="55c7b-103">Set up depreciation books (May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="55c7b-104">Questa guida attività creerà un nuovo registro beni ammortizzabili e lo assocerà a un gruppo cespite.</span><span class="sxs-lookup"><span data-stu-id="55c7b-104">This task guide will create a new depreciation book and associate it with a fixed asset group.</span></span>  <span data-ttu-id="55c7b-105">Utilizza il ruolo Ragioniere e i dati dimostrativi per la persona giuridica USMF.</span><span class="sxs-lookup"><span data-stu-id="55c7b-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-depreciation-book"></a><span data-ttu-id="55c7b-106">Creare un registro beni ammortizzabili</span><span class="sxs-lookup"><span data-stu-id="55c7b-106">Create a depreciation book</span></span>
1. <span data-ttu-id="55c7b-107">Andare a Cespiti > Impostazioni > Registri beni ammortizzabili.</span><span class="sxs-lookup"><span data-stu-id="55c7b-107">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="55c7b-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="55c7b-108">Click New.</span></span>
3. <span data-ttu-id="55c7b-109">Nel campo Registro beni ammortizzabili digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="55c7b-109">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="55c7b-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="55c7b-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="55c7b-111">Selezionare o deselezionare la casella di controllo Calcola ammortamento.</span><span class="sxs-lookup"><span data-stu-id="55c7b-111">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="55c7b-112">Nel campo Profilo di ammortamento fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="55c7b-112">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="55c7b-113">Nell'elenco trovare e selezionare il profilo di ammortamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="55c7b-113">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="55c7b-114">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="55c7b-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="55c7b-115">Nel campo Profilo di ammortamento alternativo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="55c7b-115">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="55c7b-116">Nell'elenco selezionare il profilo di ammortamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="55c7b-116">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="55c7b-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="55c7b-117">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="55c7b-118">Parametri di ammortamento straordinario viene utilizzato per l'ammortamento aggiuntivo di un cespite in circostanze insolite.</span><span class="sxs-lookup"><span data-stu-id="55c7b-118">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="55c7b-119">È ad esempio possibile utilizzare questi parametri per registrare l'ammortamento causato da un disastro naturale.</span><span class="sxs-lookup"><span data-stu-id="55c7b-119">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="55c7b-120">Selezionare o deselezionare la casella di controllo Crea rettifiche all'ammortamento con rettifiche di base.</span><span class="sxs-lookup"><span data-stu-id="55c7b-120">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="55c7b-121">Nel campo Calendario fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="55c7b-121">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="55c7b-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="55c7b-122">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="55c7b-123">Consente di associare il registro beni ammortizzabili a un gruppo cespite.</span><span class="sxs-lookup"><span data-stu-id="55c7b-123">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="55c7b-124">Fare clic su Gruppi cespiti.</span><span class="sxs-lookup"><span data-stu-id="55c7b-124">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="55c7b-125">Nel campo Gruppo cespite fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="55c7b-125">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="55c7b-126">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="55c7b-126">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="55c7b-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="55c7b-127">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="55c7b-128">Nel campo Convenzione di ammortamento selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="55c7b-128">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="55c7b-129">Immettere un numero nel campo Vita utile.</span><span class="sxs-lookup"><span data-stu-id="55c7b-129">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="55c7b-130">Si noti che il valore del campo Periodi di ammortamento viene calcolato dopo aver impostato la Vita utile.</span><span class="sxs-lookup"><span data-stu-id="55c7b-130">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  


