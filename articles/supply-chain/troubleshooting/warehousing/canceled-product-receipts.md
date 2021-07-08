---
title: Le ricevute di prodotti annullate non aggiornano lo stato della transazione su Registrato
description: Dopo aver annullato la ricevuta di prodotti in un carico in entrata, il sistema aggiorna automaticamente lo stato della transazione di magazzino da Ricevuto a Ordinato.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c86457d50a7a9ac2a699a0e0a9c7bdf4cd7c67b
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294108"
---
# <a name="canceled-product-receipts-dont-update-transaction-status-to-registered"></a><span data-ttu-id="c4679-103">Le ricevute di prodotti annullate non aggiornano lo stato della transazione su Registrato</span><span class="sxs-lookup"><span data-stu-id="c4679-103">Canceled product receipts don't update transaction status to Registered</span></span>

## <a name="symptoms"></a><span data-ttu-id="c4679-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="c4679-104">Symptoms</span></span>

<span data-ttu-id="c4679-105">Dopo aver eseguito l'azione **Annulla ricevute prodotti** in un carico in entrata, il sistema aggiorna automaticamente lo stato delle transazioni di magazzino da *Ricevuto* a *Ordinato*.</span><span class="sxs-lookup"><span data-stu-id="c4679-105">After you run the **Cancel product receipts** action on an inbound load, the system automatically updates the status of inventory transactions from *Received* to *Ordered*.</span></span>

## <a name="resolution"></a><span data-ttu-id="c4679-106">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="c4679-106">Resolution</span></span>

<span data-ttu-id="c4679-107">Quando i documenti di trasporto vengono annullati per i carichi in uscita, lo stato delle transazioni di magazzino rimane *Prelevato*.</span><span class="sxs-lookup"><span data-stu-id="c4679-107">When packing slips are canceled for outbound loads, the status of inventory transactions remains *Picked*.</span></span> <span data-ttu-id="c4679-108">Tuttavia, quando le ricevute prodotti da un carico in entrata vengono annullate, lo stato delle transazioni di magazzino non viene ripristinato su *Registrato*.</span><span class="sxs-lookup"><span data-stu-id="c4679-108">However, when product receipts from an inbound load are canceled, the status of inventory transactions isn't restored to *Registered*.</span></span> <span data-ttu-id="c4679-109">Pertanto, dopo l'annullamento di una ricevuta prodotti da un carico in entrata, l'addetto al magazzino deve registrare nuovamente le quantità di articoli per i carichi.</span><span class="sxs-lookup"><span data-stu-id="c4679-109">Therefore, after a product receipt from an inbound load is canceled, the warehouse worker must re-register item quantities for the loads.</span></span>

<span data-ttu-id="c4679-110">Per ulteriori informazioni, vedi [Registrare le quantità di articoli che arrivano in un carico in entrata](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).</span><span class="sxs-lookup"><span data-stu-id="c4679-110">For more information, see [Register item quantities that arrive on an inbound load](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).</span></span>
