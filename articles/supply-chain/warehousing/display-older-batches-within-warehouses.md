---
title: Configurare la visualizzazione dei batch meno recenti di un magazzino su un dispositivo mobile
description: In questo argomento viene descritto come configurare un dispositivo mobile per visualizzare un elenco di ubicazioni con batch meno recenti rispetto a quelli dell'ubicazione corrente di una riga di lavoro.
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 946266e73d59bdf383f1f91cdf70dd58f01b995c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "352645"
---
# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a><span data-ttu-id="3da27-103">Configurare la visualizzazione dei batch meno recenti di un magazzino su un dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="3da27-103">Configure Display older batches within warehouse on a mobile device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3da27-104">La configurazione **Visualizza batch meno recenti di un magazzino** consente di visualizzare un elenco di ubicazioni con batch meno recenti rispetto a quelli dell'ubicazione corrente della riga di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3da27-104">The **Display older batches within warehouse** configuration lets you display a list of locations with batches older than the current location of the work line.</span></span> <span data-ttu-id="3da27-105">L'elenco delle ubicazioni visualizzate include informazioni sui batch meno recenti nell'ubicazione con la data di scadenza e l'inventario fisico di ogni batch.</span><span class="sxs-lookup"><span data-stu-id="3da27-105">The list of locations that are displayed includes information about the older batches in the location with the expiration date and the physical inventory of each batch.</span></span> <span data-ttu-id="3da27-106">È possibile scegliere di prelevare da una nuova ubicazione o di continuare a prelevare dall'ubicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="3da27-106">You can choose to pick from a new location or to continue picking from the current location.</span></span> 
- <span data-ttu-id="3da27-107">Preleva da una nuova ubicazione - Se si seleziona il prelievo da una nuova ubicazione, la riga di lavoro corrente verrà aggiornata per utilizzare la nuova ubicazione e il lavoro continuerà normalmente con la nuova ubicazione.</span><span class="sxs-lookup"><span data-stu-id="3da27-107">Pick from a new location - If you select a new location to pick from, the  current work line will be updated to use the new location and work will continue as usual with the new location.</span></span> <span data-ttu-id="3da27-108">Affinché la nuova ubicazione sia valida, deve avere una quantità disponibile sufficiente per l'intera riga di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3da27-108">For the new location to be valid, it must have enough available quantity for the whole work line.</span></span> <span data-ttu-id="3da27-109">Se la quantità richiesta non è disponibile, la riga di lavoro non verrà aggiornata e verrà visualizzato l'elenco.</span><span class="sxs-lookup"><span data-stu-id="3da27-109">If the required quantity is not available, the work line will not be updated, and the list will display.</span></span> 
- <span data-ttu-id="3da27-110">Continua a prelevare dalla posizione corrente - Se si continua con l'ubicazione della riga di lavoro corrente, le quantità per la riga di lavoro continueranno a essere prelevate dall'ubicazione originale.</span><span class="sxs-lookup"><span data-stu-id="3da27-110">Continue picking from the current location - If you continue with the current work line location, the quantities for the work line will continue to be picked from the original location.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="3da27-111">Dove si applica</span><span class="sxs-lookup"><span data-stu-id="3da27-111">Where it applies</span></span>
<span data-ttu-id="3da27-112">La visualizzazione dei batch meno recenti è configurata nelle voci di menu del dispositivo mobile e ha impatto sul prelievo di batch degli articoli seguenti.</span><span class="sxs-lookup"><span data-stu-id="3da27-112">Display older batches within warehouse is configured on mobile device menu items and affects the pick for batch below items.</span></span>

## <a name="set-up-display-older-batches-within-warehouse"></a><span data-ttu-id="3da27-113">Configurare la visualizzazione di batch meno recenti nel magazzino</span><span class="sxs-lookup"><span data-stu-id="3da27-113">Set up Display older batches within warehouse</span></span>
<span data-ttu-id="3da27-114">La configurazione **Visualizza batch meno recenti all'interno del magazzino** è disponibile per le voci di menu del dispositivo mobile se l'opzione **Preleva batch meno recente** è impostata su **Avvisa**.</span><span class="sxs-lookup"><span data-stu-id="3da27-114">The **Display older batches within warehouse** configuration is available on mobile device menu items when the **Pick oldest batch** option is set to **Warn**.</span></span>

- <span data-ttu-id="3da27-115">In **Gestione magazzino** > **Impostazioni** > **Dispositivo mobile** > **Voci di menu del dispositivo mobile** impostare **Utilizza lavoro esistente** su **Sì** per la voce di menu e selezionare **Avvisa** nel campo **Preleva batch meno recente**.</span><span class="sxs-lookup"><span data-stu-id="3da27-115">Under **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**, set **Use existing work** to **Yes** for the menu item, and select **Warn** in the **Pick oldest batch** field.</span></span> 

