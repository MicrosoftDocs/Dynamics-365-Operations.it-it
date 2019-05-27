---
title: Pubblicazione di annunci di lavoro su siti di avanzamento professionale esterni da Attract
description: In questo argomento viene descritto come utilizzare Dynamics 365 for Talent - Attract per pubblicare annunci di lavoro su siti di reclutamento esterni
author: pganapmsft
manager: AnnBe
ms.date: 03/20/2019
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
ms.openlocfilehash: eca599ad189edae29ef2de496196b08799a5e745
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518375"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a><span data-ttu-id="c80d3-103">Pubblicazione di annunci di lavoro su siti di avanzamento professionale esterni da Attract</span><span class="sxs-lookup"><span data-stu-id="c80d3-103">Post jobs to external career sites from Attract</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c80d3-104">Se si desidera rendere visibili le posizioni aperte nella propria azienda al maggior numero possibile di candidati,</span><span class="sxs-lookup"><span data-stu-id="c80d3-104">You want to get your open positions in front of as many qualified candidates as possible.</span></span> <span data-ttu-id="c80d3-105">esistono siti di reclutamento come Broadbean che consentono di soddisfare tale esigenza.</span><span class="sxs-lookup"><span data-stu-id="c80d3-105">Recruiting sites such as Broadbean help you accomplish this goal.</span></span> <span data-ttu-id="c80d3-106">Microsoft Dynamics 365 Talent: Attract consente ora di pubblicare annunci di lavoro su Broadbean e Microsoft fornisce costantemente nuove offerte in quest'area.</span><span class="sxs-lookup"><span data-stu-id="c80d3-106">Microsoft Dynamics 365 Talent: Attract now lets you post jobs to Broadbean, and Microsoft is constantly providing new offerings in this area.</span></span>

## <a name="post-jobs-to-broadbean"></a><span data-ttu-id="c80d3-107">Pubblicare annunci di lavoro su Broadbean</span><span class="sxs-lookup"><span data-stu-id="c80d3-107">Post jobs to Broadbean</span></span>

<span data-ttu-id="c80d3-108">Prima di pubblicare annunci di lavoro su Broadbean, è necessario configurare l'integrazione di tale piattaforma.</span><span class="sxs-lookup"><span data-stu-id="c80d3-108">Before you can post jobs to Broadbean, you must configure the Broadbean integration.</span></span>

> [!NOTE]
> - <span data-ttu-id="c80d3-109">Per pubblicare annunci di lavoro su siti esterni, è necessario disporre del [componente aggiuntivo per l'assunzione a livello globale](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="c80d3-109">To post jobs to external sites, you must have the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>
> - <span data-ttu-id="c80d3-110">Questa funzionalità è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="c80d3-110">This feature is currently in preview.</span></span> <span data-ttu-id="c80d3-111">Se si desidera provarlo, è necessario [attivarlo nelle impostazioni di amministrazione di Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="c80d3-111">If you want to try it, you must [turn it on in the Attract admin settings](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

### <a name="configure-broadbean-integration"></a><span data-ttu-id="c80d3-112">Configurare l'integrazione di Broadbean</span><span class="sxs-lookup"><span data-stu-id="c80d3-112">Configure Broadbean integration</span></span>

1. <span data-ttu-id="c80d3-113">Accedere a Attract come amministratore.</span><span class="sxs-lookup"><span data-stu-id="c80d3-113">Sign in to Attract as an admin.</span></span>
2. <span data-ttu-id="c80d3-114">Selezionare il pulsante **Impostazioni** (il simbolo dell'ingranaggio) nell'angolo superiore destro della pagina, quindi selezionare **Interfaccia di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="c80d3-114">Select the **Settings** button (the gear symbol) in the upper-right corner of the page, and then select **Admin center**.</span></span>
3. <span data-ttu-id="c80d3-115">Nella scheda **Impostazioni bacheca mansioni**, nella sezione **Abilita integrazione di Broadbean**, attivare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="c80d3-115">On the **Job board settings** tab, in the **Enable Broadbean integration** section, turn on the integration.</span></span>
4. <span data-ttu-id="c80d3-116">Contattare Broadbean e immettere le informazioni in **Nome utente, ID client, Token di crittografia**.</span><span class="sxs-lookup"><span data-stu-id="c80d3-116">Contact Broadbean, and enter your information in **Username, Client ID, Encryption Token**.</span></span>

> [!WARNING]
> <span data-ttu-id="c80d3-117">Le credenziali Broadbean sono sensibili e riservate.</span><span class="sxs-lookup"><span data-stu-id="c80d3-117">Your Broadbean credentials are sensitive and confidential.</span></span> <span data-ttu-id="c80d3-118">Di conseguenza, conservarle e condividerle in modo responsabile.</span><span class="sxs-lookup"><span data-stu-id="c80d3-118">Therefore, store and share them responsibly.</span></span> <span data-ttu-id="c80d3-119">Chiunque abbia un ruolo di amministratore in Attract può visualizzare tali credenziali.</span><span class="sxs-lookup"><span data-stu-id="c80d3-119">Anyone who has an Administrator role in Attract can view these credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="c80d3-120">Microsoft e Attract non partecipano alla creazione e alla gestione di tali dati.</span><span class="sxs-lookup"><span data-stu-id="c80d3-120">Microsoft and Attract aren't involved in creating and maintaining these values.</span></span> <span data-ttu-id="c80d3-121">È responsabilità dell'utente mantenerli aggiornati in Attract e collaborare con Broadbean per risolvere eventuali problemi relativi alle credenziali.</span><span class="sxs-lookup"><span data-stu-id="c80d3-121">It's your responsibility to keep them up to date in Attract and to work with Broadbean to resolve any issues that involve your credentials.</span></span>

### <a name="post-a-job-to-broadbean"></a><span data-ttu-id="c80d3-122">Pubblicare un annuncio di lavoro su Broadbean</span><span class="sxs-lookup"><span data-stu-id="c80d3-122">Post a job to Broadbean</span></span>

<span data-ttu-id="c80d3-123">Dopo l'attivazione di Broadbean, i selezionatori e gli amministratori possono pubblicarvi un annuncio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c80d3-123">After Broadbean has been turned on, recruiters and admins can post a job to it.</span></span> <span data-ttu-id="c80d3-124">È necessario disporre dell'URL della domanda per l'annuncio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c80d3-124">You must have an apply URL for the job.</span></span>

1. <span data-ttu-id="c80d3-125">In Attract, aprire l'annuncio di lavoro che si intende pubblicare su Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c80d3-125">In Attract, open the job that you want to post to Broadbean.</span></span>
2. <span data-ttu-id="c80d3-126">Nella sezione **Registrazioni**, selezionare il pulsante **Pubblica ora** corrispondente a Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c80d3-126">In the **Postings** section, select the **Post Now** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="c80d3-127">Seguire le istruzioni nella finestra di Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c80d3-127">Follow the instructions in the Broadbean window.</span></span>

<span data-ttu-id="c80d3-128">Attract passa le seguenti informazioni a Broadbean:</span><span class="sxs-lookup"><span data-stu-id="c80d3-128">Attract passes the following information to Broadbean:</span></span>

- <span data-ttu-id="c80d3-129">ID richiesta</span><span class="sxs-lookup"><span data-stu-id="c80d3-129">Request ID</span></span>
- <span data-ttu-id="c80d3-130">Titolo posizione</span><span class="sxs-lookup"><span data-stu-id="c80d3-130">Job title</span></span>
- <span data-ttu-id="c80d3-131">Descrizione posizione</span><span class="sxs-lookup"><span data-stu-id="c80d3-131">Job description</span></span>
- <span data-ttu-id="c80d3-132">Ubicazione posizione</span><span class="sxs-lookup"><span data-stu-id="c80d3-132">Job location</span></span>
- <span data-ttu-id="c80d3-133">URL della domanda</span><span class="sxs-lookup"><span data-stu-id="c80d3-133">Apply URL</span></span>
- <span data-ttu-id="c80d3-134">Informazioni selezionatore</span><span class="sxs-lookup"><span data-stu-id="c80d3-134">Recruiter information</span></span>

<span data-ttu-id="c80d3-135">Dopo il completamento della pubblicazione, lo stato Broadbean nella sezione **Registrazioni** dell'annuncio di lavoro in Attract è **Pubblicato**.</span><span class="sxs-lookup"><span data-stu-id="c80d3-135">After Broadbean successfully completes the posting, the **Postings** section of the job in Attract shows the Broadbean status as **Posted**.</span></span>

> [!NOTE]
> - <span data-ttu-id="c80d3-136">Broadbean richiede il campo **Settore**.</span><span class="sxs-lookup"><span data-stu-id="c80d3-136">Broadbean requires the **Industry** field.</span></span> <span data-ttu-id="c80d3-137">Attualmente, l'impostazione predefinita di questo campo è **IT**.</span><span class="sxs-lookup"><span data-stu-id="c80d3-137">Currently, this field is set to **IT** by default.</span></span> <span data-ttu-id="c80d3-138">Tuttavia, è possibile impostare il settore corretto nella finestra per la pubblicazione dell'annuncio di lavoro di Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c80d3-138">However, you can change the value to the correct industry in the window for Broadbean job posting.</span></span>
> - <span data-ttu-id="c80d3-139">La pubblicazione dell'annuncio di lavoro mediante Broadbean in tutte le bacheche mansioni selezionate può richiedere un certo tempo.</span><span class="sxs-lookup"><span data-stu-id="c80d3-139">It takes some time for Broadbean to finish posting your job to all the job boards that you selected.</span></span> <span data-ttu-id="c80d3-140">Di conseguenza, è possibile che lo stato dell'annuncio di lavoro in Attract venga aggiornato con leggero ritardo.</span><span class="sxs-lookup"><span data-stu-id="c80d3-140">Therefore, there might be a slight delay before Attract provides a status update for the job.</span></span>

### <a name="view-a-broadbean-job-posting"></a><span data-ttu-id="c80d3-141">Visualizzare la pubblicazione di un annuncio di lavoro in Broadbean</span><span class="sxs-lookup"><span data-stu-id="c80d3-141">View a Broadbean job posting</span></span>

<span data-ttu-id="c80d3-142">Dopo aver pubblicato un annuncio di lavoro su Broadbean, è possibile visualizzarlo da Attract.</span><span class="sxs-lookup"><span data-stu-id="c80d3-142">After you post a job to Broadbean, you can view it from Attract.</span></span>

1. <span data-ttu-id="c80d3-143">In Attract, aprire l'annuncio di lavoro da visualizzare in Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c80d3-143">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="c80d3-144">Nella sezione **Registrazioni**, selezionare il pulsante con i puntini di sospensione (**...**) corrispondente a Broadbean, quindi selezionare **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="c80d3-144">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>

<span data-ttu-id="c80d3-145">La pubblicazione dell'annuncio di lavoro in Broadbean è visualizzata in una nuova finestra.</span><span class="sxs-lookup"><span data-stu-id="c80d3-145">The Broadbean job posting appears in a new window.</span></span>

### <a name="update-a-broadbean-job-posting"></a><span data-ttu-id="c80d3-146">Aggiornare la pubblicazione di un annuncio di lavoro in Broadbean</span><span class="sxs-lookup"><span data-stu-id="c80d3-146">Update a Broadbean job posting</span></span>

<span data-ttu-id="c80d3-147">È possibile aggiornare la pubblicazione di un annuncio di lavoro in Broadbean in due modi.</span><span class="sxs-lookup"><span data-stu-id="c80d3-147">You can update a Broadbean job posting in two ways.</span></span>

1. <span data-ttu-id="c80d3-148">In Attract, aprire l'annuncio di lavoro da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="c80d3-148">In Attract, open the job that you want to update.</span></span>
2. <span data-ttu-id="c80d3-149">Nella sezione **Registrazioni**, selezionare il pulsante **Aggiorna pubblicazione** corrispondente a Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c80d3-149">In the **Postings** section, select the **Update Post** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="c80d3-150">Modificare la pubblicazione nella finestra di Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c80d3-150">Edit the posting in the Broadbean window.</span></span>

<span data-ttu-id="c80d3-151">oppure</span><span class="sxs-lookup"><span data-stu-id="c80d3-151">–or–</span></span>

1. <span data-ttu-id="c80d3-152">In Attract, aprire l'annuncio di lavoro da visualizzare in Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c80d3-152">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="c80d3-153">Nella sezione **Registrazioni**, selezionare il pulsante con i puntini di sospensione (**...**) corrispondente a Broadbean, quindi selezionare **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="c80d3-153">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>
3. <span data-ttu-id="c80d3-154">Nella finestra di Broadbean, modificare i dettagli dell'annuncio di lavoro e quindi ripubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="c80d3-154">In the Broadbean window, edit the job details, and then repost the job.</span></span> <span data-ttu-id="c80d3-155">I dettagli dell'annuncio di lavoro in Attract non vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="c80d3-155">The job details in Attract aren't changed.</span></span>

### <a name="remove-a-broadbean-job-posting"></a><span data-ttu-id="c80d3-156">Rimuovere la pubblicazione di un annuncio di lavoro da Broadbean</span><span class="sxs-lookup"><span data-stu-id="c80d3-156">Remove a Broadbean job posting</span></span>

<span data-ttu-id="c80d3-157">È possibile rimuovere la registrazione di un annuncio di lavoro da Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c80d3-157">You can remove a job posting from Broadbean as you require.</span></span>

1. <span data-ttu-id="c80d3-158">In Attract, aprire l'annuncio di lavoro da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="c80d3-158">In Attract, open the job that you want to remove.</span></span>
2. <span data-ttu-id="c80d3-159">Nella sezione **Registrazioni**, selezionare il pulsante con i puntini di sospensione (**...**) corrispondente a Broadbean, quindi selezionare **Rimuovi pubblicazione**.</span><span class="sxs-lookup"><span data-stu-id="c80d3-159">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **Remove Post**.</span></span>

<span data-ttu-id="c80d3-160">Dopo che Broadbean rimuove l'annuncio di lavoro, l'elemento Broadbean in Attract presenta il pulsante **Pubblica ora**.</span><span class="sxs-lookup"><span data-stu-id="c80d3-160">After Broadbean removes the job, the Broadbean item in Attract has a **Post Now** button.</span></span> <span data-ttu-id="c80d3-161">La presenza di questo pulsante indica che l'annuncio di lavoro è stato rimosso e può essere pubblicato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="c80d3-161">The presence of this button indicates that the job has been removed and can be posted again.</span></span>

### <a name="troubleshoot-the-broadbean-integration"></a><span data-ttu-id="c80d3-162">Risolvere i problemi relativi all'integrazione di Broadbean</span><span class="sxs-lookup"><span data-stu-id="c80d3-162">Troubleshoot the Broadbean integration</span></span>

<span data-ttu-id="c80d3-163">In caso di problemi nel pubblicare un annuncio di lavoro su Broadbean, effettuare quanto segue.</span><span class="sxs-lookup"><span data-stu-id="c80d3-163">If you're having trouble posting a job to Broadbean, try these steps.</span></span>

1. <span data-ttu-id="c80d3-164">Verificare che le credenziali di Broadbean immesse in Attract siano valide e corrette.</span><span class="sxs-lookup"><span data-stu-id="c80d3-164">Verify that the Broadbean credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="c80d3-165">Se le credenziali sono valide e corrette, contattare il [supporto Broadbean](https://www.broadbean.com/resources/support/).</span><span class="sxs-lookup"><span data-stu-id="c80d3-165">If the credentials are valid and correct, contact [Broadbean support](https://www.broadbean.com/resources/support/).</span></span>
3. <span data-ttu-id="c80d3-166">Se il problema persiste, contattare il [supporto tecnico Microsoft](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="c80d3-166">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>
