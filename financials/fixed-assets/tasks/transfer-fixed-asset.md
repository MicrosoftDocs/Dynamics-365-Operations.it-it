--- 
title: Trasferire un cespite
description: "Questa guida attività trasferirà le informazioni finanziarie per un libro cespiti da un set di dimensioni finanziarie in un nuovo set di dimensioni finanziarie."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b193cf6fbed810f0d5234514573d0f5c23c7b2c8
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="transfer-a-fixed-asset"></a><span data-ttu-id="0eaff-103">Trasferire un cespite</span><span class="sxs-lookup"><span data-stu-id="0eaff-103">Transfer a fixed asset</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0eaff-104">Questa guida attività trasferirà le informazioni finanziarie per un libro cespiti da un set di dimensioni finanziarie in un nuovo set di dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="0eaff-104">This task guide will transfer the financial information for a fixed asset book from one financial dimension set to a new financial dimension set.</span></span>  <span data-ttu-id="0eaff-105">Utilizza il ruolo Ragioniere e i dati dimostrativi per la persona giuridica USMF.</span><span class="sxs-lookup"><span data-stu-id="0eaff-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="0eaff-106">Passare a Cespiti > Cespiti > Cespiti.</span><span class="sxs-lookup"><span data-stu-id="0eaff-106">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="0eaff-107">Nell'elenco, individuare e selezionare il cespite da trasferire.</span><span class="sxs-lookup"><span data-stu-id="0eaff-107">In the list, find and select the fixed asset to transfer.</span></span>
3. <span data-ttu-id="0eaff-108">Nel riquadro azioni fare clic su Cespite.</span><span class="sxs-lookup"><span data-stu-id="0eaff-108">On the Action Pane, click Fixed asset.</span></span>
4. <span data-ttu-id="0eaff-109">Fare clic su Trasferisci cespiti.</span><span class="sxs-lookup"><span data-stu-id="0eaff-109">Click Transfer fixed assets.</span></span>
5. <span data-ttu-id="0eaff-110">Nel campo Data di trasferimento immettere una data.</span><span class="sxs-lookup"><span data-stu-id="0eaff-110">In the Transfer date field, enter a date.</span></span>
6. <span data-ttu-id="0eaff-111">Immettere i commenti per descrivere il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="0eaff-111">Enter comments to describe the transfer.</span></span>
    * <span data-ttu-id="0eaff-112">In questo elenco vengono visualizzati tutti i libri per il cespite.</span><span class="sxs-lookup"><span data-stu-id="0eaff-112">This list shows all books for the fixed asset.</span></span>  
7. <span data-ttu-id="0eaff-113">Contrassegnare i libri da trasferire in un nuovo set di dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="0eaff-113">Mark the books you want to transfer to a new financial dimension set.</span></span>
    * <span data-ttu-id="0eaff-114">In questo elenco vengono visualizzati i valori di dimensione finanziaria esistenti per il libro selezionato.</span><span class="sxs-lookup"><span data-stu-id="0eaff-114">This list shows the existing financial dimension values for the selected book.</span></span>  
    * <span data-ttu-id="0eaff-115">Selezionare la dimensione finanziaria da aggiornare per il libro cespiti selezionato.</span><span class="sxs-lookup"><span data-stu-id="0eaff-115">Select the financial dimension you want to update for the selected fixed asset book.</span></span>  
8. <span data-ttu-id="0eaff-116">Nel campo Dimensione finanziaria fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="0eaff-116">In the Financial dimension field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="0eaff-117">Impostare altri valori di dimensione finanziaria in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="0eaff-117">Set other financial dimension values as appropriate.</span></span>  
    * <span data-ttu-id="0eaff-118">Tutti i valori di dimensione finanziaria vengono modificati quando avviene un trasferimento, sia che il valore sia stato immesso o lasciato vuoto.</span><span class="sxs-lookup"><span data-stu-id="0eaff-118">All financial dimension values change when a transfer occurs, whether a value has been entered or left blank.</span></span> <span data-ttu-id="0eaff-119">Ad esempio, se è stato immesso un valore per il BusinessUnit e sono stati lasciati vuoti dimensioni finanziarie Reparto e CostCenter.</span><span class="sxs-lookup"><span data-stu-id="0eaff-119">For example, if you entered a value for the BusinessUnit and left the CostCenter and Department financial dimensions blank.</span></span> <span data-ttu-id="0eaff-120">Se la struttura dei conti consente valori vuoti per CostCenter e Reparto, il trasferimento determinerà che ciascun modello di valore abbia il nuovo valore per BusinessUnit e un valore vuoto per CostCenter e Reparto.</span><span class="sxs-lookup"><span data-stu-id="0eaff-120">If your account structure allows blank values for CostCenter and Department, the transfer would result in each value model having the new value for BusinessUnit and a blank value for CostCenter and Department.</span></span>  
9. <span data-ttu-id="0eaff-121">Fare clic su Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="0eaff-121">Click Update.</span></span>
    * <span data-ttu-id="0eaff-122">Si ha l'opportunità di visualizzare l'anteprima delle modifiche prima di finalizzare il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="0eaff-122">You have the opportunity to preview the changes before finalizing the transfer.</span></span>  
    * <span data-ttu-id="0eaff-123">Esaminare i risultati prima di trasferire i libri cespiti.</span><span class="sxs-lookup"><span data-stu-id="0eaff-123">Review results before transferring the fixed asset books.</span></span>  
10. <span data-ttu-id="0eaff-124">Fare clic su Trasferisci.</span><span class="sxs-lookup"><span data-stu-id="0eaff-124">Click Transfer.</span></span>

