---
title: Controllo costo degli errori dei cespiti
description: In questo argomento viene descritto il controllo dei costi relativi agli errori di cespite in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 93bd6fb320822f17af5725e227936df623f8d0be
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431047"
---
# <a name="asset-fault-cost-control"></a><span data-ttu-id="8f6ff-103">Controllo costo degli errori dei cespiti</span><span class="sxs-lookup"><span data-stu-id="8f6ff-103">Asset fault cost control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="8f6ff-104">In Gestione cespiti, è possibile calcolare i costi nelle registrazioni di errore di cespite per ottenere una panoramica dei costi effettivi rispetto ai costi in budget.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-104">In Asset Management, you can calculate costs on asset fault registrations to get an overview of actual costs compared to budget costs.</span></span> <span data-ttu-id="8f6ff-105">I costi effettivi sono basati sulle transazioni registrate.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-105">Actual costs are based on posted transactions.</span></span> <span data-ttu-id="8f6ff-106">La data è quella in cui il sintomo dell'errore è stato registrato.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-106">The date is the fault date on which the symptom was recorded.</span></span>

1. <span data-ttu-id="8f6ff-107">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Errore di cespite** > **Controllo costo degli errori dei cespiti**.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-107">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault cost control**.</span></span>

2. <span data-ttu-id="8f6ff-108">Nella finestra di dialogo **Controllo costo degli errori dei cespiti**, selezionare un set di dimensioni finanziarie da includere nel calcolo, se necessario.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-108">In the **Asset fault cost control** dialog, select a financial dimension set to be included in the calculation, if required.</span></span>

4. <span data-ttu-id="8f6ff-109">Impostare l'interruttore **Ignora lo zero** su "Sì" se non si desidera visualizzare i risultati con un costo zero.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-109">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="8f6ff-110">È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe del controllo dei costi in relazione alle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-110">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="8f6ff-111">Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe del controllo dei costi relativi agli errori di cespite per un'unità funzionale verranno visualizzate nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali in un livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="8f6ff-112">Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe del controllo dei costi degli errori di cespite in tutti i livelli di unità funzionali a cui sono correlate.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault cost control lines on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="8f6ff-113">Se si desidera limitare la ricerca, è possibile selezionare specifici cespiti, date di errore e cause di errore nella Scheda dettaglio **Record da includere**.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-113">If you want to limit the search, you can select specific assets, fault dates, and fault causes on the **Records to include** FastTab.</span></span>

7. <span data-ttu-id="8f6ff-114">Fare clic su **OK** per avviare il calcolo.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-114">Click **OK** to start the calculation.</span></span>

8. <span data-ttu-id="8f6ff-115">Fare clic sui pulsanti **Raggruppa per** per visualizzare il livello di dettagli necessario per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-115">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="8f6ff-116">I pulsanti **Raggruppa per** selezionati sono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-116">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="8f6ff-117">Fare clic su un pulsante per attivarlo o disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-117">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="8f6ff-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f6ff-118">Example</span></span>

<span data-ttu-id="8f6ff-119">In questo esempio viene illustrato un calcolo del controllo costi dell'errore cespiti.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-119">This example shows an asset fault cost control calculation.</span></span>

- <span data-ttu-id="8f6ff-120">Nel campo **Budget originale** sono visualizzati i costi in budget della previsione dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-120">The **Original budget** field shows budget costs from the work order forecast.</span></span> 
- <span data-ttu-id="8f6ff-121">Nel campo **Costo effettivo** sono visualizzati i costi registrati negli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-121">The **Actual cost** field shows posted costs on work orders.</span></span> 
- <span data-ttu-id="8f6ff-122">Nel campo **Costo impegnato** sono visualizzati i costi totali della società in relazione agli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8f6ff-122">The **Committed cost** field shows total costs that your company is committed to in relation to work orders.</span></span>

    ![Figura 1](media/05-controlling-and-reporting.png)

<span data-ttu-id="8f6ff-124">Per informazioni su come impostare gli errori, fare riferimento alla sezione [Gestione errori](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="8f6ff-124">For information about how to set up faults, see the [Fault management](../setup-for-work-orders/fault-management.md) topic.</span></span>
