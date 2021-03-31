---
title: Condividi le configurazioni per la creazione di report elettronici in RCS/repository globale con organizzazioni esterne
description: Questo argomento spiega come condividere le configurazioni di report elettronici (ER) in Microsoft Regulatory Configuration Services (RCS)/repository globale direttamente con organizzazioni esterne.
author: JaneA07
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: e7ec24ddc532ee3b87108d076d5103538be903be
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218832"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a><span data-ttu-id="8f3c4-103">Condividere le configurazioni di report elettronici (ER) nel repository globale di Regulatory Configuration Services (RCS) con organizzazioni esterne</span><span class="sxs-lookup"><span data-stu-id="8f3c4-103">Share Electronic reporting (ER) configurations in Regulatory Configuration Services (RCS) Global repository with external organizations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8f3c4-104">Puoi utilizzare Microsoft Regulatory Configuration Services (RCS) per condividere configurazioni di reporting elettronico (ER) e pubblicarle su organizzazioni esterne.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-104">You can use Microsoft Regulatory Configuration Services (RCS) to share Electronic reporting (ER) configurations and then publish them to external organizations.</span></span>

<span data-ttu-id="8f3c4-105">Le seguenti procedure spiegano come un utente RCS può condividere una versione di una configurazione ER che è stata configurata in un'istanza RCS con un'organizzazione esterna.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-105">The following procedures explain how an RCS user can share a version of an ER configuration that has been configured in an RCS instance with an external organization.</span></span> <span data-ttu-id="8f3c4-106">Prima di poter completare queste procedure, devi completare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="8f3c4-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="8f3c4-107">Accesso a un'istanza RCS.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-107">Access an RCS instance.</span></span>
- <span data-ttu-id="8f3c4-108">Creare fornitore di configurazioni attivo.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-108">Create an active configuration provider.</span></span> <span data-ttu-id="8f3c4-109">Per ulteriori informazioni, vedi [Creare provider di configurazioni e contrassegnarli come attivi](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="8f3c4-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
- <span data-ttu-id="8f3c4-110">Crea e carica una nuova versione di una configurazione ER.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-110">Create and upload a new version of an ER configuration.</span></span> <span data-ttu-id="8f3c4-111">Per ulteriori informazioni, vedi [Crea e carica una nuova versione di una configurazione di creazione di report elettronici (ER)](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="8f3c4-111">For more information, see [Create and upload a new version of an Electronic reporting (ER) configuration](rcs-global-repo-upload.md).</span></span>

<span data-ttu-id="8f3c4-112">Puoi inoltre assicurarti che venga fornito un ambiente RCS per la tua azienda.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-112">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="8f3c4-113">In un'app Finance and Operations, vai ad **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-113">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="8f3c4-114">Se non è stato effettuato il provisioning di nessun ambiente RCS per la società, seleziona **Regulatory services - Configurazione** e segui le istruzioni per il provisioning di un ambiente.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-114">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="8f3c4-115">Se è già stato eseguito il provisioning di un ambiente RCS per la tua azienda, utilizza l'URL della pagina per accedervi selezionando l'opzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-115">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="verify-the-configuration-that-you-want-to-share"></a><span data-ttu-id="8f3c4-116">Verifica la configurazione che desideri condividere</span><span class="sxs-lookup"><span data-stu-id="8f3c4-116">Verify the configuration that you want to share</span></span>

<span data-ttu-id="8f3c4-117">Segui questi passaggi per verificare che la configurazione che si desidera condividere sia già stata caricata nel repository globale.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-117">Follow these steps to verify that the configuration that you want to share has already been uploaded to the Global repository.</span></span>

1. <span data-ttu-id="8f3c4-118">Nell'area di lavoro **Creazione di report elettronici**, seleziona **Repository** per il tuo provider di configurazioni.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-118">In the **Electronic reporting** workspace, select **Repositories** for your configuration provider.</span></span>

    ![Provider di configurazione](media/1_RCS_Repo_for_config_provider.JPG)

2. <span data-ttu-id="8f3c4-120">Seleziona **Repository globale** \> **Apri**.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-120">Select **Global repository** \> **Open**.</span></span>
3. <span data-ttu-id="8f3c4-121">Cerca la configurazione che desideri condividere.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-121">Search for the configuration that you want to share.</span></span> <span data-ttu-id="8f3c4-122">Puoi utilizzare il campo del filtro per restringere la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-122">You can use the filter field to narrow your search.</span></span> <span data-ttu-id="8f3c4-123">Se non riesci a trovare la configurazione nel repository globale, segui i passaggi in [Crea e carica una nuova versione di una configurazione di creazione di report elettronici (ER)](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="8f3c4-123">If you can't find the configuration in the Global repository, follow the steps in [Create and upload a new version of an Electronic reporting (ER) configuration](rcs-global-repo-upload.md).</span></span>

## <a name="share-er-configurations-with-external-organizations"></a><span data-ttu-id="8f3c4-124">Condividi le configurazioni ER con organizzazioni esterne</span><span class="sxs-lookup"><span data-stu-id="8f3c4-124">Share ER configurations with external organizations</span></span>

<span data-ttu-id="8f3c4-125">Dopo aver creato una configurazione con il tuo provider di configurazione, puoi condividerla direttamente con organizzazioni esterne utilizzando la Scheda dettaglio **Condiviso con** nella pagina **Repository di configurazioni globali**.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-125">After a configuration has been created under your configuration provider, you can share it directly with external organizations by using the **Shared with** FastTab on the **Global configuration repository** page.</span></span>

1. <span data-ttu-id="8f3c4-126">Nell'area di lavoro **Creazione di report elettronici**, seleziona **Repository** per il tuo provider di configurazioni.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-126">In the **Electronic reporting** workspace, select **Repositories** for your configuration provider.</span></span>
2. <span data-ttu-id="8f3c4-127">Seleziona **Repository globale** \> **Apri**.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-127">Select **Global repository** \> **Open**.</span></span> 
3. <span data-ttu-id="8f3c4-128">Seleziona la configurazione che desideri condividere.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-128">Select the configuration that you want to share.</span></span>
4. <span data-ttu-id="8f3c4-129">Nella Scheda dettaglio **Condiviso con**, seleziona **Organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-129">On the **Shared with** FastTab, select **Organization**.</span></span>

    ![Condiviso con Scheda dettaglio](media/1_RCS_Repo_for_Share_with_org.JPG)

5. <span data-ttu-id="8f3c4-131">Nella finestra di dialogo, immetti il nome di dominio per l'organizzazione esterna, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-131">In the dialog box, enter the domain name for the external organization, and then select **OK**.</span></span>

    ![Condividi la versione di configurazione con la finestra di dialogo dell'organizzazione esterna](media/1_RCS_Repo_for_Share_with_form.JPG)

<span data-ttu-id="8f3c4-133">La configurazione è condivisa con l'organizzazione esterna ed è disponibile per tale organizzazione nel repository globale.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-133">The configuration is shared with the external organization and is available to that organization in the Global repository.</span></span> <span data-ttu-id="8f3c4-134">Da lì, può essere importata nell'istanza di RCS dell'organizzazione o nelle sue istanze delle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8f3c4-134">From there, it can be imported into the organization's instance of RCS or into its instances of Finance and Operations apps.</span></span>

6. <span data-ttu-id="8f3c4-135">Per annullare la condivisione di una configurazione precedentemente condivisa con un'organizzazione esterna, seleziona la configurazione e fai clic su **Annulla la condivisione**, quindi seleziona **OK**</span><span class="sxs-lookup"><span data-stu-id="8f3c4-135">To unshare a configuration that has been previously shared with an external organization, select the configuration and click **Unshare**, and then select **OK**</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]