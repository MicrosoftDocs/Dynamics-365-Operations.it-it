---
title: Analisi dei pagamenti dei clienti (anteprima)
description: "Questo argomento descrive come le analisi dei pagamenti dei clienti possono aiutare a prevedere quando una fattura verrà pagata e aiutare le organizzazioni a creare strategie di ottimizzazione che migliorano le probabilità di pagamenti tempestivi."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: 
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-04-02
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: 841ea53f754f61c2930e77fdafc85eac72f47d7a
ms.openlocfilehash: 9e722db6302d7ef51c01601cde245d4f4a333eba
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---

# <a name="customer-payment-insights-preview"></a><span data-ttu-id="37e7b-103">Analisi dei pagamenti dei clienti (anteprima)</span><span class="sxs-lookup"><span data-stu-id="37e7b-103">Customer payment insights (preview)</span></span>

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="37e7b-104">Questa funzionalità fa parte di una versione di destinazione ed è disponibile soltanto per gli utenti che hanno scelto l'anteprima privata.</span><span class="sxs-lookup"><span data-stu-id="37e7b-104">This feature is part of a targeted release and is only available to users who have opted into the Private Preview.</span></span> <span data-ttu-id="37e7b-105">Questa funzionalità verrà inclusa in una prossima versione a disponibilità generale.</span><span class="sxs-lookup"><span data-stu-id="37e7b-105">This feature will be included in an upcoming general availability release.</span></span>

# <a name="overview"></a><span data-ttu-id="37e7b-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="37e7b-106">Overview</span></span>

<span data-ttu-id="37e7b-107">Le organizzazioni scoprono spesso che è difficile prevedere quando un cliente pagherà le fatture.</span><span class="sxs-lookup"><span data-stu-id="37e7b-107">Organizations often find it challenging to predict when a customer will pay their invoices.</span></span> <span data-ttu-id="37e7b-108">Questa mancanza di informazioni può condurre a previsioni di cassa non corrette, a processi inefficienti della raccolta e a possibilità di ordini che vengono emessi ai clienti che possono comportare un rischio di credito.</span><span class="sxs-lookup"><span data-stu-id="37e7b-108">This lack of insight can lead to inaccurate cash flow forecasts, inefficient collection processes, and the possibility of orders being released to customers who may pose a credit risk.</span></span> <span data-ttu-id="37e7b-109">L'analisi dei pagamenti del cliente (anteprima) utilizza Machine Learning per prevedere quando la fattura verrà pagata.</span><span class="sxs-lookup"><span data-stu-id="37e7b-109">Customer payment insights (preview) uses machine learning to predict when an invoice will be paid.</span></span> <span data-ttu-id="37e7b-110">Fornisce inoltre strategie di ottimizzazione che possono essere adattate di ottimizzare la probabilità che i clienti paghino con puntualità.</span><span class="sxs-lookup"><span data-stu-id="37e7b-110">It also provides optimization strategies that can be tailored to maximize the probability of customers paying on time.</span></span>

## <a name="predictions"></a><span data-ttu-id="37e7b-111">Previsioni</span><span class="sxs-lookup"><span data-stu-id="37e7b-111">Predictions</span></span>

<span data-ttu-id="37e7b-112">Le previsioni di pagamento consentono alle organizzazioni di migliorare i processi aziendali aiutando a:</span><span class="sxs-lookup"><span data-stu-id="37e7b-112">Payment predictions allow organizations to improve their business processes by helping to:</span></span>

-   <span data-ttu-id="37e7b-113">Identificare facilmente le fatture che si prevede che verranno pagate in ritardo.</span><span class="sxs-lookup"><span data-stu-id="37e7b-113">Easily identify the invoices that are predicted to be paid late.</span></span>
-   <span data-ttu-id="37e7b-114">Adottare le misurazioni appropriate per migliorare le possibilità di ottenere il pagamento puntualmente.</span><span class="sxs-lookup"><span data-stu-id="37e7b-114">Take appropriate measures to improve chances of getting paid on time.</span></span>

<span data-ttu-id="37e7b-115">L'analisi dei pagamenti del cliente (anteprima) utilizza Machine Learning per prevedere quando la fattura verrà pagata.</span><span class="sxs-lookup"><span data-stu-id="37e7b-115">Customer payment insights (preview) uses machine learning to predict when an invoice will be paid.</span></span> <span data-ttu-id="37e7b-116">Utilizza i dati storici di fatture, pagamenti e cliente per creare un modello di Machine Learning che venga usato per prevedere quando una fattura verrà pagata.</span><span class="sxs-lookup"><span data-stu-id="37e7b-116">It uses historical invoice, payment, and customer data to create a machine learning model that is used to predict when an invoice will be paid.</span></span>

<span data-ttu-id="37e7b-117">Per ciascuna la fattura aperta, l'analisi dei pagamenti del cliente (anteprima) stima tre probabilità di pagamento:</span><span class="sxs-lookup"><span data-stu-id="37e7b-117">For each open invoice, Customer payment insights (preview) predicts three payment probabilities:</span></span>

-  <span data-ttu-id="37e7b-118">Probabilità che il pagamento venga effettuato con puntualità (entro la data di scadenza della fattura).</span><span class="sxs-lookup"><span data-stu-id="37e7b-118">Probability of payment being made on time (within the invoice due date).</span></span>
-  <span data-ttu-id="37e7b-119">Probabilità che il pagamento venga effettuato entro 30 giorni dalla data di scadenza della fattura.</span><span class="sxs-lookup"><span data-stu-id="37e7b-119">Probability of payment being made within 30 days of the invoice due date.</span></span>
-  <span data-ttu-id="37e7b-120">Probabilità che il pagamento venga effettuato dopo 30 giorni dalla data di scadenza della fattura.</span><span class="sxs-lookup"><span data-stu-id="37e7b-120">Probability of payment being made beyond 30 days of the invoice due date.</span></span>

<span data-ttu-id="37e7b-121">Probabilità che i pagamenti vengano visualizzati nella sezione previsione.</span><span class="sxs-lookup"><span data-stu-id="37e7b-121">The probability of payments can be viewed in the prediction section.</span></span>

<span data-ttu-id="37e7b-122">[![Previsioni di pagamento](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)</span><span class="sxs-lookup"><span data-stu-id="37e7b-122">[![Payment predictions](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)</span></span>

<span data-ttu-id="37e7b-123">A ogni fattura viene inoltre assegnata una probabilità vincente di pagamento utilizzando uno dei tre scenari di probabilità di pagamento definite sopra.</span><span class="sxs-lookup"><span data-stu-id="37e7b-123">Each invoice is also assigned a winning probability of payment using one of the three predicted payment probabilities scenarios defined above.</span></span> <span data-ttu-id="37e7b-124">Lo scenario con la più alta probabilità di pagamento è lo scenario vincente.</span><span class="sxs-lookup"><span data-stu-id="37e7b-124">The scenario with the highest probability of payment is the winning scenario.</span></span>


<span data-ttu-id="37e7b-125">Ad esempio, supponiamo che per una fattura la previsione mostri una probabilità del 71% che la fattura venga pagata puntualmente, una probabilità del 13% che venga pagata entro 30 giorni dalla data di scadenza e una probabilità del 16% che venga pagata dopo 30 giorni dalla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="37e7b-125">For example, let’s assume for an invoice the prediction shows a 71 percent probability that the invoice will be paid on time, 13 percent probability that the invoice will be paid within 30 days of due date, and 16 percent probability that the invoice will be paid beyond 30 days of the due date.</span></span> <span data-ttu-id="37e7b-126">La probabilità più alta indica che la fattura rientrerà nello scenario di puntualità, pertanto la fattura verrà etichettata con la probabilità di essere pagata puntualmente.</span><span class="sxs-lookup"><span data-stu-id="37e7b-126">The highest probability shows that the invoice will be in the on-time scenario, so the invoice will be tagged with the probability of being paid on time.</span></span>

<span data-ttu-id="37e7b-127">[![Previsioni di pagamento](./media/payment-predict.png)](./media/payment-predict.png)</span><span class="sxs-lookup"><span data-stu-id="37e7b-127">[![Payment predictions](./media/payment-predict.png)](./media/payment-predict.png)</span></span>

## <a name="optimization-strategies"></a><span data-ttu-id="37e7b-128">Strategie di ottimizzazione</span><span class="sxs-lookup"><span data-stu-id="37e7b-128">Optimization strategies</span></span>

<span data-ttu-id="37e7b-129">Oltre alle previsioni di pagamento, l'analisi dei pagamenti del cliente (anteprima) può utilizzare le strategie di ottimizzazione per migliorare le possibilità di ottenere il pagamento puntuale.</span><span class="sxs-lookup"><span data-stu-id="37e7b-129">In addition to payment predictions, the Customer Payment Insights (preview) can use optimization strategies to improve the chances of getting paid on time.</span></span> <span data-ttu-id="37e7b-130">In questo modo le organizzazioni eseguono l'analisi "What if" consentendo agli utenti di regolare i parametri di fattura e di cliente e quindi di confrontare l'effetto corrispondente sulla probabilità di ricevere il pagamento delle fatture in tempo.</span><span class="sxs-lookup"><span data-stu-id="37e7b-130">This lets organizations do 'What if' analysis by allowing users to adjust invoice and customer parameters and then compare the corresponding effect on the probability of receiving payment on invoices on time.</span></span>

<span data-ttu-id="37e7b-131">Ad esempio, per un'organizzazione può essere opportuno valutare gli effetti di aggiornamento dello sconto di cassa nelle fatture sulla probabilità di ricevere il pagamento in tempo.</span><span class="sxs-lookup"><span data-stu-id="37e7b-131">For example, an organization may want to evaluate the effect of updating the cash discount on invoices on the probability of receiving the payment on time.</span></span> <span data-ttu-id="37e7b-132">Quando le fatture vengono ottimizzate per utilizzare il nuovo sconto, gli utenti possono esaminare gli effetti dell'applicazione dello sconto sulla probabilità di ricevere i pagamenti per le fatture in tempo.</span><span class="sxs-lookup"><span data-stu-id="37e7b-132">When the invoices are optimized to use the new discount, the users can review the effect of applying the discount on the probability of receiving payments for those invoices on time.</span></span> <span data-ttu-id="37e7b-133">Se il costo dell'applicazione dello sconto è minimo confrontato con il vantaggio di ricevere il pagamento in tempo, l'organizzazione può scegliere di applicare lo sconto selezionato a tutti i futuri ordini aperti.</span><span class="sxs-lookup"><span data-stu-id="37e7b-133">If the cost of applying the discount is minimal when compared to the benefit of collecting the payment on time, the organization may choose to apply the selected discount to all future open orders.</span></span>

> [!NOTE] 
> <span data-ttu-id="37e7b-134">Attualmente, solo lo sconto è disponibile come strategia di ottimizzazione per l'analisi dei pagamenti del cliente (anteprima).</span><span class="sxs-lookup"><span data-stu-id="37e7b-134">Currently, only discount is available as an optimization strategy for Customer payment insights (preview).</span></span>

<span data-ttu-id="37e7b-135">[![Previsioni ottimizzate](./media/optimized-pay.png)](./media/optimized-pay.png)</span><span class="sxs-lookup"><span data-stu-id="37e7b-135">[![Optimized predictions](./media/optimized-pay.png)](./media/optimized-pay.png)</span></span>

## <a name="how-to-get-customer-payment-insights-preview"></a><span data-ttu-id="37e7b-136">Come ottenere l'analisi dei pagamenti dei clienti (anteprima)</span><span class="sxs-lookup"><span data-stu-id="37e7b-136">How to get Customer payment insights (preview)</span></span>

<span data-ttu-id="37e7b-137">Se si desidera provare l'analisi dei pagamenti del cliente (anteprima), inviare un'e-mail al [team dell'anteprima di analisi finanziaria](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="37e7b-137">If you are interested in trying Customer payment insights (preview), please email [Finance Insights Preview team](mailto:fiap@microsoft.com).</span></span> 

## <a name="privacy-statement"></a><span data-ttu-id="37e7b-138">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="37e7b-138">Privacy Statement</span></span>

<span data-ttu-id="37e7b-139">Le anteprime archiviano i dati dei clienti negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="37e7b-139">Previews store customer data in the United States.</span></span> <span data-ttu-id="37e7b-140">Inoltre, le anteprime (1) possono utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 for Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.</span><span class="sxs-lookup"><span data-stu-id="37e7b-140">In addition, previews (1) may utilize less privacy and security measures than the Dynamics 365 for Finance and Operations service, (2) are not included in the service level agreement for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) has limited support.</span></span>

