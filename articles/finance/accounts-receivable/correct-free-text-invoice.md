---
title: Correzione di una fattura a testo libero
description: In questo articolo viene illustrato come correggere una fattura a testo libero registrata e come riemetterla in modo corretto.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0bf6e7a070d7c151c6ff5d868f4f916359b82683
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444652"
---
# <a name="correct-a-free-text-invoice"></a><span data-ttu-id="8da9c-103">Correzione di una fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="8da9c-103">Correct a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8da9c-104">In questo articolo viene illustrato come correggere una fattura a testo libero registrata e come riemetterla in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="8da9c-104">This article explains how to correct a free text invoice that has been posted and reissue it as a corrected invoice.</span></span>

<span data-ttu-id="8da9c-105">Per correggere una fattura a testo libero già registrata, aprire la fattura a testo libero registrata.</span><span class="sxs-lookup"><span data-stu-id="8da9c-105">To correct a free text invoice that has already been posted, open the posted free text invoice.</span></span> <span data-ttu-id="8da9c-106">Nella pagina **Fattura** selezionare **Annulla** e quindi selezionare **Fattura corretta**.</span><span class="sxs-lookup"><span data-stu-id="8da9c-106">On the **Invoice** page, select **Cancel**, and then select **Correct invoice**.</span></span> <span data-ttu-id="8da9c-107">Selezionare un codice motivo, aggiungere commenti e selezionare la data della nuova fattura corretta.</span><span class="sxs-lookup"><span data-stu-id="8da9c-107">Select a reason code, add comments, and select the date for new corrected invoice.</span></span> <span data-ttu-id="8da9c-108">È possibile modificare la fattura corretta e registrarla.</span><span class="sxs-lookup"><span data-stu-id="8da9c-108">You can modify the corrected invoice, and post it.</span></span> 

<span data-ttu-id="8da9c-109">Quando si registra la fattura corretta, una fattura di annullamento viene creata per un importo in Avere equivalente all'importo della fattura originale.</span><span class="sxs-lookup"><span data-stu-id="8da9c-109">When you post the corrected invoice, a canceling invoice is created for a credit amount that equals the original invoice amount.</span></span> <span data-ttu-id="8da9c-110">Quindi, il saldo combinato della fattura originale e della fattura di annullamento sarà 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="8da9c-110">Therefore, the combined balance of the original invoice and the canceling invoice is 0 (zero).</span></span> <span data-ttu-id="8da9c-111">La fattura di annullamento viene liquidata a fronte della fattura originale.</span><span class="sxs-lookup"><span data-stu-id="8da9c-111">The canceling invoice is settled against the original invoice.</span></span> 

<span data-ttu-id="8da9c-112">Dopo la registrazione della fattura corretta, si avranno tre fatture:</span><span class="sxs-lookup"><span data-stu-id="8da9c-112">After you post the corrected invoice, you will have three invoices:</span></span>

-   <span data-ttu-id="8da9c-113">**Fattura originale**: fattura che include le informazioni da correggere.</span><span class="sxs-lookup"><span data-stu-id="8da9c-113">**Original invoice** – The invoice that includes the information that you're correcting.</span></span>
-   <span data-ttu-id="8da9c-114">**Fattura di annullamento**: fattura nota di accredito generata dal sistema e creata per annullare l'ultima fattura corretta.</span><span class="sxs-lookup"><span data-stu-id="8da9c-114">**Canceling invoice** – The system-generated credit invoice that was created to cancel the invoice that was most recently corrected.</span></span>
-   <span data-ttu-id="8da9c-115">**Fattura corretta**: fattura che contiene le informazioni della fattura corrette.</span><span class="sxs-lookup"><span data-stu-id="8da9c-115">**Corrected invoice** – The invoice that contains the corrected invoice information.</span></span>

<span data-ttu-id="8da9c-116">È possibile identificare la fattura di annullamento e di correzione in due modi:</span><span class="sxs-lookup"><span data-stu-id="8da9c-116">You can identify canceling and correcting invoices in two ways:</span></span>

-   <span data-ttu-id="8da9c-117">La pagina **Tutte le fatture a testo libero** include una colonna **Correzione**, in cui è possibile visualizzare quali fatture sono di annullamento e quali fatture corrette.</span><span class="sxs-lookup"><span data-stu-id="8da9c-117">The **All free text invoices** page includes a **Correction** column, where you can see which invoices are canceling invoices and corrected invoices.</span></span>
-   <span data-ttu-id="8da9c-118">Nell'intestazione della fattura a testo libero viene visualizzato uno stato **Fattura di annullamento '\[numero fattura\]'** o **Fattura corretta '\[numero fattura\]'**.</span><span class="sxs-lookup"><span data-stu-id="8da9c-118">The header of the free text invoice shows a status of **Cancelling invoice '\[invoice number\]'** or **Corrected invoice '\[invoice number\]'**.</span></span>

> [!NOTE]
> <span data-ttu-id="8da9c-119">Questa funzionalità è disponibile solo se è selezionata la chiave di configurazione **Correzione fattura a testo libero.**</span><span class="sxs-lookup"><span data-stu-id="8da9c-119">This feature is available only if the **Free text invoice correction** configuration key is selected.</span></span> <span data-ttu-id="8da9c-120">Per ulteriori informazioni su come abilitare le chiavi di configurazione, vedere la sezione relativa all'abilitazione (o disabilitazione) delle chiavi di configurazione nell'argomento [Modalità manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="8da9c-120">For more information on how to enable Configuration keys refer to the Enable (or disable) configuration keys section in the [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) topic.</span></span> 



