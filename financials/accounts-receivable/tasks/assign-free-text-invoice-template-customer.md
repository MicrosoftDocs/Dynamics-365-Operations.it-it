--- 
title: Assegnare al cliente un modello di fattura a testo libero
description: "Questa attività descrive come assegnare un modello di fattura a testo libero a un cliente."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 3bcb59c6edd04877dc2a052002be513205ae840a
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a><span data-ttu-id="0cbe6-103">Assegnare al cliente un modello di fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="0cbe6-103">Assign a free text invoice template to a customer</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0cbe6-104">Questa attività descrive come assegnare un modello di fattura a testo libero a un cliente.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-104">This task demonstrates how to assign a free text invoice template to a customer.</span></span> <span data-ttu-id="0cbe6-105">In questa attività viene utilizzata la società dimostrativa USMF ed è destinata all'utente responsabile della gestione e dell'elaborazione delle fatture di CoCli.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-105">This task uses the USMF demo company and is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="0cbe6-106">Andare a Contabilità clienti > Clienti > Tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-106">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="0cbe6-107">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="0cbe6-108">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-108">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="0cbe6-109">Fare clic su Fatture ricorrenti.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-109">Click Recurring invoices.</span></span>
    * <span data-ttu-id="0cbe6-110">Utilizzare questa pagina per assegnare ai clienti modelli di fattura a testo libero e specificare con quale frequenza le fatture verranno inviate al cliente.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-110">Use this page to assign free text invoice templates to customers and specify how frequently invoices will be sent to the customer.</span></span>  
5. <span data-ttu-id="0cbe6-111">Fare clic su Nuovo per assegnare un nuovo modello al cliente.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-111">Click New to assign a new template to the customer.</span></span>
6. <span data-ttu-id="0cbe6-112">Selezionare il modello di fattura a testo libero da assegnare al cliente.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-112">Select the free text invoice template you want to assign to the customer.</span></span>
7. <span data-ttu-id="0cbe6-113">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-113">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="0cbe6-114">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="0cbe6-115">Immettere la data in cui verrà generata la prima fattura.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-115">Enter the date when the first invoice will be generated.</span></span>
    * <span data-ttu-id="0cbe6-116">Immettere una data di fine ricorrente.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-116">Enter a recurring end date.</span></span>  
    * <span data-ttu-id="0cbe6-117">Selezionare una delle opzioni seguenti. Nessuna data di fine: le fatture verranno generate indefinitamente finché il modello non verrà rimosso dal conto cliente.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-117">Select one of the following: No end date – Invoices will be generated indefinitely until the template is removed from the customer account.</span></span>  <span data-ttu-id="0cbe6-118">Data di fine fatturazione: selezionare questa opzione e immettere l'ultima data in cui la fattura può essere generata.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-118">Billing end date – Select this option and enter the last date that the invoice can be generated.</span></span>  
    * <span data-ttu-id="0cbe6-119">Importo cumulativo massimo dopo il quale la generazione della fattura verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-119">Maximum cumulative amount after which invoice generation will stop.</span></span>  
    * <span data-ttu-id="0cbe6-120">Immettere l'importo cumulativo massimo che può essere raggiunto utilizzando il modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-120">Enter the maximum cumulative amount that can be reached using the selected template.</span></span> <span data-ttu-id="0cbe6-121">Se si immette, ad esempio, 1.000,00 e vengono generate fatture mensili per 100,00 ciascuna, la generazione delle fatture verrà interrotta dopo la decima fattura.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-121">For example, if you enter 1,000.00 and generate monthly invoices for 100.00 each, invoices will stop generating after the tenth invoice is generated.</span></span>  
    * <span data-ttu-id="0cbe6-122">Genera fatture ricorrenti utilizzando i valori predefiniti dal modello di fattura a testo libero o dal conto cliente.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-122">Generate recurring invoices by using the default values from either free text invoice template or the customer account.</span></span>  
    * <span data-ttu-id="0cbe6-123">Scegliere se utilizzare il modello di fattura a testo libero o il conto cliente per determinare i valori predefiniti per lingua, profilo registrazione, fascia IVA, fascia IVA articoli, codice elenco, paese di consegna, valuta, termini di pagamento, metodo di pagamento, specifica di pagamento, scadenzario pagamenti, sconto di cassa, dimensioni finanziarie e distinta ordine di accredito quando vengono create le fatture.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-123">Select whether to use the free text invoice template or the customer account to determine the default values for the language, posting profile, sales tax group, item sales tax group, list code, country/region for delivery, currency, terms of payment, method of payment, payment specification, payment schedule, cash discount, financial dimensions, and giro money transfer slip when invoices are created.</span></span>  
10. <span data-ttu-id="0cbe6-124">Selezionare il criterio di ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-124">Select the recurrence pattern.</span></span>
    * <span data-ttu-id="0cbe6-125">Giornaliero: selezionare questa opzione e immettere il numero di giorni nel campo Per.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-125">Daily – Select this option and enter the number of days in the Per field.</span></span> <span data-ttu-id="0cbe6-126">Se si immette, ad esempio, 15, la fattura verrà generata ogni 15 giorni per il cliente specificato.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-126">For example, if you enter 15, an invoice will be generated every 15 days for this customer.</span></span>  <span data-ttu-id="0cbe6-127">Settimanale: selezionare questa opzione e immettere il numero di settimane nel campo Per.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-127">Weekly - Select this option and enter the number of weeks in the Per field.</span></span> <span data-ttu-id="0cbe6-128">Se si immette, ad esempio, 2, la fattura verrà generata ogni 2 settimane per il cliente specificato.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-128">For example, if you enter 2, an invoice will be generated every two weeks for this customer.</span></span>  <span data-ttu-id="0cbe6-129">Mensile: selezionare questa opzione e immettere il numero di mesi nel campo Per.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-129">Monthly - Select this option and enter the number of months in the Per field.</span></span> <span data-ttu-id="0cbe6-130">Se si immette, ad esempio, 6, la fattura verrà generata ogni 6 mesi per il cliente specificato.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-130">For example, if you enter 6, an invoice will be generated every six months for this customer.</span></span>  <span data-ttu-id="0cbe6-131">Annuale: selezionare questa opzione e immettere il numero di anni nel campo Per.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-131">Yearly – Select this option and enter the number of years in the Per field.</span></span> <span data-ttu-id="0cbe6-132">Se si immette, ad esempio, 2, la fattura verrà generata ogni 2 anni per il cliente specificato.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-132">For example, if you enter 2, an invoice will be generated every two years for this customer.</span></span>  
11. <span data-ttu-id="0cbe6-133">Nel campo Per immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-133">In the Per field, enter a number.</span></span>

