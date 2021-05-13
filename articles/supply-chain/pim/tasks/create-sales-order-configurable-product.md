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
ms.openlocfilehash: 8607de5705354aa58c985fb536f3e1d52acd1f37
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921291"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="fcd6e-103">Creare un ordine cliente per un prodotto configurabile</span><span class="sxs-lookup"><span data-stu-id="fcd6e-103">Create a sales order for a configurable product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fcd6e-104">Questa procedura mostra come applicare un modello di configurazione a un prodotto in un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="fcd6e-105">Nell'esempio viene utilizzato il modello di altoparlante D0006 della società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="fcd6e-106">In genere, un gestore degli ordini cliente usa questa procedura.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-106">Typically, a sales order processor uses this procedure.</span></span>

## <a name="create-a-sales-order"></a><span data-ttu-id="fcd6e-107">Crea un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="fcd6e-107">Create a sales order</span></span>

1. <span data-ttu-id="fcd6e-108">Vai a **Vendite e marketing \> Aree di lavoro \> Elaborazione e richiesta di informazioni ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-108">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="fcd6e-109">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-109">Select **New**.</span></span>
1. <span data-ttu-id="fcd6e-110">Selezionare **Ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-110">Select **Sales order**.</span></span>
1. <span data-ttu-id="fcd6e-111">Nel campo **Conto cliente** selezionare *US-001*.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-111">In the **Customer account** field, select *US-001*.</span></span> 
1. <span data-ttu-id="fcd6e-112">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-112">Select **OK**.</span></span>
1. <span data-ttu-id="fcd6e-113">Nel campo **Numero articolo** selezionare *D0006*.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-113">In the **Item number** field, select *D0006*.</span></span>
    * <span data-ttu-id="fcd6e-114">Per questa attività, selezionare un prodotto configurabile.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-114">For this task, you must select a configurable product.</span></span>  
1. <span data-ttu-id="fcd6e-115">Fare clic su **Prodotto e fornitura**.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-115">Select **Product and supply**.</span></span>
1. <span data-ttu-id="fcd6e-116">Selezionare **Configura riga**.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-116">Select **Configure line**.</span></span>
    * <span data-ttu-id="fcd6e-117">Si noti che il prezzo è cambiato, in base alla configurazione selezionata, e che il campo **Includi cavo** ora è impostato su *True*.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-117">Note that the price has changed, based on the configuration that was selected, and that the **Include cable** field is now set to *True*.</span></span>  
    * <span data-ttu-id="fcd6e-118">Notare il prezzo predefinito e le impostazioni selezionate per il cavo.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-118">Note the default price and the settings that are selected for the cable.</span></span>  
1. <span data-ttu-id="fcd6e-119">Selezionare **Carica modello**.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-119">Select **Load template**.</span></span>
    * <span data-ttu-id="fcd6e-120">In questo esempio viene illustrato come è possibile utilizzare un modello per selezionare una configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="fcd6e-121">Se si usa questa procedura come guida attività e si desidera visualizzare gli altri valori di attributo disponibili, è necessario fare clic sul pulsante **Sblocca**.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-121">If you're using this procedure as a task guide and want to see the other attribute values that are available, you must select the **Unlock** button.</span></span>  
1. <span data-ttu-id="fcd6e-122">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-122">Select **OK**.</span></span>
1. <span data-ttu-id="fcd6e-123">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-123">Select **OK**.</span></span>
1. <span data-ttu-id="fcd6e-124">Espandere la sezione **Dettagli riga**.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-124">Expand the **Line details** section.</span></span>
1. <span data-ttu-id="fcd6e-125">Selezionare la scheda **Prodotto**</span><span class="sxs-lookup"><span data-stu-id="fcd6e-125">Select the **Product** tab.</span></span>
    * <span data-ttu-id="fcd6e-126">La configurazione dell'articolo è ora elencata nelle dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-126">The configuration of the item is now listed under the product dimensions.</span></span>  
1. <span data-ttu-id="fcd6e-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fcd6e-127">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]