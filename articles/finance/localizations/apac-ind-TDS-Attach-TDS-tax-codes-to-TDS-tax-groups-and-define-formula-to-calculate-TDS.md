---
title: Associare codici imposta TDS a gruppi di imposte TDS e definire la formula per il calcolo della TDS
description: In questo argomento viene illustrato come impostare gruppi di imposte TDS e associare codici imposta TDS a gruppi di imposte TDS. Per calcolare la TDS per un gruppo di imposte TDS, devi definire la formula per i codici imposta TDS ad essa associati.
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
ms.openlocfilehash: ec0d683153bd5ab731035159d32881fbdb352d70
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023367"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a><span data-ttu-id="38da1-104">Associare codici imposta TDS a gruppi di imposte TDS e definire la formula per il calcolo della TDS</span><span class="sxs-lookup"><span data-stu-id="38da1-104">Attach TDS tax codes to TDS tax groups and define the formula for calculating TDS</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="38da1-105">In questo argomento viene illustrato come impostare gruppi di imposte TDS e associare codici imposta TDS a gruppi di imposte TDS.</span><span class="sxs-lookup"><span data-stu-id="38da1-105">This topic explains how to set up Tax Deducted at Source (TDS) tax groups and attach TDS tax codes to TDS tax groups.</span></span> <span data-ttu-id="38da1-106">Per calcolare la TDS per un gruppo di imposte TDS, devi definire la formula per i codici imposta TDS ad essa associati.</span><span class="sxs-lookup"><span data-stu-id="38da1-106">To calculate TDS for a TDS tax group, you must define the formula for TDS tax codes that are attached to it.</span></span>

<span data-ttu-id="38da1-107">Attieniti alla seguente procedura per impostare un gruppo di imposte TDS, associarvi codici imposta TDS e definire la formula per il calcolo della TDS.</span><span class="sxs-lookup"><span data-stu-id="38da1-107">Follow these steps to set up a TDS tax group, attach TDS tax codes to it, and define the formula for calculating TDS.</span></span>

1. <span data-ttu-id="38da1-108">Vai a **Imposta \> Imposte indirette \> Ritenuta d'acconto \> Gruppi ritenute d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="38da1-108">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax groups**.</span></span>

    <span data-ttu-id="38da1-109">[![Pagina Gruppi ritenute d'acconto](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)</span><span class="sxs-lookup"><span data-stu-id="38da1-109">[![Withholding tax groups page](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)</span></span>

2. <span data-ttu-id="38da1-110">Nel riquadro Azioni seleziona **Nuovo** per creare un gruppo di ritenute d'acconto per la TDS e immetti i dettagli necessari.</span><span class="sxs-lookup"><span data-stu-id="38da1-110">On the Action Pane, select **New** to create a withholding tax group for TDS, and enter the required details.</span></span>
3. <span data-ttu-id="38da1-111">Nel campo **Tipo di imposta** seleziona **TDS**.</span><span class="sxs-lookup"><span data-stu-id="38da1-111">In the **Tax type** field, select **TDS**.</span></span>
4. <span data-ttu-id="38da1-112">Nella Scheda dettaglio **Imposta** seleziona **Aggiungi** per creare una riga.</span><span class="sxs-lookup"><span data-stu-id="38da1-112">On the **Setup** FastTab, select **Add** to create a line.</span></span>
5. <span data-ttu-id="38da1-113">Nel campo **Codice ritenuta d'acconto**, seleziona il codice imposta TDS per il gruppo di imposte TDS.</span><span class="sxs-lookup"><span data-stu-id="38da1-113">In the **Withholding tax code** field, select the TDS tax code for the TDS tax group.</span></span> <span data-ttu-id="38da1-114">Il campo **Nome ritenuta d'acconto** mostra il nome del codice imposta TDS e il campo **Valore** mostra il valore.</span><span class="sxs-lookup"><span data-stu-id="38da1-114">The **Withholding tax name** field shows the name of the TDS tax code, and the **Value** field shows the value.</span></span>
6. <span data-ttu-id="38da1-115">Per ignorare il limite di soglia e il limite di soglia di eccezione definiti per il componente fiscale TDS associato al codice imposta TDS nelle transazioni TDS, seleziona la casella di controllo **Ignora soglia**.</span><span class="sxs-lookup"><span data-stu-id="38da1-115">To ignore the threshold limit and exception threshold limit that are defined for the TDS tax component that is attached to the TDS tax code in TDS transactions, select the **Overlook threshold** check box.</span></span>
7. <span data-ttu-id="38da1-116">Per impedire il calcolo del gruppo di imposte nelle transazioni, seleziona la casella di controllo **Esente**.</span><span class="sxs-lookup"><span data-stu-id="38da1-116">To prevent the tax group from being calculated in transactions, select the **Exempt** check box.</span></span>
8. <span data-ttu-id="38da1-117">Nel riquadro Azioni, seleziona **Designer** per aprire il designer formula, in modo da poter definire la formula per il calcolo della TDS per il gruppo di imposte TDS.</span><span class="sxs-lookup"><span data-stu-id="38da1-117">On the Action Pane, select **Designer** to open the formula designer, so that you can define the formula for calculating TDS for the TDS tax group.</span></span> <span data-ttu-id="38da1-118">Nella pagina **Designer**, la scheda **Imposte** mostra i codici imposta TDS che sono stati selezionati per il gruppo di imposte TDS.</span><span class="sxs-lookup"><span data-stu-id="38da1-118">On the **Designer** page, the **Taxes** tab shows the TDS tax codes that have been selected for the TDS tax group.</span></span>

    <span data-ttu-id="38da1-119">[![Pagina Designer](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)</span><span class="sxs-lookup"><span data-stu-id="38da1-119">[![Designer page](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)</span></span>

9. <span data-ttu-id="38da1-120">Nella scheda **Calcolo**, seleziona **ALT + N** per creare una riga.</span><span class="sxs-lookup"><span data-stu-id="38da1-120">On the **Calculation** tab, select **Alt+N** to create a line.</span></span> <span data-ttu-id="38da1-121">Il campo **ID** mostra l'ID priorità generato automaticamente per il calcolo della TDS.</span><span class="sxs-lookup"><span data-stu-id="38da1-121">The **ID** field shows the automatically generated priority ID for TDS calculation.</span></span>
10. <span data-ttu-id="38da1-122">Nel campo **Codice imposta**, seleziona il codice imposta TDS per cui definire la formula.</span><span class="sxs-lookup"><span data-stu-id="38da1-122">In the **Tax code** field, select the TDS tax code to define the formula for.</span></span> <span data-ttu-id="38da1-123">Tutti i codici imposta TDS che sono stati selezionati per il gruppo di imposte TDS sono disponibili per la selezione in questo campo.</span><span class="sxs-lookup"><span data-stu-id="38da1-123">All the TDS tax codes that have been selected for the TDS tax group are available for selection in this field.</span></span>
11. <span data-ttu-id="38da1-124">Nel campo **Base imponibile** seleziona la base per il calcolo della TDS:</span><span class="sxs-lookup"><span data-stu-id="38da1-124">In the **Taxable basis** field, select the basis for calculating TDS:</span></span>

    - <span data-ttu-id="38da1-125">**Importo lordo** - Calcola la TDS in base all'importo lordo della transazione (ovvero l'importo della fattura) utilizzando l'espressione di calcolo definita per il codice imposta.</span><span class="sxs-lookup"><span data-stu-id="38da1-125">**Gross amount** – Calculate TDS based on the gross transaction amount (that is, the invoice amount) by using the calculation expression that is defined for the tax code.</span></span>
    - <span data-ttu-id="38da1-126">**Importo lordo escluso** - Calcola la TDS in base all'espressione di calcolo definita per il codice imposta.</span><span class="sxs-lookup"><span data-stu-id="38da1-126">**Excl Gross amount** – Calculate TDS based on the calculation expression that is defined for the tax code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="38da1-127">Il campo **Base imponibile** non può essere impostato su **Importo lordo escluso** per il codice imposta TDS il cui ID priorità è **1**.</span><span class="sxs-lookup"><span data-stu-id="38da1-127">The **Taxable basis** field can't be set to **Excl Gross amount** for the TDS tax code that has a priority ID of **1**.</span></span>

12. <span data-ttu-id="38da1-128">Il calcolo TDS si basa sulla formula definita nel campo **Espressione di calcolo** per ogni codice imposta associato al gruppo di imposte TDS.</span><span class="sxs-lookup"><span data-stu-id="38da1-128">The TDS calculation is based on the formula that is defined in the **Calculation expression** field for each tax code that is attached to the TDS tax group.</span></span> <span data-ttu-id="38da1-129">Seleziona il segno più (**+**), il segno meno (**-**), il segno di moltiplicazione (**\**_) o il segno di divisione (_*/**) per immettere l'espressione di calcolo per il codice imposta TDS selezionato nel campo **Espressione di calcolo**.</span><span class="sxs-lookup"><span data-stu-id="38da1-129">Select the plus sign (**+**), minus sign (**-**), multiplication sign (**\**_), or division sign (_*/**) button to enter the calculation expression for the selected TDS tax code in the **Calculation expression** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="38da1-130">Nessuna espressione di calcolo può essere definita per il codice imposta TDS il cui ID priorità è **1**.</span><span class="sxs-lookup"><span data-stu-id="38da1-130">No calculation expression can be defined for the TDS tax code that has a priority ID of **1**.</span></span>

13. <span data-ttu-id="38da1-131">Per definire l'espressione di calcolo per il codice imposta TDS nel campo **Espressione di calcolo**, aggiungi i codici imposta TDS disponibili nella scheda **Imposte**. Per aggiungere codici imposta TDS nel campo **Espressione di calcolo**, puoi utilizzare uno dei seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="38da1-131">To define the calculation expression for the TDS tax code in the **Calculation expression** field, add TDS tax codes that are available on the **Taxes** tab. To add TDS tax codes in the **Calculation expression** field, you can use any of the following methods:</span></span>

    - <span data-ttu-id="38da1-132">Trascina il codice imposta richiesto dalla scheda **Imposte** al campo **Espressione di calcolo**.</span><span class="sxs-lookup"><span data-stu-id="38da1-132">Drag the required tax code from the **Taxes** tab to the **Calculation expression** field.</span></span>
    - <span data-ttu-id="38da1-133">Tocca due volte (o fai doppio clic) sul codice imposta necessario nella scheda **Imposte**.</span><span class="sxs-lookup"><span data-stu-id="38da1-133">Double-tap (or double-click) the required tax code on the **Taxes** tab.</span></span>
    - <span data-ttu-id="38da1-134">Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) sul codice imposta necessario nella scheda **Imposte**, quindi seleziona **Aggiungi codice imposta**.</span><span class="sxs-lookup"><span data-stu-id="38da1-134">Select and hold (or right-click) the required tax code on the **Taxes** tab, and then select **Add tax code**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="38da1-135">Inserisci un'espressione di calcolo prima di ogni codice imposta TDS.</span><span class="sxs-lookup"><span data-stu-id="38da1-135">Insert a calculation expression before each TDS tax code.</span></span> <span data-ttu-id="38da1-136">I codici imposta TDS aggiunti all'espressione di calcolo vengono visualizzati tra parentesi (\[...\]).</span><span class="sxs-lookup"><span data-stu-id="38da1-136">The TDS tax codes that have been added to the calculation expression appear in brackets (\[...\]).</span></span>

14. <span data-ttu-id="38da1-137">Per cancellare l'espressione di calcolo definita per un codice imposta nel campo **Espressione di calcolo**, seleziona il pulsante **C**.</span><span class="sxs-lookup"><span data-stu-id="38da1-137">To clear the calculation expression that is defined for a tax code in the **Calculation expression** field, select the **C** button.</span></span>
15. <span data-ttu-id="38da1-138">Per eliminare un record nella scheda **Calcolo**, seleziona **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="38da1-138">To delete a record on the **Calculation** tab, select **Delete**.</span></span>
16. <span data-ttu-id="38da1-139">Chiudi la pagina.</span><span class="sxs-lookup"><span data-stu-id="38da1-139">Close the page.</span></span>
