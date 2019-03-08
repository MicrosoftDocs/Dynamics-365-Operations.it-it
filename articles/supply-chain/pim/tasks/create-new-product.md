---
title: Crea un nuovo prodotto
description: Questa attività mostra come creare un nuovo prodotto condiviso.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a603d89749242a4c6039ab83da286ec6ab727d8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "328541"
---
# <a name="create-a-new-product"></a><span data-ttu-id="9b737-103">Crea un nuovo prodotto</span><span class="sxs-lookup"><span data-stu-id="9b737-103">Create a new product</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9b737-104">Questa attività mostra come creare un nuovo prodotto condiviso.</span><span class="sxs-lookup"><span data-stu-id="9b737-104">This task shows how to create a new shared product.</span></span> <span data-ttu-id="9b737-105">Viene in genere svolta da un responsabile del design del prodotto.</span><span class="sxs-lookup"><span data-stu-id="9b737-105">It is usually carried out by a product designer.</span></span> <span data-ttu-id="9b737-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="9b737-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="9b737-107">Andare a Gestione informazioni sul prodotto > Prodotti > Prodotti.</span><span class="sxs-lookup"><span data-stu-id="9b737-107">Go to Product information management > Products > Products.</span></span>

## <a name="create-a-product"></a><span data-ttu-id="9b737-108">Creare un prodotto</span><span class="sxs-lookup"><span data-stu-id="9b737-108">Create a product</span></span>
1. <span data-ttu-id="9b737-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9b737-109">Click New.</span></span>
2. <span data-ttu-id="9b737-110">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="9b737-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="9b737-111">Se una sequenza numerica non è stata impostata per il numero di prodotto, deve essere immessa manualmente.</span><span class="sxs-lookup"><span data-stu-id="9b737-111">If a number sequence has not been set up for the product number, it must be entered manually.</span></span>  
3. <span data-ttu-id="9b737-112">Digitare un valore nel campo Nome prodotto.</span><span class="sxs-lookup"><span data-stu-id="9b737-112">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="9b737-113">Il nome prodotto è impostato come valore predefinito sul nome di ricerca.</span><span class="sxs-lookup"><span data-stu-id="9b737-113">The product name defaults to the search name.</span></span> <span data-ttu-id="9b737-114">Se necessario, questo valore può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="9b737-114">You can change this if needed.</span></span>  
4. <span data-ttu-id="9b737-115">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9b737-115">Click OK.</span></span>

## <a name="set-up-dimension-groups"></a><span data-ttu-id="9b737-116">Impostare i gruppi di dimensioni</span><span class="sxs-lookup"><span data-stu-id="9b737-116">Set up dimension groups</span></span>
1. <span data-ttu-id="9b737-117">Fare clic su gruppi di dimensioni per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9b737-117">Click Dimension groups to open the drop dialog.</span></span>
2. <span data-ttu-id="9b737-118">Nel campo Dimensione di immagazzinamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9b737-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="9b737-119">Il gruppo di dimensioni di immagazzinamento determina quali dimensioni di immagazzinamento è necessario immettere in ciascuna transazione per il prodotto e come ne verrà tenuta traccia in magazzino.</span><span class="sxs-lookup"><span data-stu-id="9b737-119">The storage dimension group determines which storage dimensions you must enter on each transaction for the product and how it will be tracked in inventory.</span></span>  
3. <span data-ttu-id="9b737-120">Nel campo Dimensione di tracciabilità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9b737-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="9b737-121">Il gruppo di dimensioni di tracciabilità determina quali dimensioni di tracciabilità è necessario immettere in ciascuna transazione per il prodotto e come verrà gestita in magazzino.</span><span class="sxs-lookup"><span data-stu-id="9b737-121">The tracking dimension group determines which tracking dimensions you must enter for each transaction for the product, and how it will be handled in inventory.</span></span>  
4. <span data-ttu-id="9b737-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9b737-122">Click OK.</span></span>

