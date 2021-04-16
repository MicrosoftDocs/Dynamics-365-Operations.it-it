---
title: Creare un ordine cliente per un prodotto configurabile
description: Questa procedura mostra come applicare un modello di configurazione a un prodotto in un ordine cliente.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 81e573593fbbb0bf87e53c5cbd985b38a8db89ac
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841601"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="ad487-103">Creare un ordine cliente per un prodotto configurabile</span><span class="sxs-lookup"><span data-stu-id="ad487-103">Create a sales order for a configurable product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ad487-104">Questa procedura mostra come applicare un modello di configurazione a un prodotto in un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="ad487-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="ad487-105">Nell'esempio viene utilizzato il modello di altoparlante D0006 della società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="ad487-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="ad487-106">In genere, un gestore degli ordini cliente usa questa procedura.</span><span class="sxs-lookup"><span data-stu-id="ad487-106">Typically, a sales order processor uses this procedure.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="ad487-107">Crea un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="ad487-107">Create a sales order</span></span>
1. <span data-ttu-id="ad487-108">Fare clic su Elaborazione e richiesta di informazioni ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="ad487-108">Click Sales order processing and inquiry.</span></span>
2. <span data-ttu-id="ad487-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ad487-109">Click New.</span></span>
3. <span data-ttu-id="ad487-110">Fare clic su Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="ad487-110">Click Sales order.</span></span>
4. <span data-ttu-id="ad487-111">Nel campo Conto cliente selezionare US-001.</span><span class="sxs-lookup"><span data-stu-id="ad487-111">In the Customer account field, select US-001.</span></span> 
5. <span data-ttu-id="ad487-112">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ad487-112">Click OK.</span></span>
6. <span data-ttu-id="ad487-113">Nel campo Numero articolo selezionare D0006.</span><span class="sxs-lookup"><span data-stu-id="ad487-113">In the Item number field, select D0006.</span></span>
    * <span data-ttu-id="ad487-114">Per questa attività, selezionare un prodotto configurabile.</span><span class="sxs-lookup"><span data-stu-id="ad487-114">For this task, you must select a configurable product.</span></span>  
7. <span data-ttu-id="ad487-115">Fare clic su Prodotto e fornitura.</span><span class="sxs-lookup"><span data-stu-id="ad487-115">Click Product and supply.</span></span>
8. <span data-ttu-id="ad487-116">Fare clic su Configura riga.</span><span class="sxs-lookup"><span data-stu-id="ad487-116">Click Configure line.</span></span>
    * <span data-ttu-id="ad487-117">Si noti che il prezzo è cambiato, in base alla configurazione selezionata, e che il campo Include cable ora è impostato su True.</span><span class="sxs-lookup"><span data-stu-id="ad487-117">Note that the price has changed, based on the configuration that was selected, and that the Include cable field is now set to True.</span></span>  
    * <span data-ttu-id="ad487-118">Notare il prezzo predefinito e le impostazioni selezionate per il cavo.</span><span class="sxs-lookup"><span data-stu-id="ad487-118">Note the default price and the settings that are selected for the cable.</span></span>  
9. <span data-ttu-id="ad487-119">Fare clic su Carica modello.</span><span class="sxs-lookup"><span data-stu-id="ad487-119">Click Load template.</span></span>
    * <span data-ttu-id="ad487-120">In questo esempio viene illustrato come è possibile utilizzare un modello per selezionare una configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ad487-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="ad487-121">Se si usa questa procedura come guida attività e si desidera visualizzare gli altri valori di attributo disponibili, è necessario fare clic sul pulsante Sblocca.</span><span class="sxs-lookup"><span data-stu-id="ad487-121">If you're using this procedure as a task guide and want to see the other attribute values that are available, you must click the Unlock button.</span></span>  
10. <span data-ttu-id="ad487-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ad487-122">Click OK.</span></span>
11. <span data-ttu-id="ad487-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ad487-123">Click OK.</span></span>
12. <span data-ttu-id="ad487-124">Espandere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="ad487-124">Expand the Line details section.</span></span>
13. <span data-ttu-id="ad487-125">Fare clic sulla scheda Prodotto.</span><span class="sxs-lookup"><span data-stu-id="ad487-125">Click the Product tab.</span></span>
    * <span data-ttu-id="ad487-126">La configurazione dell'articolo è ora elencata nelle dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="ad487-126">The configuration of the item is now listed under the product dimensions.</span></span>  
14. <span data-ttu-id="ad487-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ad487-127">Close the page.</span></span>

## <a name="select-the-product-configuration"></a><span data-ttu-id="ad487-128">Selezionare la configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="ad487-128">Select the product configuration</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]