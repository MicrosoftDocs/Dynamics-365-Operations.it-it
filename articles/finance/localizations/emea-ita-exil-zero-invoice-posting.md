---
title: Registrazione fatture con importo zero
description: Questo argomento spiega come registrare transazioni finanziarie per fatture che hanno un importo pari a 0 (zero).
author: ilkond
manager: AnnBe
ms.date: 11/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-29
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: feb01e1eb34631fa0f94283d7b88ba4155928883
ms.sourcegitcommit: 4c60f5dccdf0b94ed110a657ef331546adc5424a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2020
ms.locfileid: "2982324"
---
# <a name="posting-invoices-with-zero-amount"></a><span data-ttu-id="f655a-103">Registrazione fatture con importo zero</span><span class="sxs-lookup"><span data-stu-id="f655a-103">Posting invoices with zero amount</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f655a-104">In Italia, devono essere registrate transazioni finanziarie per fatture che hanno un importo totale pari a 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="f655a-104">In Italy, financial transactions for invoices that have a total amount of 0 (zero) must be posted.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f655a-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f655a-105">Prerequisites</span></span>

<span data-ttu-id="f655a-106">Prima di poter registrare transazioni finanziarie per fatture che hanno un importo totale pari a 0 (zero), devono essere soddisfatti i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="f655a-106">Before you can post financial transactions for invoices that have a total amount of 0 (zero), the following prerequisites must be met:</span></span>

- <span data-ttu-id="f655a-107">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="f655a-107">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="f655a-108">Nell'area di lavoro **Gestione funzionalità**, attivare la funzionalità **Registrazione fatture con importo pari a zero**.</span><span class="sxs-lookup"><span data-stu-id="f655a-108">In the **Feature management** workspace, turn on the **Posting invoices with zero amount** feature.</span></span> <span data-ttu-id="f655a-109">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f655a-109">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="posting-invoices-that-have-an-amount-of-0-zero"></a><span data-ttu-id="f655a-110">Registrazione di fatture con un importo pari a 0 (zero)</span><span class="sxs-lookup"><span data-stu-id="f655a-110">Posting invoices that have an amount of 0 (zero)</span></span>

<span data-ttu-id="f655a-111">La funzione Registrazione fatture con importo pari a zero si applica alle fatture create nei moduli **Contabilità clienti** e **Contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="f655a-111">The Posting invoices with zero amount feature applies to invoices that are created in the **Accounts receivable** and **Accounts payable** modules.</span></span>

<span data-ttu-id="f655a-112">Quando vengono registrate fatture con un importo pari a 0 (zero), il sistema crea transazioni cliente/fornitore e transazioni giustificativo.</span><span class="sxs-lookup"><span data-stu-id="f655a-112">When invoices that have an amount of 0 (zero) are posted, the system creates customer/vendor transactions and voucher transactions.</span></span>
