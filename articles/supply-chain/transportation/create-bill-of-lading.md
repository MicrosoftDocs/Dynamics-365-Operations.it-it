---
title: Creare una polizza di carico
description: In questo argomento viene descritto come creare una polizza di carico quando si utilizzano i processi di gestione magazzino.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 05ad5d4b49f1fa50bde7df9c835ee99a981420c4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206313"
---
# <a name="create-a-bill-of-lading"></a><span data-ttu-id="bf80b-103">Creare una polizza di carico</span><span class="sxs-lookup"><span data-stu-id="bf80b-103">Create a bill of lading</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bf80b-104">In questo argomento viene descritto come creare una polizza di carico quando si utilizzano i processi di gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="bf80b-104">This topic describes how to create a bill of lading when using warehouse management processes.</span></span>  

<span data-ttu-id="bf80b-105">La polizza di carico costituisce un documento legale tra la società che spedisce articoli e il vettore.</span><span class="sxs-lookup"><span data-stu-id="bf80b-105">A bill of lading is a legal document between the company that ships the items and the carrier.</span></span> <span data-ttu-id="bf80b-106">Il documento accompagna gli articoli spediti e serve come ricevuta di spedizione quando gli articoli vengono consegnati a destinazione.</span><span class="sxs-lookup"><span data-stu-id="bf80b-106">The document accompanies the shipped items, and it serves as a receipt of shipment when the items are delivered at the destination.</span></span> <span data-ttu-id="bf80b-107">Se si utilizza la gestione magazzino, sono presenti due modi per generare una polizza di carico:</span><span class="sxs-lookup"><span data-stu-id="bf80b-107">If you're using warehouse management, there are two ways to generate a bill of lading:</span></span>

  -   <span data-ttu-id="bf80b-108">Creare manualmente il report, utilizzando la pagina **Polizza di carico**.</span><span class="sxs-lookup"><span data-stu-id="bf80b-108">Create the report manually, using the **Bill of lading** page.</span></span>
  -   <span data-ttu-id="bf80b-109">Generare il report da **Workbench pianificazione carico**.</span><span class="sxs-lookup"><span data-stu-id="bf80b-109">Generate the report from the **Load planning workbench**.</span></span>

<span data-ttu-id="bf80b-110">Se si genera la polizza di carico da **Workbench pianificazione carico**, lo stato del carico deve essere **Spedito**.</span><span class="sxs-lookup"><span data-stu-id="bf80b-110">If you generate the bill of lading from the **Load planning workbench**, the load status must be **Shipped.**</span></span> <span data-ttu-id="bf80b-111">Se sono presenti più di una spedizione nel carico, una polizza di carico viene creata per ogni spedizione.</span><span class="sxs-lookup"><span data-stu-id="bf80b-111">If there's more than one shipment in the load, a bill of lading is created for each shipment.</span></span> <span data-ttu-id="bf80b-112">Dopo che una polizza di carico è stata creata è possibile apportarvi modifiche nella pagina **Polizza di carico**.</span><span class="sxs-lookup"><span data-stu-id="bf80b-112">After a bill of lading has been created you can make changes to it on the **Bill of lading** page.</span></span>

## <a name="master-bill-of-lading"></a><span data-ttu-id="bf80b-113">Polizza di carico generale</span><span class="sxs-lookup"><span data-stu-id="bf80b-113">Master bill of lading</span></span>
<span data-ttu-id="bf80b-114">Se nel carico è presente più di una spedizione, è possibile generare una polizza di carico generale</span><span class="sxs-lookup"><span data-stu-id="bf80b-114">If there's more than one shipment in the load, you can generate a master bill of lading.</span></span> <span data-ttu-id="bf80b-115">che ha lo stesso layout e le stesse informazioni di una polizza di carico, ma è presente il contenuto di riepilogo per tutte le spedizioni.</span><span class="sxs-lookup"><span data-stu-id="bf80b-115">This has the same layout and information as a bill of lading, but contains the summarized content for all the shipments.</span></span> <span data-ttu-id="bf80b-116">Se l'opzione **Creare una polizza di carico generale se è presente più di una spedizione in un carico** è impostata su **Sì** nella pagina **Parametri di gestione trasporto**, una polizza di carico generale viene generata automaticamente se si crea una polizza di carico in **Workbench pianificazione carico** ed è presente più di una spedizione.</span><span class="sxs-lookup"><span data-stu-id="bf80b-116">If the **Create a master bill of lading when there's more than one shipment on a load** option is set to **Yes** on the **Transportation management parameters** page, a master bill of lading is automatically generated if you create a bill of lading from the **Load planning workbench**, and there's more than one shipment.</span></span> <span data-ttu-id="bf80b-117">È inoltre possibile ottenere un elenco delle polizze di carico facendo clic su **Informazioni correlate** &gt; **Polizza di carico**.</span><span class="sxs-lookup"><span data-stu-id="bf80b-117">You can also get a list of the bills of lading by clicking **Related information** &gt; **Bill of lading**.</span></span> <span data-ttu-id="bf80b-118">Se si creano manualmente le polizze di carico, è possibile creare una polizza di carico generale nella pagina **Polizza di carico**.</span><span class="sxs-lookup"><span data-stu-id="bf80b-118">If you're creating bills of lading manually, you can create a master bill of lading on the **Bill of lading** page.</span></span>



