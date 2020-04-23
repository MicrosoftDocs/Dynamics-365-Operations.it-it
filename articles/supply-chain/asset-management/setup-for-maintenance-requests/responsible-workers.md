---
title: Addetti alla manutenzione responsabili
description: In questo argomento viene illustrato come impostare gli addetti alla manutenzione responsabili in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b5f83474e56c996a40bdbdf7d3a7c8d495429c6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208940"
---
# <a name="responsible-maintenance-workers"></a><span data-ttu-id="adb17-103">Addetti alla manutenzione responsabili</span><span class="sxs-lookup"><span data-stu-id="adb17-103">Responsible maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="adb17-104">Gli addetti alla manutenzione responsabili possono essere correlati ai tipi di cespite, ai cespiti, unità funzionali, le categorie di tipi di processi di manutenzione, ai tipi di processi di manutenzione, varianti di tipi di processi di manutenzione e alle mansioni qualificate.</span><span class="sxs-lookup"><span data-stu-id="adb17-104">Responsible maintenance workers can be related to asset types, assets, functional locations, maintenance job type categories, maintenance job types, maintenance job type variants, and trades.</span></span> <span data-ttu-id="adb17-105">Possono essere utilizzati negli ordini di lavoro e nelle richieste di intervento di manutenzione per indicare una preferenza relativa agli addetti alla manutenzione che devono essere responsabile di un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="adb17-105">They can be used on work orders and maintenance requests to indicate a preference about the maintenance workers who should be responsible for a work order.</span></span> <span data-ttu-id="adb17-106">(Tuttavia, questi addetti alla manutenzione non sono necessariamente gli lavoratori che vengano programmati per eseguire l'ordine di lavoro.) L'utilizzo di questa funzionalità è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="adb17-106">(However, those maintenance workers aren't necessarily the same workers who are scheduled to carry out the work order.) Use of this functionality is optional.</span></span> <span data-ttu-id="adb17-107">Ad esempio, la si può utilizzare per selezionare i lavoratori o i gruppi di lavoratori responsabili per determinati tipi o aree di lavoro.</span><span class="sxs-lookup"><span data-stu-id="adb17-107">For example, it can be used to select responsible workers or worker groups for specific work types or work areas.</span></span>

<span data-ttu-id="adb17-108">Durante il ciclo di vita di un ordine di lavoro o una richiesta di intervento di manutenzione, gli addetti alla manutenzione responsabili possono essere modificati o aggiornati.</span><span class="sxs-lookup"><span data-stu-id="adb17-108">During a work order lifecycle or a maintenance request lifecycle, responsible maintenance workers can be changed or updated.</span></span> <span data-ttu-id="adb17-109">Questa modifica o aggiornamento può essere correlato, ad esempio, a una modifica dello stato del ciclo di vita della richiesta di intervento di manutenzione o dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="adb17-109">This change or update might be related to, for example, a change in the maintenance request lifecycle state or the work order lifecycle state.</span></span>

<span data-ttu-id="adb17-110">L'impostazione della pagina **Addetti alla manutenzione responsabili** *non* viene utilizzata durante la programmazione degli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="adb17-110">The setup on the **Responsible maintenance workers** page is *not* used during work order scheduling.</span></span>

> [!NOTE]
> <span data-ttu-id="adb17-111">In Gestione cespiti, è inoltre possibile impostare gli addetti alla manutenzione *preferiti* che possono essere assegnati agli ordini di lavoro durante la programmazione degli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="adb17-111">In Asset Management, you can also set up *preferred* maintenance workers who might be allocated to work orders during work order scheduling.</span></span>

<span data-ttu-id="adb17-112">Prima di poter impostare gli addetti alla manutenzione responsabili, è necessario impostare i lavoratori e i gruppi di addetti alla manutenzione che devono essere disponibili per la selezione.</span><span class="sxs-lookup"><span data-stu-id="adb17-112">Before you can set up responsible maintenance workers, you must set up the workers and maintenance worker groups that should be available for selection.</span></span> <span data-ttu-id="adb17-113">Per informazioni su come impostare i lavoratori e i gruppi di addetti alla manutenzione, vedere [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="adb17-113">For information about how to set up workers and maintenance worker groups, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

## <a name="set-up-responsible-maintenance-workers"></a><span data-ttu-id="adb17-114">Imposta gli addetti alla manutenzione responsabili</span><span class="sxs-lookup"><span data-stu-id="adb17-114">Set up responsible maintenance workers</span></span>

1. <span data-ttu-id="adb17-115">Selezionare **Gestione cespiti** \> **Impostazione** \> **Lavoratori** \> **Addetti alla manutenzione responsabili**.</span><span class="sxs-lookup"><span data-stu-id="adb17-115">Select **Asset management** \> **Setup** \> **Workers** \> **Responsible maintenance workers**.</span></span>
2. <span data-ttu-id="adb17-116">Selezionare **Nuovo** per creare un record.</span><span class="sxs-lookup"><span data-stu-id="adb17-116">Select **New** to create a record.</span></span>
3. <span data-ttu-id="adb17-117">Creare innanzitutto un'impostazione predefinita di addetto alla manutenzione responsabile o di gruppo di addetti alla manutenzione responsabili, in cui impostate soltanto il campo **Gruppo di addetti alla manutenzione responsabili** e/o il campo **Lavoratore responsabile**.</span><span class="sxs-lookup"><span data-stu-id="adb17-117">First create a default responsible maintenance worker or responsible maintenance worker group setup, where you set only the **Responsible maintenance worker group** field and/or the **Responsible worker** field.</span></span> <span data-ttu-id="adb17-118">Lasciare vuoti i campi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="adb17-118">Leave the remaining fields blank.</span></span> <span data-ttu-id="adb17-119">Questa impostazione predefinita verrà utilizzata durante la programmazione degli ordini di lavoro se nessun'altra combinazione più specifica corrisponde al contenuto dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="adb17-119">This default setup will be used during work order scheduling if no other, more specific combination matches the contents of the work order.</span></span>

    > [!NOTE]
    > <span data-ttu-id="adb17-120">Durante la creazione di una richiesta di intervento di manutenzione, quando un addetto alla manutenzione responsabile o un gruppo di addetti alla manutenzione responsabili vengono resi disponibili per la selezione nella pagina **Tutte le richieste di intervento di manutenzione**, Gestione cespiti analizza tutti i record lavoratori responsabili di manutenzione per verificare la presenza di una corrispondenza possibile.</span><span class="sxs-lookup"><span data-stu-id="adb17-120">During creation of a maintenance request, when a responsible maintenance worker or responsible maintenance worker group is made available for selection on the **All maintenance requests** page, Asset Management goes through all responsible maintenance worker records to check for a possible match.</span></span> <span data-ttu-id="adb17-121">Controlla sempre la combinazione più specifica per prima.</span><span class="sxs-lookup"><span data-stu-id="adb17-121">It always checks the most specific combination first.</span></span> <span data-ttu-id="adb17-122">In altre parole, Gestione cespiti controlla prima **Mansione qualificata** per trovare una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="adb17-122">In other words, Asset Management first checks for a match for the **Trade** field.</span></span> <span data-ttu-id="adb17-123">Se non trova corrispondenza, controlla **Variante tipo di processo di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="adb17-123">If no match is found, it checks for a match for the **Maintenance job type variant** field.</span></span> <span data-ttu-id="adb17-124">Se non trova corrispondenza, controlla **Tipo di processo di manutenzione** e così via.</span><span class="sxs-lookup"><span data-stu-id="adb17-124">If no match is found, it checks for a match for the **Maintenance job type** field, and so on.</span></span> <span data-ttu-id="adb17-125">Come si vede nel layout di questa pagina, questo comportamento significa che, per individuare la combinazione più specifica, Gestione cespiti controlla ogni record da destra a-sinistra per trovare una corrispondenza (prima **Mansione qualificata**, poi **Variante tipo di processo di manutenzione** poi **Tipo di processo di manutenzione**, poi **Categoria tipo di processo di manutenzione**, poi **UNità funzionale**, quindi **Cespite** e infine **Tipo di cespite**).</span><span class="sxs-lookup"><span data-stu-id="adb17-125">As you can see in the layout of the page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match (first **Trade**, then **Maintenance job type variant**, then **Maintenance job type**, then **Maintenance job type category**, then **Functional location**, then **Asset**, and finally **Asset type**).</span></span> <span data-ttu-id="adb17-126">Se non viene trovata alcuna corrispondenza, il record predefinito senza selezioni in quei sette campi viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="adb17-126">If no match is found, the default record that has no selections in those seven fields is used.</span></span>

<span data-ttu-id="adb17-127">Nella figura seguente è illustrato un esempio della pagina **Addetti alla manutenzione responsabili**.</span><span class="sxs-lookup"><span data-stu-id="adb17-127">The following illustration shows an example of the **Responsible maintenance workers** page.</span></span>

![Pagina Addetti alla manutenzione responsabili](media/08-setup-for-requests.png)
