---
title: Il lavoro non può essere annullato perché è bloccato
description: Il lavoro non può essere annullato perché è bloccato
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a7ab4c7263947767164702fb7dd6da7573175253
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924281"
---
# <a name="work-cant-be-canceled-because-its-blocked"></a><span data-ttu-id="79099-103">Il lavoro non può essere annullato perché è bloccato</span><span class="sxs-lookup"><span data-stu-id="79099-103">Work can't be canceled because it's blocked</span></span>

<span data-ttu-id="79099-104">Codice di errore: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="79099-104">Error code: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="79099-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="79099-105">Symptoms</span></span>

<span data-ttu-id="79099-106">Il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="79099-106">The system shows the following error message:</span></span>

> <span data-ttu-id="79099-107">Il lavoro %1 non può essere annullato perché bloccato dal tipo di motivo %2.</span><span class="sxs-lookup"><span data-stu-id="79099-107">Work %1 cannot be cancelled because it is blocked by reason type %2.</span></span> <span data-ttu-id="79099-108">Il lavoro deve essere sbloccato per poterlo annullare.</span><span class="sxs-lookup"><span data-stu-id="79099-108">The work must be unblocked before it can be cancelled.</span></span>

## <a name="cause"></a><span data-ttu-id="79099-109">Causa</span><span class="sxs-lookup"><span data-stu-id="79099-109">Cause</span></span>

<span data-ttu-id="79099-110">Il lavoro è bloccato e non può essere annullato.</span><span class="sxs-lookup"><span data-stu-id="79099-110">The work is blocked and can't be canceled.</span></span>

<span data-ttu-id="79099-111">Nella pagina **Lavoro**, nella scheda **Generale**, l'opzione **Bloccato** è impostata su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="79099-111">On the **Work** page, on the **General** tab, the **Blocked** option is set to *Yes*.</span></span> <span data-ttu-id="79099-112">Questa impostazione indica che il lavoro è bloccato.</span><span class="sxs-lookup"><span data-stu-id="79099-112">This setting indicates that the work is blocked.</span></span> <span data-ttu-id="79099-113">La scheda **Motivi di blocco** mostra il motivo per cui il lavoro è stato bloccato.</span><span class="sxs-lookup"><span data-stu-id="79099-113">The **Blocking reasons** tab shows why the work was blocked.</span></span>

## <a name="resolution"></a><span data-ttu-id="79099-114">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="79099-114">Resolution</span></span>

<span data-ttu-id="79099-115">Per sbloccare il lavoro, seleziona la scheda **Motivi di blocco**, quindi segui uno di questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="79099-115">To unblock the work, select the **Blocking reasons** tab, and then follow one of these steps:</span></span>

- <span data-ttu-id="79099-116">Se il campo **Motivo blocco lavoro** è impostato su *Motivo indefinito*: Nel riquadro azioni, nella scheda **Lavoro**, gruppo **Lavoro** gruppo, selezionare **Sblocca lavoro**.</span><span class="sxs-lookup"><span data-stu-id="79099-116">If the **Work blocking reason** field is set to *Undefined reason*: On the Action Pane, on the **Work** tab, in the **Work** group, select **Unblock work**.</span></span>
- <span data-ttu-id="79099-117">Se il campo **Motivo blocco lavoro** campo è impostato su *Ciclo di elaborazione*: Nel riquadro azioni, scheda **Informazioni correlate**, nel gruppo **Informazioni correlate** selezionare **Ciclo**.</span><span class="sxs-lookup"><span data-stu-id="79099-117">If the **Work blocking reason** field is set to *Processing wave*: On the Action Pane, on the **Related information** tab, in the **Related information** group, select **Wave**.</span></span> <span data-ttu-id="79099-118">Quindi Nel riquadro azioni, nella pagina **Cicli**, nella scheda **Ciclo** e, nel gruppo **Ciclo**, seleziona **Pulizia dati ciclo**.</span><span class="sxs-lookup"><span data-stu-id="79099-118">Then, on the **Waves** page, on the Action Pane, on the **Wave** tab, in the **Wave** group, select **Cleanup wave data**.</span></span>

## <a name="workaround"></a><span data-ttu-id="79099-119">Soluzione alternativa</span><span class="sxs-lookup"><span data-stu-id="79099-119">Workaround</span></span>

<span data-ttu-id="79099-120">Se i passaggi precedenti non hanno risolto il problema, puoi annullare il lavoro seguendo questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="79099-120">If the previous steps didn't fix the issue, you can cancel the work by following these steps.</span></span>

1. <span data-ttu-id="79099-121">Vai a **Gestione magazzino \> Attività periodiche \> Pulitura \> Annulla lavoro**.</span><span class="sxs-lookup"><span data-stu-id="79099-121">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="79099-122">Nel campo **ID lavoro**, specifica l'ID del lavoro che desideri annullare e che attualmente ha valore **Stato lavoro** uguale a *Aperto*, *In corso*, *Annullato*, *Combinato* o *Chiuso*.</span><span class="sxs-lookup"><span data-stu-id="79099-122">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="79099-123">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="79099-123">Select **OK**.</span></span>
1. <span data-ttu-id="79099-124">Selezionare **Sì** per confermare che si desidera annullare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="79099-124">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="79099-125">Per ulteriori informazioni, vedere [Annullare il lavoro di magazzino per la gestione delle eccezioni](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="79099-125">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
