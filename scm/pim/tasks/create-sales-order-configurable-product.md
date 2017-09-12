--- 
title: Creare un ordine cliente per un prodotto configurabile
description: Questa procedura mostra come applicare un modello di configurazione a un prodotto in un ordine cliente.
author: BibiSp
manager: AnnBe
ms.date: 10/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7084c3749f18e4fbe90fe4e04bdeac320cefeafa
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="95302-103">Creare un ordine cliente per un prodotto configurabile</span><span class="sxs-lookup"><span data-stu-id="95302-103">Create a sales order for a configurable product</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="95302-104">Questa procedura mostra come applicare un modello di configurazione a un prodotto in un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="95302-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="95302-105">Nell'esempio viene utilizzato il modello di altoparlante D0006 della società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="95302-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="95302-106">In genere, un gestore degli ordini cliente usa questa procedura.</span><span class="sxs-lookup"><span data-stu-id="95302-106">Typically, a sales order processor uses this procedure.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="95302-107">Crea un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="95302-107">Create a sales order</span></span>
1. <span data-ttu-id="95302-108">Fare clic su Elaborazione e richiesta di informazioni ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="95302-108">Click Sales order processing and inquiry.</span></span>
2. <span data-ttu-id="95302-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="95302-109">Click New.</span></span>
3. <span data-ttu-id="95302-110">Fare clic su Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="95302-110">Click Sales order.</span></span>
4. <span data-ttu-id="95302-111">Nel campo Conto cliente selezionare US-001.</span><span class="sxs-lookup"><span data-stu-id="95302-111">In the Customer account field, select US-001.</span></span> 
5. <span data-ttu-id="95302-112">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="95302-112">Click OK.</span></span>
6. <span data-ttu-id="95302-113">Nel campo Numero articolo selezionare D0006.</span><span class="sxs-lookup"><span data-stu-id="95302-113">In the Item number field, select D0006.</span></span>
    * <span data-ttu-id="95302-114">Per questa attività, selezionare un prodotto configurabile.</span><span class="sxs-lookup"><span data-stu-id="95302-114">For this task, you must select a configurable product.</span></span>  
7. <span data-ttu-id="95302-115">Fare clic su Prodotto e fornitura.</span><span class="sxs-lookup"><span data-stu-id="95302-115">Click Product and supply.</span></span>
8. <span data-ttu-id="95302-116">Fare clic su Configura riga.</span><span class="sxs-lookup"><span data-stu-id="95302-116">Click Configure line.</span></span>
    * <span data-ttu-id="95302-117">Si noti che il prezzo è cambiato, in base alla configurazione selezionata, e che il campo Include cable ora è impostato su True.</span><span class="sxs-lookup"><span data-stu-id="95302-117">Note that the price has changed, based on the configuration that was selected, and that the Include cable field is now set to True.</span></span>  
    * <span data-ttu-id="95302-118">Notare il prezzo predefinito e le impostazioni selezionate per il cavo.</span><span class="sxs-lookup"><span data-stu-id="95302-118">Note the default price and the settings that are selected for the cable.</span></span>  
9. <span data-ttu-id="95302-119">Fare clic su Carica modello.</span><span class="sxs-lookup"><span data-stu-id="95302-119">Click Load template.</span></span>
    * <span data-ttu-id="95302-120">In questo esempio viene illustrato come è possibile utilizzare un modello per selezionare una configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="95302-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="95302-121">Se si usa questa procedura come guida attività e si desidera visualizzare gli altri valori di attributo disponibili, è necessario fare clic sul pulsante Sblocca.</span><span class="sxs-lookup"><span data-stu-id="95302-121">If you’re using this procedure as a task guide and want to see the other attribute values that are available, you must click the Unlock button.</span></span>  
10. <span data-ttu-id="95302-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="95302-122">Click OK.</span></span>
11. <span data-ttu-id="95302-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="95302-123">Click OK.</span></span>
12. <span data-ttu-id="95302-124">Espandere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="95302-124">Expand the Line details section.</span></span>
13. <span data-ttu-id="95302-125">Fare clic sulla scheda Prodotto.</span><span class="sxs-lookup"><span data-stu-id="95302-125">Click the Product tab.</span></span>
    * <span data-ttu-id="95302-126">La configurazione dell'articolo è ora elencata nelle dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="95302-126">The configuration of the item is now listed under the product dimensions.</span></span>  
14. <span data-ttu-id="95302-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="95302-127">Close the page.</span></span>

## <a name="select-the-product-configuration"></a><span data-ttu-id="95302-128">Selezionare la configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="95302-128">Select the product configuration</span></span>

