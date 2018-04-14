---
title: Impostazione del mandato di addebito diretto SEPA
description: "Un addebito diretto SEPA (Single Euro Payment Area) consente al creditore di prelevare denaro dal conto corrente bancario del cliente, purché il cliente abbia concesso un mandato firmato al creditore."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 84e4a714b1233a0fb4ebb04757ba12a5d14d6f44
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="set-up-sepa-direct-debit-mandate"></a><span data-ttu-id="df6eb-103">Impostazione del mandato di addebito diretto SEPA</span><span class="sxs-lookup"><span data-stu-id="df6eb-103">Set up SEPA direct debit mandate</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="df6eb-104">Un addebito diretto SEPA (Single Euro Payment Area) consente al creditore di prelevare denaro dal conto corrente bancario del cliente, purché il cliente abbia concesso un mandato firmato al creditore.</span><span class="sxs-lookup"><span data-stu-id="df6eb-104">A Single Euro Payment Area (SEPA) direct debit lets a creditor collect funds from a customer's bank account, provided that the customer has granted a signed mandate to the creditor.</span></span> <span data-ttu-id="df6eb-105">Il mandato firmato dal cliente autorizza il creditore a riscuotere un pagamento e istruisce la banca del cliente a effettuare il pagamento.</span><span class="sxs-lookup"><span data-stu-id="df6eb-105">The mandate that the customer signs authorizes the creditor to collect a payment and instructs the customer's bank to pay the collection.</span></span> <span data-ttu-id="df6eb-106">Questo argomento è organizzato per visualizzare il processo per l'impostazione dei mandati di addebito diretto SEPA.</span><span class="sxs-lookup"><span data-stu-id="df6eb-106">This topic is organized to show the process for setting up SEPA direct debit mandates.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="df6eb-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="df6eb-107">Prerequisites</span></span>
<span data-ttu-id="df6eb-108">Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="df6eb-108">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="df6eb-109">Categoria</span><span class="sxs-lookup"><span data-stu-id="df6eb-109">Category</span></span>       | <span data-ttu-id="df6eb-110">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="df6eb-110">Prerequisite</span></span>                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="df6eb-111">Paese</span><span class="sxs-lookup"><span data-stu-id="df6eb-111">Country/region</span></span> | <span data-ttu-id="df6eb-112">L'indirizzo principale della persona giuridica deve essere nei seguenti paesi: Austria, Belgio, Germania, Spagna, Francia, Italia o i Paesi Bassi.</span><span class="sxs-lookup"><span data-stu-id="df6eb-112">The primary address for the legal entity must be in the following countries/regions: Austria, Belgium, Germany, Spain, France, Italy, or the Netherlands.</span></span> |

1. <span data-ttu-id="df6eb-113">Impostare una sequenza numerica per i mandati di addebito diretto. Ogni mandato deve avere un numero univoco.</span><span class="sxs-lookup"><span data-stu-id="df6eb-113">Set up a number sequence for direct debit mandates Each direct debit mandate must have a unique number.</span></span> <span data-ttu-id="df6eb-114">Utilizzare la pagina **Sequenze numeriche** per creare una sequenza numerica per i mandati di addebito diretto.</span><span class="sxs-lookup"><span data-stu-id="df6eb-114">Use the **Number sequences** page to create a number sequence for direct debit mandates.</span></span> <span data-ttu-id="df6eb-115">Questo identificatore servirà ad assegnare la sequenza numerica al sistema di mandato di addebito diretto nella pagina **Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="df6eb-115">You will use this identifier to assign the number sequence to the direct debit mandate system on the **Accounts receivable parameters** page.</span></span>

2. <span data-ttu-id="df6eb-116">Impostare i parametri di contabilità clienti per i mandati di addebito dirett. Utilizzare la pagina **Parametri contabilità clienti** per impostare i parametri per i mandati di addebito diretto.</span><span class="sxs-lookup"><span data-stu-id="df6eb-116">Set up Accounts receivable parameters for direct debit mandates Use the **Accounts receivable parameters** page to set up parameters for direct debit mandates.</span></span> <span data-ttu-id="df6eb-117">Per impostare i parametri, nella scheda **Addebito diretto** , modificare i parametri predefiniti come necessario.</span><span class="sxs-lookup"><span data-stu-id="df6eb-117">To set up the parameters, on the **Direct debit** tab, change the default parameters as you require.</span></span> <span data-ttu-id="df6eb-118">Quindi, nella scheda **Sequenze numeriche**, aggiornare il campo **ID mandato di addebito diretto** con la sequenza numerica impostata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="df6eb-118">Then, on the **Number sequences** tab, update the **Direct debit mandate ID** field with the number sequence that you set up earlier.</span></span>

3. <span data-ttu-id="df6eb-119">Impostare un metodo di pagamento per i mandati di addebito diretto. È necessario impostare un metodo di pagamento per i mandati di addebito diretto.</span><span class="sxs-lookup"><span data-stu-id="df6eb-119">Set up a method of payment for direct debit mandates You must set up a method of payment for direct debit mandates.</span></span> <span data-ttu-id="df6eb-120">Si utilizza questo metodo di pagamento per eseguire query sulle fatture per le quali generare i pagamenti in addebito diretto.</span><span class="sxs-lookup"><span data-stu-id="df6eb-120">You use this method of payment to query for invoices to generate direct debit payments for.</span></span> <span data-ttu-id="df6eb-121">Utilizzare la pagina **Metodi di pagamento** per impostare il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="df6eb-121">Use the **Methods of payment** page to set up the method of payment.</span></span> <span data-ttu-id="df6eb-122">Per impostare un metodo di pagamento per i mandati di addebito diretto, è necessario completare questi passaggi aggiuntivi per un metodo di pagamento:</span><span class="sxs-lookup"><span data-stu-id="df6eb-122">To set up a method of payment for direct debit mandates, you must follow these additional steps for a method of payment:</span></span>

-   <span data-ttu-id="df6eb-123">Nel campo **Tipo di pagamento** selezionare **Pagamento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="df6eb-123">In the **Payment type** field, select **Electronic payment**.</span></span>
-   <span data-ttu-id="df6eb-124">Facoltativo: se si prevede che ogni cliente avrà più mandati, nel campo  **Periodo** selezionare **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="df6eb-124">Optional: If you expect each of your customers to have multiple mandates, in the **Period** field, select **Invoice**.</span></span> <span data-ttu-id="df6eb-125">In questo modo viene creato un pagamento distinto per ogni fattura e ogni pagamento utilizza il mandato specificato per la fattura.</span><span class="sxs-lookup"><span data-stu-id="df6eb-125">A separate payment will be created for each invoice, and each payment will use the mandate that is specified for the invoice.</span></span>
-   <span data-ttu-id="df6eb-126">Selezionare l'opzione **Richiedi mandato** per creare i pagamenti utilizzando i mandati di addebito diretto.</span><span class="sxs-lookup"><span data-stu-id="df6eb-126">Select the **Require mandate** option to create payments by using direct debit mandates.</span></span> <span data-ttu-id="df6eb-127">L'opzione **Richiedi mandato** è disponibile solo se si seleziona **Pagamento elettronico** nel campo **Tipo di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="df6eb-127">The **Require mandate** option is available only if you select **Electronic payment** in the **Payment type** field.</span></span>

<span data-ttu-id="df6eb-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df6eb-128">See Also</span></span>

[<span data-ttu-id="df6eb-129">Panoramica degli addebiti diretti SEPA</span><span class="sxs-lookup"><span data-stu-id="df6eb-129">Direct debit overview</span></span>](sepa-direct-debit-overview.md) 

[<span data-ttu-id="df6eb-130">Creare un nuovo mandato di addebito diretto per un cliente</span><span class="sxs-lookup"><span data-stu-id="df6eb-130">Create a direct debit mandate for a customer</span></span>](tasks/create-direct-debit-mandate-customer.md) 


