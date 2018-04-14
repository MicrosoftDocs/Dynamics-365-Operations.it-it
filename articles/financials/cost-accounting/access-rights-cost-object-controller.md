---
title: Definire i diritti di accesso per i controller oggetto di costo
description: Di seguito vengono descritti i diritti di accesso per i controller oggetto di costo.
author: AndersGirke
manager: AnnBe
ms.date: 06/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e0ba52f4c06d5cd18c8f0ff7972671cc722289e7
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="access-rights-of-a-cost-object-controller"></a><span data-ttu-id="ecb68-103">Diritti di accesso di un controller oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="ecb68-103">Access rights of a cost object controller</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="ecb68-104">L'area di lavoro **Controllo costi** è un punto centrale in cui i responsabili possono visualizzare le prestazioni degli oggetti di costo.</span><span class="sxs-lookup"><span data-stu-id="ecb68-104">The **Cost control** workspace is a central point where managers can view the performance of their cost objects.</span></span> <span data-ttu-id="ecb68-105">Questa area di lavoro consente ai responsabili di utilizzare i dati di contabilità industriale anche se non sono contabili.</span><span class="sxs-lookup"><span data-stu-id="ecb68-105">This workspace lets managers consume Cost accounting data even though they aren't cost accountants.</span></span> <span data-ttu-id="ecb68-106">Per motivi di sicurezza, i responsabili devono poter visualizzare solo i dati della contabilità industriale correlati agli oggetti di costo specifici di cui sono responsabili.</span><span class="sxs-lookup"><span data-stu-id="ecb68-106">For security reasons, managers should be allowed to see only the Cost accounting data that is related to the specific cost objects that they are responsible for.</span></span>

<span data-ttu-id="ecb68-107">Sono disponibili quattro ruoli specifici nella contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="ecb68-107">There are four unique roles in Cost accounting.</span></span>

| <span data-ttu-id="ecb68-108">Nome ruolo</span><span class="sxs-lookup"><span data-stu-id="ecb68-108">Role name</span></span>               | <span data-ttu-id="ecb68-109">Licenza</span><span class="sxs-lookup"><span data-stu-id="ecb68-109">License</span></span>      |
|-------------------------|--------------|
| <span data-ttu-id="ecb68-110">Responsabile contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="ecb68-110">Cost accounting manager</span></span> | <span data-ttu-id="ecb68-111">Attività</span><span class="sxs-lookup"><span data-stu-id="ecb68-111">Activity</span></span>     |
| <span data-ttu-id="ecb68-112">Contabile</span><span class="sxs-lookup"><span data-stu-id="ecb68-112">Cost accountant</span></span>         | <span data-ttu-id="ecb68-113">Operations</span><span class="sxs-lookup"><span data-stu-id="ecb68-113">Operations</span></span>   |
| <span data-ttu-id="ecb68-114">Addetto contabilità</span><span class="sxs-lookup"><span data-stu-id="ecb68-114">Cost accountant clerk</span></span>   | <span data-ttu-id="ecb68-115">Operations</span><span class="sxs-lookup"><span data-stu-id="ecb68-115">Operations</span></span>   |
| <span data-ttu-id="ecb68-116">Controller oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="ecb68-116">Cost object controller</span></span>  | <span data-ttu-id="ecb68-117">Membri del team</span><span class="sxs-lookup"><span data-stu-id="ecb68-117">Team members</span></span> |

<span data-ttu-id="ecb68-118">In questo argomento viene descritto come assegnare il ruolo **Controller oggetto di costo** a un responsabile.</span><span class="sxs-lookup"><span data-stu-id="ecb68-118">This topic explains how to assign the **Cost object controller** role to a manager.</span></span>

<span data-ttu-id="ecb68-119">Quando il ruolo **Controller oggetto di costo** viene assegnato a un responsabile, il responsabile può effettuare le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="ecb68-119">When the **Cost object controller** role is assigned to a manager, the manager can perform the following tasks:</span></span>

- <span data-ttu-id="ecb68-120">Accedere all'area di lavoro **Controllo costi** nel client.</span><span class="sxs-lookup"><span data-stu-id="ecb68-120">Access the **Cost control** workspace (in the client).</span></span>

    - <span data-ttu-id="ecb68-121">Eseguire il drill-through e avere l'accesso in lettura alle pagine che supportano l'esperienza drill-through.</span><span class="sxs-lookup"><span data-stu-id="ecb68-121">Drill through and have view access to the pages that support the drill-through experience.</span></span>

- <span data-ttu-id="ecb68-122">Accedere all'area di lavoro **Controllo costi** nell'applicazione mobile.</span><span class="sxs-lookup"><span data-stu-id="ecb68-122">Access the **Cost control** workspace (in the mobile application).</span></span>

> [!NOTE]
> <span data-ttu-id="ecb68-123">Il ruolo **Controller oggetto di costo** non verifica per quale oggetti di costo l'utente può accedere e visualizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="ecb68-123">The **Cost object controller** role doesn't control which cost objects the user can access and view data for.</span></span> <span data-ttu-id="ecb68-124">La sicurezza a livello di riga viene fornita tramite le gerarchie di dimensioni e la gerarchia dell'elenco accessi.</span><span class="sxs-lookup"><span data-stu-id="ecb68-124">Row-level security is provided via dimension hierarchies and the Access list hierarchy.</span></span>

## <a name="grant-access-rights"></a><span data-ttu-id="ecb68-125">Concedere i diritti di accesso</span><span class="sxs-lookup"><span data-stu-id="ecb68-125">Grant access rights</span></span>
<span data-ttu-id="ecb68-126">Nel seguente esempio viene illustrato cosa è una gerarchia di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="ecb68-126">The following example shows what a dimension hierarchy can look like.</span></span>

<span data-ttu-id="ecb68-127">**Dettagli gerarchia dimensioni**</span><span class="sxs-lookup"><span data-stu-id="ecb68-127">**Dimension hierarchy details**</span></span>

| <span data-ttu-id="ecb68-128">Nome gerarchia dimensioni</span><span class="sxs-lookup"><span data-stu-id="ecb68-128">Dimension hierarchy name</span></span> | <span data-ttu-id="ecb68-129">Dimensione</span><span class="sxs-lookup"><span data-stu-id="ecb68-129">Dimension</span></span>    | <span data-ttu-id="ecb68-130">Nome tipo di gerarchia dimensioni</span><span class="sxs-lookup"><span data-stu-id="ecb68-130">Dimension hierarchy type name</span></span>      | <span data-ttu-id="ecb68-131">Gerarchia elenco accessi</span><span class="sxs-lookup"><span data-stu-id="ecb68-131">Access list hierarchy</span></span> |
|--------------------------|--------------|------------------------------------|-----------------------|
| <span data-ttu-id="ecb68-132">Organizzazione</span><span class="sxs-lookup"><span data-stu-id="ecb68-132">Organization</span></span>             | <span data-ttu-id="ecb68-133">Centri di costo</span><span class="sxs-lookup"><span data-stu-id="ecb68-133">Cost centers</span></span> | <span data-ttu-id="ecb68-134">Gerarchia classificazioni dimensione</span><span class="sxs-lookup"><span data-stu-id="ecb68-134">Dimension classification hierarchy</span></span> | <span data-ttu-id="ecb68-135">**Sì**</span><span class="sxs-lookup"><span data-stu-id="ecb68-135">**Yes**</span></span>               |

<span data-ttu-id="ecb68-136">È possibile utilizzare la scheda dettaglio **Utenti** nella finestra di progettazione della gerarchia per inserire una o più ID utente in ogni nodo.</span><span class="sxs-lookup"><span data-stu-id="ecb68-136">You can use the **Users** FastTab in the hierarchy designer to insert one or more user IDs on each node.</span></span>

|                                   | <span data-ttu-id="ecb68-137">Utenti</span><span class="sxs-lookup"><span data-stu-id="ecb68-137">Users</span></span>            | <span data-ttu-id="ecb68-138">Intervalli membro di dimensione</span><span class="sxs-lookup"><span data-stu-id="ecb68-138">Dimension member ranges</span></span>   |                         |
|-----------------------------------|------------------|---------------------------|-------------------------|
| <span data-ttu-id="ecb68-139">**Nodi**</span><span class="sxs-lookup"><span data-stu-id="ecb68-139">**Nodes**</span></span>                         | <span data-ttu-id="ecb68-140">**ID utente**</span><span class="sxs-lookup"><span data-stu-id="ecb68-140">**User ID**</span></span>      | <span data-ttu-id="ecb68-141">**Membro di dimensione di inizio**</span><span class="sxs-lookup"><span data-stu-id="ecb68-141">**From dimension member**</span></span> | <span data-ttu-id="ecb68-142">**Membro di dimensione di fine**</span><span class="sxs-lookup"><span data-stu-id="ecb68-142">**To dimension member**</span></span> |
| <span data-ttu-id="ecb68-143">Organizzazione</span><span class="sxs-lookup"><span data-stu-id="ecb68-143">Organization</span></span>                      | <span data-ttu-id="ecb68-144">Benjamin, Claire</span><span class="sxs-lookup"><span data-stu-id="ecb68-144">Benjamin, Claire</span></span> |                           |                         |
| <span data-ttu-id="ecb68-145">&nbsp;&nbsp;Amministratore</span><span class="sxs-lookup"><span data-stu-id="ecb68-145">&nbsp;&nbsp;Admin</span></span>                 | <span data-ttu-id="ecb68-146">aprile</span><span class="sxs-lookup"><span data-stu-id="ecb68-146">April</span></span>            |                           |                         |
| <span data-ttu-id="ecb68-147">&nbsp;&nbsp;&nbsp;&nbsp;Dati finanziari</span><span class="sxs-lookup"><span data-stu-id="ecb68-147">&nbsp;&nbsp;&nbsp;&nbsp;Finance</span></span>   | <span data-ttu-id="ecb68-148">Alicia</span><span class="sxs-lookup"><span data-stu-id="ecb68-148">Alicia</span></span>           | <span data-ttu-id="ecb68-149">CC002</span><span class="sxs-lookup"><span data-stu-id="ecb68-149">CC002</span></span>                     | <span data-ttu-id="ecb68-150">CC003</span><span class="sxs-lookup"><span data-stu-id="ecb68-150">CC003</span></span>                   |
|                                   |                  | <span data-ttu-id="ecb68-151">CC007</span><span class="sxs-lookup"><span data-stu-id="ecb68-151">CC007</span></span>                     | <span data-ttu-id="ecb68-152">CC007</span><span class="sxs-lookup"><span data-stu-id="ecb68-152">CC007</span></span>                   |
| <span data-ttu-id="ecb68-153">&nbsp;&nbsp;&nbsp;&nbsp;Risorse umane</span><span class="sxs-lookup"><span data-stu-id="ecb68-153">&nbsp;&nbsp;&nbsp;&nbsp;HR</span></span>        | <span data-ttu-id="ecb68-154">Arnie</span><span class="sxs-lookup"><span data-stu-id="ecb68-154">Arnie</span></span>            | <span data-ttu-id="ecb68-155">CC001</span><span class="sxs-lookup"><span data-stu-id="ecb68-155">CC001</span></span>                     | <span data-ttu-id="ecb68-156">CC001</span><span class="sxs-lookup"><span data-stu-id="ecb68-156">CC001</span></span>                   |
| <span data-ttu-id="ecb68-157">&nbsp;&nbsp;Produzione</span><span class="sxs-lookup"><span data-stu-id="ecb68-157">&nbsp;&nbsp;Production</span></span>            | <span data-ttu-id="ecb68-158">David</span><span class="sxs-lookup"><span data-stu-id="ecb68-158">David</span></span>            |                           |                         |
| <span data-ttu-id="ecb68-159">&nbsp;&nbsp;&nbsp;&nbsp;Imballaggio</span><span class="sxs-lookup"><span data-stu-id="ecb68-159">&nbsp;&nbsp;&nbsp;&nbsp;Packaging</span></span> | <span data-ttu-id="ecb68-160">Ellen</span><span class="sxs-lookup"><span data-stu-id="ecb68-160">Ellen</span></span>            | <span data-ttu-id="ecb68-161">CC005</span><span class="sxs-lookup"><span data-stu-id="ecb68-161">CC005</span></span>                     | <span data-ttu-id="ecb68-162">CC005</span><span class="sxs-lookup"><span data-stu-id="ecb68-162">CC005</span></span>                   |
| <span data-ttu-id="ecb68-163">&nbsp;&nbsp;&nbsp;&nbsp;Assemblaggio</span><span class="sxs-lookup"><span data-stu-id="ecb68-163">&nbsp;&nbsp;&nbsp;&nbsp;Assembly</span></span>  | <span data-ttu-id="ecb68-164">Chris</span><span class="sxs-lookup"><span data-stu-id="ecb68-164">Chris</span></span>            | <span data-ttu-id="ecb68-165">CC006</span><span class="sxs-lookup"><span data-stu-id="ecb68-165">CC006</span></span>                     | <span data-ttu-id="ecb68-166">CC006</span><span class="sxs-lookup"><span data-stu-id="ecb68-166">CC006</span></span>                   |

> [!NOTE]
> <span data-ttu-id="ecb68-167">I contabili devono essere assegnati al primo livello della gerarchia, in modo che possano visualizzare tutte le voci della contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="ecb68-167">Cost accountants should be assigned to the top level of the hierarchy, so that they can see all entries in Cost accounting.</span></span>

<span data-ttu-id="ecb68-168">Prima che la gerarchia dell'elenco accessi e le impostazioni di sicurezza possano essere applicate, l'opzione **Abilita accesso in visualizzazione per membri di dimensione oggetto di costo** deve essere impostata su **Sì** nella scheda **Generale** della pagina **Parametri di contabilità industriale** (**Contabilità industriale** > **Impostazione** > **Parametri**).</span><span class="sxs-lookup"><span data-stu-id="ecb68-168">Before the Access list hierarchy and its security settings can be applied, the **Enable view access for cost object dimension members** option must be set to **Yes** on the **General** tab of the **Cost accounting parameters** page (**Cost accounting** > **Setup** > **Parameters**).</span></span>

<span data-ttu-id="ecb68-169">Le impostazioni per la gerarchia dell'elenco accessi vengono utilizzate per controllare i dati visualizzati nelle seguenti aree:</span><span class="sxs-lookup"><span data-stu-id="ecb68-169">The settings for the Access list hierarchy are used to control the data that is shown in following areas:</span></span>

- <span data-ttu-id="ecb68-170">Area di lavoro **controllo costi** nel client:</span><span class="sxs-lookup"><span data-stu-id="ecb68-170">**Cost control** workspace (in the client):</span></span>

    - <span data-ttu-id="ecb68-171">Dati delle pagine utilizzate per il drill-through</span><span class="sxs-lookup"><span data-stu-id="ecb68-171">Data on the pages that are used for drill-through</span></span>

- <span data-ttu-id="ecb68-172">Area di lavoro **Controllo costi** nell'applicazione mobile:</span><span class="sxs-lookup"><span data-stu-id="ecb68-172">**Cost control** workspace (in the mobile application):</span></span>

    - <span data-ttu-id="ecb68-173">Saldi nelle schede</span><span class="sxs-lookup"><span data-stu-id="ecb68-173">Balances in cards</span></span>

- <span data-ttu-id="ecb68-174">Microsoft Power BI:</span><span class="sxs-lookup"><span data-stu-id="ecb68-174">Microsoft Power BI:</span></span>

    - <span data-ttu-id="ecb68-175">Data visualizzati nelle visualizzazioni di Power BI</span><span class="sxs-lookup"><span data-stu-id="ecb68-175">Data that is shown in Power BI visualizations</span></span>
    - <span data-ttu-id="ecb68-176">Le visualizzazioni dei dati di Power BI sono incorporate nel client Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ecb68-176">Data Power BI visualizations that are embedded in the Microsoft Dynamics 365 for Finance and Operations, client</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="ecb68-177">Prima che la gerarchia dell'elenco accessi possa influire sui dati in Power BI, la gerarchia dell'elenco accessi e la sicurezza a livello di riga in Power BI devono essere abbinate.</span><span class="sxs-lookup"><span data-stu-id="ecb68-177">Before the Access list hierarchy can affect data in Power BI, the Access list hierarchy and row-level security in Power BI must be paired.</span></span> <span data-ttu-id="ecb68-178">Per ulteriori informazioni, vedere [Impostare la sicurezza del pacchetto di contenuti per la contabilità industriale](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span><span class="sxs-lookup"><span data-stu-id="ecb68-178">For more information, see [Set up security for Cost accounting content pack](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span></span>
> - <span data-ttu-id="ecb68-179">In questo argomento vengono illustrati i prerequisiti che devono essere definiti prima di poter utilizzare l'area di lavoro **Controllo costi**.</span><span class="sxs-lookup"><span data-stu-id="ecb68-179">This topic shows the prerequisites that must be in place before you can use the **Cost control** workspace.</span></span>

<span data-ttu-id="ecb68-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecb68-180">See also</span></span>

- [<span data-ttu-id="ecb68-181">Area di lavoro controllo costi</span><span class="sxs-lookup"><span data-stu-id="ecb68-181">Cost control workspace</span></span>](cost-control-workspace.md)
- [<span data-ttu-id="ecb68-182">Gerarchia dimensioni</span><span class="sxs-lookup"><span data-stu-id="ecb68-182">Dimension hierarchy</span></span>](dimension-hierarchy.md)
- [<span data-ttu-id="ecb68-183">Impostare la sicurezza per il pacchetto di contenuti della contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="ecb68-183">Set up security for Cost accounting content pack</span></span>](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)

