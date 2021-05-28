---
title: Configurare componenti di imposta per il tipo di imposta TDS
description: In questo argomento viene illustrato come impostare i componenti di ritenuta d'acconto per il tipo di imposta TDS. Descrive inoltre come definire il limite di soglia utilizzato per calcolare la TDS per ogni componente TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 6e0a6a05fcb4afb8c8965e25c3089bc1b3d98431
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023353"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a><span data-ttu-id="6376f-104">Configurare componenti di imposta per il tipo di imposta TDS</span><span class="sxs-lookup"><span data-stu-id="6376f-104">Set up tax components for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6376f-105">In questo argomento viene illustrato come impostare i componenti di ritenuta d'acconto per il tipo di imposta TDS.</span><span class="sxs-lookup"><span data-stu-id="6376f-105">This topic explains how to set up withholding tax components for the Tax Deducted at Source (TDS) tax type.</span></span> <span data-ttu-id="6376f-106">I componenti TDS sono TDS, supplemento, PE-Cess e SHE Cess.</span><span class="sxs-lookup"><span data-stu-id="6376f-106">The TDS components are TDS, surcharge, PE-Cess, and SHE Cess.</span></span> <span data-ttu-id="6376f-107">Questo argomento descrive inoltre come definire il limite utilizzato per calcolare la TDS per ogni componente TDS.</span><span class="sxs-lookup"><span data-stu-id="6376f-107">This topic also explains how to define the threshold that is used to calculate TDS for each TDS component.</span></span> <span data-ttu-id="6376f-108">Inoltre, è possibile definire una soglia di eccezione utilizzata per calcolare la TDS per ogni componente TDS.</span><span class="sxs-lookup"><span data-stu-id="6376f-108">Additionally, you can define an exception threshold that is used to calculate TDS for each TDS component.</span></span>

<span data-ttu-id="6376f-109">Per impostare i componenti TDS, procedi come segue:</span><span class="sxs-lookup"><span data-stu-id="6376f-109">Follow these steps to set up TDS components.</span></span>

1. <span data-ttu-id="6376f-110">Seleziona **Imposta \> Impostazione \> Ritenuta d'acconto \> Componenti ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="6376f-110">Go to **Tax \> Setup \> Withholding tax \> Withholding tax components**.</span></span>

    <span data-ttu-id="6376f-111">[![Pagina Componenti ritenuta d'acconto](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)</span><span class="sxs-lookup"><span data-stu-id="6376f-111">[![Withholding tax components page](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)</span></span>

2. <span data-ttu-id="6376f-112">Nel campo **Tipo di imposta**, seleziona **TDS** per impostare i componenti di ritenuta d'acconto per il tipo di imposta TDS.</span><span class="sxs-lookup"><span data-stu-id="6376f-112">In the **Tax type** field, select **TDS** to set up withholding tax components for the TDS tax type.</span></span>
3. <span data-ttu-id="6376f-113">Nel riquadro azioni seleziona **Nuova** per creare una riga.</span><span class="sxs-lookup"><span data-stu-id="6376f-113">On the Action Pane, select **New** to create a line.</span></span>
4. <span data-ttu-id="6376f-114">Nel campo **Componente ritenuta d'acconto**, immetti un nome per il componente TDS.</span><span class="sxs-lookup"><span data-stu-id="6376f-114">In the **Withholding tax component** field, enter a name for the TDS component.</span></span>
5. <span data-ttu-id="6376f-115">Nel campo **Gruppo componenti ritenuta d'acconto** seleziona il gruppo di componenti di ritenuta d'acconto TDS a cui associare il componente TDS.</span><span class="sxs-lookup"><span data-stu-id="6376f-115">In the **Withholding tax component group** field, select the TDS withholding tax component group to attach the TDS component to.</span></span>
6. <span data-ttu-id="6376f-116">Nella Scheda dettaglio **Generale**, nel campo **Descrizione** immetti una descrizione del componente TDS.</span><span class="sxs-lookup"><span data-stu-id="6376f-116">On the **General** FastTab, in the **Description** field, enter a description of  the TDS component.</span></span>
7. <span data-ttu-id="6376f-117">Nel riquadro Azioni, seleziona **Soglia** per aprire la pagina **Soglia**, in modo da poter definire il limite utilizzato per calcolare la TDS per il componente TDS.</span><span class="sxs-lookup"><span data-stu-id="6376f-117">On the Action Pane, select **Threshold** to open **Threshold** page, so that you can define the threshold that is used to calculate TDS for the TDS component.</span></span>
8. <span data-ttu-id="6376f-118">Usa i campi **Data iniziale** e **Data finale** per definire il periodo a cui si applica la soglia.</span><span class="sxs-lookup"><span data-stu-id="6376f-118">Use the **From date** and **To date** fields to define the period that the threshold is applicable to.</span></span>
9. <span data-ttu-id="6376f-119">Nella Scheda dettaglio **Generale**, in **Soglia**, immetti l'importo della soglia utilizzato per calcolare la TDS per il componente TDS.</span><span class="sxs-lookup"><span data-stu-id="6376f-119">On the **General** FastTab, in the **Threshold** field, enter the threshold amount that is used to calculate TDS for the TDS component.</span></span> <span data-ttu-id="6376f-120">L'imposta verrà dedotta all'origine solo quando l'importo cumulativo delle fatture supera la soglia.</span><span class="sxs-lookup"><span data-stu-id="6376f-120">The tax will be deducted at the source only when the cumulative invoice amount crosses the threshold.</span></span>

    <span data-ttu-id="6376f-121">Ad esempio, se l'importo della soglia è 10.000, la TDS viene calcolata dopo che l'importo cumulativo delle fatture supera 10.000 (in altre parole, quando è 10.001 o più).</span><span class="sxs-lookup"><span data-stu-id="6376f-121">For example, if the threshold amount is 10,000, TDS is calculated after the cumulative invoice amount exceeds 10,000 (in other words, when it's 10,001 or more).</span></span>

10. <span data-ttu-id="6376f-122">Nel campo **Soglia eccezione**, immetti l'importo della soglia di eccezione utilizzato per calcolare la TDS per il componente TDS.</span><span class="sxs-lookup"><span data-stu-id="6376f-122">In the **Exception threshold** field, enter the exception threshold amount that is used to calculate TDS for the TDS component.</span></span> <span data-ttu-id="6376f-123">L'imposta su una riga di fattura verrà dedotta all'origine solo quando l'importo supera la soglia.</span><span class="sxs-lookup"><span data-stu-id="6376f-123">The tax on an invoice line will be deducted at the source only when the amount crosses the exception threshold.</span></span>

    <span data-ttu-id="6376f-124">Ad esempio, se l'importo della soglia di eccezione è 5.000, la TDS viene calcolata su una specifica riga di fattura se l'importo della riga di fattura supera 5.000 (in altre parole, è 5.001 o più).</span><span class="sxs-lookup"><span data-stu-id="6376f-124">For example, if the exception threshold amount is 5,000, TDS is calculated on a specific invoice line if the invoice line amount exceeds 5,000 (in other words, if it's 5,001 or more).</span></span>

    <span data-ttu-id="6376f-125">[![Pagina Soglia](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)</span><span class="sxs-lookup"><span data-stu-id="6376f-125">[![Threshold page](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="6376f-126">L'importo della soglia di eccezione deve essere inferiore o uguale all'importo della soglia.</span><span class="sxs-lookup"><span data-stu-id="6376f-126">The exception threshold amount must be less than or equal to the threshold amount.</span></span>
    >
    > <span data-ttu-id="6376f-127">L'imposta viene dedotta per una transazione se l'importo della transazione supera la soglia di eccezione, anche se l'importo cumulativo delle fatture non supera la soglia specificata nel campo **Soglia**.</span><span class="sxs-lookup"><span data-stu-id="6376f-127">The tax is deducted for a transaction if the transaction amount crosses the exception threshold, even if the cumulative invoice amount doesn't cross the threshold that is specified in the **Threshold** field.</span></span>

11. <span data-ttu-id="6376f-128">Chiudi la pagina **Soglia** per tornare alla pagina **Componenti ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="6376f-128">Close the **Threshold** page to return to the **Withholding tax components** page.</span></span>
12. <span data-ttu-id="6376f-129">Nel riquadro Azioni seleziona **Copia** per aprire la finestra di dialogo **Copia componenti ritenuta d'acconto**, in modo da poter copiare i componenti TDS impostati per un gruppo di componenti TDS in un altro gruppo di componenti TDS.</span><span class="sxs-lookup"><span data-stu-id="6376f-129">On the Action Pane, select **Copy** to open the **Copy withholding tax components** dialog box, so that you can copy the TDS components that were set up for one TDS component group to another TDS component group.</span></span>
13. <span data-ttu-id="6376f-130">Nel campo **Da** seleziona il gruppo di componenti TDS da cui copiare i componenti TDS.</span><span class="sxs-lookup"><span data-stu-id="6376f-130">In the **From** field, select the TDS component group to copy the TDS components from.</span></span> <span data-ttu-id="6376f-131">Nel campo **A** seleziona il gruppo di componenti di ritenuta d'acconto in cui copiare i componenti TDS.</span><span class="sxs-lookup"><span data-stu-id="6376f-131">In the **To** field, select the withholding tax component group to copy the TDS components to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6376f-132">I componenti TDS comuni associati a entrambi i gruppi di componenti TDS non vengono copiati.</span><span class="sxs-lookup"><span data-stu-id="6376f-132">Common TDS components that are attached to both TDS component groups aren't copied.</span></span>

14. <span data-ttu-id="6376f-133">Seleziona **OK** per copiare e creare componenti TDS per l'altro gruppo di componenti TDS nella pagina **Componenti ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="6376f-133">Select **OK** to copy and create TDS components for the other TDS component group on the **Withholding tax components** page.</span></span>

    <span data-ttu-id="6376f-134">[![Finestra di dialogo Copia componenti ritenuta d'acconto](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)</span><span class="sxs-lookup"><span data-stu-id="6376f-134">[![Copy withholding tax components dialog box](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)</span></span>

15. <span data-ttu-id="6376f-135">Chiudi la pagina.</span><span class="sxs-lookup"><span data-stu-id="6376f-135">Close the page.</span></span>
