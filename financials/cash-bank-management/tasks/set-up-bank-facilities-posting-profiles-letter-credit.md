--- 
title: Impostare le linee di credito bancarie e i profili registrazione per la lettera di credito
description: Questa procedura consente di creare una linea di credito bancaria e di registrare un profilo necessari per elaborare le lettere di credito.
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a5c68feeb163e09f183c49afea24d2f9e5999594
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a><span data-ttu-id="2d7a6-103">Impostare le linee di credito bancarie e i profili registrazione per la lettera di credito</span><span class="sxs-lookup"><span data-stu-id="2d7a6-103">Set up bank facilities and posting profiles for letter of credit</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2d7a6-104">Questa procedura consente di creare una linea di credito bancaria e di registrare un profilo necessari per elaborare le lettere di credito.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-104">This procedure walks through creating a Bank facility and posting profile required to process Letters of credit.</span></span> 

<span data-ttu-id="2d7a6-105">In questa attività viene utilizzata la società dimostrativa "USMF".</span><span class="sxs-lookup"><span data-stu-id="2d7a6-105">This tasks uses the demo company 'USMF'.</span></span>






## <a name="general-ledger-parameter"></a><span data-ttu-id="2d7a6-106">Parametro di contabilità generale</span><span class="sxs-lookup"><span data-stu-id="2d7a6-106">General ledger parameter</span></span>
1. <span data-ttu-id="2d7a6-107">Andare a Gestione cassa e banche > Impostazioni > Parametri di gestione cassa e banche.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="2d7a6-108">Espandere la sezione Documento bancario.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="2d7a6-109">Selezionare l'opzione Abilita lettera di credito di importazione.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-109">Select the Enable import letter of credit option.</span></span>
4. <span data-ttu-id="2d7a6-110">Selezionare l'opzione Abilita lettera di credito di esportazione.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-110">Select the Enable export letter of credit option.</span></span>
5. <span data-ttu-id="2d7a6-111">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-111">Click Save.</span></span>
6. <span data-ttu-id="2d7a6-112">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-112">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="2d7a6-113">Creare una linea di credito bancaria</span><span class="sxs-lookup"><span data-stu-id="2d7a6-113">Create Bank facility</span></span>
1. <span data-ttu-id="2d7a6-114">Andare a Gestione cassa e banche > Impostazioni > Linee di credito bancarie.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-114">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="2d7a6-115">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-115">Click New.</span></span>
3. <span data-ttu-id="2d7a6-116">Nel campo Gruppo di linee di credito immettere il nome del gruppo di linee di credito bancarie.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-116">In the Facility group field, enter the bank facility group name.</span></span>
4. <span data-ttu-id="2d7a6-117">Nel campo Descrizione immettere la descrizione del gruppo di linee di credito bancarie.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-117">In the Description field, enter the bank facility group description.</span></span>
5. <span data-ttu-id="2d7a6-118">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-118">Click Save.</span></span>
6. <span data-ttu-id="2d7a6-119">Fare clic sulla scheda Tipi di linee di credito.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-119">Click the Facility types tab.</span></span>
7. <span data-ttu-id="2d7a6-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-120">Click New.</span></span>
8. <span data-ttu-id="2d7a6-121">Nel campo Tipi di linee di credito immettere un codice univoco.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-121">In the Facility type field, enter a unique code.</span></span>
9. <span data-ttu-id="2d7a6-122">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="2d7a6-123">Nel campo Gruppo di linee di credito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-123">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="2d7a6-124">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="2d7a6-125">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-125">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="2d7a6-126">Nel campo Natura linea di credito selezionare la natura della linea di credito bancaria.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-126">In the Facility nature field, select the nature of the bank facility.</span></span>
14. <span data-ttu-id="2d7a6-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-127">Click Save.</span></span>
15. <span data-ttu-id="2d7a6-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-128">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="2d7a6-129">Profilo di registrazione bancaria</span><span class="sxs-lookup"><span data-stu-id="2d7a6-129">Bank posting profile</span></span>
1. <span data-ttu-id="2d7a6-130">Andare a Gestione cassa e banche > Impostazioni > Profilo di registrazione documenti bancari.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-130">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="2d7a6-131">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-131">Click New.</span></span>
3. <span data-ttu-id="2d7a6-132">Nel campo Numero conto/gruppo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-132">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="2d7a6-133">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-133">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="2d7a6-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-134">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2d7a6-135">Selezionare il conto principale per la liquidazione.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-135">Select the main account for settlement.</span></span>
    * <span data-ttu-id="2d7a6-136">Tale conto viene utilizzato per il calcolo della previsione di cassa.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-136">This account is used when calculating cash flow forecast.</span></span>  
7. <span data-ttu-id="2d7a6-137">Nel campo Conto spese selezionare il conto per le transazioni di spesa.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-137">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="2d7a6-138">Nel campo Conto a margine selezionare il conto per le transazioni a margine.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-138">In the Margin account field, select the account for margin transactions.</span></span>
    * <span data-ttu-id="2d7a6-139">Su questo conto viene effettuato un addebito quando il margine iniziale viene registrato e accreditato al momento della registrazione del pagamento.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-139">This account is debited when the opening margin is posted and credited when the payment is posted.</span></span>  
9. <span data-ttu-id="2d7a6-140">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2d7a6-140">Click Save.</span></span>

