---
title: Ammortamento manuale dei cespiti per l'Italia
description: In questo argomento vengono fornite informazioni sull'ammortamento dei cespiti per le persone giuridiche in Italia.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile, LedgerJournalTransApprove, LedgerJournalTransAsset, LedgerJournalTransDaily, LedgerJournalTransVendInvoice, PurchTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264294
ms.search.region: Italy
ms.author: v-elgolu
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 1e847ecf40ce2536d724d72f243bc1c0df4f95f7
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="manual-depreciation-of-fixed-assets-for-italy"></a><span data-ttu-id="d1d6a-103">Ammortamento manuale dei cespiti per l'Italia</span><span class="sxs-lookup"><span data-stu-id="d1d6a-103">Manual depreciation of fixed assets for Italy</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d1d6a-104">In questo argomento vengono fornite informazioni sull'ammortamento dei cespiti per le persone giuridiche in Italia.</span><span class="sxs-lookup"><span data-stu-id="d1d6a-104">This topic provides information about fixed assets depreciation for legal entities in Italy.</span></span> 

<span data-ttu-id="d1d6a-105">Per le persone giuridiche in Italia, il metodo di ammortamento manuale ha una funzionalità aggiuntiva che include i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="d1d6a-105">For legal entities in Italy, the manual depreciation method has additional functionality that includes the following fields:</span></span>

-   <span data-ttu-id="d1d6a-106">**Base di calcolo** - ** **Questo campo presenta due opzioni: **Giorni** o **Mesi** nella pagina **Profili di ammortamento**.</span><span class="sxs-lookup"><span data-stu-id="d1d6a-106">**Calculation basis** -** **This field has two options: **Days** or **Months** on the **Depreciation profiles** page.</span></span> <span data-ttu-id="d1d6a-107">L'ammortamento di cespiti viene calcolato per l'anno nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="d1d6a-107">Fixed assets depreciation is calculated for the year as follows:</span></span>
    -   <span data-ttu-id="d1d6a-108">Ammortamento in giorni = intero ammortamento \* (numero di giorni rimanenti/giorni totali nell'anno)</span><span class="sxs-lookup"><span data-stu-id="d1d6a-108">Days depreciation = Full years depreciation \* (number of days remaining/total days in the year)</span></span>
    -   <span data-ttu-id="d1d6a-109">Ammortamento in mesi = intero ammortamento \* (numero di mesi rimanenti/12)</span><span class="sxs-lookup"><span data-stu-id="d1d6a-109">Months depreciation = Full years depreciation \* (number of months remaining/12)</span></span>
-   <span data-ttu-id="d1d6a-110">**Data d'esecuzione ammortamento**: questo campo è stato aggiunto alle pagine seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1d6a-110">**Depreciation run date** - This field was added to the following pages:</span></span>
    -   <span data-ttu-id="d1d6a-111">Giornale di registrazione generale</span><span class="sxs-lookup"><span data-stu-id="d1d6a-111">General journal</span></span>
    -   <span data-ttu-id="d1d6a-112">Giornale di registrazione cespiti</span><span class="sxs-lookup"><span data-stu-id="d1d6a-112">Fixed asset journal</span></span>
    -   <span data-ttu-id="d1d6a-113">Giornale di approvazione fatture</span><span class="sxs-lookup"><span data-stu-id="d1d6a-113">Invoice approval journal</span></span>
    -   <span data-ttu-id="d1d6a-114">Giornale di registrazione fatture</span><span class="sxs-lookup"><span data-stu-id="d1d6a-114">Invoice journal</span></span>
    -   <span data-ttu-id="d1d6a-115">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="d1d6a-115">Purchase order</span></span>

<span data-ttu-id="d1d6a-116">La **Data d'esecuzione ammortamento** deve essere configurata al momento dell'acquisto ed essere impostata sulla data del sistema durante l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="d1d6a-116">The **Depreciation run date** should be set up at the time of acquisition and is set to the system date during the acquisition.</span></span> <span data-ttu-id="d1d6a-117">La **Data d'esecuzione ammortamento** viene utilizzata per calcolare l'ammortamento per **Numero di giorni rimanenti** o **Numero di mesi rimanenti**, a seconda del valore di **Base di calcolo**.</span><span class="sxs-lookup"><span data-stu-id="d1d6a-117">The **Depreciation run date** is used to calculate depreciation for the **Number of days remaining** or **Number of Months remaining**, depending on the **Calculation basis** value.</span></span> <span data-ttu-id="d1d6a-118">Se la **Data d'esecuzione ammortamento** è precedente alla metà del mese (il 15 o il 14 febbraio), il mese corrente viene incluso nel numero di mesi, in caso contrario il cespite viene considerato come acquisito nel mese successivo.</span><span class="sxs-lookup"><span data-stu-id="d1d6a-118">If the **Depreciation run date** is before the middle of the month (either the 15th or 14th for February), then the current month is included in number of months, otherwise the asset is considered as acquired in the next month.</span></span>




