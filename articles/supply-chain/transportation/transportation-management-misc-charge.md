---
title: Spese varie della gestione dei trasporti
description: Questo argomento spiega come le spese generate dal trasporto devono essere associate a un codice spese.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: cb503072fb76e04aa01ff2d231c756eeb244c65a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004703"
---
# <a name="transportation-management-miscellaneous-charges"></a><span data-ttu-id="21325-103">Spese varie della gestione dei trasporti</span><span class="sxs-lookup"><span data-stu-id="21325-103">Transportation management miscellaneous charges</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="21325-104">Come per tutte le spese varie, le spese generate dal trasporto devono essere associate a un codice spese.</span><span class="sxs-lookup"><span data-stu-id="21325-104">As with all miscellaneous charges, transportation-generated charges must be associated with a charge code.</span></span> <span data-ttu-id="21325-105">In caso contrario, non verranno aggiunte all'ordine come spesa varia.</span><span class="sxs-lookup"><span data-stu-id="21325-105">Otherwise, they won't be added back to the order as a miscellaneous charge.</span></span> <span data-ttu-id="21325-106">Il **Codice spese** determina la modalità di contabilizzazione dell'addebito in relazione all'ordine e alla riga ordine in cui viene aggiunto.</span><span class="sxs-lookup"><span data-stu-id="21325-106">The **Charges code** determines how the charge is accounted for in relation to the order and order line where it is added.</span></span>

<span data-ttu-id="21325-107">Andare a **Gestione trasporti > Impostazione > Valutazione > Spese varie** definire i criteri di qualificazione che determinano quando uno specifico **Codice spese** viene applicato a una spesa.</span><span class="sxs-lookup"><span data-stu-id="21325-107">Go to **Transportation management > Setup > Rating > Miscellaneous charges** to define the qualifying criteria that determine when a specific **Charges code** is applied to a charge.</span></span>

<span data-ttu-id="21325-108">È necessaria almeno una configurazione per ogni impostazione **Modulo spese** pertinente (*Cliente* e *Fornitore*) dove il **Tipo di spesa varia** è impostato su *Nessuno*.</span><span class="sxs-lookup"><span data-stu-id="21325-108">You should have at least one setup for each relevant **Charges module** setting (*Customer* and *Vendor*) where the **Miscellaneous charge type** is set to *None*.</span></span> <span data-ttu-id="21325-109">Se questa manca, la spesa varia *non* viene aggiunta all'ordine.</span><span class="sxs-lookup"><span data-stu-id="21325-109">If this is missing, the miscellaneous charge will *not* be added to the order.</span></span>
