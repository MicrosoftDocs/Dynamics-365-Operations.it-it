---
title: Impossibile fatturare un ordine cliente visualizzabile dal cliente
description: Non è più possibile fatturare l'ordine cliente originale e l'ordine fornitore con consegna diretta originale dopo aver abilitato l'opzione Registra fattura automaticamente.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ab18a2a1dec4b70c55a55637b087c6b11023aa40
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026639"
---
# <a name="you-cant-invoice-a-customer-facing-sales-order"></a><span data-ttu-id="8726b-103">Impossibile fatturare un ordine cliente visualizzabile dal cliente</span><span class="sxs-lookup"><span data-stu-id="8726b-103">You can't invoice a customer-facing sales order</span></span>

<span data-ttu-id="8726b-104">Numero KB: 4611793</span><span class="sxs-lookup"><span data-stu-id="8726b-104">KB number: 4611793</span></span>

## <a name="symptoms"></a><span data-ttu-id="8726b-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="8726b-105">Symptoms</span></span>

<span data-ttu-id="8726b-106">Non è più possibile fatturare l'ordine cliente originale e l'ordine fornitore con consegna diretta originale dopo aver abilitato l'opzione **Registra fattura automaticamente** nella pagina **Interaziendale** di un fornitore.</span><span class="sxs-lookup"><span data-stu-id="8726b-106">You can no longer invoice the original sales order and the original direct delivery purchase order after you enable the **Post invoice automatically** option on the **Intercompany** page for a vendor.</span></span>

## <a name="resolution"></a><span data-ttu-id="8726b-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="8726b-107">Resolution</span></span>

<span data-ttu-id="8726b-108">Il comportamento di sincronizzazione per le fatture degli ordini di consegna diretta e interaziendali è controllato e forzato dai parametri descritti in [Impostare i parametri per la registrazione di un ordine interaziendale](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).</span><span class="sxs-lookup"><span data-stu-id="8726b-108">The synchronization behavior for intercompany and direct delivery order invoices is controlled and forced by the parameters that are described in [Set up parameters to post an intercompany order](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).</span></span>

<span data-ttu-id="8726b-109">Dopo aver impostato tali parametri, devi dapprima fatturare l'ordine cliente interaziendale.</span><span class="sxs-lookup"><span data-stu-id="8726b-109">After you set those parameters, you must invoice the intercompany sales order first.</span></span> <span data-ttu-id="8726b-110">Gli ordini cliente e gli ordini fornitore originali verranno quindi sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="8726b-110">The original sales orders and purchase orders will then be synchronized.</span></span>
