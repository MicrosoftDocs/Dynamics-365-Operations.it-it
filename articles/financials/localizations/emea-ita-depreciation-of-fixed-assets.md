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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c4f5b0035ac2f757d6172dab6cd7b37d1bf8d3bd
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="manual-depreciation-of-fixed-assets-for-italy"></a><span data-ttu-id="97c1b-103">Ammortamento manuale dei cespiti per l'Italia</span><span class="sxs-lookup"><span data-stu-id="97c1b-103">Manual depreciation of fixed assets for Italy</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="97c1b-104">In questo argomento vengono fornite informazioni sull'ammortamento dei cespiti per le persone giuridiche in Italia.</span><span class="sxs-lookup"><span data-stu-id="97c1b-104">This topic provides information about fixed assets depreciation for legal entities in Italy.</span></span> 

<span data-ttu-id="97c1b-105">Per le persone giuridiche in Italia, il metodo di ammortamento manuale ha una funzionalità aggiuntiva che include i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="97c1b-105">For legal entities in Italy, the manual depreciation method has additional functionality that includes the following fields:</span></span>

- <span data-ttu-id="97c1b-106"><strong>Base di calcolo</strong> -** <strong>Questo campo contiene due opzioni: **Giorni</strong> o <strong>Mesi</strong> nella pagina <strong>Profili di ammortamento</strong>.</span><span class="sxs-lookup"><span data-stu-id="97c1b-106"><strong>Calculation basis</strong> -** <strong>This field has two options: **Days</strong> or <strong>Months</strong> on the <strong>Depreciation profiles</strong> page.</span></span> <span data-ttu-id="97c1b-107">L'ammortamento di cespiti viene calcolato per l'anno nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="97c1b-107">Fixed assets depreciation is calculated for the year as follows:</span></span>
  -   <span data-ttu-id="97c1b-108">Ammortamento in giorni = intero ammortamento \* (numero di giorni rimanenti/giorni totali nell'anno)</span><span class="sxs-lookup"><span data-stu-id="97c1b-108">Days depreciation = Full years depreciation \* (number of days remaining/total days in the year)</span></span>
  -   <span data-ttu-id="97c1b-109">Ammortamento in mesi = intero ammortamento \* (numero di mesi rimanenti/12)</span><span class="sxs-lookup"><span data-stu-id="97c1b-109">Months depreciation = Full years depreciation \* (number of months remaining/12)</span></span>
- <span data-ttu-id="97c1b-110">**Data d'esecuzione ammortamento**: questo campo è stato aggiunto alle pagine seguenti:</span><span class="sxs-lookup"><span data-stu-id="97c1b-110">**Depreciation run date** - This field was added to the following pages:</span></span>
  -   <span data-ttu-id="97c1b-111">Giornale di registrazione generale</span><span class="sxs-lookup"><span data-stu-id="97c1b-111">General journal</span></span>
  -   <span data-ttu-id="97c1b-112">Giornale di registrazione cespiti</span><span class="sxs-lookup"><span data-stu-id="97c1b-112">Fixed asset journal</span></span>
  -   <span data-ttu-id="97c1b-113">Giornale di approvazione fatture</span><span class="sxs-lookup"><span data-stu-id="97c1b-113">Invoice approval journal</span></span>
  -   <span data-ttu-id="97c1b-114">Giornale di registrazione fatture</span><span class="sxs-lookup"><span data-stu-id="97c1b-114">Invoice journal</span></span>
  -   <span data-ttu-id="97c1b-115">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="97c1b-115">Purchase order</span></span>

<span data-ttu-id="97c1b-116">La **Data d'esecuzione ammortamento** deve essere configurata al momento dell'acquisto ed essere impostata sulla data del sistema durante l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="97c1b-116">The **Depreciation run date** should be set up at the time of acquisition and is set to the system date during the acquisition.</span></span> <span data-ttu-id="97c1b-117">La **Data d'esecuzione ammortamento** viene utilizzata per calcolare l'ammortamento per **Numero di giorni rimanenti** o **Numero di mesi rimanenti**, a seconda del valore di **Base di calcolo**.</span><span class="sxs-lookup"><span data-stu-id="97c1b-117">The **Depreciation run date** is used to calculate depreciation for the **Number of days remaining** or **Number of Months remaining**, depending on the **Calculation basis** value.</span></span> <span data-ttu-id="97c1b-118">Se la **Data d'esecuzione ammortamento** è precedente alla metà del mese (il 15 o il 14 febbraio), il mese corrente viene incluso nel numero di mesi, in caso contrario il cespite viene considerato come acquisito nel mese successivo.</span><span class="sxs-lookup"><span data-stu-id="97c1b-118">If the **Depreciation run date** is before the middle of the month (either the 15th or 14th for February), then the current month is included in number of months, otherwise the asset is considered as acquired in the next month.</span></span>




