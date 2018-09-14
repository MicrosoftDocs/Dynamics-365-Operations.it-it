--- 
title: Creare tipi di sollecito e criteri di assegnazione punteggi per RdO
description: Questa guida vi mostra come creare un tipo di sollecito ed associarlo a un metodo di assegnazione del punteggio.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 14fd7d0bfa17427883f97c5e0a72044016d4965e
ms.contentlocale: it-it
ms.lasthandoff: 09/14/2018

---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a><span data-ttu-id="fb4d3-103">Creare tipi di sollecito e criteri di assegnazione punteggi per RdO</span><span class="sxs-lookup"><span data-stu-id="fb4d3-103">Create solicitation types and scoring criteria for RFQs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fb4d3-104">Questa guida vi mostra come creare un tipo di sollecito ed associarlo a un metodo di assegnazione del punteggio.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-104">This guide shows you how to create a solicitation type and associate this with a scoring method.</span></span> <span data-ttu-id="fb4d3-105">Inoltre mostra come usare il tipo di sollecito per una richiesta di offerta (RdO), che poi imposta il metodo di assegnazione del punteggio predefinito.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-105">It also shows how to use the solicitation type on a request for quotation (RFQ) which then sets the default scoring method.</span></span> <span data-ttu-id="fb4d3-106">Queste attività verranno in genere svolte da un responsabile degli acquisti.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-106">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="fb4d3-107">È necessario impostare le classificazioni del contratto di acquisto prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="fb4d3-108">Dovete avere un metodo di assegnazione del punteggio disponibile prima che cominciate.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-108">You need to have a scoring method available before you start.</span></span>


## <a name="create-a-solicitation-type"></a><span data-ttu-id="fb4d3-109">Creare un tipo di sollecito.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-109">Create a solicitation type</span></span>
1. <span data-ttu-id="fb4d3-110">Andare a Approvvigionamento > Impostazioni > Richiesta di offerta > Tipo di sollecito.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-110">Go to Procurement and sourcing > Setup > Request for quotation > Solicitation type.</span></span>
2. <span data-ttu-id="fb4d3-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-111">Click New.</span></span>
3. <span data-ttu-id="fb4d3-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="fb4d3-113">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fb4d3-114">Nel campo Metodo di assegnazione del punteggio selezionare il metodo che si desidera utilizzare per questo tipo di sollecito.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-114">In the Scoring method field, select the scoring method that you want to use for this solicitation type.</span></span>
6. <span data-ttu-id="fb4d3-115">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-115">Click Save.</span></span>
7. <span data-ttu-id="fb4d3-116">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-116">Close the page.</span></span>

## <a name="use-the-solicitation-type"></a><span data-ttu-id="fb4d3-117">Usare il tipo di sollecito</span><span class="sxs-lookup"><span data-stu-id="fb4d3-117">Use the solicitation type</span></span>
1. <span data-ttu-id="fb4d3-118">Andare ad Approvvigionamento > Richieste di offerta > Tutte le richieste di offerta.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-118">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="fb4d3-119">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-119">Click New.</span></span>
3. <span data-ttu-id="fb4d3-120">Nel campo Tipo di sollecito, selezionare il tipo di sollecito che avete creato appena.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-120">In the Solicitation type field, select the solicitation type that you have just created.</span></span> 
    *   
4. <span data-ttu-id="fb4d3-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-121">Click OK.</span></span>
5. <span data-ttu-id="fb4d3-122">Fare clic su Criteri di assegnazione del punteggio.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-122">Click Scoring criteria.</span></span>
    * <span data-ttu-id="fb4d3-123">I criteri di assegnazione del punteggio indicati sono quelli del metodo di assegnazione punteggio associato con il tipo di sollecito.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-123">The scoring criteria that are shown are the ones from the scoring method that you associated with the solicitation type.</span></span> <span data-ttu-id="fb4d3-124">Potete scegliere di aggiungere o eliminare i criteri in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-124">You can choose to add or delete criteria on this page.</span></span> <span data-ttu-id="fb4d3-125">È inoltre possibile aggiungere nuovi criteri copiandoli da altri metodi di assegnazione del punteggio.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-125">It's also possible to add new criteria by copying them from other scoring methods.</span></span>  
6. <span data-ttu-id="fb4d3-126">Fare clic su Copia criteri.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-126">Click Copy criteria.</span></span>
7. <span data-ttu-id="fb4d3-127">Nel campo Metodo di assegnazione del punteggio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-127">In the Scoring method field, enter or select a value.</span></span>
8. <span data-ttu-id="fb4d3-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-128">Click OK.</span></span>
9. <span data-ttu-id="fb4d3-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fb4d3-129">Close the page.</span></span>


