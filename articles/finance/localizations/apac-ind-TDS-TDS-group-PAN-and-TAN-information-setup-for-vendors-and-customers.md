---
title: Impostare informazioni su gruppo TDS, PAN e TAN per clienti e fornitori
description: In questo argomento viene illustrato come impostare le informazioni sul gruppo TDS (Tax Deducted at Source, imposta dedotta all'origine), PAN (Permanent Account Number, numero di conto permanente) e TAN (Tax Account Number, numero di conto imposta) per fornitori e clienti.
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
ms.openlocfilehash: fd33b1775afefed798f1e9bb7601f4112222c430
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023359"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a><span data-ttu-id="4015a-103">Impostazione delle informazioni su gruppo TDS, PAN e TAN per clienti e fornitori</span><span class="sxs-lookup"><span data-stu-id="4015a-103">TDS group, PAN, and TAN information setup for vendors and customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4015a-104">In questo argomento viene illustrato come impostare le informazioni sul gruppo TDS (Tax Deducted at Source, imposta dedotta all'origine), PAN (Permanent Account Number, numero di conto permanente) e TAN (Tax Account Number, numero di conto imposta) per fornitori e clienti.</span><span class="sxs-lookup"><span data-stu-id="4015a-104">This topic explains how to set up information about the Tax Deducted at Source (TDS) group, permanent account number (PAN), and tax account number (TAN) for vendors and customers.</span></span>

1. <span data-ttu-id="4015a-105">Andare a **Contabilità fornitori \> Fornitori \> Tutti i fornitori** o **Contabilità clienti \> Clienti \> Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="4015a-105">Go to **Accounts payable \> Vendors \> All vendors** or **Accounts receivable \> Customers \> All customers**.</span></span>

    <span data-ttu-id="4015a-106">[![Pagina Tutti i fornitori](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)</span><span class="sxs-lookup"><span data-stu-id="4015a-106">[![All vendors page](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)</span></span>

2. <span data-ttu-id="4015a-107">Nel riquadro azioni selezionare **Nuovo** per creare un fornitore o un cliente e immettere i dettagli necessari.</span><span class="sxs-lookup"><span data-stu-id="4015a-107">On the Action Pane, select **New** to create a vendor or customer, and enter the required details.</span></span> <span data-ttu-id="4015a-108">In alternativa, selezionare un fornitore o un cliente esistente.</span><span class="sxs-lookup"><span data-stu-id="4015a-108">Alternatively, select an existing vendor or customer.</span></span>
3. <span data-ttu-id="4015a-109">Nella Scheda dettaglio **Fattura e consegna**, nella sezione **Ritenuta d'acconto**, impostare l'opzione **Calcola ritenuta d'acconto** su **Sì** per calcolare la ritenuta d'acconto, la TDS o la TCS del fornitore o del cliente.</span><span class="sxs-lookup"><span data-stu-id="4015a-109">On the **Invoice and delivery** FastTab, in the **Withholding tax** section, set the **Calculate withholding tax** option to **Yes** to calculate withholding tax, TDS, or Tax Collected at Source (TCS) for the vendor or customer.</span></span>
4. <span data-ttu-id="4015a-110">La TDS per una fattura di acquisto viene calcolata in base al gruppo TDS predefinito definito per il fornitore o il cliente.</span><span class="sxs-lookup"><span data-stu-id="4015a-110">TDS for a purchase invoice is calculated based on the default TDS group that is defined for the vendor or customer.</span></span> <span data-ttu-id="4015a-111">Nel campo **Gruppo TDS**, selezionare il gruppo TDS predefinito.</span><span class="sxs-lookup"><span data-stu-id="4015a-111">In the **TDS group** field, select the default TDS group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4015a-112">Quando si seleziona un gruppo TDS nel campo **Gruppo TDS**, i campi **Gruppo ritenute d'acconto** e **Gruppo TCS** non sono più disponibili.</span><span class="sxs-lookup"><span data-stu-id="4015a-112">When you select a TDS group in the **TDS group** field, the **Withholding tax group** and **TCS group** fields become unavailable.</span></span>

5. <span data-ttu-id="4015a-113">Nella Scheda dettaglio **Informazioni fiscali**, nella sezione **Informazioni PAN**, nel campo **Stato** selezionare lo stato del numero di conto permanente per il fornitore o il cliente:</span><span class="sxs-lookup"><span data-stu-id="4015a-113">On the **Tax information** FastTab, in the **PAN information** section, in the **Status** field, select the status of the permanent account number for the vendor or customer:</span></span>

    - <span data-ttu-id="4015a-114">**Non disponibile** - Il venditore o il cliente non dispone di un PAN.</span><span class="sxs-lookup"><span data-stu-id="4015a-114">**Not available** – The vendor or customer doesn't have a PAN.</span></span>
    - <span data-ttu-id="4015a-115">**Ricevuto** - Il venditore o il cliente ha un PAN.</span><span class="sxs-lookup"><span data-stu-id="4015a-115">**Received** – The vendor or customer has a PAN.</span></span>
    - <span data-ttu-id="4015a-116">**Richiesto** - Il venditore o il cliente ha richiesto un PAN.</span><span class="sxs-lookup"><span data-stu-id="4015a-116">**Applied** – The vendor or customer has applied for a PAN.</span></span>
    - <span data-ttu-id="4015a-117">**Non valido** - Il venditore o il cliente ha un PAN, ma non è valido.</span><span class="sxs-lookup"><span data-stu-id="4015a-117">**Invalid** – The vendor or customer has a PAN, but it isn't valid.</span></span>

6. <span data-ttu-id="4015a-118">Se si è selezionato **Ricevuto** nel campo **Stato** per indicare che il fornitore o il cliente ha un PAN, immettere il PAN nel campo **Numero**.</span><span class="sxs-lookup"><span data-stu-id="4015a-118">If you selected **Received** in the **Status** field to indicate that the vendor or customer has a PAN, enter the PAN in the **Number** field.</span></span> <span data-ttu-id="4015a-119">Il PAN deve essere composto da cinque caratteri alfabetici, quattro caratteri numerici e un carattere alfabetico.</span><span class="sxs-lookup"><span data-stu-id="4015a-119">The PAN must consist of five alphabetic characters, then four numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="4015a-120">Ad esempio: **ABCDE1260A**.</span><span class="sxs-lookup"><span data-stu-id="4015a-120">Here is an example: **ABCDE1260A**.</span></span>
7. <span data-ttu-id="4015a-121">Se si è selezionato **Richiesto** nel campo **Stato** per indicare che il fornitore o il cliente ha richiesto un PAN, immettere il numero di riferimento nel campo **Numero di riferimento**.</span><span class="sxs-lookup"><span data-stu-id="4015a-121">If you selected **Applied** in the **Status** field to indicate that the vendor or customer has applied for PAN, enter the reference number in the **Reference number** field.</span></span>
8. <span data-ttu-id="4015a-122">Nel campo **Natura soggetto valutato** selezionare la natura della categoria di soggetto valutato a cui appartiene il fornitore o il cliente:</span><span class="sxs-lookup"><span data-stu-id="4015a-122">In the **Nature of assessee** field, select the nature of assessee category that the vendor or customer belongs to:</span></span>

    - <span data-ttu-id="4015a-123">Società</span><span class="sxs-lookup"><span data-stu-id="4015a-123">Company</span></span>
    - <span data-ttu-id="4015a-124">HUF</span><span class="sxs-lookup"><span data-stu-id="4015a-124">HUF</span></span>
    - <span data-ttu-id="4015a-125">Stabilizza</span><span class="sxs-lookup"><span data-stu-id="4015a-125">Firm</span></span>
    - <span data-ttu-id="4015a-126">Singolo</span><span class="sxs-lookup"><span data-stu-id="4015a-126">Individual</span></span>
    - <span data-ttu-id="4015a-127">AOP</span><span class="sxs-lookup"><span data-stu-id="4015a-127">AOP</span></span>
    - <span data-ttu-id="4015a-128">BOI</span><span class="sxs-lookup"><span data-stu-id="4015a-128">BOI</span></span>
    - <span data-ttu-id="4015a-129">Autorità locale</span><span class="sxs-lookup"><span data-stu-id="4015a-129">Local authority</span></span>
    - <span data-ttu-id="4015a-130">Altro</span><span class="sxs-lookup"><span data-stu-id="4015a-130">Others</span></span>

    <span data-ttu-id="4015a-131">[![Scheda dettaglio Informazioni fiscali](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)</span><span class="sxs-lookup"><span data-stu-id="4015a-131">[![Tax information FastTab](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)</span></span>

9. <span data-ttu-id="4015a-132">Nel riquadro azioni, nella scheda **Fornitore**, nel gruppo **Registrazione** , selezionare **ID registrazione** per aprire la pagina **Gestisci indirizzi**.</span><span class="sxs-lookup"><span data-stu-id="4015a-132">On the Action Pane, on the **Vendor** tab, in the **Registration** group, select **Registration IDs** to open the **Manage addresses** page.</span></span>
10. <span data-ttu-id="4015a-133">Nella pagina **Gestisci indirizzi**, nella Scheda dettaglio **Informazioni fiscali**, selezionare **Aggiungi** o **Modifica** per aprire la pagina **Gestisci informazioni fiscali**, in cui è possibile mantenere la voce di registrazione fiscale.</span><span class="sxs-lookup"><span data-stu-id="4015a-133">On the **Manage addresses** page, on the **Tax information** FastTab, select **Add** or **Edit** to open the **Manage tax information** page, where you can maintain the tax registration entry.</span></span>
11. <span data-ttu-id="4015a-134">Nella pagina **Gestisci informazioni fiscali**, nella Scheda dettaglio **Ritenuta d'acconto**, nel campo **Numero conto imposta (TAN)**, immettere il TAN.</span><span class="sxs-lookup"><span data-stu-id="4015a-134">On the **Manage tax information** page, on the **Withholding tax** FastTab, in the **Tax Account Number (TAN)** field, enter the TAN.</span></span> <span data-ttu-id="4015a-135">Il TAN deve essere composto da quattro caratteri alfabetici, cinque caratteri numerici e un carattere alfabetico.</span><span class="sxs-lookup"><span data-stu-id="4015a-135">The TAN must consist of four alphabetic characters, then five numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="4015a-136">Ad esempio: **AFGH54821T**.</span><span class="sxs-lookup"><span data-stu-id="4015a-136">Here is an example: **AFGH54821T**.</span></span>
12. <span data-ttu-id="4015a-137">Chiudi la pagina.</span><span class="sxs-lookup"><span data-stu-id="4015a-137">Close the page.</span></span>
