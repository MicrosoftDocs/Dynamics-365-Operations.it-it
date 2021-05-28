---
title: Impossibile aggiornare il costo unitario previsto quando si importano record di previsione della domanda
description: Quando si utilizzano entità di dati per importare record di previsione della domanda, il prezzo di costo dei record esistenti non viene aggiornato di modo che corrisponda ai dati importati.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c8ea8322a6c7bafe2dfcaaee3e9989f753c85e2a
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026647"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a><span data-ttu-id="3d346-103">Impossibile aggiornare il costo unitario previsto quando si importano record di previsione della domanda</span><span class="sxs-lookup"><span data-stu-id="3d346-103">You can't update the forecasted unit cost when you import demand forecast records</span></span>

<span data-ttu-id="3d346-104">Numero KB: 4614109</span><span class="sxs-lookup"><span data-stu-id="3d346-104">KB number: 4614109</span></span>

## <a name="symptoms"></a><span data-ttu-id="3d346-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="3d346-105">Symptoms</span></span>

<span data-ttu-id="3d346-106">Quando utilizzi entità di dati per importare record di previsione della domanda, il valore **Costo unitario previsto** dei record esistenti non viene aggiornato di modo che corrisponda ai dati importati.</span><span class="sxs-lookup"><span data-stu-id="3d346-106">When you use data entities to import demand forecast records, the **Forecasted unit cost** value for existing records isn't updated so that it matches the imported data.</span></span>

## <a name="cause"></a><span data-ttu-id="3d346-107">Causa</span><span class="sxs-lookup"><span data-stu-id="3d346-107">Cause</span></span>

<span data-ttu-id="3d346-108">**Costo unitario previsto** è un campo di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="3d346-108">**Forecasted unit cost** is a read-only field.</span></span> <span data-ttu-id="3d346-109">Il valore si basa sul costo unitario del prodotto e non può essere impostato direttamente tramite importazione.</span><span class="sxs-lookup"><span data-stu-id="3d346-109">The value is based on the product unit cost and can't be set directly through import.</span></span>

## <a name="resolution"></a><span data-ttu-id="3d346-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="3d346-110">Resolution</span></span>

<span data-ttu-id="3d346-111">Poiché il campo è di sola lettura, non è possibile importare valori per lo stesso.</span><span class="sxs-lookup"><span data-stu-id="3d346-111">Because the field is read only, you can't import values for it.</span></span> <span data-ttu-id="3d346-112">Il valore verrà calcolato in base alla logica aziendale esistente.</span><span class="sxs-lookup"><span data-stu-id="3d346-112">The value will be calculated according to the existing business logic.</span></span>
