---
title: Valutazione delle condizioni
description: In questo argomento viene descritto come creare un modello e una registrazione di valutazione delle condizioni di un cespite in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectCondition, EntAssetConditionTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 774c788959c5ebea69b4d22c886ac673f50b97f5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431257"
---
# <a name="condition-assessment"></a><span data-ttu-id="c9102-103">Valutazione delle condizioni</span><span class="sxs-lookup"><span data-stu-id="c9102-103">Condition assessment</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="c9102-104">In questo argomento viene descritto come creare un modello e una registrazione di valutazione delle condizioni di un cespite in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="c9102-104">This topic explains how to create a condition assessment template and registration on an asset in Asset Management.</span></span> <span data-ttu-id="c9102-105">La valutazione delle condizioni viene eseguita a intervalli regolari e l'obiettivo principale è di creare e gestire i dati di condizione sui cespiti.</span><span class="sxs-lookup"><span data-stu-id="c9102-105">Condition assessment is performed at regular intervals, and the primary objective is to create and maintain condition data on assets.</span></span> <span data-ttu-id="c9102-106">Visto da una prospettiva di manutenzione preventiva, è importante monitorare le informazioni come la condizione attuale e la durata rimanente.</span><span class="sxs-lookup"><span data-stu-id="c9102-106">Seen from a preventive maintenance perspective, it is important to monitor key information such as current condition, and remaining life span.</span></span> <span data-ttu-id="c9102-107">Inoltre, se si effettua la valutazione delle condizioni a intervalli regolari, sarà possibile monitorare e confrontare le condizioni dei macchinari nella fabbrica.</span><span class="sxs-lookup"><span data-stu-id="c9102-107">Furthermore, if you carry out condition assessment at regular intervals, you will be able to monitor and compare conditions on the machinery in your factory.</span></span>

<span data-ttu-id="c9102-108">Valutazione delle condizioni può essere utilizzata per misurare e monitorare molte condizioni nelle attrezzature.</span><span class="sxs-lookup"><span data-stu-id="c9102-108">Condition assessment can be used to measure and monitor many conditions on your equipment.</span></span> <span data-ttu-id="c9102-109">Esempio: È possibile misurare le vibrazioni del macchinario.</span><span class="sxs-lookup"><span data-stu-id="c9102-109">Example: You could measure vibrations on your machinery.</span></span> <span data-ttu-id="c9102-110">Dopo la registrazione delle misure delle vibrazioni in Gestione cespiti dei vari tipi di attrezzature, è possibile eseguire la ricerca dell'ultima valutazione registrata e visualizzare le misure delle vibrazioni.</span><span class="sxs-lookup"><span data-stu-id="c9102-110">After you have registered vibration measurements in Asset Management on various types of equipment, you can search for the latest registered assessment and view vibration measurements.</span></span>

<span data-ttu-id="c9102-111">Valutazione delle condizioni viene creata sui cespiti.</span><span class="sxs-lookup"><span data-stu-id="c9102-111">Condition assessment is created on assets.</span></span> <span data-ttu-id="c9102-112">Si deve configurare un modello di valutazione delle condizioni per un tipo di cespite prima di eseguire la procedura di valutazione delle condizioni.</span><span class="sxs-lookup"><span data-stu-id="c9102-112">You set up a condition assessment template on an asset type before you carry out the condition assessment procedure.</span></span> <span data-ttu-id="c9102-113">Motivo per utilizzare i modelli per la valutazione delle condizioni è evitare la variazione dei dati di condizione per cespiti simili.</span><span class="sxs-lookup"><span data-stu-id="c9102-113">The reason for using templates for condition assessment is to avoid variation of condition data on similar assets.</span></span> <span data-ttu-id="c9102-114">La sequenza per la configurazione e l'utilizzo della valutazione delle condizioni in Gestione cespiti è: Innanzitutto si impostano i modelli necessari per la valutazione delle condizioni.</span><span class="sxs-lookup"><span data-stu-id="c9102-114">The sequence for setting up and using condition assessment in Asset Management is: First you set up the required condition assessment templates.</span></span> <span data-ttu-id="c9102-115">A questo punto, associare i modelli con i tipi di cespite nel modulo **Tipi di cespite**.</span><span class="sxs-lookup"><span data-stu-id="c9102-115">Next, you associate templates with asset types in the **Asset types** form.</span></span> <span data-ttu-id="c9102-116">Infine, è possibile creare registrazioni di valutazione delle condizioni di un cespite nel modulo **Cespite**.</span><span class="sxs-lookup"><span data-stu-id="c9102-116">Finally, you can create condition assessment registrations on an asset in the **Asset** form.</span></span>

## <a name="create-a-condition-assessment-template"></a><span data-ttu-id="c9102-117">Creare un modello di valutazione delle condizioni</span><span class="sxs-lookup"><span data-stu-id="c9102-117">Create a condition assessment template</span></span>

1. <span data-ttu-id="c9102-118">Selezionare **Gestione cespiti** > **Impostazione** > **Tipi di cespite** > **Valutazione delle condizioni**.</span><span class="sxs-lookup"><span data-stu-id="c9102-118">Select **Asset management** > **Setup** > **Asset types** > **Condition assessment**.</span></span>
2. <span data-ttu-id="c9102-119">Selezionare **Nuovo** per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="c9102-119">Select **New** to create a new template.</span></span>
3. <span data-ttu-id="c9102-120">Nel campo **Modello**, digitare un ID per il modello.</span><span class="sxs-lookup"><span data-stu-id="c9102-120">Insert and ID for the template in the **Template** field.</span></span>
4. <span data-ttu-id="c9102-121">Nel campo **Nome** immettere un nome per il modello.</span><span class="sxs-lookup"><span data-stu-id="c9102-121">Insert a name for the template in the **Name** field.</span></span>
5. <span data-ttu-id="c9102-122">Nella Scheda dettaglio **Righe di valutazione condizione** aggiungere le righe necessarie per la valutazione delle condizioni, inclusa la selezione del tipo di condizione e dell'unità di misura appropriati.</span><span class="sxs-lookup"><span data-stu-id="c9102-122">On the **Condition assessment lines** FastFab, add the lines required for the condition assessment, including selection of the appropriate condition type and measurement unit.</span></span>
6. <span data-ttu-id="c9102-123">Nella Scheda dettaglio **Tipi di cespite**, aggiungere i tipi di cespite che devono utilizzare il modello di valutazione delle condizioni.</span><span class="sxs-lookup"><span data-stu-id="c9102-123">On the **Asset types** FastTab, add the asset types that should use the condition assessment template.</span></span>
7. <span data-ttu-id="c9102-124">Nei campi **Righe** e **Tipi di cespite** nel gruppo **Dettagli** nella parte superiore della schermata, vedrete il numero di righe di valutazione e i tipi di cespit correlati al modello di valutazione delle condizioni selezionato.</span><span class="sxs-lookup"><span data-stu-id="c9102-124">In the **Lines** and **Asset types** fields in the **Details** group at the top of the screen, you will see the number of assessment lines and asset types related to the selected condition assessment template.</span></span>


## <a name="create-condition-assessment-registration-on-an-asset"></a><span data-ttu-id="c9102-125">Creare una registrazione di valutazione delle condizioni per un cespite</span><span class="sxs-lookup"><span data-stu-id="c9102-125">Create condition assessment registration on an asset</span></span>

1. <span data-ttu-id="c9102-126">Selezionare **Gestione cespiti** > **Comune** > **Cespiti** > **Tutti i cespiti**.</span><span class="sxs-lookup"><span data-stu-id="c9102-126">Select **Asset management** > **Common** > **Assets** > **All Assets**.</span></span>
2. <span data-ttu-id="c9102-127">Nell'elenco, selezionare il cespite per cui si desidera creare una valutazione delle condizioni.</span><span class="sxs-lookup"><span data-stu-id="c9102-127">In the list, select the asset for which you want to create a condition assessment registration.</span></span>
3. <span data-ttu-id="c9102-128">Nella scheda **Generale** fare clic su **Valutazione delle condizioni**.</span><span class="sxs-lookup"><span data-stu-id="c9102-128">On the **General** tab, click **Condition assessment**.</span></span>
4. <span data-ttu-id="c9102-129">Fare clic su **Nuovo** per creare una nuova registrazione.</span><span class="sxs-lookup"><span data-stu-id="c9102-129">Click **New** to make a new registration.</span></span>
5. <span data-ttu-id="c9102-130">Selezionare la data per la valutazione delle condizioni nel campo **Data**.</span><span class="sxs-lookup"><span data-stu-id="c9102-130">Select the date for the condition assessment in the **Date** field.</span></span>
6. <span data-ttu-id="c9102-131">Selezionare il nome del lavoratore che ha eseguito la registrazione di valutazione prezzo nel campo **Lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="c9102-131">Select the name of the worker who carried out the assessment registration in the **Worker** field.</span></span>
7. <span data-ttu-id="c9102-132">Nel campo **Righe**, vengono visualizzati il numero delle righe di valutazione configurate per la valutazione delle condizioni.</span><span class="sxs-lookup"><span data-stu-id="c9102-132">In the **Lines** field, you see the number of assessment lines set up on the condition assessment.</span></span>
8. <span data-ttu-id="c9102-133">Selezionare un modello per la valutazione delle condizioni nel campo **Modello**.</span><span class="sxs-lookup"><span data-stu-id="c9102-133">Select a template for the condition assessment in the **Template** field.</span></span> <span data-ttu-id="c9102-134">Il nome del modello viene automaticamente inserito nel campo **Nome** e le righe di registrazione correlate vengono immesse nella Scheda dettaglio **Righe di valutazione condizione**.</span><span class="sxs-lookup"><span data-stu-id="c9102-134">The name of the template is automatically inserted in the **Name** field, and the related registration lines are inserted on the **Condition assessment lines** FastTab.</span></span>
9. <span data-ttu-id="c9102-135">È possibile inserire note relative alla valutazione delle condizioni selezionata nella Scheda dettaglio **Note**.</span><span class="sxs-lookup"><span data-stu-id="c9102-135">You can insert notes relating to the selected condition assessment on the **Notes** FastTab.</span></span>
10. <span data-ttu-id="c9102-136">Per ciascuna riga di valutazione delle condizioni, inserire i dati di misura nel campo **Valore**.</span><span class="sxs-lookup"><span data-stu-id="c9102-136">For each condition assessment line, insert measurement data in the **Value** field.</span></span>
11. <span data-ttu-id="c9102-137">È possibile inserire un commento riguardante la riga registrazione selezionata nella Scheda dettaglio **Righe di valutazione condizione** > campo **Commenti**.</span><span class="sxs-lookup"><span data-stu-id="c9102-137">You can insert a comment relating to the selected registration line on the **Condition assessment lines** FastTab > **Comments** field.</span></span> <span data-ttu-id="c9102-138">Se si aggiunge un commento su una riga, la casella di controllo **Commento** verrà selezionata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c9102-138">If you add a comment on a line, the **Comment** check box is automatically selected.</span></span>

<span data-ttu-id="c9102-139">Dopo avere effettuato una registrazione di valutazione delle condizioni di un cespite, è possibile stampare un report della valutazione delle condizioni.</span><span class="sxs-lookup"><span data-stu-id="c9102-139">After you have made a condition assessment registration on an asset, you can print a condition assessment report.</span></span>

>[!NOTE]
><span data-ttu-id="c9102-140">È anche possibile registrare la valutazione delle condizioni in un ordine di lavoro (**Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** > **Valutazione delle condizioni** ).</span><span class="sxs-lookup"><span data-stu-id="c9102-140">You can also register condition assessment on a work order (**Asset management** > **Common** > **Work orders** > **All Work orders** > **Condition assessment** button.)</span></span>
