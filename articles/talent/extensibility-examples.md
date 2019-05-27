---
title: Estendere Talent utilizzando PowerApps e Microsoft Flow - Scenari di esempio
description: In questo argomento vengono descritti alcuni esempi di scenari di estendibilità per Microsoft Dynamics 365 for Talent che utilizzano Microsoft PowerApps e Microsoft Flow.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 for Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c113b0f4ab2c8e44d00fcfca3f0a6ca828a854ae
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518348"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a><span data-ttu-id="cf99e-103">Estendere Talent utilizzando PowerApps e Microsoft Flow - Scenari di esempio</span><span class="sxs-lookup"><span data-stu-id="cf99e-103">Extend Talent by using PowerApps and Microsoft Flow - Example scenarios</span></span>

<span data-ttu-id="cf99e-104">In questo argomento vengono descritti alcuni esempi di scenari di estendibilità per Microsoft Dynamics 365 for Talent che utilizzano Microsoft PowerApps e Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="cf99e-104">This topic describes some examples of extensibility scenarios for Microsoft Dynamics 365 for Talent that use Microsoft PowerApps and Microsoft Flow.</span></span> <span data-ttu-id="cf99e-105">È possibile importare il pacchetto di soluzioni associato a ogni esempio nell'ambiente di PowerApps.</span><span class="sxs-lookup"><span data-stu-id="cf99e-105">You can import the solution package that is associated with each example into your PowerApps environment.</span></span> <span data-ttu-id="cf99e-106">È quindi possibile utilizzare i pacchetti come riferimento o punto di partenza per implementare scenari applicabili all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf99e-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf99e-107">Se si desidera utilizzare i modelli e l'app descritti in questo argomento "così come sono", testarli per assicurarsi che coprano tutti gli scenari specifici dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="cf99e-107">If you want to use the templates and app that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="cf99e-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cf99e-108">Prerequisites</span></span>

- <span data-ttu-id="cf99e-109">Per importare pacchetti, gli utenti devono disporre dell'autorizzazione **Creazione ambiente**.</span><span class="sxs-lookup"><span data-stu-id="cf99e-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="cf99e-110">Per esportare o importare app, gli utenti devono disporre di una licenza di PowerApps Piano 2 o una licenza di valutazione di PowerApps Piano 2.</span><span class="sxs-lookup"><span data-stu-id="cf99e-110">To export or import apps, users must have a PowerApps Plan 2 license or a PowerApps Plan 2 trial license.</span></span>

## <a name="flow--form-connect"></a><span data-ttu-id="cf99e-111">Flusso – Connessione a modulo</span><span class="sxs-lookup"><span data-stu-id="cf99e-111">Flow – Form Connect</span></span>

<span data-ttu-id="cf99e-112">Il modello **Flusso – Connessione a modulo** può essere utilizzato per leggere i dati in Microsoft Forms e archiviarli in un'entità Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="cf99e-112">The **Flow – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="cf99e-113">Questo modello può essere esteso in modo da poterlo utilizzare per altri scenari.</span><span class="sxs-lookup"><span data-stu-id="cf99e-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="cf99e-114">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="cf99e-114">Here are some examples:</span></span>

- <span data-ttu-id="cf99e-115">Acquisire valutazioni di candidati.</span><span class="sxs-lookup"><span data-stu-id="cf99e-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="cf99e-116">Acquisire risultati da questionari di corsi.</span><span class="sxs-lookup"><span data-stu-id="cf99e-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="cf99e-117">Compilare una libreria di domande di colloqui per gli amministratori delle Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="cf99e-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="cf99e-118">Acquisire la valutazione del colloquio di un candidato</span><span class="sxs-lookup"><span data-stu-id="cf99e-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="cf99e-119">In Microsoft Dynamics 365: Attract, i moduli possono essere visualizzati nel portale Candidato e i candidati possono immettere i dettagli.</span><span class="sxs-lookup"><span data-stu-id="cf99e-119">In Microsoft Dynamics 365: Attract, forms can appear in Candidate portal, and candidates can fill in details.</span></span> <span data-ttu-id="cf99e-120">I moduli possono anche essere incorporati come attività in un modello posizioni lavorative.</span><span class="sxs-lookup"><span data-stu-id="cf99e-120">Forms can also be embedded as activities in a job template.</span></span>

<span data-ttu-id="cf99e-121">Quando un candidato invia un modulo, Microsoft Flow lo acquisisce, legge i dati e li archivia nell'entità Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="cf99e-121">When a candidate submits a form, Microsoft Flow captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="cf99e-122">Per scaricare il modello **Flusso – Connessione a modulo** e Custom Entity Structure, andare a [Flusso – Connessione a modulo](https://go.microsoft.com/fwlink/?linkid=2081988) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf99e-122">To download the **Flow – Form Connect** template and Custom Entity Structure, go to [Flow – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a><span data-ttu-id="cf99e-123">Iniziare ed estrarre parametri passati a PowerApps</span><span class="sxs-lookup"><span data-stu-id="cf99e-123">Initiate and Extract Parameters Passed to Powerapps</span></span>

<span data-ttu-id="cf99e-124">Il modello **Iniziare ed estrarre parametri passati a PowerApps** può essere utilizzato come punto di partenza per qualsiasi scenario di PowerApps specifico di Attract.</span><span class="sxs-lookup"><span data-stu-id="cf99e-124">The **Initiate and Extract Parameters Passed to Powerapps** template can be used as a starting point for any PowerApps scenario that is specific to Attract.</span></span> <span data-ttu-id="cf99e-125">Include tutti i parametri predefiniti passati da Attract, come **Domanda di lavoro**, **ID candidato** e **JobID**.</span><span class="sxs-lookup"><span data-stu-id="cf99e-125">It includes all the default parameters that are passed by Attract, such as **Job Application**, **Candidate ID**, and **JobID**.</span></span>

<span data-ttu-id="cf99e-126">Questo modello può essere utilizzato per recuperare un modulo di valutazione dei candidati, di modo che un responsabile delle assunzioni possa visualizzare la valutazione di un candidato.</span><span class="sxs-lookup"><span data-stu-id="cf99e-126">This template can be used to retrieve a candidate assessment form, so that a hiring manager can view the assessment that a candidate filled in.</span></span>

<span data-ttu-id="cf99e-127">Le app create tramite PowerApps possono essere incorporate nel modello posizioni lavorative in Attract.</span><span class="sxs-lookup"><span data-stu-id="cf99e-127">Apps that are created by using PowerApps can be embedded into the job template in Attract.</span></span>

<span data-ttu-id="cf99e-128">Per scaricare il modello **Iniziare ed estrarre parametri passati a PowerApps** e Custom Entity Structure, andare a [Iniziare ed estrarre parametri passati a PowerApps](https://go.microsoft.com/fwlink/?linkid=2081991) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf99e-128">To download the **Initiate and Extract Parameters Passed to Powerapps** template and Custom Entity Structure, go to [Initiate and Extract Parameters Passed to Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) on the Microsoft Download Center.</span></span>

## <a name="integration-with-office-365"></a><span data-ttu-id="cf99e-129">Integration with Office 365</span><span class="sxs-lookup"><span data-stu-id="cf99e-129">Integration with Office 365</span></span>

<span data-ttu-id="cf99e-130">L'app **Integration with Office 365** può essere utilizzata per estrarre informazioni sui team per gli utenti registrati da Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="cf99e-130">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="cf99e-131">Questa app fa riferimento ai lavoratori in Talent per estrarre informazioni relative all'ora di entrata e all'ora di uscita e registrazioni delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="cf99e-131">It references workers in Talent to extract clock-in and clock-out details and exception recordings.</span></span> <span data-ttu-id="cf99e-132">Le informazioni sull'ora di entrata e quella di uscita sono archiviate nelle entità Common Data Service personalizzate.</span><span class="sxs-lookup"><span data-stu-id="cf99e-132">Clock-in and Clock-out details are stored in custom Common Data Service entities.</span></span> <span data-ttu-id="cf99e-133">Si presuppone che queste informazioni siano immesse da sistemi di terze parti via l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="cf99e-133">The assumption is that these details are filled in from third-party systems via integration.</span></span>

<span data-ttu-id="cf99e-134">Questa app può essere estesa in modo da essere utilizzata per altri scenari.</span><span class="sxs-lookup"><span data-stu-id="cf99e-134">This app can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="cf99e-135">Ad esempio, per visualizzare informazioni sulle ferie del team, eventi di calendario e qualsiasi evento specifico del team.</span><span class="sxs-lookup"><span data-stu-id="cf99e-135">For example, it can be used to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="cf99e-136">Per scaricare l'app **Integration with Office 365** e Custome Entity Structure, andare a [Integrazione con Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf99e-136">To download the **Integration with Office 365** app and Custome Entity Structure, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="flow--email-notification"></a><span data-ttu-id="cf99e-137">Flusso – Notifica tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="cf99e-137">Flow – Email Notification</span></span>

<span data-ttu-id="cf99e-138">Il modello **Flusso – Notifica tramite posta elettronica** può essere utilizzato per scenari di notifica tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="cf99e-138">The **Flow – Email Notification** template can be used for email notification scenarios.</span></span> <span data-ttu-id="cf99e-139">Può essere utilizzato per inviare messaggi di posta elettronica di notifica a candidati che il team di assunzione non seleziona durante una qualsiasi fase del processo di selezione.</span><span class="sxs-lookup"><span data-stu-id="cf99e-139">It can be used to trigger notification emails to candidates that the hiring team rejects during any stage of the recruiting process.</span></span>

<span data-ttu-id="cf99e-140">Questo modello può essere esteso per tenere traccia delle modifiche alla fase di candidatura durante il processo di selezione e per inviare notifiche al team di assunzione e al candidato.</span><span class="sxs-lookup"><span data-stu-id="cf99e-140">This template can be extended to track changes to the candidate stage throughout the recruiting process, and to send notifications to the hiring team and candidate.</span></span>

<span data-ttu-id="cf99e-141">In genere per le entità archiviate in Common Data Service, i flussi possono essere configurati per inviare notifiche per eventi che si verificano in Core HR, Attract o Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="cf99e-141">In general, for entities that are stored in Common Data Service, flows can be set up to send notifications for events that occur in Core HR, Attract, or Dynamics 365 Talent: Onboard.</span></span>

<span data-ttu-id="cf99e-142">Per scaricare il modello **Flusso – Notifica tramite posta elettronica**, andare a [Flusso – Notifica tramite posta elettronica](https://go.microsoft.com/fwlink/?linkid=2082103) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf99e-142">To download the **Flow – Email Notification** template, go to [Flow – Email Notification](https://go.microsoft.com/fwlink/?linkid=2082103) on the Microsoft Download Center.</span></span>

## <a name="flow--sql-connect-and-execute"></a><span data-ttu-id="cf99e-143">Flusso – Connessione a SQL ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="cf99e-143">Flow – SQL Connect and execute</span></span>

<span data-ttu-id="cf99e-144">Il modello **Flusso – Connessione a SQL ed esecuzione** esegue la connessione a Microsoft SQL Server e consente l'esecuzione delle query SQL.</span><span class="sxs-lookup"><span data-stu-id="cf99e-144">The **Flow – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="cf99e-145">Sebbene questo modello sia progettato per leggere e aggiornare le tabelle SQL, può essere esteso in modo da essere utilizzato per altri scenari.</span><span class="sxs-lookup"><span data-stu-id="cf99e-145">Although this template is designed to read and update SQL tables, it can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="cf99e-146">Ad esempio, per compilare una tabella di gestione temporanea in Common Data Service con record di SQL Server e per sincronizzarla periodicamente utilizzando un push incrementale di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cf99e-146">For example, it can be used to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="cf99e-147">Per scaricare il modello **Flusso – Connessione a SQL ed esecuzione** e Custom Entity Structure, andare a [Flusso – Connessione a SQL ed esecuzione](https://go.microsoft.com/fwlink/?linkid=2081789) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf99e-147">To download the **Flow – SQL Connect and execute** template, go to [Flow – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="flow--sharepoint-integration"></a><span data-ttu-id="cf99e-148">Flusso – Integrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="cf99e-148">Flow – SharePoint Integration</span></span>

<span data-ttu-id="cf99e-149">Il modello **Flusso – Integrazione di SharePoint** può essere utilizzato per leggere dati in un elenco di Microsoft SharePoint, confrontare l'elenco con valori di campi per qualsiasi entità Common Data Service e inviare i risultati del confronto in forma di messaggio di posta elettronica di notifica.</span><span class="sxs-lookup"><span data-stu-id="cf99e-149">The **Flow – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="cf99e-150">Un'organizzazione potrebbe avere un insieme di competenze che richiede urgentemente.</span><span class="sxs-lookup"><span data-stu-id="cf99e-150">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="cf99e-151">Queste competenze possono essere archiviate in SharePoint come elenco di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cf99e-151">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="cf99e-152">Quando un candidato si candida a una mansione per la quale è elencato un insieme di competenze, se è presente una corrispondenza significativa tra le competenze del candidato e quelle archiviate in SharePoint, viene inviato un messaggio di posta elettronica di notifica.</span><span class="sxs-lookup"><span data-stu-id="cf99e-152">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="cf99e-153">In questo modo, le posizioni urgenti vengono coperte più rapidamente in quanto le notifiche consentono ai selezionatori di contattare e assumere i candidati nell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf99e-153">In this way, positions that are urgently required are filled faster, because the notifications help recruiters reach out and cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="cf99e-154">Questo modello può essere esteso di modo che sia possibile utilizzarlo per qualsiasi scenario che comporta l'integrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cf99e-154">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="cf99e-155">Per scaricare il modello **Flusso – Integrazione di SharePoint**, andare a [Flusso – Integrazione di SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf99e-155">To download the **Flow – SharePoint Integration** template, go to [Flow – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="admin-console-to-manage-talent-pools"></a><span data-ttu-id="cf99e-156">Console di amministrazione per gestire i pool di talenti</span><span class="sxs-lookup"><span data-stu-id="cf99e-156">Admin console to manage talent pools</span></span>

<span data-ttu-id="cf99e-157">Quando si abilita l'integrazione con LinkedIn, Attract crea automaticamente un pool di talenti su LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="cf99e-157">When you enable integration with LinkedIn, Attract automatically createas a LinkedIn talent pool.</span></span> <span data-ttu-id="cf99e-158">Quando un selezionatore scambia InMail con un candidato tramite LinkedIn, Attract crea un profilo per il candidato e il candidato diventa un membro del pool di talenti di LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="cf99e-158">When a recruiter exchanges InMail with a recruit through LinkedIn, Attract creates a profile for the recruit, and the recruit becomes a member of the LinkedIn talent pool.</span></span> <span data-ttu-id="cf99e-159">Questa app PowerApps è utile per riorganizzare i candidati nei pool di talenti in base alle competenze.</span><span class="sxs-lookup"><span data-stu-id="cf99e-159">This PowerApps app is useful for reorganizing candidates in talent pools based on skill.</span></span>

<span data-ttu-id="cf99e-160">Eseguire questa app PowerApps come console di amministrazione per eseguire le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="cf99e-160">Run this PowerApps app as an admin console to perform the following tasks:</span></span>

- <span data-ttu-id="cf99e-161">Elencare i candidati in un pool di talenti</span><span class="sxs-lookup"><span data-stu-id="cf99e-161">List candidates in a talent pool</span></span>
- <span data-ttu-id="cf99e-162">Aggiungere e rimuovere candidati da un pool di talenti</span><span class="sxs-lookup"><span data-stu-id="cf99e-162">Add and remove candidates from a talent pool</span></span>
- <span data-ttu-id="cf99e-163">Spostare i candidati da un pool di talenti a un altro</span><span class="sxs-lookup"><span data-stu-id="cf99e-163">Move candidates from one talent pool to another</span></span>
- <span data-ttu-id="cf99e-164">Determinare se i candidati fanno già parte di un pool di talenti prima di spostarli</span><span class="sxs-lookup"><span data-stu-id="cf99e-164">Determine whether candidates are already part of a talent pool before moving them</span></span>
- <span data-ttu-id="cf99e-165">Verificare le competenze dei candidati prima di spostarli in altri pool di talenti</span><span class="sxs-lookup"><span data-stu-id="cf99e-165">Check the skills of candidates before moving them to other talent pools</span></span>

<span data-ttu-id="cf99e-166">Questa app di PowerApps utilizza relazioni molti-a-molti, quindi è possibile utilizzarla come modello per altri scenari in cui è necessario estrarre record con relazioni molti-a-molti.</span><span class="sxs-lookup"><span data-stu-id="cf99e-166">This PowerApps app uses many-to-many relationships, so you can use it as a template for other scenarios where you need to extract records that have many-to-many relationships.</span></span>

<span data-ttu-id="cf99e-167">Per scaricare il modello **Console di amministrazione per gestire i pool di talenti**, andare a [Console di amministrazione per gestire i pool di talenti](http://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf99e-167">To download the **Admin console to manage talent pools** template,  go to [Admin console to manage talent pools](http://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) on the Microsoft Download Center.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cf99e-168">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="cf99e-168">Additional resources</span></span>

[<span data-ttu-id="cf99e-169">Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="cf99e-169">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[<span data-ttu-id="cf99e-170">Migrare app tra tenant e ambienti</span><span class="sxs-lookup"><span data-stu-id="cf99e-170">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/en-us/power-platform/admin/environment-and-tenant-migration)
