---
title: Utilizzo dell'articolo
description: In questo argomento viene descritto come ottenere una panoramica sull'utilizzo di un articolo in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetItemWhereUsed, EntAssetItemWhereUsedCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ef020c6a917f0a2c358f775991182e1e494d45d6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253760"
---
# <a name="item-where-used"></a><span data-ttu-id="54875-103">Utilizzo dell'articolo</span><span class="sxs-lookup"><span data-stu-id="54875-103">Item where used</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="54875-104">È possibile eseguire un calcolo relativo a un articolo specifico per ottenere una panoramica dell'utilizzo dell'articolo in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="54875-104">You can make a calculation for a specific item to get an overview of where in Asset Management the item has been used.</span></span> <span data-ttu-id="54875-105">I risultati visualizzano il contesto in cui l'articolo è stato utilizzato durante il relativo ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="54875-105">The results show the context in which the item has been used during its lifetime.</span></span> <span data-ttu-id="54875-106">La pagina **Utilizzo dell'articolo** può essere aperta dal menu Gestione cespiti principale nonché dalle pagine seguenti:</span><span class="sxs-lookup"><span data-stu-id="54875-106">The **Item where used** page can be opened from the main Asset Management menu, and it can also be accessed from the following pages:</span></span>

- [<span data-ttu-id="54875-107">DBA cespiti</span><span class="sxs-lookup"><span data-stu-id="54875-107">Asset BOMs</span></span>](../objects/object-BOM.md)

- [<span data-ttu-id="54875-108">Pezzi di ricambio in valori predefiniti di tipo di cespite</span><span class="sxs-lookup"><span data-stu-id="54875-108">Spare parts on asset type defaults</span></span>](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [<span data-ttu-id="54875-109">Categorie di tipi di processi di manutenzione e tipi di processi di manutenzione, varianti di tipo di processi di manutenzione, commerci di processi di manutenzione e ed elenchi di controllo di manutenzione</span><span class="sxs-lookup"><span data-stu-id="54875-109">Maintenance job type categories and maintenance job types, maintenance job type variants, maintenance job trades, and maintenance checklists</span></span>](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [<span data-ttu-id="54875-110">Previsione di manutenzione</span><span class="sxs-lookup"><span data-stu-id="54875-110">Maintenance forecast</span></span>](../work-orders/maintenance-forecasts.md)

- [<span data-ttu-id="54875-111">Approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="54875-111">Procurement</span></span>](../work-orders/procurement.md)

- [<span data-ttu-id="54875-112">Acquisto ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="54875-112">Work order purchase</span></span>](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a><span data-ttu-id="54875-113">Eseguire un calcolo Utilizzo dell'articolo</span><span class="sxs-lookup"><span data-stu-id="54875-113">Make an item-where-used calculation</span></span>

1. <span data-ttu-id="54875-114">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Utilizzo dell'articolo** o selezionare il pulsante **Utilizzo dell'articolo** in una delle pagine menzionate sopra.</span><span class="sxs-lookup"><span data-stu-id="54875-114">Click **Asset management** > **Inquiries** > **Item where used**, or select the **Item where used** button on one of the pages mentioned above.</span></span>

2. <span data-ttu-id="54875-115">Nella finestra di dialogo **Utilizza dell'articolo**, selezionare l'articolo per il quale si desidera eseguire il calcolo nel campo **Numero articolo**.</span><span class="sxs-lookup"><span data-stu-id="54875-115">In the **Item where used** dialog, select the item for which you want to make the calculation in the **Item number** field.</span></span>

3. <span data-ttu-id="54875-116">È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe articolo in relazione alle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="54875-116">You can use the **Level** field to indicate how detailed you want the item lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="54875-117">Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe articolo di un'unità funzionale saranno visualizzate nel livello principale.</span><span class="sxs-lookup"><span data-stu-id="54875-117">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all item lines for a functional location will be shown on the top level.</span></span> <span data-ttu-id="54875-118">Di conseguenza, la relazione/quantità di una riga può essere aggiunta dalle unità funzionali in un livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="54875-118">Therefore, relation/quantity on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="54875-119">Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe articolo in tutti i livelli di unità funzionali a cui sono correlate.</span><span class="sxs-lookup"><span data-stu-id="54875-119">If you insert the number "0" in the **Level** field, you will see a detailed result showing all item lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="54875-120">Nella sezione **Includi** selezionare gli interruttori su "Sì" che si desidera includere nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="54875-120">In the **Include** section, select "Yes" on the toggle buttons that you want to include in the calculation.</span></span>

5. <span data-ttu-id="54875-121">Fare clic su **OK** per avviare il calcolo.</span><span class="sxs-lookup"><span data-stu-id="54875-121">Click **OK** to start the calculation.</span></span>

6. <span data-ttu-id="54875-122">Nella scheda **Utilizzo dell'articolo** selezionare i pulsanti **Raggruppa per** per visualizzare il livello di dettagli necessario per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="54875-122">On the **Item where used** tab, select the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="54875-123">I pulsanti **Raggruppa per** selezionati sono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="54875-123">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="54875-124">Fare clic su un pulsante per attivarlo o disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="54875-124">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="54875-125">Se si desidera visualizzare le dimensioni relative all'articolo, fare clic su **Visualizza dimensioni** e selezionare le dimensioni da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="54875-125">If you want to show dimensions related to the item, click **Display dimensions**, and select the dimensions to be shown.</span></span>

## <a name="example"></a><span data-ttu-id="54875-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="54875-126">Example</span></span>

<span data-ttu-id="54875-127">Nella schermata seguente, viene visualizzato un esempio di un calcolo Utilizzo dell'articolo per l'articolo numero "1000".</span><span class="sxs-lookup"><span data-stu-id="54875-127">In the screenshot below, you see an example of an item-where-used calculation for item number "1000".</span></span>

![Esempio di calcolo Utilizzo dell'articolo](media/12-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]