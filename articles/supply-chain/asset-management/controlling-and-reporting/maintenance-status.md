---
title: Stato della manutenzione
description: In questo argomento viene illustrato come calcolare lo stato della manutenzione in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f336086838632dd3f464de2870e9a9197746daa
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652128"
---
# <a name="maintenance-status"></a><span data-ttu-id="c9ead-103">Stato della manutenzione</span><span class="sxs-lookup"><span data-stu-id="c9ead-103">Maintenance status</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="c9ead-104">In Gestione cespiti, è possibile eseguire un calcolo per un periodo specifico per visualizzare una panoramica delle richieste di intervento di manutenzione nuove, attive e completate, degli ordini di lavoro e delle attività dei tempi di fermo per la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="c9ead-104">In Asset Management, you can make an overview calculation for a specific period for new, active, and completed maintenance requests, work orders, and maintenance downtime activities.</span></span> <span data-ttu-id="c9ead-105">È inoltre possibile visualizzare il numero di valutazioni delle condizioni completate per lo stesso periodo.</span><span class="sxs-lookup"><span data-stu-id="c9ead-105">You can also see the number of completed condition assessments for the same period.</span></span> <span data-ttu-id="c9ead-106">Utilizzare questo calcolo per ottenere una panoramica del carico di lavoro relativo alle richieste di intervento di manutenzione ricevute e completate e agli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c9ead-106">Use this calculation to get an overview of workload for incoming and completed maintenance requests and work orders.</span></span>

## <a name="make-a-maintenance-status-calculation"></a><span data-ttu-id="c9ead-107">Eseguire il calcolo di uno stato di manutenzione</span><span class="sxs-lookup"><span data-stu-id="c9ead-107">Make a maintenance status calculation</span></span>

1. <span data-ttu-id="c9ead-108">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Stato della manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="c9ead-108">Click **Asset management** > **Inquiries** > **Maintenance status**.</span></span>

2. <span data-ttu-id="c9ead-109">Nella finestra di dialogo **Calcola stato**, selezionare l'intervallo di tempo per il quale si desidera eseguire il calcolo nei campi **Dal** e **Al**.</span><span class="sxs-lookup"><span data-stu-id="c9ead-109">In the **Calculate status** dialog, select the time range that you want to make the calculation in the **From date** and **To date** fields.</span></span>

3. <span data-ttu-id="c9ead-110">È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe di manutenzione in relazione alle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="c9ead-110">You can use the **Level** field to indicate how detailed you want the maintenance lines to be regarding functional locations.</span></span> 

  <span data-ttu-id="c9ead-111">Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe di manutenzione per un'unità funzionale verranno visualizzate nel livello principale, quindi lo stato in una riga può essere aggiunto dalle unità funzionali situate a un livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="c9ead-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance lines for a functional location will be shown on the top level, and therefore the status on a line may be added up from functional locations located at a lower level.</span></span> 
  
  <span data-ttu-id="c9ead-112">Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe di manutenzione in tutti i livelli di unità funzionali a cui sono correlate.</span><span class="sxs-lookup"><span data-stu-id="c9ead-112">If you insert the number "0" in the **Level** field, you see a detailed result showing all maintenance lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="c9ead-113">Fare clic su **OK** per avviare il calcolo.</span><span class="sxs-lookup"><span data-stu-id="c9ead-113">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="c9ead-114">Fare clic sui pulsanti **Raggruppa per** per visualizzare il livello di dettagli necessario per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="c9ead-114">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="c9ead-115">I pulsanti **Raggruppa per** selezionati sono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="c9ead-115">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="c9ead-116">Fare clic su un pulsante per attivarlo o disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="c9ead-116">Click on a button to activate or deactivate it.</span></span>

6. <span data-ttu-id="c9ead-117">Ricordarsi di fare clic sul pulsante **Aggiorna** per aggiornare il calcolo ogni volta che si apportano modifiche attivando o disattivando i pulsanti **Raggruppa per**, oppure eseguendo un calcolo per un nuovo periodo.</span><span class="sxs-lookup"><span data-stu-id="c9ead-117">Remember to click the **Update** button to update the calculation each time you make changes by activating or deactivating **Group by** buttons, or by making a calculation for a new period.</span></span>

7. <span data-ttu-id="c9ead-118">Fare clic su **Stato** se si desidera creare un nuovo calcolo dello stato della manutenzione.</span><span class="sxs-lookup"><span data-stu-id="c9ead-118">Click **Status** if you want to create a new maintenance status calculation.</span></span>

>[!NOTE]
><span data-ttu-id="c9ead-119">I risultati visualizzati in **Stato della manutenzione** includono solo le richieste di intervento di manutenzione e gli ordini di lavoro che hanno una data di inizio e di fine effettive.</span><span class="sxs-lookup"><span data-stu-id="c9ead-119">The results shown in **Maintenance status** only include maintenance requests and work orders that have an actual start date and time.</span></span> <span data-ttu-id="c9ead-120">La data e l'ora di fine possono essere vuote.</span><span class="sxs-lookup"><span data-stu-id="c9ead-120">End date and time may be blank.</span></span>

## <a name="example-1"></a><span data-ttu-id="c9ead-121">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="c9ead-121">Example 1</span></span>

<span data-ttu-id="c9ead-122">Nella schermata seguente, i pulsanti **Mese** e **Anno** sono stati attivati.</span><span class="sxs-lookup"><span data-stu-id="c9ead-122">In the screenshot below, the **Year** and **Month** buttons have been activated.</span></span> <span data-ttu-id="c9ead-123">Con le opzioni **Raggruppa per** selezionate, si ha una panoramica generale su base mensile del carico di lavoro e della produttività relativi alle richieste di intervento di manutenzione e agli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c9ead-123">With these **Group by** options selected, you get a general overview on a monthly basis of workload and throughput related to maintenance requests and work orders.</span></span> 

![Esempio del carico di lavoro mensile](media/13-controlling-and-reporting.png)

## <a name="example-2"></a><span data-ttu-id="c9ead-125">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="c9ead-125">Example 2</span></span>

<span data-ttu-id="c9ead-126">Nella schermata seguente, sono state aggiunte le informazioni sulle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="c9ead-126">In the screenshot below, information about functional locations has been added.</span></span> <span data-ttu-id="c9ead-127">A questo punto, è possibile confrontare il carico di lavoro e la produttività nelle unità funzionali, che possono rappresentare le ubicazioni geografiche, gli stabilimenti o le aree di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c9ead-127">Now it is possible to compare workload and throughput across functional locations, which may represent geographical locations, factories, or work areas.</span></span> 

![Esempio del carico di lavoro mensile con unità funzionali](media/14-controlling-and-reporting.png)

