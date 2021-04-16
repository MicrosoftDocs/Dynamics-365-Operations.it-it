---
title: Ritenuta d'acconto in transazioni di vendita
description: Questo argomento elenca i passaggi per evitare il calcolo della ritenuta d'acconto per i clienti selezionati. Per i clienti che specificano la ritenuta d'acconto nei loro pagamenti, è possibile assegnare il gruppo di ritenuta d'acconto predefinito.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8e11ce10faa9b450b6f36a856b34b06b4ee1838d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842346"
---
# <a name="withholding-tax-in-sales-transactions"></a><span data-ttu-id="4b6d8-104">Ritenuta d'acconto in transazioni di vendita</span><span class="sxs-lookup"><span data-stu-id="4b6d8-104">Withholding tax in sales transactions</span></span>

<span data-ttu-id="4b6d8-105">Questo argomento elenca i passaggi per evitare il calcolo della ritenuta d'acconto per i clienti selezionati.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-105">This topic lists the steps for avoiding the calculation of withholding tax for selected customers.</span></span> <span data-ttu-id="4b6d8-106">Per i clienti che specificano la ritenuta d'acconto nei loro pagamenti, è possibile assegnare il **gruppo di ritenuta d'acconto** predefinito nella pagina **Clienti**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-106">For customers who specify withholding tax in their payments to you, you can assign the default **Withholding tax group** on the **Customers** page.</span></span> 

1. <span data-ttu-id="4b6d8-107">Vai a **Pannello di navigazione > Moduli > Contabilità clienti > Clienti > Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-107">Go to **Navigation pane > Modules > Accounts receivable > Customers > All customers**.</span></span>

2. <span data-ttu-id="4b6d8-108">Fai clic sul rispettivo conto cliente, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-108">Click the respective customer account, click **Edit**.</span></span>

3. <span data-ttu-id="4b6d8-109">Nella scheda **Fattura e consegna**, imposta il campo **Calcola ritenuta d'acconto** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-109">In the **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="4b6d8-110">La ritenuta d'acconto non sarà calcolata se **Calcola ritenuta d'acconto** non è attivata per questo cliente nei dati master.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-110">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this customer in the master data.</span></span>

4. <span data-ttu-id="4b6d8-111">Seleziona un gruppo ritenuta d'acconto in **Gruppo ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-111">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="4b6d8-112">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-112">Click **Save**.</span></span>

<span data-ttu-id="4b6d8-113">Per articoli/servizi soggetti a ritenuta d'acconto puoi assegnare l'impostazione predefinita **Gruppo ritenuta d'acconto articolo** in **Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-113">For items/services, which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="4b6d8-114">Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-114">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="4b6d8-115">Fai clic sul rispettivo numero articolo, quindi su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-115">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="4b6d8-116">Nella scheda **Vendi**, fai clic su **Calcola ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-116">In the **Sell** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="4b6d8-117">La ritenuta d'acconto non sarà calcolata se **Calcola ritenuta d'acconto** non è impostata su **Sì** per questo articolo nella scheda **Vendita** nella pagina **Prodotto rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-117">Withholding tax will not be calculated if **Calculate withholding tax** is not set to **Yes** for this Item in the **Sell** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="4b6d8-118">Seleziona un gruppo ritenuta d'acconto articolo nell'elenco **Gruppo ritenuta d'acconto articolo**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-118">Select an Item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="4b6d8-119">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-119">Click **Save**.</span></span>

<span data-ttu-id="4b6d8-120">I gruppi di ritenute d'acconto e ritenute d'acconto articoli possono essere assegnati utilizzando la pagina **Ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-120">Withholding tax groups and Item withholding tax groups can be assigned using the **Sales order** page.</span></span> 

<span data-ttu-id="4b6d8-121">Il Gruppo ritenute d'acconto e il Gruppo ritenuta d'acconto articolo predefiniti verranno utilizzati come voci predefinite nelle righe ordini di vendita quando si crea un nuovo ordine di vendita.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-121">The default Withholding tax group and Item withholding tax group will be used as default entries on sales order lines when you create a new sales order.</span></span>

<span data-ttu-id="4b6d8-122">La ritenuta d'acconto viene calcolata e registrata con **Giornale di registrazione pagamenti cliente**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-122">Withholding tax is calculated and posted with **Customer payment journal**.</span></span> <span data-ttu-id="4b6d8-123">Puoi modificare manualmente il codice della ritenuta d'acconto applicabile, nonché l'importo effettivo della ritenuta d'acconto nella scheda **Ritenuta d'acconto** nella pagina **Liquida transazioni**.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-123">You can manually adjust the applicable withholding tax code, as well as the actual withholding tax amount in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

<span data-ttu-id="4b6d8-124">L'importo della ritenuta d'acconto calcolato verrà detratto dal pagamento del cliente e registrato nel conto **Compensazione della ritenuta d'acconto** in un voucher correlato.</span><span class="sxs-lookup"><span data-stu-id="4b6d8-124">The calculated withholding tax amount will be deducted from the customer payment and posted to the **Withholding tax offset** account in a related voucher.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]