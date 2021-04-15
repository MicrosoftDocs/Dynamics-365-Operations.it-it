---
title: Impostare i registri di beni ammortizzabili
description: Questa procedura illustra il processo di creazione di un nuovo registro beni ammortizzabili e di associazione a un gruppo di cespiti.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0ab7f9332e3224c3dadd62aae532ccffb05c82a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815598"
---
# <a name="set-up-depreciation-books"></a><span data-ttu-id="9a590-103">Impostare i registri di beni ammortizzabili</span><span class="sxs-lookup"><span data-stu-id="9a590-103">Set up depreciation books</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9a590-104">Questa procedura illustra il processo di creazione di un nuovo registro beni ammortizzabili e di associazione a un gruppo di cespiti.</span><span class="sxs-lookup"><span data-stu-id="9a590-104">This procedure walks through the process of creating a new depreciation book and associate it with a fixed asset group.</span></span> 

## <a name="create-a-depreciation-book"></a><span data-ttu-id="9a590-105">Creare un registro beni ammortizzabili</span><span class="sxs-lookup"><span data-stu-id="9a590-105">Create a depreciation book</span></span>
1. <span data-ttu-id="9a590-106">Andare a Cespiti > Impostazioni > Registri beni ammortizzabili.</span><span class="sxs-lookup"><span data-stu-id="9a590-106">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="9a590-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9a590-107">Click New.</span></span>
3. <span data-ttu-id="9a590-108">Nel campo Registro beni ammortizzabili digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="9a590-108">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="9a590-109">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="9a590-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9a590-110">Selezionare o deselezionare la casella di controllo Calcola ammortamento.</span><span class="sxs-lookup"><span data-stu-id="9a590-110">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="9a590-111">Nel campo Profilo di ammortamento fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="9a590-111">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="9a590-112">Nell'elenco trovare e selezionare il profilo di ammortamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="9a590-112">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="9a590-113">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="9a590-113">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="9a590-114">Nel campo Profilo di ammortamento alternativo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="9a590-114">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="9a590-115">Nell'elenco selezionare il profilo di ammortamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="9a590-115">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="9a590-116">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="9a590-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9a590-117">Parametri di ammortamento straordinario viene utilizzato per l'ammortamento aggiuntivo di un cespite in circostanze insolite.</span><span class="sxs-lookup"><span data-stu-id="9a590-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="9a590-118">È ad esempio possibile utilizzare questi parametri per registrare l'ammortamento causato da un disastro naturale.</span><span class="sxs-lookup"><span data-stu-id="9a590-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="9a590-119">Selezionare o deselezionare la casella di controllo Crea rettifiche all'ammortamento con rettifiche di base.</span><span class="sxs-lookup"><span data-stu-id="9a590-119">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="9a590-120">Nel campo Calendario fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="9a590-120">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="9a590-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="9a590-121">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="9a590-122">Consente di associare il registro beni ammortizzabili a un gruppo cespite.</span><span class="sxs-lookup"><span data-stu-id="9a590-122">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="9a590-123">Fare clic su Gruppi cespiti.</span><span class="sxs-lookup"><span data-stu-id="9a590-123">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="9a590-124">Nel campo Gruppo cespite fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="9a590-124">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="9a590-125">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="9a590-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="9a590-126">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="9a590-126">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="9a590-127">Nel campo Convenzione di ammortamento selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="9a590-127">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="9a590-128">Immettere un numero nel campo Vita utile.</span><span class="sxs-lookup"><span data-stu-id="9a590-128">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="9a590-129">Si noti che il valore del campo Periodi di ammortamento viene calcolato dopo aver impostato la Vita utile.</span><span class="sxs-lookup"><span data-stu-id="9a590-129">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]