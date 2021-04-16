---
title: Visualizzazione cespiti
description: In questo argomento viene descritta la visualizzazione cespiti in Gestione cespiti.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTree, EntAssetFunctionalLocationTree
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a7bf1cf07178f570f32e3fa4c4c1e5a2106b10d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837851"
---
# <a name="asset-view"></a><span data-ttu-id="cd505-103">Visualizzazione cespiti</span><span class="sxs-lookup"><span data-stu-id="cd505-103">Asset view</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="cd505-104">In questo argomento viene descritta la visualizzazione cespiti in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="cd505-104">This topic describes the asset view in Asset Management.</span></span> <span data-ttu-id="cd505-105">La pagina **Visualizzazione cespiti** mostra i cespiti attivi e le unità funzionali in una visualizzazione struttura.</span><span class="sxs-lookup"><span data-stu-id="cd505-105">The **Asset view** page shows active assets and functional locations in a tree view.</span></span> <span data-ttu-id="cd505-106">Di conseguenza, è possibile ottenere facilmente una panoramica delle relazioni cespiti alle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="cd505-106">Therefore, you can easily get an overview of asset relations to functional locations.</span></span> <span data-ttu-id="cd505-107">Inoltre, è possibile visualizzare informazioni dettagliate sulle unità funzionali, Cespiti e distinte base (DBA) correlate.</span><span class="sxs-lookup"><span data-stu-id="cd505-107">Additionally, you can view detailed information about functional locations, assets, and related bills of materials (BOMs).</span></span> <span data-ttu-id="cd505-108">È inoltre possibile visualizzare una veloce panoramica delle richieste di intervento di manutenzione e degli ordini di lavoro attivi correlati a un cespite.</span><span class="sxs-lookup"><span data-stu-id="cd505-108">You can also get a quick overview of active maintenance requests and work orders that are related to an asset.</span></span>

1. <span data-ttu-id="cd505-109">Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Visualizzazione cespiti**.</span><span class="sxs-lookup"><span data-stu-id="cd505-109">Select **Asset management** \> **Common** \> **Assets** \> **Asset view**.</span></span>
2. <span data-ttu-id="cd505-110">Per cambiare la visualizzazione nella pagina, selezionare un nuovo valore nel campo **Visualizzazione**.</span><span class="sxs-lookup"><span data-stu-id="cd505-110">To change the view that is shown on the page, select a new value in the **View** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cd505-111">La visualizzazione predefinita che viene visualizzata quando si apre la pagina **Visualizzazione cespiti** dipende dal valore selezionato nel campo **Visualizzazione** della scheda **Cespiti** della pagina **Parametri di gestione cespiti** (**Gestione cespiti** \> **Impostazione** \> **Parametri di gestione cespiti**).</span><span class="sxs-lookup"><span data-stu-id="cd505-111">The default view that is shown when you open the **Asset view** page depends on the value that is selected in the **View** field on the **Assets** tab of the **Asset management parameters** page (**Asset management** \> **Setup** \> **Asset management parameters**).</span></span>

<span data-ttu-id="cd505-112">Nel lato destro della pagina, schede dettaglio mostrano i dettagli della visualizzazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="cd505-112">On the right side of the page, FastTabs shows details of the selected view.</span></span>

<span data-ttu-id="cd505-113">Il percorso di navigazione visualizzato sopra la visualizzazione struttura mostra la selezione corrente nella visualizzazione struttura.</span><span class="sxs-lookup"><span data-stu-id="cd505-113">The breadcrumb trail that appears above the tree view shows the current selection in the tree view.</span></span> <span data-ttu-id="cd505-114">Questo percorso di navigazione utilizza il seguente formato:</span><span class="sxs-lookup"><span data-stu-id="cd505-114">This breadcrumb trail uses the following format:</span></span>

<span data-ttu-id="cd505-115">ID unità funzionale /ID unità funzionale (se sono disponibili più di una unità funzionale) \>ID cespite/ID cespite (se sono disponibili più di un cespite) - numero di articolo.</span><span class="sxs-lookup"><span data-stu-id="cd505-115">Functional location ID / Functional location ID (if there is more than one functional location) \> Asset ID / Asset ID (if there is more than one asset) - Item number.</span></span>

<span data-ttu-id="cd505-116">Se è stato selezionato un cespite nella visualizzazione struttura, è possibile selezionare **Richieste attive** o **Ordini di lavoro attivi** per visualizzare le richieste di intervento di manutenzione o gli ordini di lavoro correlati al cespite.</span><span class="sxs-lookup"><span data-stu-id="cd505-116">If you've selected an asset in the tree view, you can select **Active requests** or **Active work orders** to view the maintenance requests or work orders that are related to the asset.</span></span> <span data-ttu-id="cd505-117">È inoltre possibile selezionare **Apri** \> **Unità funzionale**, **Cespite**, **DBA cespiti** per aprire la visualizzazione correlata.</span><span class="sxs-lookup"><span data-stu-id="cd505-117">You can also select **Open** \> **Functional location**, **Asset**, or **Asset BOM** to open the related view.</span></span>

<span data-ttu-id="cd505-118">L'opzione **Unità funzionali cespiti** selezionabile nel campo **Visualizzazione** è inoltre disponibile in qualsiasi ricerca del cespite in cui è possibile selezionare un cespite.</span><span class="sxs-lookup"><span data-stu-id="cd505-118">The **Asset functional locations** option that you can select in the **View** field is also available in any asset lookup where you can select an asset.</span></span> <span data-ttu-id="cd505-119">La visualizzazione struttura viene visualizzata in una scheda **Visualizzazione cespiti**, ad esempio, dove [creare un cespite](../objects/create-an-object.md), creare una richiesta di intervento di manutenzione o creare un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cd505-119">The tree view is shown on an **Asset view** tab, for example, where you [create an asset](../objects/create-an-object.md), create a maintenance request, or create a work order.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]