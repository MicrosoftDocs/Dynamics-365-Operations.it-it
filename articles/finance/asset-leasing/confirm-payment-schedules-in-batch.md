---
title: Confermare gli scadenzari pagamenti di Leasing cespite in un batch
description: Questo argomento spiega come confermare più scadenziari pagamenti in un batch.
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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b5a90b96ac598d145e2b0697627de04731b55f59
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444986"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a><span data-ttu-id="ca387-103">Confermare gli scadenzari pagamenti di Leasing cespite in un batch</span><span class="sxs-lookup"><span data-stu-id="ca387-103">Confirm Asset leasing payment schedules in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ca387-104">Questo argomento spiega come confermare più scadenziari pagamenti in un batch.</span><span class="sxs-lookup"><span data-stu-id="ca387-104">This topic explains how to confirm multiple payment schedules in a batch.</span></span> <span data-ttu-id="ca387-105">Gli scadenziari di pagamento vengono confermati in base al leasing o tramite il processo batch di conferma.</span><span class="sxs-lookup"><span data-stu-id="ca387-105">Payment schedules are confirmed either on a lease-to-lease basis or through the confirmation batch process.</span></span> <span data-ttu-id="ca387-106">Una scrittura contabile può essere registrata solo a fronte di un leasing con uno scadenzario pagamenti confermato.</span><span class="sxs-lookup"><span data-stu-id="ca387-106">A journal entry can be posted only against a lease that has a confirmed payment schedule.</span></span> <span data-ttu-id="ca387-107">La conferma dello scadenziario di pagamento serve come approvazione finale delle informazioni finanziarie per il leasing.</span><span class="sxs-lookup"><span data-stu-id="ca387-107">Confirmation of the payment schedule serves as a final approval of the financial information for the lease.</span></span> <span data-ttu-id="ca387-108">Tutte le modifiche future alle informazioni finanziarie per il leasing, come i pagamenti e il termine del leasing, costituiscono una rettifica del leasing e dovrebbero essere elaborate in questo modo.</span><span class="sxs-lookup"><span data-stu-id="ca387-108">All future changes to the financial information for the lease, such as payments and the lease term, constitute a lease adjustment and should be processed in that way.</span></span>

<span data-ttu-id="ca387-109">Per confermare più scadenziari di pagamento, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="ca387-109">To confirm multiple payment schedules, follow these steps.</span></span>

1. <span data-ttu-id="ca387-110">Vai a **Leasing cespite \> Periodico \> Batch di conferma**.</span><span class="sxs-lookup"><span data-stu-id="ca387-110">Go to **Asset leasing \> Periodic \> Confirmation batch**.</span></span>
2. <span data-ttu-id="ca387-111">Nella pagina **Batch di conferma**, seleziona **Batch di conferma**.</span><span class="sxs-lookup"><span data-stu-id="ca387-111">On the **Confirmation batch** page, select **Confirmation batch**.</span></span>
3. <span data-ttu-id="ca387-112">Nella finestra di dialogo che appare, filtra i libri che desideri confermare.</span><span class="sxs-lookup"><span data-stu-id="ca387-112">In the dialog box that appears, filter for the books that you want to confirm.</span></span>

    - <span data-ttu-id="ca387-113">Per confermare tutti i libri in uno specifico gruppo di leasing, seleziona il gruppo nel campo **Gruppo leasing**.</span><span class="sxs-lookup"><span data-stu-id="ca387-113">To confirm all the books in a specific lease group, select the group in the **Lease group** field.</span></span>
    - <span data-ttu-id="ca387-114">Per confermare libri specifici, seleziona i libri nel campo **ID libro**.</span><span class="sxs-lookup"><span data-stu-id="ca387-114">To confirm specific books, select the books in the **Book ID** field.</span></span>
    - <span data-ttu-id="ca387-115">Per confermare tutti i libri, attiva il parametro **Per tutti i libri**.</span><span class="sxs-lookup"><span data-stu-id="ca387-115">To confirm all books, turn on the **For all books** parameter.</span></span>

<span data-ttu-id="ca387-116">Le informazioni per i libri appena confermati sono mostrate nella pagina **Libri confermati**.</span><span class="sxs-lookup"><span data-stu-id="ca387-116">Information for the newly confirmed books is shown on the **Confirmed books** page.</span></span> <span data-ttu-id="ca387-117">Dopo la conferma degli scadenziari di pagamento, le scritture contabili di riconoscimento iniziale possono essere registrate a fronte dei leasing.</span><span class="sxs-lookup"><span data-stu-id="ca387-117">After the payment schedules are confirmed, the initial recognition journal entries can be posted against the leases.</span></span>
