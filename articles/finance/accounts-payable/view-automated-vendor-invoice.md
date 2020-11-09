---
title: Visualizzare i risultati dell'automazione delle fatture fornitore (anteprima)
description: In questo argomento viene descritto come visualizzare lo stato delle fatture fornitore che si trovano nel processo di invio al flusso di lavoro automatizzato.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ec49a621e24b6373532497b499e8b9d45c9bed14
ms.sourcegitcommit: 9e7ceb5604472f3088f611aa0360bd6a716db32b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4022615"
---
# <a name="view-vendor-invoice-automation-results"></a><span data-ttu-id="eaaf4-103">Visualizzare i risultati dell'automazione delle fatture dei fornitori</span><span class="sxs-lookup"><span data-stu-id="eaaf4-103">View vendor invoice automation results</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eaaf4-104">In questo argomento viene descritto come visualizzare lo stato delle fatture fornitore che si trovano nel processo di invio al flusso di lavoro automatizzato.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-104">This topic explains how to view the status of vendor invoices that are in the automated submit-to-workflow process.</span></span> <span data-ttu-id="eaaf4-105">I dettagli della cronologia dell'automazione vengono mantenuti per ogni fattura fornitore importata.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-105">Details of the automation history are maintained for each imported vendor invoice.</span></span> <span data-ttu-id="eaaf4-106">A seconda dei processi aziendali che hai automatizzato, la pagina **Fatture fornitore in sospeso** mostra i valori **Stato corrispondenza entrate automatizzate** e **Stato Invio a flusso di lavoro automatizzato**.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-106">Depending on the business processes that you've automated, the **Pending vendor invoices** page shows **Automated receipt match status** and **Automated submit to workflow status** values.</span></span> <span data-ttu-id="eaaf4-107">Puoi visualizzare i dettagli e creare un piano per concentrarti sulle fatture che non hanno superato un passaggio automatizzato.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-107">You can view the details and make a plan to focus on the invoices that failed an automated step.</span></span> <span data-ttu-id="eaaf4-108">Quindi, dopo aver corretto il problema, puoi riprendere il processo automatizzato per la fattura importata.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-108">Then, after you correct the issue, you can resume the automated process for the imported invoice.</span></span>

<span data-ttu-id="eaaf4-109">Prima di poter modificare una fattura inviata, devi sospendere l'elaborazione automatizzata.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-109">Before you can edit an invoice that has been submitted, you must pause the automated processing.</span></span> <span data-ttu-id="eaaf4-110">Se una fattura nel processo di invio al flusso di lavoro automatizzato deve essere sospesa, imposta il campo **Includi in elaborazione automatizzata** su **No** nella pagina **Fatture fornitore**.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-110">If an invoice in the automated submit-to-workflow process must be paused, set the **Include in Automated processing** field to **No** on the **Vendor invoices** page.</span></span> <span data-ttu-id="eaaf4-111">L'automazione quindi non verrà eseguita fino a quando **Includi in elaborazione automatizzata** non viene impostato su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-111">Automation then won't run until **Include in Automated processing** is set to **Yes**.</span></span> <span data-ttu-id="eaaf4-112">Una fattura può non essere sottoposta a un'ulteriore automazione se non è ancora nel sistema flusso di lavoro e non è utilizzata dal processo automatizzato.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-112">An invoice can be paused from further automation if it isn't yet in the workflow system and isn't used by the automated process.</span></span>

<span data-ttu-id="eaaf4-113">Se una fattura importata è soggetta al processo di invio al flusso di lavoro, è possibile visualizzare il relativo valore **Stato automazione** nella pagina **Fatture fornitore**.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-113">If an imported invoice is subject to the submit-to-workflow process, you can view its **Automation status** value on the **Vendor invoices** page.</span></span> <span data-ttu-id="eaaf4-114">Vengono monitorati i seguenti stati:</span><span class="sxs-lookup"><span data-stu-id="eaaf4-114">The following statuses are tracked:</span></span>

- <span data-ttu-id="eaaf4-115">**Incluso** - I processi automatizzati definiti nella pagina **Parametri contabilità fornitori** funzionano correttamente ma non sono ancora stati completati.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-115">**Included** – The automated processes that are defined on the **Accounts payable parameters** page are running correctly but haven't yet been completed.</span></span>
- <span data-ttu-id="eaaf4-116">**In sospeso** - I processi automatizzati definiti nella pagina **Parametri contabilità fornitori** sono stati eseguiti, ma almeno un passaggio del processo non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-116">**Paused** – The automated processes that are defined on the **Accounts payable parameters** page have run, but at least one step in the process failed.</span></span> <span data-ttu-id="eaaf4-117">Lo stato **In sospeso** viene applicato anche se il campo **Includi in elaborazione automatizzata** è impostato su **No**.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-117">The **Paused** status is also applied if the **Include in automated processing** field is set to **No**.</span></span> <span data-ttu-id="eaaf4-118">Puoi visualizzare gli errori selezionando **Visualizza risultati più recenti**.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-118">You can view the failures by selecting **View most recent results**.</span></span>
- <span data-ttu-id="eaaf4-119">**In flusso di lavoro** - La fattura importata è stata inviata al sistema flusso di lavoro, tramite il processo di invio al flusso di lavoro automatizzato o manualmente.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-119">**In workflow** – The imported invoice has been submitted to the workflow system, either by the automated submit-to-workflow process or manually.</span></span>
- <span data-ttu-id="eaaf4-120">**Flusso di lavoro completato** - Il processo del flusso di lavoro è stato completato per la fattura importata.</span><span class="sxs-lookup"><span data-stu-id="eaaf4-120">**Workflow complete** – The workflow process has been completed for the imported invoice.</span></span>
