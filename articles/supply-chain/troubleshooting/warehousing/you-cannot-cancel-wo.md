---
title: Non puoi annullare il lavoro di un utente
description: Non puoi annullare il lavoro di un utente
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
ms.openlocfilehash: e5f6912cfb1d5be8e46b7989856af99f8a611c11
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924403"
---
# <a name="you-cant-cancel-work-that-is-on-a-user"></a><span data-ttu-id="be6ad-103">Non puoi annullare il lavoro di un utente</span><span class="sxs-lookup"><span data-stu-id="be6ad-103">You can't cancel work that is on a user</span></span>

<span data-ttu-id="be6ad-104">Codice errore: WAX708</span><span class="sxs-lookup"><span data-stu-id="be6ad-104">Error code: WAX708</span></span>

## <a name="symptoms"></a><span data-ttu-id="be6ad-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="be6ad-105">Symptoms</span></span>

<span data-ttu-id="be6ad-106">Il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="be6ad-106">The system shows the following error message:</span></span>

> <span data-ttu-id="be6ad-107">Impossibile annullare il lavoro di un utente.</span><span class="sxs-lookup"><span data-stu-id="be6ad-107">You cannot cancel work that is on a user.</span></span>

## <a name="cause"></a><span data-ttu-id="be6ad-108">Causa</span><span class="sxs-lookup"><span data-stu-id="be6ad-108">Cause</span></span>

<span data-ttu-id="be6ad-109">Il lavoro è bloccato da un utente e non può essere annullato.</span><span class="sxs-lookup"><span data-stu-id="be6ad-109">The work is locked by a user and can't be canceled.</span></span> <span data-ttu-id="be6ad-110">Per verificare ciò, apri l'ID lavoro e quindi apri la scheda **Generale**. Se il lavoro è bloccato, il campo **Stato del lavoro** sarà impostato su *In corso*, e il campo **Bloccato da** è impostato su un ID utente.</span><span class="sxs-lookup"><span data-stu-id="be6ad-110">To confirm this, open the work ID and then open the **General** tab. If the work is locked, the **Work status** field will be set to *In progress*, and the **Locked by** field will be set to a user ID.</span></span>

## <a name="resolution"></a><span data-ttu-id="be6ad-111">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="be6ad-111">Resolution</span></span>

<span data-ttu-id="be6ad-112">Per annullare il lavoro, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="be6ad-112">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="be6ad-113">Vai a **Gestione magazzino \> Attività periodiche \> Pulitura \> Annulla lavoro**.</span><span class="sxs-lookup"><span data-stu-id="be6ad-113">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="be6ad-114">Nel campo **ID lavoro** specificare l'ID del lavoro che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="be6ad-114">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="be6ad-115">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="be6ad-115">Select **OK**.</span></span>
1. <span data-ttu-id="be6ad-116">Selezionare **Sì** per confermare che si desidera annullare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="be6ad-116">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="be6ad-117">Per ulteriori informazioni, vedere [Annullare il lavoro di magazzino per la gestione delle eccezioni](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="be6ad-117">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
