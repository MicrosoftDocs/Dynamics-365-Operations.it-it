---
title: Il lavoro resta bloccato
description: Il lavoro resta bloccato
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f85364d1ecfadc36b26c3395ab4402d3cb3b1603
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924132"
---
# <a name="work-remains-blocked"></a><span data-ttu-id="887de-103">Il lavoro resta bloccato</span><span class="sxs-lookup"><span data-stu-id="887de-103">Work remains blocked</span></span>

<span data-ttu-id="887de-104">Codice di errore: WHSWorkBlockingExecutingWaveReason_ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="887de-104">Error code: WHSWorkBlockingExecutingWaveReason_ErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="887de-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="887de-105">Symptoms</span></span>

<span data-ttu-id="887de-106">Il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="887de-106">The system shows the following error message:</span></span>

> <span data-ttu-id="887de-107">Il lavoro %1 rimane bloccato poiché lo stato dell'ondata correlata %2 è %3.</span><span class="sxs-lookup"><span data-stu-id="887de-107">Work %1 remains blocked because the related wave %2 has status %3.</span></span>

## <a name="cause"></a><span data-ttu-id="887de-108">Causa</span><span class="sxs-lookup"><span data-stu-id="887de-108">Cause</span></span>

<span data-ttu-id="887de-109">Il lavoro è attualmente in fase di elaborazione in un ciclo e non può essere sbloccato, come indicato da una delle seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="887de-109">The work is currently being processed on a wave and can't be unblocked, as indicated by one of the following conditions:</span></span>

- <span data-ttu-id="887de-110">Nella scheda **Motivi di blocco** il campo **Motivo blocco lavoro** per una o più righe è impostato su *Ciclo di elaborazione*.</span><span class="sxs-lookup"><span data-stu-id="887de-110">On the **Blocking reasons** tab, the **Work blocking reason** field for one or more lines is set to *Processing wave*.</span></span>
- <span data-ttu-id="887de-111">Quando si seleziona **Ciclo** nel gruppo **Informazioni correlate** della scheda **Informazioni correlate** del riquadro azioni, il campo **Stato ciclo** è impostato su *In elaborazione*.</span><span class="sxs-lookup"><span data-stu-id="887de-111">When you select **Wave** in the **Related information** group on the **Related information** tab of the Action Pane, the **Wave status** field is set to *Processing*.</span></span>

## <a name="resolution"></a><span data-ttu-id="887de-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="887de-112">Resolution</span></span>

<span data-ttu-id="887de-113">Nella scheda **Informazioni correlate** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Ciclo**.</span><span class="sxs-lookup"><span data-stu-id="887de-113">On the Action Pane, on the **Related information** tab, in the **Related information** group, select **Wave**.</span></span> <span data-ttu-id="887de-114">Quindi Nel riquadro azioni, nella pagina **Cicli**, nella scheda **Ciclo** e, nel gruppo **Ciclo**, seleziona **Pulizia dati ciclo**.</span><span class="sxs-lookup"><span data-stu-id="887de-114">Then, on the **Waves** page, on the Action Pane, on the **Wave** tab, in the **Wave** group, select **Cleanup wave data**.</span></span>

## <a name="workaround"></a><span data-ttu-id="887de-115">Soluzione alternativa</span><span class="sxs-lookup"><span data-stu-id="887de-115">Workaround</span></span>

<span data-ttu-id="887de-116">Se i passaggi precedenti non hanno risolto il problema, puoi annullare il lavoro seguendo questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="887de-116">If the previous steps didn't fix the issue, you can cancel the work by following these steps.</span></span>

1. <span data-ttu-id="887de-117">Vai a **Gestione magazzino \> Attività periodiche \> Pulitura \> Annulla lavoro**.</span><span class="sxs-lookup"><span data-stu-id="887de-117">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="887de-118">Nel campo **ID lavoro**, specifica l'ID del lavoro che desideri annullare e che attualmente ha valore **Stato lavoro** uguale a *Aperto*, *In corso*, *Annullato*, *Combinato* o *Chiuso*.</span><span class="sxs-lookup"><span data-stu-id="887de-118">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="887de-119">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="887de-119">Select **OK**.</span></span>
1. <span data-ttu-id="887de-120">Selezionare **Sì** per confermare che si desidera annullare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="887de-120">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="887de-121">Per ulteriori informazioni, vedere [Annullare il lavoro di magazzino per la gestione delle eccezioni](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="887de-121">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
