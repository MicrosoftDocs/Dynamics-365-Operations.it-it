---
title: Sconti di cassa
description: Gli sconti di cassa vengono impostati e condivisi per la contabilità fornitori e la contabilità clienti.  Lo sconto di cassa disponibile può essere definito sulla fattura cliente o sulla fattura fornitore e verrà applicato se la fattura viene pagata entro la data dello sconto di cassa.
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CashDisc
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd15a021244e55ea988a95184a758a321ebeafb3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "320031"
---
# <a name="cash-discounts"></a><span data-ttu-id="13542-104">Sconti di cassa</span><span class="sxs-lookup"><span data-stu-id="13542-104">Cash discounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="13542-105">Gli sconti di cassa vengono impostati e condivisi per la contabilità fornitori e la contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="13542-105">Cash discounts are setup and shared for Accounts payable and Accounts receivable.</span></span>  <span data-ttu-id="13542-106">Lo sconto di cassa disponibile può essere definito sulla fattura cliente o sulla fattura fornitore e verrà applicato se la fattura viene pagata entro la data dello sconto di cassa.</span><span class="sxs-lookup"><span data-stu-id="13542-106">The cash discount available can be defined on the customer invoice or vendor invoice, and will be taken if the invoice is paid within the cash discount date.</span></span> 

## <a name="cash-discounts"></a><span data-ttu-id="13542-107">Sconti di cassa</span><span class="sxs-lookup"><span data-stu-id="13542-107">Cash discounts</span></span>

<span data-ttu-id="13542-108">Gli sconti di cassa per entrambi i clienti o fornitori possono essere creati nella pagina di sconti di cassa.</span><span class="sxs-lookup"><span data-stu-id="13542-108">Cash discounts for both customers or vendors can be created in the Cash discounts page.</span></span> <span data-ttu-id="13542-109">Utilizzando il campo Codice sconto successivo è inoltre possibile definire una serie di sconti di cassa che si succedono via via che gli sconti di cassa precedenti scadono.</span><span class="sxs-lookup"><span data-stu-id="13542-109">You can also define, by using the Next discount code field, a series of cash discounts that succeed each other as previous cash discount dates expire.</span></span> <span data-ttu-id="13542-110">Per ulteriori informazioni, vedere "Esempio: Serie di sconti di cassa" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="13542-110">For more information, see “Example: Series of cash discounts” later in this topic.</span></span> <span data-ttu-id="13542-111">Se la fattura, la transazione in Avere (un pagamento oppure una nota di accredito) o entrambe sono immesse una valuta diversa da quella di contabilizzazione della persona giuridica, lo sconto di cassa è calcolato usando il tasso di cambio alla data del pagamento o della nota di accredito.</span><span class="sxs-lookup"><span data-stu-id="13542-111">If the invoice, credit transaction (either a payment or a credit note), or both are entered in a currency other than the accounting currency of the legal entity, the cash discount is calculated using the exchange rate based on the date of the payment or credit note.</span></span> <span data-ttu-id="13542-112">Se la fattura e il documento di credito vengono inseriti in persone giuridiche diverse, e se le valute di contabilizzazione per le persone giuridiche differiscono, il tasso di cambio viene preso dalla persona giuridica della fattura, alla data del documento di credito.</span><span class="sxs-lookup"><span data-stu-id="13542-112">If the invoice and credit document are entered in different legal entities, and if the accounting currencies for the legal entities differ, the exchange rate is taken from the legal entity of the invoice, as of the date of the credit document.</span></span> <span data-ttu-id="13542-113">Per ulteriori informazioni, vedere "Esempio: Tassi di cambio per sconti di cassa" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="13542-113">For more information, see “Example: Exchange rates for cash discounts” later in this topic.</span></span>

## <a name="defaulting-order-of-cash-discount-main-account"></a><span data-ttu-id="13542-114">Ordine predefinito del conto principale dello sconto di cassa</span><span class="sxs-lookup"><span data-stu-id="13542-114">Defaulting order of cash discount main account</span></span>

<span data-ttu-id="13542-115">Se una fattura viene liquidata in tempo per ottenere uno sconto di cassa, questo verrà registrato automaticamente in un conto principale per sconti di cassa in base alle seguenti priorità di default:</span><span class="sxs-lookup"><span data-stu-id="13542-115">If an invoice is settled in time to obtain a cash discount, the cash discount is automatically posted to a cash discount main account according to the following defaulting priority:</span></span>
1.  <span data-ttu-id="13542-116">Il conto principale specificato nel campo Conto sconto di cassa alternativo sulla pagina Liquida transazioni aperte del cliente o del fornitore.</span><span class="sxs-lookup"><span data-stu-id="13542-116">The main account specified in the Alternative cash discount account field on the customer Settle open transactions page or the vendor Settle open transactions page.</span></span>
2.  <span data-ttu-id="13542-117">Il conto principale specificato nel campo Sconto di cassa cliente o nel campo Sconto di cassa fornitore del gruppo di registrazione contabile assegnato al codice IVA della fattura.</span><span class="sxs-lookup"><span data-stu-id="13542-117">The main account specified in the Customer cash discount field or the Vendor cash discount field of the ledger posting group that is assigned to the sales tax code of the invoice.</span></span> <span data-ttu-id="13542-118">Configurare gruppi di registrazione contabile nella pagina Gruppi registrazione contabile e assegnarli ai codici IVA nella relativa pagina.</span><span class="sxs-lookup"><span data-stu-id="13542-118">Set up ledger posting groups on the Ledger posting groups page and assign them to sales tax codes in the Sales tax codes page.</span></span>
3.  <span data-ttu-id="13542-119">Il conto di registrazione principale nella pagina Sconti di cassa nel campo Conto principale per sconti cliente o nel campo Conto principale per sconti fornitore per il codice sconto di cassa del cliente o del fornitore indicato nella fattura liquidata.</span><span class="sxs-lookup"><span data-stu-id="13542-119">The main posting account on the Cash discounts page in either the Main account for customer discounts field or the Main account for vendor discounts field for the cash discount code that is on the settled invoice.</span></span>
4.  <span data-ttu-id="13542-120">Il conto principale per gli sconti di cassa, come definito nella pagina Conti per transazioni automatiche.</span><span class="sxs-lookup"><span data-stu-id="13542-120">The main account for cash discounts, as defined in the Accounts for automatic transactions page.</span></span>

## <a name="example-series-of-cash-discounts"></a><span data-ttu-id="13542-121"> Esempio: Serie di sconti di cassa</span><span class="sxs-lookup"><span data-stu-id="13542-121">Example: Series of cash discounts</span></span>
<span data-ttu-id="13542-122">Impostare tre codici sconto di cassa come segue:</span><span class="sxs-lookup"><span data-stu-id="13542-122">Set up three cash discount codes as follows:</span></span>
-   <span data-ttu-id="13542-123">Codice 5G10%: viene applicato uno sconto di cassa del 10% quando l'importo viene pagato entro 5 giorni.</span><span class="sxs-lookup"><span data-stu-id="13542-123">Code 5D10% – A cash discount of 10% when the amount is paid within 5 days.</span></span>
-   <span data-ttu-id="13542-124">Codice 10G5%: viene applicato uno sconto di cassa del 5% quando l'importo viene pagato entro 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="13542-124">Code 10D5% – A cash discount of 5% when the amount is paid within 10 days.</span></span>
-   <span data-ttu-id="13542-125">Codice 14G2%: viene applicato uno sconto di cassa del 2% quando l'importo viene pagato entro 14 giorni.</span><span class="sxs-lookup"><span data-stu-id="13542-125">Code 14D2% – A cash discount of 2% when the amount is paid within 14 days.</span></span>

<span data-ttu-id="13542-126">Nel campo Codice sconto successivo:</span><span class="sxs-lookup"><span data-stu-id="13542-126">In the Next discount code field:</span></span>
-   <span data-ttu-id="13542-127">Per il codice 5G10% selezionare 10G5%.</span><span class="sxs-lookup"><span data-stu-id="13542-127">For the 5D10% code, select 10D5%.</span></span>
-   <span data-ttu-id="13542-128">Per il codice 10G5% selezionare 14G2%.</span><span class="sxs-lookup"><span data-stu-id="13542-128">For the 10D5% code, select 14D2%.</span></span>
-   <span data-ttu-id="13542-129">Per il codice 14D2%, lasciare vuoto il campo Codice sconto successivo.</span><span class="sxs-lookup"><span data-stu-id="13542-129">For the 14D2% code, leave the Next discount code field blank.</span></span>

<span data-ttu-id="13542-130">I tre sconti di cassa si succedono via via che la data del pagamento supera la data dello sconto di cassa precedente sulla fattura.</span><span class="sxs-lookup"><span data-stu-id="13542-130">The three cash discounts succeed each other as the payment date exceeds the previous cash discount date on the invoice.</span></span> <span data-ttu-id="13542-131">Solo uno sconto di cassa viene concesso quando la fattura viene pagata, in base alla data dello sconto di cassa soddisfatta nella sequenza di sconti di cassa.</span><span class="sxs-lookup"><span data-stu-id="13542-131">Only one cash discount is granted when the invoice is paid, based on which cash discount date is meet in the sequence of cash discounts.</span></span>

## <a name="example-exchange-rates-for-cash-discounts"></a><span data-ttu-id="13542-132"> Esempio: Tassi di cambio per sconti di cassa</span><span class="sxs-lookup"><span data-stu-id="13542-132">Example: Exchange rates for cash discounts</span></span>
<span data-ttu-id="13542-133">La valuta di contabilizzazione della persona giuridica è l'EUR e per gli USD vengono specificati i seguenti tassi di cambio:</span><span class="sxs-lookup"><span data-stu-id="13542-133">Your legal entity’s accounting currency is EUR and the following exchange rates are specified for USD:</span></span>
-   <span data-ttu-id="13542-134">1 febbraio = 110</span><span class="sxs-lookup"><span data-stu-id="13542-134">February 1 = 110</span></span>
-   <span data-ttu-id="13542-135">1 marzo = 80</span><span class="sxs-lookup"><span data-stu-id="13542-135">March 1 = 80</span></span>

<span data-ttu-id="13542-136">Una fattura del valore di 1000 USD con termini di sconto di cassa di 20G2% viene registrata il 15 febbraio.</span><span class="sxs-lookup"><span data-stu-id="13542-136">An invoice for 1000 USD with cash discount terms of 20D2% is posted on February 15.</span></span> <span data-ttu-id="13542-137">L'importo della fattura nella valuta di contabilizzazione è di 1100 EUR.</span><span class="sxs-lookup"><span data-stu-id="13542-137">The accounting currency amount of the invoice is 1100 EUR.</span></span> <span data-ttu-id="13542-138">Un pagamento di 980 USD viene liquidato con la fattura il 1 marzo.</span><span class="sxs-lookup"><span data-stu-id="13542-138">A payment for 980 USD is settled with the invoice on March 1.</span></span> <span data-ttu-id="13542-139">L'importo dello sconto di cassa è 20 USD.</span><span class="sxs-lookup"><span data-stu-id="13542-139">The cash discount amount is 20 USD.</span></span> <span data-ttu-id="13542-140">L'importo del pagamento nella valuta di contabilizzazione è di 784 EUR.</span><span class="sxs-lookup"><span data-stu-id="13542-140">The accounting currency amount of the payment is 784 EUR.</span></span> <span data-ttu-id="13542-141">L'importo dello sconto di cassa nella valuta di contabilizzazione viene calcolato usando il tasso di cambio al 1 marzo: 20 \* 80 / 100 = 16 EUR.</span><span class="sxs-lookup"><span data-stu-id="13542-141">The accounting currency amount of the cash discount is calculated by using the exchange rate as of March 1: 20 \* 80 / 100 = 16 EUR.</span></span>

> [!NOTE]
> <span data-ttu-id="13542-142">Se l'opzione Calcola sconti di cassa per pagamenti parziali è selezionata nei parametri di contabilità clienti o nelle pagine di parametri di contabilità fornitori, viene utilizzato il tasso di cambio in vigore alla data di ciascun pagamento parziale.</span><span class="sxs-lookup"><span data-stu-id="13542-142">If the Calculate cash discounts for partial payments option is selected in the Accounts receivable parameters or Accounts payable parameters pages, the exchange rate that is in effect on the date of each partial payment is used.</span></span> 

