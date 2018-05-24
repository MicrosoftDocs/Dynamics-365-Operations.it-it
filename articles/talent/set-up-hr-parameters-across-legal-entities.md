---
title: Configurare i parametri HR nelle persone giuridiche
description: "È necessario impostare parametri condivisi per i record condivisi tra società, ad esempio Record posizione. In questo articolo viene spiegato come impostare i parametri delle risorse umane tra persone giuridiche."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSharedParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 1241d8da101af094ac510819376908727f9bcf07
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="set-up-hr-parameters-across-legal-entities"></a><span data-ttu-id="ece74-104">Configurare i parametri HR nelle persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="ece74-104">Set up HR parameters across legal entities</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ece74-105">È necessario impostare parametri condivisi per i record condivisi tra società, ad esempio Record posizione.</span><span class="sxs-lookup"><span data-stu-id="ece74-105">You must set up shared parameters for records that are shared across companies, such as Position records.</span></span> <span data-ttu-id="ece74-106">In questo articolo viene spiegato come impostare i parametri delle risorse umane tra persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="ece74-106">This article explains how to set up Human resources parameters across legal entities.</span></span>

<span data-ttu-id="ece74-107">Alcuni tipi di record, ad esempio i record Posizione, sono condivisi tra le società.</span><span class="sxs-lookup"><span data-stu-id="ece74-107">Some types of records, such as Position records, are shared across companies.</span></span> <span data-ttu-id="ece74-108">Per questi record, è necessario configurare dei parametri condivisi.</span><span class="sxs-lookup"><span data-stu-id="ece74-108">For these records, you must set up shared parameters.</span></span> <span data-ttu-id="ece74-109">Ad esempio, è possibile utilizzare la pagina **Parametri condivisi Risorse umane** per configurare i parametri HR in tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="ece74-109">For example, you use the **Human resources shared parameters** page to set up Human resources parameters across legal entities.</span></span> 

<span data-ttu-id="ece74-110">Nella pagina **Parametri condivisi Risorse umane** i parametri sono raggruppati in aree a seconda della relativa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ece74-110">On the **Human resources shared parameters** page, parameters are grouped into areas, based on their functionality.</span></span> 

### <a name="previously-released-functionality"></a><span data-ttu-id="ece74-111">Funzionalità già rilasciata</span><span class="sxs-lookup"><span data-stu-id="ece74-111">Previously released functionality</span></span>
<span data-ttu-id="ece74-112">Nella scheda **Identificazione** è necessario selezionare i tipi di identificazione che rappresentano i numeri di identificazione che sono elencati nella pagina.</span><span class="sxs-lookup"><span data-stu-id="ece74-112">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="ece74-113">È necessario impostare i tipi di identificazione prima di immettere le informazioni di identificazione per i lavoratori.</span><span class="sxs-lookup"><span data-stu-id="ece74-113">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="ece74-114">Le informazioni sul Social Security Number, il numero del documento di identità, il numero di identificativo straniero e il codice ID personale vengono gestite nella pagina **Tipo di identificazione**.</span><span class="sxs-lookup"><span data-stu-id="ece74-114">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="ece74-115">Per definire un nuovo tipo di identificazione o rivedere l'elenco dei tipi esistenti, fare clic su **Gestione dipendente** &gt; **scheda Collegamenti** &gt; **Impostazioni** &gt; **Tipi di identificazione**.</span><span class="sxs-lookup"><span data-stu-id="ece74-115">To define a new identification type or review the list of existing types, click **Personnel management** &gt; **Links tab** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="ece74-116">È possibile immettere un codice e una descrizione semplici.</span><span class="sxs-lookup"><span data-stu-id="ece74-116">You can enter a simple code and description.</span></span> 

### <a name="if-youre-using-dynamics-365-for-talent"></a><span data-ttu-id="ece74-117">Se si utilizza Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="ece74-117">If you're using Dynamics 365 for Talent</span></span>
<span data-ttu-id="ece74-118">Nella scheda **Identificazione** è necessario selezionare i tipi di identificazione che rappresentano i numeri di identificazione che sono elencati nella pagina.</span><span class="sxs-lookup"><span data-stu-id="ece74-118">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="ece74-119">È necessario impostare i tipi di identificazione prima di immettere le informazioni di identificazione per i lavoratori.</span><span class="sxs-lookup"><span data-stu-id="ece74-119">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="ece74-120">Le informazioni sul Social Security Number, il numero del documento di identità, il numero di identificativo straniero e il codice ID personale vengono gestite nella pagina **Tipo di identificazione**.</span><span class="sxs-lookup"><span data-stu-id="ece74-120">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="ece74-121">Per definire un nuovo tipo di identificazione o rivedere l'elenco dei tipi esistenti, fare clic su su **Risorse umane** &gt; **Impostazione** &gt; **Tipi di identificazione**.</span><span class="sxs-lookup"><span data-stu-id="ece74-121">To define a new identification type or review the list of existing types, click **Human resources** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="ece74-122">È possibile immettere un codice e una descrizione semplici.</span><span class="sxs-lookup"><span data-stu-id="ece74-122">You can enter a simple code and description.</span></span> 

<span data-ttu-id="ece74-123">Nella scheda **Sequenze numeriche** è possibile selezionare le sequenze numeriche che sono utilizzate per i seguenti record: Numero dipendente, Posizione, ID richiesta utente, Documento I-9, Candidato, Discussione, ID benefit e Azione dipendente (se questo tipo di record è attivato).</span><span class="sxs-lookup"><span data-stu-id="ece74-123">On the **Number sequences** tab, you can select the number sequences that are used for the following records: Personnel number, Position, User request ID, I-9 document, Applicant, Discussion, Benefit ID, and Personnel action (if this record type is enabled).</span></span> <span data-ttu-id="ece74-124">Per gestire i codici e i riferimenti delle sequenze numeriche, utilizzare la pagina elenco **Sequenze numeriche**.</span><span class="sxs-lookup"><span data-stu-id="ece74-124">To maintain number sequence references and codes, use the **Number sequences** list page.</span></span> <span data-ttu-id="ece74-125">Per trovare questa pagina, utilizzare la funzionalità di ricerca della pagina.</span><span class="sxs-lookup"><span data-stu-id="ece74-125">To find this page, use the page search feature.</span></span> 

<span data-ttu-id="ece74-126">Nella scheda **Posizioni** indicare se per impostazione predefinita sono disponibili nuove posizioni da assegnare:</span><span class="sxs-lookup"><span data-stu-id="ece74-126">On the **Positions** tab, indicate whether new positions are available for assignment by default:</span></span>

-   <span data-ttu-id="ece74-127">**Sempre**: è possibile assegnare lavoratori a nuove posizioni quando si creano posizioni.</span><span class="sxs-lookup"><span data-stu-id="ece74-127">**Always** – You can assign workers to new positions when positions are created.</span></span> <span data-ttu-id="ece74-128">Quando vengono create posizioni, la data e l'ora **Disponibile per l'assegnazione** nella scheda **Generale** della pagina **Posizione** vengono impostate automaticamente sulla data e ora di creazione.</span><span class="sxs-lookup"><span data-stu-id="ece74-128">When positions are created, the **Available for assignment** date and time on the **General** tab of the **Position** page are automatically set to the creation date and time.</span></span>
-   <span data-ttu-id="ece74-129">**Mai**: non è possibile assegnare lavoratori a nuove posizioni quando si creano posizioni.</span><span class="sxs-lookup"><span data-stu-id="ece74-129">**Never** – You can't assign workers to new positions when positions are created.</span></span> <span data-ttu-id="ece74-130">Se si seleziona questa opzione, è necessario aprire la pagina **Posizione** per ciascuna nuova posizione nel momento in cui diventa disponibile e, successivamente, nella scheda **Generale**, immettere la data di **Disponibile per l'assegnazione** per consentire l'assegnazione ai lavoratori.</span><span class="sxs-lookup"><span data-stu-id="ece74-130">If you select this option, you must open the **Position** page for each new position as it becomes available, and then, on the **General** tab, enter the **Available for assignment** date to enable worker assignment.</span></span>


<a name="additional-resources"></a><span data-ttu-id="ece74-131">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ece74-131">Additional resources</span></span>
--------

[<span data-ttu-id="ece74-132">Impostare parametri HR specifici della società</span><span class="sxs-lookup"><span data-stu-id="ece74-132">Set up company specific HR parameters</span></span>](set-up-company-specific-hr-parameters.md)




