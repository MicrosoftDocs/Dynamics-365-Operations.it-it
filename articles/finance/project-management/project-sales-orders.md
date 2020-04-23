---
title: Ordini cliente progetto per progetti di tempistica e materiali
description: In questo argomento viene descritto come creare ordini cliente basati su progetti per progetti di tempistica e materiali.
author: KimANelson
manager: AnnBe
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2
ms.openlocfilehash: d19ee9de70cd14c78a997b7a87c10b53ab3917b0
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249095"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a><span data-ttu-id="085c3-103">Ordini cliente progetto per progetti di tempistica e materiali</span><span class="sxs-lookup"><span data-stu-id="085c3-103">Project sales orders for time and material projects</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="085c3-104">In questo argomento viene descritto come creare un ordine cliente per un progetto.</span><span class="sxs-lookup"><span data-stu-id="085c3-104">This topic describes how to create a sales order for a project.</span></span> <span data-ttu-id="085c3-105">Gli ordini cliente possono essere creati solo per progetti di tipo **tempistica e materiali**.</span><span class="sxs-lookup"><span data-stu-id="085c3-105">Sales orders can only be created for projects of type **time and material**.</span></span>

<span data-ttu-id="085c3-106">Se un progetto di tempistica e materiali ha più fonti di finanziamento sul contratto di progetto, è necessario abilitare il parametro **Consenti ordini cliente per progetti con più fonti di finanziamento** nella pagina **Parametri Gestione progetti e contabilità**.</span><span class="sxs-lookup"><span data-stu-id="085c3-106">If a time and material project has multiple funding sources on the project contract, you must enable the **Allow sales orders for projects with multiple funding sources** parameter on the **Project management and accounting parameters** page.</span></span> 

> [!NOTE]
> - <span data-ttu-id="085c3-107">Il supporto per ordini cliente progetto con più fonti di finanziamento è disponibile a partire dalla versione 10.0.2 dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="085c3-107">Support for project sales orders with multiple funding sources is available starting with application release 10.0.2 and higher.</span></span>
> - <span data-ttu-id="085c3-108">Il parametro per abilitare il supporto per ordini cliente progetto con più fonti di finanziamento verrà rimosso nell'ondata di rilascio di aprile 2020, dopodiché la funzionalità sarà sempre abilitata.</span><span class="sxs-lookup"><span data-stu-id="085c3-108">The parameter to enable the support for project sales orders with multiple funding sources will be removed in the April 2020 release wave, after which the functionality will always be enabled.</span></span>

<span data-ttu-id="085c3-109">È possibile creare ordini cliente basati su progetti in due modi:</span><span class="sxs-lookup"><span data-stu-id="085c3-109">You can create project-based sales orders in two ways:</span></span>

- <span data-ttu-id="085c3-110">Accedere al progetto in questione.</span><span class="sxs-lookup"><span data-stu-id="085c3-110">Go to the project itself.</span></span> <span data-ttu-id="085c3-111">Nel Riquadro azioni, selezionare **Gestire > Attività articolo > Ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="085c3-111">On the Action Pane, select **Manage > Item tasks > Sales order**.</span></span> <span data-ttu-id="085c3-112">Le informazioni sul progetto passeranno dal progetto all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="085c3-112">The project information will default to the sales order from the project.</span></span> <span data-ttu-id="085c3-113">Se il contratto di progetto ha più fonti di finanziamento, sarà necessario selezionare la fonte di finanziamento per impostare il cliente per l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="085c3-113">If the project contract has more than one funding source, you will need to select the funding source to set the customer for the sales order.</span></span> <span data-ttu-id="085c3-114">Se è presente una sola fonte di finanziamento per il progetto, il cliente verrà impostato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="085c3-114">If there is only one funding source for the project, the customer will be automatically set.</span></span>
- <span data-ttu-id="085c3-115">Andare alla pagina elenco **Tutti gli ordini cliente** e creare un nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="085c3-115">Go to the **All sales order** list page and create a new sales order.</span></span> <span data-ttu-id="085c3-116">Sarà necessario selezionare il progetto per l'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="085c3-116">You will need to select the project for the sales order.</span></span> <span data-ttu-id="085c3-117">Dopo la selezione del progetto, il cliente verrà impostato a partire dalla fonte di finanziamento oppure sarà necessario selezionare la fonte di finanziamento se il contratto di progetto ha più fonti di finanziamento.</span><span class="sxs-lookup"><span data-stu-id="085c3-117">After the project is selected, the customer will be set from the funding source or you will need to select the funding source if the project contract has multiple funding sources.</span></span>

