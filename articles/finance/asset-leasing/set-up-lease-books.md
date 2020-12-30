---
title: Configurare i libri di leasing
description: In questo argomento vengono descritte le informazioni conservate nei libri di leasing. I libri di leasing contengono i criteri contabili che determinano la modalità di contabilizzazione di un leasing nel sistema.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 28518341544327f1983e563b719b0f455b6e1c43
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444982"
---
# <a name="set-up-lease-books"></a><span data-ttu-id="cdb26-104">Configurare i libri di leasing</span><span class="sxs-lookup"><span data-stu-id="cdb26-104">Set up lease books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cdb26-105">I libri di leasing contengono i criteri contabili che determinano la modalità di contabilizzazione di un leasing nel sistema.</span><span class="sxs-lookup"><span data-stu-id="cdb26-105">Lease books contain the accounting policies that determine how a lease is accounted for in the system.</span></span> <span data-ttu-id="cdb26-106">Oltre alla contabilità di cassa, Leasing cespite supporta i seguenti standard:</span><span class="sxs-lookup"><span data-stu-id="cdb26-106">In addition to cash basis accounting, Asset leasing supports the following standards:</span></span>

- <span data-ttu-id="cdb26-107">Principi contabili generalmente accettati negli Stati Uniti (US GAAP)</span><span class="sxs-lookup"><span data-stu-id="cdb26-107">Generally Accepted Accounting Principles in the United States (US GAAP)</span></span>
- <span data-ttu-id="cdb26-108">Accounting Standards Codification Topic 842 (ASC 842)</span><span class="sxs-lookup"><span data-stu-id="cdb26-108">Accounting Standards Codification Topic 842 (ASC 842)</span></span>
- <span data-ttu-id="cdb26-109">ASC 840</span><span class="sxs-lookup"><span data-stu-id="cdb26-109">ASC 840</span></span>
- <span data-ttu-id="cdb26-110">International Financial Reporting Standard 16 (IFRS 16)</span><span class="sxs-lookup"><span data-stu-id="cdb26-110">International Financial Reporting Standard 16 (IFRS 16)</span></span>
- <span data-ttu-id="cdb26-111">International Accounting Standard 17 (IAS 17)</span><span class="sxs-lookup"><span data-stu-id="cdb26-111">International Accounting Standard 17 (IAS 17)</span></span>

<span data-ttu-id="cdb26-112">Per creare un libro di leasing, procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="cdb26-112">To create a lease book, follow these steps.</span></span>

1. <span data-ttu-id="cdb26-113">Vai a **Leasing cespiti \> Imposta \> Libri di leasing**.</span><span class="sxs-lookup"><span data-stu-id="cdb26-113">Go to **Asset leasing \> Setup \> Lease books**.</span></span>
2. <span data-ttu-id="cdb26-114">Seleziona **Nuovo** per aggiungere un libro.</span><span class="sxs-lookup"><span data-stu-id="cdb26-114">Select **New** to add a book.</span></span>
3. <span data-ttu-id="cdb26-115">Impostare i seguenti campi.</span><span class="sxs-lookup"><span data-stu-id="cdb26-115">Set the following fields.</span></span>

    | <span data-ttu-id="cdb26-116">Nome</span><span class="sxs-lookup"><span data-stu-id="cdb26-116">Name</span></span>                                     | <span data-ttu-id="cdb26-117">descrizione</span><span class="sxs-lookup"><span data-stu-id="cdb26-117">Description</span></span> |
    |------------------------------------------|-------------|
    | <span data-ttu-id="cdb26-118">Livello di registrazione</span><span class="sxs-lookup"><span data-stu-id="cdb26-118">Posting layer</span></span>                            | <span data-ttu-id="cdb26-119">Seleziona il livello di registrazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="cdb26-119">Select the posting layer to use.</span></span> <span data-ttu-id="cdb26-120">Ogni libro allegato a un leasing è configurato per uno specifico livello di registrazione.</span><span class="sxs-lookup"><span data-stu-id="cdb26-120">Each book that is attached to a lease is set up for a specific posting layer.</span></span> <span data-ttu-id="cdb26-121">Ogni livello di registrazione ha scopi di registrazione diversi.</span><span class="sxs-lookup"><span data-stu-id="cdb26-121">Each posting layer has different posting purposes.</span></span> |
    | <span data-ttu-id="cdb26-122">Tipo di leasing</span><span class="sxs-lookup"><span data-stu-id="cdb26-122">Lease type</span></span>                               | <span data-ttu-id="cdb26-123">Seleziona se il leasing deve essere classificato automaticamente o se deve essere predefinito come leasing finanziario o operativo.</span><span class="sxs-lookup"><span data-stu-id="cdb26-123">Select whether the lease should be classified automatically, or whether it should be predefined as a finance or operating lease.</span></span> |
    | <span data-ttu-id="cdb26-124">Framework di contabilità</span><span class="sxs-lookup"><span data-stu-id="cdb26-124">Accounting framework</span></span>                     | <span data-ttu-id="cdb26-125">Seleziona il framework associato al libro.</span><span class="sxs-lookup"><span data-stu-id="cdb26-125">Select the framework that is associated with the book.</span></span> |
    | <span data-ttu-id="cdb26-126">Configurazione termine del leasing/vita utile</span><span class="sxs-lookup"><span data-stu-id="cdb26-126">Lease term/Useful life Set Up</span></span>          | <span data-ttu-id="cdb26-127">Il sistema classificherà il leasing come leasing finanziario se il tipo di leasing è impostato su **Automatico** e se il termine del leasing sulla vita utile del cespite è maggiore o uguale alla percentuale immessa in questo campo.</span><span class="sxs-lookup"><span data-stu-id="cdb26-127">The system will classify the lease as a finance lease if the lease type is set to **Automatic**, and if the lease term over useful life of the asset is greater than or equal to the percentage entered in this field.</span></span>  |
    | <span data-ttu-id="cdb26-128">Configurazione valore corrente/valore equo cespite</span><span class="sxs-lookup"><span data-stu-id="cdb26-128">Present value / Asset fair value setup</span></span>   | <span data-ttu-id="cdb26-129">Immetti un numero intero per definire la soglia che determinerà il tipo di leasing.</span><span class="sxs-lookup"><span data-stu-id="cdb26-129">Enter a whole number to define the threshold that will determine the lease type.</span></span> <span data-ttu-id="cdb26-130">Se il valore attuale dei canoni di leasing minimi futuri è superiore al valore definito dall'utente dalla configurazione del libro e se la classificazione del leasing del libro è impostata su automatica, il sistema classificherà il leasing come finanziario.</span><span class="sxs-lookup"><span data-stu-id="cdb26-130">If the present value of future minimum lease payments is more than the user-defined value from the book setup, and if the book's lease classification is set to automatic, the system will classify the lease as a finance lease.</span></span> |
    | <span data-ttu-id="cdb26-131">Soglia a breve termine</span><span class="sxs-lookup"><span data-stu-id="cdb26-131">Short-term threshold</span></span>                     | <span data-ttu-id="cdb26-132">Immetti il numero di mesi da utilizzare come soglia per i leasing a breve termine.</span><span class="sxs-lookup"><span data-stu-id="cdb26-132">Enter the number of months to use as a threshold for short-term leases.</span></span> <span data-ttu-id="cdb26-133">Se il termine del leasing è inferiore o uguale al numero di mesi che immetti qui, il sistema classificherà il leasing come un leasing a breve termine e verrà applicato il trattamento della passività sui contratti.</span><span class="sxs-lookup"><span data-stu-id="cdb26-133">If the lease term is less than or equal to the number of months that you enter here, the system will classify the lease as a short-term lease, and the deferred rent treatment will be applied.</span></span> |
    | <span data-ttu-id="cdb26-134">Soglia valore basso</span><span class="sxs-lookup"><span data-stu-id="cdb26-134">Low value threshold</span></span>                      | <span data-ttu-id="cdb26-135">Immetti un importo da utilizzare come soglia per i leasing a valore basso.</span><span class="sxs-lookup"><span data-stu-id="cdb26-135">Enter an amount to use as a threshold for low-value leases.</span></span> <span data-ttu-id="cdb26-136">Se il valore equo del cespite è inferiore o uguale al valore immesso qui, il sistema classificherà il leasing come un leasing a valore basso e verrà applicato il trattamento della passività sui contratti.</span><span class="sxs-lookup"><span data-stu-id="cdb26-136">If the fair value of the asset is less than or equal or the value that you enter here, the system will classify the lease as a low-value lease, and the deferred rent treatment will be applied.</span></span> |
    | <span data-ttu-id="cdb26-137">Paga il fornitore</span><span class="sxs-lookup"><span data-stu-id="cdb26-137">Pay to vendor</span></span>                            | <span data-ttu-id="cdb26-138">Imposta questa opzione su **Sì** per consentire la registrazione dei canoni di leasing, come fattura, nel conto fornitore specificato in ogni leasing.</span><span class="sxs-lookup"><span data-stu-id="cdb26-138">Set this option to **Yes** to allow lease payments to be posted, as an invoice, to the vendor account that is specified on each lease.</span></span> <span data-ttu-id="cdb26-139">Quando viene registrato un canone di leasing, verrà accreditato il conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="cdb26-139">When a lease payment is posted, the vendor account will be credited.</span></span> <span data-ttu-id="cdb26-140">Se questa opzione è impostata su **No**, il conto specificato per il tipo di registrazione **Canone di leasing** nella pagina **Parametri di registrazione del leasing** verrà invece accreditato.</span><span class="sxs-lookup"><span data-stu-id="cdb26-140">If this option is set to **No**, the account that is specified for the **Lease payment** posting type on the **Lease posting parameters** page will be credited instead.</span></span> |
