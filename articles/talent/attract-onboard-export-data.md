---
title: Esportare dati da Attract e Onboard
description: Esportare dati da Dynamics 365 Talent - Attract e Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Talent October 2019 update
ms.openlocfilehash: eb97a16c15476c2f34ec581a32a677fa6fee8739
ms.sourcegitcommit: acdd93637385246f9c5c652cccdf2cbfb263cc33
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2020
ms.locfileid: "2975936"
---
# <a name="export-data-from-attract-and-onboard"></a><span data-ttu-id="f4291-103">Esportare dati da Attract e Onboard</span><span class="sxs-lookup"><span data-stu-id="f4291-103">Export data from Attract and Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f4291-104">Come annunciato in [Ritiro delle app Dynamics 365 Talent: Attract e Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), Dynamics 365 Talent: Attract e Dynamics 365 Talent: Onboard verranno ritirate il 1° febbraio 2022.</span><span class="sxs-lookup"><span data-stu-id="f4291-104">As announced in [Retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard Apps](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), we're retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard on February 1, 2022.</span></span> <span data-ttu-id="f4291-105">Per facilitare la migrazione verso un altro prodotto, entrambe le app offrono ora funzionalità di esportazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="f4291-105">To help with your migration to another product, both apps now provide data export capabilities.</span></span>

## <a name="export-data-from-attract"></a><span data-ttu-id="f4291-106">Esportare dati da Attract</span><span class="sxs-lookup"><span data-stu-id="f4291-106">Export data from Attract</span></span>

<span data-ttu-id="f4291-107">È possibile esportare i propri dati senza limitare l'accesso all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="f4291-107">You can export your data without restricting access to your environment.</span></span> <span data-ttu-id="f4291-108">È possibile che si voglia eseguire questa operazione per scopo di test o per comprendere la nostra struttura dati.</span><span class="sxs-lookup"><span data-stu-id="f4291-108">You might want to do this for testing purposes or to understand our data structure.</span></span> <span data-ttu-id="f4291-109">Quando si è pronti per migrare, limitare l'accesso all'ambiente Attract usando le istruzioni dopo questa procedura.</span><span class="sxs-lookup"><span data-stu-id="f4291-109">When you're ready to migrate, restrict access to your Attract environment using the instructions after this procedure.</span></span> <span data-ttu-id="f4291-110">Assicurarsi di esportare di nuovo i propri dati.</span><span class="sxs-lookup"><span data-stu-id="f4291-110">Be sure to export your data again.</span></span> 

1. <span data-ttu-id="f4291-111">Accedere a [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span><span class="sxs-lookup"><span data-stu-id="f4291-111">Go to [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span></span>

2. <span data-ttu-id="f4291-112">Sotto **Esportazione dati**, selezionare **Richiedi un'esportazione di dati**.</span><span class="sxs-lookup"><span data-stu-id="f4291-112">Under **Data export**, select **Request a data export**.</span></span>

   ![[<span data-ttu-id="f4291-113">Richiedere un'esportazione di dati da Attract</span><span class="sxs-lookup"><span data-stu-id="f4291-113">Request a data export from Attract</span></span>](./media/attract-onboard-export-data-attract-request.png)](./media/attract-onboard-export-data-attract-request.png)

3. <span data-ttu-id="f4291-114">Quando viene visualizzata la finestra di messaggio **Elaborazione della richiesta in corso**, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4291-114">When the **Your request is being processed** message box appears, select **OK**.</span></span> <span data-ttu-id="f4291-115">L'esportazione di dati può richiedere fino a 20 minuti, a seconda delle dimensioni dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="f4291-115">The data export can take up to 20 minutes, depending on the size of your export.</span></span>

4. <span data-ttu-id="f4291-116">Al termine dell'esportazione, selezionare il pulsante **Scarica**.</span><span class="sxs-lookup"><span data-stu-id="f4291-116">When your export completes, select the **Download** button next to it.</span></span> 

   >[!NOTE]
   ><span data-ttu-id="f4291-117">Tutte le esportazioni di dati sono disponibili per sette giorni, dopodiché il collegamento **Scarica** scade.</span><span class="sxs-lookup"><span data-stu-id="f4291-117">All data exports are available for seven days, at which point the **Download** link expires.</span></span></br>
   
<span data-ttu-id="f4291-118">Il download contiene un file zip con i dati di Attract, incluse le seguenti cartelle:</span><span class="sxs-lookup"><span data-stu-id="f4291-118">The download contains a .zip file with your Attract data, including the following folders:</span></span>

| <span data-ttu-id="f4291-119">Nome cartella</span><span class="sxs-lookup"><span data-stu-id="f4291-119">Folder name</span></span> | <span data-ttu-id="f4291-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f4291-120">Description</span></span> |
| --- | --- |
| <span data-ttu-id="f4291-121">Impostazioni di amministrazione</span><span class="sxs-lookup"><span data-stu-id="f4291-121">Admin settings</span></span> | <span data-ttu-id="f4291-122">Le configurazioni dell'interfaccia di amministrazione di Attract.</span><span class="sxs-lookup"><span data-stu-id="f4291-122">Attract admin center configurations.</span></span> |
| <span data-ttu-id="f4291-123">Candidati</span><span class="sxs-lookup"><span data-stu-id="f4291-123">Candidates</span></span> | <span data-ttu-id="f4291-124">Tutti i candidati aggiunti a posti di lavoro o pool di talenti.</span><span class="sxs-lookup"><span data-stu-id="f4291-124">All candidates that were added to jobs or talent pools.</span></span> |
| <span data-ttu-id="f4291-125">Modelli di messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="f4291-125">Email templates</span></span> | <span data-ttu-id="f4291-126">Tutti i modelli di posta elettronica configurati per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="f4291-126">All email templates that were configured for the environment.</span></span> |
| <span data-ttu-id="f4291-127">Modelli di pacchetti di offerte di lavoro</span><span class="sxs-lookup"><span data-stu-id="f4291-127">Job offer package templates</span></span> | <span data-ttu-id="f4291-128">Tutti i modelli di pacchetti di offerte di lavoro creati, oltre alle relative configurazioni associate.</span><span class="sxs-lookup"><span data-stu-id="f4291-128">All job offer package templates that were created, plus their associated configurations.</span></span> |
| <span data-ttu-id="f4291-129">Set di regole per offerte di lavoro</span><span class="sxs-lookup"><span data-stu-id="f4291-129">Job offer rule sets</span></span> |  <span data-ttu-id="f4291-130">Tutti i file di set di regole caricati per la gestione delle offerte.</span><span class="sxs-lookup"><span data-stu-id="f4291-130">All rule set files that were uploaded for offer management.</span></span> |
| <span data-ttu-id="f4291-131">Modelli di offerte di lavoro</span><span class="sxs-lookup"><span data-stu-id="f4291-131">Job offer templates</span></span> | <span data-ttu-id="f4291-132">Tutti i modelli di documenti di offerte di lavoro creati per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="f4291-132">All job offer document templates created for the environment.</span></span> |
| <span data-ttu-id="f4291-133">Posizioni aperta</span><span class="sxs-lookup"><span data-stu-id="f4291-133">Job openings</span></span> | <span data-ttu-id="f4291-134">Tutte le posizioni create.</span><span class="sxs-lookup"><span data-stu-id="f4291-134">All created jobs.</span></span> <span data-ttu-id="f4291-135">Le posizioni eliminate non vengono esportate.</span><span class="sxs-lookup"><span data-stu-id="f4291-135">Deleted jobs aren't exported.</span></span> <span data-ttu-id="f4291-136">Le sottocartelle contengono domande di lavoro dei candidati, con sottocartelle per gli allegati delle domande di lavoro e pacchetti di offerte, dove applicabile.</span><span class="sxs-lookup"><span data-stu-id="f4291-136">The sub-folders contain candidate applications, with sub-folders for candidate application attachments and offer packages, where applicable.</span></span> |
| <span data-ttu-id="f4291-137">Modelli di posizioni lavorative</span><span class="sxs-lookup"><span data-stu-id="f4291-137">Job opening templates</span></span> | <span data-ttu-id="f4291-138">Modelli di elaborazione delle posizioni lavorative configurati per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="f4291-138">Job process templates that were configured in the environment.</span></span> |
| <span data-ttu-id="f4291-139">Pool di talenti</span><span class="sxs-lookup"><span data-stu-id="f4291-139">Talent pools</span></span> | <span data-ttu-id="f4291-140">Tutti i gruppi di talenti creati, gli elenchi dei relativi contributori e gli elenchi dei candidati per i gruppi di talenti.</span><span class="sxs-lookup"><span data-stu-id="f4291-140">All created talent pools, their contributors lists, and the candidates lists for the talent pools.</span></span> |
| <span data-ttu-id="f4291-141">Lavoratori</span><span class="sxs-lookup"><span data-stu-id="f4291-141">Workers</span></span> | <span data-ttu-id="f4291-142">Elenco di tutti i lavoratori presenti nell'ambiente, oltre ai loro ruoli.</span><span class="sxs-lookup"><span data-stu-id="f4291-142">List of all the workers who are present in the environment, plus their roles.</span></span> |
| <span data-ttu-id="f4291-143">(cartella principale)</span><span class="sxs-lookup"><span data-stu-id="f4291-143">(root folder)</span></span> | <span data-ttu-id="f4291-144">Un file di schema JSON che descrive i campi della struttura dei dati.</span><span class="sxs-lookup"><span data-stu-id="f4291-144">A JSON schema file that describes the data structure fields.</span></span> |

### <a name="restrict-access-to-attract"></a><span data-ttu-id="f4291-145">Limitare l'accesso a Attract</span><span class="sxs-lookup"><span data-stu-id="f4291-145">Restrict access to Attract</span></span>

<span data-ttu-id="f4291-146">Quando si è pronti per migrare, impedire ai non amministratori di accedere all'ambiente Attract e di esportare i dati.</span><span class="sxs-lookup"><span data-stu-id="f4291-146">When you're ready to migrate, restrict non-admins from accessing your Attract environment and export your data.</span></span>

>[!IMPORTANT]
><span data-ttu-id="f4291-147">La limitazione dell'accesso all'ambiente Attract è permanente e non può essere annullata.</span><span class="sxs-lookup"><span data-stu-id="f4291-147">Restricting access to your Attract environment is permanent and can't be undone.</span></span> <span data-ttu-id="f4291-148">Se si desidera che gli utenti non amministratori continuino ad accedere all'ambiente, saltare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="f4291-148">If you want non-admin users to continue accessing your environment, skip this step.</span></span>

1. <span data-ttu-id="f4291-149">Accedere a [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span><span class="sxs-lookup"><span data-stu-id="f4291-149">Go to [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span></span>

2. <span data-ttu-id="f4291-150">Per impedire ai non amministratori di accedere all'ambiente Attract, in **Limita accesso a questa app**, selezionare **Limita l'accesso ora**.</span><span class="sxs-lookup"><span data-stu-id="f4291-150">To restrict non-admins from accessing your Attract environment, under **Restrict access to this app**, select **Restrict access now**.</span></span> <span data-ttu-id="f4291-151">La limitazione dell'accesso inoltre annulla le posizioni lavorative attive che sono state pubblicate.</span><span class="sxs-lookup"><span data-stu-id="f4291-151">Restricting access also unposts any active jobs that have been posted.</span></span>

   ![[<span data-ttu-id="f4291-152">Impedire l'accesso a Attract ai non amministratori</span><span class="sxs-lookup"><span data-stu-id="f4291-152">Restrict non-admin access to Attract</span></span>](./media/attract-onboard-export-data-attract-restrict-access.png)](./media/attract-onboard-export-data-attract-restrict-access.png)

3. <span data-ttu-id="f4291-153">Quando viene visualizzato l'avvertimento **Questa è una modifica permanente**, selezionare **Limita accesso** per limitare in modo permanente l'accesso degli utenti non amministratori da questo ambiente.</span><span class="sxs-lookup"><span data-stu-id="f4291-153">When you see the warning **This is a permanent change**, select **Restrict access** to permanently restrict non-admin users from this environment.</span></span> <span data-ttu-id="f4291-154">Se non si è pronti per completare questo passaggio, selezionare **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="f4291-154">If you're not ready to complete this step, select **Cancel**.</span></span>

   ![[<span data-ttu-id="f4291-155">Avviso che informa che la limitazione dell'accesso è una modifica permanente</span><span class="sxs-lookup"><span data-stu-id="f4291-155">Warning that restricting access is a permanent change</span></span>](./media/attract-onboard-export-data-attract-warning.png)](./media/attract-onboard-export-data-attract-warning.png)

   >[!NOTE]
   ><span data-ttu-id="f4291-156">Gli amministratori possono continuare ad accedere alle pagine di esportazione dei dati e dei report personali dopo la limitazione dell'accesso all'ambiente Attract.</span><span class="sxs-lookup"><span data-stu-id="f4291-156">Admins can continue to access the data export and person report pages after you restrict access to the Attract environment.</span></span>

## <a name="export-data-from-onboard"></a><span data-ttu-id="f4291-157">Esportare dati da Onboard</span><span class="sxs-lookup"><span data-stu-id="f4291-157">Export data from Onboard</span></span>

<span data-ttu-id="f4291-158">Quando si è pronti, è possibile scaricare modelli, guide e dati sui candidati da Onboard.</span><span class="sxs-lookup"><span data-stu-id="f4291-158">When you're ready, you can download templates, guides, and candidate data from Onboard.</span></span>

1. <span data-ttu-id="f4291-159">Accedere a [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).</span><span class="sxs-lookup"><span data-stu-id="f4291-159">Go to [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).</span></span>

2. <span data-ttu-id="f4291-160">Sotto **Esportazione dati**, selezionare **Richiedi un'esportazione di dati**.</span><span class="sxs-lookup"><span data-stu-id="f4291-160">Under **Data export**, select **Request a data export**.</span></span> 

   ![[<span data-ttu-id="f4291-161">Richiedere un'esportazione di dati da Onboard</span><span class="sxs-lookup"><span data-stu-id="f4291-161">Request a data export from Onboard</span></span>](./media/attract-onboard-export-data-onboard-request.png)](./media/attract-onboard-export-data-onboard-request.png)

3. <span data-ttu-id="f4291-162">Quando viene visualizzata la finestra di messaggio **Elaborazione della richiesta in corso**, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4291-162">When the **Your request is being processed** message box appears, select **OK**.</span></span> <span data-ttu-id="f4291-163">L'esportazione di dati può richiedere fino a 20 minuti, a seconda delle dimensioni dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="f4291-163">The data export can take up to 20 minutes, depending on the size of your export.</span></span>

4. <span data-ttu-id="f4291-164">Al termine dell'esportazione, selezionare il pulsante **Scarica**.</span><span class="sxs-lookup"><span data-stu-id="f4291-164">When your export completes, select the **Download** button next to it.</span></span> 

   ![[<span data-ttu-id="f4291-165">Scaricare un esportazione di dati da Onboard</span><span class="sxs-lookup"><span data-stu-id="f4291-165">Download data export from Onboard</span></span>](./media/attract-onboard-export-data-onboard-download.png)](./media/attract-onboard-export-data-onboard-download.png)

   >[!NOTE]
   ><span data-ttu-id="f4291-166">L'esportazione di dati è disponibile per sette giorni.</span><span class="sxs-lookup"><span data-stu-id="f4291-166">Your data export is available for seven days.</span></span> <span data-ttu-id="f4291-167">Dopo sette giorni, il collegamento **Scarica** scade ed è necessario richiedere una nuova esportazione per scaricare di nuovo i dati.</span><span class="sxs-lookup"><span data-stu-id="f4291-167">After seven days, the **Download** link expires, and you must request a new export if you need to download your data again.</span></span> <span data-ttu-id="f4291-168">Quando si avvia una nuova esportazione di dati, tutti i download esistenti scadranno al completamento della nuova esportazione.</span><span class="sxs-lookup"><span data-stu-id="f4291-168">When you start a new data export, any existing downloads will expire after the new export succeeds.</span></span>

<span data-ttu-id="f4291-169">Il download è un file zip che contiene:</span><span class="sxs-lookup"><span data-stu-id="f4291-169">The download is a .zip file that contains:</span></span>

- <span data-ttu-id="f4291-170">Una cartella **Modelli** che contiene i modelli di Onboard nel formato documento di Word.</span><span class="sxs-lookup"><span data-stu-id="f4291-170">A **Templates** folder that contains your Onboard templates in Word document format.</span></span>

- <span data-ttu-id="f4291-171">Una cartella **Guide** che contiene le guide di Onboard nel formato documento di Word.</span><span class="sxs-lookup"><span data-stu-id="f4291-171">A **Guides** folder that contains your Onboard guides in Word document format.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4291-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4291-172">See also</span></span>

[<span data-ttu-id="f4291-173">Ritiro delle app Dynamics 365 Talent: Attract e Dynamics 365 Talent: Onboard</span><span class="sxs-lookup"><span data-stu-id="f4291-173">Retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard Apps</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)