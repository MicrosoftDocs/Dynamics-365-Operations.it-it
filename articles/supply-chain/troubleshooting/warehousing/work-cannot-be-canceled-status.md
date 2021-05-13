---
title: Il lavoro non può essere annullato a causa del suo stato
description: Il lavoro non può essere annullato a causa del suo stato
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 60b4da44ca5e6790302e0797640317cef8493db7
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924257"
---
# <a name="work-cant-be-canceled-because-of-its-status"></a><span data-ttu-id="15aa7-103">Il lavoro non può essere annullato a causa del suo stato</span><span class="sxs-lookup"><span data-stu-id="15aa7-103">Work can't be canceled because of its status</span></span>

<span data-ttu-id="15aa7-104">Codice errore: WAX2190</span><span class="sxs-lookup"><span data-stu-id="15aa7-104">Error code: WAX2190</span></span>

## <a name="symptoms"></a><span data-ttu-id="15aa7-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="15aa7-105">Symptoms</span></span>

<span data-ttu-id="15aa7-106">Il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="15aa7-106">The system shows the following error message:</span></span>

> <span data-ttu-id="15aa7-107">Impossibile annullare il lavoro %1 poiché ha uno stato %2.</span><span class="sxs-lookup"><span data-stu-id="15aa7-107">You cannot cancel work %1 because it has a status of %2.</span></span>

## <a name="cause"></a><span data-ttu-id="15aa7-108">Causa</span><span class="sxs-lookup"><span data-stu-id="15aa7-108">Cause</span></span>

<span data-ttu-id="15aa7-109">Il lavoro non può essere annullato nel suo stato attuale.</span><span class="sxs-lookup"><span data-stu-id="15aa7-109">The work can't be canceled in its current state.</span></span>

<span data-ttu-id="15aa7-110">L'intestazione del lavoro o le righe di lavoro non hanno il valore **Stato lavoro** previsto.</span><span class="sxs-lookup"><span data-stu-id="15aa7-110">The work header or work lines don't have the expected **Work status** value.</span></span> <span data-ttu-id="15aa7-111">Il campo **Stato lavoro** nell'intestazione del lavoro non è impostato su *Aperto* o *In corso*.</span><span class="sxs-lookup"><span data-stu-id="15aa7-111">The **Work status** field on the work header isn't set to *Open* or *In progress*.</span></span>

## <a name="resolution"></a><span data-ttu-id="15aa7-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="15aa7-112">Resolution</span></span>

<span data-ttu-id="15aa7-113">Per annullare il lavoro, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="15aa7-113">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="15aa7-114">Vai a **Gestione magazzino \> Attività periodiche \> Pulitura \> Annulla lavoro**.</span><span class="sxs-lookup"><span data-stu-id="15aa7-114">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="15aa7-115">Nel campo **ID lavoro** specificare l'ID del lavoro che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="15aa7-115">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="15aa7-116">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="15aa7-116">Select **OK**.</span></span>
1. <span data-ttu-id="15aa7-117">Selezionare **Sì** per confermare che si desidera annullare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="15aa7-117">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="15aa7-118">Per ulteriori informazioni, vedere [Annullare il lavoro di magazzino per la gestione delle eccezioni](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="15aa7-118">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
