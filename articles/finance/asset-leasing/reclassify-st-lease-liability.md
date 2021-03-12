---
title: Riclassificare la quota a breve termine di un'obbligazione sul leasing
description: Questo argomento spiega come creare una scrittura contabile mensile per riclassificare una parte dell'obbligazione sul leasing come a breve termine.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 08ca824bb4c4a02a80f2187fb5f8fe4e8b7327c9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992916"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a><span data-ttu-id="8786f-103">Riclassificare la quota a breve termine di obbligazione sul leasing</span><span class="sxs-lookup"><span data-stu-id="8786f-103">Reclassify the short-term portion of lease liability</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8786f-104">Questo argomento spiega come creare una scrittura contabile mensile per riclassificare una parte dell'obbligazione sul leasing come a breve termine.</span><span class="sxs-lookup"><span data-stu-id="8786f-104">This topic explains how to create a monthly journal entry to reclassify a portion of the lease liability as short-term.</span></span> <span data-ttu-id="8786f-105">Quando lo scadenziario selezionato nel processo batch è **Riclassificazione dell'obbligazione sul leasing a breve termine**, viene creata una scrittura contabile.</span><span class="sxs-lookup"><span data-stu-id="8786f-105">When the schedule that is selected in the batch process is **Short-term lease liability reclass**, a journal entry is created.</span></span> <span data-ttu-id="8786f-106">Questa voce viene utilizzata per registrare la parte corrente dell'obbligazione sul leasing l'ultimo giorno del mese.</span><span class="sxs-lookup"><span data-stu-id="8786f-106">This entry is used to post the current portion of the lease liability on the last day of the month.</span></span> <span data-ttu-id="8786f-107">Allo stesso tempo, viene registrato un movimento di storno a partire dal primo giorno del mese successivo.</span><span class="sxs-lookup"><span data-stu-id="8786f-107">At the same time, a reversal entry is posted as of the first day of the next month.</span></span>

<span data-ttu-id="8786f-108">La quota a breve termine dell'obbligazione sul leasing è indicata nel piano di ammortamento della passività.</span><span class="sxs-lookup"><span data-stu-id="8786f-108">The short-term portion of the lease liability is shown on the liability amortization schedule.</span></span> <span data-ttu-id="8786f-109">Quando la scrittura contabile viene registrata, la colonna **Giornale di riclassificazione passività creato** diventa disponibile e l'ID del giornale di registrazione viene inserito anche nello scadenziario.</span><span class="sxs-lookup"><span data-stu-id="8786f-109">When the journal entry is posted, the **Liability reclass journal created** column becomes available, and the journal ID is also filled in on the schedule.</span></span>

<span data-ttu-id="8786f-110">Per creare e registrare la scrittura contabile di riclassificazione dell'obbligazione a breve termine, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="8786f-110">To create and post the short-term liability reclassification journal entry, follow these steps.</span></span>

1. <span data-ttu-id="8786f-111">Vai a **Leasing cespite \> Periodico \> Creazione di un giornale in batch**.</span><span class="sxs-lookup"><span data-stu-id="8786f-111">Go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span>
2. <span data-ttu-id="8786f-112">Nella finestra di dialogo **Creazione di un giornale in batch**, nel campo **Seleziona scadenziario**, seleziona **Riclassificazione dell'obbligazione sul leasing a breve termine**.</span><span class="sxs-lookup"><span data-stu-id="8786f-112">In the **Batch journal creation** dialog box, in the **Select schedule** field, select **Short-term lease liability reclass**.</span></span>
3. <span data-ttu-id="8786f-113">Nel campo **Gruppo di leasing** selezionare un gruppo di leasing.</span><span class="sxs-lookup"><span data-stu-id="8786f-113">In the **Lease group** field, select a lease group.</span></span> <span data-ttu-id="8786f-114">In alternativa, nel campo **ID libro** seleziona l'ID libro.</span><span class="sxs-lookup"><span data-stu-id="8786f-114">Alternatively, in the **Book ID** field, select the book ID.</span></span>
4. <span data-ttu-id="8786f-115">Attiva il parametro **Registra**.</span><span class="sxs-lookup"><span data-stu-id="8786f-115">Turn on the **Post** parameter.</span></span> <span data-ttu-id="8786f-116">In alternativa, se la voce deve essere creata ma non pubblicata, lascia questo parametro disattivato.</span><span class="sxs-lookup"><span data-stu-id="8786f-116">Alternatively, if the entry should be created but not posted, leave this parameter turned off.</span></span>
5. <span data-ttu-id="8786f-117">Attiva il parametro **Visualizza anteprima prima della registrazione** per visualizzare la voce prima che venga registrata.</span><span class="sxs-lookup"><span data-stu-id="8786f-117">Turn on the **Preview before posting** parameter to view the entry before it's posted.</span></span>
6. <span data-ttu-id="8786f-118">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8786f-118">Select **OK**.</span></span>
