---
title: Introduzione all'API di integrazione del sistema di tracciabilità dei candidati
description: Questo argomento descrive l'API di integrazione del sistema di tracciabilità dei candidati (ATS) Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 48e368fe69443a5105ddba78a887bf9159bfe52a
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125595"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a><span data-ttu-id="f7b34-103">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="f7b34-103">Applicant Tracking System integration API introduction</span></span>

<span data-ttu-id="f7b34-104">Questo argomento descrive l'API di integrazione del sistema di tracciabilità dei candidati (ATS) Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f7b34-104">This topic describes the Dynamics 365 Human Resources Applicant Tracking System (ATS) integration API.</span></span> <span data-ttu-id="f7b34-105">Lo scopo dell'API è abilitare le integrazioni semplificate tra Dynamics 365 Human Resources e i sistemi ATS dei partner.</span><span class="sxs-lookup"><span data-stu-id="f7b34-105">The intent of the API is to enable streamlined integrations between Dynamics 365 Human Resources and partnering ATSs.</span></span>

![Flusso di integrazione ATS](media/hr-admin-integration-ats-api-introduction-flow.png)

<span data-ttu-id="f7b34-107">L'esperienza integrata inizia in Human Resources quando un responsabile delle assunzioni crea una richiesta di reclutamento.</span><span class="sxs-lookup"><span data-stu-id="f7b34-107">The integrated experience begins in Human Resources when a hiring manager creates a recruiting request.</span></span> <span data-ttu-id="f7b34-108">Quando la richiesta viene attivata, l'ATS estrae i dettagli della richiesta per creare un progetto di reclutamento.</span><span class="sxs-lookup"><span data-stu-id="f7b34-108">When the request is activated, the ATS pulls the detail for the request to create a recruiting project.</span></span> <span data-ttu-id="f7b34-109">Quindi segue la pipeline di reclutamento per selezionare e assumere un candidato per le posizioni.</span><span class="sxs-lookup"><span data-stu-id="f7b34-109">Then it follows the recruiting pipeline to select and hire a candidate for the position(s).</span></span> <span data-ttu-id="f7b34-110">Infine, l'ATS completa l'integrazione round trip inviando il record del candidato selezionato in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f7b34-110">Finally, the ATS completes the round-trip integration by sending the selected candidate’s record into Human Resources.</span></span> <span data-ttu-id="f7b34-111">Il record del candidato può quindi passare attraverso più convalide e flussi di lavoro di onboarding per creare il record del dipendente.</span><span class="sxs-lookup"><span data-stu-id="f7b34-111">The candidate record can then go through more onboarding validations and workflows to create the employee record.</span></span>

<span data-ttu-id="f7b34-112">Per abilitare l'integrazione, Human Resources ha aggiunto i seguenti componenti:</span><span class="sxs-lookup"><span data-stu-id="f7b34-112">To enable the integration, Human Resources has added the following components:</span></span>

1.  <span data-ttu-id="f7b34-113">Funzionalità per creare una richiesta di reclutamento.</span><span class="sxs-lookup"><span data-stu-id="f7b34-113">Functionality to create a recruiting request.</span></span>
2.  <span data-ttu-id="f7b34-114">Un profilo candidato ampliato e flussi di lavoro correlati.</span><span class="sxs-lookup"><span data-stu-id="f7b34-114">An expanded candidate profile and related workflows.</span></span>
3.  <span data-ttu-id="f7b34-115">Un'API di integrazione che apre le nuove funzionalità alle applicazioni di integrazione.</span><span class="sxs-lookup"><span data-stu-id="f7b34-115">An integration API opening up the new functionality to integrating applications.</span></span>

<span data-ttu-id="f7b34-116">Per ulteriori informazioni sulla configurazione e l'utilizzo della richiesta di reclutamento e della funzionalità candidato, vedi [Selezione dei candidati](hr-personnel-recruit.md).</span><span class="sxs-lookup"><span data-stu-id="f7b34-116">For more information about setting up and using the recruiting request and candidate functionality, see [Recruit job candidates](hr-personnel-recruit.md).</span></span>

## <a name="microsoft-dataverse"></a><span data-ttu-id="f7b34-117">Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="f7b34-117">Microsoft Dataverse</span></span>

<span data-ttu-id="f7b34-118">Questa API è creata su Microsoft Dataverse (in precedenza Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="f7b34-118">This API is built on Microsoft Dataverse (formerly Common Data Service).</span></span> <span data-ttu-id="f7b34-119">Tutta l'interazione RESTful con questa API viene eseguita tramite l'API Web Microsoft Dataverse, che utilizza OData.</span><span class="sxs-lookup"><span data-stu-id="f7b34-119">All RESTful interaction with this API is done via the Microsoft Dataverse Web API, which uses OData.</span></span> <span data-ttu-id="f7b34-120">Questa API è un sottoinsieme di API Web Dataverse.</span><span class="sxs-lookup"><span data-stu-id="f7b34-120">This API is a subset of the Dataverse Web API.</span></span> <span data-ttu-id="f7b34-121">L'API Web Dataverse definisce caratteristiche quali autenticazione, SLA, batch, controllo della concorrenza e gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="f7b34-121">The Dataverse Web API defines characteristics such as authentication, SLAs, batch, concurrency control, and error handling.</span></span>

<span data-ttu-id="f7b34-122">Per ulteriori informazioni generali sull'API Web Microsoft Dataverse, vedi:</span><span class="sxs-lookup"><span data-stu-id="f7b34-122">For more general information about the Microsoft Dataverse Web API, see:</span></span>

- [<span data-ttu-id="f7b34-123">Che cos'è Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="f7b34-123">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)
- [<span data-ttu-id="f7b34-124">Usa l'API Web Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="f7b34-124">Use the Microsoft Dataverse Web API</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)
- [<span data-ttu-id="f7b34-125">Guida per gli sviluppatori Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="f7b34-125">Microsoft Dataverse developer guide</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform)

<span data-ttu-id="f7b34-126">La documentazione di cui sopra include dettagli e indicazioni per sviluppatori sull'utilizzo dell'API Web Dataverse, ad esempio [gestione dell'autenticazione](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/authenticate-web-api), [esecuzione delle operazioni](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/perform-operations-web-api), [uso di Postman con l'API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/use-postman-web-api) e [uso del rilevamento delle modifiche o i token delta](https://docs.microsoft.com/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) con l'API.</span><span class="sxs-lookup"><span data-stu-id="f7b34-126">The above documentation includes detail and developer guidance on using the Dataverse Web API, such as [managing authentication](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/authenticate-web-api), [performing operations](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/perform-operations-web-api), [using Postman with the API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/use-postman-web-api), and [using change tracking or delta tokens](https://docs.microsoft.com/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) with the API.</span></span>

### <a name="option-sets"></a><span data-ttu-id="f7b34-127">Set di opzioni</span><span class="sxs-lookup"><span data-stu-id="f7b34-127">Option sets</span></span>

<span data-ttu-id="f7b34-128">Il modello di dati per l'API di integrazione ATS descritto in questo documento include set di opzioni che forniscono valori enumerati associati alle proprietà dell'entità.</span><span class="sxs-lookup"><span data-stu-id="f7b34-128">The data model for the ATS integration API described in this document includes option sets that provide enumerated values associated with entity properties.</span></span> <span data-ttu-id="f7b34-129">Per i dettagli su come lavorare con i set di opzioni nell'API Web Dataverse, vedi [Crea e aggiorna i set di opzioni utilizzando l'API Web](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets).</span><span class="sxs-lookup"><span data-stu-id="f7b34-129">For detail on working with option sets in the Dataverse Web API, see [Create and update option sets using the Web API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets).</span></span> <span data-ttu-id="f7b34-130">I set di opzioni sono definiti per ciascun ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="f7b34-130">Option sets are defined for each Dataverse environment.</span></span>

### <a name="virtual-tables-for-human-resources-in-dataverse"></a><span data-ttu-id="f7b34-131">Tabelle virtuali per Human Resources in Dataverse</span><span class="sxs-lookup"><span data-stu-id="f7b34-131">Virtual tables for Human Resources in Dataverse</span></span>

<span data-ttu-id="f7b34-132">Gli endpoint per l'API di integrazione ATS utilizzano le funzionalità della piattaforma di tabelle virtuali di Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="f7b34-132">The endpoints for the ATS integration API use the virtual table platform capabilities of Microsoft Dataverse.</span></span> <span data-ttu-id="f7b34-133">Per impostazione predefinita, le tabelle virtuali e gli endpoint API associati non vengono distribuiti per gli ambienti Human Resources, consentendo alle organizzazioni di determinare quali endpoint OData saranno esposti per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="f7b34-133">By default, the virtual tables and their associated API endpoints are not deployed for Human Resources environments, enabling organizations to determine which OData endpoints will be exposed for the environment.</span></span> <span data-ttu-id="f7b34-134">Per utilizzare l'API, le tabelle virtuali per le entità Human Resources devono essere generate per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="f7b34-134">To use the API, the virtual tables for the Human Resources entities must be generated for the environment.</span></span> 

<span data-ttu-id="f7b34-135">Per informazioni sulla generazione delle tabelle virtuali per l'API, vedi [Configura tabelle virtuali Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="f7b34-135">For information on generating the virtual tables for the API, see [Configure Dataverse virtual tables](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span></span>

## <a name="data-model"></a><span data-ttu-id="f7b34-136">Modello dati</span><span class="sxs-lookup"><span data-stu-id="f7b34-136">Data model</span></span>

<span data-ttu-id="f7b34-137">Il modello di dati è incentrato su due entità principali:</span><span class="sxs-lookup"><span data-stu-id="f7b34-137">The data model is centered around two main entities:</span></span>

- <span data-ttu-id="f7b34-138">**RecruitingRequest** rappresenta una richiesta a un ATS di reclutare per una o più posizioni aperte. Per una query di esempio, vedi [Query di esempio per richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-example-query.md).</span><span class="sxs-lookup"><span data-stu-id="f7b34-138">**RecruitingRequest** represents a request to an ATS to recruit for one or more open positions.For an example query, see [Example query for Recruiting request](hr-admin-integration-ats-api-recruiting-request-example-query.md).</span></span>
- <span data-ttu-id="f7b34-139">**CandidateToHire** rappresenta i dettagli di un candidato che ha accettato un'offerta per una posizione.</span><span class="sxs-lookup"><span data-stu-id="f7b34-139">**CandidateToHire** represents details of a candidate who has accepted an offer for a position.</span></span> <span data-ttu-id="f7b34-140">**Person** rappresenta l'individuo che è il candidato.</span><span class="sxs-lookup"><span data-stu-id="f7b34-140">**Person** represents the individual who is the candidate.</span></span> <span data-ttu-id="f7b34-141">Una persona può avere più ruoli nell'azienda, come candidato, lavoratore, dipendente o terzista.</span><span class="sxs-lookup"><span data-stu-id="f7b34-141">A person can have multiple roles in the company, such as candidate, worker, employee, or contractor.</span></span> <span data-ttu-id="f7b34-142">Per una query di esempio, vedi [Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).</span><span class="sxs-lookup"><span data-stu-id="f7b34-142">For an example query, see [Example query for Candidate to hire](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).</span></span>

<span data-ttu-id="f7b34-143">Nel diagramma riportato di seguito vengono illustrate le relazioni all'interno dell'API.</span><span class="sxs-lookup"><span data-stu-id="f7b34-143">The following diagram illustrates relationships within the API.</span></span> <span data-ttu-id="f7b34-144">Diversi tipi hanno chiavi esterne per altre entità preesistenti in Human Resources che non sono illustrate qui.</span><span class="sxs-lookup"><span data-stu-id="f7b34-144">Several types have foreign keys to other, pre-existing entities in Human Resources that aren't illustrated here.</span></span> <span data-ttu-id="f7b34-145">Questo documento fornisce informazioni sulle entità specifiche per gli scenari di integrazione della selezione.</span><span class="sxs-lookup"><span data-stu-id="f7b34-145">This document provides information on entities that are specific to recruiting integration scenarios.</span></span> <span data-ttu-id="f7b34-146">Tuttavia, ci sono molte altre entità nell'API Web Dataverse per Dynamics 365 Human Resources potrebbe anche essere rilevante per la tua integrazione.</span><span class="sxs-lookup"><span data-stu-id="f7b34-146">However, there are many other entities in the Dataverse Web API for Dynamics 365 Human Resources that may also be relevant to your integration.</span></span> <span data-ttu-id="f7b34-147">Ad esempio, potresti anche aver bisogno di dettagli per lavoratori, lavori, posizioni o altre entità non definite qui.</span><span class="sxs-lookup"><span data-stu-id="f7b34-147">For example, you may also need detail for workers, jobs, positions, or other entities not defined here.</span></span> <span data-ttu-id="f7b34-148">Molte di queste entità sono referenziate in relazioni di chiavi esterne o proprietà di navigazione.</span><span class="sxs-lookup"><span data-stu-id="f7b34-148">Many of these entities are referenced in foreign key relationships or navigation properties.</span></span>

![Modello di dati dell'API di integrazione ATS](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a><span data-ttu-id="f7b34-150">Richiesta di selezione ed entità correlate e set di opzioni</span><span class="sxs-lookup"><span data-stu-id="f7b34-150">Recruiting request and related entities and option sets</span></span>

<span data-ttu-id="f7b34-151">Query di esempio:</span><span class="sxs-lookup"><span data-stu-id="f7b34-151">Example query:</span></span> 

- [<span data-ttu-id="f7b34-152">Query di esempio per la richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="f7b34-152">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)

<span data-ttu-id="f7b34-153">Entità:</span><span class="sxs-lookup"><span data-stu-id="f7b34-153">Entities:</span></span>

- [<span data-ttu-id="f7b34-154">Richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="f7b34-154">Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request.md)
- [<span data-ttu-id="f7b34-155">Posizione richieste di selezione</span><span class="sxs-lookup"><span data-stu-id="f7b34-155">Recruiting request position</span></span>](hr-admin-integration-ats-api-recruiting-request-position.md)
- [<span data-ttu-id="f7b34-156">Competenza di richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="f7b34-156">Recruiting request skill</span></span>](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [<span data-ttu-id="f7b34-157">Istruzione richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="f7b34-157">Recruiting request education</span></span>](hr-admin-integration-ats-api-recruiting-request-education.md)
- [<span data-ttu-id="f7b34-158">Percorso richieste di selezione</span><span class="sxs-lookup"><span data-stu-id="f7b34-158">Recruiting request location</span></span>](hr-admin-integration-ats-api-recruiting-request-location.md)

<span data-ttu-id="f7b34-159">Set di opzioni:</span><span class="sxs-lookup"><span data-stu-id="f7b34-159">Option sets:</span></span>

- [<span data-ttu-id="f7b34-160">Stato esenzione mansione</span><span class="sxs-lookup"><span data-stu-id="f7b34-160">Job exempt status</span></span>](hr-admin-integration-ats-api-job-exempt-status.md)
- [<span data-ttu-id="f7b34-161">Stato della posizione della richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="f7b34-161">Recruiting request position status</span></span>](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [<span data-ttu-id="f7b34-162">Stato della richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="f7b34-162">Recruiting request status</span></span>](hr-admin-integration-ats-api-recruiting-request-status.md)
- [<span data-ttu-id="f7b34-163">Categoria di lavoro normativa</span><span class="sxs-lookup"><span data-stu-id="f7b34-163">Regulatory job category</span></span>](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a><span data-ttu-id="f7b34-164">Candidato da assumere ed entità correlate e set di opzioni</span><span class="sxs-lookup"><span data-stu-id="f7b34-164">Candidate to hire and related entities and option sets</span></span>

<span data-ttu-id="f7b34-165">Query di esempio:</span><span class="sxs-lookup"><span data-stu-id="f7b34-165">Example query:</span></span>

- [<span data-ttu-id="f7b34-166">Query di esempio per il candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="f7b34-166">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

<span data-ttu-id="f7b34-167">Entità:</span><span class="sxs-lookup"><span data-stu-id="f7b34-167">Entities:</span></span>

- [<span data-ttu-id="f7b34-168">Candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="f7b34-168">Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire.md)
- [<span data-ttu-id="f7b34-169">Persona</span><span class="sxs-lookup"><span data-stu-id="f7b34-169">Person</span></span>](hr-admin-integration-ats-api-person.md)
- [<span data-ttu-id="f7b34-170">Educazione della persona</span><span class="sxs-lookup"><span data-stu-id="f7b34-170">Person education</span></span>](hr-admin-integration-ats-api-person-education.md)
- [<span data-ttu-id="f7b34-171">Esperienza professionale persona</span><span class="sxs-lookup"><span data-stu-id="f7b34-171">Person professional experience</span></span>](hr-admin-integration-ats-api-person-professional-experience.md)
- [<span data-ttu-id="f7b34-172">Indirizzo della persona</span><span class="sxs-lookup"><span data-stu-id="f7b34-172">Person address</span></span>](hr-admin-integration-ats-api-person-address.md)
- [<span data-ttu-id="f7b34-173">Contatto parte</span><span class="sxs-lookup"><span data-stu-id="f7b34-173">Party contact</span></span>](hr-admin-integration-ats-api-party-contact.md)
- [<span data-ttu-id="f7b34-174">Competenza della persona</span><span class="sxs-lookup"><span data-stu-id="f7b34-174">Person skill</span></span>](hr-admin-integration-ats-api-person-skill.md)
- [<span data-ttu-id="f7b34-175">Livello di valutazione</span><span class="sxs-lookup"><span data-stu-id="f7b34-175">Rating level</span></span>](hr-admin-integration-ats-api-rating-level.md)
- [<span data-ttu-id="f7b34-176">Certificato della persona</span><span class="sxs-lookup"><span data-stu-id="f7b34-176">Person certificate</span></span>](hr-admin-integration-ats-api-person-certificate.md)
- [<span data-ttu-id="f7b34-177">Tipo di certificato</span><span class="sxs-lookup"><span data-stu-id="f7b34-177">Certificate type</span></span>](hr-admin-integration-ats-api-certificate-type.md)
- [<span data-ttu-id="f7b34-178">Screening persona</span><span class="sxs-lookup"><span data-stu-id="f7b34-178">Person screening</span></span>](hr-admin-integration-ats-api-person-screening.md)
- [<span data-ttu-id="f7b34-179">Tipi di screening</span><span class="sxs-lookup"><span data-stu-id="f7b34-179">Screening types</span></span>](hr-admin-integration-ats-api-screening-types.md)
- [<span data-ttu-id="f7b34-180">Numero di identificazione persona</span><span class="sxs-lookup"><span data-stu-id="f7b34-180">Person identification number</span></span>](hr-admin-integration-ats-api-person-identification-number.md)

<span data-ttu-id="f7b34-181">Set di opzioni:</span><span class="sxs-lookup"><span data-stu-id="f7b34-181">Option sets:</span></span>

- [<span data-ttu-id="f7b34-182">Risultati integrazione candidato</span><span class="sxs-lookup"><span data-stu-id="f7b34-182">Applicant integration result</span></span>](hr-admin-integration-ats-api-applicant-integration-result.md)
- [<span data-ttu-id="f7b34-183">Vuoto Sì No</span><span class="sxs-lookup"><span data-stu-id="f7b34-183">Blank Yes No</span></span>](hr-admin-integration-ats-api-blank-yes-no.md)
- [<span data-ttu-id="f7b34-184">Stato di completamento</span><span class="sxs-lookup"><span data-stu-id="f7b34-184">Completion status</span></span>](hr-admin-integration-ats-api-completion-status.md)
- [<span data-ttu-id="f7b34-185">Tipo di contatto</span><span class="sxs-lookup"><span data-stu-id="f7b34-185">Contact type</span></span>](hr-admin-integration-ats-api-contact-type.md)
- [<span data-ttu-id="f7b34-186">Base di credito per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="f7b34-186">Education credit basis</span></span>](hr-admin-integration-ats-api-education-credit-basis.md)
- [<span data-ttu-id="f7b34-187">Genere</span><span class="sxs-lookup"><span data-stu-id="f7b34-187">Gender</span></span>](hr-admin-integration-ats-api-gender.md)
- [<span data-ttu-id="f7b34-188">Stato civile</span><span class="sxs-lookup"><span data-stu-id="f7b34-188">Marital status</span></span>](hr-admin-integration-ats-api-marital-status.md)
- [<span data-ttu-id="f7b34-189">Mesi dell'anno</span><span class="sxs-lookup"><span data-stu-id="f7b34-189">Months of year</span></span>](hr-admin-integration-ats-api-months-of-year.md)
- [<span data-ttu-id="f7b34-190">No/Sì</span><span class="sxs-lookup"><span data-stu-id="f7b34-190">No Yes</span></span>](hr-admin-integration-ats-api-no-yes.md)
- [<span data-ttu-id="f7b34-191">Unità del periodo</span><span class="sxs-lookup"><span data-stu-id="f7b34-191">Period unit</span></span>](hr-admin-integration-ats-api-period-unit.md)
- [<span data-ttu-id="f7b34-192">Frequenza di screening</span><span class="sxs-lookup"><span data-stu-id="f7b34-192">Screening frequency</span></span>](hr-admin-integration-ats-api-screening-frequency.md)
- [<span data-ttu-id="f7b34-193">Frequenza di screening generata da</span><span class="sxs-lookup"><span data-stu-id="f7b34-193">Screening frequency generate from</span></span>](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [<span data-ttu-id="f7b34-194">Tipo di livello di competenza</span><span class="sxs-lookup"><span data-stu-id="f7b34-194">Skill level type</span></span>](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a><span data-ttu-id="f7b34-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7b34-195">See also</span></span>

[<span data-ttu-id="f7b34-196">Selezione dei candidati</span><span class="sxs-lookup"><span data-stu-id="f7b34-196">Recruit job candidates</span></span>](hr-personnel-recruit.md)<br>
[<span data-ttu-id="f7b34-197">Che cos'è Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="f7b34-197">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="f7b34-198">Usa l'API Web Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="f7b34-198">Use the Microsoft Dataverse Web API</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)<br>
[<span data-ttu-id="f7b34-199">Crea e aggiorna i set di opzioni utilizzando l'API Web</span><span class="sxs-lookup"><span data-stu-id="f7b34-199">Create and update option sets using the Web API</span></span>](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>