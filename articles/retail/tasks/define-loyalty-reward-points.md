--- 
title: " Definire punti premio fedeltà"
description: "In questa procedura vengono descritti i passaggi per definire i punti premio fedeltà."
author: scott-tucker
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 26b5615df427fb01cc4a1764507fbaa11bf0d7a0
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---
# <a name="define-loyalty-reward-points"></a><span data-ttu-id="9f00f-103"> Definire punti premio fedeltà</span><span class="sxs-lookup"><span data-stu-id="9f00f-103">Define loyalty reward points</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="9f00f-104">In questa procedura vengono descritti i passaggi per definire i punti premio fedeltà.</span><span class="sxs-lookup"><span data-stu-id="9f00f-104">This procedure walks through defining loyalty reward points.</span></span> <span data-ttu-id="9f00f-105">È necessario impostare i punti premio fedeltà prima di impostare un programma di fedeltà.</span><span class="sxs-lookup"><span data-stu-id="9f00f-105">You should set up loyalty reward points before you set up a loyalty program.</span></span> <span data-ttu-id="9f00f-106">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="9f00f-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="9f00f-107">Passare a Vendita al dettaglio e commercio > Clienti > Fedeltà > Punti premio fedeltà.</span><span class="sxs-lookup"><span data-stu-id="9f00f-107">Go to Retail and commerce > Customers > Loyalty > Loyalty reward points.</span></span>
2. <span data-ttu-id="9f00f-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9f00f-108">Click New.</span></span>
3. <span data-ttu-id="9f00f-109">Nel campo ID punto premio, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="9f00f-109">In the Reward point ID field, type a value.</span></span>
4. <span data-ttu-id="9f00f-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="9f00f-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9f00f-111">Nel campo Tipo di punto premio selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="9f00f-111">In the Reward point type field, select an option.</span></span>
    * <span data-ttu-id="9f00f-112">Selezionare Quantità se si desidera che i punti premio vengano arrotondati all'intero più vicino.</span><span class="sxs-lookup"><span data-stu-id="9f00f-112">Select Quantity if you want the reward points to be rounded to the nearest integer.</span></span> <span data-ttu-id="9f00f-113">Selezionare Importo se si desidera che i punti premio vengano arrotondati secondo le regole di arrotondamento valuta.</span><span class="sxs-lookup"><span data-stu-id="9f00f-113">Select Amount if you want the reward points to be rounded according to currency rounding rules.</span></span> <span data-ttu-id="9f00f-114">Se si seleziona Quantità, ignorare il passaggio successivo di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="9f00f-114">If you select Quantity, skip the next step of this procedure..</span></span>  
6. <span data-ttu-id="9f00f-115">Digitare un valore nel campo Valuta.</span><span class="sxs-lookup"><span data-stu-id="9f00f-115">In the Currency field, type a value.</span></span>
    * <span data-ttu-id="9f00f-116">Per i punti premio di tipo Importo, tutti i punti emessi avranno la valuta selezionata.</span><span class="sxs-lookup"><span data-stu-id="9f00f-116">For Amount type reward points, all points issued will have the selected currency.</span></span> <span data-ttu-id="9f00f-117">Per i punti di ricompensa di tipo Quantità, questo campo viene applicato, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="9f00f-117">For Quantity type reward points, this field doesn't apply—skip this step.</span></span>  
7. <span data-ttu-id="9f00f-118">Selezionare o deselezionare la casella di controllo Riscattabile.</span><span class="sxs-lookup"><span data-stu-id="9f00f-118">Check or uncheck the Redeemable checkbox.</span></span>
8. <span data-ttu-id="9f00f-119">Immettere un numero nel campo Classificazione di riscatto.</span><span class="sxs-lookup"><span data-stu-id="9f00f-119">In the Redeem ranking field, enter a number.</span></span>
    * <span data-ttu-id="9f00f-120">Classificazione di riscatto viene utilizzato quando due o più punti premio riscattabili possono essere utilizzati per pagare i prodotti.</span><span class="sxs-lookup"><span data-stu-id="9f00f-120">Redeem ranking is used when two or more redeemable reward points can be used to pay for products.</span></span> <span data-ttu-id="9f00f-121">Se i due punti premio hanno la stessa classificazione di riscatto, verrà utilizzato quello per cui è necessario ridurre il numero di punti.</span><span class="sxs-lookup"><span data-stu-id="9f00f-121">If the two reward points have the same redeem ranking, then the one that needs to lower number of points will be used.</span></span>  
9. <span data-ttu-id="9f00f-122">Immettere un numero nel campo Valore ora di scadenza.</span><span class="sxs-lookup"><span data-stu-id="9f00f-122">In the Expiration time value field, enter a number.</span></span>
    * <span data-ttu-id="9f00f-123">I punti premio scadono dopo il numero specificato di giorni, mesi o anni a partire dall'emissione.</span><span class="sxs-lookup"><span data-stu-id="9f00f-123">The reward points will expire the specified number of days, months, or years after when the points are issued.</span></span> <span data-ttu-id="9f00f-124">Il valore "0" indica che i punti premio fedeltà non hanno scadenza.</span><span class="sxs-lookup"><span data-stu-id="9f00f-124">A value of ‘0’ means the loyalty reward points will never expire.</span></span>  
10. <span data-ttu-id="9f00f-125">Selezionare un'opzione nel campo Unità ora di scadenza.</span><span class="sxs-lookup"><span data-stu-id="9f00f-125">In the Expiration time unit field, select an option.</span></span>
11. <span data-ttu-id="9f00f-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9f00f-126">Click Save.</span></span>


