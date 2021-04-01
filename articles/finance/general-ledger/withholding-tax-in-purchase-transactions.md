---
title: Ritenuta d'acconto in transazioni di acquisto
description: Per i fornitori soggetti a ritenuta d'acconto, puoi assegnare il **gruppo di ritenuta d'acconto** predefinito nella pagina **Tutti i fornitori**.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
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
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 06c18e6b0779539a6da7ae7afbe000c4cfc78d9e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256669"
---
# <a name="withholding-tax-in-purchase-transactions"></a><span data-ttu-id="57bed-103">Ritenuta d'acconto in transazioni di acquisto</span><span class="sxs-lookup"><span data-stu-id="57bed-103">Withholding tax in purchase transactions</span></span>

<span data-ttu-id="57bed-104">Per i fornitori soggetti a ritenuta d'acconto, puoi assegnare il **gruppo di ritenuta d'acconto** predefinito nella pagina **Tutti i fornitori**.</span><span class="sxs-lookup"><span data-stu-id="57bed-104">For vendors who are liable to withholding tax, you can assign the default **Withholding tax group** on the **All vendors** page.</span></span>

1. <span data-ttu-id="57bed-105">Vai a **Pannello di navigazione > Moduli > Contabilità fornitori > Fornitori > Tutti i fornitori**.</span><span class="sxs-lookup"><span data-stu-id="57bed-105">Go to **Navigation pane > Modules > Accounts payable > Vendors > All vendors**.</span></span>

2. <span data-ttu-id="57bed-106">Fai clic sul rispettivo conto fornitore, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="57bed-106">Click the respective Vendor account, click **Edit**.</span></span>

3. <span data-ttu-id="57bed-107">Nella scheda **Fattura e consegna**, imposta il campo **Calcola ritenuta d'acconto** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="57bed-107">In **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="57bed-108">La ritenuta d'acconto non sarà calcolata se **Calcola ritenuta d'acconto** non è attivata per questo fornitore nei dati.</span><span class="sxs-lookup"><span data-stu-id="57bed-108">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this vendor in the data.</span></span>

4. <span data-ttu-id="57bed-109">Seleziona un gruppo ritenuta d'acconto in **Gruppo ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="57bed-109">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="57bed-110">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="57bed-110">Click **Save**.</span></span>

<span data-ttu-id="57bed-111">Per articoli/servizi soggetti a ritenuta d'acconto puoi assegnare l'impostazione predefinita **Gruppo ritenuta d'acconto articolo** in **Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="57bed-111">For items/services which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="57bed-112">Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="57bed-112">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="57bed-113">Fai clic sul rispettivo numero articolo, quindi su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="57bed-113">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="57bed-114">Nella scheda **Acquisto**, fai clic su **Calcola ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="57bed-114">In **Purchase** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="57bed-115">La ritenuta d'acconto non sarà calcolata se **Calcola ritenuta d'acconto** non è impostata su **Sì** per questo articolo nella scheda **Acquisto** nella pagina **Prodotto rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="57bed-115">Withholding tax will not be calculated if **Calculate withholding tax** isn't set to **Yes** for this Item in the **Purchase** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="57bed-116">Seleziona un gruppo ritenuta d'acconto articolo nell'elenco **Gruppo ritenuta d'acconto articolo**.</span><span class="sxs-lookup"><span data-stu-id="57bed-116">Select an item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="57bed-117">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="57bed-117">Click **Save**.</span></span>

<span data-ttu-id="57bed-118">I gruppi di ritenute d'acconto e ritenute d'acconto articoli possono essere assegnati nelle pagine:</span><span class="sxs-lookup"><span data-stu-id="57bed-118">Withholding tax groups and Item withholding tax groups can be assigned in pages:</span></span> 

- <span data-ttu-id="57bed-119">**Ordine fornitore**</span><span class="sxs-lookup"><span data-stu-id="57bed-119">**Purchase order**</span></span>
- <span data-ttu-id="57bed-120">**Fattura fornitore**</span><span class="sxs-lookup"><span data-stu-id="57bed-120">**Vendor invoice**</span></span>
- <span data-ttu-id="57bed-121">**Giornale di registrazione fatture**</span><span class="sxs-lookup"><span data-stu-id="57bed-121">**Invoice journal**</span></span>

<span data-ttu-id="57bed-122">Il gruppo ritenuta d'acconto e gruppo ritenuta d'acconto articolo predefiniti verranno riportati nelle righe durante la creazione **Ordini di acquisto** e/o **Fatture fornitore in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="57bed-122">The default Withholding tax group and Item withholding tax group will be carried into the lines when creating **Purchase orders** and/or **Pending Vendor invoices**.</span></span> <span data-ttu-id="57bed-123">Per **Giornale di registrazione fatture**, puoi cambiare **Calcola ritenuta d'acconto** e seleziona **Gruppo ritenuta d'acconto articolo** nella scheda **Generale** del giornale.</span><span class="sxs-lookup"><span data-stu-id="57bed-123">For **Vendor invoice journal**, you can switch on **Calculate withholding tax** and select **Item withholding tax group** in the **General** tab in the journal.</span></span>

<span data-ttu-id="57bed-124">L'importo temporaneo della ritenuta d'acconto è disponibile nel campo **Ritenuta d'acconto rettificata** della scheda **Totali** nella pagina **Ordine d'acquisto**.</span><span class="sxs-lookup"><span data-stu-id="57bed-124">The temporary amount of withholding tax is available in the field **Adjusted withholding tax** of the **Totals** tab on the **Purchase order** page.</span></span>

![La ritenuta d'acconto è inclusa nell'ordine d'acquisto](media/withholding-tax-adjusted.png)

<span data-ttu-id="57bed-126">La ritenuta d'acconto viene calcolata su **Giornale di registrazione pagamenti fornitore**.</span><span class="sxs-lookup"><span data-stu-id="57bed-126">Withholding tax is calculated on **Vendor payment journal**.</span></span> <span data-ttu-id="57bed-127">Puoi modificare manualmente i codici della ritenuta d'acconto applicabile, nonché gli importi effettivi della ritenuta d'acconto nella scheda **Ritenuta d'acconto** nella pagina **Liquida transazioni**.</span><span class="sxs-lookup"><span data-stu-id="57bed-127">You can manually adjust the applicable withholding tax codes as well as the actual withholding tax amounts in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

![La ritenuta può essere regolata manualmente nella pagina Liquidazione transazioni](media/withholding-tax-vendor-payment-tab.png)

<span data-ttu-id="57bed-129">L'importo della ritenuta d'acconto derivato verrà detratto dal pagamento del fornitore e registrato nel conto **Conto della ritenuta d'acconto** in un voucher correlato.</span><span class="sxs-lookup"><span data-stu-id="57bed-129">The derived withholding tax amount will be deducted from the vendor payment and posted to the **Withholding tax account** in a related voucher.</span></span>

![Conto ritenuta d'acconto con relativo giustificativo](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]