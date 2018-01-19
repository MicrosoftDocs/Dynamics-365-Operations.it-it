---
title: Risolvere le discrepanze durante l'abbinamento dei totali fatture
description: "È possibile utilizzare l'abbinamento dei totali fatture per garantire che gli importi totali delle fatture non si discostino dagli importi previsti oltre un livello accettabile."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 17a7d9c40d07524378a671397fed566b9bd3af6b
ms.openlocfilehash: 306edb85a202ba750c0e9519e5157b6b06292fde
ms.contentlocale: it-it
ms.lasthandoff: 01/19/2018

---

# <a name="resolve-discrepancies-during-invoice-totals-matching"></a><span data-ttu-id="d0730-103">Risolvere le discrepanze durante l'abbinamento dei totali fatture</span><span class="sxs-lookup"><span data-stu-id="d0730-103">Resolve discrepancies during invoice totals matching</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d0730-104">Un tipo di convalida dell'abbinamento fatture è l'abbinamento dei totali fatture.</span><span class="sxs-lookup"><span data-stu-id="d0730-104">One type of invoice matching validation is invoice totals matching.</span></span> <span data-ttu-id="d0730-105">Per fare in modo che il sistema esegua l'abbinamento dei totali fatture, nella pagina **Parametri contabilità fornitori**, nella scheda **Convalida fattura**, impostare l'opzione **Abbina totali fatture** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d0730-105">To specify that the system should perform invoice totals matching, on the **Accounts payable parameters** page, on the **Invoice validation** tab, set the **Match invoice totals** option **Yes**.</span></span> 

<span data-ttu-id="d0730-106">È possibile utilizzare l'abbinamento dei totali fatture per garantire che gli importi totali delle fatture non si discostino dagli importi previsti oltre un livello accettabile.</span><span class="sxs-lookup"><span data-stu-id="d0730-106">You can use invoice totals matching to help guarantee that total invoice amounts don't deviate from expected amounts by more than an acceptable variance.</span></span> <span data-ttu-id="d0730-107">Nella pagina **Dettagli abbinamento totali fatture** vengono confrontati sei totali.</span><span class="sxs-lookup"><span data-stu-id="d0730-107">Six totals are compared on the **Invoice totals matching details** page.</span></span> <span data-ttu-id="d0730-108">Se uno qualsiasi dei totali devia dal corrispondente totale ordine acquisto previsto, viene segnalata una discrepanza di abbinamento.</span><span class="sxs-lookup"><span data-stu-id="d0730-108">If any one of the totals deviates from the expected corresponding purchase order total, a matching discrepancy is flagged.</span></span> 

<span data-ttu-id="d0730-109">Per esaminare la fattura che presenta le discrepanze nell'abbinamento dei totali, nell'area di lavoro **Inserimento fatture fornitore** fare clic sul riquadro **Fatture in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="d0730-109">To review the invoice that has the totals matching discrepancies, in the **Vendor invoice entry** workspace, click the **Pending invoices** tile.</span></span> <span data-ttu-id="d0730-110">Successivamente, nel riquadro azioni, nella scheda **Revisione**, fare clic su **Dettagli abbinamento**.</span><span class="sxs-lookup"><span data-stu-id="d0730-110">Then, on the Action Pane, on the **Review** tab, click **Matching details**.</span></span> <span data-ttu-id="d0730-111">Se sono state rilevate discrepanze di abbinamento, accanto all'importo fattura vengono visualizzate delle icone di avviso.</span><span class="sxs-lookup"><span data-stu-id="d0730-111">If matching discrepancies have been detected, warning icons appear next to the invoice amount.</span></span> <span data-ttu-id="d0730-112">È possibile visualizzare ulteriori dettagli sui totali visualizzando i dettagli di abbinamento dei totali fatture.</span><span class="sxs-lookup"><span data-stu-id="d0730-112">You can view more detail about the totals by viewing the invoice totals matching details.</span></span> 

<span data-ttu-id="d0730-113">Dopo aver identificato la discrepanza, potrebbe essere necessario contattare il fornitore se si ritiene che le informazioni riportate nella fattura non siano corrette.</span><span class="sxs-lookup"><span data-stu-id="d0730-113">After you identify a discrepancy, you might have to contact the vendor if you think that the information on the invoice is incorrect.</span></span> <span data-ttu-id="d0730-114">A seconda dell'accordo risultante con il fornitore, sarà possibile effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="d0730-114">Depending on the resulting agreement with the vendor, you can then take one of these actions:</span></span>

-   <span data-ttu-id="d0730-115">Accettare la differenza di prezzo e registrare la fattura che presenta discrepanze di abbinamento.</span><span class="sxs-lookup"><span data-stu-id="d0730-115">Accept the price difference, and post the invoice that has matching discrepancies.</span></span> <span data-ttu-id="d0730-116">È possibile che il sistema sia impostato in modo da richiedere l'approvazione prima della registrazione in presenza di discrepanze di abbinamento.</span><span class="sxs-lookup"><span data-stu-id="d0730-116">Your system might be set up to require approval before it can post if there are matching discrepancies.</span></span> <span data-ttu-id="d0730-117">In questo caso, è necessario approvare la discrepanza di abbinamento e facoltativamente si può scegliere di immettere un commento di approvazione.</span><span class="sxs-lookup"><span data-stu-id="d0730-117">In this case, you must approve the matching discrepancy and can optionally enter an approval comment.</span></span> <span data-ttu-id="d0730-118">Successivamente si può scegliere di registrare la fattura.</span><span class="sxs-lookup"><span data-stu-id="d0730-118">You can then select to post the invoice.</span></span>
-   <span data-ttu-id="d0730-119">Modificare l'importo della fattura in modo che corrisponda a quello previsto e registrare la fattura.</span><span class="sxs-lookup"><span data-stu-id="d0730-119">Revise the invoice amount to the expected amount, and post the invoice.</span></span>
-   <span data-ttu-id="d0730-120">Richiedere al fornitore un credito totale e una nuova fattura corretta.</span><span class="sxs-lookup"><span data-stu-id="d0730-120">Request a full credit and a new, corrected invoice from the vendor.</span></span>

<span data-ttu-id="d0730-121">Per ulteriori informazioni, vedere [Cercare o risolvere eccezioni](tasks/research-resolve-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="d0730-121">For more information, see [Research or resolve exceptions](tasks/research-resolve-exceptions.md).</span></span>



