---
title: " Definire punti premio fedeltà"
description: In questa procedura vengono descritti i passaggi per definire i punti premio fedeltà.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailLoyaltyRewardPoints
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af217a5e756db571e3e351b743aa44b842f478f1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000486"
---
# <a name="define-loyalty-reward-points"></a><span data-ttu-id="0b7fb-103"> Definire punti premio fedeltà</span><span class="sxs-lookup"><span data-stu-id="0b7fb-103">Define loyalty reward points</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0b7fb-104">In questa procedura vengono descritti i passaggi per definire i punti premio fedeltà.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-104">This procedure walks through defining loyalty reward points.</span></span> <span data-ttu-id="0b7fb-105">È necessario impostare i punti premio fedeltà prima di impostare un programma di fedeltà.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-105">You should set up loyalty reward points before you set up a loyalty program.</span></span> <span data-ttu-id="0b7fb-106">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="0b7fb-107">Passare a Retail e Commerce > Clienti > Fedeltà > Punti premio fedeltà.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-107">Go to Retail and Commerce > Customers > Loyalty > Loyalty reward points.</span></span>
2. <span data-ttu-id="0b7fb-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-108">Click New.</span></span>
3. <span data-ttu-id="0b7fb-109">Nel campo ID punto premio, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-109">In the Reward point ID field, type a value.</span></span>
4. <span data-ttu-id="0b7fb-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="0b7fb-111">Nel campo Tipo di punto premio selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-111">In the Reward point type field, select an option.</span></span>
    * <span data-ttu-id="0b7fb-112">Selezionare Quantità se si desidera che i punti premio vengano arrotondati all'intero più vicino.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-112">Select Quantity if you want the reward points to be rounded to the nearest integer.</span></span> <span data-ttu-id="0b7fb-113">Selezionare Importo se si desidera che i punti premio vengano arrotondati secondo le regole di arrotondamento valuta.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-113">Select Amount if you want the reward points to be rounded according to currency rounding rules.</span></span> <span data-ttu-id="0b7fb-114">Se si seleziona Quantità, ignorare il passaggio successivo di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-114">If you select Quantity, skip the next step of this procedure..</span></span>  
6. <span data-ttu-id="0b7fb-115">Digitare un valore nel campo Valuta.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-115">In the Currency field, type a value.</span></span>
    * <span data-ttu-id="0b7fb-116">Per i punti premio di tipo Importo, tutti i punti emessi avranno la valuta selezionata.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-116">For Amount type reward points, all points issued will have the selected currency.</span></span> <span data-ttu-id="0b7fb-117">Per i punti di ricompensa di tipo Quantità, questo campo viene applicato, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-117">For Quantity type reward points, this field doesn't apply—skip this step.</span></span>  
7. <span data-ttu-id="0b7fb-118">Selezionare o deselezionare la casella di controllo Riscattabile.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-118">Check or uncheck the Redeemable checkbox.</span></span>
8. <span data-ttu-id="0b7fb-119">Immettere un numero nel campo Classificazione di riscatto.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-119">In the Redeem ranking field, enter a number.</span></span>
    * <span data-ttu-id="0b7fb-120">Classificazione di riscatto viene utilizzato quando due o più punti premio riscattabili possono essere utilizzati per pagare i prodotti.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-120">Redeem ranking is used when two or more redeemable reward points can be used to pay for products.</span></span> <span data-ttu-id="0b7fb-121">Se i due punti premio hanno la stessa classificazione di riscatto, verrà utilizzato quello per cui è necessario ridurre il numero di punti.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-121">If the two reward points have the same redeem ranking, then the one that needs to lower number of points will be used.</span></span>  
9. <span data-ttu-id="0b7fb-122">Immettere un numero nel campo Valore ora di scadenza.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-122">In the Expiration time value field, enter a number.</span></span>
    * <span data-ttu-id="0b7fb-123">I punti premio scadono dopo il numero specificato di giorni, mesi o anni a partire dall'emissione.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-123">The reward points will expire the specified number of days, months, or years after when the points are issued.</span></span> <span data-ttu-id="0b7fb-124">Il valore "0" indica che i punti premio fedeltà non hanno scadenza.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-124">A value of '0' means the loyalty reward points will never expire.</span></span>  
10. <span data-ttu-id="0b7fb-125">Selezionare un'opzione nel campo Unità ora di scadenza.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-125">In the Expiration time unit field, select an option.</span></span>
11. <span data-ttu-id="0b7fb-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="0b7fb-126">Click Save.</span></span>

