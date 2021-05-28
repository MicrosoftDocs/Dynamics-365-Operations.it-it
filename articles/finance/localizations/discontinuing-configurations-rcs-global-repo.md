---
title: Sospendere le configurazioni nel repository RCS Global
description: In questo argomento viene descritto come sospendere le configurazioni nel repository RCS Global.
author: JaneA07
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 2bd22e991de376cfd93f75158f1f29716d2559e1
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018735"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a><span data-ttu-id="4d504-103">Sospendere le configurazioni nel repository RCS Global</span><span class="sxs-lookup"><span data-stu-id="4d504-103">Discontinue configurations in the RCS Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4d504-104">In questo argomento viene descritto come sospendere le configurazioni nel repository RCS Global.</span><span class="sxs-lookup"><span data-stu-id="4d504-104">This topic describes how to discontinue configuration in the RCS Global repository.</span></span> <span data-ttu-id="4d504-105">In precedenza era possibile eliminare solo le configurazioni non più necessarie.</span><span class="sxs-lookup"><span data-stu-id="4d504-105">Previously, it was possible only to delete configurations that were no longer required.</span></span> <span data-ttu-id="4d504-106">Tuttavia ora è possibile contrassegnare una configurazione rilasciata come **Sospesa** nel repository RCS Global.</span><span class="sxs-lookup"><span data-stu-id="4d504-106">However now you can mark a released configuration as **Discontinued** in the RCS Global repository.</span></span> <span data-ttu-id="4d504-107">Con questa funzionalità, è inoltre possibile effettuare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4d504-107">With this functionality, you can also do the following:</span></span> 
 
 - <span data-ttu-id="4d504-108">Fornire notifiche anticipate quando si pianifica la sospensione di una configurazione.</span><span class="sxs-lookup"><span data-stu-id="4d504-108">Provide up front notifications when a configuration is planned to be discontinued.</span></span>
 - <span data-ttu-id="4d504-109">Includere i dettagli applicabili sulla configurazione sostitutiva.</span><span class="sxs-lookup"><span data-stu-id="4d504-109">Include applicable details about the replacement configuration.</span></span>
 - <span data-ttu-id="4d504-110">Impostare una data in **Supportata fino al** per la configurazione specifica per informare l'utente quando verrà sospesa.</span><span class="sxs-lookup"><span data-stu-id="4d504-110">Set a **Supported until** date for the specific configuration to inform the user when it will be discontinued.</span></span>

<span data-ttu-id="4d504-111">Quando si sospende una versione di configurazione, è possibile specificare le seguenti informazioni facoltative:</span><span class="sxs-lookup"><span data-stu-id="4d504-111">When you discontinue a configuration version, you can specify the following optional information:</span></span>

  - <span data-ttu-id="4d504-112">**Configurazione della sostituzione**</span><span class="sxs-lookup"><span data-stu-id="4d504-112">**Replacement configuration**</span></span>
  - <span data-ttu-id="4d504-113">**Versione della configurazione sostitutiva**</span><span class="sxs-lookup"><span data-stu-id="4d504-113">**Replacement configuration version**</span></span>
  - <span data-ttu-id="4d504-114">**Nota a testo libero**: utilizzare questo campo per fornire collegamenti o riferimenti alla documentazione</span><span class="sxs-lookup"><span data-stu-id="4d504-114">**Free text note**: Use this field to provide documentation links or references</span></span>
  - <span data-ttu-id="4d504-115">**Supportata fino al**: questo campo fornisce la data proposta fino alla quale la configurazione/versione corrente sarà supportata.</span><span class="sxs-lookup"><span data-stu-id="4d504-115">**Supported until**: This field provides the proposed date up to which the current configuration/version will be supported.</span></span> <span data-ttu-id="4d504-116">Questa data deve essere aggiornata manualmente.</span><span class="sxs-lookup"><span data-stu-id="4d504-116">This date must be updated manually.</span></span>
  
<span data-ttu-id="4d504-117">Per sospendere la configurazione, completare i seguenti passaggi.</span><span class="sxs-lookup"><span data-stu-id="4d504-117">To discontinue the configuration, complete the following steps.</span></span> 

1. <span data-ttu-id="4d504-118">Selezionare se si desidera sospendere una singola versione o tutte le versioni con le stesse impostazioni in un'unica operazione impostando **Tutte le versioni** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="4d504-118">Select whether you want to discontinue a single version or all versions with the same settings in one operation by setting **All versions** to **Yes**.</span></span> 
2. <span data-ttu-id="4d504-119">Impostare il parametro **Sospendi** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="4d504-119">Set the **Discontinue** parameter to **Yes**.</span></span>
3. <span data-ttu-id="4d504-120">Selezionare **OK** per sospendere le configurazioni.</span><span class="sxs-lookup"><span data-stu-id="4d504-120">Select **OK** to discontinue the configurations.</span></span> <span data-ttu-id="4d504-121">Il campo **Data sospensione** verrà popolato quando si salvano le modifiche.</span><span class="sxs-lookup"><span data-stu-id="4d504-121">The **Discontinued date** field will be populated when you save the changes.</span></span>

![Informazioni sulla sospensione della configurazione](media/Discontinue-details-2.png)
  
<span data-ttu-id="4d504-123">È possibile reimpostare la configurazione su **Condivisa** o modificare le informazioni sulla sospensione in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="4d504-123">You can revert configuration back to **Shared** or adjust discontinuation information at any time.</span></span> <span data-ttu-id="4d504-124">Se si condivide una configurazione, specificare la data **Supportata fino al** e tutte le altre informazioni relative alla sospensione per indicare i piani di una futura sospensione.</span><span class="sxs-lookup"><span data-stu-id="4d504-124">If you share a configuration, specify the **Supported until** date and all other information related to the discontinuation to indicate your plans for future discontinuation.</span></span>

<span data-ttu-id="4d504-125">Se si desidera condividere le informazioni su una sospensione pianificata, prima di sospendere effettivamente la configurazione, l'utente può precompilare tutti i campi relativi alla sostituzione ma lasciare il parametro **Sospendi** impostato su **No**.</span><span class="sxs-lookup"><span data-stu-id="4d504-125">If you want to share information about a planned discontinuation, prior to actually discontinuing the configuration, user is able to prefill all fields related to replacement but leave the **Discontinue** parameter set to **No**.</span></span>

> [!NOTE]
> <span data-ttu-id="4d504-126">La sospensione non limita le operazioni con le configurazioni.</span><span class="sxs-lookup"><span data-stu-id="4d504-126">Discontinuation doesn't limit operations with configurations.</span></span> <span data-ttu-id="4d504-127">È possibile continuare a importare, eseguire o derivare le configurazioni; questi campi sono informativi.</span><span class="sxs-lookup"><span data-stu-id="4d504-127">You can continue to import, run, or derive the configurations, these fields are informational.</span></span>

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a><span data-ttu-id="4d504-128">Finance supporta la visualizzazione di queste informazioni a partire dalla versione 10.0.14</span><span class="sxs-lookup"><span data-stu-id="4d504-128">Finance supports displaying this information starting in version 10.0.14</span></span>

<span data-ttu-id="4d504-129">A partire dalla versione 10.0.14, Dynamics 365 Finance supporta la visualizzazione delle informazioni sulla sospensione.</span><span class="sxs-lookup"><span data-stu-id="4d504-129">Starting in version 10.0.14, Dynamics 365 Finance supports displaying discontinuation information.</span></span> <span data-ttu-id="4d504-130">Nella pagina **Repository globale**, è possibile visualizzare informazioni aggiornate relative alla sospensione.</span><span class="sxs-lookup"><span data-stu-id="4d504-130">On the **Global repository** page, you can view up to date information related to discontinuation.</span></span> <span data-ttu-id="4d504-131">Per impostazione predefinita, le configurazioni sospese vengono filtrate.</span><span class="sxs-lookup"><span data-stu-id="4d504-131">By default, configurations that are discontinued are filtered out.</span></span>
  
<span data-ttu-id="4d504-132">La pagina **Configurazioni importate** (ERSolutionTable) mostra le configurazioni che erano già state sospese quando sono state importate.</span><span class="sxs-lookup"><span data-stu-id="4d504-132">The **Imported configurations** (ERSolutionTable) page, shows configurations that were already discontinued when there were imported.</span></span> <span data-ttu-id="4d504-133">Per queste configurazioni che erano state sospese dopo l'importazione, le informazioni sulla sospensione possono essere sincronizzate eseguendo il processo **Importare aggiornamenti delle configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="4d504-133">For those configurations that were discontinued after import, the discontinuation information can be synchronized by running the **Import configurations updates** job.</span></span>


