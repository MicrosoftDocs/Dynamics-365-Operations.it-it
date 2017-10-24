---
title: Impostare il mandato di addebito diretto SEPA.
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8b50c2d585c7e0bcd8dc15aa70446cd7346ad33c
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-sepa-direct-debit-mandate"></a><span data-ttu-id="e4ff8-102">Impostare il mandato di addebito diretto SEPA.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-102">Set up SEPA direct debit mandate</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="e4ff8-103">Un addebito diretto SEPA (Single Euro Payment Area) consente al creditore di prelevare denaro dal conto corrente bancario del cliente, purché il cliente abbia concesso un mandato firmato al creditore.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-103">A Single Euro Payment Area (SEPA) direct debit lets a creditor collect funds from a customer's bank account, provided that the customer has granted a signed mandate to the creditor.</span></span> <span data-ttu-id="e4ff8-104">Il mandato firmato dal cliente autorizza il creditore a riscuotere un pagamento e istruisce la banca del cliente a effettuare il pagamento.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-104">The mandate that the customer signs authorizes the creditor to collect a payment and instructs the customer's bank to pay the collection.</span></span> <span data-ttu-id="e4ff8-105">Questo argomento è organizzato per visualizzare il processo per l'impostazione dei mandati di addebito diretto SEPA.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-105">This topic is organized to show the process for setting up SEPA direct debit mandates.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e4ff8-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e4ff8-106">Prerequisites</span></span>
<span data-ttu-id="e4ff8-107">Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="e4ff8-108">Categoria</span><span class="sxs-lookup"><span data-stu-id="e4ff8-108">Category</span></span>       | <span data-ttu-id="e4ff8-109">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="e4ff8-109">Prerequisite</span></span>                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e4ff8-110">Paese</span><span class="sxs-lookup"><span data-stu-id="e4ff8-110">Country/region</span></span> | <span data-ttu-id="e4ff8-111">L'indirizzo principale della persona giuridica deve essere nei seguenti paesi: Austria, Belgio, Germania, Spagna, Francia, Italia o i Paesi Bassi.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-111">The primary address for the legal entity must be in the following countries/regions: Austria, Belgium, Germany, Spain, France, Italy, or the Netherlands.</span></span> |

1. <span data-ttu-id="e4ff8-112">Impostare una sequenza numerica per i mandati di addebito diretto. Ogni mandato deve avere un numero univoco.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-112">Set up a number sequence for direct debit mandates Each direct debit mandate must have a unique number.</span></span> <span data-ttu-id="e4ff8-113">Utilizzare la pagina **Sequenze numeriche** per creare una sequenza numerica per i mandati di addebito diretto.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-113">Use the **Number sequences** page to create a number sequence for direct debit mandates.</span></span> <span data-ttu-id="e4ff8-114">Questo identificatore servirà ad assegnare la sequenza numerica al sistema di mandato di addebito diretto nella pagina **Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-114">You will use this identifier to assign the number sequence to the direct debit mandate system on the **Accounts receivable parameters** page.</span></span>

2. <span data-ttu-id="e4ff8-115">Impostare i parametri di contabilità clienti per i mandati di addebito dirett. Utilizzare la pagina **Parametri contabilità clienti** per impostare i parametri per i mandati di addebito diretto.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-115">Set up Accounts receivable parameters for direct debit mandates Use the **Accounts receivable parameters** page to set up parameters for direct debit mandates.</span></span> <span data-ttu-id="e4ff8-116">Per impostare i parametri, nella scheda **Addebito diretto** , modificare i parametri predefiniti come necessario.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-116">To set up the parameters, on the **Direct debit** tab, change the default parameters as you require.</span></span> <span data-ttu-id="e4ff8-117">Quindi, nella scheda **Sequenze numeriche**, aggiornare il campo **ID mandato di addebito diretto** con la sequenza numerica impostata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-117">Then, on the **Number sequences** tab, update the **Direct debit mandate ID** field with the number sequence that you set up earlier.</span></span>

3. <span data-ttu-id="e4ff8-118">Impostare un metodo di pagamento per i mandati di addebito diretto. È necessario impostare un metodo di pagamento per i mandati di addebito diretto.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-118">Set up a method of payment for direct debit mandates You must set up a method of payment for direct debit mandates.</span></span> <span data-ttu-id="e4ff8-119">Si utilizza questo metodo di pagamento per eseguire query sulle fatture per le quali generare i pagamenti in addebito diretto.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-119">You use this method of payment to query for invoices to generate direct debit payments for.</span></span> <span data-ttu-id="e4ff8-120">Utilizzare la pagina **Metodi di pagamento** per impostare il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-120">Use the **Methods of payment** page to set up the method of payment.</span></span> <span data-ttu-id="e4ff8-121">Per impostare un metodo di pagamento per i mandati di addebito diretto, è necessario completare questi passaggi aggiuntivi per un metodo di pagamento:</span><span class="sxs-lookup"><span data-stu-id="e4ff8-121">To set up a method of payment for direct debit mandates, you must follow these additional steps for a method of payment:</span></span>

-   <span data-ttu-id="e4ff8-122">Nel campo **Tipo di pagamento** selezionare **Pagamento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-122">In the **Payment type** field, select **Electronic payment**.</span></span>
-   <span data-ttu-id="e4ff8-123">Facoltativo: se si prevede che ogni cliente avrà più mandati, nel campo  **Periodo** selezionare **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-123">Optional: If you expect each of your customers to have multiple mandates, in the **Period** field, select **Invoice**.</span></span> <span data-ttu-id="e4ff8-124">In questo modo viene creato un pagamento distinto per ogni fattura e ogni pagamento utilizza il mandato specificato per la fattura.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-124">A separate payment will be created for each invoice, and each payment will use the mandate that is specified for the invoice.</span></span>
-   <span data-ttu-id="e4ff8-125">Selezionare l'opzione **Richiedi mandato** per creare i pagamenti utilizzando i mandati di addebito diretto.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-125">Select the **Require mandate** option to create payments by using direct debit mandates.</span></span> <span data-ttu-id="e4ff8-126">L'opzione **Richiedi mandato** è disponibile solo se si seleziona **Pagamento elettronico** nel campo **Tipo di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="e4ff8-126">The **Require mandate** option is available only if you select **Electronic payment** in the **Payment type** field.</span></span>

<span data-ttu-id="e4ff8-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4ff8-127">See Also</span></span>

[<span data-ttu-id="e4ff8-128">Panoramica degli addebiti diretti SEPA</span><span class="sxs-lookup"><span data-stu-id="e4ff8-128">Direct debit overview</span></span>](sepa-direct-debit-overview.md) 

[<span data-ttu-id="e4ff8-129">Creare un nuovo mandato di addebito diretto per un cliente</span><span class="sxs-lookup"><span data-stu-id="e4ff8-129">Create a direct debit mandate for a customer</span></span>](tasks/create-direct-debit-mandate-customer.md) 


