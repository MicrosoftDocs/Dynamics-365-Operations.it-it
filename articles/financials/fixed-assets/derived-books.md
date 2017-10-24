---
title: Libri derivati
description: "Questo articolo fornisce una panoramica delle funzionalità dei libri derivati."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5afdabf93128bc52cb223d0c35c6bcdae5f5ca2a
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="derived-books"></a><span data-ttu-id="348c4-103">Libri derivati</span><span class="sxs-lookup"><span data-stu-id="348c4-103">Derived books</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="348c4-104">Questo articolo fornisce una panoramica delle funzionalità dei libri derivati.</span><span class="sxs-lookup"><span data-stu-id="348c4-104">This article provides an overview of derived book functionality.</span></span>

<span data-ttu-id="348c4-105">Lo scopo dei libri derivati è semplificare la registrazione delle transazioni relative ai libri di cespiti pianificate a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="348c4-105">The purpose of derived books is to simplify the posting of fixed asset book transactions that are planned for regular intervals.</span></span>  <span data-ttu-id="348c4-106">È possibile selezionare un libro come primario.</span><span class="sxs-lookup"><span data-stu-id="348c4-106">You choose one book as the primary book.</span></span> <span data-ttu-id="348c4-107">Di solito si tratta del libro utilizzato per l'ammortamento contabile.</span><span class="sxs-lookup"><span data-stu-id="348c4-107">This usually is the book that is used for accounting depreciation.</span></span> <span data-ttu-id="348c4-108">Quindi lo si collega ad altri libri impostati per la registrazione di transazioni negli stessi intervalli del libro principale.</span><span class="sxs-lookup"><span data-stu-id="348c4-108">You then attach to it other books that are set up to post transactions in the same intervals as the primary book.</span></span> <span data-ttu-id="348c4-109">I libri di ammortamento fiscale sono spesso impostati come libri derivati.</span><span class="sxs-lookup"><span data-stu-id="348c4-109">Tax depreciation books are often set up as derived books.</span></span> 

<span data-ttu-id="348c4-110">Le transazioni più comuni da impostare per la registrazione in libri derivati sono le acquisizioni, le rettifiche di acquisizioni e le dismissioni.</span><span class="sxs-lookup"><span data-stu-id="348c4-110">The most common transactions to set up to post to derived books are acquisitions, acquisition adjustments, and disposals.</span></span> 

## <a name="example"></a><span data-ttu-id="348c4-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="348c4-111">Example</span></span>

<span data-ttu-id="348c4-112">Il libro B e il libro C vengono impostati come libri derivati per il libro A per il tipo di transazione di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="348c4-112">Book B and book C are set up as derived books for book A for the Acquisition transaction type.</span></span> <span data-ttu-id="348c4-113">Nel libro A immettere una transazione di acquisizione per il cespite 123 di 1.500,00.</span><span class="sxs-lookup"><span data-stu-id="348c4-113">In book A, you enter an acquisition transaction for asset 123 for 1,500.00.</span></span> 

<span data-ttu-id="348c4-114">Quando la transazione viene registrata, una transazione di acquisizione viene generata e registrata nel cespite 123 per il libro B e nel cespite 123 per il libro C per 1.500,00.</span><span class="sxs-lookup"><span data-stu-id="348c4-114">When the transaction is posted, an acquisition transaction is generated and posted in asset 123 for book B and in asset 123 for book C for 1,500.00.</span></span> <span data-ttu-id="348c4-115">Quando si preparano le transazioni del libro principale per la registrazione nel giornale di registrazione cespiti, è possibile visualizzare e modificare anche le transazioni dei libri derivati.</span><span class="sxs-lookup"><span data-stu-id="348c4-115">When you prepare the transactions of the primary book for posting in the fixed asset journal, you can also view and modify the transactions of the derived books.</span></span> <span data-ttu-id="348c4-116">Quando si preparano le transazioni del libro principale per la registrazione in un altro giornale di registrazione, le transazioni del valore derivato non vengono visualizzate.</span><span class="sxs-lookup"><span data-stu-id="348c4-116">If you prepare the primary book transactions in another journal, the transactions of the derived value are not displayed.</span></span> <span data-ttu-id="348c4-117">Queste vengono comunque registrate nei conti e nei livelli di registrazione appropriati quando si registrano le transazioni del libro principale.</span><span class="sxs-lookup"><span data-stu-id="348c4-117">However, they are posted to the appropriate accounts and posting layers when you post the primary book transactions.</span></span>

> [!NOTE]                                                                                                                               
> <span data-ttu-id="348c4-118">I libri impostati per la registrazione di transazioni a intervalli diversi da quelli del libro principale devono essere collegati al cespite come libri separati, non come libri derivati.</span><span class="sxs-lookup"><span data-stu-id="348c4-118">Books that are set up to post transactions at intervals other than the primary book intervals must be attached to the fixed asset as separate books and not as derived books.</span></span>  

<span data-ttu-id="348c4-119">Per ulteriori informazioni, vedere [Registrazione con i libri derivati](post-derived-value-models.md).</span><span class="sxs-lookup"><span data-stu-id="348c4-119">For more information, see [Posting with derived books](post-derived-value-models.md).</span></span>




