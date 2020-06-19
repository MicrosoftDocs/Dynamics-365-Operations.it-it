---
title: Gestire gli articoli affidati ai lavoratori
description: Gli articoli prestito sono record che consentono ai responsabili di tenere traccia degli articoli fisici che la società presta ai lavoratori.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmLoanItem, HcmLoanType, HcmPersonLoan, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 3581
ms.assetid: b14bdddb-f10e-4619-9f91-8c88439da862
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 5915df388da7ce8b90cdcb0e859268c00003110c
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429315"
---
# <a name="manage-items-that-are-lent-to-workers"></a><span data-ttu-id="076e3-103">Gestire gli articoli affidati ai lavoratori</span><span class="sxs-lookup"><span data-stu-id="076e3-103">Manage items that are lent to workers</span></span>

<span data-ttu-id="076e3-104">Gli articoli prestito sono record che consentono ai responsabili di tenere traccia degli articoli fisici che la società presta ai lavoratori.</span><span class="sxs-lookup"><span data-stu-id="076e3-104">Loan items are records that help managers track the physical items that your company lends to its workers.</span></span> 

<span data-ttu-id="076e3-105">I punti di seguito sono esempi di articoli che una società potrebbe prestare ai lavoratori:</span><span class="sxs-lookup"><span data-stu-id="076e3-105">The following points list examples of items that a company might lend to workers:</span></span>
-   <span data-ttu-id="076e3-106">Telefoni cellulari</span><span class="sxs-lookup"><span data-stu-id="076e3-106">Mobile telephones</span></span>
-   <span data-ttu-id="076e3-107">Automobili</span><span class="sxs-lookup"><span data-stu-id="076e3-107">Automobiles</span></span>
-   <span data-ttu-id="076e3-108">Attrezzature informatiche</span><span class="sxs-lookup"><span data-stu-id="076e3-108">Computer equipment</span></span>

<span data-ttu-id="076e3-109">Ogni articolo fisico deve avere un articolo prestito corrispondente.</span><span class="sxs-lookup"><span data-stu-id="076e3-109">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="076e3-110">Per ciascun record di articolo prestito dovranno essere descritti la tipologia, il responsabile del prestito e la durata in giorni consentita per il prestito.</span><span class="sxs-lookup"><span data-stu-id="076e3-110">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can loaned to a worker.</span></span> <span data-ttu-id="076e3-111">È possibile creare più articoli prestito, ad esempio chiavi, schede di accesso o divise, contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="076e3-111">You can create multiple loan items, for items such as keys, access cards or uniforms, at the same time.</span></span> 

<span data-ttu-id="076e3-112">Quando un articolo viene concesso in prestito, è necessario immettere la data di inizio del prestito e la data di restituzione pianificata.</span><span class="sxs-lookup"><span data-stu-id="076e3-112">When loaning an item, enter the date that the item was loaned, and the planned return date.</span></span> <span data-ttu-id="076e3-113">Quando l'articolo viene restituito, immettere la data di restituzione effettiva.</span><span class="sxs-lookup"><span data-stu-id="076e3-113">When the item is returned, enter the actual return date.</span></span>

<span data-ttu-id="076e3-114">I dipendenti possono visualizzare i record degli articoli che sono stati prestati utilizzando area di lavoro Dipendente self-service.</span><span class="sxs-lookup"><span data-stu-id="076e3-114">Employees can view the records of the items that have been loaned to them using the Employee self-service workspace.</span></span> <span data-ttu-id="076e3-115">Possono inoltre modificare i record esistenti o immettere nuovi articoli prestito,se hanno ricevuto articoli fisici aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="076e3-115">They can also edit the existing records or enter new loan items, if they've received additional physical items.</span></span>  <span data-ttu-id="076e3-116">Il flusso di lavoro può essere configurato in modo da instradare le modifiche ai nuovi o esistenti articoli prestito tramite un processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="076e3-116">Workflow can be set up to route changes to new or existing loan items through an approval process.</span></span> 

<span data-ttu-id="076e3-117">I responsabili possono visualizzare gli articoli prestati per i propri subordinati diretti.</span><span class="sxs-lookup"><span data-stu-id="076e3-117">Managers can view loaned items for their direct reports.</span></span> <span data-ttu-id="076e3-118">Può anche essere concessa l'autorizzazione per aggiungere nuovi articoli in prestito per conto dei relativi dipendenti.</span><span class="sxs-lookup"><span data-stu-id="076e3-118">They can also be granted permission to add new loan items on behalf of their employees.</span></span>

 <a name="account-for-lost-or-misplaced-loan-items"></a><span data-ttu-id="076e3-119">Conto per articoli prestito spostati o andati perduti</span><span class="sxs-lookup"><span data-stu-id="076e3-119">Account for lost or misplaced loan items</span></span>
-----------------------------------------

<span data-ttu-id="076e3-120">Se un articolo viene non correttamente collocato o danneggiato, immettere una restituzione fittizia.</span><span class="sxs-lookup"><span data-stu-id="076e3-120">If an item becomes damaged or misplaced, enter a fictitious return record.</span></span> <span data-ttu-id="076e3-121">Successivamente sarà possibile eliminare l'articolo oppure mantenerlo della panoramica e modificare la relativa descrizione per segnalare che non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="076e3-121">Then either delete the item or keep it in the overview and change the description to indicate that the item is not available.</span></span>


<a name="additional-resources"></a><span data-ttu-id="076e3-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="076e3-122">Additional resources</span></span>
--------

[<span data-ttu-id="076e3-123">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="076e3-123">Human resources</span></span>](index.md)



