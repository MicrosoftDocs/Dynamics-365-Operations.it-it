---
title: Aggiornare un processo
description: Microsoft Dynamics 365 Human Resources è un vero software come un servizio (SaaS, software as a service) che fornisce aggiornamenti di servizio continui e touchless per modifiche di applicazioni o piattaforme.
author: andreabichsel
manager: tfehr
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 27561bfd9cb4f115cc507954c837ea93f9c93b72
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466834"
---
# <a name="update-process"></a><span data-ttu-id="ed836-103">Aggiornare un processo</span><span class="sxs-lookup"><span data-stu-id="ed836-103">Update process</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="ed836-104">Microsoft Dynamics 365 Human Resources è un vero software come un servizio (SaaS, software as a service) che fornisce aggiornamenti di servizio continui e touchless.</span><span class="sxs-lookup"><span data-stu-id="ed836-104">Microsoft Dynamics 365 Human Resources is a true software as a service (SaaS) that provides continuous, touchless service updates.</span></span> <span data-ttu-id="ed836-105">Questi aggiornamenti contengono modifiche all'applicazione e alla piattaforma che spesso generano miglioramenti fondamentali nel servizio, inclusi aggiornamenti normativi.</span><span class="sxs-lookup"><span data-stu-id="ed836-105">These updates contain both application and platform changes that often provide critical improvements to the service, including regulatory updates.</span></span>

## <a name="update-policy"></a><span data-ttu-id="ed836-106">Criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="ed836-106">Update policy</span></span>

<span data-ttu-id="ed836-107">Gli aggiornamenti vengono rilasciati a cadenza regolare per tutti gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="ed836-107">Updates are released on a regular cadence to all environments.</span></span> <span data-ttu-id="ed836-108">Human Resources è supportato secondo i [criteri relativi al ciclo di vita di Microsoft](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), i quali offrono linee guida coerenti e prevedibili per la disponibilità del supporto.</span><span class="sxs-lookup"><span data-stu-id="ed836-108">Human Resources is supported according to the [Microsoft Lifecycle policy](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), which provides consistent and predictable guidelines for the availability of support.</span></span>

## <a name="release-cadence"></a><span data-ttu-id="ed836-109">Cadenza di rilascio</span><span class="sxs-lookup"><span data-stu-id="ed836-109">Release cadence</span></span> 

<span data-ttu-id="ed836-110">Gli aggiornamenti di Human Resources vengono applicati automaticamente a tutti gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="ed836-110">Human Resources updates are applied to all environments automatically.</span></span> <span data-ttu-id="ed836-111">Human Resources fornisce due tipi di rilasci:</span><span class="sxs-lookup"><span data-stu-id="ed836-111">Human Resources provides two types of releases:</span></span>

- <span data-ttu-id="ed836-112">**Aggiornamenti del servizio**: aggiornamenti bisettimanali che includono correzioni di bug e nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ed836-112">**Service updates**: Updates occur every two weeks that include bug fixes and new features.</span></span> <span data-ttu-id="ed836-113">Gli aggiornamenti del servizio includono anche gli aggiornamenti applicabili della piattaforma quando vengono rilasciati.</span><span class="sxs-lookup"><span data-stu-id="ed836-113">Service updates also include applicable Platform updates when they release.</span></span> <span data-ttu-id="ed836-114">Per avere un'idea di quando vengono rilasciati gli aggiornamenti della piattaforma, vedere [Tabella 3: versioni della piattaforma ](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases).</span><span class="sxs-lookup"><span data-stu-id="ed836-114">To get an idea of when Platform updates are released, see [Table 3: Platform releases](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases).</span></span> <span data-ttu-id="ed836-115">Gli aggiornamenti bisettimanali prevedono un'implementazione globale in fasi tra le regioni.</span><span class="sxs-lookup"><span data-stu-id="ed836-115">Biweekly updates have a staged global rollout across regions.</span></span> <span data-ttu-id="ed836-116">Per ulteriori informazioni sugli aggiornamenti bisettimanali, vedere [Novità o modifiche in Dynamics 365 Human Resources](hr-admin-whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="ed836-116">For more information about biweekly updates, see [What's new or changed in Dynamics 365 Human Resources](hr-admin-whats-new.md).</span></span>

    <span data-ttu-id="ed836-117">Tutti i datacenter supportati vengono aggiornati ogni due settimane, salvo diversa indicazione.</span><span class="sxs-lookup"><span data-stu-id="ed836-117">All supported data centers update every two weeks, unless otherwise noted.</span></span> <span data-ttu-id="ed836-118">Gli Stati Uniti, l'Australia, l'Europa, il Regno Unito, l'Asia e il Canada sono inclusi negli aggiornamenti bisettimanali.</span><span class="sxs-lookup"><span data-stu-id="ed836-118">US, Australia, Europe, UK, Asia, and Canada regions are included in biweekly updates.</span></span> 

- <span data-ttu-id="ed836-119">**Aggiornamenti della soluzione Dataverse**: questi aggiornamenti si verificano all'incirca ogni sei settimane, come necessario.</span><span class="sxs-lookup"><span data-stu-id="ed836-119">**Dataverse solution updates**: These updates occur approximately every six weeks, as needed.</span></span> <span data-ttu-id="ed836-120">Includono nuove entità e modifiche a entità esistenti in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="ed836-120">They include new entities and changes to existing entities in Dataverse.</span></span> <span data-ttu-id="ed836-121">Questi aggiornamenti vengono rilasciati nelle stesse aree degli aggiornamenti bisettimanali e richiedono circa sei settimane per replicarsi in tutti i datacenter.</span><span class="sxs-lookup"><span data-stu-id="ed836-121">These updates release to the same regions as the biweekly updates, and they take about six weeks to replicate through all data centers.</span></span> <span data-ttu-id="ed836-122">Gli aggiornamenti della soluzione possono essere allineati o meno agli aggiornamenti del servizio bisettimanali.</span><span class="sxs-lookup"><span data-stu-id="ed836-122">Solution updates may or may not align with biweekly service updates.</span></span>

> [!NOTE]
> <span data-ttu-id="ed836-123">Gli aggiornamenti della soluzione sono disponibili in tutti i datacenter una volta rilasciati.</span><span class="sxs-lookup"><span data-stu-id="ed836-123">Solution updates are available on all data centers once they're released.</span></span> <span data-ttu-id="ed836-124">Se non si desidera attendere la replica automatica degli aggiornamenti, è possibile applicare manualmente questi aggiornamenti in qualsiasi datacenter di qualsiasi ambiente.</span><span class="sxs-lookup"><span data-stu-id="ed836-124">If you don't want to wait for the updates to replicate automatically, you can manually apply these updates on any environment in any data center.</span></span>

<span data-ttu-id="ed836-125">Quando necessario, Human Resources fornisce anche i seguenti tipi di correzioni:</span><span class="sxs-lookup"><span data-stu-id="ed836-125">When needed, Human Resources also provides the following types of fixes:</span></span>

- <span data-ttu-id="ed836-126">**Revisione (aggiornamento rapido)**: correzioni di bug che possono verificarsi con o indipendentemente da una versione di aggiornamento del servizio bisettimanale</span><span class="sxs-lookup"><span data-stu-id="ed836-126">**Revision (hotfix)**: Bug fixes that can occur either with or apart from a biweekly service update release</span></span>

- <span data-ttu-id="ed836-127">**Correzione di emergenza**: aggiornamenti rapidi proattivi e reattivi in genere autonomi che possono includere modifiche al codice o solo alla configurazione per risolvere problemi del sito live e possono verificarsi separatamente da una versione di aggiornamento del servizio bisettimanale</span><span class="sxs-lookup"><span data-stu-id="ed836-127">**Emergency fix**: Proactive and reactive hotfixes that are standalone in nature, can include configuration-only or code changes to resolve live site issues, and can occur apart from a biweekly service update release</span></span>

<span data-ttu-id="ed836-128">I rilasci sono verificati, testati e convalidati in un ambiente interno.</span><span class="sxs-lookup"><span data-stu-id="ed836-128">Releases are reviewed, tested, and validated on an internal environment.</span></span> <span data-ttu-id="ed836-129">Dopo essere state autorizzate, le build vengono distribuite alla produzione.</span><span class="sxs-lookup"><span data-stu-id="ed836-129">After builds are signed off, they're then deployed to production.</span></span>

## <a name="release-cadence-exceptions-in-2020"></a><span data-ttu-id="ed836-130">Eccezioni di cadenza di rilascio nel 2020</span><span class="sxs-lookup"><span data-stu-id="ed836-130">Release cadence exceptions in 2020</span></span>

<span data-ttu-id="ed836-131">Per tenere conto delle festività, il programma di rilascio per novembre e dicembre 2020 è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ed836-131">To account for holidays, the release schedule for November and December 2020 is as follows:</span></span>

- <span data-ttu-id="ed836-132">Versione di novembre: 2 novembre - 13 novembre</span><span class="sxs-lookup"><span data-stu-id="ed836-132">November release: November 2 - November 13</span></span>
- <span data-ttu-id="ed836-133">Versione di dicembre: 30 dicembre - 11 dicembre</span><span class="sxs-lookup"><span data-stu-id="ed836-133">December release: November 30 - December 11</span></span>
 
<span data-ttu-id="ed836-134">La cadenza di rilascio bisettimanale riprenderà come al solito l'11 gennaio 2021.</span><span class="sxs-lookup"><span data-stu-id="ed836-134">The two-week release cadence will resume as usual on January 11, 2021.</span></span>

## <a name="communications"></a><span data-ttu-id="ed836-135">Comunicazioni</span><span class="sxs-lookup"><span data-stu-id="ed836-135">Communications</span></span>

<span data-ttu-id="ed836-136">È possibile scoprire cosa c'è in cantiere per Human Resources e cosa abbiamo rilasciato nelle seguenti pagine:</span><span class="sxs-lookup"><span data-stu-id="ed836-136">You can find out what's in the works for Human Resources and what we've released in the following locations:</span></span>

- [<span data-ttu-id="ed836-137">Roadmap di Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="ed836-137">Dynamics 365 Human Resources roadmap</span></span>](https://dynamics.microsoft.com/roadmap/human-resources/)

- [<span data-ttu-id="ed836-138">Piani di rilascio di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ed836-138">Dynamics 365 Release Plans</span></span>](https://docs.microsoft.com/dynamics365/release-plans/)

- [<span data-ttu-id="ed836-139">Novità o modifiche in Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="ed836-139">What's new or changed in Dynamics 365 Human Resources</span></span>](hr-admin-whats-new.md)

- <span data-ttu-id="ed836-140">[Ricerca di problemi in Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs) (solo per bug relativi alla piattaforma)</span><span class="sxs-lookup"><span data-stu-id="ed836-140">[Issue search in Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs) (for Platform-related bugs only)</span></span>

- [<span data-ttu-id="ed836-141">Blog di Human Resources</span><span class="sxs-lookup"><span data-stu-id="ed836-141">Human Resources blog</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [<span data-ttu-id="ed836-142">Comunità Yammer di Human Resources</span><span class="sxs-lookup"><span data-stu-id="ed836-142">Human Resources Yammer community</span></span>](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a><span data-ttu-id="ed836-143">Funzionalità di anteprima in un ambiente sandbox</span><span class="sxs-lookup"><span data-stu-id="ed836-143">Preview features in a sandbox environment</span></span>

<span data-ttu-id="ed836-144">È possibile convalidare le funzionalità di anteprima in un ambiente sandbox prima di abilitarle nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="ed836-144">You can validate preview features in a sandbox environment before enabling them in your production environment.</span></span> <span data-ttu-id="ed836-145">Per ulteriori informazioni sull'abilitazione delle funzionalità, vedere [Panoramica della gestione funzionalità](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="ed836-145">For more information about enabling features, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>

<span data-ttu-id="ed836-146">Tutte le nuove funzionalità rimangono in anteprima per almeno 30 giorni e in genere per 30-60 giorni.</span><span class="sxs-lookup"><span data-stu-id="ed836-146">All new features remain in preview for at least 30 days, and typically 30-60 days.</span></span> <span data-ttu-id="ed836-147">Le principali funzionalità sono generalmente disponibili in ottobre e aprile di ogni anno successivo al periodo di anteprima.</span><span class="sxs-lookup"><span data-stu-id="ed836-147">Major features are generally available in October and April of each year following the preview period.</span></span> <span data-ttu-id="ed836-148">Non appena nuove funzioni sono presenti nell'area di lavoro Gestione funzionalità, è possibile attivarle.</span><span class="sxs-lookup"><span data-stu-id="ed836-148">As soon as you see new capabilities in the Feature management workspace, you can turn them on.</span></span> <span data-ttu-id="ed836-149">Alcune funzionalità possono essere attive per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ed836-149">Some features may be on by default.</span></span>

<span data-ttu-id="ed836-150">Talvolta, una funzionalità integrale viene attivata per impostazione predefinita e non può essere disattivata, ad esempio l'area di lavoro Gestione funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ed836-150">At times, an integral feature will be on by default and can't be turned off (for example, the Feature management workspace).</span></span>

<span data-ttu-id="ed836-151">Una volta che una funzionalità è generalmente disponibile, può essere attivata o disattivata negli ambienti di produzione.</span><span class="sxs-lookup"><span data-stu-id="ed836-151">Once a feature is generally available, it may be turned on or off in production environments.</span></span> <span data-ttu-id="ed836-152">L'area di lavoro Gestione funzionalità indica quando una funzionalità di anteprima diventa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="ed836-152">The Feature management workspace indicates when a preview feature will become mandatory.</span></span> <span data-ttu-id="ed836-153">Questa data è in genere il 1° ottobre o il 1° aprile in base ai piani di rilascio semestrali.</span><span class="sxs-lookup"><span data-stu-id="ed836-153">This date is usually on October 1 or April 1 to align with the semiannual release plans.</span></span> <span data-ttu-id="ed836-154">Non è possibile disattivare le funzionalità obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="ed836-154">You can't turn off mandatory features.</span></span> <span data-ttu-id="ed836-155">Finché non diventa obbligatoria, è possibile attivare e disattivare una funzionalità in tutti gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="ed836-155">Until it becomes mandatory, you can turn a feature on and off in all environments.</span></span>

<span data-ttu-id="ed836-156">Consigliamo vivamente di visualizzare in anteprima le funzionalità in un ambiente sandbox o di prova.</span><span class="sxs-lookup"><span data-stu-id="ed836-156">We highly recommend previewing features in a sandbox or trial environment.</span></span> <span data-ttu-id="ed836-157">È meglio creare una copia dell'ambiente di produzione o del database corrente in un ambiente sandbox in modo da poter ottenere l'esperienza completa delle nuove funzionalità con i propri dati.</span><span class="sxs-lookup"><span data-stu-id="ed836-157">It's best to create a copy of your current production environment or database into a sandbox environment so you can get the complete experience of the new features with your data.</span></span>

<span data-ttu-id="ed836-158">Per ulteriori informazioni sul provisioning di un ambiente sandbox, vedere [Eseguire il provisioning di un progetto di Human Resources](hr-admin-setup-provision.md).</span><span class="sxs-lookup"><span data-stu-id="ed836-158">For more information about provisioning a sandbox environment, see [Provision a Human Resources project](hr-admin-setup-provision.md).</span></span> <span data-ttu-id="ed836-159">Per rimuovere un ambiente di test, vedere [Rimuovere un'istanza](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span><span class="sxs-lookup"><span data-stu-id="ed836-159">To remove a test environment, see [Remove an instance](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span></span> 

## <a name="report-bugs"></a><span data-ttu-id="ed836-160">Segnalare i bug</span><span class="sxs-lookup"><span data-stu-id="ed836-160">Report bugs</span></span>

<span data-ttu-id="ed836-161">Durante il test delle funzionalità di anteprima o di nuove funzionalità, è possibile che vengano rilevati elementi che non funzionano come previsto.</span><span class="sxs-lookup"><span data-stu-id="ed836-161">While testing preview features or trying new capabilities, you might find items that don't work as expected.</span></span> <span data-ttu-id="ed836-162">Si prega di segnalare eventuali bug mediante il [supporto di Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).</span><span class="sxs-lookup"><span data-stu-id="ed836-162">Please report any bugs through [Microsoft Dynamics 365 support](https://dynamics.microsoft.com/support/).</span></span>

## <a name="see-also"></a><span data-ttu-id="ed836-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed836-163">See also</span></span>

[<span data-ttu-id="ed836-164">Piani di rilascio di Dynamics 365 e Power Platform</span><span class="sxs-lookup"><span data-stu-id="ed836-164">Dynamics 365 and Power Platform Release Plans</span></span>](https://docs.microsoft.com/dynamics365/release-plans)</br>
[<span data-ttu-id="ed836-165">Novità o modifiche in Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="ed836-165">What's new or changed in Dynamics 365 Human Resource</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="ed836-166">Criteri del ciclo di vita del software</span><span class="sxs-lookup"><span data-stu-id="ed836-166">Software lifecycle policy</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy)



[!INCLUDE[footer-include](../includes/footer-banner.md)]