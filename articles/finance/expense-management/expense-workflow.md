---
title: Flusso di lavoro di Gestione spese
description: Questo argomento descrive come è possibile utilizzare il sistema del flusso di lavoro in Microsoft Dynamics 365 Finance per impostare un processo di verifica delle note spese in Gestione spese.
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
ms.openlocfilehash: 5207be92cb58d8ab2658096b3e0f3fc81d73d91e
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "3153974"
---
# <a name="expense-management-workflow"></a><span data-ttu-id="e0612-103">Flusso di lavoro di Gestione spese</span><span class="sxs-lookup"><span data-stu-id="e0612-103">Expense management workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0612-104">È possibile utilizzare il sistema del flusso di lavoro per impostare un processo di verifica delle note spese in Gestione spese.</span><span class="sxs-lookup"><span data-stu-id="e0612-104">You can use the workflow system to set up a review process for expense reports in Expense management.</span></span> <span data-ttu-id="e0612-105">È possibile impostare un flusso di lavoro che utilizza i seguenti criteri per determinare il responsabile dell'approvazione delle note spese:</span><span class="sxs-lookup"><span data-stu-id="e0612-105">You can set up a workflow that uses the following criteria to determine who approves expense reports:</span></span>

- <span data-ttu-id="e0612-106">Relazioni gerarchiche tra i dipendenti e limiti di approvazione predefiniti</span><span class="sxs-lookup"><span data-stu-id="e0612-106">The employee reporting hierarchy and predefined approval limits</span></span>
- <span data-ttu-id="e0612-107">Approvazione multilivello che supporta gli approvatori provvisori e un approvatore finale</span><span class="sxs-lookup"><span data-stu-id="e0612-107">Multi-level approval that supports interim approvers and a final approver</span></span>
- <span data-ttu-id="e0612-108">Dimensioni finanziarie e responsabilità dei progetti</span><span class="sxs-lookup"><span data-stu-id="e0612-108">Financial dimensions and project responsibility</span></span>
- <span data-ttu-id="e0612-109">Assegnazione a utenti o gruppi di utenti specifici</span><span class="sxs-lookup"><span data-stu-id="e0612-109">Assignment to specific users or user groups</span></span>

<span data-ttu-id="e0612-110">È possibile creare approvazioni del flusso di lavoro per note spese, richieste di viaggio, anticipo contanti e recupero dell'imposta sul valore aggiunto (IVA).</span><span class="sxs-lookup"><span data-stu-id="e0612-110">Workflow approvals can be created for expense reports, travel requisitions, cash advances, and value-added tax (VAT) recovery.</span></span>

<span data-ttu-id="e0612-111">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="e0612-111">**Example**</span></span>

<span data-ttu-id="e0612-112">Il processo riportato di seguito è un esempio di flusso di lavoro di gestione delle spese per una nota spese.</span><span class="sxs-lookup"><span data-stu-id="e0612-112">The following process is an example of the expense management workflow for an expense report.</span></span>

1. <span data-ttu-id="e0612-113">Un dipendente crea e salva una nota spese.</span><span class="sxs-lookup"><span data-stu-id="e0612-113">An employee creates and saves an expense report.</span></span>
2. <span data-ttu-id="e0612-114">Il dipendente invia la nota spese per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="e0612-114">The employee submits the expense report for approval.</span></span> <span data-ttu-id="e0612-115">L'approvatore è identificato in base alle regole definite durante l'impostazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e0612-115">The approver is identified based on the rules that were defined when the workflow was set up.</span></span>
3. <span data-ttu-id="e0612-116">L'approvatore riceve una notifica che lo informa che una nota spese è pronta per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="e0612-116">The approver receives a notification that an expense report is ready for approval.</span></span> <span data-ttu-id="e0612-117">L'approvatore rivede la nota spese e verifica che le seguenti condizioni siano soddisfatte:</span><span class="sxs-lookup"><span data-stu-id="e0612-117">The approver reviews the expense report and verifies that the following conditions are met:</span></span>

    - <span data-ttu-id="e0612-118">Le spese non violano alcun criterio di spesa.</span><span class="sxs-lookup"><span data-stu-id="e0612-118">The expenses don't violate any expense policies.</span></span> <span data-ttu-id="e0612-119">Se una spesa viola i criteri, l'approvatore verifica che nella nota spese sia inclusa una motivazione aziendale valida.</span><span class="sxs-lookup"><span data-stu-id="e0612-119">If an expense violates a policy, the approver verifies that the expense report includes a valid business justification.</span></span>
    - <span data-ttu-id="e0612-120">Le ricevute elettroniche sono allegate alla nota spese.</span><span class="sxs-lookup"><span data-stu-id="e0612-120">Electronic receipts are attached to the expense report.</span></span>

4. <span data-ttu-id="e0612-121">L'approvatore approva la nota spese.</span><span class="sxs-lookup"><span data-stu-id="e0612-121">The approver approves the expense report.</span></span>
5. <span data-ttu-id="e0612-122">La nota spese viene assegnata al coordinatore della contabilità fornitori per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="e0612-122">The expense report is assigned to the Accounts payable coordinator for posting.</span></span>
6. <span data-ttu-id="e0612-123">Una delle seguenti azioni viene eseguita a seconda che la registrazione automatica è configurata o meno:</span><span class="sxs-lookup"><span data-stu-id="e0612-123">One of the following steps occurs, depending on whether automatic posting is configured:</span></span>

    - <span data-ttu-id="e0612-124">Se la registrazione automatica è configurata, la nota spese viene elaborata per il pagamento e il relativo stato viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="e0612-124">If automatic posting is configured, the expense report is processed for payment, and the status of the expense report is updated.</span></span>
    - <span data-ttu-id="e0612-125">In caso contrario, il coordinatore della contabilità fornitori verifica che tutte le ricevute originali siano state inviate e che siano allineate alle spese nella nota spese.</span><span class="sxs-lookup"><span data-stu-id="e0612-125">If automatic posting isn't configured, the Accounts payable coordinator verifies that all original receipts have been submitted, and that the receipts are aligned with the expenses on the expense report.</span></span> <span data-ttu-id="e0612-126">È inoltre necessario verificare che tutti i codici imposta immessi nella nota spese siano corretti.</span><span class="sxs-lookup"><span data-stu-id="e0612-126">All tax codes that are entered on the expense report must also be verified as correct.</span></span>

<span data-ttu-id="e0612-127">In seguito alla verifica dei requisiti, la nota spese viene registrata.</span><span class="sxs-lookup"><span data-stu-id="e0612-127">After these requirements are verified, the expense report is posted.</span></span>

<span data-ttu-id="e0612-128">Dopo la registrazione della nota spese, il pagamento viene autorizzato e il dipendente viene rimborsato.</span><span class="sxs-lookup"><span data-stu-id="e0612-128">After the expense report is posted, payment is authorized for the expense report, and the employee is reimbursed.</span></span>
