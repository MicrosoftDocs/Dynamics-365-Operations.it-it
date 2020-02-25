---
title: " Elaborare correzioni punti fedeltà"
description: Questa procedura dimostra come individuare le informazioni sulla carta fedeltà e rettificare i punti premio fedeltà.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailLoyaltyCards, RetailLoyaltyCardRewardPointTrans, RetailLoyaltyCardRewardPointAdjustment, RetailAffiliationLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e767ca571255bcf583b83c6e300292552a96a38
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023022"
---
# <a name="process-loyalty-reward-point-adjustments"></a><span data-ttu-id="ea819-103"> Elaborare correzioni punti fedeltà</span><span class="sxs-lookup"><span data-stu-id="ea819-103">Process loyalty reward point adjustments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="ea819-104">Questa procedura dimostra come individuare le informazioni sulla carta fedeltà e rettificare i punti premio fedeltà.</span><span class="sxs-lookup"><span data-stu-id="ea819-104">This procedure demonstrates how to look up loyalty card information and adjust loyalty reward points.</span></span> <span data-ttu-id="ea819-105">La società di dati dimostrativi utilizzata per creare questa attività è USRT.</span><span class="sxs-lookup"><span data-stu-id="ea819-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="ea819-106">Questa attività è destinata al ruolo Responsabile operativo commercio o Responsabile assistenza clienti.</span><span class="sxs-lookup"><span data-stu-id="ea819-106">This task is intended for the Commerce operations manager role or a Customer service manager role.</span></span>

1. <span data-ttu-id="ea819-107">Passare a Carte fedeltà.</span><span class="sxs-lookup"><span data-stu-id="ea819-107">Go to Loyalty cards.</span></span>
2. <span data-ttu-id="ea819-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ea819-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ea819-109">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ea819-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ea819-110">Fare clic su Transazioni carte.</span><span class="sxs-lookup"><span data-stu-id="ea819-110">Click Card transactions.</span></span>
    * <span data-ttu-id="ea819-111">In questa pagina è possibile visualizzare tutte le transazioni di fedeltà della carta fedeltà selezionata.</span><span class="sxs-lookup"><span data-stu-id="ea819-111">On this page you can view all loyalty transactions for the selected loyalty card.</span></span>  
5. <span data-ttu-id="ea819-112">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ea819-112">Close the page.</span></span>
6. <span data-ttu-id="ea819-113">Fare clic su Rettifiche carta.</span><span class="sxs-lookup"><span data-stu-id="ea819-113">Click Card adjustments.</span></span>
7. <span data-ttu-id="ea819-114">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ea819-114">Click New.</span></span>
8. <span data-ttu-id="ea819-115">Nel campo Punto premio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ea819-115">In the Reward point field, enter or select a value.</span></span>
9. <span data-ttu-id="ea819-116">Nel campo Importo o quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ea819-116">In the Amount or quantity field, enter a number.</span></span>
    * <span data-ttu-id="ea819-117">È possibile aggiungere o rimuovere i punti della carta fedeltà utilizzando gli importi positivi o negativi.</span><span class="sxs-lookup"><span data-stu-id="ea819-117">You can add or remove points from the loyalty card by using positive or negative amounts.</span></span>  
10. <span data-ttu-id="ea819-118">Nel campo Programma fedeltà immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ea819-118">In the Loyalty program field, enter or select a value.</span></span>
11. <span data-ttu-id="ea819-119">Digitare un valore nel campo Commento.</span><span class="sxs-lookup"><span data-stu-id="ea819-119">In the Comment field, type a value.</span></span>
12. <span data-ttu-id="ea819-120">Fare clic su Registra rettifica.</span><span class="sxs-lookup"><span data-stu-id="ea819-120">Click Post adjustment.</span></span>
13. <span data-ttu-id="ea819-121">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="ea819-121">Click Yes.</span></span>
14. <span data-ttu-id="ea819-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ea819-122">Close the page.</span></span>
    * <span data-ttu-id="ea819-123">Generalmente in questa fase si aggiorna la pagina per visualizzare il risultato della rettifica dei punti premio nella scheda Riepilogo punti premio. Se invece si esegue la fase come guida attività, non aggiornare ora perché altrimenti la guida attività verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="ea819-123">Normally at this point you'd refresh the page to see the result of the reward points adjustment in the Reward point summary tab. But if you are running this as a task guide, don't refresh now because if you do, the task guide will stop.</span></span>  
15. <span data-ttu-id="ea819-124">Fare clic su Transazioni carte.</span><span class="sxs-lookup"><span data-stu-id="ea819-124">Click Card transactions.</span></span>
16. <span data-ttu-id="ea819-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ea819-125">Close the page.</span></span>

