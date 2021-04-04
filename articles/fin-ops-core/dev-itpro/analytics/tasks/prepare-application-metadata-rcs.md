---
title: Preparare i metadati dell'applicazione da utilizzare in RCS
description: In questo argomento viene descritto come creare una nuova configurazione di creazione report che contiene i metadati dell'applicazione.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9609da50482f39bafe65d3a7b655e5047c74bdba
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560119"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a><span data-ttu-id="58c2d-103">Preparare i metadati dell'applicazione da utilizzare in RCS</span><span class="sxs-lookup"><span data-stu-id="58c2d-103">Prepare application metadata to be used in RCS</span></span>
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="58c2d-104">I passaggi seguenti illustrano come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) che contiene i metadati dell'applicazione per la progettazione di configurazioni del mapping di modello ER in Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="58c2d-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains application metadata for designing ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="58c2d-105">Questa configurazione verrà utilizzata per la progettazione di una configurazione del mapping di modello ER di esempio per accedere alle transazioni del commercio estero.</span><span class="sxs-lookup"><span data-stu-id="58c2d-105">This configuration will be used for designing a sample ER model mapping configuration to access foreign trade transactions.</span></span> <span data-ttu-id="58c2d-106">In questo esempio si creerà una configurazione per la società di esempio Litware, Inc. Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="58c2d-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company.</span></span> <span data-ttu-id="58c2d-107">Per completare questi passaggi, è necessario dapprima completare i passaggi nell'argomento [Creare provider di configurazione e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="58c2d-107">To complete these steps, you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="58c2d-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="58c2d-108">Prerequisites</span></span>
1.    <span data-ttu-id="58c2d-109">Andare a **Amministrazione organizzazione** > **Aree di lavoro** > **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-109">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2.    <span data-ttu-id="58c2d-110">Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="58c2d-111">Se questo provider di configurazione non è visualizzato, completare i passaggi nella procedura [Creare provider di configurazioni e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="58c2d-111">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3.    <span data-ttu-id="58c2d-112">Fare clic su **Configurazioni dei metadati**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-112">Click **Metadata configurations**.</span></span> 
4.    <span data-ttu-id="58c2d-113">Supponiamo che RCS venga utilizzato per progettare una soluzione ER per un'applicazione Finance and Operations che genererà documenti elettronici contenenti informazioni del dominio aziendale per il commercio estero.</span><span class="sxs-lookup"><span data-stu-id="58c2d-113">Assume that RCS will be used to design an ER solution for a Finance and Operation application that will generate electronic documents that contain information from foreign trade business domain.</span></span> <span data-ttu-id="58c2d-114">Per specificare il mapping tra il modello di dati ER e le origini dei dati necessari, in RCS è necessario accedere ai metadati dell'applicazione di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="58c2d-114">To specify the mapping between ER data model and sources of required data, in RCS we need to have access to metadata of the Finance and Operation application.</span></span> <span data-ttu-id="58c2d-115">Di conseguenza, nell'ambito della progettazione della soluzione ER configuriamo una nuova configurazione dei metadati ER contenente tutti i metadati attualmente necessari per generare report ER per il dominio aziendale selezionato.</span><span class="sxs-lookup"><span data-stu-id="58c2d-115">Therefore, as part of designing ER solution we configure a new ER metadata configuration containing all metadata that is currently required for generation ER reports for selected business domain.</span></span> 

## <a name="add-metadata-configuration"></a><span data-ttu-id="58c2d-116">Aggiungere una configurazione dei metadati</span><span class="sxs-lookup"><span data-stu-id="58c2d-116">Add metadata configuration</span></span> 
1.    <span data-ttu-id="58c2d-117">Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="58c2d-117">Click **Create configuration** to open the drop dialog.</span></span> 
2.    <span data-ttu-id="58c2d-118">Nel campo **Nome**, digitare "Metadati del commercio estero".</span><span class="sxs-lookup"><span data-stu-id="58c2d-118">In the **Name** field, type 'Foreign trade metadata'.</span></span> 
3.    <span data-ttu-id="58c2d-119">Fare clic su **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-119">Click **Create configuration**.</span></span> 
4.    <span data-ttu-id="58c2d-120">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-120">Click **Designer**.</span></span> 
5.    <span data-ttu-id="58c2d-121">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-121">Click **Add**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="58c2d-122">È possibile selezionare tutti i metadati per l'intera applicazione o i modelli o i moduli selezionati.</span><span class="sxs-lookup"><span data-stu-id="58c2d-122">You can select all metadata for the entire application or selected models or selected modules.</span></span> <span data-ttu-id="58c2d-123">Tenere presente che in questo caso i seguenti metadati verranno aggiunti automaticamente: tabelle di record, enumerazioni e tipi di dati estesi.</span><span class="sxs-lookup"><span data-stu-id="58c2d-123">Be aware that in this case the following metadata will be automatically added: tables of records, enumerations, and extended data types.</span></span> <span data-ttu-id="58c2d-124">Quando sono necessari tipi aggiuntivi di metadati, devono essere aggiunti manualmente.</span><span class="sxs-lookup"><span data-stu-id="58c2d-124">When additional types of metadata are needed, they must be added manually.</span></span> 
 
<span data-ttu-id="58c2d-125">Se si selezionano elementi di metadati manualmente, si hanno alcuni metadati relativi alle transazioni del commercio estero.</span><span class="sxs-lookup"><span data-stu-id="58c2d-125">We have some foreign trade transactions related metadata by selecting metadata items manually.</span></span> 
  
6.    <span data-ttu-id="58c2d-126">Fare clic su **Aggiungi origine dati**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-126">Click **Add data source**.</span></span> 
7.    <span data-ttu-id="58c2d-127">Fare clic su **Record di tabella**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-127">Click **Table records**.</span></span> 
8.    <span data-ttu-id="58c2d-128">Utilizzare il filtro rapido per filtrare il campo **Nome** in base al valore "Intrastat".</span><span class="sxs-lookup"><span data-stu-id="58c2d-128">Use the Quick Filter to filter on the **Name** field with a value of 'Intrastat'.</span></span> 
9.    <span data-ttu-id="58c2d-129">Selezionare il record di tabella **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-129">Select the **Intrastat** table record.</span></span> 
10.    <span data-ttu-id="58c2d-130">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-130">Click **OK**.</span></span>
  
<span data-ttu-id="58c2d-131">Abbiamo aggiunto informazioni sui metadati relative alla tabella di record Intrastat.</span><span class="sxs-lookup"><span data-stu-id="58c2d-131">We added metadata information about the Intrastat table of records.</span></span> 
  
11.    <span data-ttu-id="58c2d-132">Nella struttura espandere **Record di tabella Intrastat**\>**Relazioni**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-132">In the tree, expand **Table records Intrastat**\>**Relations**.</span></span> 
12.    <span data-ttu-id="58c2d-133">Nella struttura, selezionare **Record di tabella Intrastat**\>**Relazioni\IntrastatCommodity (Record di tabella EcoResCategory)**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-133">In the tree, select **Table records Intrastat**\>**Relations\IntrastatCommodity (Table records EcoResCategory)**.</span></span>     
13.    <span data-ttu-id="58c2d-134">Fare clic su **Aggiungi metadati**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-134">Click **Add metadata**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="58c2d-135">I metadati relativi alle relazioni necessarie per la tabella di record selezionata devono essere aggiunti manualmente.</span><span class="sxs-lookup"><span data-stu-id="58c2d-135">Metadata about required relations for selected table of records must be added manually.</span></span> 
  
16.    <span data-ttu-id="58c2d-136">Fare clic su **Aggiungi origine dati**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-136">Click **Add data source**.</span></span> 
17.    <span data-ttu-id="58c2d-137">Fare clic su **Enumerazione**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-137">Click **Enumeration**.</span></span> 
18.    <span data-ttu-id="58c2d-138">Utilizzare il filtro rapido per filtrare il campo **Nome** in base al valore "IntrastatDirection".</span><span class="sxs-lookup"><span data-stu-id="58c2d-138">Use the Quick Filter to filter on the **Name** field with a value of 'IntrastatDirection'.</span></span> 
19.    <span data-ttu-id="58c2d-139">Selezionare il record **Enumerazione IntrastatDirection**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-139">Select the **IntrastatDirection enumeration** record.</span></span> 
20.    <span data-ttu-id="58c2d-140">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-140">Click **OK**.</span></span> 
21.    <span data-ttu-id="58c2d-141">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-141">Click **Save**.</span></span>  
22.    <span data-ttu-id="58c2d-142">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="58c2d-142">Close the page.</span></span> 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a><span data-ttu-id="58c2d-143">Completare la versione bozza della configurazione dei metadati</span><span class="sxs-lookup"><span data-stu-id="58c2d-143">Complete the draft version of metadata configuration</span></span>
1.    <span data-ttu-id="58c2d-144">Fare clic su **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-144">Click **Change status**.</span></span> 
2.    <span data-ttu-id="58c2d-145">Fare clic su **Completa**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-145">Click **Complete**.</span></span> 
3.    <span data-ttu-id="58c2d-146">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-146">Click **OK**.</span></span> 
4.    <span data-ttu-id="58c2d-147">Selezionare la versione completata **1**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-147">Select the completed version **1**.</span></span> 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a><span data-ttu-id="58c2d-148">Esportare la versione completata della configurazione dei metadati dall'applicazione come file XML</span><span class="sxs-lookup"><span data-stu-id="58c2d-148">Export the completed version of metadata configuration from application as XML file</span></span>
1.    <span data-ttu-id="58c2d-149">Fare clic su **Scambia**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-149">Click **Exchange**.</span></span> 
2.    <span data-ttu-id="58c2d-150">Fare clic su **Esporta come file XML**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-150">Click **Export as XML file**.</span></span> 
3.    <span data-ttu-id="58c2d-151">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="58c2d-151">Click **OK**.</span></span> 
    
<span data-ttu-id="58c2d-152">La configurazione dei metadati ER creata è stata salvata come file XML che può essere importato in RCS e utilizzato come origine delle informazioni sui metadati per il dominio aziendale del commercio estero.</span><span class="sxs-lookup"><span data-stu-id="58c2d-152">The created ER metadata configuration has been saved as XML file that can be imported to RCS and used as the source of information about metadata for the foreign trade business domain.</span></span> <span data-ttu-id="58c2d-153">In base a queste informazioni, possiamo specificare il mapping tra i metadati dell'applicazione e il modello di dati ER.</span><span class="sxs-lookup"><span data-stu-id="58c2d-153">Based on this information, we can specify the mapping between application metadata and ER data model.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]