---
title: Creare uno stato del ciclo di vita del prodotto per escludere i prodotti dalla pianificazione principale
description: In questa procedura viene illustrato come creare un nuovo stato del ciclo di vita del prodotto che esclude i prodotti dal calcolo del livello DBA e dalla pianificazione generale.
author: cvocph
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cadf1d812e737309dbe8ca26d04ffb1ee88ef16a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818039"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a><span data-ttu-id="57d52-103">Creare uno stato del ciclo di vita del prodotto per escludere i prodotti dalla pianificazione principale</span><span class="sxs-lookup"><span data-stu-id="57d52-103">Create a product lifecycle state to exclude products from Master planning</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="57d52-104">In questa procedura viene illustrato come creare un nuovo stato del ciclo di vita del prodotto che esclude i prodotti dal calcolo del livello DBA e dalla pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="57d52-104">This procedure shows how to create a new product lifecycle state that excludes the products from Master planning and BOM-level calculation.</span></span>


## <a name="create-an-obsolete-state"></a><span data-ttu-id="57d52-105">Creare uno stato obsoleto</span><span class="sxs-lookup"><span data-stu-id="57d52-105">Create an obsolete state</span></span>
1. <span data-ttu-id="57d52-106">Fare clic su Gestione informazioni sul prodotto > Impostazioni > Stato del ciclo di vita prodotto.</span><span class="sxs-lookup"><span data-stu-id="57d52-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="57d52-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="57d52-107">Click New.</span></span>
3. <span data-ttu-id="57d52-108">Nel campo Stato digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="57d52-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="57d52-109">Selezionare No nel campo Attivo per pianificazione.</span><span class="sxs-lookup"><span data-stu-id="57d52-109">Select No in the Is active for planning field.</span></span>
5. <span data-ttu-id="57d52-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="57d52-110">In the Description field, type a value.</span></span>

## <a name="associate-the-obsolete-state-to-a-released-product"></a><span data-ttu-id="57d52-111">Associare lo stato obsoleto a un prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="57d52-111">Associate the obsolete state to a released product</span></span>
1. <span data-ttu-id="57d52-112">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="57d52-112">Close the page.</span></span>
2. <span data-ttu-id="57d52-113">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="57d52-113">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="57d52-114">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="57d52-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="57d52-115">Ad esempio, applicare un filtro al campo Nome di ricerca con il valore 'M00'.</span><span class="sxs-lookup"><span data-stu-id="57d52-115">For example, filter on the Search name field with a value of 'M00'.</span></span>
4. <span data-ttu-id="57d52-116">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="57d52-116">Click Edit.</span></span>
5. <span data-ttu-id="57d52-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="57d52-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="57d52-118">Nel campo Stato del ciclo di vita prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="57d52-118">In the Product lifecycle state field, enter or select a value.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]