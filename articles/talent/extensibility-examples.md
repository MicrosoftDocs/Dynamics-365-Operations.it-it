---
title: Estendere Talent con Power Apps e Power Automate
description: In questo articolo vengono descritti alcuni esempi di scenari di estendibilità per Microsoft Dynamics 365 Talent - Attract che utilizzano Microsoft Power Apps e Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 1051fa4db16bb94cc9d60a91fc3637d7e5305cc2
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029913"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a><span data-ttu-id="fd53b-103">Estendere Talent con Power Apps e Power Automate</span><span class="sxs-lookup"><span data-stu-id="fd53b-103">Extend Talent with Power Apps and Power Automate</span></span>

<span data-ttu-id="fd53b-104">In questo articolo vengono descritti alcuni esempi di scenari di estendibilità per Microsoft Dynamics 365 Talent: Attract che utilizzano Microsoft Power Apps e Microsoft Power Automate.</span><span class="sxs-lookup"><span data-stu-id="fd53b-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Talent: Attract that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="fd53b-105">È possibile importare il pacchetto di soluzioni associato a ogni esempio nell'ambiente di Power Apps.</span><span class="sxs-lookup"><span data-stu-id="fd53b-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="fd53b-106">È quindi possibile utilizzare i pacchetti come riferimento o punto di partenza per implementare scenari applicabili all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fd53b-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd53b-107">Se si desidera utilizzare i modelli e l'app descritti in questo articolo "così come sono", testarli per assicurarsi che coprano tutti gli scenari specifici dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="fd53b-107">If you want to use the templates and app that are described in this article "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="fd53b-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fd53b-108">Prerequisites</span></span>

- <span data-ttu-id="fd53b-109">Per importare pacchetti, gli utenti devono disporre dell'autorizzazione **Creazione ambiente**.</span><span class="sxs-lookup"><span data-stu-id="fd53b-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="fd53b-110">Per esportare o importare app, gli utenti devono disporre di una licenza di Power Apps Piano 2 o una licenza di valutazione di Power Apps Piano 2.</span><span class="sxs-lookup"><span data-stu-id="fd53b-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="power-automate--form-connect"></a><span data-ttu-id="fd53b-111">Power Automate – Connessione a modulo</span><span class="sxs-lookup"><span data-stu-id="fd53b-111">Power Automate – Form Connect</span></span>

<span data-ttu-id="fd53b-112">Il modello **Power Automate – Connessione a modulo** può essere utilizzato per leggere i dati in Microsoft Forms e archiviarli in un'entità Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fd53b-112">The **Power Automate – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="fd53b-113">Questo modello può essere esteso in modo da poterlo utilizzare per altri scenari.</span><span class="sxs-lookup"><span data-stu-id="fd53b-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="fd53b-114">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="fd53b-114">Here are some examples:</span></span>

- <span data-ttu-id="fd53b-115">Acquisire valutazioni di candidati.</span><span class="sxs-lookup"><span data-stu-id="fd53b-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="fd53b-116">Acquisire risultati da questionari di corsi.</span><span class="sxs-lookup"><span data-stu-id="fd53b-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="fd53b-117">Compilare una libreria di domande di colloqui per gli amministratori delle Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="fd53b-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="fd53b-118">Acquisire la valutazione del colloquio di un candidato</span><span class="sxs-lookup"><span data-stu-id="fd53b-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="fd53b-119">In Microsoft Dynamics 365: Attract, è possibile utilizzare moduli nel portale del candidato, ovvero dove i candidati immettono i dettagli.</span><span class="sxs-lookup"><span data-stu-id="fd53b-119">In Microsoft Dynamics 365: Attract, you can use forms in the candidate portal, where candidates fill in details.</span></span> <span data-ttu-id="fd53b-120">È anche possibile incorporare moduli come attività in un modello posizioni lavorative.</span><span class="sxs-lookup"><span data-stu-id="fd53b-120">You can also embed forms as activities in a job template.</span></span>

<span data-ttu-id="fd53b-121">Quando un candidato invia un modulo, Microsoft Power Automate lo acquisisce, legge i dati e li archivia nell'entità Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fd53b-121">When a candidate submits a form, Microsoft Power Automate captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="fd53b-122">Per scaricare il modello **Power Automate – Connessione a modulo** e Custom Entity Structure, andare a [Power Automate – Connessione a modulo](https://go.microsoft.com/fwlink/?linkid=2081988) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd53b-122">To download the **Power Automate – Form Connect** template and Custom Entity Structure, go to [Power Automate – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sharepoint-integration"></a><span data-ttu-id="fd53b-123">Power Automate – Integrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="fd53b-123">Power Automate – SharePoint Integration</span></span>

<span data-ttu-id="fd53b-124">Il modello **Power Automate – Integrazione di SharePoint** può essere utilizzato per leggere dati in un elenco di Microsoft SharePoint, confrontare l'elenco con valori di campi per qualsiasi entità Common Data Service e inviare i risultati del confronto in forma di messaggio di posta elettronica di notifica.</span><span class="sxs-lookup"><span data-stu-id="fd53b-124">The **Power Automate – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="fd53b-125">Un'organizzazione potrebbe avere un insieme di competenze che richiede urgentemente.</span><span class="sxs-lookup"><span data-stu-id="fd53b-125">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="fd53b-126">Queste competenze possono essere archiviate in SharePoint come elenco di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fd53b-126">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="fd53b-127">Quando un candidato si candida a una mansione per la quale è elencato un insieme di competenze, se è presente una corrispondenza significativa tra le competenze del candidato e quelle archiviate in SharePoint, viene inviato un messaggio di posta elettronica di notifica.</span><span class="sxs-lookup"><span data-stu-id="fd53b-127">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="fd53b-128">In questo modo, le posizioni urgenti vengono coperte più rapidamente in quanto le notifiche consentono ai selezionatori di assumere i candidati nell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fd53b-128">This helps fill positions that are urgently required faster, because the notifications help recruiters cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="fd53b-129">Questo modello può essere esteso di modo che sia possibile utilizzarlo per qualsiasi scenario che comporta l'integrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fd53b-129">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="fd53b-130">Per scaricare il modello **Power Automate – Integrazione di SharePoint**, andare a [Power Automate – Integrazione di SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd53b-130">To download the **Power Automate – SharePoint Integration** template, go to [Power Automate – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="referral-app"></a><span data-ttu-id="fd53b-131">Referral App</span><span class="sxs-lookup"><span data-stu-id="fd53b-131">Referral App</span></span>

<span data-ttu-id="fd53b-132">È possibile utilizzare Referral App per aggiungere candidati a un pool di talenti condiviso.</span><span class="sxs-lookup"><span data-stu-id="fd53b-132">You can use the Referral App to add candidates to a shared talent pool.</span></span> <span data-ttu-id="fd53b-133">Il referente può immettere **Nome**, **Cognome**, **E-mail** e **URL LinkedIn** quando invia un candidato.</span><span class="sxs-lookup"><span data-stu-id="fd53b-133">The referrer can enter **Firstname**, **Lastname**, **Email**, and **LinkedIn URL** when submitting a candidate.</span></span> <span data-ttu-id="fd53b-134">I metadati di origine del candidato vengono quindi completati con le informazioni del referente.</span><span class="sxs-lookup"><span data-stu-id="fd53b-134">The candidate source metadata is then populated with the referrer’s information.</span></span>

<span data-ttu-id="fd53b-135">È possibile incorporare questa app in Dipendente self-service per inviare referenze oppure è possibile utilizzarla come collegamento ipertestuale nel portale aziendale ed eseguirla come applicazione autonoma.</span><span class="sxs-lookup"><span data-stu-id="fd53b-135">You can embed this app in Employee self service for submitting referrals, or you can use it as a hyperlink in the corporate portal and run it as a stand-alone app.</span></span>

<span data-ttu-id="fd53b-136">Per scaricare **Referral App**, accedere a [Soluzione di estensibilità Dynamics 365 Talent: Referral App](https://www.microsoft.com/download/details.aspx?id=58497) nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd53b-136">To download **Referral App**, go to [Dynamics 365 Talent extensibility solution: Referral App](https://www.microsoft.com/download/details.aspx?id=58497) on the Microsoft Download Center.</span></span> <span data-ttu-id="fd53b-137">È possibile importare questa app e personalizzarla per aggiungere altre funzionalità.</span><span class="sxs-lookup"><span data-stu-id="fd53b-137">You can import this app and customize it to add additional functionality.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fd53b-138">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fd53b-138">Additional resources</span></span>

[<span data-ttu-id="fd53b-139">Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="fd53b-139">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[<span data-ttu-id="fd53b-140">Migrare app tra tenant e ambienti</span><span class="sxs-lookup"><span data-stu-id="fd53b-140">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
