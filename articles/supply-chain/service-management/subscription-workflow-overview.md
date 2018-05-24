---
title: Informazioni generali sul flusso di lavoro delle sottoscrizioni
description: In questo argomento viene fornita una panoramica del flusso di lavoro delle sottoscrizioni.
author: YuyuScheller
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: b4872c0753b54bdddf2c7778a13819726eea4a90
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---


# <a name="subscription-workflow-overview"></a><span data-ttu-id="5c687-103">Informazioni generali sul flusso di lavoro delle sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="5c687-103">Subscription workflow overview</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="5c687-104">Si supponga di essere l'amministratore delle sottoscrizioni di una società elettrica che offre sottoscrizioni per la manutenzione di linee elettriche.</span><span class="sxs-lookup"><span data-stu-id="5c687-104">You are the subscriptions administrator for a light company that offers subscriptions for lighting rig maintenance.</span></span> <span data-ttu-id="5c687-105">Un cliente si rivolge alla società per richiedere una sottoscrizione annuale.</span><span class="sxs-lookup"><span data-stu-id="5c687-105">A customer contacts your company to purchase a yearly subscription for lighting rig maintenance.</span></span>

## <a name="setting-up-subscriptions"></a><span data-ttu-id="5c687-106">Impostazione di sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="5c687-106">Setting up subscriptions</span></span>

<span data-ttu-id="5c687-107">Per impostare una sottoscrizione, è innanzitutto necessario creare un gruppo di sottoscrizioni per il nuovo contratto di assistenza o verificare l'esistenza di tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="5c687-107">To set up a subscription, you must first create a subscription group for the new service agreement or verify that a subscription group exists.</span></span> <span data-ttu-id="5c687-108">Se il gruppo di sottoscrizioni è disponibile, è necessario impostarlo in modo che sia possibile eseguire una fatturazione annuale al cliente e accumulare i ricavi da vendite ogni mese dell'anno.</span><span class="sxs-lookup"><span data-stu-id="5c687-108">If a subscription group exists, you must set it up to invoice the customer yearly and to accrue sales revenue every month of the year.</span></span> <span data-ttu-id="5c687-109">Per ulteriori informazioni su come impostare sottoscrizioni, vedere [Impostare gruppi di sottoscrizioni](set-up-subscription-groups.md).</span><span class="sxs-lookup"><span data-stu-id="5c687-109">For more information about how to set up subscriptions, see [Set up subscription groups](set-up-subscription-groups.md).</span></span>

<span data-ttu-id="5c687-110">Dopo la creazione del gruppo è possibile creare la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="5c687-110">After the subscription group is created, you can create the subscription.</span></span> <span data-ttu-id="5c687-111">Per ulteriori informazioni sulla creazione di sottoscrizioni di assistenza, vedere [Creare sottoscrizioni dell'assistenza da un gruppo di sottoscrizioni](create-service-subscriptions-from-subscription-group.md).</span><span class="sxs-lookup"><span data-stu-id="5c687-111">For more information about how to create service subscriptions, see [Create service subscriptions from a subscription group](create-service-subscriptions-from-subscription-group.md).</span></span>

## <a name="create-and-modify-subscription-transactions"></a><span data-ttu-id="5c687-112">Creare e modificare transazioni di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="5c687-112">Create and modify subscription transactions</span></span>

<span data-ttu-id="5c687-113">Dopo l'impostazione della sottoscrizione, si crea una transazione di commissione di sottoscrizione per il primo periodo di fatturazione, ovvero un anno.</span><span class="sxs-lookup"><span data-stu-id="5c687-113">After you set up the subscription, you create the subscription fee transaction for the first invoicing period, which is one year.</span></span> <span data-ttu-id="5c687-114">Le transazioni sono di tipo **Normale**.</span><span class="sxs-lookup"><span data-stu-id="5c687-114">The transactions are of the **Regular** type.</span></span> <span data-ttu-id="5c687-115">È pertanto unicamente possibile creare transazioni di sottoscrizione in cui la data iniziale e la data finale corrispondano a periodi creati in precedenza nel modulo **Tipi di periodo**.</span><span class="sxs-lookup"><span data-stu-id="5c687-115">Therefore, you can only create subscription transactions where the from date and the to date correspond to periods that were previously created in the **Period types** form.</span></span> <span data-ttu-id="5c687-116">Per ulteriori informazioni sulle transazioni di commissione, vedere [Creare transazioni di commissione di sottoscrizione](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="5c687-116">For more information about fee transactions, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="5c687-117">Dopo aver impostato la sottoscrizione per il cliente, si ricorda di aver concordato uno sconto del 10% su tutti i prezzi di listino relativi ai servizi.</span><span class="sxs-lookup"><span data-stu-id="5c687-117">After you set up the subscription for your customer, you remember that they have negotiated a 10 percent discount on all list prices for service offerings.</span></span> <span data-ttu-id="5c687-118">È pertanto necessario ridurre il prezzo della commissione appena creata.</span><span class="sxs-lookup"><span data-stu-id="5c687-118">Therefore, you must reduce the price of the transaction fee that you created.</span></span>

<span data-ttu-id="5c687-119">Più tardi si riceve una telefonata dal contatto del cliente in cui viene comunicato che il cliente desidera ancora il contratto di assistenza per la manutenzione delle linee elettriche, ma ha pianificato l'introduzione di una nuova linea elettrica nel corso dell'anno.</span><span class="sxs-lookup"><span data-stu-id="5c687-119">Later in the day, your customer contact calls to say that, although they still want the service agreement for the lighting rig, they plan to introduce a new lighting rig later in the year.</span></span> <span data-ttu-id="5c687-120">La copertura del contratto di assistenza è quindi necessaria solo fino a ottobre 2013.</span><span class="sxs-lookup"><span data-stu-id="5c687-120">Therefore, they only need maintenance coverage until October 2013.</span></span> <span data-ttu-id="5c687-121">Per ridurre il numero di mesi della sottoscrizione del cliente, creare una nuova transazione di commissione di sottoscrizione di tipo **Giorni riduzione**.</span><span class="sxs-lookup"><span data-stu-id="5c687-121">To reduce the number of months for the customer’s subscription, you create a new subscription fee transaction of the **Reduction days** type.</span></span> <span data-ttu-id="5c687-122">Per ulteriori informazioni sulla riduzione dei giorni, vedere [Ridurre i giorni delle commissioni di sottoscrizione](reduce-the-days-on-subscription-fees.md).</span><span class="sxs-lookup"><span data-stu-id="5c687-122">For more information about how to reduce days, see [Reduce the days on subscription fees](reduce-the-days-on-subscription-fees.md).</span></span>

## <a name="invoice-and-accrue-subscription-transactions"></a><span data-ttu-id="5c687-123">Fatturare e accumulare le transazioni di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="5c687-123">Invoice and accrue subscription transactions</span></span>

<span data-ttu-id="5c687-124">L'impostazione della sottoscrizione è completata ed è possibile fatturare la sottoscrizione al cliente.</span><span class="sxs-lookup"><span data-stu-id="5c687-124">You have now finished setting up the subscription, and you are ready to invoice your customer for it.</span></span> <span data-ttu-id="5c687-125">Per ulteriori informazioni sulla fatturazione delle sottoscrizioni, vedere [Fatturare transazioni di sottoscrizione](invoice-subscription-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="5c687-125">For more information about how to invoice subscriptions, see [Invoice subscription transactions](invoice-subscription-transactions.md).</span></span>

<span data-ttu-id="5c687-126">Due giorni dopo, il cliente richiede la fatturazione in dollari statunitensi, anziché in euro.</span><span class="sxs-lookup"><span data-stu-id="5c687-126">Two days later, your customer calls to say that the subscription should be invoiced in U.S. dollars, not Euros.</span></span> <span data-ttu-id="5c687-127">È pertanto necessario creare una nota di accredito e una nuova transazione di sottoscrizione nella valuta corretta.</span><span class="sxs-lookup"><span data-stu-id="5c687-127">Therefore, you create a credit note, and you also create a new subscription transaction in the correct currency.</span></span> <span data-ttu-id="5c687-128">Per ulteriori informazioni sull'accredito di transazioni di sottoscrizione, vedere [Accreditare transazioni di sottoscrizione](credit-subscription-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="5c687-128">For more information about how to credit subscription transactions, see [Credit subscription transactions](credit-subscription-transactions.md).</span></span>

<span data-ttu-id="5c687-129">Alla fine di ogni mese, è possibile accumulare i ricavi mensili provenienti dalla sottoscrizione del cliente nel conto profitti e perdite e nei conti WIP.</span><span class="sxs-lookup"><span data-stu-id="5c687-129">At the end of each month, one month's revenue can be accrued from the customer's subscription to the profit and loss account and the WIP accounts.</span></span> <span data-ttu-id="5c687-130">Per ulteriori informazioni sull'accumulo di ricavi per le sottoscrizioni, vedere [Accumulare ricavi sottoscrizioni](accrue-subscription-revenue.md).</span><span class="sxs-lookup"><span data-stu-id="5c687-130">For more information about how to accrue revenue for subscriptions, see [Accrue subscription revenue](accrue-subscription-revenue.md).</span></span>

  



