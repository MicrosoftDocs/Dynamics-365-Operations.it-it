---
title: Impostare periodi di liquidazione della ritenuta d'acconto per il tipo di imposta TDS
description: Questo argomento descrive come impostare i periodi di liquidazione dell'imposta dedotta all'origine (TDS, Tax Deducted at Source).
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
ms.openlocfilehash: 9430bc1386f127d02b598d6cad1b53f66e0cf2ba
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023345"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a><span data-ttu-id="0446c-103">Impostare periodi di liquidazione della ritenuta d'acconto per il tipo di imposta TDS</span><span class="sxs-lookup"><span data-stu-id="0446c-103">Set up withholding tax settlement periods for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0446c-104">Questo argomento descrive come impostare i periodi di liquidazione dell'imposta dedotta all'origine (TDS, Tax Deducted at Source).</span><span class="sxs-lookup"><span data-stu-id="0446c-104">This topic explains how to set up settlement periods for Tax Deducted at Source (TDS) settlement periods.</span></span>

1. <span data-ttu-id="0446c-105">Vai a **Imposta \> Imposte indirette \> Ritenuta d'acconto \> Periodi liquidazione ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="0446c-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax settlement periods**.</span></span>

    <span data-ttu-id="0446c-106">[![Pagina Periodi liquidazione ritenuta d'acconto](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)</span><span class="sxs-lookup"><span data-stu-id="0446c-106">[![Withholding tax settlement periods page](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)</span></span>

2. <span data-ttu-id="0446c-107">Nel campo **Tipo di imposta**, seleziona **TDS** per impostare i periodi di liquidazione della ritenuta d'acconto per il tipo di imposta TDS.</span><span class="sxs-lookup"><span data-stu-id="0446c-107">In the **Tax type** field, select **TDS** to set up withholding tax settlement periods for the TDS tax type.</span></span>
3. <span data-ttu-id="0446c-108">Seleziona **Nuovo** per creare una riga.</span><span class="sxs-lookup"><span data-stu-id="0446c-108">Select **New** to create a line.</span></span>
4. <span data-ttu-id="0446c-109">Nel campo **Periodo di liquidazione** immetti un nome per il periodo di liquidazione TDS.</span><span class="sxs-lookup"><span data-stu-id="0446c-109">In the **Settlement period** field, enter a name for the TDS settlement period.</span></span>
5. <span data-ttu-id="0446c-110">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="0446c-110">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="0446c-111">Nel campo **Ufficio tributario ritenuta d'acconto**, seleziona l'autorità TDS per cui stai definendo il periodo di liquidazione TDS.</span><span class="sxs-lookup"><span data-stu-id="0446c-111">In the **Withholding tax authority** field, select the TDS authority that you're defining the TDS settlement period for.</span></span>
7. <span data-ttu-id="0446c-112">Nella Scheda dettaglio **Generale** nel campo **Intervallo periodico** seleziona il tipo di intervallo periodico per il periodo di liquidazione TDS.</span><span class="sxs-lookup"><span data-stu-id="0446c-112">On the **General** FastTab, in the **Period interval** field, select the type of period interval for the TDS settlement period.</span></span>
8. <span data-ttu-id="0446c-113">Nel campo **Numero di unità**, specifica il numero di unità per il tipo di intervallo periodico.</span><span class="sxs-lookup"><span data-stu-id="0446c-113">In the **Number of units** field, specify the number of units for the period interval type.</span></span>
9. <span data-ttu-id="0446c-114">Nella Scheda dettaglio **Periodi**, nel campo **Data iniziale** seleziona la data iniziale del periodo di liquidazione TDS.</span><span class="sxs-lookup"><span data-stu-id="0446c-114">On the **Periods** FastTab, in the **From date** field, select the start date for the TDS settlement period.</span></span> <span data-ttu-id="0446c-115">Nel campo **Data finale** seleziona una data di fine.</span><span class="sxs-lookup"><span data-stu-id="0446c-115">In the **To date** field, select the end date.</span></span>
10. <span data-ttu-id="0446c-116">Per creare un periodo di liquidazione TDS successivo per un periodo esistente, in base all'intervallo periodico e alle unità del periodo, seleziona **Nuovo periodo**.</span><span class="sxs-lookup"><span data-stu-id="0446c-116">To create a subsequent TDS settlement period for an existing period, based on the period interval and period units, select **New period**.</span></span>
11. <span data-ttu-id="0446c-117">Per visualizzare i dettagli della liquidazione TDS periodica eseguita per uno specifico periodo di liquidazione, seleziona **Pagamento ritenuta d'acconto** per aprire la pagina **Pagamento ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="0446c-117">To view the details of the periodic TDS settlement that is run for a specific settlement period, select **Withholding tax payments** to open the **Withholding tax payment** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0446c-118">Per eseguire il processo di liquidazione TDS periodico, vai a **Contabilità generale \> Periodico \> Ritenuta d'acconto \> Pagamento ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="0446c-118">To run the periodic TDS settlement process, go to **General ledger \> Periodic \> Withholding tax \> Withholding tax payment**.</span></span>

    <span data-ttu-id="0446c-119">[![Pagina Pagamento ritenuta d'acconto](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)</span><span class="sxs-lookup"><span data-stu-id="0446c-119">[![Withholding tax payment page](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)</span></span>

12. <span data-ttu-id="0446c-120">Chiudi la pagina.</span><span class="sxs-lookup"><span data-stu-id="0446c-120">Close the page.</span></span>
