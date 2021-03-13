---
title: Livelli di servizio cespiti
description: In questo argomento vengono descritti i livelli di servizio cespiti in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 83b195add44927d847491e6394e72637323117b3
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021631"
---
# <a name="asset-service-levels"></a><span data-ttu-id="649dc-103">Livelli di servizio cespiti</span><span class="sxs-lookup"><span data-stu-id="649dc-103">Asset service levels</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="649dc-104">In questo argomento vengono descritti i livelli di servizio cespiti in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="649dc-104">This topic explains asset service levels in Asset Management.</span></span> <span data-ttu-id="649dc-105">I livelli di servizio cespiti sono correlati ai cespiti e trasferiti alle richieste di intervento di manutenzione e ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="649dc-105">Asset service levels are related to assets, and are transferred to maintenance requests and work orders.</span></span> <span data-ttu-id="649dc-106">Vengono utilizzati per calcolare la priorità degli ordini di lavoro durante la programmazione degli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="649dc-106">They are used to calculate the priority of work orders during work order scheduling.</span></span> <span data-ttu-id="649dc-107">I livelli di servizio cespiti possono essere modificati, se le modifiche sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="649dc-107">Asset service levels can be changed, if changes are required.</span></span>

<span data-ttu-id="649dc-108">Per ulteriori informazioni sull'impostazione relativa al calcolo dei punteggi di valutazione per la programmazione degli ordini di lavoro, vedere [Parametri di Gestione cespiti](../setup-for-objects/enterprise-asset-management-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="649dc-108">For more information about the setup that is related to the calculation of rating scores for work order scheduling, see [Asset Management parameters](../setup-for-objects/enterprise-asset-management-parameters.md).</span></span> <span data-ttu-id="649dc-109">È necessario impostare almeno un record predefinito per il livello di servizio cespiti.</span><span class="sxs-lookup"><span data-stu-id="649dc-109">You must set up at least one default record for the asset service level.</span></span> <span data-ttu-id="649dc-110">Questo record predefinito viene utilizzato se non sono presenti altre corrispondenze durante la programmazione degli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="649dc-110">This default record is used if no other match is found during work order scheduling.</span></span>

<span data-ttu-id="649dc-111">**Esempio 1:** Il livello di servizio predefinito utilizzato se non sono presenti altre corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="649dc-111">**Example 1:** The default service level that is used if no other match is found.</span></span> <span data-ttu-id="649dc-112">In questo record, si seleziona solo un livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="649dc-112">In this record, you select only a service level.</span></span>

<span data-ttu-id="649dc-113">**Esempio 2:** un livello di servizio elevato utilizzato per la programmazione dei processi per un camion Volvo.</span><span class="sxs-lookup"><span data-stu-id="649dc-113">**Example 2:** A high service level that is used to schedule jobs for a Volvo truck engine.</span></span> <span data-ttu-id="649dc-114">In questo record, si selezionare un tipo di cespite pertinente (ad esempio **Camion**), un produttore (**Volvo**) e un livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="649dc-114">In this record, you select a relevant asset type (such as **Truck Engine**), a manufacturer (**Volvo**), and a service level.</span></span>

## <a name="set-up-asset-service-levels"></a><span data-ttu-id="649dc-115">Impostare i livelli di servizio cespiti</span><span class="sxs-lookup"><span data-stu-id="649dc-115">Set up asset service levels</span></span>

1. <span data-ttu-id="649dc-116">Selezionare **Gestione cespiti** \> **Impostazione** \> **Livelli di servizio cespiti**.</span><span class="sxs-lookup"><span data-stu-id="649dc-116">Select **Asset management** \> **Setup** \> **Asset service levels**.</span></span>
2. <span data-ttu-id="649dc-117">Selezionare **Nuovo** per creare un record.</span><span class="sxs-lookup"><span data-stu-id="649dc-117">Select **New** to create a record.</span></span>
3. <span data-ttu-id="649dc-118">A seconda del livello di dettaglio necessario per il livello di servizio cespiti, selezionare opzioni appropriate nei campi **Unità funzionale**, **Tipo di cespite**, **Produttore**, **Modello**, **Cespite**, **Tipo di ordine di lavoro** e **Livello servizio**.</span><span class="sxs-lookup"><span data-stu-id="649dc-118">Depending on the detail level that is required for the asset service level, make relevant selections in the **Functional location**, **Asset type**, **Manufacturer**, **Model**, **Asset**, **Work order type**, and **Service level** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="649dc-119">Quando il livello di servizio cespiti viene utilizzato per le richieste di intervento di manutenzione e gli ordini di lavoro, Gestione cespiti analizza tutti i record di livello di servizio cespiti per verificare la presenza di una corrispondenza possibile.</span><span class="sxs-lookup"><span data-stu-id="649dc-119">When the asset service level is used for maintenance requests and work orders, Asset Management goes through all asset service level records to check for a possible match.</span></span> <span data-ttu-id="649dc-120">Controlla sempre la combinazione più specifica per prima.</span><span class="sxs-lookup"><span data-stu-id="649dc-120">It always checks the most specific combination first.</span></span> <span data-ttu-id="649dc-121">In altre parole, Gestione cespiti controlla prima **Tipo di ordine di lavoro** per trovare una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="649dc-121">In other words, Asset Management first checks for a match for the **Work order type** field.</span></span> <span data-ttu-id="649dc-122">Se non trova corrispondenza, controlla **Cespite** e così via.</span><span class="sxs-lookup"><span data-stu-id="649dc-122">If no match is found, it checks for a match for the **Asset** field, and so on.</span></span> <span data-ttu-id="649dc-123">Come si vede nel layout della pagina **Livelli di servizio cespiti**, questo comportamento significa che, per individuare la combinazione più specifica, Gestione cespiti controlla ogni record da destra a-sinistra per una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="649dc-123">As you can see in the layout of the **Asset service levels** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="649dc-124">Se non viene trovata alcuna corrispondenza, il record predefinito senza selezioni in quei campi viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="649dc-124">If no match is found, the default record that has no selections in those fields is used.</span></span>

4. <span data-ttu-id="649dc-125">Nel campo **Livello servizio**, selezionare un numero che indica il livello di servizio (priorità).</span><span class="sxs-lookup"><span data-stu-id="649dc-125">In the **Service level** field, select a number that indicates the service level (priority).</span></span>


> [!NOTE]
> <span data-ttu-id="649dc-126">Se si modifica un record di livello di servizio cespiti nella pagina **Livelli di servizio cespiti** dopo che è stato già utilizzato in un ordine di lavoro, il livello di servizio per le richieste di intervento di manutenzione e ordini di lavoro non verrà aggiornato di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="649dc-126">If you change an asset service level record on the **Asset service levels** page after you've already used it on a work order, the service level on maintenance requests and work orders isn't updated accordingly.</span></span>
