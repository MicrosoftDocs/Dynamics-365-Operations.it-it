---
title: Campionamento degli articoli per la gestione della qualità
description: In questo argomento viene descritto come impostare il campionamento degli articoli.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae8bfd329ca0d7c30adcd93a759ee6bea7b76278
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022230"
---
# <a name="quality-management-item-sampling"></a><span data-ttu-id="2f51d-103">Campionamento degli articoli per la gestione della qualità</span><span class="sxs-lookup"><span data-stu-id="2f51d-103">Quality management item sampling</span></span>

<span data-ttu-id="2f51d-104">Il campionamento degli articoli viene utilizzato come parte di un'associazione di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="2f51d-104">Item sampling is used as part of a quality association.</span></span> <span data-ttu-id="2f51d-105">Definisce la quantità di scorte fisiche correnti da ispezionare.</span><span class="sxs-lookup"><span data-stu-id="2f51d-105">It defines the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="2f51d-106">Il campionamento può essere basato su quantità fisse, una percentuale o una targa completa.</span><span class="sxs-lookup"><span data-stu-id="2f51d-106">Sampling can be based on fixed quantities, a percentage, or a full license plate.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="2f51d-107">Imposta il campionamento articoli</span><span class="sxs-lookup"><span data-stu-id="2f51d-107">Set up item sampling</span></span>

<span data-ttu-id="2f51d-108">Per impostare il campionamento degli articoli, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="2f51d-108">Follow these steps to set up item sampling.</span></span>

1. <span data-ttu-id="2f51d-109">Fare clic su **Gestione scorte \> Impostazioni \> Controllo qualità \> Campionamento articoli**.</span><span class="sxs-lookup"><span data-stu-id="2f51d-109">Go to **Inventory management \> Setup \> Quality control \> Item sampling**.</span></span>
1. <span data-ttu-id="2f51d-110">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2f51d-110">Select **New**.</span></span>
1. <span data-ttu-id="2f51d-111">Nel campo **Campionamento articoli**, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2f51d-111">In the **Item sampling** field, enter a value.</span></span>
1. <span data-ttu-id="2f51d-112">Nel campo **Descrizione** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="2f51d-112">In the **Description** field, enter a value.</span></span>
1. <span data-ttu-id="2f51d-113">Nel campo **Valore** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="2f51d-113">In the **Value** field, enter a number.</span></span> <span data-ttu-id="2f51d-114">Questo valore è correlato al valore della specifica della quantità selezionato nel campo adiacente.</span><span class="sxs-lookup"><span data-stu-id="2f51d-114">This value is related to the quantity specification value that is selected in the adjacent field.</span></span>
1. <span data-ttu-id="2f51d-115">Nella sezione **Elaborazione** selezionare la casella di controllo **Blocco completo** se l'intero lotto o la quantità della riga ordine deve essere bloccata se un test non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="2f51d-115">In the **Process** section, select the **Full blocking** check box if the whole lot or order line quantity should be blocked if a test is failed.</span></span> <span data-ttu-id="2f51d-116">Se questa casella di controllo è deselezionata, solo gli articoli nell'ordine di controllo qualità verranno bloccati se un test non viene superato.</span><span class="sxs-lookup"><span data-stu-id="2f51d-116">If this check box is cleared, only the items in the quality order will be blocked if a test is failed.</span></span>
1. <span data-ttu-id="2f51d-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2f51d-117">Select **Save**.</span></span>
1. <span data-ttu-id="2f51d-118">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2f51d-118">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="2f51d-119">La funzionalità *Gestione della qualità per i processi di magazzino* fornisce ulteriori funzionalità di campionamento degli articoli.</span><span class="sxs-lookup"><span data-stu-id="2f51d-119">The *Quality management for warehouse processes* feature provides additional item sampling capabilities.</span></span> <span data-ttu-id="2f51d-120">Aggiunge il concetto di *ambito di campionamento articoli* e consente di definire una targa completa come specifica della quantità.</span><span class="sxs-lookup"><span data-stu-id="2f51d-120">It adds the concept of *item sampling scope* and lets you define a full license plate as the quantity specification.</span></span> <span data-ttu-id="2f51d-121">Se è stata abilitata questa funzionalità, vedere [Gestione qualità per i processi di magazzino](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="2f51d-121">If you've turned on this feature, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
