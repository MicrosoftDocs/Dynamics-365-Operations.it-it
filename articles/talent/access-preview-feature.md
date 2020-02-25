---
title: Gestire le funzionalità
description: Questo argomento descrive come un amministratore può attivare le funzionalità in anteprima in Microsoft Dynamics 365 Talent ed elenca le funzionalità attualmente attivate per l'anteprima.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.1.0, Talent
ms.openlocfilehash: d818e9e04ce88e5ab285ef8176334809447fb477
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006431"
---
# <a name="manage-features"></a><span data-ttu-id="d32e8-103">Gestire le funzionalità</span><span class="sxs-lookup"><span data-stu-id="d32e8-103">Manage features</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d32e8-104">Nell'ambito della continua implementazione di funzionalità di gestione risorse umane per Microsoft Dynamics 365 Human Resources, vogliamo consentire ai clienti di utilizzare al più presto le nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d32e8-104">As part of our continuous rollout of human capital management (HCM) capabilities for Microsoft Dynamics 365 Human Resources, we want to let customers experience new features as soon as possible.</span></span> <span data-ttu-id="d32e8-105">Gli amministratori possono visualizzare e utilizzare le funzionalità in anteprima nei loro ambienti.</span><span class="sxs-lookup"><span data-stu-id="d32e8-105">Administrators can see and use preview features in their environments.</span></span> <span data-ttu-id="d32e8-106">Queste funzionalità sono quasi pronte per la disponibilità generale e sono state sottoposte a test esaurienti.</span><span class="sxs-lookup"><span data-stu-id="d32e8-106">These features are almost ready for general availability and have gone through extensive testing.</span></span> <span data-ttu-id="d32e8-107">Il nostro scopo è di ottenere un ultimo riscontro e la convalida dai clienti prima del rilascio delle funzionalità per una disponibilità generale.</span><span class="sxs-lookup"><span data-stu-id="d32e8-107">We're just looking for a final round of customer feedback and validation before we release them for general availability.</span></span>

<span data-ttu-id="d32e8-108">Questo argomento descrive come è possibile attivare le funzionalità in anteprima ed elenca le funzionalità attualmente disponibili per l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="d32e8-108">This topic describes how you can enable preview features, and it lists the features that are currently available for preview.</span></span> <span data-ttu-id="d32e8-109">L'elenco sarà aggiornato a mano a mano che vengono rilasciate nuove funzionalità in anteprima e le versioni di disponibilità generale delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d32e8-109">This list will be updated as features are released to general availability and as new features are released to preview.</span></span> <span data-ttu-id="d32e8-110">Il rilascio di nuove funzionalità in anteprima non viene notificato.</span><span class="sxs-lookup"><span data-stu-id="d32e8-110">No notification is given when new features are released to preview.</span></span> <span data-ttu-id="d32e8-111">Gli utenti scopriranno tali funzionalità durante l'utilizzo del prodotto.</span><span class="sxs-lookup"><span data-stu-id="d32e8-111">Users will just start to see the features.</span></span> <span data-ttu-id="d32e8-112">Per ulteriori informazioni sulle nuove funzionalità, vedere [Novità o modifiche in Dynamics 365 Talent](./whats-new.md) e [Note sulla versione di Dynamics 365 e Power Platform](https://docs.microsoft.com/business-applications-release-notes).</span><span class="sxs-lookup"><span data-stu-id="d32e8-112">For more information about new features in Talent, see [What's new or changed in Dynamics 365 Talent](./whats-new.md) and [Dynamics 365 and Power Platform Release Notes](https://docs.microsoft.com/business-applications-release-notes).</span></span>

## <a name="enable-or-disable-preview-features"></a><span data-ttu-id="d32e8-113">Attivare o disattivare le funzionalità in anteprima</span><span class="sxs-lookup"><span data-stu-id="d32e8-113">Enable or disable preview features</span></span>

<span data-ttu-id="d32e8-114">Per accedere alle funzionalità in anteprima, è necessario dapprima attivarle nel proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="d32e8-114">To access preview features, you must first enable them in your environment.</span></span> <span data-ttu-id="d32e8-115">L'attivazione o la disattivazione delle funzionalità in anteprima è specifica dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="d32e8-115">Enabling or disabling preview features is environment-specific.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d32e8-116">Quando si attiva l'impostazione **Funzionalità in anteprima**, si attivano le funzionalità in anteprima per tutti gli utenti dell'organizzazione in quell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="d32e8-116">When you turn on the **Preview Features** setting, you enable preview features for all users in your organization who are in that environment.</span></span> <span data-ttu-id="d32e8-117">Quando si disattiva l'impostazione, si disattivano le funzionalità in anteprima e le si rendono inaccessibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="d32e8-117">When you turn off the setting, you disable preview features and make them inaccessible to your users.</span></span> <span data-ttu-id="d32e8-118">Il supporto delle funzionalità in anteprima in Talent è limitato.</span><span class="sxs-lookup"><span data-stu-id="d32e8-118">Preview features have limited support in Talent.</span></span> <span data-ttu-id="d32e8-119">È possibile che utilizzino minori misure di privacy e di sicurezza e non sono incluse nel contratto di servizio di Talent.</span><span class="sxs-lookup"><span data-stu-id="d32e8-119">They might use fewer privacy and security measures, and they aren't included in the Talent service level agreement (SLA).</span></span> <span data-ttu-id="d32e8-120">Si consiglia di non utilizzare le funzionalità in anteprima per elaborare dati personali (ovvero qualsiasi informazione che potrebbe consentire l'identificazione dell'utente) o per elaborare altri dati soggetti a requisiti di conformità legali o normativi.</span><span class="sxs-lookup"><span data-stu-id="d32e8-120">You should not use preview features to process personal data (that is, any information that could identify you), or to process other data that is subject to legal or regulatory compliance requirements.</span></span>

### <a name="attract"></a><span data-ttu-id="d32e8-121">Attract</span><span class="sxs-lookup"><span data-stu-id="d32e8-121">Attract</span></span>

1. <span data-ttu-id="d32e8-122">Accedere a Microsoft Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="d32e8-122">Sign in to Microsoft Dynamics 365 Talent: Attract.</span></span>
2. <span data-ttu-id="d32e8-123">Nel menu **Impostazione** (il simbolo di ingranaggio) nell'angolo superiore destro, selezionare **Interfaccia di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="d32e8-123">On the **Setup** menu (the gear symbol) in the upper-right corner, select **Admin center**.</span></span>
3. <span data-ttu-id="d32e8-124">Nella scheda **Gestione funzionalità**, selezionare l'opzione accanto a **Funzionalità in anteprima** di modo che diventi blu e sia impostata su **Attivata**.</span><span class="sxs-lookup"><span data-stu-id="d32e8-124">On the **Feature management** tab, select the option next to **Preview features** so that it turns blue and says **On**.</span></span>

    ![Attivare funzionalità in anteprima in Attract](./media/attract-enable-preview-features.png)

4. <span data-ttu-id="d32e8-126">Selezionare o deselezionare singole funzionalità in anteprima.</span><span class="sxs-lookup"><span data-stu-id="d32e8-126">Select or cancel the selection of individual preview features.</span></span> <span data-ttu-id="d32e8-127">Se non si esegue alcuna operazione, tutte le funzionalità in anteprima disponibili vengono attivate.</span><span class="sxs-lookup"><span data-stu-id="d32e8-127">If you do nothing, all available preview features are enabled.</span></span>
5. <span data-ttu-id="d32e8-128">Aggiornare il browser per visualizzare le nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d32e8-128">Refresh your browser to start to see the new features.</span></span> <span data-ttu-id="d32e8-129">Tutti gli utenti che hanno già eseguito l'accesso, vedranno le funzionalità all'accesso successivo oppure possono aggiornare il browser per visualizzare le funzionalità immediatamente.</span><span class="sxs-lookup"><span data-stu-id="d32e8-129">Any users who are already signed in will see the features the next time they sign in, or they can refresh their browser to see the features immediately.</span></span>

> [!NOTE]
> <span data-ttu-id="d32e8-130">Alcune funzionalità in anteprima potrebbero richiedere una configurazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="d32e8-130">Some preview features might require additional configuration.</span></span> <span data-ttu-id="d32e8-131">Utilizzare i collegamenti accanto alla funzionalità in anteprima per completarne la configurazione.</span><span class="sxs-lookup"><span data-stu-id="d32e8-131">Follow the links next to the preview feature to complete the setup for it.</span></span>

## <a name="feedback"></a><span data-ttu-id="d32e8-132">Commenti e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="d32e8-132">Feedback</span></span>

<span data-ttu-id="d32e8-133">Vogliamo ricevere commenti degli utenti riguardo l'utilizzo di una o più di queste funzionalità in anteprima.</span><span class="sxs-lookup"><span data-stu-id="d32e8-133">We want to hear from you about your experience with any of these preview features.</span></span> <span data-ttu-id="d32e8-134">Invitiamo gli utenti a pubblicare regolarmente i loro commenti relativi all'utilizzo di queste o altre funzionalità sui siti elencati di seguito:</span><span class="sxs-lookup"><span data-stu-id="d32e8-134">We encourage you to regularly post your feedback on the following sites as you use these or any other features:</span></span>

- <span data-ttu-id="d32e8-135">[Community](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) - Questo sito è una risorsa eccellente dove gli utenti possono discutere casi d'uso, porre domande e ottenere informazioni dalla community.</span><span class="sxs-lookup"><span data-stu-id="d32e8-135">[Community](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – This site is a great resource where users can discuss use cases, ask questions, and get community help.</span></span>
- <span data-ttu-id="d32e8-136">Invitiamo gli utenti a indicare le funzionalità che vorrebbero fossero integrate nel prodotto o le modifiche che dovrebbero essere apportate alle funzionalità esistenti.</span><span class="sxs-lookup"><span data-stu-id="d32e8-136">Let us know about features that you want to see in the product, or let us know about any changes you think we should make to existing features.</span></span> <span data-ttu-id="d32e8-137">È possibile suggerire idee sul prodotto su tali siti:</span><span class="sxs-lookup"><span data-stu-id="d32e8-137">Suggest product ideas on the following sites:</span></span>

    - [<span data-ttu-id="d32e8-138">Idee per Attract</span><span class="sxs-lookup"><span data-stu-id="d32e8-138">Attract ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [<span data-ttu-id="d32e8-139">Idee per Onboard</span><span class="sxs-lookup"><span data-stu-id="d32e8-139">Onboard ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Onboard/idb-p/Onboard)

<span data-ttu-id="d32e8-140">Assicurarsi di non includere dati personali (qualsiasi informazione che possa consentire l'identificazione dell'utente) nel riscontro o nei commenti sul prodotto inviati.</span><span class="sxs-lookup"><span data-stu-id="d32e8-140">Make sure that you don't include personal data (any information that could identify you) in your feedback or product review submissions.</span></span> <span data-ttu-id="d32e8-141">Le informazioni raccolte potrebbero essere analizzate ulteriormente e non vengono utilizzate per soddisfare richieste in base alle normative sulla privacy applicabili.</span><span class="sxs-lookup"><span data-stu-id="d32e8-141">Collected information might be analyzed further and isn't used to answer requests under applicable privacy laws.</span></span> <span data-ttu-id="d32e8-142">I dati personali raccolti separatamente in questi programmi sono soggetti all'[Informativa sulla privacy di Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="d32e8-142">Personal data that is collected separately under these programs is subject to the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span>

> [!TIP]
> <span data-ttu-id="d32e8-143">Si consiglia di aggiungere questo argomento ai Preferiti per mantenersi aggiornati sulle nuove funzionalità in anteprima che vengono rilasciate.</span><span class="sxs-lookup"><span data-stu-id="d32e8-143">Bookmark this topic, and check back often to stay up to date about new preview features as we release them.</span></span>

## <a name="see-also"></a><span data-ttu-id="d32e8-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d32e8-144">See also</span></span>

- [<span data-ttu-id="d32e8-145">Provare o acquistare app Talent</span><span class="sxs-lookup"><span data-stu-id="d32e8-145">Try or buy Talent apps</span></span>](https://dynamics.microsoft.com/talent/overview/)
- [<span data-ttu-id="d32e8-146">Novità o modifiche in Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="d32e8-146">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="d32e8-147">Piani di rilascio</span><span class="sxs-lookup"><span data-stu-id="d32e8-147">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="d32e8-148">Ottenere supporto per Microsoft Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="d32e8-148">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)
