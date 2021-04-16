---
title: Costo del programma di manutenzione
description: In questo argomento viene descritto il costo del programma di manutenzione in Gestione cespiti.
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 405fd7fbbbb8862446d09b9ea33ef14348e691f9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813775"
---
# <a name="maintenance-schedule-cost"></a><span data-ttu-id="ac971-103">Costo del programma di manutenzione</span><span class="sxs-lookup"><span data-stu-id="ac971-103">Maintenance schedule cost</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="ac971-104">In Gestione cespiti, è possibile calcolare i costi in budget nelle righe di programma di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="ac971-104">In Asset Management, you can calculate budget costs on maintenance schedule lines.</span></span> <span data-ttu-id="ac971-105">Questa funzionalità è utile se si desidera ottenere una panoramica dei costi previsti, ad esempio, i costi relativi ai processi di manutenzione preventiva pianificati per l'anno successivo.</span><span class="sxs-lookup"><span data-stu-id="ac971-105">This is useful if you want to get an overview of expected costs, for example, costs relating to planned preventive maintenance jobs for the next year.</span></span> <span data-ttu-id="ac971-106">I calcoli si basano sulle righe di programma di manutenzione esistenti di tipo "Piani di manutenzione ", "Cicli di manutenzione" e "Richiesta di intervento di manutenzione".</span><span class="sxs-lookup"><span data-stu-id="ac971-106">The calculations are based on existing maintenance schedule lines of type "Maintenance plans" and "Maintenance rounds" and "Maintenance requests".</span></span>

1. <span data-ttu-id="ac971-107">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **Costo del programma di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="ac971-107">Click **Asset management** > **Inquiries** > **Assets** > **Maintenance schedule cost**.</span></span>

2. <span data-ttu-id="ac971-108">Nella finestra di dialogo **Costo del programma di manutenzione**, è possibile selezionare **Set di dimensioni finanziarie** se si desidera visualizzare i costi raggruppati in dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="ac971-108">In the **Maintenance schedule cost** dialog, you can select a **Financial dimension set** if you want to see costs grouped in financial dimensions.</span></span>

>[!NOTE]
><span data-ttu-id="ac971-109">I set di dimensioni finanziarie sono impostati in **Contabilità generale** > **Piano dei conti** > **Dimensioni** > **Set di dimensioni finanziarie**.</span><span class="sxs-lookup"><span data-stu-id="ac971-109">Financial dimension sets are set up in **General ledger** > **Chart of accounts** > **Dimensions** > **Financial dimension sets**.</span></span>

3. <span data-ttu-id="ac971-110">È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe di programma di manutenzione in relazione alle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="ac971-110">You can use the **Level** field to indicate how detailed you want the maintenance schedule lines to be regarding functional locations.</span></span> <span data-ttu-id="ac971-111">Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe di programma di manutenzione per un'unità funzionale verranno visualizzate nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali situate a un livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="ac971-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="ac971-112">Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe di programma di manutenzione in tutti i livelli di unità funzionali a cui sono correlate.</span><span class="sxs-lookup"><span data-stu-id="ac971-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="ac971-113">Se si desidera eseguire un calcolo per specifici cespiti, fare clic su **Filtro** nella Scheda dettaglio **Record da includere** e selezionare i cespiti pertinenti.</span><span class="sxs-lookup"><span data-stu-id="ac971-113">If you want to make a calculation for specific assets, click **Filter** on the **Records to include** FastTab, and select the relevant assets.</span></span> <span data-ttu-id="ac971-114">Se necessario, è anche possibile specificare uno **Stato** diverso o una **Data di inizio prevista** per il calcolo dei costi.</span><span class="sxs-lookup"><span data-stu-id="ac971-114">If required, you can also specify an **Expected start** date for the cost calculation or select a different **Status** for the cost calculation</span></span>

5. <span data-ttu-id="ac971-115">Scegliere **OK** per avviare il ricalcolo del costi.</span><span class="sxs-lookup"><span data-stu-id="ac971-115">Click **OK** to start the cost calculation.</span></span>

6. <span data-ttu-id="ac971-116">Nella scheda **Costo del programma di manutenzione** > nei gruppi di riquadri azioni **Raggruppa per**, fai clic sui pulsanti appropriati per visualizzare il livello di dettagli necessario per il calcolo dei costi.</span><span class="sxs-lookup"><span data-stu-id="ac971-116">On the **Maintenance schedule cost** tab > in the **Group by...** Action Pane groups, click the relevant buttons to show the required detail level of the cost calculation.</span></span> <span data-ttu-id="ac971-117">I pulsanti del gruppo di riquadri azioni selezionati sono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="ac971-117">The selected Action Pane group buttons are highlighted.</span></span> <span data-ttu-id="ac971-118">Fare clic su un pulsante per attivarlo o disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="ac971-118">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="ac971-119">Fare clic sul pulsante **Calcola costo** se si desidera eseguire un nuovo calcolo dei costi.</span><span class="sxs-lookup"><span data-stu-id="ac971-119">Click the **Calculate cost** button if you want to make a new cost calculation.</span></span>

<span data-ttu-id="ac971-120">Nella figura seguente vengono illustrati i risultati di un calcolo del costo del programma di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="ac971-120">The illustration below shows the results of a maintenance schedule cost calculation.</span></span>

![Figura 1](media/17-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]