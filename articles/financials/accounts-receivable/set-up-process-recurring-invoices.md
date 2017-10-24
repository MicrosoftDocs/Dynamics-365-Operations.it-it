---
title: Impostare ed elaborare fatture ricorrenti
description: "Questo articolo illustra come impostare ed elaborare le fatture ricorrenti. È possibile utilizzare le fatture ricorrenti se è necessario fatturare ai clienti lo stesso importo su base regolare."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5f095b74df8b680f6e7e54520f9684298ec51aad
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-and-process-recurring-invoices"></a><span data-ttu-id="7b28e-104">Impostare ed elaborare fatture ricorrenti</span><span class="sxs-lookup"><span data-stu-id="7b28e-104">Set up and process recurring invoices</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7b28e-105">Questo articolo illustra come impostare ed elaborare le fatture ricorrenti.</span><span class="sxs-lookup"><span data-stu-id="7b28e-105">This article explains how to set up and process recurring invoices.</span></span> <span data-ttu-id="7b28e-106">È possibile utilizzare le fatture ricorrenti se è necessario fatturare ai clienti lo stesso importo su base regolare.</span><span class="sxs-lookup"><span data-stu-id="7b28e-106">You can use recurring invoices if you must invoice customers for the same amount on a regular basis.</span></span>

<a name="create-a-recurring-free-text-invoice-template"></a><span data-ttu-id="7b28e-107">Creare un modello di fattura ricorrente a testo libero</span><span class="sxs-lookup"><span data-stu-id="7b28e-107">Create a recurring free text invoice template</span></span>
---------------------------------------------

<span data-ttu-id="7b28e-108">Per fatturare a carico di clienti per gli stessi servizi a intervalli regolari, è necessario definire un modello di fattura a testo libero che può essere riutilizzato per creare le fatture.</span><span class="sxs-lookup"><span data-stu-id="7b28e-108">To invoice customers for the same services on a regular basis, you must define a free text invoice template that can be reused to create the invoices.</span></span> <span data-ttu-id="7b28e-109">In questo modello sono incluse le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="7b28e-109">This template contains the following information:</span></span>

-   <span data-ttu-id="7b28e-110">Informazioni di intestazione, ad esempio gruppi di imposte, termini e metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="7b28e-110">Header information, such as tax groups, terms of payment, and the method of payment</span></span>
-   <span data-ttu-id="7b28e-111">Informazioni sulle righe, ad esempio la descrizione del servizio, i conti ricavi, il prezzo unitario e l'importo della fattura</span><span class="sxs-lookup"><span data-stu-id="7b28e-111">Line information, such as the service description, revenue accounts, unit price, and invoice amount</span></span>
-   <span data-ttu-id="7b28e-112">Spese per spedizione o gestione</span><span class="sxs-lookup"><span data-stu-id="7b28e-112">Charges for shipping or handling</span></span>
-   <span data-ttu-id="7b28e-113">Distribuzioni contabili insieme alle informazioni sulle dimensioni finanziarie, ad esempio i centri di costo e Business Unit</span><span class="sxs-lookup"><span data-stu-id="7b28e-113">Accounting distributions together with financial dimension information, such as cost centers and business units</span></span>

<span data-ttu-id="7b28e-114">In pratica, si crea una fattura completa e la si salva come modello.</span><span class="sxs-lookup"><span data-stu-id="7b28e-114">In effect, you're creating an entire invoice and saving it as a template.</span></span> <span data-ttu-id="7b28e-115">È possibile impostare i modelli utilizzando la pagina **Fatture ricorrenti**.</span><span class="sxs-lookup"><span data-stu-id="7b28e-115">You can set up the templates using the **Recurring invoices** page.</span></span>

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a><span data-ttu-id="7b28e-116">Assegnare un modello di fattura a testo libero a un cliente e immettere i dettagli di ricorrenza</span><span class="sxs-lookup"><span data-stu-id="7b28e-116">Assign a free text invoice template to a customer and enter recurrence details</span></span>
<span data-ttu-id="7b28e-117">Una volta creato il modello, è necessario assegnarlo ai clienti per i quali si desidera emettere la fattura.</span><span class="sxs-lookup"><span data-stu-id="7b28e-117">After the template is created, you must assign the template to the customers that you want to invoice.</span></span> <span data-ttu-id="7b28e-118">Inoltre, è necessario specificare quando e con quale frequenza verrà utilizzata la fattura.</span><span class="sxs-lookup"><span data-stu-id="7b28e-118">Additionally, you must specify when and how often the invoice will be used.</span></span> <span data-ttu-id="7b28e-119">È possibile assegnare i modelli sulla scheda **Fattura** della pagina **Clienti**.</span><span class="sxs-lookup"><span data-stu-id="7b28e-119">You can assign the templates on the **Invoice** tab of the **Customers** page.</span></span> <span data-ttu-id="7b28e-120">Aggiungere il modello all'elenco e aggiornare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b28e-120">Add the template to the list, and update the following information:</span></span>

-   <span data-ttu-id="7b28e-121">La data di inizio e, facoltativamente, la data di fine per la fatturazione ricorrente</span><span class="sxs-lookup"><span data-stu-id="7b28e-121">The start date and, optionally, the end date for the recurring billing</span></span>
-   <span data-ttu-id="7b28e-122">La frequenza della fatturazione ricorrente (ad esempio ogni giorno o una volta al mese)</span><span class="sxs-lookup"><span data-stu-id="7b28e-122">The frequency of the recurring billing (for example, every day or once a month)</span></span>
-   <span data-ttu-id="7b28e-123">L'importo massimo di fatturazione (se queste informazioni sono necessarie)</span><span class="sxs-lookup"><span data-stu-id="7b28e-123">The maximum billing amount (if this information is required)</span></span>

<span data-ttu-id="7b28e-124">Un cliente può avere più modelli con frequenze diverse.</span><span class="sxs-lookup"><span data-stu-id="7b28e-124">A customer can have multiple templates that have different frequencies.</span></span>

## <a name="generate-the-recurring-invoices"></a><span data-ttu-id="7b28e-125">Generare le fatture ricorrenti</span><span class="sxs-lookup"><span data-stu-id="7b28e-125">Generate the recurring invoices</span></span>
<span data-ttu-id="7b28e-126">Nella pagina **Fatture ricorrenti**è presente un'attività che elabora modelli di fattura ricorrente.</span><span class="sxs-lookup"><span data-stu-id="7b28e-126">On the **Recurring invoices** page, there is a task that processes recurring invoice templates.</span></span> <span data-ttu-id="7b28e-127">Specificare la data della fattura e il modello da cui generare le fatture.</span><span class="sxs-lookup"><span data-stu-id="7b28e-127">You specify the invoice date and the template to generate the invoices from.</span></span> <span data-ttu-id="7b28e-128">Le fatture verranno generate e verrà assegnato un singolo numero ID ricorrenza per ciascun gruppo di fatture elaborato.</span><span class="sxs-lookup"><span data-stu-id="7b28e-128">Invoices will be generated and assigned a single recurrence ID number for each group of invoices that is processed.</span></span>
<span data-ttu-id="7b28e-129">Registrare fatture a testo libero ricorrenti</span><span class="sxs-lookup"><span data-stu-id="7b28e-129">Post recurring free text invoices</span></span>
---------------------------------

<span data-ttu-id="7b28e-130">Dopo la generazione delle fatture ricorrenti, gli ID ricorrenza delle fatture vengono visualizzati in un'attività di registrazione nella pagina **Fatture ricorrenti**.</span><span class="sxs-lookup"><span data-stu-id="7b28e-130">After recurring invoices are generated, the invoice recurrence IDs appear in a posting task on the **Recurring invoices** page.</span></span> <span data-ttu-id="7b28e-131">È possibile visualizzare tutte le fatture per un ID ricorrenza facendo clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="7b28e-131">You can view all of the invoices for a recurrence ID by clicking the link.</span></span> <span data-ttu-id="7b28e-132">Durante la revisione delle fatture per ID ricorrenza, è possibile eliminare singole fatture.</span><span class="sxs-lookup"><span data-stu-id="7b28e-132">During your review of the invoices for the recurrence ID, you can delete individual invoices.</span></span> <span data-ttu-id="7b28e-133">Le impostazioni di ricorrenza del cliente saranno reimpostate per il modello, in modo da poterlo rigenerare successivamente.</span><span class="sxs-lookup"><span data-stu-id="7b28e-133">The customer's recurrence settings will be reset for that template, so that it can be regenerated later.</span></span> <span data-ttu-id="7b28e-134">È possibile registrare una, molte o tutte le fatture per un ID ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="7b28e-134">You can post one, many, or all of the invoices for a recurrence ID.</span></span> <span data-ttu-id="7b28e-135">Se i flussi di lavoro sono attivati, è necessario fare clic su **Invia** per poter registrare le fatture.</span><span class="sxs-lookup"><span data-stu-id="7b28e-135">If workflows are enabled, you must click **Submit** before you can post the invoices.</span></span>
<span data-ttu-id="7b28e-136">Stampare fatture a testo libero ricorrenti</span><span class="sxs-lookup"><span data-stu-id="7b28e-136">Print recurring free text invoices</span></span>
----------------------------------

<span data-ttu-id="7b28e-137">Dopo la registrazione delle fatture ricorrenti, è possibile stampare le fatture dalla pagina elenco delle fatture a testo libero.</span><span class="sxs-lookup"><span data-stu-id="7b28e-137">After recurring invoices are posted, you can print the invoices from the free text invoice list page.</span></span> <span data-ttu-id="7b28e-138">È possibile stampare le fatture selezionate oppure selezionare un intervallo di fatture da stampare.</span><span class="sxs-lookup"><span data-stu-id="7b28e-138">You can print the invoices that are selected, or you can select a range of invoices to print.</span></span>




