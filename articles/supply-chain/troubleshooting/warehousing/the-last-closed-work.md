---
title: L'ultima riga di lavoro chiusa deve essere un inserimento
description: L'ultima riga di lavoro chiusa deve essere un inserimento
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
ms.openlocfilehash: a5b78154b51252b3ac96ba28c254e823caf87019
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924377"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a><span data-ttu-id="0b1eb-103">L'ultima riga di lavoro chiusa deve essere un inserimento</span><span class="sxs-lookup"><span data-stu-id="0b1eb-103">The last closed work line must be a put</span></span>

<span data-ttu-id="0b1eb-104">Codice errore: WAX1285</span><span class="sxs-lookup"><span data-stu-id="0b1eb-104">Error code: WAX1285</span></span>

## <a name="symptoms"></a><span data-ttu-id="0b1eb-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="0b1eb-105">Symptoms</span></span>

<span data-ttu-id="0b1eb-106">Il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="0b1eb-106">The system shows the following error message:</span></span>

> <span data-ttu-id="0b1eb-107">L'ultima riga di lavoro chiusa deve essere un inserimento.</span><span class="sxs-lookup"><span data-stu-id="0b1eb-107">The last closed work line must be a put.</span></span>

## <a name="cause"></a><span data-ttu-id="0b1eb-108">Causa</span><span class="sxs-lookup"><span data-stu-id="0b1eb-108">Cause</span></span>

<span data-ttu-id="0b1eb-109">Il lavoro non può essere annullato nel suo stato attuale.</span><span class="sxs-lookup"><span data-stu-id="0b1eb-109">The work can't be canceled in its current state.</span></span>

<span data-ttu-id="0b1eb-110">Nell'ultima riga di lavoro, il campo **Stato lavoro** è impostato su *Chiuso*, ma **Tipo di lavoro** non è impostato su *Inserisci*.</span><span class="sxs-lookup"><span data-stu-id="0b1eb-110">On the last work line, the **Work status** field is set to *Closed*, but the **Work type** field isn't set to *Put*.</span></span>

## <a name="resolution"></a><span data-ttu-id="0b1eb-111">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="0b1eb-111">Resolution</span></span>

<span data-ttu-id="0b1eb-112">Per annullare il lavoro, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="0b1eb-112">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="0b1eb-113">Vai a **Gestione magazzino \> Attività periodiche \> Pulitura \> Annulla lavoro**.</span><span class="sxs-lookup"><span data-stu-id="0b1eb-113">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="0b1eb-114">Nel campo **ID lavoro** specificare l'ID del lavoro che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="0b1eb-114">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="0b1eb-115">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b1eb-115">Select **OK**.</span></span>
1. <span data-ttu-id="0b1eb-116">Selezionare **Sì** per confermare che si desidera annullare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="0b1eb-116">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="0b1eb-117">Per ulteriori informazioni, vedere [Annullare il lavoro di magazzino per la gestione delle eccezioni](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="0b1eb-117">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
