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
ms.openlocfilehash: 0b455a8194f58b41a349f004ceda8183c7ee3f7c
ms.sourcegitcommit: 9f94eff93d29bc27352569824e00bbccc2f961b8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2019
ms.locfileid: "1781444"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a><span data-ttu-id="1c4aa-103">Estendere Talent utilizzando PowerApps e Microsoft Flow - Scenari di esempio</span><span class="sxs-lookup"><span data-stu-id="1c4aa-103">Extend Talent by using PowerApps and Microsoft Flow - Example scenarios</span></span>

<span data-ttu-id="1c4aa-104">In questo argomento vengono descritti alcuni esempi di scenari di estendibilità per Microsoft Dynamics 365 for Talent che utilizzano Microsoft PowerApps e Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-104">This topic describes some examples of extensibility scenarios for Microsoft Dynamics 365 for Talent that use Microsoft PowerApps and Microsoft Flow.</span></span> <span data-ttu-id="1c4aa-105">È possibile importare il pacchetto di soluzioni associato a ogni esempio nell'ambiente di PowerApps.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-105">You can import the solution package that is associated with each example into your PowerApps environment.</span></span> <span data-ttu-id="1c4aa-106">È quindi possibile utilizzare i pacchetti come riferimento o punto di partenza per implementare scenari applicabili all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c4aa-107">Se si desidera utilizzare i modelli e l'app descritti in questo argomento "così come sono", testarli per assicurarsi che coprano tutti gli scenari specifici dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-107">If you want to use the templates and app that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="1c4aa-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1c4aa-108">Prerequisites</span></span>

- <span data-ttu-id="1c4aa-109">Per importare pacchetti, gli utenti devono disporre dell'autorizzazione **Creazione ambiente**.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="1c4aa-110">Per esportare o importare app, gli utenti devono disporre di una licenza di PowerApps Piano 2 o una licenza di valutazione di PowerApps Piano 2.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-110">To export or import apps, users must have a PowerApps Plan 2 license or a PowerApps Plan 2 trial license.</span></span>

## <a name="flow--form-connect"></a><span data-ttu-id="1c4aa-111">Flusso – Connessione a modulo</span><span class="sxs-lookup"><span data-stu-id="1c4aa-111">Flow – Form Connect</span></span>

<span data-ttu-id="1c4aa-112">Il modello **Flusso – Connessione a modulo** può essere utilizzato per leggere i dati in Microsoft Forms e archiviarli in un'entità Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-112">The **Flow – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="1c4aa-113">Questo modello può essere esteso in modo da poterlo utilizzare per altri scenari.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="1c4aa-114">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-114">Here are some examples:</span></span>

- <span data-ttu-id="1c4aa-115">Acquisire valutazioni di candidati.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="1c4aa-116">Acquisire risultati da questionari di corsi.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="1c4aa-117">Compilare una libreria di domande di colloqui per gli amministratori delle Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="1c4aa-118">Acquisire la valutazione del colloquio di un candidato</span><span class="sxs-lookup"><span data-stu-id="1c4aa-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="1c4aa-119">In Microsoft Dynamics 365: Attract, i moduli possono essere visualizzati nel portale Candidato e i candidati possono immettere i dettagli.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-119">In Microsoft Dynamics 365: Attract, forms can appear in Candidate portal, and candidates can fill in details.</span></span> <span data-ttu-id="1c4aa-120">I moduli possono anche essere incorporati come attività in un modello posizioni lavorative.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-120">Forms can also be embedded as activities in a job template.</span></span>

<span data-ttu-id="1c4aa-121">Quando un candidato invia un modulo, Microsoft Flow lo acquisisce, legge i dati e li archivia nell'entità Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-121">When a candidate submits a form, Microsoft Flow captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="1c4aa-122">Per scaricare il modello **Flusso – Connessione a modulo** e Custom Entity Structure, andare a [Flusso – Connessione a modulo](https://go.microsoft.com/fwlink/?linkid=2081988) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-122">To download the **Flow – Form Connect** template and Custom Entity Structure, go to [Flow – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a><span data-ttu-id="1c4aa-123">Iniziare ed estrarre parametri passati a PowerApps</span><span class="sxs-lookup"><span data-stu-id="1c4aa-123">Initiate and Extract Parameters Passed to Powerapps</span></span>

<span data-ttu-id="1c4aa-124">Il modello **Iniziare ed estrarre parametri passati a PowerApps** può essere utilizzato come punto di partenza per qualsiasi scenario di PowerApps specifico di Attract.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-124">The **Initiate and Extract Parameters Passed to Powerapps** template can be used as a starting point for any PowerApps scenario that is specific to Attract.</span></span> <span data-ttu-id="1c4aa-125">Include tutti i parametri predefiniti passati da Attract, come **Domanda di lavoro**, **ID candidato** e **JobID**.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-125">It includes all the default parameters that are passed by Attract, such as **Job Application**, **Candidate ID**, and **JobID**.</span></span>

<span data-ttu-id="1c4aa-126">Questo modello può essere utilizzato per recuperare un modulo di valutazione dei candidati, di modo che un responsabile delle assunzioni possa visualizzare la valutazione di un candidato.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-126">This template can be used to retrieve a candidate assessment form, so that a hiring manager can view the assessment that a candidate filled in.</span></span>

<span data-ttu-id="1c4aa-127">Le app create tramite PowerApps possono essere incorporate nel modello posizioni lavorative in Attract.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-127">Apps that are created by using PowerApps can be embedded into the job template in Attract.</span></span>

<span data-ttu-id="1c4aa-128">Per scaricare il modello **Iniziare ed estrarre parametri passati a PowerApps** e Custom Entity Structure, andare a [Iniziare ed estrarre parametri passati a PowerApps](https://go.microsoft.com/fwlink/?linkid=2081991) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-128">To download the **Initiate and Extract Parameters Passed to Powerapps** template and Custom Entity Structure, go to [Initiate and Extract Parameters Passed to Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) on the Microsoft Download Center.</span></span>

## <a name="integration-with-office-365"></a><span data-ttu-id="1c4aa-129">Integration with Office 365</span><span class="sxs-lookup"><span data-stu-id="1c4aa-129">Integration with Office 365</span></span>

<span data-ttu-id="1c4aa-130">L'app **Integration with Office 365** può essere utilizzata per estrarre informazioni sui team per gli utenti registrati da Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-130">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="1c4aa-131">Questa app fa riferimento ai lavoratori in Talent per estrarre informazioni relative all'ora di entrata e all'ora di uscita e registrazioni delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-131">It references workers in Talent to extract clock-in and clock-out details and exception recordings.</span></span> <span data-ttu-id="1c4aa-132">Le informazioni sull'ora di entrata e quella di uscita sono archiviate nelle entità Common Data Service personalizzate.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-132">Clock-in and Clock-out details are stored in custom Common Data Service entities.</span></span> <span data-ttu-id="1c4aa-133">Si presuppone che queste informazioni siano immesse da sistemi di terze parti via l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-133">The assumption is that these details are filled in from third-party systems via integration.</span></span>

<span data-ttu-id="1c4aa-134">Questa app può essere estesa in modo da essere utilizzata per altri scenari.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-134">This app can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="1c4aa-135">Ad esempio, per visualizzare informazioni sulle ferie del team, eventi di calendario e qualsiasi evento specifico del team.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-135">For example, it can be used to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="1c4aa-136">Per scaricare l'app **Integration with Office 365** e Custome Entity Structure, andare a [Integrazione con Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-136">To download the **Integration with Office 365** app and Custome Entity Structure, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="flow--email-notification"></a><span data-ttu-id="1c4aa-137">Flusso – Notifica tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="1c4aa-137">Flow – Email Notification</span></span>

<span data-ttu-id="1c4aa-138">Il modello **Flusso – Notifica tramite posta elettronica** può essere utilizzato per scenari di notifica tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-138">The **Flow – Email Notification** template can be used for email notification scenarios.</span></span> <span data-ttu-id="1c4aa-139">Può essere utilizzato per inviare messaggi di posta elettronica di notifica a candidati che il team di assunzione non seleziona durante una qualsiasi fase del processo di selezione.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-139">It can be used to trigger notification emails to candidates that the hiring team rejects during any stage of the recruiting process.</span></span>

<span data-ttu-id="1c4aa-140">Questo modello può essere esteso per tenere traccia delle modifiche alla fase di candidatura durante il processo di selezione e per inviare notifiche al team di assunzione e al candidato.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-140">This template can be extended to track changes to the candidate stage throughout the recruiting process, and to send notifications to the hiring team and candidate.</span></span>

<span data-ttu-id="1c4aa-141">In genere per le entità archiviate in Common Data Service, i flussi possono essere configurati per inviare notifiche per eventi che si verificano in Core HR, Attract o Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-141">In general, for entities that are stored in Common Data Service, flows can be set up to send notifications for events that occur in Core HR, Attract, or Dynamics 365 Talent: Onboard.</span></span>

<span data-ttu-id="1c4aa-142">Per scaricare il modello **Flusso – Notifica tramite posta elettronica**, andare a [Flusso – Notifica tramite posta elettronica](https://go.microsoft.com/fwlink/?linkid=2082103) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-142">To download the **Flow – Email Notification** template, go to [Flow – Email Notification](https://go.microsoft.com/fwlink/?linkid=2082103) on the Microsoft Download Center.</span></span>

## <a name="flow--sql-connect-and-execute"></a><span data-ttu-id="1c4aa-143">Flusso – Connessione a SQL ed esecuzione</span><span class="sxs-lookup"><span data-stu-id="1c4aa-143">Flow – SQL Connect and execute</span></span>

<span data-ttu-id="1c4aa-144">Il modello **Flusso – Connessione a SQL ed esecuzione** esegue la connessione a Microsoft SQL Server e consente l'esecuzione delle query SQL.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-144">The **Flow – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="1c4aa-145">Sebbene questo modello sia progettato per leggere e aggiornare le tabelle SQL, può essere esteso in modo da essere utilizzato per altri scenari.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-145">Although this template is designed to read and update SQL tables, it can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="1c4aa-146">Ad esempio, per compilare una tabella di gestione temporanea in Common Data Service con record di SQL Server e per sincronizzarla periodicamente utilizzando un push incrementale di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-146">For example, it can be used to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="1c4aa-147">Per scaricare il modello **Flusso – Connessione a SQL ed esecuzione** e Custom Entity Structure, andare a [Flusso – Connessione a SQL ed esecuzione](https://go.microsoft.com/fwlink/?linkid=2081789) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-147">To download the **Flow – SQL Connect and execute** template, go to [Flow – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="flow--sharepoint-integration"></a><span data-ttu-id="1c4aa-148">Flusso – Integrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="1c4aa-148">Flow – SharePoint Integration</span></span>

<span data-ttu-id="1c4aa-149">Il modello **Flusso – Integrazione di SharePoint** può essere utilizzato per leggere dati in un elenco di Microsoft SharePoint, confrontare l'elenco con valori di campi per qualsiasi entità Common Data Service e inviare i risultati del confronto in forma di messaggio di posta elettronica di notifica.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-149">The **Flow – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="1c4aa-150">Un'organizzazione potrebbe avere un insieme di competenze che richiede urgentemente.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-150">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="1c4aa-151">Queste competenze possono essere archiviate in SharePoint come elenco di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-151">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="1c4aa-152">Quando un candidato si candida a una mansione per la quale è elencato un insieme di competenze, se è presente una corrispondenza significativa tra le competenze del candidato e quelle archiviate in SharePoint, viene inviato un messaggio di posta elettronica di notifica.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-152">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="1c4aa-153">In questo modo, le posizioni urgenti vengono coperte più rapidamente in quanto le notifiche consentono ai selezionatori di contattare e assumere i candidati nell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-153">In this way, positions that are urgently required are filled faster, because the notifications help recruiters reach out and cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="1c4aa-154">Questo modello può essere esteso di modo che sia possibile utilizzarlo per qualsiasi scenario che comporta l'integrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-154">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="1c4aa-155">Per scaricare il modello **Flusso – Integrazione di SharePoint**, andare a [Flusso – Integrazione di SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-155">To download the **Flow – SharePoint Integration** template, go to [Flow – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="referral-app"></a><span data-ttu-id="1c4aa-156">Referral App</span><span class="sxs-lookup"><span data-stu-id="1c4aa-156">Referral App</span></span>
<span data-ttu-id="1c4aa-157">È possibile utilizzare Referral App per aggiungere candidati a un pool di talenti condiviso.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-157">You can use the Referral App to add candidates to a shared talent pool.</span></span> <span data-ttu-id="1c4aa-158">Il referente può immettere **Nome**, **Cognome**, **E-mail** e **URL Linkedln** quando invia un candidato.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-158">The referrer can enter **Firstname**, **Lastname**, **Email**, and **Linkedln URL** when submitting a candidate.</span></span> <span data-ttu-id="1c4aa-159">I metadati di origine del candidato vengono quindi completati con le informazioni del referente.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-159">The candidate source metadata is then populated with the referrer’s information.</span></span>

<span data-ttu-id="1c4aa-160">È possibile incorporare questa app in Dipendente self-service (ESS) per inviare referenze oppure è possibile utilizzarla come collegamento ipertestuale nel portale aziendale ed eseguirla come applicazione autonoma.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-160">You can embed this app in Employee self-service (ESS) for submitting referrals, or you can be use it as a hyperlink in the Corporate Portal and run as a stand-alone app.</span></span>

<span data-ttu-id="1c4aa-161">Per scaricare **Referral App**, accedere a [Soluzione di estensibilità Dynamics 365 for Talent: Referral App](http://www.microsoft.com/downloads/details.aspx?FamilyID=9a59c9d1-f8a1-4d4d-b768-cfc4f4eb9d0d) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-161">To download **Referral App**, go to [Dynamics 365 for Talent extensibility solution: Referral App](http://www.microsoft.com/downloads/details.aspx?FamilyID=9a59c9d1-f8a1-4d4d-b768-cfc4f4eb9d0d) on the Microsoft Download Center.</span></span> <span data-ttu-id="1c4aa-162">È possibile importare questa app e personalizzarla per aggiungere altre funzionalità.</span><span class="sxs-lookup"><span data-stu-id="1c4aa-162">You can import this app and customize it to add additional functionality.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1c4aa-163">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1c4aa-163">Additional resources</span></span>

[<span data-ttu-id="1c4aa-164">Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="1c4aa-164">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[<span data-ttu-id="1c4aa-165">Migrare app tra tenant e ambienti</span><span class="sxs-lookup"><span data-stu-id="1c4aa-165">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
