---
title: Impostare flussi di lavoro per le spese
description: È possibile impostare un processo del flusso di lavoro utilizzato per rivedere e approvare i documenti viaggi e spese.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86cadf7277fbb7e08dad4b5dc2a46e1c6ce5a888
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178466"
---
# <a name="set-up-workflows-for-expense"></a><span data-ttu-id="39660-103">Impostare flussi di lavoro per le spese</span><span class="sxs-lookup"><span data-stu-id="39660-103">Set up workflows for expense</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39660-104"> È possibile impostare un processo del flusso di lavoro utilizzato per rivedere e approvare i documenti viaggi e spese.</span><span class="sxs-lookup"><span data-stu-id="39660-104">You can set up a workflow process that is used to review and approve travel and expense documents.</span></span> <span data-ttu-id="39660-105">I documenti per cui è possibile definire flussi di lavoro includono note spese, richieste di viaggio e richieste di anticipo contanti.</span><span class="sxs-lookup"><span data-stu-id="39660-105">The documents for which workflows can be defined include expense reports, travel requisitions, and cash advance requests.</span></span>

<span data-ttu-id="39660-106">Un flusso di lavoro rappresenta un processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="39660-106">A workflow represents a business process.</span></span> <span data-ttu-id="39660-107">Definisce il modo in cui un documento attraversa il sistema e stabilisce chi deve completare un'attività o approvare un documento.</span><span class="sxs-lookup"><span data-stu-id="39660-107">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="39660-108">Di seguito sono descritti i vantaggi derivanti dall'utilizzo di un sistema basato su flusso di lavoro all'interno dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="39660-108">There are several benefits of using the workflow system in your organization:</span></span>

-   <span data-ttu-id="39660-109">**Processi coerenti**: è possibile definire il processo di approvazione per documenti specifici, ad esempio richieste di acquisto e note spese.</span><span class="sxs-lookup"><span data-stu-id="39660-109">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="39660-110">L'utilizzo del sistema flusso di lavoro consente di garantire che i documenti vengano elaborati e approvati in modo efficiente e coerente.</span><span class="sxs-lookup"><span data-stu-id="39660-110">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>

-   <span data-ttu-id="39660-111">Visibilità dei processi: è possibile tenere traccia delle metriche relative a stato, storico e prestazioni di una specifica istanza di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="39660-111">Process visibility — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="39660-112">In questo modo è possibile stabilire se il flusso di lavoro necessita di modifiche allo scopo di migliorarne l'efficienza.</span><span class="sxs-lookup"><span data-stu-id="39660-112">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>

-   <span data-ttu-id="39660-113">Elenco di lavoro centralizzato: gli utenti possono visualizzare un elenco di lavoro centralizzato contenente le attività del flusso di lavoro e le approvazioni loro assegnati.</span><span class="sxs-lookup"><span data-stu-id="39660-113">Centralized work list — Users can view a centralized work list to view the workflow tasks and approvals assigned to them.</span></span> 

<span data-ttu-id="39660-114">**Tipi di flussi di lavoro che è possibile creare**</span><span class="sxs-lookup"><span data-stu-id="39660-114">**The types of workflows you can create**</span></span>

<span data-ttu-id="39660-115">Nella tabella riportata di seguito sono elencati i tipi di flussi di lavoro che è possibile creare in **Spesa**.</span><span class="sxs-lookup"><span data-stu-id="39660-115">The following table lists the types of workflows that you can create in **Expense**.</span></span>


|              <span data-ttu-id="39660-116"><strong>Tipo</strong></span><span class="sxs-lookup"><span data-stu-id="39660-116"><strong>Type</strong></span></span>              |                   <span data-ttu-id="39660-117"><strong>Utilizzare questo tipo per:</strong></span><span class="sxs-lookup"><span data-stu-id="39660-117"><strong>Use this type to</strong></span></span>                   |
|-------------------------------------------------|-----------------------------------------------------------------------|
|         <span data-ttu-id="39660-118"><strong>Nota spese</strong></span><span class="sxs-lookup"><span data-stu-id="39660-118"><strong>Expense report</strong></span></span>         |            <span data-ttu-id="39660-119">Creare flussi di lavoro di approvazione per le note spese.</span><span class="sxs-lookup"><span data-stu-id="39660-119">Create approval workflows for expense reports.</span></span>             |
|  <span data-ttu-id="39660-120"><strong>Registrazione automatica nota spese</strong></span><span class="sxs-lookup"><span data-stu-id="39660-120"><strong>Expense report auto posting</strong></span></span>   |        <span data-ttu-id="39660-121">Creare flussi di lavoro di registrazione automatica per le note spese.</span><span class="sxs-lookup"><span data-stu-id="39660-121">Create automatic posting workflows for expense reports.</span></span>        |
|       <span data-ttu-id="39660-122"><strong>Voce di spesa</strong></span><span class="sxs-lookup"><span data-stu-id="39660-122"><strong>Expense line item</strong></span></span>        |     <span data-ttu-id="39660-123">Creare flussi di lavoro di approvazione per le voci delle note spese.</span><span class="sxs-lookup"><span data-stu-id="39660-123">Create approval workflows for line items on expense reports.</span></span>      |
| <span data-ttu-id="39660-124"><strong>Registrazione automatica voce di spesa</strong></span><span class="sxs-lookup"><span data-stu-id="39660-124"><strong>Expense line item auto posting</strong></span></span> | <span data-ttu-id="39660-125">Creare flussi di lavoro di registrazione automatica per le voci delle note spese.</span><span class="sxs-lookup"><span data-stu-id="39660-125">Create automatic posting workflows for line items on expense reports.</span></span> |
|       <span data-ttu-id="39660-126"><strong>Richiesta di acquisto viaggio</strong></span><span class="sxs-lookup"><span data-stu-id="39660-126"><strong>Travel requisition</strong></span></span>       |          <span data-ttu-id="39660-127">Creare flussi di lavoro di approvazione per le richieste di viaggio.</span><span class="sxs-lookup"><span data-stu-id="39660-127">Create approval workflows for travel requisitions.</span></span>           |
|      <span data-ttu-id="39660-128"><strong>Richiesta di anticipo contanti</strong></span><span class="sxs-lookup"><span data-stu-id="39660-128"><strong>Cash advance request</strong></span></span>      |         <span data-ttu-id="39660-129">Creare flussi di lavoro di approvazione per richieste di anticipo contanti.</span><span class="sxs-lookup"><span data-stu-id="39660-129">Create approval workflows for cash advance requests.</span></span>          |
|        <span data-ttu-id="39660-130"><strong>Recupero IVA</strong></span><span class="sxs-lookup"><span data-stu-id="39660-130"><strong>VAT tax recovery</strong></span></span>        | <span data-ttu-id="39660-131">Creare flussi di lavoro di approvazione per il recupero dell'imposta sul valore aggiunto (IVA).</span><span class="sxs-lookup"><span data-stu-id="39660-131">Create approval workflows for the recovery of value-added tax (VAT).</span></span>  |

