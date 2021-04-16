---
title: Creare dimensioni e importare i membri di dimensione
description: La contabilità industriale è un modulo indipendente che necessita dei dati master di altri moduli.
author: ShylaThompson
ms.date: 09/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a9634612bcffbcf71b77dbb184e71367c67bac10
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822929"
---
# <a name="create-dimensions-and-import-dimension-members"></a><span data-ttu-id="0cf7d-103">Creare dimensioni e importare i membri di dimensione</span><span class="sxs-lookup"><span data-stu-id="0cf7d-103">Create dimensions and import dimension members</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0cf7d-104">La contabilità industriale è un modulo indipendente che necessita dei dati di altri moduli.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-104">Cost accounting is an independent module that requires data from other modules.</span></span> <span data-ttu-id="0cf7d-105">Questi dati sono suddivisi nelle seguenti categorie:</span><span class="sxs-lookup"><span data-stu-id="0cf7d-105">This data is categorized into the following:</span></span>

-  <span data-ttu-id="0cf7d-106">Elementi di costo</span><span class="sxs-lookup"><span data-stu-id="0cf7d-106">Cost elements</span></span>
-  <span data-ttu-id="0cf7d-107">Oggetti di costo</span><span class="sxs-lookup"><span data-stu-id="0cf7d-107">Cost objects</span></span>
-  <span data-ttu-id="0cf7d-108">Dimensioni statistiche</span><span class="sxs-lookup"><span data-stu-id="0cf7d-108">Statistical dimensions</span></span>

<span data-ttu-id="0cf7d-109">Un **elemento di costo** corrisponde a un articolo pertinente per i costi nel piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-109">A **Cost element** corresponds to a cost-relevant item in the chart of accounts.</span></span> <span data-ttu-id="0cf7d-110">Un **oggetto di costo** corrisponde a qualsiasi tipo di dimensione finanziaria, ad esempio prodotti, centri di costo e progetti da stimare, a cui allocare i costi o da misurare direttamente.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-110">A **Cost object** corresponds to any type of financial dimension, such as products, cost centers, and projects that you want to estimate, allocate costs to, or measure directly.</span></span> <span data-ttu-id="0cf7d-111">Una **dimensione statistica** e i relativi membri vengono utilizzati per registrare le voci non monetarie.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-111">A **Statistical dimension** and its members are used to register non-monetary entries.</span></span> <span data-ttu-id="0cf7d-112">I membri di dimensione statistica possono essere utilizzati come base di allocazione nella distribuzione e nell'allocazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-112">Statistical dimension members can be used as an allocation base in cost distribution and allocation</span></span> 

<span data-ttu-id="0cf7d-113">Nel seguente diagramma sono illustrate le dimensioni utilizzate nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-113">The following diagram illustrates the dimensions that are used in Cost accounting.</span></span>

<span data-ttu-id="0cf7d-114">[![Dimensioni contabilità industriale](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="0cf7d-114">[![Cost accounting dimensions](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)</span></span>

<span data-ttu-id="0cf7d-115">Dopo l'importazione dei dati nella contabilità industriale, è possibile utilizzarli per creare diverse prospettive che forniscono indicazioni utili ai responsabili a tutti i livelli dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-115">After the data is imported into Cost accounting, you can use it to build various perspectives that provide insights to managers at all levels of the organization.</span></span> <span data-ttu-id="0cf7d-116">Negli argomenti riportati di seguito vengono fornite informazioni sulla creazione di dimensioni e sull'importazione dei membri di dimensione.</span><span class="sxs-lookup"><span data-stu-id="0cf7d-116">The following topics provide information about creating dimensions and importing dimension members.</span></span> 

-  [<span data-ttu-id="0cf7d-117">Dimensioni elemento di costo</span><span class="sxs-lookup"><span data-stu-id="0cf7d-117">Cost element dimensions</span></span>](cost-elements.md)
-  [<span data-ttu-id="0cf7d-118">Creare elementi di costo</span><span class="sxs-lookup"><span data-stu-id="0cf7d-118">Create cost elements</span></span>](./tasks/create-cost-elements.md)
-  [<span data-ttu-id="0cf7d-119">Dimensioni oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="0cf7d-119">Cost object dimensions</span></span>](cost-objects.md)
-  [<span data-ttu-id="0cf7d-120">Eseguire il mapping dei membri di dimensione elemento di costo a un set comune di membri di dimensione</span><span class="sxs-lookup"><span data-stu-id="0cf7d-120">Map cost element dimension members to a common set of dimension members</span></span>](map-cost-elements-dimension-members.md)
-  [<span data-ttu-id="0cf7d-121">Mappare una dimensione elemento di costo</span><span class="sxs-lookup"><span data-stu-id="0cf7d-121">Map a cost element dimension</span></span>](./tasks/map-cost-element-dimension.md)
-  [<span data-ttu-id="0cf7d-122">Membri di dimensione statistica e modelli provider misure statistiche</span><span class="sxs-lookup"><span data-stu-id="0cf7d-122">Statistical dimension members and statistical measure provider templates</span></span>](statistical-measure-provider-template.md)








[!INCLUDE[footer-include](../../includes/footer-banner.md)]