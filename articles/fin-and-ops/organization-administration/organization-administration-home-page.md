---
title: Home page di amministrazione organizzazione
description: Sono indicate le risorse che consentono di utilizzare Microsoft Dynamics 365 for Finance and Operations nell'organizzazione.
author: sericks007
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 20421
ms.assetid: 7aa24a03-d172-47e9-81f8-ebd39e80bc60
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a693529b55b66eb940f8215a336d5c4ae0acedd
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "332819"
---
# <a name="organization-administration-home-page"></a><span data-ttu-id="f8c2f-103">Home page di amministrazione organizzazione</span><span class="sxs-lookup"><span data-stu-id="f8c2f-103">Organization administration home page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f8c2f-104">Questo argomento descrive le risorse che power user e amministratori possono utilizzare per configurare Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-104">This topic points to content that will help power users and administrators configure Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="f8c2f-105">Tali risorse consentono di configurare efficacemente il sistema per l'organizzazione e l'attività commerciale.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-105">This content will help them configure the system to work smoothly and effectively for your organization and business.</span></span>

<span data-ttu-id="f8c2f-106">La maggior parte del contenuto qui elencato si applica alle funzionalità del modulo **Amministrazione organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-106">Much of the content listed here applies to features in the **Organizational administration** module.</span></span> <span data-ttu-id="f8c2f-107">Un paio di attività, ad esempio la creazione e l'uso di un modello di record, sono tuttavia eseguibili in qualsiasi modulo per consentire una gestione ancor più efficace dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-107">However, there are a couple of tasks, such as creating and using a record template, that can be performed in any module to help your organization run more efficiently.</span></span>

## <a name="number-sequences"></a><span data-ttu-id="f8c2f-108">Sequenze numeriche</span><span class="sxs-lookup"><span data-stu-id="f8c2f-108">Number sequences</span></span>

<span data-ttu-id="f8c2f-109">Le sequenze numeriche vengono utilizzate per generare identificatori univoci leggibili per record transazioni e dati master che richiedono identificatori.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-109">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require identifiers.</span></span> <span data-ttu-id="f8c2f-110">Un record transazioni o dati master che richiede un identificatore viene definito *riferimento*.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-110">A master data record or transaction record that requires an identifier is referred to as a *reference*.</span></span> <span data-ttu-id="f8c2f-111">Prima di poter creare nuovi record per un riferimento, è necessario impostare una sequenza numerica e associarla al riferimento.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-111">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span>

- [<span data-ttu-id="f8c2f-112">Panoramica delle sequenze numeriche</span><span class="sxs-lookup"><span data-stu-id="f8c2f-112">Number sequence overview</span></span>](number-sequence-overview.md)
- <span data-ttu-id="f8c2f-113">[Impostazione guidata sequenze numeriche](tasks/set-up-number-sequences-wizard.md) (guida attività)</span><span class="sxs-lookup"><span data-stu-id="f8c2f-113">[Set up number sequences by using a wizard](tasks/set-up-number-sequences-wizard.md) (Task guide)</span></span>
- <span data-ttu-id="f8c2f-114">[Impostare sequenze numeriche singole](tasks/set-up-number-sequences-individual-basis.md) (guida attività)</span><span class="sxs-lookup"><span data-stu-id="f8c2f-114">[Set up number sequences on an individual basis](tasks/set-up-number-sequences-individual-basis.md) (Task guide)</span></span>

## <a name="organizations"></a><span data-ttu-id="f8c2f-115">Organizzazioni</span><span class="sxs-lookup"><span data-stu-id="f8c2f-115">Organizations</span></span>

<span data-ttu-id="f8c2f-116">Un'organizzazione è un gruppo di persone che collaborano per svolgere un processo aziendale o raggiungere un obiettivo.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-116">An organization is a group of people who are working together to carry out a business process or achieve a goal.</span></span> <span data-ttu-id="f8c2f-117">Le gerarchie organizzative rappresentano i rapporti tra le organizzazioni che fanno parte dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-117">Organizational hierarchies represent the relationships between the organizations that make up your business.</span></span>

<span data-ttu-id="f8c2f-118">Prima di impostare le organizzazioni e le gerarchie organizzative in Finance and Operations, assicurarsi di pianificare il modo in cui l'azienda verrà modellata.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-118">Before you set up organizations and organization hierarchies in Finance and Operations, make sure that you plan how your business will be modeled.</span></span> <span data-ttu-id="f8c2f-119">Il modello di organizzazione ha un effetto significativo sull'implementazione di Finance and Operations e sui processi aziendali.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-119">The organization model has a significant effect on the implementation of Finance and Operations and on business processes.</span></span>

- [<span data-ttu-id="f8c2f-120">Organizzazioni e gerarchie organizzative</span><span class="sxs-lookup"><span data-stu-id="f8c2f-120">Organizations and organizational hierarchies</span></span>](organizations-organizational-hierarchies.md)
- [<span data-ttu-id="f8c2f-121">Pianificazione della gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="f8c2f-121">Plan your organizational hierarchy</span></span>](plan-organizational-hierarchy.md)
- <span data-ttu-id="f8c2f-122">[Creare una gerarchia organizzativa](tasks/create-organization-hierarchy.md) (guida attività)</span><span class="sxs-lookup"><span data-stu-id="f8c2f-122">[Create an organization hierarchy](tasks/create-organization-hierarchy.md) (Task guide)</span></span>
- <span data-ttu-id="f8c2f-123">[Creare una persona giuridica](tasks/create-legal-entity.md) (guida attività)</span><span class="sxs-lookup"><span data-stu-id="f8c2f-123">[Create a legal entity](tasks/create-legal-entity.md) (Task guide)</span></span>
- <span data-ttu-id="f8c2f-124">[Creare un'unità operativa](tasks/create-operating-unit.md) (guida attività)</span><span class="sxs-lookup"><span data-stu-id="f8c2f-124">[Create an operating unit](tasks/create-operating-unit.md) (Task guide)</span></span>

## <a name="address-books"></a><span data-ttu-id="f8c2f-125">Rubriche</span><span class="sxs-lookup"><span data-stu-id="f8c2f-125">Address books</span></span>

<span data-ttu-id="f8c2f-126">La rubrica globale è un archivio centralizzato per dati master che devono essere archiviati per tutte le persone e organizzazioni interne ed esterne con cui la società interagisce.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-126">The global address book is a centralized repository for master data that must be stored for all internal and external persons and organizations that the company interacts with.</span></span> <span data-ttu-id="f8c2f-127">I dati associati ai record della parte includono il nome, l'indirizzo e le informazioni di contatto della parte.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-127">The data that is associated with party records includes the party's name, address, and contact information.</span></span>

<span data-ttu-id="f8c2f-128">Dopo aver creato la Rubrica globale, è possibile creare Rubriche aggiuntive in base alle esigenze, ad esempio una Rubrica separata per ogni società nell'organizzazione o per ogni linea di business.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-128">After you create the global address book, you can create additional address books as you require, such as a separate address book for each company in your organization or for each line of business.</span></span>

- [<span data-ttu-id="f8c2f-129">Rubrica globale</span><span class="sxs-lookup"><span data-stu-id="f8c2f-129">Global address book</span></span>](overview-global-address-book.md)
- [<span data-ttu-id="f8c2f-130">Pianificare la modalità di configurazione della rubrica globale e di rubriche aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f8c2f-130">Plan how to configure the global address book and additional address books</span></span>](plan-configuration-global-address-book-additional-address-books.md)
- [<span data-ttu-id="f8c2f-131">Configurare la rubrica globale</span><span class="sxs-lookup"><span data-stu-id="f8c2f-131">Configure the global address book</span></span>](tasks/configure-global-address-book.md)
- [<span data-ttu-id="f8c2f-132">Domande frequenti sulla rubrica</span><span class="sxs-lookup"><span data-stu-id="f8c2f-132">Address books FAQ</span></span>](qa-address-books.md)

## <a name="workflow"></a><span data-ttu-id="f8c2f-133">Workflow</span><span class="sxs-lookup"><span data-stu-id="f8c2f-133">Workflow</span></span>

<span data-ttu-id="f8c2f-134">Workflow è un sistema installato con Finance and Operations che consente di creare singoli flussi di lavoro o processi aziendali.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-134">Workflow is a system that is installed with Finance and Operations that you can use to create individual workflows, or business processes.</span></span> <span data-ttu-id="f8c2f-135">Quando si crea un flusso di lavoro, si definisce il modo in cui un documento attraversa il sistema, o si sposta allinterno dello stesso, identificando chi deve completare un'attività, prendere una decisione o approvare un documento.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-135">When you create a workflow, you specify how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span>

- [<span data-ttu-id="f8c2f-136">Panoramica del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f8c2f-136">Workflow overview</span></span>](overview-workflow-system.md)
- [<span data-ttu-id="f8c2f-137">Elementi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f8c2f-137">Workflow elements</span></span>](workflow-elements.md)
- [<span data-ttu-id="f8c2f-138">Azioni flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f8c2f-138">Workflow actions</span></span>](workflow-actions.md)
- [<span data-ttu-id="f8c2f-139">Creare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f8c2f-139">Create a workflow</span></span>](create-workflow.md)

## <a name="electronic-signatures"></a><span data-ttu-id="f8c2f-140">Firme elettroniche</span><span class="sxs-lookup"><span data-stu-id="f8c2f-140">Electronic signatures</span></span>

<span data-ttu-id="f8c2f-141">Una firma elettronica consente di confermare l'identità di una persona che sta per avviare o approvare un processo di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-141">An electronic signature confirms the identity of a person who is about to start or approve a computing process.</span></span> <span data-ttu-id="f8c2f-142">In alcuni settori una firma elettronica è considerata legalmente vincolante come una firma manuale.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-142">In some industries, an electronic signature is as legally binding as a handwritten signature.</span></span> <span data-ttu-id="f8c2f-143">Le firme elettroniche rappresentano un requisito di legge per diversi settori regolamentati, tra cui quello farmaceutico, quello alimentare e quello aerospaziale e della difesa.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-143">Electronic signatures are a regulations compliance requirement for several regulated industries, such as pharmaceuticals, food and beverage, and aerospace and defense.</span></span>

<span data-ttu-id="f8c2f-144">In Finance and Operations è possibile utilizzare le firme elettroniche per i processi aziendali critici.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-144">In Finance and Operations, you can use electronic signatures for critical business processes.</span></span> <span data-ttu-id="f8c2f-145">In alcuni processi sono disponibili funzionalità di firma elettronica incorporate.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-145">Some processes have built-in electronic signature capabilities.</span></span> <span data-ttu-id="f8c2f-146">È inoltre possibile creare requisiti di firma personalizzati per qualsiasi tabella o campo di database.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-146">You can also create custom signature requirements for any database table and field.</span></span>

- [<span data-ttu-id="f8c2f-147">Panoramica delle firme elettroniche</span><span class="sxs-lookup"><span data-stu-id="f8c2f-147">Electronic signature overview</span></span>](electronic-signature-overview.md)
- <span data-ttu-id="f8c2f-148">[Impostare firme elettroniche](tasks/set-up-electronic-signatures.md) (guida attività)</span><span class="sxs-lookup"><span data-stu-id="f8c2f-148">[Set up electronic signatures](tasks/set-up-electronic-signatures.md) (Task guide)</span></span>

## <a name="case-management"></a><span data-ttu-id="f8c2f-149">Gestione casi</span><span class="sxs-lookup"><span data-stu-id="f8c2f-149">Case management</span></span>

<span data-ttu-id="f8c2f-150">Grazie alla pianificazione, alla tracciabilità e all'analisi dei casi è possibile sviluppare soluzioni efficienti da poter utilizzare per problemi simili.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-150">By planning, tracking, and analyzing cases, you can develop efficient resolutions that can be used for similar issues.</span></span> <span data-ttu-id="f8c2f-151">Quando ad esempio i rappresentanti dell'assistenza clienti o gli specialisti delle risorse umane creano un caso, possono trovare nei file di caratteristiche del caso informazioni utili per gestire e risolvere il caso in modo più efficiente.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-151">For example, when customer service representatives or Human Resources generalists create cases, they can find information in knowledge articles to help them work with or resolve a case more efficiently.</span></span>

- [<span data-ttu-id="f8c2f-152">Panoramica della gestione casi</span><span class="sxs-lookup"><span data-stu-id="f8c2f-152">Case management overview</span></span>](cases.md)
- [<span data-ttu-id="f8c2f-153">Configurare la sicurezza, i processi e le categorie dei casi</span><span class="sxs-lookup"><span data-stu-id="f8c2f-153">Configure case security, processes, and categories</span></span>](plan-case-management.md)

## <a name="record-templates"></a><span data-ttu-id="f8c2f-154">Modelli di record</span><span class="sxs-lookup"><span data-stu-id="f8c2f-154">Record templates</span></span>

<span data-ttu-id="f8c2f-155">I modelli di record possono risultare utili per creare più rapidamente i record.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-155">Record templates can help you to create records more quickly.</span></span> <span data-ttu-id="f8c2f-156">È possibile creare un modello di record in modo che non sia necessario inserire in modo esplicito per ogni nuovo record i valori dei campi che vengono utilizzati più spesso.</span><span class="sxs-lookup"><span data-stu-id="f8c2f-156">You can create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span>

- [<span data-ttu-id="f8c2f-157">Modelli record</span><span class="sxs-lookup"><span data-stu-id="f8c2f-157">Record templates</span></span>](record-templates.md)
- <span data-ttu-id="f8c2f-158">[Creare un modello di record per facilitare l'immissione dei dati](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (Guida attività)</span><span class="sxs-lookup"><span data-stu-id="f8c2f-158">[Create a record template to facilitate data entry](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (Task guide)</span></span>
- <span data-ttu-id="f8c2f-159">[Utilizzare un modello di record per creare un nuovo record](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (guida attività)</span><span class="sxs-lookup"><span data-stu-id="f8c2f-159">[Use a record template to create a new record](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (Task guide)</span></span>

## <a name="general-organization-administration"></a><span data-ttu-id="f8c2f-160">Amministrazione organizzazione generale</span><span class="sxs-lookup"><span data-stu-id="f8c2f-160">General organization administration</span></span>

- <span data-ttu-id="f8c2f-161">[Modificare il banner o il logo](../get-started/tasks/change-banner-or-logo.md) (guida attività)</span><span class="sxs-lookup"><span data-stu-id="f8c2f-161">[Change the banner or logo](../get-started/tasks/change-banner-or-logo.md) (Task guide)</span></span>
- [<span data-ttu-id="f8c2f-162">Configurare la gestione dei documenti</span><span class="sxs-lookup"><span data-stu-id="f8c2f-162">Configure document management</span></span>](configure-document-management.md)
- [<span data-ttu-id="f8c2f-163">Configurare e inviare messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="f8c2f-163">Configure and send email</span></span>](configure-email.md)
- [<span data-ttu-id="f8c2f-164">Dati di data/ora e fusi orari</span><span class="sxs-lookup"><span data-stu-id="f8c2f-164">Date/time data and time zones</span></span>](date-time-zones.md)
