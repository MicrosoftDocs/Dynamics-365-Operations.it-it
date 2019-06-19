---
title: Pubblicazione di annunci di lavoro su siti di avanzamento professionale esterni da Attract
description: In questo argomento viene descritto come utilizzare Dynamics 365 for Talent - Attract per pubblicare annunci di lavoro su siti di reclutamento esterni
author: pganapmsft
manager: AnnBe
ms.date: 05/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-03-19
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 9c27d1810a89ed7d7a7745e41c5f118dbdfe5dda
ms.sourcegitcommit: cadce85ca3004d53caf6bc49147a524c1bfd421f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2019
ms.locfileid: "1590484"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a><span data-ttu-id="523d4-103">Pubblicazione di annunci di lavoro su siti di avanzamento professionale esterni da Attract</span><span class="sxs-lookup"><span data-stu-id="523d4-103">Post jobs to external career sites from Attract</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="523d4-104">Se si desidera rendere visibili le posizioni aperte nella propria azienda al maggior numero possibile di candidati,</span><span class="sxs-lookup"><span data-stu-id="523d4-104">You want to get your open positions in front of as many qualified candidates as possible.</span></span> <span data-ttu-id="523d4-105">esistono siti di reclutamento come Broadbean che consentono di soddisfare tale esigenza.</span><span class="sxs-lookup"><span data-stu-id="523d4-105">Recruiting sites such as Broadbean help you accomplish this goal.</span></span> <span data-ttu-id="523d4-106">Microsoft Dynamics 365 Talent: Attract consente ora di pubblicare annunci di lavoro su Broadbean e Microsoft fornisce costantemente nuove offerte in quest'area.</span><span class="sxs-lookup"><span data-stu-id="523d4-106">Microsoft Dynamics 365 Talent: Attract now lets you post jobs to Broadbean, and Microsoft is constantly providing new offerings in this area.</span></span>

## <a name="post-jobs-to-broadbean"></a><span data-ttu-id="523d4-107">Pubblicare annunci di lavoro su Broadbean</span><span class="sxs-lookup"><span data-stu-id="523d4-107">Post jobs to Broadbean</span></span>

<span data-ttu-id="523d4-108">Prima di pubblicare annunci di lavoro su Broadbean, è necessario configurare l'integrazione di tale piattaforma.</span><span class="sxs-lookup"><span data-stu-id="523d4-108">Before you can post jobs to Broadbean, you must configure the Broadbean integration.</span></span>

> [!NOTE]
> - <span data-ttu-id="523d4-109">Per pubblicare annunci di lavoro su siti esterni, è necessario disporre del [componente aggiuntivo per l'assunzione a livello globale](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="523d4-109">To post jobs to external sites, you must have the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>
> - <span data-ttu-id="523d4-110">Per pubblicare annunci di lavoro tramite Attract, è necessario disporre di una sottoscrizione Broadbend.</span><span class="sxs-lookup"><span data-stu-id="523d4-110">To post jobs to Broadbean through Attract, you must have a Broadbean subscription.</span></span>
> - <span data-ttu-id="523d4-111">Questa funzionalità è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="523d4-111">This feature is currently in preview.</span></span> <span data-ttu-id="523d4-112">Se si desidera provarlo, è necessario [attivarlo nelle impostazioni di amministrazione di Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="523d4-112">If you want to try it, you must [turn it on in the Attract admin settings](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

### <a name="configure-broadbean-integration"></a><span data-ttu-id="523d4-113">Configurare l'integrazione di Broadbean</span><span class="sxs-lookup"><span data-stu-id="523d4-113">Configure Broadbean integration</span></span>

1. <span data-ttu-id="523d4-114">Accedere a Attract come amministratore.</span><span class="sxs-lookup"><span data-stu-id="523d4-114">Sign in to Attract as an admin.</span></span>
2. <span data-ttu-id="523d4-115">Selezionare il pulsante **Impostazioni** (il simbolo dell'ingranaggio) nell'angolo superiore destro della pagina, quindi selezionare **Interfaccia di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="523d4-115">Select the **Settings** button (the gear symbol) in the upper-right corner of the page, and then select **Admin center**.</span></span>
3. <span data-ttu-id="523d4-116">Nella scheda **Impostazioni bacheca mansioni**, nella sezione **Abilita integrazione di Broadbean**, attivare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="523d4-116">On the **Job board settings** tab, in the **Enable Broadbean integration** section, turn on the integration.</span></span>
4. <span data-ttu-id="523d4-117">Contattare Broadbean e immettere le informazioni in **Nome utente, ID client, Token di crittografia**.</span><span class="sxs-lookup"><span data-stu-id="523d4-117">Contact Broadbean, and enter your information in **Username, Client ID, Encryption Token**.</span></span>

> [!WARNING]
> <span data-ttu-id="523d4-118">Le credenziali Broadbean sono sensibili e riservate.</span><span class="sxs-lookup"><span data-stu-id="523d4-118">Your Broadbean credentials are sensitive and confidential.</span></span> <span data-ttu-id="523d4-119">Di conseguenza, conservarle e condividerle in modo responsabile.</span><span class="sxs-lookup"><span data-stu-id="523d4-119">Therefore, store and share them responsibly.</span></span> <span data-ttu-id="523d4-120">Chiunque abbia un ruolo di amministratore in Attract può visualizzare tali credenziali.</span><span class="sxs-lookup"><span data-stu-id="523d4-120">Anyone who has an Administrator role in Attract can view these credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="523d4-121">Microsoft e Attract non partecipano alla creazione e alla gestione di tali dati.</span><span class="sxs-lookup"><span data-stu-id="523d4-121">Microsoft and Attract aren't involved in creating and maintaining these values.</span></span> <span data-ttu-id="523d4-122">È responsabilità dell'utente mantenerli aggiornati in Attract e collaborare con Broadbean per risolvere eventuali problemi relativi alle credenziali.</span><span class="sxs-lookup"><span data-stu-id="523d4-122">It's your responsibility to keep them up to date in Attract and to work with Broadbean to resolve any issues that involve your credentials.</span></span>

### <a name="post-a-job-to-broadbean"></a><span data-ttu-id="523d4-123">Pubblicare un annuncio di lavoro su Broadbean</span><span class="sxs-lookup"><span data-stu-id="523d4-123">Post a job to Broadbean</span></span>

<span data-ttu-id="523d4-124">Dopo l'attivazione di Broadbean, i selezionatori e gli amministratori possono pubblicarvi un annuncio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="523d4-124">After Broadbean has been turned on, recruiters and admins can post a job to it.</span></span> <span data-ttu-id="523d4-125">È necessario disporre dell'URL della domanda per l'annuncio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="523d4-125">You must have an apply URL for the job.</span></span>

1. <span data-ttu-id="523d4-126">In Attract, aprire l'annuncio di lavoro che si intende pubblicare su Broadbean.</span><span class="sxs-lookup"><span data-stu-id="523d4-126">In Attract, open the job that you want to post to Broadbean.</span></span>
2. <span data-ttu-id="523d4-127">Nella sezione **Registrazioni**, selezionare il pulsante **Pubblica ora** corrispondente a Broadbean.</span><span class="sxs-lookup"><span data-stu-id="523d4-127">In the **Postings** section, select the **Post Now** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="523d4-128">Seguire le istruzioni nella finestra di Broadbean.</span><span class="sxs-lookup"><span data-stu-id="523d4-128">Follow the instructions in the Broadbean window.</span></span>

<span data-ttu-id="523d4-129">Attract passa le seguenti informazioni a Broadbean:</span><span class="sxs-lookup"><span data-stu-id="523d4-129">Attract passes the following information to Broadbean:</span></span>

- <span data-ttu-id="523d4-130">ID richiesta</span><span class="sxs-lookup"><span data-stu-id="523d4-130">Request ID</span></span>
- <span data-ttu-id="523d4-131">Titolo posizione</span><span class="sxs-lookup"><span data-stu-id="523d4-131">Job title</span></span>
- <span data-ttu-id="523d4-132">Descrizione posizione</span><span class="sxs-lookup"><span data-stu-id="523d4-132">Job description</span></span>
- <span data-ttu-id="523d4-133">Ubicazione posizione</span><span class="sxs-lookup"><span data-stu-id="523d4-133">Job location</span></span>
- <span data-ttu-id="523d4-134">URL della domanda</span><span class="sxs-lookup"><span data-stu-id="523d4-134">Apply URL</span></span>
- <span data-ttu-id="523d4-135">Informazioni selezionatore</span><span class="sxs-lookup"><span data-stu-id="523d4-135">Recruiter information</span></span>

<span data-ttu-id="523d4-136">Dopo il completamento della pubblicazione, lo stato Broadbean nella sezione **Registrazioni** dell'annuncio di lavoro in Attract è **Pubblicato**.</span><span class="sxs-lookup"><span data-stu-id="523d4-136">After Broadbean successfully completes the posting, the **Postings** section of the job in Attract shows the Broadbean status as **Posted**.</span></span>

> [!NOTE]
> - <span data-ttu-id="523d4-137">Broadbean richiede il campo **Settore**.</span><span class="sxs-lookup"><span data-stu-id="523d4-137">Broadbean requires the **Industry** field.</span></span> <span data-ttu-id="523d4-138">Attualmente, l'impostazione predefinita di questo campo è **IT**.</span><span class="sxs-lookup"><span data-stu-id="523d4-138">Currently, this field is set to **IT** by default.</span></span> <span data-ttu-id="523d4-139">Tuttavia, è possibile impostare il settore corretto nella finestra per la pubblicazione dell'annuncio di lavoro di Broadbean.</span><span class="sxs-lookup"><span data-stu-id="523d4-139">However, you can change the value to the correct industry in the window for Broadbean job posting.</span></span>
> - <span data-ttu-id="523d4-140">La pubblicazione dell'annuncio di lavoro mediante Broadbean in tutte le bacheche mansioni selezionate può richiedere un certo tempo.</span><span class="sxs-lookup"><span data-stu-id="523d4-140">It takes some time for Broadbean to finish posting your job to all the job boards that you selected.</span></span> <span data-ttu-id="523d4-141">Di conseguenza, è possibile che lo stato dell'annuncio di lavoro in Attract venga aggiornato con leggero ritardo.</span><span class="sxs-lookup"><span data-stu-id="523d4-141">Therefore, there might be a slight delay before Attract provides a status update for the job.</span></span>

### <a name="view-a-broadbean-job-posting"></a><span data-ttu-id="523d4-142">Visualizzare la pubblicazione di un annuncio di lavoro in Broadbean</span><span class="sxs-lookup"><span data-stu-id="523d4-142">View a Broadbean job posting</span></span>

<span data-ttu-id="523d4-143">Dopo aver pubblicato un annuncio di lavoro su Broadbean, è possibile visualizzarlo da Attract.</span><span class="sxs-lookup"><span data-stu-id="523d4-143">After you post a job to Broadbean, you can view it from Attract.</span></span>

1. <span data-ttu-id="523d4-144">In Attract, aprire l'annuncio di lavoro da visualizzare in Broadbean.</span><span class="sxs-lookup"><span data-stu-id="523d4-144">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="523d4-145">Nella sezione **Registrazioni**, selezionare il pulsante con i puntini di sospensione (**...**) corrispondente a Broadbean, quindi selezionare **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="523d4-145">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>

<span data-ttu-id="523d4-146">La pubblicazione dell'annuncio di lavoro in Broadbean è visualizzata in una nuova finestra.</span><span class="sxs-lookup"><span data-stu-id="523d4-146">The Broadbean job posting appears in a new window.</span></span>

### <a name="update-a-broadbean-job-posting"></a><span data-ttu-id="523d4-147">Aggiornare la pubblicazione di un annuncio di lavoro in Broadbean</span><span class="sxs-lookup"><span data-stu-id="523d4-147">Update a Broadbean job posting</span></span>

<span data-ttu-id="523d4-148">È possibile aggiornare la pubblicazione di un annuncio di lavoro in Broadbean in due modi.</span><span class="sxs-lookup"><span data-stu-id="523d4-148">You can update a Broadbean job posting in two ways.</span></span>

1. <span data-ttu-id="523d4-149">In Attract, aprire l'annuncio di lavoro da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="523d4-149">In Attract, open the job that you want to update.</span></span>
2. <span data-ttu-id="523d4-150">Nella sezione **Registrazioni**, selezionare il pulsante **Aggiorna pubblicazione** corrispondente a Broadbean.</span><span class="sxs-lookup"><span data-stu-id="523d4-150">In the **Postings** section, select the **Update Post** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="523d4-151">Modificare la pubblicazione nella finestra di Broadbean.</span><span class="sxs-lookup"><span data-stu-id="523d4-151">Edit the posting in the Broadbean window.</span></span>

<span data-ttu-id="523d4-152">oppure</span><span class="sxs-lookup"><span data-stu-id="523d4-152">–or–</span></span>

1. <span data-ttu-id="523d4-153">In Attract, aprire l'annuncio di lavoro da visualizzare in Broadbean.</span><span class="sxs-lookup"><span data-stu-id="523d4-153">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="523d4-154">Nella sezione **Registrazioni**, selezionare il pulsante con i puntini di sospensione (**...**) corrispondente a Broadbean, quindi selezionare **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="523d4-154">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>
3. <span data-ttu-id="523d4-155">Nella finestra di Broadbean, modificare i dettagli dell'annuncio di lavoro e quindi ripubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="523d4-155">In the Broadbean window, edit the job details, and then repost the job.</span></span> <span data-ttu-id="523d4-156">I dettagli dell'annuncio di lavoro in Attract non vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="523d4-156">The job details in Attract aren't changed.</span></span>

### <a name="remove-a-broadbean-job-posting"></a><span data-ttu-id="523d4-157">Rimuovere la pubblicazione di un annuncio di lavoro da Broadbean</span><span class="sxs-lookup"><span data-stu-id="523d4-157">Remove a Broadbean job posting</span></span>

<span data-ttu-id="523d4-158">È possibile rimuovere la registrazione di un annuncio di lavoro da Broadbean.</span><span class="sxs-lookup"><span data-stu-id="523d4-158">You can remove a job posting from Broadbean as you require.</span></span>

1. <span data-ttu-id="523d4-159">In Attract, aprire l'annuncio di lavoro da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="523d4-159">In Attract, open the job that you want to remove.</span></span>
2. <span data-ttu-id="523d4-160">Nella sezione **Registrazioni**, selezionare il pulsante con i puntini di sospensione (**...**) corrispondente a Broadbean, quindi selezionare **Rimuovi pubblicazione**.</span><span class="sxs-lookup"><span data-stu-id="523d4-160">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **Remove Post**.</span></span>

<span data-ttu-id="523d4-161">Dopo che Broadbean rimuove l'annuncio di lavoro, l'elemento Broadbean in Attract presenta il pulsante **Pubblica ora**.</span><span class="sxs-lookup"><span data-stu-id="523d4-161">After Broadbean removes the job, the Broadbean item in Attract has a **Post Now** button.</span></span> <span data-ttu-id="523d4-162">La presenza di questo pulsante indica che l'annuncio di lavoro è stato rimosso e può essere pubblicato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="523d4-162">The presence of this button indicates that the job has been removed and can be posted again.</span></span>

### <a name="troubleshoot-the-broadbean-integration"></a><span data-ttu-id="523d4-163">Risolvere i problemi relativi all'integrazione di Broadbean</span><span class="sxs-lookup"><span data-stu-id="523d4-163">Troubleshoot the Broadbean integration</span></span>

<span data-ttu-id="523d4-164">In caso di problemi nel pubblicare un annuncio di lavoro su Broadbean, effettuare quanto segue.</span><span class="sxs-lookup"><span data-stu-id="523d4-164">If you're having trouble posting a job to Broadbean, try these steps.</span></span>

1. <span data-ttu-id="523d4-165">Verificare che le credenziali di Broadbean immesse in Attract siano valide e corrette.</span><span class="sxs-lookup"><span data-stu-id="523d4-165">Verify that the Broadbean credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="523d4-166">Se le credenziali sono valide e corrette, contattare il [supporto Broadbean](https://www.broadbean.com/resources/support/).</span><span class="sxs-lookup"><span data-stu-id="523d4-166">If the credentials are valid and correct, contact [Broadbean support](https://www.broadbean.com/resources/support/).</span></span>
3. <span data-ttu-id="523d4-167">Se il problema persiste, contattare il [supporto tecnico Microsoft](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="523d4-167">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>
