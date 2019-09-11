---
title: Garanzie sui cespiti e sui tipi di cespite
description: In questo argomento viene descritto come impostare le garanzie sui cespiti e sui tipi di cespite in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3b13f8aba7e1d2448495f97a4772eb573e08c025
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874603"
---
# <a name="warranty-on-assets-and-asset-types"></a><span data-ttu-id="14a29-103">Garanzia sui cespiti e sui tipi di cespite</span><span class="sxs-lookup"><span data-stu-id="14a29-103">Warranty on assets and asset types</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="14a29-104">In questo argomento viene descritto come impostare le garanzie sui cespiti e sui tipi di cespite in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="14a29-104">This topic explains how to set up warranties on assets and asset types in Asset Management.</span></span>

## <a name="set-up-a-warranty-on-an-asset-type"></a><span data-ttu-id="14a29-105">Impostare una garanzia su un tipo di cespite</span><span class="sxs-lookup"><span data-stu-id="14a29-105">Set up a warranty on an asset type</span></span>

1. <span data-ttu-id="14a29-106">Selezionare **Gestione cespiti** \> **Impostazione** \> **Tipi di cespite** \> **Tipi di cespite**.</span><span class="sxs-lookup"><span data-stu-id="14a29-106">Select **Asset management** \> **Setup** \> **Asset types** \> **Asset types**.</span></span>
2. <span data-ttu-id="14a29-107">Nel riquadro sinistro, selezionare il tipo di cespite a cui collegare un contratto di garanzia del fornitore e quindi selezionare **Valori predefiniti tipo di cespite**.</span><span class="sxs-lookup"><span data-stu-id="14a29-107">In the left pane, select the asset type to attach a vendor warranty agreement to, and then select **Asset type defaults**.</span></span>
3. <span data-ttu-id="14a29-108">Nella Scheda dettaglio **Generale**, nel campo **Garanzia fornitore**, selezionare il contratto.</span><span class="sxs-lookup"><span data-stu-id="14a29-108">On the **General** FastTab, in the **Vendor warranty** field, select the agreement.</span></span>

## <a name="set-up-a-warranty-on-an-asset"></a><span data-ttu-id="14a29-109">Impostare una garanzia su un cespite</span><span class="sxs-lookup"><span data-stu-id="14a29-109">Set up a warranty on an asset</span></span>

1. <span data-ttu-id="14a29-110">Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti**.</span><span class="sxs-lookup"><span data-stu-id="14a29-110">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="14a29-111">Selezionare il cespite e quindi **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="14a29-111">Select the asset, and then select **Edit**.</span></span>
3. <span data-ttu-id="14a29-112">Nella Scheda dettaglio **Fornitore**, nella sezione **Garanzia fornitore**, nel campo **Garanzia**, selezionare il contratto di garanzia.</span><span class="sxs-lookup"><span data-stu-id="14a29-112">On the **Vendor** FastTab, in the **Vendor warranty** section, in the **Warranty** field, select the warranty agreement.</span></span>
4. <span data-ttu-id="14a29-113">Nei campi **Data di inizio garanzia** e **Data di fine garanzia**, selezionare le date di inizio e fine.</span><span class="sxs-lookup"><span data-stu-id="14a29-113">In the **Warranty start** and **Warranty end** fields, select the start and end dates.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="14a29-114">Se una data è selezionata nel campo **Data di inizio garanzia** in un ordine di lavoro, la garanzia diventa valida per l'ordine di lavoro in tale data.</span><span class="sxs-lookup"><span data-stu-id="14a29-114">If a date is selected in the **Warranty start** field on a work order, the warranty becomes valid for the work order on that date.</span></span> <span data-ttu-id="14a29-115">Quando si crea un ordine di lavoro, il campo **Data di inizio garanzia** viene impostato automaticamente alla data di creazione.</span><span class="sxs-lookup"><span data-stu-id="14a29-115">When you create a work order, the **Warranty start** field is automatically set to the date of creation.</span></span> <span data-ttu-id="14a29-116">Tuttavia, è possibile modificare la data di modo che corrisponda, ad esempio, alla data di inizio di un contratto di garanzia.</span><span class="sxs-lookup"><span data-stu-id="14a29-116">However, you can change the date so that it corresponds to, for example, the start date of a warranty agreement.</span></span>
    >
    > ![Figura 1](media/02-warranty.png)

> [!NOTE]
> <span data-ttu-id="14a29-118">Quando si crea un ordine di lavoro per un cespite coperto da una garanzia del fornitore, se l'ordine di lavoro ha una data di inizio prevista durante il periodo di garanzia, si riceve una notifica sul contratto di garanzia.</span><span class="sxs-lookup"><span data-stu-id="14a29-118">When you create a work order for an asset that is covered by a vendor warranty, if the work order has an expected start date during the warranty period, you receive a notification about the warranty agreement.</span></span> <span data-ttu-id="14a29-119">È quindi possibile annullare l'ordine di lavoro, come necessario.</span><span class="sxs-lookup"><span data-stu-id="14a29-119">You can then cancel the work order, as you require.</span></span>
