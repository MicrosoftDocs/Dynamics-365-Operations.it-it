---
title: Impostare i registri di beni ammortizzabili
description: Questa procedura illustra il processo di creazione di un nuovo registro beni ammortizzabili e di associazione a un gruppo di cespiti.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 03f915fa91e0eeff2f26ab9a60bbd5118317e853
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154603"
---
# <a name="set-up-depreciation-books"></a><span data-ttu-id="55969-103">Impostare i registri di beni ammortizzabili</span><span class="sxs-lookup"><span data-stu-id="55969-103">Set up depreciation books</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="55969-104">Questa procedura illustra il processo di creazione di un nuovo registro beni ammortizzabili e di associazione a un gruppo di cespiti.</span><span class="sxs-lookup"><span data-stu-id="55969-104">This procedure walks through the process of creating a new depreciation book and associate it with a fixed asset group.</span></span> 

## <a name="create-a-depreciation-book"></a><span data-ttu-id="55969-105">Creare un registro beni ammortizzabili</span><span class="sxs-lookup"><span data-stu-id="55969-105">Create a depreciation book</span></span>
1. <span data-ttu-id="55969-106">Andare a Cespiti > Impostazioni > Registri beni ammortizzabili.</span><span class="sxs-lookup"><span data-stu-id="55969-106">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="55969-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="55969-107">Click New.</span></span>
3. <span data-ttu-id="55969-108">Nel campo Registro beni ammortizzabili digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="55969-108">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="55969-109">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="55969-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="55969-110">Selezionare o deselezionare la casella di controllo Calcola ammortamento.</span><span class="sxs-lookup"><span data-stu-id="55969-110">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="55969-111">Nel campo Profilo di ammortamento fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="55969-111">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="55969-112">Nell'elenco trovare e selezionare il profilo di ammortamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="55969-112">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="55969-113">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="55969-113">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="55969-114">Nel campo Profilo di ammortamento alternativo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="55969-114">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="55969-115">Nell'elenco selezionare il profilo di ammortamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="55969-115">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="55969-116">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="55969-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="55969-117">Parametri di ammortamento straordinario viene utilizzato per l'ammortamento aggiuntivo di un cespite in circostanze insolite.</span><span class="sxs-lookup"><span data-stu-id="55969-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="55969-118">È ad esempio possibile utilizzare questi parametri per registrare l'ammortamento causato da un disastro naturale.</span><span class="sxs-lookup"><span data-stu-id="55969-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="55969-119">Selezionare o deselezionare la casella di controllo Crea rettifiche all'ammortamento con rettifiche di base.</span><span class="sxs-lookup"><span data-stu-id="55969-119">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="55969-120">Nel campo Calendario fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="55969-120">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="55969-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="55969-121">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="55969-122">Consente di associare il registro beni ammortizzabili a un gruppo cespite.</span><span class="sxs-lookup"><span data-stu-id="55969-122">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="55969-123">Fare clic su Gruppi cespiti.</span><span class="sxs-lookup"><span data-stu-id="55969-123">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="55969-124">Nel campo Gruppo cespite fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="55969-124">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="55969-125">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="55969-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="55969-126">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="55969-126">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="55969-127">Nel campo Convenzione di ammortamento selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="55969-127">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="55969-128">Immettere un numero nel campo Vita utile.</span><span class="sxs-lookup"><span data-stu-id="55969-128">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="55969-129">Si noti che il valore del campo Periodi di ammortamento viene calcolato dopo aver impostato la Vita utile.</span><span class="sxs-lookup"><span data-stu-id="55969-129">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  

