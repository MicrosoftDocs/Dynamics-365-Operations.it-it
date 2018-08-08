---
title: Correzione di una fattura a testo libero
description: In questo articolo viene illustrato come correggere una fattura a testo libero registrata e come riemetterla in modo corretto.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: c8c1b90b7b2c02a53e53cc13d70445a237b126d4
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="correct-a-free-text-invoice"></a><span data-ttu-id="63e98-103">Correzione di una fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="63e98-103">Correct a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63e98-104">In questo articolo viene illustrato come correggere una fattura a testo libero registrata e come riemetterla in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="63e98-104">This article explains how to correct a free text invoice that has been posted and reissue it as a corrected invoice.</span></span>

<span data-ttu-id="63e98-105">Per correggere una fattura a testo libero già registrata, aprire la fattura a testo libero registrata.</span><span class="sxs-lookup"><span data-stu-id="63e98-105">To correct a free text invoice that has already been posted, open the posted free text invoice.</span></span> <span data-ttu-id="63e98-106">Nella pagina **Fattura** selezionare **Annulla** e quindi selezionare **Fattura corretta**.</span><span class="sxs-lookup"><span data-stu-id="63e98-106">On the **Invoice** page, select **Cancel**, and then select **Correct invoice**.</span></span> <span data-ttu-id="63e98-107">Selezionare un codice motivo, aggiungere commenti e selezionare la data della nuova fattura corretta.</span><span class="sxs-lookup"><span data-stu-id="63e98-107">Select a reason code, add comments, and select the date for new corrected invoice.</span></span> <span data-ttu-id="63e98-108">È possibile modificare la fattura corretta e registrarla.</span><span class="sxs-lookup"><span data-stu-id="63e98-108">You can modify the corrected invoice, and post it.</span></span> 

<span data-ttu-id="63e98-109">Quando si registra la fattura corretta, una fattura di annullamento viene creata per un importo in Avere equivalente all'importo della fattura originale.</span><span class="sxs-lookup"><span data-stu-id="63e98-109">When you post the corrected invoice, a canceling invoice is created for a credit amount that equals the original invoice amount.</span></span> <span data-ttu-id="63e98-110">Quindi, il saldo combinato della fattura originale e della fattura di annullamento sarà 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="63e98-110">Therefore, the combined balance of the original invoice and the canceling invoice is 0 (zero).</span></span> <span data-ttu-id="63e98-111">La fattura di annullamento viene liquidata a fronte della fattura originale.</span><span class="sxs-lookup"><span data-stu-id="63e98-111">The canceling invoice is settled against the original invoice.</span></span> 

<span data-ttu-id="63e98-112">Dopo la registrazione della fattura corretta, si avranno tre fatture:</span><span class="sxs-lookup"><span data-stu-id="63e98-112">After you post the corrected invoice, you will have three invoices:</span></span>

-   <span data-ttu-id="63e98-113">**Fattura originale**: fattura che include le informazioni da correggere.</span><span class="sxs-lookup"><span data-stu-id="63e98-113">**Original invoice** – The invoice that includes the information that you're correcting.</span></span>
-   <span data-ttu-id="63e98-114">**Fattura di annullamento**: fattura nota di accredito generata dal sistema e creata per annullare l'ultima fattura corretta.</span><span class="sxs-lookup"><span data-stu-id="63e98-114">**Canceling invoice** – The system-generated credit invoice that was created to cancel the invoice that was most recently corrected.</span></span>
-   <span data-ttu-id="63e98-115">**Fattura corretta**: fattura che contiene le informazioni della fattura corrette.</span><span class="sxs-lookup"><span data-stu-id="63e98-115">**Corrected invoice** – The invoice that contains the corrected invoice information.</span></span>

<span data-ttu-id="63e98-116">È possibile identificare la fattura di annullamento e di correzione in due modi:</span><span class="sxs-lookup"><span data-stu-id="63e98-116">You can identify canceling and correcting invoices in two ways:</span></span>

-   <span data-ttu-id="63e98-117">La pagina **Tutte le fatture a testo libero** include una colonna **Correzione**, in cui è possibile visualizzare quali fatture sono di annullamento e quali fatture corrette.</span><span class="sxs-lookup"><span data-stu-id="63e98-117">The **All free text invoices** page includes a **Correction** column, where you can see which invoices are canceling invoices and corrected invoices.</span></span>
-   <span data-ttu-id="63e98-118">Nell'intestazione della fattura a testo libero viene visualizzato uno stato **Fattura di annullamento '\[numero fattura\]'** o **Fattura corretta '\[numero fattura\]'**.</span><span class="sxs-lookup"><span data-stu-id="63e98-118">The header of the free text invoice shows a status of **Cancelling invoice '\[invoice number\]'** or **Corrected invoice '\[invoice number\]'**.</span></span>

> [!NOTE]
> <span data-ttu-id="63e98-119">Questa funzionalità è disponibile solo se è selezionata la chiave di configurazione **Correzione fattura a testo libero.**</span><span class="sxs-lookup"><span data-stu-id="63e98-119">This feature is available only if the **Free text invoice correction** configuration key is selected.</span></span>




