---
title: Calcolo della TDS sulle fatture dalla pagina Fattura a testo libero
description: Questo argomento spiega come calcolare l'imposta dedotta all'origine (TDS) sulle fatture utilizzando la pagina Fattura a testo libero.
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
ms.openlocfilehash: 7d551a8ba6ba9ca282fd9de3fa7d7c7303e394ed
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023364"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a><span data-ttu-id="fa36a-103">Calcolo della TDS sulle fatture dalla pagina Fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="fa36a-103">TDS calculation on invoices from the Free text invoice page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fa36a-104">Questo argomento descrive come calcolare l'imposta dedotta all'origine (TDS) sulle fatture utilizzando la pagina **Fattura a testo libero**.</span><span class="sxs-lookup"><span data-stu-id="fa36a-104">This topic explains how to calculate Tax Deducted at Source (TDS) on invoices by using the **Free text invoice** page.</span></span>

1. <span data-ttu-id="fa36a-105">Passa a **Contabilità clienti \> Fatture \> Tutte le fatture a testo libero**.</span><span class="sxs-lookup"><span data-stu-id="fa36a-105">Go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>

    <span data-ttu-id="fa36a-106">[![Pagina della fattura a testo libero](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)</span><span class="sxs-lookup"><span data-stu-id="fa36a-106">[![Free text invoice page](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)</span></span>

2. <span data-ttu-id="fa36a-107">Seleziona **Nuovo** per creare una fattura a testo libero e immetti i dettagli richiesti.</span><span class="sxs-lookup"><span data-stu-id="fa36a-107">Select **New** to create a free text invoice, and enter the required details.</span></span>
3. <span data-ttu-id="fa36a-108">Seleziona la scheda **Fattura**. Nella sezione **Gruppo ritenute d'acconto**, il campo **Natura soggetto valutato** mostra la natura della categoria di soggetto valutato del cliente.</span><span class="sxs-lookup"><span data-stu-id="fa36a-108">Select the **Invoice** tab. In the **Withholding tax group** section, the **Nature of assessee** field shows the nature of assessee category of the customer.</span></span>
4. <span data-ttu-id="fa36a-109">Nel campo **Gruppo TDS**, esamina o modifica il gruppo TDS predefinito definito per il cliente.</span><span class="sxs-lookup"><span data-stu-id="fa36a-109">In the **TDS group** field, review or change the default TDS group that is defined for the customer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fa36a-110">Quando selezioni un valore nel campo **Gruppo TCS**, il campo **Gruppo TCS** non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="fa36a-110">When you select a value in the **TDS group** field, the **TCS group** field becomes unavailable.</span></span> <span data-ttu-id="fa36a-111">La TDS viene calcolata solo se l'opzione **Calcola ritenuta d'acconto** è impostata su **Sì** per il cliente nella pagina **Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="fa36a-111">TDS is calculated only if the **Calculate withholding tax** option is set to **Yes** for the customer on the **All customers** page.</span></span>

5. <span data-ttu-id="fa36a-112">Nella scheda **Informazioni fiscali**, nella sezione **Informazioni società**, nel campo **Nome**, seleziona il nome della società per un indirizzo alternativo impostato per la società.</span><span class="sxs-lookup"><span data-stu-id="fa36a-112">On the **Tax information** tab, in the **Company information** section, in the **Name** field, select the company name for an alternate address that has been set up for the company.</span></span>

    <span data-ttu-id="fa36a-113">Nella sezione **Ritenuta d'acconto**, il campo **Numero conto imposta (TAN)** mostra il numero di conto imposta (TAN) della società selezionata.</span><span class="sxs-lookup"><span data-stu-id="fa36a-113">In the **Withholding tax** section, the **Tax Account Number (TAN)** field shows the tax account number (TAN) for the selected company.</span></span>

6. <span data-ttu-id="fa36a-114">Nella scheda **Righe fattura**, crea righe fattura immetti i dettagli richiesti.</span><span class="sxs-lookup"><span data-stu-id="fa36a-114">On the **Invoice lines** tab, create invoice lines, and enter the required details.</span></span>

    <span data-ttu-id="fa36a-115">Nella sezione **Gruppo ritenute d'acconto**, il campo **Numero conto imposta (TAN)** mostra il TAN e il campo **Gruppo TDS** mostra il gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="fa36a-115">In the **Withholding tax group** section, the **Tax Account Number (TAN)** field shows the TAN, and the **TDS group** field shows the TDS group.</span></span>

7. <span data-ttu-id="fa36a-116">Seleziona **Ritenuta d'acconto** per aprire la pagina **Transazioni ritenuta d'acconto temporanee**.</span><span class="sxs-lookup"><span data-stu-id="fa36a-116">Select **Withholding tax** to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="fa36a-117">La parte superiore di questa pagina ha i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="fa36a-117">The upper part of this page has the following fields:</span></span>

    - <span data-ttu-id="fa36a-118">**Importo ritenuta d'acconto in totale** - La TDS totale calcolata per la transazione per il gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="fa36a-118">**Withholding tax amount in total** – The total TDS that was calculated for the transaction for the TDS group.</span></span>
    - <span data-ttu-id="fa36a-119">**Valore** - La percentuale totale utilizzata per calcolare la TDS per la transazione.</span><span class="sxs-lookup"><span data-stu-id="fa36a-119">**Value** – The total percentage that was used to calculate TDS for the transaction.</span></span> <span data-ttu-id="fa36a-120">La percentuale totale si basa sulla formula definita per i codici imposta TDS e associata al gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="fa36a-120">The total percentage is based on the formula that is defined for the TDS tax codes and attached to the TDS group.</span></span>
    - <span data-ttu-id="fa36a-121">**Importo ritenuta d'acconto rettificato in totale** - L'importo TDS rettificato totale per tutti i codici imposta nel gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="fa36a-121">**Adjusted withholding tax amount in total** – The total adjusted TDS amount for all tax codes in the TDS group.</span></span>
    - <span data-ttu-id="fa36a-122">**TDS** - Una casella di controllo selezionata indica che un gruppo TDS è associato alla transazione.</span><span class="sxs-lookup"><span data-stu-id="fa36a-122">**TDS** – A selected checkbox indicates that a TDS group is attached to the transaction.</span></span>

    <span data-ttu-id="fa36a-123">I campi nelle schede **Panoramica**, **Generale** e **Rettifica** mostrano l'importo TDS calcolato ei dettagli dell'importo TDS rettificato per ogni codice imposta TDS associato al gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="fa36a-123">The fields on the **Overview**, **General**, and **Adjustment** tabs show the calculated TDS amount and details of the adjusted TDS amount for each TDS tax code that is attached to the TDS group.</span></span>

8. <span data-ttu-id="fa36a-124">Seleziona **Soglia** per aprire la pagina **Soglia**, in cui è possibile esaminare il limite di soglia definito per il componente fiscale TDS associato a un codice fiscale TDS specifico.</span><span class="sxs-lookup"><span data-stu-id="fa36a-124">Select **Threshold** to open the **Threshold** page, where you can review the threshold limit that is defined for the TDS tax component that is attached to a specific TDS tax code.</span></span>
9. <span data-ttu-id="fa36a-125">Seleziona **Designer formula** per aprire la pagina **Designer formula**, in cui è possibile esaminare la formula definita per uno specifico codice imposta TDS.</span><span class="sxs-lookup"><span data-stu-id="fa36a-125">Select **Formula designer** to open the **Formula designer** page, where you can review the formula that is defined for a specific TDS tax code.</span></span>
10. <span data-ttu-id="fa36a-126">Registra la fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="fa36a-126">Post the free text invoice.</span></span> <span data-ttu-id="fa36a-127">L'importo TDS calcolato per la fattura a testo libero viene registrato nel conto clienti definito per ogni codice imposta TDS nel gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="fa36a-127">The TDS amount that is calculated for the free text invoice is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="fa36a-128">I conti clienti per i codici imposta TDS sono definiti nella pagina **Codici ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="fa36a-128">The receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>
11. <span data-ttu-id="fa36a-129">Seleziona **Ritenuta d'acconto registrata** per aprire la pagina **Transazioni ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="fa36a-129">Select **Posted withholding tax** to open the **Withholding tax transactions** page.</span></span> <span data-ttu-id="fa36a-130">Il campo **Valore** mostra la percentuale totale utilizzata per calcolare la TDS per la transazione.</span><span class="sxs-lookup"><span data-stu-id="fa36a-130">The **Value** field shows the total percentage that was used to calculate TDS for the transaction.</span></span>

    <span data-ttu-id="fa36a-131">I campi nelle schede **Panoramica**, **Generale** e **Importo** mostrano gli importi TDS calcolati sulle righe fattura.</span><span class="sxs-lookup"><span data-stu-id="fa36a-131">The fields on the **Overview**, **General**, and **Amount** tabs show the TDS amounts that were calculated on the invoice lines.</span></span>

12. <span data-ttu-id="fa36a-132">Esamina le informazioni sul calcolo della TDS per ogni codice imposta TDS associato al gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="fa36a-132">Review the TDS calculation information for each TDS tax code that is attached to the TDS group.</span></span>
