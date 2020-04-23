---
title: Creare un nuovo prodotto
description: Viene descritta la procedura per creare un nuovo prodotto condiviso.
author: ShylaThompson
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0bf15359e085b541407bb49c266f7d9505893e25
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203712"
---
# <a name="create-a-new-product"></a><span data-ttu-id="33227-103">Creare un nuovo prodotto</span><span class="sxs-lookup"><span data-stu-id="33227-103">Create a new product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="33227-104">Viene descritta la procedura per creare un nuovo prodotto condiviso.</span><span class="sxs-lookup"><span data-stu-id="33227-104">This topic describes how to create a new shared product.</span></span> <span data-ttu-id="33227-105">Viene in genere svolta da un responsabile del design del prodotto.</span><span class="sxs-lookup"><span data-stu-id="33227-105">It is usually carried out by a product designer.</span></span> <span data-ttu-id="33227-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="33227-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-product"></a><span data-ttu-id="33227-107">Creare un prodotto</span><span class="sxs-lookup"><span data-stu-id="33227-107">Create a product</span></span>
1. <span data-ttu-id="33227-108">Nel pannello di navigazione andare a **Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti**.</span><span class="sxs-lookup"><span data-stu-id="33227-108">In the Navigation pane, go to **Modules > Product information management > Products > Products**.</span></span>
2. <span data-ttu-id="33227-109">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="33227-109">Select **New**.</span></span>
3. <span data-ttu-id="33227-110">Nel campo **Numero prodotto**, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="33227-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="33227-111">Se una sequenza numerica non è stata impostata per il numero di prodotto, deve essere immessa manualmente.</span><span class="sxs-lookup"><span data-stu-id="33227-111">If a number sequence has not been set up for the product number, it must be entered manually.</span></span>  
4. <span data-ttu-id="33227-112">Digitare un valore nel campo **Nome prodotto**.</span><span class="sxs-lookup"><span data-stu-id="33227-112">In the **Product name** field, type a value.</span></span> <span data-ttu-id="33227-113">Il nome prodotto è impostato come valore predefinito sul nome di ricerca.</span><span class="sxs-lookup"><span data-stu-id="33227-113">The product name defaults to the search name.</span></span> <span data-ttu-id="33227-114">Se necessario, questo valore può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="33227-114">You can change this if needed.</span></span>  
5. <span data-ttu-id="33227-115">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="33227-115">Select **OK**.</span></span>

## <a name="set-up-dimension-groups"></a><span data-ttu-id="33227-116">Impostare i gruppi di dimensioni</span><span class="sxs-lookup"><span data-stu-id="33227-116">Set up dimension groups</span></span>
1. <span data-ttu-id="33227-117">Fare clic su **Gruppi di dimensioni** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="33227-117">Select **Dimension groups** to open the drop dialog.</span></span>
2. <span data-ttu-id="33227-118">Nel campo **Gruppo di dimensioni di immagazzinamento** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="33227-118">In the **Storage dimension group** field, enter or select a value.</span></span> <span data-ttu-id="33227-119">Il gruppo di dimensioni di immagazzinamento determina quali dimensioni di immagazzinamento è necessario immettere in ciascuna transazione per il prodotto e come ne verrà tenuta traccia in magazzino.</span><span class="sxs-lookup"><span data-stu-id="33227-119">The storage dimension group determines which storage dimensions you must enter on each transaction for the product and how it will be tracked in inventory.</span></span>  
3. <span data-ttu-id="33227-120">Nel campo **Gruppo di dimensioni di tracciabilità** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="33227-120">In the **Tracking dimension group** field, enter or select a value.</span></span> <span data-ttu-id="33227-121">Il gruppo di dimensioni di tracciabilità determina quali dimensioni di tracciabilità è necessario immettere in ciascuna transazione per il prodotto e come verrà gestita in magazzino.</span><span class="sxs-lookup"><span data-stu-id="33227-121">The tracking dimension group determines which tracking dimensions you must enter for each transaction for the product, and how it will be handled in inventory.</span></span>  
4. <span data-ttu-id="33227-122">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="33227-122">Select **OK**.</span></span>

