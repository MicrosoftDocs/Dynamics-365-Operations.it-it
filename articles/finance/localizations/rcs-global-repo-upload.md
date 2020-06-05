---
title: Creare configurazioni ER in RCS e caricarle nel repository globale
description: Questo argomento spiega come creare una configurazione di report elettronico (ER) in Microsoft Regulatory Configuration Services (RCS) e caricarla nel repository globale.
author: JaneA07
manager: AnnBe
ms.date: 05/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 0e194a8b777f984412d81e315f92ab4bb8a3b0c9
ms.sourcegitcommit: 204cec8ca2a6c4474d21dbcd408e369131a47856
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "3371253"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a><span data-ttu-id="040b7-103">Creare configurazioni ER in Regulatory Configuration Services (RCS) e caricarle nel repository globale</span><span class="sxs-lookup"><span data-stu-id="040b7-103">Create ER configurations in Regulatory Configuration Services (RCS) and upload them to the Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="040b7-104">Puoi utilizzare Microsoft Regulatory Configuration Services (RCS) per progettare configurazioni di reporting elettronico (ER) e pubblicarle in modo che possano essere utilizzate nella tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="040b7-104">You can use Microsoft Regulatory Configuration Services (RCS) to design Electronic reporting (ER) configurations and publish them so that they can be used in your organization.</span></span>

<span data-ttu-id="040b7-105">Le seguenti procedure spiegano come un utente nel ruolo di amministratore di sistema o sviluppatore di report elettronici può creare una versione derivata di una configurazione ER che è stata configurata in un'istanza RCS e quindi caricare la configurazione derivata nel repository globale.</span><span class="sxs-lookup"><span data-stu-id="040b7-105">The following procedures explain how a user in the System Administrator or Electronic Reporting Developer role can create a derived version of an ER configuration that has been configured in an RCS instance, and then upload the derived configuration to the Global repository.</span></span> 

<span data-ttu-id="040b7-106">Prima di poter completare queste procedure, devi completare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="040b7-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="040b7-107">Accesso a un'istanza RCS.</span><span class="sxs-lookup"><span data-stu-id="040b7-107">Access an RCS instance.</span></span>
- <span data-ttu-id="040b7-108">Creare fornitore di configurazioni attivo.</span><span class="sxs-lookup"><span data-stu-id="040b7-108">Create an active configuration provider.</span></span> <span data-ttu-id="040b7-109">Per ulteriori informazioni, vedi [Creare provider di configurazioni e contrassegnarli come attivi](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="040b7-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="040b7-110">Puoi inoltre assicurarti che venga fornito un ambiente RCS per la tua azienda.</span><span class="sxs-lookup"><span data-stu-id="040b7-110">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="040b7-111">In un'app Finance and Operations, vai ad **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="040b7-111">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="040b7-112">Se non è stato effettuato il provisioning di nessun ambiente RCS per la società, seleziona **Regulatory services - Configurazione** e segui le istruzioni per il provisioning di un ambiente.</span><span class="sxs-lookup"><span data-stu-id="040b7-112">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="040b7-113">Se è già stato eseguito il provisioning di un ambiente RCS per la tua azienda, utilizza l'URL della pagina per accedervi selezionando l'opzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="040b7-113">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a><span data-ttu-id="040b7-114">Crea una versione derivata di una configurazione in RCS</span><span class="sxs-lookup"><span data-stu-id="040b7-114">Create a derived version of a configuration in RCS</span></span>

1. <span data-ttu-id="040b7-115">Nell'area di lavoro **Creazione di report elettronici**, verifica di disporre di un provider di configurazione attivo per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="040b7-115">In the **Electronic reporting** workspace, verify that you have an active configuration provider for your organization.</span></span> 
2. <span data-ttu-id="040b7-116">Selezionare **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="040b7-116">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="040b7-117">Seleziona la configurazione da cui vuoi derivare una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="040b7-117">Select the configuration that you want to derive a new version from.</span></span> <span data-ttu-id="040b7-118">Puoi utilizzare il campo del filtro sopra l'albero per restringere la ricerca.</span><span class="sxs-lookup"><span data-stu-id="040b7-118">You can use the filter field above the tree to narrow your search.</span></span>
4. <span data-ttu-id="040b7-119">Seleziona **Crea configurazione** \> **Deriva da nome**.</span><span class="sxs-lookup"><span data-stu-id="040b7-119">Select **Create configuration** \> **Derive from Name**.</span></span>
5. <span data-ttu-id="040b7-120">Immetti un nome e una descrizione, quindi seleziona **Crea configurazione** per creare una nuova versione derivata.</span><span class="sxs-lookup"><span data-stu-id="040b7-120">Enter a name and description, and then select **Create configuration** to create a new derived version.</span></span>
6. <span data-ttu-id="040b7-121">Seleziona la configurazione appena derivata, aggiungi una descrizione della versione, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="040b7-121">Select the newly derived configuration, add a description of the version, and then select **OK**.</span></span> <span data-ttu-id="040b7-122">Lo stato della configurazione viene modificato in **Completato**.</span><span class="sxs-lookup"><span data-stu-id="040b7-122">The status of the configuration to is changed to **Completed**.</span></span>

![Nuova versione di configurazione in RCS](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_CompleteConfig.JPG)

> [!NOTE]
> <span data-ttu-id="040b7-124">Quando lo stato della configurazione viene modificato, è possibile che venga visualizzato un messaggio di errore di convalida correlato alle applicazioni connesse.</span><span class="sxs-lookup"><span data-stu-id="040b7-124">When the configuration status is changed, you might receive a validation error message that is related to the connected applications.</span></span> <span data-ttu-id="040b7-125">Per disattivare la convalida, nel riquadro azioni della scheda **Configurazioni**, seleziona **Parametri utente**, quindi imposta l'opzione **Ignora convalida alla riassegnazione e alla modifica dello stato della configurazione** su **Sì**</span><span class="sxs-lookup"><span data-stu-id="040b7-125">To turn off the validation, on the Action Pane on the **Configurations** tab, select **User parameters**, and then set the **Skip validation at configuration's status change and rebase** option to **Yes**</span></span> 

## <a name="upload-a-configuration-to-the-global-repository"></a><span data-ttu-id="040b7-126">Carica una configurazione nel repository globale</span><span class="sxs-lookup"><span data-stu-id="040b7-126">Upload a configuration to the Global repository</span></span>

<span data-ttu-id="040b7-127">Per condividere una configurazione nuova o derivata con la tua organizzazione, puoi caricarla nel repository globale.</span><span class="sxs-lookup"><span data-stu-id="040b7-127">To share a new or derived configuration with your organization, you can upload it to the Global repository.</span></span>

1. <span data-ttu-id="040b7-128">Seleziona la versione completa della configurazione, quindi **Carica nel repository**.</span><span class="sxs-lookup"><span data-stu-id="040b7-128">Select the completed version of the configuration, and then select **Upload into repository**.</span></span>
2. <span data-ttu-id="040b7-129">Seleziona l'opzione **Globale (Microsoft)**, quindi **Carica**.</span><span class="sxs-lookup"><span data-stu-id="040b7-129">Select the **Global (Microsoft)** option, and then select **Upload**.</span></span>

    ![Carica nelle opzioni del repository](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_Upload_to_GlobalRepo_options.JPG)

3. <span data-ttu-id="040b7-131">Nella finestra del messaggio di conferma, seleziona **Sì**.</span><span class="sxs-lookup"><span data-stu-id="040b7-131">In the confirmation message box, select **Yes**.</span></span> 
4. <span data-ttu-id="040b7-132">Aggiorna la descrizione della versione come richiesto, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="040b7-132">Update the description of the version as required, and then select **OK**.</span></span> 

<span data-ttu-id="040b7-133">Lo stato della configurazione viene aggiornato su **Condividi**e la configurazione viene caricata nel repository globale.</span><span class="sxs-lookup"><span data-stu-id="040b7-133">The status of the configuration is updated to **Share**, and the configuration is uploaded to the Global repository.</span></span> <span data-ttu-id="040b7-134">Da qui, puoi utilizzarla nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="040b7-134">From there, you can work with it in the following ways:</span></span>

- <span data-ttu-id="040b7-135">Importala nell'istanza di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="040b7-135">Import it into your Dynamics 365 instance.</span></span> <span data-ttu-id="040b7-136">Per ulteriori informazioni, vedi [(ER) Importare le configurazioni da RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="040b7-136">For more information, see [(ER) Import configurations from RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span></span>
- <span data-ttu-id="040b7-137">Condividila con una terza parte o un'organizzazione esterna, vedi [Configurazioni RCS per la condivisione di report elettronici (ER) con organizzazioni esterne](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/rcs-global-share-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="040b7-137">Share it with a third party or an external organization, see [RCS Share Electronic reporting (ER) configurations with external organizations](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/rcs-global-share-configuration.md)</span></span>

![Versione di configurazione Contoso Intrastat derivata nel repository globale](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_Config_upload_GlobalRepo.JPG)
