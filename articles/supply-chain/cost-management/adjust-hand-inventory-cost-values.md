---
title: Rettificare i valori di costo delle scorte disponibili
description: "Utilizzare la pagina Rettifica delle scorte disponibili per rettificare il valore di costo delle quantità di scorte disponibili dopo l'esecuzione di un processo di chiusura di inventario."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 9243c1bc2af1f6c60333007fd04e1f872a440b8b
ms.contentlocale: it-it
ms.lasthandoff: 01/17/2018

---

# <a name="adjust-on-hand-inventory-cost-values"></a><span data-ttu-id="28cef-103">Rettificare i valori di costo delle scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="28cef-103">Adjust on-hand inventory cost values</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="28cef-104">Utilizzare la pagina Rettifica delle scorte disponibili per rettificare il valore di costo delle quantità di scorte disponibili dopo l'esecuzione di un processo di chiusura di inventario.</span><span class="sxs-lookup"><span data-stu-id="28cef-104">Use the Adjustment of on-hand inventory page to adjust the cost value of the on-hand inventory quantities after an inventory close process is run.</span></span>

<span data-ttu-id="28cef-105">È possibile utilizzare la pagina **Rettifica delle scorte disponibili** per rettificare il valore di costo delle quantità di scorte disponibili dopo l'esecuzione di un processo di chiusura di inventario.</span><span class="sxs-lookup"><span data-stu-id="28cef-105">You can use the **Adjustment of on-hand inventory** page to adjust the cost value of on-hand inventory quantities after an inventory close process is run.</span></span> <span data-ttu-id="28cef-106">**Nota:** per aprire la pagina **Rettifica delle scorte disponibili**, sulla pagina **Chiusura e rettifica**, selezionare il record di un processo di chiusura di inventario completato, quindi fare clic su **Rettifica** &gt; **Disponibilità**.</span><span class="sxs-lookup"><span data-stu-id="28cef-106">**Note:** To open the **Adjustment of on-hand inventory** page, on the **Closing and adjustment** page, select the record of a completed inventory close process, and then click **Adjustment** &gt; **On-hand**.</span></span> <span data-ttu-id="28cef-107">**Esempio:** nel mese di febbraio sono state registrate le seguenti transazioni:</span><span class="sxs-lookup"><span data-stu-id="28cef-107">**Example:** You have the following transactions in February:</span></span>

-   <span data-ttu-id="28cef-108">1° febbraio: entrata finanziaria in magazzino per una quantità pari a 2 al costo di 10,00 EUR</span><span class="sxs-lookup"><span data-stu-id="28cef-108">February 1: An inventory financial receipt for a quantity of 2 at a cost of USD 10.00</span></span>
-   <span data-ttu-id="28cef-109">5 febbraio: entrata finanziaria in magazzino per una quantità pari a 1 al costo di 13,00 EUR</span><span class="sxs-lookup"><span data-stu-id="28cef-109">February 5: An inventory financial receipt for a quantity of 1 at a cost of USD 13.00</span></span>
-   <span data-ttu-id="28cef-110">19 febbraio: uscita finanziaria da magazzino di una quantità pari a 1 al costo medio corrente di 11,00 EUR</span><span class="sxs-lookup"><span data-stu-id="28cef-110">February 19: An inventory financial issue for a quantity of 1 at a running average cost of USD 11.00</span></span>

<span data-ttu-id="28cef-111">L'articolo è stato impostato con il modello inventariale FIFO e la chiusura dell'inventario è stata eseguita il 28 febbraio.</span><span class="sxs-lookup"><span data-stu-id="28cef-111">This item was set up with the first in, first out (FIFO) inventory model, and inventory close was performed as of February 28.</span></span> <span data-ttu-id="28cef-112">La transazione di uscita finanziaria di 11,00 EUR verrà liquidata a fronte dell'entrata finanziaria datata 1° febbraio e verrà eseguita una rettifica per 1,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="28cef-112">The financial issue transaction of USD 11.00 will be settled against the financial receipt that is dated February 1, and an adjustment of USD 1.00 will be made.</span></span> <span data-ttu-id="28cef-113">Le seguenti entrate in magazzino conterranno quindi quantità in magazzino aperte:</span><span class="sxs-lookup"><span data-stu-id="28cef-113">The following inventory receipts will then contain open inventory quantities:</span></span>

-   <span data-ttu-id="28cef-114">1 febbraio: quantità pari a 1 al costo di 10,00 EUR</span><span class="sxs-lookup"><span data-stu-id="28cef-114">February 1: A quantity of 1 at a cost of USD 10.00</span></span>
-   <span data-ttu-id="28cef-115">5 febbraio: quantità pari a 1 al costo di 13,00 EUR</span><span class="sxs-lookup"><span data-stu-id="28cef-115">February 5: A quantity of 1 at a cost of USD 13.00</span></span>

<span data-ttu-id="28cef-116">Per impostare il costo di questi due articoli a EUR 15,00, utilizzare l'opzione di rettifica delle disponibilità per aprire le quantità disponibili aperte all'ultimo periodo di chiusura dell'inventario.</span><span class="sxs-lookup"><span data-stu-id="28cef-116">To set the cost of these two items to USD 15.00, use the on-hand adjustment option to adjust the open on-hand quantities as of the last inventory close period.</span></span> <span data-ttu-id="28cef-117">**Nota:** la data di registrazione della transazione di rettifica delle disponibilità sarà la data dell'ultima chiusura dell'inventario.</span><span class="sxs-lookup"><span data-stu-id="28cef-117">**Note:** The posting date of the on-hand adjustment transaction will be the date of the last inventory close.</span></span> <span data-ttu-id="28cef-118">Non è possibile modificare questa data.</span><span class="sxs-lookup"><span data-stu-id="28cef-118">This date can't be modified.</span></span>

