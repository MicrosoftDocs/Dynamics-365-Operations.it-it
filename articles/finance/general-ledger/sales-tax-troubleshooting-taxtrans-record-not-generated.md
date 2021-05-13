---
title: Il record TaxTrans non viene generato
description: Questo argomento fornisce informazioni sulla risoluzione dei problemi che possono essere utili quando un record TaxTrans non viene generato.
author: qire
manager: beya
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 0c7414cc39198ff4d5be9b4c41ca62f9c78c9250
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947661"
---
# <a name="taxtrans-record-isnt-generated"></a><span data-ttu-id="e65f5-103">Il record TaxTrans non viene generato</span><span class="sxs-lookup"><span data-stu-id="e65f5-103">TaxTrans record isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e65f5-104">Se selezioni **IVA registrata** per una transazione, ma la pagina **IVA registrata** non mostra alcuna riga di imposta o manca di una riga di imposta, il record **TaxTrans** potrebbe non essere stato generato.</span><span class="sxs-lookup"><span data-stu-id="e65f5-104">If you select **Posted sales tax** for a transaction, but the **Posted sales tax** page either shows no tax lines or is missing a tax line, the **TaxTrans** record might not have been generated.</span></span>

<span data-ttu-id="e65f5-105">[![Pagina IVA registrata senza voci](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="e65f5-105">[![Posted sales tax page that has no line items](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)</span></span>

<span data-ttu-id="e65f5-106">Per risolvere questo problema, seguire i passaggi nelle sezioni seguenti come richiesto.</span><span class="sxs-lookup"><span data-stu-id="e65f5-106">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a><span data-ttu-id="e65f5-107">Controllare l'IVA prima di registrare la transazione</span><span class="sxs-lookup"><span data-stu-id="e65f5-107">Check the sales tax before you post the transaction</span></span>

1. <span data-ttu-id="e65f5-108">Prima di registrare la transazione, nella pagina **Registrazione fattura**, selezionare **IVA** per controllare il calcolo.</span><span class="sxs-lookup"><span data-stu-id="e65f5-108">Before you post the transaction, on the **Posting invoice** page, select **Sales tax** to check the calculation.</span></span>

    <span data-ttu-id="e65f5-109">[![Pulsante IVA nella pagina Registrazione fattura](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="e65f5-109">[![Sales tax button on the Posting invoice page](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)</span></span>

2. <span data-ttu-id="e65f5-110">Nella pagina **Transazioni IVA provvisorie** rivedere il risultato del calcolo.</span><span class="sxs-lookup"><span data-stu-id="e65f5-110">On the **Temporary sales tax transactions** page, review the result of the calculation.</span></span> <span data-ttu-id="e65f5-111">Se non viene calcolata alcuna imposta, vedere [L'imposta non viene calcolata o l'importo dell'imposta è zero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).</span><span class="sxs-lookup"><span data-stu-id="e65f5-111">If no tax is calculated, see [Tax isn't calculated or the tax amount is zero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).</span></span>

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a><span data-ttu-id="e65f5-112">Trovare il record TaxTrans in tutta l'IVA registrata</span><span class="sxs-lookup"><span data-stu-id="e65f5-112">Find the TaxTrans record in all posted sales tax</span></span>

1. <span data-ttu-id="e65f5-113">Passare a **Imposta** \> **Richieste di informazioni e report** \> **Richieste di informazioni su IVA** > **IVA registrata**.</span><span class="sxs-lookup"><span data-stu-id="e65f5-113">Go to **Tax** \> **Inquiries and reports** \> **Sales tax inquiries** > **Posted sales tax**.</span></span>
2. <span data-ttu-id="e65f5-114">Nell'intestazione di colonna **Giustificativo** selezionare il simbolo del filtro per trovare il record **TaxTrans**.</span><span class="sxs-lookup"><span data-stu-id="e65f5-114">In the **Voucher** column heading, select the filter symbol to find the **TaxTrans** record.</span></span>
3. <span data-ttu-id="e65f5-115">Se trovi i record IVA che stai cercando, controlla la data.</span><span class="sxs-lookup"><span data-stu-id="e65f5-115">If you find the sales tax records that you're looking for, check the date.</span></span> <span data-ttu-id="e65f5-116">Se la data è diversa dalla data dell'intestazione del giornale di registrazione, crea una richiesta di assistenza Microsoft per ulteriore supporto.</span><span class="sxs-lookup"><span data-stu-id="e65f5-116">If the date differs from the date of the journal header, create a Microsoft service request for additional support.</span></span>

    <span data-ttu-id="e65f5-117">[![Pagina IVA registrata](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="e65f5-117">[![Posted sales tax page](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)</span></span>

## <a name="debug-to-check-details"></a><span data-ttu-id="e65f5-118">Eseguire il debug per verificare i dettagli</span><span class="sxs-lookup"><span data-stu-id="e65f5-118">Debug to check details</span></span>

1. <span data-ttu-id="e65f5-119">Per informazioni su come eseguire il debug e determinare se **TmpTaxWorkTrans** e **TaxUncommitted** sono generati correttamente, vedere [Valore di campo errato in TaxTrans](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).</span><span class="sxs-lookup"><span data-stu-id="e65f5-119">For information about how to debug and determine whether **TmpTaxWorkTrans** and **TaxUncommitted** are correctly generated, see [Field value in TaxTrans is incorrect](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).</span></span>
2. <span data-ttu-id="e65f5-120">Se **TaxTmpWorkTrans** o **TaxUncommitted** viene generato correttamente, aggiungi un punto di interruzione in corrispondenza di **TaxPost::SaveAndPost()** e **Tax::SaveAndPost** per eseguire il debug del motivo per cui **TaxTrans** non è inserito.</span><span class="sxs-lookup"><span data-stu-id="e65f5-120">If **TaxTmpWorkTrans** or **TaxUncommitted** is correctly generated, add a breakpoint at **TaxPost::SaveAndPost()** and **Tax::SaveAndPost** to debug the reason why **TaxTrans** isn't inserted.</span></span>

    <span data-ttu-id="e65f5-121">[![Punti di interruzione aggiunti nel codice](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="e65f5-121">[![Breakpoints added in code](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)</span></span>

    <span data-ttu-id="e65f5-122">[![Risultati dei punti di interruzione aggiunti](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="e65f5-122">[![Results of added breakpoints](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="e65f5-123">Determinare se esiste la personalizzazione</span><span class="sxs-lookup"><span data-stu-id="e65f5-123">Determine whether customization exists</span></span>

<span data-ttu-id="e65f5-124">Se hai completato i passaggi nelle sezioni precedenti ma non hai riscontrato alcun problema, determina se esiste la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="e65f5-124">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="e65f5-125">Se non esiste alcuna personalizzazione, creare una richiesta di assistenza Microsoft per ulteriore supporto.</span><span class="sxs-lookup"><span data-stu-id="e65f5-125">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
