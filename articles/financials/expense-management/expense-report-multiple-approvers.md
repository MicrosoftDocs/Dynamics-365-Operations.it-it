---
title: "Note spese e più approvatori"
description: "In questo argomento vengono fornite informazioni sui report di spesa che richiedono l'approvazione da parte di più persone."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvExpensesReportList
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 0f7592c580a21040c8b630885939ceaab3855c2c
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2018

---

# <a name="expense-reports-and-multiple-approvers"></a><span data-ttu-id="cbcf9-103">Note spese e più approvatori</span><span class="sxs-lookup"><span data-stu-id="cbcf9-103">Expense reports and multiple approvers</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="cbcf9-104">In base ai criteri di approvazione di spesa dell'organizzazione, potrebbe essere necessario che più di una persona approvi una nota spese che viene inviata da un dipendente.</span><span class="sxs-lookup"><span data-stu-id="cbcf9-104">Depending on your organization's expense approval policies, more than one person might have to approve an expense report that is submitted by an employee.</span></span> <span data-ttu-id="cbcf9-105">Quando si imposta il processo del flusso di lavoro per l'approvazione della nota spese, è possibile aggiungere elementi del flusso di lavoro che includono le attività o le operazioni per uno o più approvatori della nota spese.</span><span class="sxs-lookup"><span data-stu-id="cbcf9-105">When you set up the workflow process for expense report approval, you can add workflow elements that include tasks or steps for one or more expense report approvers.</span></span> <span data-ttu-id="cbcf9-106">Ad esempio, è possibile richiedere che tutte le note spese vengano approvate prima dall'amministratore del dipendente che ha inviato il report e quindi dal coordinatore della contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="cbcf9-106">For example, you might require that all expense reports be approved first by the manager of the employee who submitted the report and then by the Accounts payable coordinator.</span></span>

<span data-ttu-id="cbcf9-107">Se si decide di richiedere più approvatori della nota spese, è possibile aggiungere elementi del flusso di lavoro in uno dei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="cbcf9-107">If you decide to require multiple expense report approvers, you can add the workflow elements in any of the following ways:</span></span>

- <span data-ttu-id="cbcf9-108">Aggiungere un elemento di approvazione che include un passaggio.</span><span class="sxs-lookup"><span data-stu-id="cbcf9-108">Add one approval element that has one step.</span></span> <span data-ttu-id="cbcf9-109">Ad esempio, il passaggio potrebbe richiedere che una nota spese venga assegnata a un gruppo di utenti e approvata dal 50 percento dei membri del gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="cbcf9-109">For example, the step might require that an expense report be assigned to a user group, and that it be approved by 50 percent of the user group's members.</span></span>
- <span data-ttu-id="cbcf9-110">Aggiungere un elemento di approvazione che include più passaggi.</span><span class="sxs-lookup"><span data-stu-id="cbcf9-110">Add one approval element that has multiple steps.</span></span> <span data-ttu-id="cbcf9-111">Ad esempio, l'elemento di approvazione potrebbe includere i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="cbcf9-111">For example, the approval element might have the following steps:</span></span>

    1. <span data-ttu-id="cbcf9-112">Il responsabile del dipendente che ha inviato la nota spese la approva.</span><span class="sxs-lookup"><span data-stu-id="cbcf9-112">The manager of the employee who submitted the expense report approves it.</span></span>
    2. <span data-ttu-id="cbcf9-113">Un addetto della contabilità fornitori verifica le ricevute e le voci della nota spese.</span><span class="sxs-lookup"><span data-stu-id="cbcf9-113">The Accounts payable clerk verifies the receipts and the expense report items.</span></span>
    3. <span data-ttu-id="cbcf9-114">Il proprietario del budget approva la nota spese.</span><span class="sxs-lookup"><span data-stu-id="cbcf9-114">The budget owner approves the expense report.</span></span>

- <span data-ttu-id="cbcf9-115">Aggiungere più elementi di approvazione, ciascuno dei quali include un passaggio.</span><span class="sxs-lookup"><span data-stu-id="cbcf9-115">Add multiple approval elements, each of which has one step.</span></span> <span data-ttu-id="cbcf9-116">Ad esempio, è possibile aggiungere un elemento di approvazione distinto per ognuno dei seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="cbcf9-116">For example, you might add a separate approval element for each of the following steps:</span></span>

    1. <span data-ttu-id="cbcf9-117">Il manager del dipendente approva la nota spese.</span><span class="sxs-lookup"><span data-stu-id="cbcf9-117">The employee's manager approves the expense report.</span></span>
    2. <span data-ttu-id="cbcf9-118">Il proprietario del budget approva la nota spese.</span><span class="sxs-lookup"><span data-stu-id="cbcf9-118">The budget owner approves the expense report.</span></span>

