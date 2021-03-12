---
title: Dimensioni oggetto di costo
description: Quando si analizzano i costi, si usano le dimensioni elemento di costo per determinare la destinazione del flusso dei costi. Le dimensioni oggetto di costo sono utilizzate per determinare dove assegnare i costi. In questo argomento vengono fornite informazioni sulle dimensioni oggetto di costo.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimensionMember, CAMCostObject
audience: Application User
ms.reviewer: roschlom
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9a17eaf0a65f5228ec60391e22c98c2f383d7cce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990819"
---
# <a name="cost-object-dimensions"></a><span data-ttu-id="9e2b6-105">Dimensioni oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="9e2b6-105">Cost object dimensions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9e2b6-106">Quando si analizzano i costi, si usano le dimensioni elemento di costo per determinare la destinazione del flusso dei costi.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-106">When you analyze costs, you use cost element dimensions to determine where costs flow to.</span></span> <span data-ttu-id="9e2b6-107">Le dimensioni oggetto di costo sono utilizzate per determinare dove assegnare i costi.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-107">You use cost object dimensions to determine where you should assign costs.</span></span> <span data-ttu-id="9e2b6-108">In questo argomento vengono fornite informazioni sulle dimensioni oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-108">This topic provides information about cost object dimensions.</span></span>

<span data-ttu-id="9e2b6-109">Un oggetto di costo può essere qualsiasi tipo di oggetto da stimare, a cui allocare i costi, o misurare direttamente.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-109">A cost object can be any type of object that you want to estimate, allocate costs to, or measure directly.</span></span> <span data-ttu-id="9e2b6-110">Gli oggetti di costo tipici includono prodotti, progetti, risorse, i reparti, i centri di costo e aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-110">Typical cost objects include products, projects, resources, departments, cost centers, and geographical regions.</span></span> <span data-ttu-id="9e2b6-111">La gestione utilizza gli oggetti di costo per quantificare i costi nonché per determinare l'analisi di redditività.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-111">Management uses cost objects to quantify costs and also to drive profitability analysis.</span></span>

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a><span data-ttu-id="9e2b6-112">Dimensioni oggetto di costo e membri di dimensioni oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="9e2b6-112">Cost object dimensions and cost object dimension members</span></span>
<span data-ttu-id="9e2b6-113">Gli oggetti di costo sono definiti come *dimensioni oggetto di costo*.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-113">Cost objects are known as *cost object dimensions*.</span></span> <span data-ttu-id="9e2b6-114">Una volta deciso a quale entità la dimensione oggetto di costo deve fare riferimento, è necessario specificare i singoli valori di dimensione o importarli nella contabilità industriale da altri sistemi di origine.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-114">After you’ve decided which entity the cost object dimension should refer to, you must specify the individual dimension values or import them into Cost accounting from other source systems.</span></span> <span data-ttu-id="9e2b6-115">I singoli valori delle dimensioni vengono denominati *membri delle dimensioni oggetto di costo*.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-115">These individual dimension values are known as *cost object dimension members*.</span></span> <span data-ttu-id="9e2b6-116">Ad esempio, si desidera utilizzare la dimensione finanziaria denominata Centro di costo come dimensione oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-116">For example, you want to use the financial dimension that is named Cost center as the cost object dimension.</span></span> <span data-ttu-id="9e2b6-117">Per visualizzare come i costi fluiscono nei singoli centri di costo, è necessario importare i membri delle dimensioni oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-117">To see how costs flow to the individual cost centers, you must import the cost object dimension members.</span></span> <span data-ttu-id="9e2b6-118">In questo caso, i membri delle dimensioni oggetto di costo sono gli effettivi centri di costo, ad esempio Vendite, Produzione, Amministrazione e Località geografiche.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-118">In this case, the cost object dimension members are the actual cost centers, such as Sales, Production, Administration, and Geographic locations.</span></span> <span data-ttu-id="9e2b6-119">Nella schermata seguente è illustrato un esempio di centri di costo come dimensione oggetto di costo con i relativi centri di costo effettivi come membri della dimensione oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-119">The following screenshot shows an example of Cost Centers as the cost object dimension with its actual cost centers as cost object dimension members.</span></span> 

<span data-ttu-id="9e2b6-120">[![Screenshot che mostra i centri di costo come dimensione dell'oggetto di costo](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="9e2b6-120">[![Screenshot showing Cost Centers as cost object dimension](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)</span></span>

## <a name="import-cost-object-dimension-members-through-data-connectors"></a><span data-ttu-id="9e2b6-121">Importare i membri delle dimensioni oggetto di costo tramite connettori dati</span><span class="sxs-lookup"><span data-stu-id="9e2b6-121">Import cost object dimension members through data connectors</span></span>
<span data-ttu-id="9e2b6-122">Per semplificare l'importazione di membri delle dimensioni oggetto di costo si utilizzano i connettori dati per recuperare i valori dalle entità che si desidera utilizzare come dimensioni oggetto di costo.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-122">To make the import of cost object dimension members easier, you use data connectors to retrieve the values from the entities that you want to use as cost object dimensions.</span></span> <span data-ttu-id="9e2b6-123">È possibile utilizzare connettori dati predefiniti oppure crearne di propri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="9e2b6-123">You can use either the pre-built data connectors or custom data connectors that you build.</span></span>



