---
title: Modificare una previsione della domanda manualmente
description: Questo argomento descrive come modificare la previsione per un articolo
author: ChristianRytt
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5da1d5b1fbd91964e695a704681b1c9ee513a2f1
ms.sourcegitcommit: 4016c223a985c46e33f9941bf91ba5e1583e1cfd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889026"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="57414-103">Modificare una previsione della domanda manualmente</span><span class="sxs-lookup"><span data-stu-id="57414-103">Modify a demand forecast manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="57414-104">Questa procedura illustra come modificare la previsione per un articolo.</span><span class="sxs-lookup"><span data-stu-id="57414-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="57414-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="57414-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="57414-106">Questa procedura è destinata al responsabile pianificazione produzione.</span><span class="sxs-lookup"><span data-stu-id="57414-106">This procedure is intended for the production planner.</span></span>

## <a name="modify-the-forecast-for-a-selected-item"></a><span data-ttu-id="57414-107">Modificare la previsione per un articolo selezionato</span><span class="sxs-lookup"><span data-stu-id="57414-107">Modify the forecast for a selected item</span></span>

<span data-ttu-id="57414-108">Per modificare la previsione per un articolo selezionato:</span><span class="sxs-lookup"><span data-stu-id="57414-108">To modify the forecast for a selected item:</span></span>

1. <span data-ttu-id="57414-109">Selezionare **Moduli \> Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="57414-109">Go to **Modules \> Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="57414-110">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="57414-110">In the list, find and select the desired record.</span></span> <span data-ttu-id="57414-111">Selezionare l'articolo per cui si desidera modificare la previsione.</span><span class="sxs-lookup"><span data-stu-id="57414-111">Select the item for which you want to modify the forecast.</span></span>
1. <span data-ttu-id="57414-112">Nel riquadro azioni aprire la scheda **Piano** e selezionare **Previsione della domanda**.</span><span class="sxs-lookup"><span data-stu-id="57414-112">On the Action Pane, open the **Plan** tab and select **Demand forecast**.</span></span>
1. <span data-ttu-id="57414-113">Nell'elenco selezionare una riga.</span><span class="sxs-lookup"><span data-stu-id="57414-113">In the list, select a row.</span></span> <span data-ttu-id="57414-114">Se non sono presenti righe di previsione, creare una nuova riga selezionando **Nuova** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="57414-114">If there are no forecast lines, create a new line by selecting **New** on the Action Pane.</span></span>  
1. <span data-ttu-id="57414-115">Nel campo **Quantità di vendita** immettere un numero positivo.</span><span class="sxs-lookup"><span data-stu-id="57414-115">In the **Sales quantity** field, enter a positive number.</span></span> <span data-ttu-id="57414-116">Questo numero rappresenta la quantità prevista per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="57414-116">This number represents the forecasted quantity for the item.</span></span> <span data-ttu-id="57414-117">Se si inserisce un numero negativo, verrà visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="57414-117">An error will be shown if you enter a negative number.</span></span>
1. <span data-ttu-id="57414-118">Compilare gli altri campi come necessario.</span><span class="sxs-lookup"><span data-stu-id="57414-118">Fill out the other fields as needed.</span></span>
1. <span data-ttu-id="57414-119">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="57414-119">Select **Save** on the Action Pane.</span></span>

## <a name="modify-the-forecast-for-one-or-more-items-microsoft-excel"></a><span data-ttu-id="57414-120">Modificare la previsione per uno o più elementi Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="57414-120">Modify the forecast for one or more items Microsoft Excel</span></span>

<span data-ttu-id="57414-121">Per modificare la previsione per uno o più elementi Microsoft Excel:</span><span class="sxs-lookup"><span data-stu-id="57414-121">To modify the forecast for one or more items Microsoft Excel:</span></span>

1. <span data-ttu-id="57414-122">Effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="57414-122">Do one of the following:</span></span>
    - <span data-ttu-id="57414-123">Aprire la pagina **Previsione della domanda** per qualsiasi articolo (non importa quale) come descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="57414-123">Open the **Demand forecast** page for any item (it doesn't matter which one) as described in the previous section.</span></span>
    - <span data-ttu-id="57414-124">Selezionare **Pianificazione generale \> Previsioni \> Voce di previsione \> Righe di previsione della domanda**.</span><span class="sxs-lookup"><span data-stu-id="57414-124">Go to **Master planning \> Forecasting \> Manual forecast entry \> Demand forecast lines**.</span></span>
1. <span data-ttu-id="57414-125">Nel riquadro azioni selezionare **Apri in Microsoft Office \> Voci di previsione della domanda**.</span><span class="sxs-lookup"><span data-stu-id="57414-125">On the Action Pane, select **Open in Microsoft Office \> Demand forecast entries**.</span></span>
1. <span data-ttu-id="57414-126">Selezionare un percorso di download, salvare e quindi aprire il file scaricato in Excel.</span><span class="sxs-lookup"><span data-stu-id="57414-126">Select a download location, save, and then open the downloaded file in Excel.</span></span>
1. <span data-ttu-id="57414-127">Se viene visualizzato un avviso, scegliere **Abilita modifica**.</span><span class="sxs-lookup"><span data-stu-id="57414-127">If you see a warning, choose to **Enable editing**.</span></span>
1. <span data-ttu-id="57414-128">In Excel, accedere a Supply Chain Management utilizzando il riquadro attività Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="57414-128">In Excel, sign in to Supply Chain Management using the Microsoft Dynamics task pane.</span></span> <span data-ttu-id="57414-129">È necessario accedere con l'opzione **Mantieni connesso** abilitata e considerare attendibile l'app per la connessione dati.</span><span class="sxs-lookup"><span data-stu-id="57414-129">You must sign in with the **Keep me signed in** option enabled and you must trust the data connection app.</span></span>
1. <span data-ttu-id="57414-130">Il foglio di calcolo Excel ora mostra tutte le righe di previsione della domanda corrente per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="57414-130">The Excel spreadsheet now shows all the current demand forecast lines for your company.</span></span>  <span data-ttu-id="57414-131">Aggiungere, eliminare e modificare le righe di previsione della domanda come necessario.</span><span class="sxs-lookup"><span data-stu-id="57414-131">Add, delete, and edit demand forecast lines as needed.</span></span>
1. <span data-ttu-id="57414-132">Selezionare **Pubblica** nel riquadro delle attività di Microsoft Dynamics per caricare nuovamente le modifiche in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="57414-132">Select **Publish** on the Microsoft Dynamics task pane to upload your changes back to Supply Chain Management.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
