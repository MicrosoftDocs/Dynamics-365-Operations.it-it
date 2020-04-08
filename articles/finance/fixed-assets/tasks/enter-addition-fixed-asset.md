---
title: Immettere un cespite aggiuntivo
description: In questa procedura viene illustrato come aggiungere un componente aggiuntivo a un cespite esistente.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dc1e13863ae13daaa641f52f7a55e01fc1353dc1
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142756"
---
# <a name="enter-an-addition-to-a-fixed-asset"></a><span data-ttu-id="b7c93-103">Immettere un cespite aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="b7c93-103">Enter an addition to a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b7c93-104">In questa procedura viene illustrato come aggiungere un componente aggiuntivo a un cespite esistente.</span><span class="sxs-lookup"><span data-stu-id="b7c93-104">This procedure shows how to add an addition to an existing fixed asset.</span></span> <span data-ttu-id="b7c93-105">Lo scopo di Componenti cespite aggiuntivi è di tenere traccia dei componenti articolo aggiuntivi, di manutenzione o di miglioramenti per un cespite ed è solo informativo.</span><span class="sxs-lookup"><span data-stu-id="b7c93-105">The purpose of Fixed asset additions is to track item additions, maintenance, or improvements for an asset, and is informational only.</span></span> <span data-ttu-id="b7c93-106">Tutte le modifiche al valore o alla vita utile del cespite devono essere effettuate separatamente.</span><span class="sxs-lookup"><span data-stu-id="b7c93-106">Any changes to the fixed asset value or service life must be made separately.</span></span>   

<span data-ttu-id="b7c93-107">Nella procedura viene utilizzato il ruolo Ragioniere e i dati dimostrativi per la persona giuridica USMF.</span><span class="sxs-lookup"><span data-stu-id="b7c93-107">The procedure uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="b7c93-108">Nel pannello di navigazione, passare a **Moduli > Cespiti > Cespiti > Cespiti**.</span><span class="sxs-lookup"><span data-stu-id="b7c93-108">In the Navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="b7c93-109">Nell'elenco, individuare e selezionare il cespite per il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="b7c93-109">In the list, find and select the fixed asset for the addition.</span></span>
3. <span data-ttu-id="b7c93-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b7c93-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="b7c93-111">Nel riquadro azioni fare clic su **Cespite**.</span><span class="sxs-lookup"><span data-stu-id="b7c93-111">On the Action Pane, click **Fixed asset**.</span></span>
5. <span data-ttu-id="b7c93-112">Fare clic su **Componenti cespite aggiuntivi**.</span><span class="sxs-lookup"><span data-stu-id="b7c93-112">Click **Fixed asset additions**.</span></span>
6. <span data-ttu-id="b7c93-113">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b7c93-113">Click **New**.</span></span>
7. <span data-ttu-id="b7c93-114">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="b7c93-114">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="b7c93-115">Nel campo **Data di acquisizione**, impostare la data di acquisto o di manutenzione del componente.</span><span class="sxs-lookup"><span data-stu-id="b7c93-115">In the **Acquisition date** field, set the date of the addition purchase or service.</span></span>
9. <span data-ttu-id="b7c93-116">Nel campo **Costo unitario** Immettere il costo dell'articolo, della manutenzione o di un altro miglioramento per il cespite.</span><span class="sxs-lookup"><span data-stu-id="b7c93-116">In the **Unit cost** field, enter the cost of the item, maintenance, or other improvement for the asset.</span></span>
10. <span data-ttu-id="b7c93-117">Nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="b7c93-117">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="b7c93-118">Il costo totale non avrà impatto sul valore del cespite e viene fornito solo per tenere traccia e per scopi informativi.</span><span class="sxs-lookup"><span data-stu-id="b7c93-118">The total cost will have no impact on the value of the fixed asset and is for tracking and informational purposes only.</span></span> <span data-ttu-id="b7c93-119">Se il costo verrà capitalizzato, una transazione di rettifica di rivalutazione deve essere registrata separatamente.</span><span class="sxs-lookup"><span data-stu-id="b7c93-119">If the cost will be capitalized, then a write-up adjustment transaction must be posted separately.</span></span>  
11. <span data-ttu-id="b7c93-120">Fare clic sulla scheda **Generale**.</span><span class="sxs-lookup"><span data-stu-id="b7c93-120">Click the **General** tab.</span></span>

    * <span data-ttu-id="b7c93-121">Impostare **Aumenta la vita utile** su **Sì** se il componente aggiuntivo aumenta la vita utile del cespite.</span><span class="sxs-lookup"><span data-stu-id="b7c93-121">Set **Increases service life** to **Yes** if the addition increases the service life of the asset.</span></span>  
    * <span data-ttu-id="b7c93-122">Questo campo viene visualizzato solo a scopo informativo.</span><span class="sxs-lookup"><span data-stu-id="b7c93-122">This field is informational only.</span></span> <span data-ttu-id="b7c93-123">Per aumentare la vita utile, modificare la vita utile nei modelli di valore e/o nei registri beni ammortizzabili per il cespite.</span><span class="sxs-lookup"><span data-stu-id="b7c93-123">To increase the service life, modify the Service life on the Value models and/or Depreciation books for the asset.</span></span>  

