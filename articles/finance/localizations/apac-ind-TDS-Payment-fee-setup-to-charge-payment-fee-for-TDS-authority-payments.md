---
title: Impostare commissioni di pagamento per i pagamenti all'autorità TCS
description: In questo argomento viene illustrato come impostare commissioni di pagamento addebitate per i pagamenti all'autorità TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: b52331bb1c7a1bc2c764008112f3df9cc0385995
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023373"
---
# <a name="set-up-payment-fees-for-tds-authority-payments"></a><span data-ttu-id="a31d6-103">Impostare commissioni di pagamento per i pagamenti all'autorità TCS</span><span class="sxs-lookup"><span data-stu-id="a31d6-103">Set up payment fees for TDS authority payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a31d6-104">In questo argomento viene illustrato come impostare commissioni di pagamento addebitate per i pagamenti all'autorità TDS.</span><span class="sxs-lookup"><span data-stu-id="a31d6-104">This topic explains how to set up payment fees that are charged for Tax Deducted at Source (TDS) authority payments.</span></span>

1. <span data-ttu-id="a31d6-105">Vai a **Contabilità fornitori \> Impostazione pagamenti \> Commissione di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="a31d6-105">Go to **Accounts payable \> Payment setup \> Payment fee**.</span></span>

    <span data-ttu-id="a31d6-106">[![Pagina Commissione di pagamento](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)</span><span class="sxs-lookup"><span data-stu-id="a31d6-106">[![Payment fee page](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)</span></span>

2. <span data-ttu-id="a31d6-107">Seleziona **Nuovo** per creare una nuova commissione di pagamento e immetti i dettagli richiesti.</span><span class="sxs-lookup"><span data-stu-id="a31d6-107">Select **New** to create a payment fee, and enter the required details.</span></span>
3. <span data-ttu-id="a31d6-108">Nel campo **Tipo di commissione** seleziona il tipo di commissione pagamento:</span><span class="sxs-lookup"><span data-stu-id="a31d6-108">In the **Fee type** field, select the type of payment fee:</span></span>

    - <span data-ttu-id="a31d6-109">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="a31d6-109">**None**</span></span>
    - <span data-ttu-id="a31d6-110">**Interessi** - Gli interessi vengono addebitati sui pagamenti in ritardo effettuati al fornitore dell'autorità TDS.</span><span class="sxs-lookup"><span data-stu-id="a31d6-110">**Interest** – Interest is charged on late payments that are made to the TDS authority vendor.</span></span>
    - <span data-ttu-id="a31d6-111">**Altri** -Altri addebiti vengono addebitati sui pagamenti in ritardo effettuati al fornitore dell'autorità TDS.</span><span class="sxs-lookup"><span data-stu-id="a31d6-111">**Others** – Other charges are charged on late payments that are made to the TDS authority vendor.</span></span>

    <span data-ttu-id="a31d6-112">Se selezioni **Interessi** o **Altri**, il campo **Addebito** viene impostato automaticamente su **Contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="a31d6-112">If you select **Interest** or **Others**, the **Charge** field is automatically set to **Ledger**.</span></span>

4. <span data-ttu-id="a31d6-113">Se hai selezionato **Interessi** o **Altri** nel campo **Tipo di campo**, nel campo **Conto principale** seleziona il conto CoGe in cui registrare gli interessi o altri addebiti.</span><span class="sxs-lookup"><span data-stu-id="a31d6-113">If you selected **Interest** or **Others** in the **Field type** field, in the **Main account** field, select the ledger account to post the interest or other charges to.</span></span>
5. <span data-ttu-id="a31d6-114">Immetti gli altri dettagli necessari.</span><span class="sxs-lookup"><span data-stu-id="a31d6-114">Enter the other required details.</span></span>
6. <span data-ttu-id="a31d6-115">Nel riquadro Azioni seleziona **Impostazione commissione pagamento** per aprire la pagina **Impostazione commissione pagamento**, dove è possibile impostare commissioni di pagamento per varie combinazioni di banche, metodi di pagamento, specifiche di pagamento, valute e intervalli di date.</span><span class="sxs-lookup"><span data-stu-id="a31d6-115">On the Action Pane, select **Payment fee setup** to open the **Payment fee setup** page, where you can set up payment fees for various combinations of banks, methods of payment, payment specifications, currencies, and date intervals.</span></span>

    <span data-ttu-id="a31d6-116">[![Pagina Impostazione commissione pagamento](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)</span><span class="sxs-lookup"><span data-stu-id="a31d6-116">[![Payment fee setup page](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)</span></span>

7. <span data-ttu-id="a31d6-117">Nella scheda **Panoramica**, nel campo **Raggruppamenti**, specifica per quali banche stai impostando la commissione di pagamento:</span><span class="sxs-lookup"><span data-stu-id="a31d6-117">On the **Overview** tab, in the **Groupings** field, specify which banks you're setting up the payment fee for:</span></span>

    - <span data-ttu-id="a31d6-118">**Tabella** - La commissione è valida per un conto bancario specifico.</span><span class="sxs-lookup"><span data-stu-id="a31d6-118">**Table** – The fee is valid for a specific bank account.</span></span>
    - <span data-ttu-id="a31d6-119">**Gruppo** - La commissione è valida per un gruppo bancario specifico.</span><span class="sxs-lookup"><span data-stu-id="a31d6-119">**Group** – The fee is valid for a specific bank group.</span></span>
    - <span data-ttu-id="a31d6-120">**Tutto** - La commissione è valida per tutti i conti bancari.</span><span class="sxs-lookup"><span data-stu-id="a31d6-120">**All** – The fee is valid for all the bank accounts.</span></span>

8. <span data-ttu-id="a31d6-121">Se hai selezionato **Tabella** o **Gruppo** nel campo **Raggruppamenti**, nel campo **Relazione bancaria**, seleziona il conto bancario o il gruppo bancario specifico per cui stai impostando la commissione di pagamento.</span><span class="sxs-lookup"><span data-stu-id="a31d6-121">If you selected **Table** or **Group** in the **Groupings** field, in the **Bank relation** field, select the specific bank account or bank group that you're setting up the payment fee for.</span></span>
9. <span data-ttu-id="a31d6-122">Nel campo **Metodo di pagamento**, seleziona un metodo di pagamento per il pagamento delle commissioni.</span><span class="sxs-lookup"><span data-stu-id="a31d6-122">In the **Method of payment** field, select the method of payment for the payment of fees.</span></span>
10. <span data-ttu-id="a31d6-123">Nel campo **Specifiche pagamento** seleziona o immetti il codice della specifica di pagamento che è stato generato nella pagina **Specifiche pagamento**.</span><span class="sxs-lookup"><span data-stu-id="a31d6-123">In the **Payment specification** field, select or enter the payment specification code that was generated on the **Payment specification** page.</span></span>
    - <span data-ttu-id="a31d6-124">La specifica di pagamento viene utilizzata con i metodi di trasferimento fondi attraverso sistemi di pagamento elettronici.</span><span class="sxs-lookup"><span data-stu-id="a31d6-124">The Payment specification is used with electronic fund transfer methods of payment.</span></span>
12. <span data-ttu-id="a31d6-125">Nel campo **Valuta pagamento**, seleziona la valuta che attiva la commissione.</span><span class="sxs-lookup"><span data-stu-id="a31d6-125">In the **Payment currency** field, select the currency that activates the fee.</span></span> <span data-ttu-id="a31d6-126">Solo le transazioni che utilizzano la valuta selezionata possono attivare la commissione.</span><span class="sxs-lookup"><span data-stu-id="a31d6-126">Only transactions that use the selected currency can activate the fee.</span></span> <span data-ttu-id="a31d6-127">Se lasci vuoto questo campo, tutte le valute attivano la commissione.</span><span class="sxs-lookup"><span data-stu-id="a31d6-127">If you leave this field blank, all currencies activate the fee.</span></span>
13. <span data-ttu-id="a31d6-128">Nel campo **Percentuale/importo** seleziona il metodo di calcolo.</span><span class="sxs-lookup"><span data-stu-id="a31d6-128">In the **Percentage/Amount** field, select the calculation method.</span></span> <span data-ttu-id="a31d6-129">Le opzioni sono **Importo**, **Percentuale** e **Intervallo**.</span><span class="sxs-lookup"><span data-stu-id="a31d6-129">The options are **Amount**, **Percent**, and **Interval**.</span></span>
14. <span data-ttu-id="a31d6-130">Nel campo **Importo commissione**, specifica l'importo della commissione come percentuale del pagamento o dell'importo di un pagamento.</span><span class="sxs-lookup"><span data-stu-id="a31d6-130">In the **Fee amount** field, specify the fee amount as either a percentage of the payment or the amount for one payment.</span></span>
15. <span data-ttu-id="a31d6-131">Nel campo **Valuta commissioni**, specifica il codice valuta della commissione.</span><span class="sxs-lookup"><span data-stu-id="a31d6-131">In the **Fee currency** field, specify the currency code for the fee.</span></span>
16. <span data-ttu-id="a31d6-132">Seleziona la scheda **Generale** per visualizzare o modificare i dettagli del conto bancario selezionato.</span><span class="sxs-lookup"><span data-stu-id="a31d6-132">Select the **General** tab to view or modify the details for the selected bank account.</span></span>

    <span data-ttu-id="a31d6-133">[![Scheda Generale](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)</span><span class="sxs-lookup"><span data-stu-id="a31d6-133">[![General tab](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)</span></span>

16. <span data-ttu-id="a31d6-134">Nel campo **Minimo** immetti l'importo minimo della transazione che attiva la commissione.</span><span class="sxs-lookup"><span data-stu-id="a31d6-134">In the **Minimum** field, enter the minimum transaction amount that activates the fee.</span></span>
17. <span data-ttu-id="a31d6-135">Nel campo **Massimo** immetti l'importo massimo della transazione che attiva la commissione.</span><span class="sxs-lookup"><span data-stu-id="a31d6-135">In the **Maximum** field, enter the maximum transaction amount that activates the fee.</span></span>
18. <span data-ttu-id="a31d6-136">Nei campi **Data iniziale** e **Data finale**, definisci un intervallo di date per il calcolo delle commissioni.</span><span class="sxs-lookup"><span data-stu-id="a31d6-136">In the **From date** and **To date** fields, define a date range for calculating fees.</span></span>
19. <span data-ttu-id="a31d6-137">Nel campo **Commissione minima**, specifica l'importo della commissione come percentuale del pagamento o dell'importo di un pagamento.</span><span class="sxs-lookup"><span data-stu-id="a31d6-137">In the **Minimum fee** field, specify the amount of the fee as either a percentage of the payment or the amount for one payment.</span></span>
20. <span data-ttu-id="a31d6-138">Nel campo **Fascia IVA**, seleziona la fascia IVA da utilizzare per calcolare l'IVA per l'importo della commissione.</span><span class="sxs-lookup"><span data-stu-id="a31d6-138">In the **Sales tax group** field, select the sales tax group to use to calculate the sales tax for the fee amount.</span></span>
21. <span data-ttu-id="a31d6-139">Nel campo **Fascia IVA articoli**, seleziona la fascia IVA articoli da utilizzare per calcolare l'IVA articoli per l'importo della commissione.</span><span class="sxs-lookup"><span data-stu-id="a31d6-139">In the **Item sales tax group** field, select the item sales tax group to use to calculate the item sales tax for the fee amount.</span></span>
22. <span data-ttu-id="a31d6-140">Seleziona la scheda **Intervallo**.</span><span class="sxs-lookup"><span data-stu-id="a31d6-140">Select the **Interval** tab.</span></span> 

    <span data-ttu-id="a31d6-141">[![Scheda Intervallo](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)</span><span class="sxs-lookup"><span data-stu-id="a31d6-141">[![Interval tab](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)</span></span>

23. <span data-ttu-id="a31d6-142">Nel campo **Giorni**, immetti il numero di giorni compresi tra la data di registrazione (data di sconto) del pagamento e la data di scadenza dell'effetto passivo.</span><span class="sxs-lookup"><span data-stu-id="a31d6-142">In the **Days** field, enter the number of days between the posting date (discounting date) of the payment and the due date of the promissory note.</span></span>
24. <span data-ttu-id="a31d6-143">Nel campo **Percentuale/importo**, indica se la specifica è una percentuale o un importo fisso.</span><span class="sxs-lookup"><span data-stu-id="a31d6-143">In the **Percentage/Amount** field, select whether the specification is a percentage or a set amount.</span></span>
25. <span data-ttu-id="a31d6-144">Nel campo **Importo commissione**, immetti l'importo della commissione come percentuale del pagamento o dell'importo di un pagamento.</span><span class="sxs-lookup"><span data-stu-id="a31d6-144">In the **Fee amount** field, enter the amount of the fee as either a percentage of the payment or the amount for one payment.</span></span>
26. <span data-ttu-id="a31d6-145">Chiudi la pagina **Impostazione commissione pagamento**.</span><span class="sxs-lookup"><span data-stu-id="a31d6-145">Close the **Payment fee setup** page.</span></span>
27. <span data-ttu-id="a31d6-146">Chiudi la pagina **Commissione pagamento**.</span><span class="sxs-lookup"><span data-stu-id="a31d6-146">Close the **Payment fee** page.</span></span>
