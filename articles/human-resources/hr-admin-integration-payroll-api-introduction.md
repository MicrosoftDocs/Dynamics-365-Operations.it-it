---
title: Introduzione all'API di integrazione retribuzioni
description: Questo argomento descrive l'API di integrazione retribuzioni di Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6d8a1cb9619a863184460a74e472af3f06934b6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058562"
---
# <a name="payroll-integration-api-introduction"></a><span data-ttu-id="cb3a4-103">Introduzione all'API di integrazione retribuzioni</span><span class="sxs-lookup"><span data-stu-id="cb3a4-103">Payroll integration API introduction</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="cb3a4-104">Questo documento descrive l'API di integrazione retribuzioni di Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-104">This document describes the Dynamics 365 Human Resources Payroll integration API.</span></span> <span data-ttu-id="cb3a4-105">L'API consente integrazioni end-to-end ottimizzate tra Human Resources e i sistemi di gestione delle retribuzioni dei partner.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-105">The API enables streamlined end-to-end integrations between Human Resources and partnering payroll systems.</span></span> <span data-ttu-id="cb3a4-106">L'esperienza integrata inizia in Human Resources con il profilo del dipendente, lo stipendio e le detrazioni e le informazioni sui contributi.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-106">The integrated experience begins in Human Resources with the employee profile, salary and deduction, and contribution information.</span></span> <span data-ttu-id="cb3a4-107">Quando si assume un dipendente e si immettono il profilo richiesto e le informazioni sulla retribuzione in Human Resources, il sistema delle retribuzioni estrae queste informazioni per utilizzarle durante l'elaborazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-107">When you hire an employee and enter the required profile and pay information into Human Resources, the payroll system pulls this information to use when processing payroll.</span></span> <span data-ttu-id="cb3a4-108">Anche gli eventuali aggiornamenti alle informazioni sul dipendente o sulle retribuzioni vengono estratti per essere utilizzati nei cicli di pagamenti successivi.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-108">Any updates made to the employee or pay information are also pulled for use in later pay runs.</span></span>

![Flusso di integrazione delle retribuzioni](media/hr-admin-integration-payroll-api-introduction-flow.png)

<span data-ttu-id="cb3a4-110">Per abilitare l'integrazione, Human Resources include i seguenti componenti:</span><span class="sxs-lookup"><span data-stu-id="cb3a4-110">To enable the integration, Human Resources includes the following components:</span></span>

- <span data-ttu-id="cb3a4-111">Funzionalità per contrassegnare un dipendente come Pronto per il pagamento</span><span class="sxs-lookup"><span data-stu-id="cb3a4-111">Functionality to mark an employee as ready to pay</span></span>
- <span data-ttu-id="cb3a4-112">Un'API di integrazione che apre le nuove funzionalità alle applicazioni di integrazione</span><span class="sxs-lookup"><span data-stu-id="cb3a4-112">An integration API opening up the new functionality to integrating applications</span></span>

## <a name="microsoft-dataverse"></a><span data-ttu-id="cb3a4-113">Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="cb3a4-113">Microsoft Dataverse</span></span>

<span data-ttu-id="cb3a4-114">Questa API è creata su Microsoft Dataverse (in precedenza Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="cb3a4-114">This API is built on Microsoft Dataverse (formerly Common Data Service).</span></span> <span data-ttu-id="cb3a4-115">Tutta l'interazione RESTful con questa API viene eseguita tramite l'API Web Microsoft Dataverse, che utilizza OData.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-115">All RESTful interaction with this API is done via the Microsoft Dataverse Web API, which uses OData.</span></span> <span data-ttu-id="cb3a4-116">Questa API è un sottoinsieme di API Web Dataverse.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-116">This API is a subset of the Dataverse Web API.</span></span> <span data-ttu-id="cb3a4-117">L'API Web Dataverse definisce caratteristiche quali autenticazione, SLA, batch, controllo della concorrenza e gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-117">The Dataverse Web API defines characteristics such as authentication, SLAs, batch, concurrency control, and error handling.</span></span>

<span data-ttu-id="cb3a4-118">Per ulteriori informazioni generali sull'API Web Microsoft Dataverse, vedi:</span><span class="sxs-lookup"><span data-stu-id="cb3a4-118">For more general information about the Microsoft Dataverse Web API, see:</span></span>

- [<span data-ttu-id="cb3a4-119">Che cos'è Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="cb3a4-119">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)
- [<span data-ttu-id="cb3a4-120">Usa l'API Web Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="cb3a4-120">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)
- [<span data-ttu-id="cb3a4-121">Guida per gli sviluppatori Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="cb3a4-121">Microsoft Dataverse developer guide</span></span>](/powerapps/developer/data-platform)

<span data-ttu-id="cb3a4-122">Questa documentazione include dettagli e indicazioni per sviluppatori per l'utilizzo dell'API web di Dataverse, inclusi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="cb3a4-122">This documentation includes details and developer guidance for using the Dataverse Web API, including the following topics:</span></span>

- [<span data-ttu-id="cb3a4-123">Autenticare in Microsoft Dataverse con l'API Web</span><span class="sxs-lookup"><span data-stu-id="cb3a4-123">Authenticate to Microsoft Dataverse with the Web API</span></span>](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [<span data-ttu-id="cb3a4-124">Eseguire operazioni utilizzando l'API Web</span><span class="sxs-lookup"><span data-stu-id="cb3a4-124">Perform operations using the Web API</span></span>](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [<span data-ttu-id="cb3a4-125">Usare Postman con l'API Web</span><span class="sxs-lookup"><span data-stu-id="cb3a4-125">Use Postman with the Web API</span></span>](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [<span data-ttu-id="cb3a4-126">Utilizzare il rilevamento delle modifiche per sincronizzare i dati con sistemi esterni</span><span class="sxs-lookup"><span data-stu-id="cb3a4-126">Use change tracking to synchronize data with external systems</span></span>](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a><span data-ttu-id="cb3a4-127">Tabelle virtuali per Human Resources in Dataverse</span><span class="sxs-lookup"><span data-stu-id="cb3a4-127">Virtual tables for Human Resources in Dataverse</span></span>

<span data-ttu-id="cb3a4-128">Gli endpoint per l'API di integrazione retribuzioni utilizzano le funzionalità della piattaforma di tabelle virtuali di Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-128">The endpoints for the Payroll integration API use the virtual table platform capabilities of Microsoft Dataverse.</span></span> <span data-ttu-id="cb3a4-129">Per impostazione predefinita, le tabelle virtuali e gli endpoint API associati non vengono distribuiti per gli ambienti Human Resources, consentendo alle organizzazioni di determinare quali endpoint OData saranno esposti per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-129">By default, the virtual tables and their associated API endpoints aren't deployed for Human Resources environments, enabling organizations to determine which OData endpoints will be exposed for the environment.</span></span> <span data-ttu-id="cb3a4-130">Per utilizzare l'API, le tabelle virtuali per le entità Human Resources devono essere generate per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-130">To use the API, the virtual tables for the Human Resources entities must be generated for the environment.</span></span>

<span data-ttu-id="cb3a4-131">Per informazioni sulla generazione delle tabelle virtuali per l'API, vedi [Configura tabelle virtuali Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).</span><span class="sxs-lookup"><span data-stu-id="cb3a4-131">For information on generating the virtual tables for the API, see [Configure Dataverse virtual tables](./hr-admin-integration-common-data-service-virtual-entities.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="cb3a4-132">Modello dati</span><span class="sxs-lookup"><span data-stu-id="cb3a4-132">Data model</span></span>

<span data-ttu-id="cb3a4-133">Nel diagramma riportato di seguito vengono illustrate le relazioni all'interno dell'API.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-133">The following diagram illustrates relationships within the API.</span></span> <span data-ttu-id="cb3a4-134">Diversi tipi hanno chiavi esterne per altre entità preesistenti in Human Resources che non sono illustrate qui.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-134">Several types have foreign keys to other, pre-existing entities in Human Resources that aren't illustrated here.</span></span> <span data-ttu-id="cb3a4-135">Questo documento fornisce informazioni sulle entità specifiche per gli scenari di integrazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-135">This document provides information on entities that are specific to payroll integration scenarios.</span></span> <span data-ttu-id="cb3a4-136">Tuttavia, ci sono molte altre entità nell'API Web di Dataverse per Human Resources potrebbe anche essere rilevante per la tua integrazione.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-136">However, there are many other entities in the Dataverse Web API for Human Resources that may also be relevant to your integration.</span></span> <span data-ttu-id="cb3a4-137">Alcune di queste entità sono referenziate in relazioni di chiavi esterne o proprietà di navigazione.</span><span class="sxs-lookup"><span data-stu-id="cb3a4-137">Some of these entities are referenced in foreign key relationships or navigation properties.</span></span>

![Modello di dati dell'API di integrazione retribuzioni](media/hr-admin-payroll-api-data-model.png)

## <a name="payroll-employee-and-related-entities"></a><span data-ttu-id="cb3a4-139">Dipendente retribuzioni e entità correlate</span><span class="sxs-lookup"><span data-stu-id="cb3a4-139">Payroll employee and related entities</span></span>

<span data-ttu-id="cb3a4-140">Entità:</span><span class="sxs-lookup"><span data-stu-id="cb3a4-140">Entities:</span></span>

- [<span data-ttu-id="cb3a4-141">Dipendente retribuzioni</span><span class="sxs-lookup"><span data-stu-id="cb3a4-141">Payroll employee</span></span>](hr-admin-integration-payroll-api-payroll-employee.md)
- [<span data-ttu-id="cb3a4-142">Indirizzo lavoratore retribuzioni</span><span class="sxs-lookup"><span data-stu-id="cb3a4-142">Payroll worker address</span></span>](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [<span data-ttu-id="cb3a4-143">Piano di retribuzione fissa retribuzioni</span><span class="sxs-lookup"><span data-stu-id="cb3a4-143">Payroll fixed compensation plan</span></span>](hr-admin-integration-ats-api-recruiting-request-education.md)
- [<span data-ttu-id="cb3a4-144">Mansione posizione di retribuzione</span><span class="sxs-lookup"><span data-stu-id="cb3a4-144">Payroll position job</span></span>](hr-admin-integration-payroll-api-payroll-position-job.md)
- [<span data-ttu-id="cb3a4-145">Posizione di retribuzione</span><span class="sxs-lookup"><span data-stu-id="cb3a4-145">Payroll position</span></span>](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a><span data-ttu-id="cb3a4-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb3a4-146">See also</span></span>

[<span data-ttu-id="cb3a4-147">Generare ed esaminare le entità retribuzioni</span><span class="sxs-lookup"><span data-stu-id="cb3a4-147">Generate and review payroll entities</span></span>](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[<span data-ttu-id="cb3a4-148">Configurare i parametri di Human Resources</span><span class="sxs-lookup"><span data-stu-id="cb3a4-148">Configure Human Resources parameters</span></span>](hr-setup-parameters.md)<br>
[<span data-ttu-id="cb3a4-149">Configurare i parametri condivisi di Human Resources</span><span class="sxs-lookup"><span data-stu-id="cb3a4-149">Configure Human Resources shared parameters</span></span>](hr-setup-shared-parameters.md)<br>
[<span data-ttu-id="cb3a4-150">Che cos'è Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="cb3a4-150">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="cb3a4-151">Usa l'API Web Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="cb3a4-151">Use the Microsoft Dataverse Web API</span></span>](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]