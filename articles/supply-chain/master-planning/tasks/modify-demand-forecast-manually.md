---
title: 'Guida: modificare una previsione della domanda manualmente'
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
ms.openlocfilehash: 1e12ccf90b9971379e8931bd48d6243a855bb795
ms.sourcegitcommit: 15aacd0e109b05c7281407b5bba4e6cd99116c28
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "6224012"
---
# <a name="guide-modify-a-demand-forecast-manually"></a><span data-ttu-id="c7bd1-103">Guida: modificare una previsione della domanda manualmente</span><span class="sxs-lookup"><span data-stu-id="c7bd1-103">Guide: Modify a demand forecast manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c7bd1-104">Questa procedura illustra come modificare la previsione per un articolo.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="c7bd1-105">Questa procedura è destinata al responsabile pianificazione produzione.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-105">This procedure is intended for the production planner.</span></span>

## <a name="modify-the-forecast-for-a-selected-item"></a><span data-ttu-id="c7bd1-106">Modificare la previsione per un articolo selezionato</span><span class="sxs-lookup"><span data-stu-id="c7bd1-106">Modify the forecast for a selected item</span></span>

<span data-ttu-id="c7bd1-107">Per modificare la previsione per un articolo selezionato:</span><span class="sxs-lookup"><span data-stu-id="c7bd1-107">To modify the forecast for a selected item:</span></span>

1. <span data-ttu-id="c7bd1-108">Selezionare **Moduli \> Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-108">Go to **Modules \> Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="c7bd1-109">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-109">In the list, find and select the desired record.</span></span> <span data-ttu-id="c7bd1-110">Selezionare l'articolo per cui si desidera modificare la previsione.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-110">Select the item for which you want to modify the forecast.</span></span>
1. <span data-ttu-id="c7bd1-111">Nel riquadro azioni aprire la scheda **Piano** e selezionare **Previsione della domanda**.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-111">On the Action Pane, open the **Plan** tab and select **Demand forecast**.</span></span>
1. <span data-ttu-id="c7bd1-112">Nell'elenco selezionare una riga.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-112">In the list, select a row.</span></span> <span data-ttu-id="c7bd1-113">Se non sono presenti righe di previsione, creare una nuova riga selezionando **Nuova** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-113">If there are no forecast lines, create a new line by selecting **New** on the Action Pane.</span></span>  
1. <span data-ttu-id="c7bd1-114">Nel campo **Quantità di vendita** immettere un numero positivo.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-114">In the **Sales quantity** field, enter a positive number.</span></span> <span data-ttu-id="c7bd1-115">Questo numero rappresenta la quantità prevista per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-115">This number represents the forecasted quantity for the item.</span></span> <span data-ttu-id="c7bd1-116">Se si inserisce un numero negativo, verrà visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-116">An error will be shown if you enter a negative number.</span></span>
1. <span data-ttu-id="c7bd1-117">Compilare gli altri campi come necessario.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-117">Fill out the other fields as needed.</span></span>
1. <span data-ttu-id="c7bd1-118">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-118">Select **Save** on the Action Pane.</span></span>

## <a name="modify-the-forecast-for-one-or-more-items-with-microsoft-excel"></a><span data-ttu-id="c7bd1-119">Modificare la previsione per uno o più elementi con Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="c7bd1-119">Modify the forecast for one or more items with Microsoft Excel</span></span>

<span data-ttu-id="c7bd1-120">Per modificare la previsione per uno o più elementi con Microsoft Excel:</span><span class="sxs-lookup"><span data-stu-id="c7bd1-120">To modify the forecast for one or more items with Microsoft Excel:</span></span>

1. <span data-ttu-id="c7bd1-121">Effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="c7bd1-121">Do one of the following:</span></span>
    - <span data-ttu-id="c7bd1-122">Aprire la pagina **Previsione della domanda** per qualsiasi articolo (non importa quale) come descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-122">Open the **Demand forecast** page for any item (it doesn't matter which one) as described in the previous section.</span></span>
    - <span data-ttu-id="c7bd1-123">Selezionare **Pianificazione generale \> Previsioni \> Voce di previsione \> Righe di previsione della domanda**.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-123">Go to **Master planning \> Forecasting \> Manual forecast entry \> Demand forecast lines**.</span></span>
1. <span data-ttu-id="c7bd1-124">Nel riquadro azioni selezionare **Apri in Microsoft Office \> Voci di previsione della domanda**.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-124">On the Action Pane, select **Open in Microsoft Office \> Demand forecast entries**.</span></span>
1. <span data-ttu-id="c7bd1-125">Selezionare un percorso di download, salvare e quindi aprire il file scaricato in Excel.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-125">Select a download location, save, and then open the downloaded file in Excel.</span></span>
1. <span data-ttu-id="c7bd1-126">Se viene visualizzato un avviso, scegliere **Abilita modifica**.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-126">If you see a warning, choose to **Enable editing**.</span></span>
1. <span data-ttu-id="c7bd1-127">In Excel, accedere a Supply Chain Management utilizzando il riquadro attività Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-127">In Excel, sign in to Supply Chain Management using the Microsoft Dynamics task pane.</span></span> <span data-ttu-id="c7bd1-128">È necessario accedere con l'opzione **Mantieni connesso** abilitata e considerare attendibile l'app per la connessione dati.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-128">You must sign in with the **Keep me signed in** option enabled and you must trust the data connection app.</span></span>
1. <span data-ttu-id="c7bd1-129">Il foglio di calcolo Excel ora mostra tutte le righe di previsione della domanda corrente per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-129">The Excel spreadsheet now shows all the current demand forecast lines for your company.</span></span>  <span data-ttu-id="c7bd1-130">Aggiungere, eliminare e modificare le righe di previsione della domanda come necessario.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-130">Add, delete, and edit demand forecast lines as needed.</span></span>
1. <span data-ttu-id="c7bd1-131">Selezionare **Pubblica** nel riquadro delle attività di Microsoft Dynamics per caricare nuovamente le modifiche in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c7bd1-131">Select **Publish** on the Microsoft Dynamics task pane to upload your changes back to Supply Chain Management.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
