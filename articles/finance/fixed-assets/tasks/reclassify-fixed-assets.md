---
title: Riclassifica i cespiti
description: Per riclassificare un cespite, è necessario trasferirlo in un nuovo gruppo cespite o assegnare al cespite un nuovo numero nello stesso gruppo.
author: saraschi2
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fbfb754459fad1f3b1509f4f9c65c20e0385b013
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944715"
---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="d3a3a-103">Riclassifica i cespiti</span><span class="sxs-lookup"><span data-stu-id="d3a3a-103">Reclassify fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d3a3a-104">Per riclassificare un cespite, è necessario trasferirlo in un nuovo gruppo cespite o assegnare al cespite un nuovo numero nello stesso gruppo.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="d3a3a-105">Quando un cespite viene riclassificato:</span><span class="sxs-lookup"><span data-stu-id="d3a3a-105">When a fixed asset is reclassified:</span></span>

- <span data-ttu-id="d3a3a-106">Per il nuovo cespite vengono creati tutti i libri del cespite esistente.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-106">All books for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="d3a3a-107">Le informazioni impostate per il cespite originario vengono copiate nel nuovo cespite.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="d3a3a-108">Lo stato dei libri del cespite originario è Chiuso.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-108">The status of the books for the original fixed asset is Closed.</span></span> 

- <span data-ttu-id="d3a3a-109">Nei nuovi libri del nuovo cespite è contenuta la data di riclassificazione presente nel campo **Data di acquisizione**.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-109">The new books for the new fixed asset contain the date of the reclassification in the **Acquisition date** field.</span></span> <span data-ttu-id="d3a3a-110">La data nel campo **Data esecuzione ammortamento** viene copiata dalle informazioni relative al cespite originario.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-110">The date in the **Depreciation run date** field is copied from the original asset information.</span></span> <span data-ttu-id="d3a3a-111">Se l'ammortamento è già iniziato, nel campo **Data ultimo ammortamento** viene visualizzata la data di riclassificazione.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-111">If the depreciation has already started, the **Date when depreciation was last run** field displays the date of the reclassification.</span></span> 

- <span data-ttu-id="d3a3a-112">Le transazioni cespiti esistenti per il cespite originario vengono annullate e rigenerate per il nuovo cespite.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-112">The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

- <span data-ttu-id="d3a3a-113">Quando un cespite che ha una transazione di trasferimento è stato riclassificato, il sistema visualizzerà un messaggio nel **Centro azioni** per indicare che una transazione di trasferimento non è stata completata durante il processo di riclassificazione.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-113">When an asset that has a transfer transaction has been reclassified, the system will display a message in the **Action center** to indicate that a transfer transaction wasn't completed during the reclassification process.</span></span> <span data-ttu-id="d3a3a-114">È necessario completare una transazione di trasferimento per spostare le transazioni di riclassificazione esistenti nelle dimensioni finanziarie appropriate.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-114">It's necessary to complete a transfer transaction to move the existing reclassification transactions to the appropriate financial dimensions.</span></span> 

   <span data-ttu-id="d3a3a-115">Durante il processo di riclassificazione, il sistema esegue le seguenti azioni per riclassificare il saldo cespiti dal cespite originale al nuovo.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-115">During the reclassification process, the system runs the following actions to reclassify the asset balance from the original asset to the new asset.</span></span> 
   
   - <span data-ttu-id="d3a3a-116">Il processo di riclassificazione copia i dati dal libro cespiti originale al nuovo libro cespiti.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-116">The reclassification process copies the data from the original fixed asset book to the new fixed asset book.</span></span>

   - <span data-ttu-id="d3a3a-117">La transazione di riclassificazione utilizza le informazioni dall'acquisizione registrata originale che include le informazioni sulla dimensione finanziaria incluse nella transazione di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-117">The reclassification transaction uses information from the original posted acquisition that includes financial dimension information that is included in the acquisition transaction.</span></span>  
   
   - <span data-ttu-id="d3a3a-118">Allo stesso tempo, il processo di riclassificazione storna le transazioni di acquisizione e trasferimento cespite originali.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-118">At the same time, the reclassification process reverses the original asset acquisition and asset transfer transaction.</span></span> 

<span data-ttu-id="d3a3a-119">Il diagramma e la procedura seguenti forniscono un esempio del processo di riclassificazione.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-119">The following diagram and procedure provide an example of the reclassification process.</span></span> 

<span data-ttu-id="d3a3a-120">[![Diagramma che mostra il processo di riclassificazione](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)</span><span class="sxs-lookup"><span data-stu-id="d3a3a-120">[![Diagram showing the reclassicification process](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)</span></span>

<span data-ttu-id="d3a3a-121">Seguire questi passaggi per riclassificare un cespite:</span><span class="sxs-lookup"><span data-stu-id="d3a3a-121">Follow these steps to reclassify a fixed asset:</span></span>

1. <span data-ttu-id="d3a3a-122">Passare a **Cespiti > Attività periodiche > Riclassificazione**.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-122">Go to **Fixed assets > Periodic tasks > Reclassification.**</span></span>
2. <span data-ttu-id="d3a3a-123">Nel campo **Gruppo cespite** selezionare il gruppo da riclassificare.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-123">In the **Fixed asset group** field, select the group to reclassify.</span></span>
3. <span data-ttu-id="d3a3a-124">Nel campo **Numero cespite** selezionare il cespite da riclassificare.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-124">In the **Fixed asset number** field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="d3a3a-125">Nel campo **Nuovo gruppo cespite**, selezionare un gruppo in cui trasferire il cespite.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-125">In the **New fixed asset group** field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="d3a3a-126">Se il nuovo gruppo cespite è collegato a una sequenza numerica, il campo **Nuovo numero cespite** verrà aggiornato con il numero della sequenza numerica del nuovo gruppo cespite.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-126">If the new fixed asset group is attached to a number sequence, the **New fixed asset number** field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="d3a3a-127">In caso contrario, il campo **Nuovo numero cespite** viene aggiornato con il numero della sequenza numerica impostata nella pagina **Parametri cespite**.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-127">Otherwise, the **New fixed asset number** field is updated with the number from the number sequence that is set up on the **Fixed asset parameters** page.</span></span> <span data-ttu-id="d3a3a-128">Se una sequenza numerica non è configurata nella pagina **Parametri cespite**, immettere un numero nel campo **Nuovo numero cespite**.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-128">If a number sequence is not set up on the **Fixed asset parameters** page, enter a number in the **New fixed asset number** field.</span></span>  
5. <span data-ttu-id="d3a3a-129">Immettere una data nel campo **Riclassificazione**.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-129">In the **Reclassification date** field, enter a date.</span></span>
6. <span data-ttu-id="d3a3a-130">Nel campo **Serie giustificativi** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-130">In the **Voucher series** field, enter or select a value.</span></span>
7. <span data-ttu-id="d3a3a-131">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3a3a-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
