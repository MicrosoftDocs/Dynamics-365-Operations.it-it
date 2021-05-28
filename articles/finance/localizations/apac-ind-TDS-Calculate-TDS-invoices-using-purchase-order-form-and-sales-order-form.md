---
title: Calcolare le fatture TDS utilizzando il modulo di ordine fornitore e il modulo di ordine cliente
description: In questo argomento sono elencati i passaggi per il calcolo dell'imposta dedotta all'origine (TDS) su vari tipi di fatture.
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
ms.openlocfilehash: e7925206f3c060c6332de9d4972c8a7fb0066be2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023348"
---
# <a name="calculate-tds-invoices-using-purchase-order-form-and-sales-order-form"></a><span data-ttu-id="3668b-103">Calcolare le fatture TDS utilizzando il modulo di ordine fornitore e il modulo di ordine cliente</span><span class="sxs-lookup"><span data-stu-id="3668b-103">Calculate TDS invoices using purchase order form and sales order form</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3668b-104">In questo argomento sono elencati i passaggi per il calcolo dell'imposta dedotta all'origine (TDS) su vari tipi di fatture utilizzando le pagine **Ordine fornitore**, **Giornale di registrazione acquisti**, **Ordine programmato** e **Ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="3668b-104">This topic lists the steps for calculating Tax Deducted at Source (TDS) on various types of invoices using the **Purchase order**, **Purchase journal**, **Blanket order**, and **Sales order** pages.</span></span>

1. <span data-ttu-id="3668b-105">Crea un ordine fornitore, un giornale di registrazione acquisti, un ordine programmato di acquisto o un ordine cliente utilizzando la pagina elencata.</span><span class="sxs-lookup"><span data-stu-id="3668b-105">Create a purchase order, purchase journal, purchase blanket order, or a sales order using the page listed.</span></span> <span data-ttu-id="3668b-106">Immetti i dettagli richiesti.</span><span class="sxs-lookup"><span data-stu-id="3668b-106">Enter the required details.</span></span>

2. <span data-ttu-id="3668b-107">Seleziona la scheda **Imposta** per visualizzare la natura del soggetto valutato del fornitore o del cliente.</span><span class="sxs-lookup"><span data-stu-id="3668b-107">Select the **Setup** tab to view the nature of the assessee of the vendor or customer.</span></span> <span data-ttu-id="3668b-108">Queste informazioni sono elencate nel campo **Natura soggetto valutato**, sotto il gruppo di campi **Gruppo ritenute d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="3668b-108">This information is listed in the **Nature of assessee** field, under the **Withholding tax group** field group.</span></span>

3. <span data-ttu-id="3668b-109">Nel campo **Gruppo TDS**, visualizza o modifica il gruppo TDS predefinito definito per il fornitore o il cliente.</span><span class="sxs-lookup"><span data-stu-id="3668b-109">In the **TDS group** field, view or modify the default TDS group defined for the vendor or customer.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3668b-110">Il campo **Gruppo TCS** non è disponibile quando si seleziona un gruppo TDS nel campo **Gruppo TDS**.</span><span class="sxs-lookup"><span data-stu-id="3668b-110">The **TCS group** field isn't available when you select a TDS group in the **TDS group** field.</span></span> <span data-ttu-id="3668b-111">La TDS viene calcolata solo se la casella di controllo **Calcola ritenuta d'acconto** è selezionata per il fornitore o il cliente nella pagina **Tutti i fornitori** o **Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="3668b-111">TDS is calculated only if the **Calculate withholding tax** check box is selected for the vendor or customer on the **All vendors** or **All customers** page.</span></span>  

4. <span data-ttu-id="3668b-112">Crea righe articolo nella scheda **Righe** e immetti i dettagli richiesti.</span><span class="sxs-lookup"><span data-stu-id="3668b-112">Create item lines on the **Lines** tab and enter the required details.</span></span>

5. <span data-ttu-id="3668b-113">Seleziona la scheda **Imposta** (a livello di riga) per visualizzare o modificare il gruppo TDS definito a livello di intestazione.</span><span class="sxs-lookup"><span data-stu-id="3668b-113">Select the **Setup** tab (line-level) to view or change the TDS group defined at the header-level.</span></span> <span data-ttu-id="3668b-114">Il gruppo TDS viene visualizzato nel campo **Gruppo TDS**, che si trova sotto il gruppo di campi **Gruppo ritenute d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="3668b-114">The TDS group is displayed in the **TDS group** field, which is under the **Withholding tax group** field group.</span></span>

6. <span data-ttu-id="3668b-115">Seleziona la scheda **Informazioni fiscali** e seleziona indirizzi alternativi impostati per il nome della società visualizzato in questo campo.</span><span class="sxs-lookup"><span data-stu-id="3668b-115">Select the **Tax information** tab and select alternate addresses that are set up for the company name that's displayed in this field.</span></span> <span data-ttu-id="3668b-116">Il nome della società viene visualizzato nel campo **Nome**, che si trova sotto il gruppo di campi **Informazioni società**.</span><span class="sxs-lookup"><span data-stu-id="3668b-116">The company name is displayed in the **Name** field, which is under the **Company information** field group.</span></span> 

   <span data-ttu-id="3668b-117">Il TAN del nome di società selezionato è visualizzato nel campo **Numero di conto imposta** (**TAN**), sotto il gruppo di campi **Ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="3668b-117">The TAN of the selected company name is displayed in the **Tax Account Number** (**TAN**) field, under the **Withholding tax** field group.</span></span> 

7. <span data-ttu-id="3668b-118">Seleziona **Ritenuta d'acconto** per aprire la pagina **Transazioni ritenuta d'acconto temporanee**.</span><span class="sxs-lookup"><span data-stu-id="3668b-118">Select **Withholding tax** to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="3668b-119">Visualizza i seguenti campi nel riquadro superiore della pagina **Transazioni ritenuta d'acconto temporanee**.</span><span class="sxs-lookup"><span data-stu-id="3668b-119">View the following fields on the upper pane of the **Temporary withholding tax transactions** page.</span></span>

   - <span data-ttu-id="3668b-120">**Importo** **ritenuta** **d'acconto** **in** **totale** - La TDS totale calcolata per la transazione per il gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="3668b-120">**Withholding** **tax** **amount** **in** **total** - The total TDS calculated for the transaction for the TDS group.</span></span>

   - <span data-ttu-id="3668b-121">**Valore** - La percentuale totale utilizzata per calcolare la TDS per la transazione.</span><span class="sxs-lookup"><span data-stu-id="3668b-121">**Value** - The total percentage used to calculate TDS for the transaction.</span></span> <span data-ttu-id="3668b-122">La percentuale totale si basa sulla formula definita per i codici imposta TDS e associata al gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="3668b-122">The total percentage is based on the formula that is defined for TDS tax codes attached to the TDS group.</span></span>

   - <span data-ttu-id="3668b-123">**Importo ritenuta d'acconto rettificato in totale** - L'importo TDS rettificato totale per tutti i codici imposta nel gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="3668b-123">**Adjusted withholding tax amount in total** - The total adjusted TDS amount for all tax codes in the TDS group.</span></span>

   - <span data-ttu-id="3668b-124">**TDS** - Se selezionato, un gruppo TDS viene associato alla transazione.</span><span class="sxs-lookup"><span data-stu-id="3668b-124">**TDS** - If selected, a TDS group is attached to the transaction.</span></span>

<span data-ttu-id="3668b-125">I campi nelle schede **Panoramica**, **Generale** e **Rettifica** nella pagina **Transazioni ritenuta d'acconto temporanee** visualizza dettagli sull'importo TDS calcolato e sull'importo TDS rettificato per ogni codice imposta TDS associato al gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="3668b-125">The fields on the **Overview**, **General**, and **Adjustment** tabs on the **Temporary withholding tax transactions** page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

8. <span data-ttu-id="3668b-126">Seleziona **Soglia** per aprire la pagina **Soglia**.</span><span class="sxs-lookup"><span data-stu-id="3668b-126">Select **Threshold** to open the **Threshold** page.</span></span> <span data-ttu-id="3668b-127">Visualizza il limite di soglia definito per il componente fiscale TDS associato a un codice fiscale TDS specifico in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="3668b-127">View the threshold limit defined for the TDS tax component attached to a specific TDS tax code on this page.</span></span>

9. <span data-ttu-id="3668b-128">Seleziona **Designer formula** per aprire la pagina **Designer formula**.</span><span class="sxs-lookup"><span data-stu-id="3668b-128">Select **Formula designer** to open the **Formula designer** page.</span></span> <span data-ttu-id="3668b-129">Visualizza la formula definita per un codice imposta TDS specifico in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="3668b-129">View the formula that is defined for a specific TDS tax code on this page.</span></span> 

10. <span data-ttu-id="3668b-130">Registrare la fattura.</span><span class="sxs-lookup"><span data-stu-id="3668b-130">Post the invoice.</span></span> <span data-ttu-id="3668b-131">L'importo TDS calcolato sulle fatture di acquisto viene registrato in un conto fornitori e l'importo TDS calcolato sulle fatture di vendita viene registrato in un conto clienti per ogni codice imposta TDS nel gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="3668b-131">The TDS amount calculated on purchase invoices is posted to the payable account and the TDS amount calculated on sales invoices is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="3668b-132">I conti clienti o fornitori per i codici imposta TDS sono definiti nella pagina **Codici ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="3668b-132">The payable accounts or receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>

11. <span data-ttu-id="3668b-133">Seleziona il pulsante **Richiesta info** **> Fattura > pulsante Ritenuta d'acconto registrata** per aprire la pagina **Transazioni ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="3668b-133">Select **Inquiry** button **> Invoice > Posted withholding tax** button to open the **Withholding tax transactions** page.</span></span> <span data-ttu-id="3668b-134">Puoi visualizzare la percentuale totale utilizzata per calcolare la TDS per la transazione nel campo **Valore**.</span><span class="sxs-lookup"><span data-stu-id="3668b-134">You can view the total percentage used to calculate TDS for the transaction in the **Value** field.</span></span>

<span data-ttu-id="3668b-135">I campi nelle schede **Panoramica**, **Generale** e **Importo** nella pagina **Transazioni ritenuta d'acconto** visualizza le informazioni della TDS calcolata per la transazione.</span><span class="sxs-lookup"><span data-stu-id="3668b-135">The fields on the **Overview**, **General**, and **Amount** tabs on the **Withholding tax transactions** page display the information of TDS calculated for the transaction.</span></span> <span data-ttu-id="3668b-136">Visualizza le informazioni sul calcolo della TDS per ogni codice imposta TDS associato al gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="3668b-136">View the TDS calculation information for each TDS tax code attached to the TDS group.</span></span>
