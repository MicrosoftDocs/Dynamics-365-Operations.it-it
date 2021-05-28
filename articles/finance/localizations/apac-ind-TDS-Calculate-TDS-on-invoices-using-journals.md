---
title: Calcolare la TDS sulle fatture utilizzando giornali di registrazione
description: In questo argomento sono elencati i passaggi per il calcolo dell'imposta dedotta all'origine (TDS) nei giornali di registrazione.
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
ms.openlocfilehash: d68e1b3a4dc31823ec56a525149f16bdc23c0883
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023372"
---
# <a name="calculate-tds-on-invoices-using-journals"></a><span data-ttu-id="749a8-103">Calcolare la TDS sulle fatture utilizzando giornali di registrazione</span><span class="sxs-lookup"><span data-stu-id="749a8-103">Calculate TDS on invoices using journals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="749a8-104">In questo argomento sono elencati i passaggi per il calcolo dell'imposta dedotta all'origine (TDS) nei giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="749a8-104">This topic lists the steps for calculating Tax Deducted at Source (TDS) on journals.</span></span>

<span data-ttu-id="749a8-105">Inizia aprendo la pagina **Giornali di registrazione generali** (**Contabilità generale > Inserimenti nel giornale di registrazione > Giornali di registrazione generali**).</span><span class="sxs-lookup"><span data-stu-id="749a8-105">Begin by opening the **General journals** page (**General ledger > Journal entries > General journals**).</span></span>

<span data-ttu-id="749a8-106">[![Giornali di registrazione generali](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)</span><span class="sxs-lookup"><span data-stu-id="749a8-106">[![General journals](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)</span></span>

1. <span data-ttu-id="749a8-107">Crea righe di giornale di registrazione utilizzando i moduli del giornale di registrazione elencati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="749a8-107">Create journal lines using the journal forms that are listed in the table.</span></span> <span data-ttu-id="749a8-108">Seleziona il tipo di conto e il tipo di conto di contropartita e inserisci l'importo per la transazione.</span><span class="sxs-lookup"><span data-stu-id="749a8-108">Select the account type and offset account type and enter the amount for the transaction.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="749a8-109">Nella pagina **Giornale di approvazione fatture**, seleziona **Trova giustificativi** e seleziona le fatture su cui calcolare la TDS.</span><span class="sxs-lookup"><span data-stu-id="749a8-109">On the **Invoice approval journal** page, select **Find vouchers** and select invoices to calculate TDS on.</span></span> <span data-ttu-id="749a8-110">Visualizza le fatture create nella pagina **Registro fatture** o la pagina **Trova giustificativi**.</span><span class="sxs-lookup"><span data-stu-id="749a8-110">View the invoices created in the **Invoice register** page or the **Find vouchers** page.</span></span>  

2. <span data-ttu-id="749a8-111">Nella scheda **Generale** della pagina **Giustificativo giornale di registrazione**, visualizza o modifica il gruppo TDS definito per il fornitore o il cliente nel campo **Gruppo TDS**.</span><span class="sxs-lookup"><span data-stu-id="749a8-111">On the **General** tab of the **Journal voucher** page, view or modify the default TDS group defined for the vendor or customer, in the **TDS group** field.</span></span> <span data-ttu-id="749a8-112">L'importo TDS calcolato sulle righe del giornale di registrazione si basa sulla formula definita per i codici imposta TDS elencati nel campo **Gruppo TDS**.</span><span class="sxs-lookup"><span data-stu-id="749a8-112">The TDS amount that's calculated on journal lines is based on the formula defined for the TDS tax codes listed in the **TDS group** field.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="749a8-113">Il campo **Gruppo ritenute d'acconto** e il campo **Gruppo TCS** non sono disponibili quando selezioni un gruppo TDS nel campo **Gruppo TDS**.</span><span class="sxs-lookup"><span data-stu-id="749a8-113">The **Withholding tax group**  field and the **TCS group** field become unavailable when you select a TDS group in the **TDS group** field.</span></span> <span data-ttu-id="749a8-114">Il campo **Gruppo ritenute d'acconto** è disponibile solo nella pagina **Giornale di registrazione generale**.</span><span class="sxs-lookup"><span data-stu-id="749a8-114">The **Withholding tax group** field is available only on the **General journal** page.</span></span> <span data-ttu-id="749a8-115">La TDS viene calcolata solo se la casella di controllo **Calcola ritenuta d'acconto** è selezionata per il fornitore o il cliente nelle pagine **Tutti i fornitori** o **Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="749a8-115">TDS is calculated only if the **Calculate withholding tax** check box is selected for the vendor or customer on the **All vendors** or **All customers** pages.</span></span>   

3. <span data-ttu-id="749a8-116">Seleziona la scheda **Informazioni fiscali**. Se necessario, seleziona gli indirizzi alternativi di una società impostati per la società in questo campo.</span><span class="sxs-lookup"><span data-stu-id="749a8-116">Select the **Tax information** tab. Select the alternate addresses of a company that's set up for the company in this field, if required.</span></span> <span data-ttu-id="749a8-117">Puoi visualizzare il nome della società nel campo **Nome**, che si trova sotto il gruppo di campi **Informazioni società**.</span><span class="sxs-lookup"><span data-stu-id="749a8-117">You can view the company name in the **Name** field, which is under the **Company information** field group.</span></span> 

4. <span data-ttu-id="749a8-118">Visualizza la natura della categoria di soggetto valutato del fornitore o del cliente nel campo **Natura soggetto valutato** sotto il gruppo di campi **Ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="749a8-118">View the nature of assessee category of the vendor or customer in the **Nature of assessee** field, which is under the **Withholding tax** field group.</span></span> <span data-ttu-id="749a8-119">Nel campo **Numero conto imposta** (**TAN**), visualizza il TAN del nome di società selezionato che viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="749a8-119">In the **Tax Account Number** (**TAN**) field, view the TAN of the selected company name that's displayed.</span></span>  

5. <span data-ttu-id="749a8-120">Seleziona **Ritenuta d'acconto** nel menu **Ritenuta d'acconto** per aprire la pagina **Transazioni ritenuta d'acconto temporanee**.</span><span class="sxs-lookup"><span data-stu-id="749a8-120">Select **Withholding tax** in **Withholding tax** menu to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="749a8-121">I seguenti campi sono visualizzati nel riquadro superiore della pagina **Transazioni ritenuta d'acconto temporanee**.</span><span class="sxs-lookup"><span data-stu-id="749a8-121">The following fields are displayed on the upper pane of the **Temporary withholding tax transactions** page.</span></span>

   - <span data-ttu-id="749a8-122">**Importo ritenuta d'acconto in totale** - La TDS totale calcolata per la transazione per il gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="749a8-122">**Withholding tax amount in total** - The total TDS calculated for the transaction for the TDS group.</span></span>

   - <span data-ttu-id="749a8-123">**Valore** - La percentuale totale utilizzata per calcolare la TDS per la transazione.</span><span class="sxs-lookup"><span data-stu-id="749a8-123">**Value** - The total percentage used to calculate TDS for the transaction.</span></span> <span data-ttu-id="749a8-124">La percentuale totale si basa sulla formula definita per i codici imposta TDS e associata al gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="749a8-124">The total percentage is based on the formula that is defined for TDS tax codes attached to the TDS group.</span></span>

   - <span data-ttu-id="749a8-125">**Importo ritenuta d'acconto rettificato in totale** - L'importo TDS rettificato totale per tutti i codici imposta nel gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="749a8-125">**Adjusted withholding tax amount in total** - The total adjusted TDS amount for all tax codes in the TDS group.</span></span>

   - <span data-ttu-id="749a8-126">**TDS** - Se selezionato, un gruppo TDS viene associato alla transazione.</span><span class="sxs-lookup"><span data-stu-id="749a8-126">**TDS** - If selected, a TDS group is attached to the transaction.</span></span>

  <span data-ttu-id="749a8-127">I campi nelle schede **Panoramica**, **Generale** e **Rettifica** nella pagina **Transazioni ritenuta d'acconto temporanee** visualizza dettagli sull'importo TDS calcolato e sull'importo TDS rettificato per ogni codice imposta TDS associato al gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="749a8-127">The fields on the **Overview**, **General**, and **Adjustment** tabs on the **Temporary withholding tax transactions** page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

6. <span data-ttu-id="749a8-128">Seleziona **Soglia** per aprire la pagina **Soglia**.</span><span class="sxs-lookup"><span data-stu-id="749a8-128">Select **Threshold** to open the **Threshold** page.</span></span> <span data-ttu-id="749a8-129">Visualizza il limite di soglia e il limite di soglia di eccezione definiti per il componente fiscale TDS associato a uno specifico codice imposta TDS in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="749a8-129">View the threshold limit and exception threshold limit defined for the TDS tax component attached to a specific TDS tax code on this page.</span></span>

   <span data-ttu-id="749a8-130">Seleziona **Designer formula** per aprire il modulo **Designer formula**.</span><span class="sxs-lookup"><span data-stu-id="749a8-130">Select **Formula designer** to open the **Formula designer** form.</span></span> <span data-ttu-id="749a8-131">Visualizza la formula definita per uno specifico codice imposta TDS in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="749a8-131">View the formula defined for a specific TDS tax code in this page.</span></span> <span data-ttu-id="749a8-132">Chiudi le pagine **Designer formula** e **Transazioni ritenuta d'acconto temporanee** per tornare alla pagina **Giustificativo giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="749a8-132">Close the **Formula designer** and **Temporary withholding tax transactions** pages to return to the **Journal voucher** page.</span></span>

8. <span data-ttu-id="749a8-133">Immetti gli altri dettagli necessari.</span><span class="sxs-lookup"><span data-stu-id="749a8-133">Enter the other required details.</span></span> <span data-ttu-id="749a8-134">Convalida e registra il giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="749a8-134">Validate and post the journal.</span></span> <span data-ttu-id="749a8-135">L'importo TDS calcolato sulle fatture di acquisto viene registrato nel conto fornitori.</span><span class="sxs-lookup"><span data-stu-id="749a8-135">The TDS amount that's calculated on purchase invoices is posted to the payable account.</span></span> <span data-ttu-id="749a8-136">L'importo TDS calcolato sulle fatture di vendita viene registrato nel conto clienti definito per ogni codice imposta TDS nel gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="749a8-136">The TDS amount that's calculated on sales invoices is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="749a8-137">I conti clienti o fornitori per i codici imposta TDS sono definiti nella pagina **Codici ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="749a8-137">The payable accounts or receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>

9. <span data-ttu-id="749a8-138">Seleziona **Ritenuta d'acconto registrata** per aprire la pagina **Transazioni** **ritenuta** **d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="749a8-138">Select **Posted withholding tax** to open the **Withholding** **tax** **transactions** page.</span></span> <span data-ttu-id="749a8-139">Nel campo **Valore** viene visualizzata la percentuale totale utilizzata per calcolare la TDS per la transazione.</span><span class="sxs-lookup"><span data-stu-id="749a8-139">In the **Value** field, the total percentage used to calculate TDS for the transaction is displayed.</span></span>

   <span data-ttu-id="749a8-140">I campi nelle schede **Panoramica**, **Generale** e **Importo** nella pagina Transazioni ritenuta d'acconto visualizza dettagli sull'importo TDS calcolato e sull''importo TDS rettificato per ogni codice imposta TDS associato al gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="749a8-140">The fields on the **Overview**, **General**, and **Amount** tabs in the Withholding tax transactions page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>
