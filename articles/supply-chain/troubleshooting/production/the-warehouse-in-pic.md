---
title: Il magazzino nel giornale di registrazione distinte di prelievo non viene aggiornato in una riga DBA.
description: Il magazzino nel giornale di registrazione distinte di prelievo non viene aggiornato in una riga della distinta di prelievo (DBA).
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5d24c0b8538f3894fd1d2a3edb3a6ed8633c9609
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026634"
---
# <a name="the-warehouse-in-the-picking-list-journal-isnt-updated-on-a-bom-line"></a><span data-ttu-id="d9b0a-103">Il magazzino nel giornale di registrazione distinte di prelievo non viene aggiornato in una riga DBA</span><span class="sxs-lookup"><span data-stu-id="d9b0a-103">The warehouse in the picking list journal isn't updated on a BOM line</span></span>

<span data-ttu-id="d9b0a-104">Numero KB: 4614848</span><span class="sxs-lookup"><span data-stu-id="d9b0a-104">KB number: 4614848</span></span>

## <a name="symptoms"></a><span data-ttu-id="d9b0a-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="d9b0a-105">Symptoms</span></span>

<span data-ttu-id="d9b0a-106">Il magazzino nel giornale di registrazione distinte di prelievo non viene aggiornato in una riga della distinta di prelievo (DBA).</span><span class="sxs-lookup"><span data-stu-id="d9b0a-106">The warehouse in the picking list journal isn't updated on a bill of materials (BOM) line.</span></span>

## <a name="resolution"></a><span data-ttu-id="d9b0a-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d9b0a-107">Resolution</span></span>

<span data-ttu-id="d9b0a-108">Il sistema si comporta come previsto.</span><span class="sxs-lookup"><span data-stu-id="d9b0a-108">The system is behaving as designed.</span></span> <span data-ttu-id="d9b0a-109">Se viene creata una riga del giornale di registrazione distinte di prelievo che ha un riferimento (tramite l'ID lotto) a una riga della distinta base di produzione, il magazzino nella riga della DBA di produzione non verrà aggiornato se la dimensione del magazzino nella riga del giornale di registrazione distinte di produzione viene modificata successivamente.</span><span class="sxs-lookup"><span data-stu-id="d9b0a-109">If a picking list journal line is created that has a reference (via the lot ID) to a production BOM line, the warehouse on the production BOM line won't be updated if the warehouse dimension on the production picking list journal line is changed later.</span></span>
