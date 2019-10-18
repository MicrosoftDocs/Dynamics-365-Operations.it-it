---
title: Trasferire un cespite
description: Questa guida attività trasferirà le informazioni finanziarie per un libro cespiti da un set di dimensioni finanziarie in un nuovo set di dimensioni finanziarie.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 167591cf160916f256e2d10f122eca312ba07639
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186833"
---
# <a name="transfer-a-fixed-asset"></a><span data-ttu-id="f3266-103">Trasferire un cespite</span><span class="sxs-lookup"><span data-stu-id="f3266-103">Transfer a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f3266-104">Questa guida attività trasferirà le informazioni finanziarie per un libro cespiti da un set di dimensioni finanziarie in un nuovo set di dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="f3266-104">This task guide will transfer the financial information for a fixed asset book from one financial dimension set to a new financial dimension set.</span></span>  <span data-ttu-id="f3266-105">Utilizza il ruolo Ragioniere e i dati dimostrativi per la persona giuridica USMF.</span><span class="sxs-lookup"><span data-stu-id="f3266-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="f3266-106">Nel pannello di navigazione, passare a **Moduli > Cespiti > Cespiti > Cespiti**.</span><span class="sxs-lookup"><span data-stu-id="f3266-106">In the Navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="f3266-107">Nell'elenco, individuare e selezionare il cespite da trasferire.</span><span class="sxs-lookup"><span data-stu-id="f3266-107">In the list, find and select the fixed asset to transfer.</span></span>
3. <span data-ttu-id="f3266-108">Nel riquadro azioni fare clic su **Cespite**.</span><span class="sxs-lookup"><span data-stu-id="f3266-108">On the Action Pane, click **Fixed asset**.</span></span>
4. <span data-ttu-id="f3266-109">Fare clic su **Trasferisci cespiti**.</span><span class="sxs-lookup"><span data-stu-id="f3266-109">Click **Transfer fixed assets**.</span></span>
5. <span data-ttu-id="f3266-110">Nel campo **Data di trasferimento** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="f3266-110">In the **Transfer date** field, enter a date.</span></span>
6. <span data-ttu-id="f3266-111">Immettere i commenti per descrivere il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="f3266-111">Enter comments to describe the transfer.</span></span>
    
    <span data-ttu-id="f3266-112">In questo elenco vengono visualizzati tutti i libri per il cespite.</span><span class="sxs-lookup"><span data-stu-id="f3266-112">This list shows all books for the fixed asset.</span></span>  
7. <span data-ttu-id="f3266-113">Contrassegnare i libri da trasferire in un nuovo set di dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="f3266-113">Mark the books you want to transfer to a new financial dimension set.</span></span>
    * <span data-ttu-id="f3266-114">In questo elenco vengono visualizzati i valori di dimensione finanziaria esistenti per il libro selezionato.</span><span class="sxs-lookup"><span data-stu-id="f3266-114">This list shows the existing financial dimension values for the selected book.</span></span>  
    * <span data-ttu-id="f3266-115">Selezionare la dimensione finanziaria da aggiornare per il libro cespiti selezionato.</span><span class="sxs-lookup"><span data-stu-id="f3266-115">Select the financial dimension you want to update for the selected fixed asset book.</span></span>  
8. <span data-ttu-id="f3266-116">Nel campo **Dimensione finanziaria** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f3266-116">In the **Financial dimension** field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="f3266-117">Impostare altri valori di dimensione finanziaria in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="f3266-117">Set other financial dimension values as appropriate.</span></span>  
    * <span data-ttu-id="f3266-118">Tutti i valori di dimensione finanziaria vengono modificati quando avviene un trasferimento, sia che il valore sia stato immesso o lasciato vuoto.</span><span class="sxs-lookup"><span data-stu-id="f3266-118">All financial dimension values change when a transfer occurs, whether a value has been entered or left blank.</span></span> <span data-ttu-id="f3266-119">Ad esempio, se è stato immesso un valore per il BusinessUnit e sono stati lasciati vuoti dimensioni finanziarie Reparto e CostCenter.</span><span class="sxs-lookup"><span data-stu-id="f3266-119">For example, if you entered a value for the BusinessUnit and left the CostCenter and Department financial dimensions blank.</span></span> <span data-ttu-id="f3266-120">Se la struttura dei conti consente valori vuoti per CostCenter e Reparto, il trasferimento determinerà che ciascun modello di valore abbia il nuovo valore per BusinessUnit e un valore vuoto per CostCenter e Reparto.</span><span class="sxs-lookup"><span data-stu-id="f3266-120">If your account structure allows blank values for CostCenter and Department, the transfer would result in each value model having the new value for BusinessUnit and a blank value for CostCenter and Department.</span></span>  
9. <span data-ttu-id="f3266-121">Fare clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="f3266-121">Click **Update**.</span></span>
    * <span data-ttu-id="f3266-122">Si ha l'opportunità di visualizzare l'anteprima delle modifiche prima di finalizzare il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="f3266-122">You have the opportunity to preview the changes before finalizing the transfer.</span></span>  
    * <span data-ttu-id="f3266-123">Esaminare i risultati prima di trasferire i libri cespiti.</span><span class="sxs-lookup"><span data-stu-id="f3266-123">Review results before transferring the fixed asset books.</span></span>  
10. <span data-ttu-id="f3266-124">Fare clic su **Trasferisci**.</span><span class="sxs-lookup"><span data-stu-id="f3266-124">Click **Transfer**.</span></span>

