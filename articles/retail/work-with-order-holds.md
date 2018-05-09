---
title: Sospensioni ordine
description: In questo argomento vengono descritte le sospensioni degli ordini tramite l'utilizzo di Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: MCRHoldCodeTable, MCRSalesTableOrderHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 106ce40f93704e67e53db2e62ae481d271aed755
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="order-holds"></a><span data-ttu-id="c3a83-103">Sospensioni ordine</span><span class="sxs-lookup"><span data-stu-id="c3a83-103">Order holds</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c3a83-104">In questo argomento vengono descritte le sospensioni degli ordini tramite l'utilizzo di Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="c3a83-104">This topic describes holds on orders using Dynamics 365 for Retail.</span></span>

<span data-ttu-id="c3a83-105">Un ordine può essere sospeso per diversi motivi.</span><span class="sxs-lookup"><span data-stu-id="c3a83-105">An order can be put on hold for various reasons.</span></span> <span data-ttu-id="c3a83-106">Ad esempio, è possibile sospendere un ordine fino a che non può essere verificato un indirizzo cliente o un metodo di pagamento o fino a che un responsabile non può verificare il limite di credito del cliente.</span><span class="sxs-lookup"><span data-stu-id="c3a83-106">For example, you might put an order on hold until the customer address or payment method can be verified, or until a manager can review the customer’s credit limit.</span></span> <span data-ttu-id="c3a83-107">Durante il processo di vendita, ci sono volte in cui è necessario sospendere un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="c3a83-107">During the sales process, there are times when sales orders must be put on hold.</span></span> <span data-ttu-id="c3a83-108">Ad esempio, un ordine cliente potrebbe essere sospeso a causa di problemi di pagamento di un cliente, per il sospetto di una frode o perché un responsabile deve esaminare l'ordine.</span><span class="sxs-lookup"><span data-stu-id="c3a83-108">For example, a sales order might be put on hold because of issues with a customer payment, because of suspected fraud, or because a manager must review the order.</span></span> <span data-ttu-id="c3a83-109">Quando un ordine cliente viene sospeso, a tale ordine viene assegnato un codice sospensione ordine per indicare il motivo della sospensione.</span><span class="sxs-lookup"><span data-stu-id="c3a83-109">When a sales order is put on hold, an order hold code is assigned to the sales order to indicate the reason for the hold.</span></span> <span data-ttu-id="c3a83-110">I codici sospensione degli ordini cliente vengono configurati in **Vendite e marketing** &gt; **Impostazione** &gt; **Ordini cliente** &gt; **Codici sospensione ordine**.</span><span class="sxs-lookup"><span data-stu-id="c3a83-110">Sales order hold codes are configured at **Sales and marketing** &gt; **Setup** &gt; **Sales orders** &gt; **Order holds codes**.</span></span> <span data-ttu-id="c3a83-111">Un ordine cliente può sospeso manualmente al momento della creazione dell'ordine o in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="c3a83-111">A sales order can be put on hold manually at the time of order creation or later.</span></span> <span data-ttu-id="c3a83-112">Inoltre, un ordine può essere sospeso automaticamente, in base a regole sulla frode.</span><span class="sxs-lookup"><span data-stu-id="c3a83-112">Additionally, an order can be put on hold automatically, based on fraud rules.</span></span> <span data-ttu-id="c3a83-113">Mentre un ordine cliente è in attesa, potrebbe essere necessario aggiornarlo con ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="c3a83-113">While a sales order is on hold, you might have to update it with more information.</span></span> <span data-ttu-id="c3a83-114">Oppure è possibile che si desideri eseguire il Check-out dell'ordine cliente mentre si continua a compilarlo.</span><span class="sxs-lookup"><span data-stu-id="c3a83-114">Alternatively, you might want to check out the sales order as you continue to work on it.</span></span> <span data-ttu-id="c3a83-115">È possibile eseguire il check-out di un ordine cliente, eseguirne di nuovo il check-in e, quando necessario, sovrascrivere il check-out di un altro utente utilizzando il workbench di sospensione dell'ordine (**Vendita al dettaglio** &gt; **Clienti** &gt; **Sospensioni ordine**).</span><span class="sxs-lookup"><span data-stu-id="c3a83-115">You can check out a sales order, check it back in, and even override the checkout of another user by using the order hold workbench (**Retail** &gt; **Customers** &gt; **Order holds**).</span></span> <span data-ttu-id="c3a83-116">Quando un ordine è pronto per essere completato, è necessario rimuovere la sospensione prima di poter completare il processo di ordine.</span><span class="sxs-lookup"><span data-stu-id="c3a83-116">When an order is ready to be completed, you must remove the hold before you can complete the order process.</span></span>




