---
title: Risolvere i problemi dei rilasci parziali e delle spedizioni parziali
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano rilasci parziali e spedizioni parziali in Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1c9246376505e163a4a41bf141a98deed0fd511f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263232"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a><span data-ttu-id="e4de2-103">Risolvere i problemi dei rilasci parziali e delle spedizioni parziali</span><span class="sxs-lookup"><span data-stu-id="e4de2-103">Troubleshoot partial releases and partial shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4de2-104">Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano rilasci parziali e spedizioni parziali in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e4de2-104">This topic describes how to fix common issues that you might encounter while you work with partial releases and partial shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a><span data-ttu-id="e4de2-105">Lo stato di rilascio di un ordine cliente rimane Rilasciato parzialmente anche dopo che l'ordine cliente è stato fatturato.</span><span class="sxs-lookup"><span data-stu-id="e4de2-105">The release status of a sales order remains Partially released even after the sales order is invoiced.</span></span>

### <a name="issue-description"></a><span data-ttu-id="e4de2-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="e4de2-106">Issue description</span></span>

<span data-ttu-id="e4de2-107">Un ordine cliente è un ordine di consegna, ma uno o più articoli hanno una modalità di consegna diversa.</span><span class="sxs-lookup"><span data-stu-id="e4de2-107">A sales order is a delivery order, but one or more items on it have a different mode of delivery.</span></span> <span data-ttu-id="e4de2-108">Dopo che l'ordine è stato fatturato, ha ancora lo stato di rilascio *Parzialmente rilasciato*.</span><span class="sxs-lookup"><span data-stu-id="e4de2-108">After the order is invoiced, it still has a release status of *Partially released*.</span></span>

<span data-ttu-id="e4de2-109">Ad esempio, un ordine cliente ha due articoli: uno per la consegna e uno per il ritiro.</span><span class="sxs-lookup"><span data-stu-id="e4de2-109">For example, a sales order has two items: one for delivery and one for pickup.</span></span> <span data-ttu-id="e4de2-110">Sia la consegna che il ritiro sono stati effettuati.</span><span class="sxs-lookup"><span data-stu-id="e4de2-110">Both the delivery and the pickup have been done.</span></span> <span data-ttu-id="e4de2-111">Pertanto, entrambe le righe sono state fatturate.</span><span class="sxs-lookup"><span data-stu-id="e4de2-111">Therefore, both lines have been invoiced.</span></span> <span data-ttu-id="e4de2-112">Tuttavia, lo stato di rilascio è ancora mostrato come *Parzialmente rilasciato*, che è fuorviante.</span><span class="sxs-lookup"><span data-stu-id="e4de2-112">However, the release status is still shown as *Partially released*, which is misleading.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e4de2-113">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e4de2-113">Issue resolution</span></span>

<span data-ttu-id="e4de2-114">Lo stato di rilascio si applica solo alle righe ordine in cui gli articoli sono abilitati per la gestione del magazzino.</span><span class="sxs-lookup"><span data-stu-id="e4de2-114">The release status applies only to order lines where the items are enabled for warehouse management.</span></span> <span data-ttu-id="e4de2-115">Pertanto, lo stato di rilascio rimane *Parzialmente rilasciato* in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="e4de2-115">Therefore, the release status remains *Partially released* in this scenario.</span></span> <span data-ttu-id="e4de2-116">Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e4de2-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="e4de2-117">È possibile aggiungere un'estensione come parte del documento di trasporto e del processo di fatturazione per aggiornare lo stato di rilascio.</span><span class="sxs-lookup"><span data-stu-id="e4de2-117">An extension could be added as part of the packing slip and invoicing process to update the release status.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]