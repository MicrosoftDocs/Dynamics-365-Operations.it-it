---
title: Modelli di carico
description: In questo argomento viene descritto come impostare i modelli di carico e come associare un modello di carico a un nuovo carico.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 80004b5d22e1cf81c1ffa9f74c2c479e1561df72
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247216"
---
# <a name="load-templates"></a><span data-ttu-id="e2840-103">Modelli di carico</span><span class="sxs-lookup"><span data-stu-id="e2840-103">Load templates</span></span>

<span data-ttu-id="e2840-104">Quando si crea un nuovo carico, è possibile assegnare un modello di carico.</span><span class="sxs-lookup"><span data-stu-id="e2840-104">When you create a new load, you can assign a load template.</span></span> <span data-ttu-id="e2840-105">Il modello di carico contiene informazioni sull'attrezzatura e sulle misure quali altezza, larghezza, profondità e volume del carico.</span><span class="sxs-lookup"><span data-stu-id="e2840-105">The load template contains information about equipment, and about measures such as the height, width, depth, and volume of the load.</span></span>

<span data-ttu-id="e2840-106">In questo argomento viene descritto come impostare i modelli di carico e come associare un modello di carico a un nuovo carico.</span><span class="sxs-lookup"><span data-stu-id="e2840-106">This topic describes how to set up load templates, and how to associate a load template with a new load.</span></span>

## <a name="set-up-a-load-template"></a><span data-ttu-id="e2840-107">Impostare un modello di carico</span><span class="sxs-lookup"><span data-stu-id="e2840-107">Set up a load template</span></span>

1. <span data-ttu-id="e2840-108">Andare a **Gestione trasporti \> Impostazione \> Allestimento del carico \> Modello carico**.</span><span class="sxs-lookup"><span data-stu-id="e2840-108">Go to **Transportation management \> Setup \> Load Building \> Load template**.</span></span>
1. <span data-ttu-id="e2840-109">Nel riquadro azioni selezionare **Nuovo** per aggiungere un nuovo modello oppure **Modifica** per modificare un modello esistente.</span><span class="sxs-lookup"><span data-stu-id="e2840-109">On the Action Pane, select **New** to add a new template or **Edit** to edit an existing template.</span></span>
1. <span data-ttu-id="e2840-110">Nella riga del modello nuovo o esistente, impostare i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="e2840-110">In the row for the new or existing template, set the following fields:</span></span>

    - <span data-ttu-id="e2840-111">**ID modello di carico** – Immettere un identificatore (ID) univoco per il modello di carico.</span><span class="sxs-lookup"><span data-stu-id="e2840-111">**Load template ID** – Enter a unique identifier (ID) for the load template.</span></span>
    - <span data-ttu-id="e2840-112">**Attrezzatura** - Selezionare l'attrezzatura da utilizzare per spedire il carico.</span><span class="sxs-lookup"><span data-stu-id="e2840-112">**Equipment** – Select the equipment that should be used to ship the load.</span></span>
    - <span data-ttu-id="e2840-113">**Altezza carico**, **Larghezza carico** e **Profondità carico** - Immettere le dimensioni del carico.</span><span class="sxs-lookup"><span data-stu-id="e2840-113">**Load height**, **Load width**, and **Load depth** – Enter the dimensions of the load.</span></span>
    - <span data-ttu-id="e2840-114">**Volume carico massimo consentito** e **Peso carico massimo consentito** - Immettere il volume e il peso massimi consentiti del carico.</span><span class="sxs-lookup"><span data-stu-id="e2840-114">**Max. allowed load volume** and **Max. allowed load weight** – Enter the maximum allowed volume and weight of the load.</span></span>
    - <span data-ttu-id="e2840-115">**Peso lordo massimo consentito** - Immettere il peso lordo massimo consentito del carico.</span><span class="sxs-lookup"><span data-stu-id="e2840-115">**Maximum allowed gross weight** – Enter the maximum allowed gross weight of the load.</span></span> <span data-ttu-id="e2840-116">Il peso lordo del carico include la tara e il peso di carico.</span><span class="sxs-lookup"><span data-stu-id="e2840-116">A load's gross weight includes both its tare weight and its loading weight.</span></span>
    - <span data-ttu-id="e2840-117">**Numero massimo di colli consentito** - Immettere il numero massimo di pezzi di trasporto che il carico può contenere.</span><span class="sxs-lookup"><span data-stu-id="e2840-117">**Maximum number of freight pieces allowed** – Enter the maximum number of freight pieces that the load can contain.</span></span>
    - <span data-ttu-id="e2840-118">**Impila carico su piano** - Selezionare questa casella di controllo per utilizzare il caricamento di reparto.</span><span class="sxs-lookup"><span data-stu-id="e2840-118">**Stack load on floor** – Select this check box to use floor loading.</span></span> <span data-ttu-id="e2840-119">In uno scenario di caricamento di reparto le scatole vengono impilate dal pavimento al soffitto, da parete a parete all'interno del contenitore per ottimizzare la capacità.</span><span class="sxs-lookup"><span data-stu-id="e2840-119">In a floor loading scenario, boxes are stacked floor to ceiling and wall to wall inside the container, to maximize capacity.</span></span>

1. <span data-ttu-id="e2840-120">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e2840-120">On the Action Pane, select **Save**.</span></span>

## <a name="associate-a-load-template-with-a-new-load"></a><span data-ttu-id="e2840-121">Associare un modello di carico a un nuovo carico</span><span class="sxs-lookup"><span data-stu-id="e2840-121">Associate a load template with a new load</span></span>

1. <span data-ttu-id="e2840-122">Andare a **Gestione trasporto \> Pianificazione \> Workbench pianificazione carico**.</span><span class="sxs-lookup"><span data-stu-id="e2840-122">Go to **Transportation management \> Planning \> Load planning workbench**.</span></span>
1. <span data-ttu-id="e2840-123">Nella parte superiore della pagina, selezionare una delle seguenti schede, a seconda del tipo di documento di origine per il quale si sta creando un carico: **Spedizioni**, **Righe vendita**, **Righe trasferimento** o **Righe ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="e2840-123">In the upper part of the page, select one of the following tabs, depending on the type of source document that you're creating a load for: **Shipments**, **Sales lines**, **Transfer lines**, or **Purchase order lines**.</span></span> 
1. <span data-ttu-id="e2840-124">Selezionare il documento specifico per cui pianificare il carico.</span><span class="sxs-lookup"><span data-stu-id="e2840-124">Select the specific document to plan the load for.</span></span>
1. <span data-ttu-id="e2840-125">Nel riquadro azioni, nella scheda **Domanda e offerta**, nel gruppo **Aggiungi** seleziona **Al nuovo carico**.</span><span class="sxs-lookup"><span data-stu-id="e2840-125">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span>
1. <span data-ttu-id="e2840-126">Nella finestra di dialogo **Modello carico**,nel campo **ID modello di carico** selezionare il modello da applicare.</span><span class="sxs-lookup"><span data-stu-id="e2840-126">In the **Load template** dialog box, in the **Load template ID** field, select the template to apply.</span></span>
1. <span data-ttu-id="e2840-127">Selezionare **OK** per applicare il modello.</span><span class="sxs-lookup"><span data-stu-id="e2840-127">Select **OK** to apply the template.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]