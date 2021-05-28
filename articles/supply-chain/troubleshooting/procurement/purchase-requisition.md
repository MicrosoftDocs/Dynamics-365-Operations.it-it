---
title: Impossibile aggiungere una riga a una richiesta di acquisto dopo aver richiesto una modifica
description: Il sistema non ti consente di aggiungere una riga a una richiesta di acquisto dopo che hai richiesto una modifica.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchReqTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: jeyao
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5dbb55a6a352a7acf16729c1cfe1afdac2e2eef8
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026648"
---
# <a name="you-cant-add-a-line-to-a-purchase-requisition-after-you-request-a-change"></a><span data-ttu-id="145f8-103">Impossibile aggiungere una riga a una richiesta di acquisto dopo aver richiesto una modifica</span><span class="sxs-lookup"><span data-stu-id="145f8-103">You can't add a line to a purchase requisition after you request a change</span></span>

<span data-ttu-id="145f8-104">Numero KB: 4611211</span><span class="sxs-lookup"><span data-stu-id="145f8-104">KB number: 4611211</span></span>

## <a name="symptoms"></a><span data-ttu-id="145f8-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="145f8-105">Symptoms</span></span>

<span data-ttu-id="145f8-106">Il sistema non ti consente di aggiungere una riga a una richiesta di acquisto dopo che hai richiesto una modifica.</span><span class="sxs-lookup"><span data-stu-id="145f8-106">The system doesn't allow you to add a line to a purchase requisition after you request a change.</span></span>

## <a name="resolution"></a><span data-ttu-id="145f8-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="145f8-107">Resolution</span></span>

<span data-ttu-id="145f8-108">Devi richiamare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="145f8-108">You must recall the workflow.</span></span> <span data-ttu-id="145f8-109">Una volta che lo stato della richiesta di acquisto è *Bozza*, puoi continuare a modificare la richiesta o aggiungervi una riga.</span><span class="sxs-lookup"><span data-stu-id="145f8-109">After the purchase requisition is in *Draft* status, you can continue to edit it or add a line to it.</span></span>
