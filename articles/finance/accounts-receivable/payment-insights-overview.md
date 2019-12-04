---
title: Informazioni dettagliate pagamenti cliente (anteprima)
description: Questo argomento descrive la capacità di informazioni dettagliate pagamenti che aiuta a migliorare la comprensione delle pratiche di pagamento tipiche dei singoli clienti e può identificare circostanze che giustificano l'avvio di processi di raccolta prima di quanto altrimenti fatto.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: f9f1e4ae4270380c88069723e768fd44ecf8c113
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773986"
---
# <a name="customer-payment-insights-preview"></a><span data-ttu-id="0022d-103">Informazioni dettagliate pagamenti cliente (anteprima)</span><span class="sxs-lookup"><span data-stu-id="0022d-103">Customer payment insights (Preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="0022d-104">Questo argomento descrive la capacità di informazioni dettagliate pagamenti che aiuta a migliorare la comprensione delle pratiche di pagamento tipiche dei singoli clienti e può identificare circostanze che giustificano l'avvio di processi di raccolta prima di quanto potrebbe essere altrimenti fatto.</span><span class="sxs-lookup"><span data-stu-id="0022d-104">This topic describes the payment insights capability that helps improve understanding of individual customers' typical payment practices and that can identify circumstances that justify initiating collection processes earlier than you might have done otherwise.</span></span> 

## <a name="overview"></a><span data-ttu-id="0022d-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="0022d-105">Overview</span></span>

<span data-ttu-id="0022d-106">Le organizzazioni scoprono spesso che è difficile prevedere quando i clienti pagano le fatture.</span><span class="sxs-lookup"><span data-stu-id="0022d-106">Organizations often find it challenging to predict when customers will pay their invoices.</span></span> <span data-ttu-id="0022d-107">Questa mancanza di informazione porta a previsioni del flusso di cassa meno accurate, processi di raccolta che iniziano troppo tardi e ordini che vengono rilasciati a clienti che potrebbero non ricevere il pagamento.</span><span class="sxs-lookup"><span data-stu-id="0022d-107">This lack of insight leads to less accurate cash flow forecasts, collections processes that start too late, and orders that are released to customers who may default on their payment.</span></span> <span data-ttu-id="0022d-108">Le informazioni dettagliate pagamenti cliente (anteprima) consentono alle organizzazioni di prevedere quando verrà pagata una fattura cliente, aiutando l'organizzazione a creare strategie di raccolta che migliorano la probabilità di essere pagati in tempo.</span><span class="sxs-lookup"><span data-stu-id="0022d-108">Customer payment insights (Preview) helps organizations predict when a customer invoice will be paid, helping organization create collections strategies that improve the probability of being paid on time.</span></span> 

## <a name="predictions"></a><span data-ttu-id="0022d-109">Previsioni</span><span class="sxs-lookup"><span data-stu-id="0022d-109">Predictions</span></span>

<span data-ttu-id="0022d-110">Le previsioni di pagamento consentiranno alle organizzazioni di migliorare i propri processi aziendali aiutandole a identificare facilmente le fatture che possono essere pagate in ritardo e ad adottare misure adeguate che aumentano le loro possibilità di essere pagati in tempo.</span><span class="sxs-lookup"><span data-stu-id="0022d-110">Payment predictions will enable organizations to improve their business processes by helping them easily identify the invoices that are likely to be paid late, and to take appropriate measures that improve their chances of getting paid on time.</span></span>

<span data-ttu-id="0022d-111">Utilizzando un modello di Machine Learning che sfrutta fatture storiche, pagamenti e dati dei clienti, Informazioni dettagliate pagamenti cliente (anteprima) prevede in modo più accurato quando un cliente paga una fattura in sospeso.</span><span class="sxs-lookup"><span data-stu-id="0022d-111">Using a machine learning model, which leverages historical invoices, payments and customer data, Customer payment insights (Preview) more accurately predicts when a customer will pay an outstanding invoice.</span></span>

<span data-ttu-id="0022d-112">Per ciascuna la fattura aperta, l'analisi dei pagamenti del cliente (anteprima) stima tre probabilità di pagamento:</span><span class="sxs-lookup"><span data-stu-id="0022d-112">For each open invoice, Customer payment insights (Preview) predicts three payment probabilities:</span></span>

-   <span data-ttu-id="0022d-113">Probabilità di pagamento effettuato in tempo</span><span class="sxs-lookup"><span data-stu-id="0022d-113">Probability of payment being made on time</span></span> 
-   <span data-ttu-id="0022d-114">Probabilità di pagamento effettuato in ritardo</span><span class="sxs-lookup"><span data-stu-id="0022d-114">Probability of payment being made late</span></span>
-   <span data-ttu-id="0022d-115">Probabilità di pagamento effettuato molto in ritardo</span><span class="sxs-lookup"><span data-stu-id="0022d-115">Probability of payment being made very late</span></span>

<span data-ttu-id="0022d-116">Per consentire alle organizzazioni di comprendere l'importo totale del pagamento che possono aspettarsi da un cliente in uno dei tre bucket, In tempo, In ritardo e Molto in ritardo, Informazioni dettagliate pagamenti cliente (anteprima) fornisce anche una visione aggregata dei pagamenti previsti.</span><span class="sxs-lookup"><span data-stu-id="0022d-116">To help Organizations understand the total payment amount they can expect from a customer in one of the three buckets, On time, Late and Very late, Customer payment insights (Preview) also provides an aggregated view of expected payments.</span></span>

<span data-ttu-id="0022d-117">[![Visualizzazione aggregata delle previsioni di pagamento](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)</span><span class="sxs-lookup"><span data-stu-id="0022d-117">[![Aggregated view of payment predictions](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)</span></span>

<span data-ttu-id="0022d-118">Inoltre, ciascuna fattura è assegnata una probabilità di pagamento in tempo.</span><span class="sxs-lookup"><span data-stu-id="0022d-118">Also, each invoice is assigned a probability of payment on time.</span></span> <span data-ttu-id="0022d-119">Se la probabilità di pagamento in tempo è inferiore al 50%, le fatture vengono contrassegnate con un cerchio rosso per indicare che possono richiedere attenzione per la raccolta.</span><span class="sxs-lookup"><span data-stu-id="0022d-119">If the probability of payment on time is less than 50%, the invoices are tagged with a red circle to  indicate that these invoices may require collections attention.</span></span> 

<span data-ttu-id="0022d-120">[![Elenco delle probabilità di pagamenti](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)</span><span class="sxs-lookup"><span data-stu-id="0022d-120">[![List of payment probabilities](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)</span></span>

<span data-ttu-id="0022d-121">Informazioni dettagliate pagamenti cliente (anteprima) fornisce anche informazioni contestuali per spiegare la previsione, ad esempio i principali fattori che hanno influenzato le previsioni, lo stato attuale delle attività con il cliente e i dettagli sul comportamento di pagamento storico del cliente.</span><span class="sxs-lookup"><span data-stu-id="0022d-121">Customer Payment Insights (Preview) also provides contextual information to explain the prediction, such as the top factors that influenced the predictions, the current state of business with the customer, and details about the historical customer payment behavior.</span></span> <span data-ttu-id="0022d-122">In molte aziende, il processo di raccolta è stato un'attività reattiva; il processo di raccolta non inizia fino alla scadenza delle fatture.</span><span class="sxs-lookup"><span data-stu-id="0022d-122">In many businesses, the collections process has been a reactive activity; the collections process doesn’t start until invoices come due.</span></span> 

<span data-ttu-id="0022d-123">Con Informazioni dettagliate pagamenti cliente (anteprima), le organizzazioni possono essere più proattive sulle raccolte.</span><span class="sxs-lookup"><span data-stu-id="0022d-123">With Customer payment insights (Preview), organizations can be more proactive about collections.</span></span> <span data-ttu-id="0022d-124">Non devono più attendere che le transazioni scadano per avviare il processo di raccolta.</span><span class="sxs-lookup"><span data-stu-id="0022d-124">They no longer have to wait for the transactions to become due to start the collection process.</span></span> <span data-ttu-id="0022d-125">Al contrario, possono utilizzare la capacità di previsione del pagamento per determinare se le raccolte proattive miglioreranno la probabilità di essere pagati in tempo.</span><span class="sxs-lookup"><span data-stu-id="0022d-125">Instead, they can use the payment prediction capability to determine whether proactive collections will improve the probability of being paid on time.</span></span> <span data-ttu-id="0022d-126">La previsione di pagamento fornisce inoltre alle aziende le informazioni necessarie per giustificare l'avvio anticipato del processo di raccolta.</span><span class="sxs-lookup"><span data-stu-id="0022d-126">Payment prediction also gives businesses the information needed to justify starting the collection process early.</span></span>

## <a name="methodology"></a><span data-ttu-id="0022d-127">Metodologia</span><span class="sxs-lookup"><span data-stu-id="0022d-127">Methodology</span></span>

<span data-ttu-id="0022d-128">Lo sviluppo e la distribuzione di una soluzione AI è difficile.</span><span class="sxs-lookup"><span data-stu-id="0022d-128">Developing and deploying an AI solution is hard.</span></span> <span data-ttu-id="0022d-129">Richiede un team di data scientist, esperti in materia e ingegneri che lavorano per un lungo periodo di tempo per formulare, sviluppare, implementare e mantenere una soluzione AI utilizzabile.</span><span class="sxs-lookup"><span data-stu-id="0022d-129">It takes a team of data scientists, subject matter experts and engineers, working for an extended period of time to formulate, develop, deploy and maintain a usable AI solution.</span></span> <span data-ttu-id="0022d-130">Stiamo semplificando la distribuzione e l'utilizzo delle soluzioni AI in Finance.</span><span class="sxs-lookup"><span data-stu-id="0022d-130">We are making it easy to deploy and use AI solutions in Finance.</span></span> <span data-ttu-id="0022d-131">Stiamo preparando soluzioni AI in Finance basate su Microsoft AI Builder.</span><span class="sxs-lookup"><span data-stu-id="0022d-131">We are prepackaging AI solutions in Finance that are built on top of Microsoft AI Builder.</span></span> <span data-ttu-id="0022d-132">Un utente finale, con il semplice clic del pulsante, può implementare la soluzione AI e iniziare a utilizzare i vantaggi delle previsioni intelligenti.</span><span class="sxs-lookup"><span data-stu-id="0022d-132">An end user, with the single click of button, can deploy the AI solution and start leveraging the benefits of intelligent predictions.</span></span> <span data-ttu-id="0022d-133">Se un'organizzazione non è soddisfatta della precisione delle previsioni, un utente esperto, sempre utilizzando un solo clic, può accedere all'esperienza dell'estensione AI builder, quindi selezionare o deselezionare i campi utilizzati per generare previsioni.</span><span class="sxs-lookup"><span data-stu-id="0022d-133">If an organization isn't satisfied with the accuracy of predictions, a power user, again using a single click, can enter the AI builder extension experience, and then select or deselect the fields used to generate predictions.</span></span> <span data-ttu-id="0022d-134">Una volta pronti, possono addestrare e pubblicare le modifiche e il modello appena addestrato verrà automaticamente selezionato per le previsioni in Finance.</span><span class="sxs-lookup"><span data-stu-id="0022d-134">Once ready, they can train and publish the changes, and the newly trained model will be automatically picked up for predictions in Finance.</span></span>

## <a name="how-to-get-customer-payment-insights-preview"></a><span data-ttu-id="0022d-135">Come ottenere l'analisi dei pagamenti dei clienti (anteprima)</span><span class="sxs-lookup"><span data-stu-id="0022d-135">How to get Customer payment insights (Preview)</span></span>

<span data-ttu-id="0022d-136">Inviare un'e-mail a [Informazioni dettagliate pagamenti cliente (anteprima)](mailto:fiap@microsoft.com) se si è interessati a provare Informazioni dettagliate pagamenti cliente (anteprima).</span><span class="sxs-lookup"><span data-stu-id="0022d-136">Please send email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in trying the Customer payment insights (Preview).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="0022d-137">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="0022d-137">Privacy Notice</span></span>

<span data-ttu-id="0022d-138">Le anteprime (1) possono utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.</span><span class="sxs-lookup"><span data-stu-id="0022d-138">Previews (1) may utilize less privacy and security measures than the Dynamics 365 Finance and Operations service, (2) are not included in the service level agreement for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) has limited support.</span></span>


