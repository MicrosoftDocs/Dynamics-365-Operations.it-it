---
title: L'articolo non può avere una distinta base o una formula
description: Quando tenti di stabilizzare un ordine, ricevi un messaggio di errore durante la convalida dell'articolo. Indica che l'articolo non può avere una distinta base (DBA) o una formula.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6739b8b1e4d080055a2a0501427eac1c2e8a96c5
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294110"
---
# <a name="item-cant-have-a-bom-or-formula"></a><span data-ttu-id="0425a-104">L'articolo non può avere una distinta base o una formula</span><span class="sxs-lookup"><span data-stu-id="0425a-104">Item can't have a BOM or formula</span></span>

<span data-ttu-id="0425a-105">Codice errore: PRO2614</span><span class="sxs-lookup"><span data-stu-id="0425a-105">Error code: PRO2614</span></span>

## <a name="symptoms"></a><span data-ttu-id="0425a-106">Sintomi</span><span class="sxs-lookup"><span data-stu-id="0425a-106">Symptoms</span></span>

<span data-ttu-id="0425a-107">Quando tenti di stabilizzare un ordine, ricevi il seguente messaggio di errore durante la convalida dell'articolo:</span><span class="sxs-lookup"><span data-stu-id="0425a-107">When you try to firm an order, you receive the following error message during item validation:</span></span>

> <span data-ttu-id="0425a-108">L'articolo non può contenere una DBA o una formula</span><span class="sxs-lookup"><span data-stu-id="0425a-108">Item cannot have a BOM or formula</span></span>

## <a name="resolution"></a><span data-ttu-id="0425a-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="0425a-109">Resolution</span></span>

<span data-ttu-id="0425a-110">Gli articoli che hanno una distinta base (DBA) o una formula devono essere di tipo *Elemento di pianificazione*, *DBA*, o *formula*.</span><span class="sxs-lookup"><span data-stu-id="0425a-110">Items that have a bill of materials (BOM) or formula must be of the *Planning item*, *BOM*, or *formula* type.</span></span> <span data-ttu-id="0425a-111">Per modificare il tipo di un elemento effettua le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="0425a-111">To change the type of an item, follow these steps.</span></span>

1. <span data-ttu-id="0425a-112">Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="0425a-112">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="0425a-113">Apri il prodotto rilevante.</span><span class="sxs-lookup"><span data-stu-id="0425a-113">Open the relevant product.</span></span>
1. <span data-ttu-id="0425a-114">Nella Scheda dettaglio **Progetta**, imposta il campo **Tipo di produzione** su *Elemento di pianificazione*, *DBA*, o *formula*.</span><span class="sxs-lookup"><span data-stu-id="0425a-114">On the **Engineer** FastTab, set the **Production type** field to *Planning item*, *BOM*, or *formula*.</span></span>
