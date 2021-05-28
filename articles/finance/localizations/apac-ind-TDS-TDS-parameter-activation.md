---
title: Impostare i parametri TDS
description: Questo argomento descrive come impostare i parametri per attivare la funzionalità TDS nelle transazioni specificate. Questo è un passaggio necessario per utilizzare la funzionalità TDS.
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
ms.openlocfilehash: dda276b7d634317aae26728f7d9f51af9ccfb896
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023356"
---
# <a name="set-the-tds-parameters"></a><span data-ttu-id="5673d-104">Impostare i parametri TDS</span><span class="sxs-lookup"><span data-stu-id="5673d-104">Set the TDS parameters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5673d-105">Questo argomento descrive come impostare i parametri per attivare la funzionalità TDS nelle transazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="5673d-105">This topic explains how to set parameters to activate Tax Deducted at Source (TDS) functionality in specified transactions.</span></span> <span data-ttu-id="5673d-106">Questo è un passaggio necessario per utilizzare la funzionalità TDS.</span><span class="sxs-lookup"><span data-stu-id="5673d-106">This is a necessary step to use the Tax Deducted at Source TDS feature.</span></span>

1. <span data-ttu-id="5673d-107">Passa a **Contabilità generale \> Impostazione contabilità generale \> Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="5673d-107">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="5673d-108">Nella scheda **Imposte dirette**, nella sezione **Imposta dedotta all'origine**, imposta l'opzione **TDS attiva** su **Sì** per attivare la funzionalità TDS e le relative pagine e campi.</span><span class="sxs-lookup"><span data-stu-id="5673d-108">On the **Direct taxes** tab, in the **Tax Deducted at Source** section, set the **Activate TDS** option to **Yes** to activate the TDS functionality, and the pages and fields that are used for it.</span></span>
3. <span data-ttu-id="5673d-109">Imposta l'opzione **Fattura** su **Sì** per attivare i campi utilizzati per calcolare e detrarre la TDS a livello di fattura.</span><span class="sxs-lookup"><span data-stu-id="5673d-109">Set the **Invoice** option to **Yes** to activate the fields that are used to calculate and deduct TDS at the invoice level.</span></span>
4. <span data-ttu-id="5673d-110">Imposta l'opzione **Pagamento** su **Sì** per attivare i campi utilizzati per calcolare e detrarre la TDS a livello di pagamento.</span><span class="sxs-lookup"><span data-stu-id="5673d-110">Set the **Payment** option to **Yes** to activate the fields that are used to calculate and deduct TDS at the payment level.</span></span>

    <span data-ttu-id="5673d-111">[![Scheda Imposte dirette](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)</span><span class="sxs-lookup"><span data-stu-id="5673d-111">[![Direct taxes tab](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)</span></span>

5. <span data-ttu-id="5673d-112">Nella scheda **Sequenze numeriche**, trova la riga in cui il campo **Riferimento** è impostato su **Pagamento ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="5673d-112">On the **Number sequences** tab, find the row where the **Reference** field is set to **Withholding tax payment**.</span></span> <span data-ttu-id="5673d-113">Nel campo **Codice sequenza numerica** della riga, seleziona il codice di sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="5673d-113">In the **Number sequence code** field for the row, select the number sequence code.</span></span> <span data-ttu-id="5673d-114">Il codice di sequenza numerica è utilizzato per generare i numeri di giustificativo per il processo di liquidazione TDS periodica.</span><span class="sxs-lookup"><span data-stu-id="5673d-114">The number sequence code is used to generate voucher numbers for the periodic TDS settlement process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5673d-115">Per eseguire il processo di liquidazione TDS periodico, vai a **Imposta \> Dichiarazioni \> Ritenuta d'acconto \> Pagamento ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="5673d-115">To run the periodic TDS settlement process, go to **Tax \> Declarations \> Withholding tax \> Withholding tax payment**.</span></span>

    <span data-ttu-id="5673d-116">[![Scheda Sequenze numeriche](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)</span><span class="sxs-lookup"><span data-stu-id="5673d-116">[![Number sequences tab](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)</span></span>

6. <span data-ttu-id="5673d-117">Chiudi la pagina.</span><span class="sxs-lookup"><span data-stu-id="5673d-117">Close the page.</span></span>
