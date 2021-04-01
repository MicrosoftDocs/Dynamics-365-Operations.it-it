---
title: Controllo delle ore lavorative
description: In questo argomento viene descritto il controllo delle ore lavorative in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetHourControl
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 482bee9dba22763a065c8aca93745f53f06f99be
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253712"
---
# <a name="work-hour-control"></a><span data-ttu-id="99f6d-103">Controllo delle ore lavorative</span><span class="sxs-lookup"><span data-stu-id="99f6d-103">Work hour control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="99f6d-104">In Gestione cespiti, è possibile calcolare le ore per ottenere una panoramica delle ore effettive comparate alle ore di budget in cespiti, unità funzionali o ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="99f6d-104">In Asset Management, you can calculate hours to get an overview of actual hours compared to budget hours on assets, functional locations, or work orders.</span></span> <span data-ttu-id="99f6d-105">Le ore effettive sono basate sulle transazioni registrate.</span><span class="sxs-lookup"><span data-stu-id="99f6d-105">Actual hours are based on posted transactions.</span></span>

## <a name="work-hour-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="99f6d-106">Controllo delle ore lavorative per cespiti, unità funzionali e ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="99f6d-106">Work hour control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="99f6d-107">I calcoli effettuati per cespiti, aree funzionali e ordini di lavoro sono quasi identici.</span><span class="sxs-lookup"><span data-stu-id="99f6d-107">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="99f6d-108">La sola differenza è che per i cespiti e le unità funzionali, è possibile includere cespiti secondari e ubicazioni secondarie nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="99f6d-108">Only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="99f6d-109">La data è quella di transazione alla quale la registrazione è stata registrata.</span><span class="sxs-lookup"><span data-stu-id="99f6d-109">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="99f6d-110">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **Controllo ore cespiti** o **Controllo ore unità funzionali** o **Gestione cespiti** > **Richieste di informazioni** > **Ordini di lavoro** > **Controllo ore ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="99f6d-110">Click **Asset management** > **Inquiries** > **Assets** > **Asset hour control** or **Functional location hour control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order hour control**.</span></span>

2. <span data-ttu-id="99f6d-111">Nella finestra di dialogo **Controllo ore cespiti**.</span><span class="sxs-lookup"><span data-stu-id="99f6d-111">In the **Asset hour control** dialog, .</span></span>

3. <span data-ttu-id="99f6d-112">Nella finestra di dialogo **Controllo ore cespiti** / **Controllo ore unità funzionali** / **Controllo ore ordini di lavoro**, selezionare un periodo da calcolare nei campi **Dal** e **Al**.</span><span class="sxs-lookup"><span data-stu-id="99f6d-112">In the **Asset hour control** / **Functional location hour control** / **Work order hour control** dialog, select a period to be calculated in the **From date** and **To date** fields.</span></span>

4. <span data-ttu-id="99f6d-113">Se necessario, selezionare un **Set di dimensioni finanziarie** da includere nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="99f6d-113">If required, select a **Financial dimension set** to be included in the calculation.</span></span>

5. <span data-ttu-id="99f6d-114">Impostare l'interruttore **Ignora lo zero** su "Sì" se non si desidera visualizzare i risultati contenenti zero ore.</span><span class="sxs-lookup"><span data-stu-id="99f6d-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results containing zero hours.</span></span>

6. <span data-ttu-id="99f6d-115">È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe del controllo delle ore in relazione alle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="99f6d-115">You can use the **Level** field to indicate how detailed you want the hour control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="99f6d-116">Ad esempio, se si inserisce "1" nel campo e si ha una gerarchia di unità funzionali multilivello, tutte le righe di controllo delle ore di un'unità funzionale verranno visualizzate nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali situate a un livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="99f6d-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all hour control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="99f6d-117">Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe del controllo delle ore in tutti i livelli di unità funzionali a cui sono correlate.</span><span class="sxs-lookup"><span data-stu-id="99f6d-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all hour control lines on all the functional location levels to which they are related.</span></span>

7. <span data-ttu-id="99f6d-118">Impostare l'interruttore **Includere cespiti secondari** su "Sì" per visualizzare i costi correlati ai cespiti secondari come righe separate.</span><span class="sxs-lookup"><span data-stu-id="99f6d-118">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="99f6d-119">Se si desidera limitare la ricerca, è possibile selezionare specifici cespiti/unità funzionali/ordini di lavoro nella Scheda dettaglio **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="99f6d-119">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="99f6d-120">Fare clic su **OK** per avviare il calcolo.</span><span class="sxs-lookup"><span data-stu-id="99f6d-120">Click **OK** to start the calculation.</span></span>

10. <span data-ttu-id="99f6d-121">Nella pagina **Controllo ore cespiti**, fare clic sul pulsante **Raggruppa per** per visualizzare il livello di dettagli necessario per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="99f6d-121">On the **Asset hour control** page, click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="99f6d-122">I pulsanti **Raggruppa per** selezionati sono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="99f6d-122">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="99f6d-123">Fare clic su un pulsante per attivarlo o disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="99f6d-123">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="99f6d-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="99f6d-124">Example</span></span>

<span data-ttu-id="99f6d-125">Nella schermata seguente viene illustrato un esempio di calcolo **Controllo ore cespiti**.</span><span class="sxs-lookup"><span data-stu-id="99f6d-125">The screenshot below shows an example of an **Asset hour control** calculation.</span></span>

- <span data-ttu-id="99f6d-126">Nel campo **Budget originale** sono visualizzate le ore di budget della previsione dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="99f6d-126">The **Original budget** field shows budget hours from the work order forecast.</span></span> 
- <span data-ttu-id="99f6d-127">Nel campo **Ore effettive** sono visualizzate le ore registrate negli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="99f6d-127">The **Actual hours** field shows posted hours on work orders.</span></span> 
- <span data-ttu-id="99f6d-128">Nel campo **Ore impegnate** sono visualizzate le ore totali della società in relazione agli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="99f6d-128">The **Committed hours** field shows total amount of hours that your company is committed to in relation to work orders.</span></span>

![Esempio di calcolo di controllo ore cespiti](media/04-controlling-and-reporting.png)

<span data-ttu-id="99f6d-130">Un altro metodo di eseguire un calcolo delle ore è la selezione di molteplici cespiti in **Tutti i cespiti** o **Cespiti attivi**.</span><span class="sxs-lookup"><span data-stu-id="99f6d-130">Another way of making an hour calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="99f6d-131">Quindi fare clic sul pulsante **Controllo ore** nella Scheda dettaglio **Generale**.</span><span class="sxs-lookup"><span data-stu-id="99f6d-131">Then you click the **Hour control** button on the **General** FastTab.</span></span> <span data-ttu-id="99f6d-132">I cespiti selezionati vengono inseriti automaticamente nel campo **Cespite** della Scheda dettaglio **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="99f6d-132">The selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="99f6d-133">Fare clic su **OK** nella finestra di dialogo **Controllo ore cespiti** e viene visualizzato il calcolo dei cespiti selezionati.</span><span class="sxs-lookup"><span data-stu-id="99f6d-133">Click **OK** in the **Asset hour control** dialog, and the calculation for the selected assets is shown.</span></span> <span data-ttu-id="99f6d-134">La stessa procedura può essere eseguita per le unità funzionali in **Tutte le unità funzionali** o **Unità funzionali attive** e per gli ordini di lavoro in **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="99f6d-134">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]