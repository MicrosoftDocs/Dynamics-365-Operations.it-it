---
title: Fatturazione note di accredito (Italia)
description: In questo argomento viene descritto come impostare e utilizzare la funzionalità di fatturazione delle note di accredito in Italia.
author: LizaGolub
manager: AnnBe
ms.date: 09/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxYearlyCom_IT, TaxAuthority, TaxPeriod
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 269664
ms.assetid: af07d122-5694-4de6-96bf-7bf5478b0175
ms.search.region: Italy
ms.author: sndray
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9c9c0ba97b7b7ea1e9eba2398bb67bb445a76bcf
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175785"
---
# <a name="credit-invoicing-italy"></a><span data-ttu-id="c44c2-103">Fatturazione delle note di accredito (Italia)</span><span class="sxs-lookup"><span data-stu-id="c44c2-103">Credit invoicing (Italy)</span></span>

[!include [banner](../includes/banner.md)]

## <a name="activate-credit-invoicing"></a><span data-ttu-id="c44c2-104">Attivare la fatturazione delle note di accredito</span><span class="sxs-lookup"><span data-stu-id="c44c2-104">Activate credit invoicing</span></span>

<span data-ttu-id="c44c2-105">Per attivare la funzionalità di fatturazione delle note di accredito nel modulo **Contabilità fornitori**, passare a **Contabilità fornitori** \> **Impostazione** \> **Parametri**, quindi nella scheda **Aggiornamenti**, selezionare la casella di controllo **Fatturazione note di accredito**.</span><span class="sxs-lookup"><span data-stu-id="c44c2-105">To activate the credit invoicing functionality in the **Accounts payable** module, go to **Accounts payable** \> **Setup** \> **Parameters**, and then, on the **Updates** tab, select the **Credit invoicing** check box.</span></span>

<span data-ttu-id="c44c2-106">Per attivare la funzionalità di fatturazione nel modulo **Contabilità clienti**, passare a **Contabilità clienti** \> **Impostazione** \> **Parametri**, quindi nella scheda **Aggiornamenti**, selezionare la casella di controllo **Fatturazione note di accredito**.</span><span class="sxs-lookup"><span data-stu-id="c44c2-106">To activate the functionality in the **Accounts receivable** module, go to **Accounts receivable** \> **Setup** \> **Parameters**, and then, on the **Updates** tab, select the **Credit invoicing** check box.</span></span>

## <a name="find-the-credit-invoicing-button"></a><span data-ttu-id="c44c2-107">Individuare il pulsante Fatturazione note di accredito</span><span class="sxs-lookup"><span data-stu-id="c44c2-107">Find the Credit invoicing button</span></span>

<span data-ttu-id="c44c2-108">Nel modulo **Contabilità generale**, passare a **Scritture contabili** \> **Giornale di registrazione generale**, selezionare **Righe**, quindi nel riquadro azioni, selezionare **Funzioni** \> **Fatturazione note di accredito**.</span><span class="sxs-lookup"><span data-stu-id="c44c2-108">In the **General ledger** module, go to **Journal entries** \> **General journal**, select **Lines**, and then, on the Action Pane, select **Functions** \> **Credit invoicing**.</span></span>

![Pagina Righe giornale di registrazione generale con l'opzione Fatturazione note di accredito](./media/ita-credit-invoicing-gl.png)

<span data-ttu-id="c44c2-110">Nel modulo **Contabilità clienti**, passare a **Fatture** \> **Tutte le fatture a testo libero**, quindi nel riquadro azioni, nella scheda **Fattura**, nel gruppo **Funzioni**, selezionare **Fatturazione note di accredito**.</span><span class="sxs-lookup"><span data-stu-id="c44c2-110">In the **Accounts receivable** module, go to **Invoices** \> **All free text invoices**, and then, on the Action Pane, on the **Invoice** tab, in the **Functions** group, select **Credit invoicing**.</span></span>

![Pagina Tutte le fatture a testo libero con l'opzione Fatturazione note di accredito](./media/ita-credit-invoicing-fti.png)

<span data-ttu-id="c44c2-112">Nel modulo **Contabilità clienti**, passare a **Ordini** \> **Tutti gli ordini cliente**, quindi nel riquadro azioni, nella scheda **Fattura**, nel gruppo **Correzione**, selezionare **Fatturazione note di accredito**.</span><span class="sxs-lookup"><span data-stu-id="c44c2-112">In the **Accounts receivable** module, go to **Orders** \> **All sales orders**, and then, on the Action Pane, on the **Invoice** tab, in the **Correction** group, select **Credit invoicing**.</span></span>

![Pagina Tutti gli ordini cliente con l'opzione Fatturazione note di accredito](./media/ita-credit-invoicing-so.png)

<span data-ttu-id="c44c2-114">Nel modulo **Contabilità fornitori**, passare a **Fatture** \> **Giornale di registrazione fatture**, selezionare **Righe**, quindi nel riquadro azioni, selezionare **Funzioni** \> **Fatturazione note di accredito**.</span><span class="sxs-lookup"><span data-stu-id="c44c2-114">In the **Accounts payable** module, go to **Invoices** \> **Invoice journal**, select **Lines**, and then, on the Action Pane, select **Functions** \> **Credit invoicing**.</span></span>

![Pagina Righe giornale di registrazione fatture con l'opzione Fatturazione note di accredito](./media/ita-credit-invoicing-apij.png)

<span data-ttu-id="c44c2-116">Nel modulo **Contabilità fornitori**, passare a **Ordini fornitore** \> **Tutti gli ordini fornitore**, quindi nel riquadro azioni, nella scheda **Fattura**, nel gruppo **Introduci**, selezionare **Fatturazione note di accredito**.</span><span class="sxs-lookup"><span data-stu-id="c44c2-116">In the **Accounts payable** module, go to **Purchase orders** \> **All purchase orders**, and then, on the Action Pane, on the **Invoice** tab, in the **Introduce** group, select **Credit invoicing**.</span></span>

![Pagina Tutti gli ordini fornitore con la pagina Fatturazione note di accredito](./media/ita-credit-invoicing-po.png)
