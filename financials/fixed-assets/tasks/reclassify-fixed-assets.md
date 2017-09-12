--- 
title: Riclassifica i cespiti
description: "Per riclassificare un cespite, è necessario trasferirlo in un nuovo gruppo cespite o assegnare al cespite un nuovo numero nello stesso gruppo."
author: saraschi2
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: aed171004a43adbc504d74eb02c36df824a3e649
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="5ff16-103">Riclassifica i cespiti</span><span class="sxs-lookup"><span data-stu-id="5ff16-103">Reclassify fixed assets</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5ff16-104">Per riclassificare un cespite, è necessario trasferirlo in un nuovo gruppo cespite o assegnare al cespite un nuovo numero nello stesso gruppo.</span><span class="sxs-lookup"><span data-stu-id="5ff16-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="5ff16-105">Quando un cespite viene riclassificato:</span><span class="sxs-lookup"><span data-stu-id="5ff16-105">When a fixed asset is reclassified:</span></span>

<span data-ttu-id="5ff16-106">• Per il nuovo cespite vengono creati tutti i modelli di valore del cespite esistente.</span><span class="sxs-lookup"><span data-stu-id="5ff16-106">• All value models for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="5ff16-107">Le informazioni impostate per il cespite originario vengono copiate nel nuovo cespite.</span><span class="sxs-lookup"><span data-stu-id="5ff16-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="5ff16-108">Lo stato dei modelli di valore del cespite originario è Chiuso.</span><span class="sxs-lookup"><span data-stu-id="5ff16-108">The status of the value models for the original fixed asset is Closed.</span></span> 

<span data-ttu-id="5ff16-109">• Nei nuovi modelli di valore del nuovo cespite è contenuta la data di riclassificazione presente nel campo Data di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="5ff16-109">• The new value models of the new fixed asset contain the date of the reclassification in the Acquisition date field.</span></span> <span data-ttu-id="5ff16-110">La data nel campo Data esecuzione ammortamento viene copiata dalle informazioni relative al cespite originario.</span><span class="sxs-lookup"><span data-stu-id="5ff16-110">The date in the Depreciation run date field is copied from the original asset information.</span></span> <span data-ttu-id="5ff16-111">Se l'ammortamento è già iniziato, nel campo Data ultimo ammortamento viene visualizzata la data di riclassificazione.</span><span class="sxs-lookup"><span data-stu-id="5ff16-111">If the depreciation has already started, the Date when depreciation was last run field displays the date of the reclassification.</span></span> 

<span data-ttu-id="5ff16-112">• Le transazioni cespiti esistenti per il cespite originario vengono annullate e rigenerate per il nuovo cespite.</span><span class="sxs-lookup"><span data-stu-id="5ff16-112">• The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

1. <span data-ttu-id="5ff16-113">Passare a Cespiti > Attività periodiche > Riclassificazione.</span><span class="sxs-lookup"><span data-stu-id="5ff16-113">Go to Fixed assets > Periodic tasks > Reclassification.</span></span>
2. <span data-ttu-id="5ff16-114">Nel campo Gruppo cespite selezionare il gruppo da riclassificare.</span><span class="sxs-lookup"><span data-stu-id="5ff16-114">In the Fixed asset group field, selet the group to reclassify.</span></span>
3. <span data-ttu-id="5ff16-115">Nel campo Numero cespite selezionare il cespite da riclassificare.</span><span class="sxs-lookup"><span data-stu-id="5ff16-115">In the Fixed asset number field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="5ff16-116">Nel campo Nuovo gruppo cespite, selezionare un gruppo in cui trasferire il cespite.</span><span class="sxs-lookup"><span data-stu-id="5ff16-116">In the New fixed asset group field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="5ff16-117">Se il nuovo gruppo cespite è collegato a una sequenza numerica, il campo Nuovo numero cespite verrà aggiornato con il numero della sequenza numerica del nuovo gruppo cespite.</span><span class="sxs-lookup"><span data-stu-id="5ff16-117">If the new fixed asset group is attached to a number sequence, the New fixed asset number field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="5ff16-118">In caso contrario, il campo Nuovo numero cespite viene aggiornato con il numero della sequenza numerica impostata nella pagina Parametri cespite.</span><span class="sxs-lookup"><span data-stu-id="5ff16-118">Otherwise, the New fixed asset number field is updated with the number from the number sequence that is set up in the Fixed asset parameters page.</span></span> <span data-ttu-id="5ff16-119">Se una sequenza numerica non è configurata nella pagina Parametri cespite, immettere un numero nel campo Nuovo numero cespite.</span><span class="sxs-lookup"><span data-stu-id="5ff16-119">If a number sequence is not set up in the Fixed asset parameters page, enter a number in the New fixed asset number field.</span></span>  
5. <span data-ttu-id="5ff16-120">Immettere una data nel campo Riclassificazione.</span><span class="sxs-lookup"><span data-stu-id="5ff16-120">In the Reclassification date field, enter a date.</span></span>
6. <span data-ttu-id="5ff16-121">Nel campo Serie giustificativi immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5ff16-121">In the Voucher series field, enter or select a value.</span></span>
7. <span data-ttu-id="5ff16-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ff16-122">Click OK.</span></span>


