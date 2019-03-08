---
title: Visualizza storico flusso di lavoro
description: Per visualizzare lo stato di un documento inviato al sistema del flusso di lavoro per l'elaborazione e l'approvazione, utilizzare alla procedura indicata di seguito.
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a40fe377322e2d64b751f6cace3eda20736cd321
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "309658"
---
# <a name="view-workflow-history"></a><span data-ttu-id="1ddd8-103">Visualizza storico flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1ddd8-103">View workflow history</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1ddd8-104">Per visualizzare lo stato di un documento inviato al sistema del flusso di lavoro per l'elaborazione e l'approvazione, utilizzare alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-104">Use these steps to view the status of a document that was submitted to the workflow system for processing and approval.</span></span> <span data-ttu-id="1ddd8-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-105">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="1ddd8-106">Passare a Comune > Informazioni > Flusso di lavoro > Storico flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-106">Go to Common > Inquiries > Workflow > Workflow history.</span></span>
    * <span data-ttu-id="1ddd8-107">Utilizzare questo modulo per visualizzare lo stato di un documento inviato al sistema del flusso di lavoro per l'elaborazione e l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-107">Use this form to view the status of a document that was submitted to the workflow system for processing and approval.</span></span>  
    * <span data-ttu-id="1ddd8-108">ID istanza è il codice di identificazione dell'istanza del flusso di lavoro in cui è in corso o è avvenuta l'elaborazione del documento.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-108">The Instance ID is      the identification code of the workflow instance that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="1ddd8-109">Stato è lo stato del flusso di lavoro del documento.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-109">The Status is the workflow status of the document.</span></span>  
    * <span data-ttu-id="1ddd8-110">ID flusso di lavoro è il codice di identificazione del flusso di lavoro in cui è in corso o è avvenuta l'elaborazione del documento.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-110">The Workflow ID is the identification code of the workflow that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="1ddd8-111">Documento è il codice di identificazione del documento.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-111">The Document is the identification code of the document.</span></span>  
    * <span data-ttu-id="1ddd8-112">Tipo di documento è il tipo di documento inviato per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-112">The Document type is the type of document that was submitted for processing.</span></span>  
    * <span data-ttu-id="1ddd8-113">Flusso di lavoro è il nome del flusso di lavoro in cui è in corso o è avvenuta l'elaborazione del documento.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-113">The Workflow is the name of the workflow that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="1ddd8-114">Versione è il numero di versione del flusso di lavoro in cui è in corso o è avvenuta l'elaborazione del documento.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-114">The Version is the version number of the workflow that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="1ddd8-115">Data e ora creazione è la data e ora in cui è stata inviata la voce di registro per il documento.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-115">The Created date and time is the date and time that the document was submitted.</span></span>  
    * <span data-ttu-id="1ddd8-116">Tempo trascorso è la quantità di tempo trascorsa dall'invio del documento.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-116">The Elapsed time is the time that has passed since the document was submitted.</span></span>  
    * <span data-ttu-id="1ddd8-117">Il pulsante Riprendi consente di riprendere il processo del flusso di lavoro relativo al documento selezionato.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-117">The Resume button allows you to resume the workflow process for the selected document.</span></span>  
    * <span data-ttu-id="1ddd8-118">Il pulsante Richiama consente di richiamare il documento selezionato in modo che non venga elaborato.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-118">The Recall button allows you to recall the selected document so that it is not processed.</span></span>   
2. <span data-ttu-id="1ddd8-119">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1ddd8-120">Assicurarsi che la sezione Elementi di lavoro sia espansa.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-120">Make sure the Work items section is expanded.</span></span>    <span data-ttu-id="1ddd8-121">In questa sezione è possibile visualizzare gli elementi di lavoro associati al documento selezionato.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-121">In this section you can view the work items that are associated with the selected document.</span></span> <span data-ttu-id="1ddd8-122">Può contenere, ad esempio, un'attività da completare o un documento da approvare.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-122">For example, a task may have to be completed, or the document may have to be approved.</span></span>  
    * <span data-ttu-id="1ddd8-123">Il pulsante Riassegna apre una finestra di dialogo in cui è possibile riassegnare un elemento di lavoro a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-123">The Reassign button will open a dialog box where you can reassign a work item to another user.</span></span>  
    * <span data-ttu-id="1ddd8-124">Assicurarsi che la sezione Dettagli tracciabilità sia espansa.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-124">Make sure the Tracking details section is expanded.</span></span>    <span data-ttu-id="1ddd8-125">In questa sezione è possibile visualizzare lo storico flusso di lavoro del documento selezionato.</span><span class="sxs-lookup"><span data-stu-id="1ddd8-125">In this section you can view the workflow history of the selected document.</span></span>  

