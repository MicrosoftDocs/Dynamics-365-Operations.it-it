---
title: Domande frequenti fase operativa
description: Questo argomento elenca le domande frequenti su come passare alla fase operativa con un progetto di implementazione Dynamics 365 Human Resources.
author: rachel-profitt
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d667d94983d5c8f8e6140259922396d4299a15e3
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467595"
---
# <a name="go-live-faq"></a><span data-ttu-id="0d72b-103">Domande frequenti fase operativa</span><span class="sxs-lookup"><span data-stu-id="0d72b-103">Go-live FAQ</span></span> 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="0d72b-104">Questo argomento elenca le domande frequenti su come passare alla fase operativa con un progetto di implementazione Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0d72b-104">This topic lists frequently asked questions about how to go live with a Dynamics 365 Human Resources implementation project.</span></span> 

## <a name="when-can-i-configure-and-request-my-production-environment"></a><span data-ttu-id="0d72b-105">Quando è possibile configurare e richiedere l'ambiente di produzione?</span><span class="sxs-lookup"><span data-stu-id="0d72b-105">When can I configure and request my production environment?</span></span> 

<span data-ttu-id="0d72b-106">In genere, un ambiente di produzione viene distribuito dopo aver soddisfatto i seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="0d72b-106">Typically, a production environment is deployed after meeting the following criteria:</span></span>

- <span data-ttu-id="0d72b-107">Tutte le personalizzazioni del codice sono state completate.</span><span class="sxs-lookup"><span data-stu-id="0d72b-107">All customizations are code-complete.</span></span>
- <span data-ttu-id="0d72b-108">Il test di accettazione dell'utente (UAT) è stato completato.</span><span class="sxs-lookup"><span data-stu-id="0d72b-108">User acceptance testing (UAT) is complete.</span></span>
- <span data-ttu-id="0d72b-109">Il cliente ha autorizzato la soluzione.</span><span class="sxs-lookup"><span data-stu-id="0d72b-109">The customer has signed off on the solution.</span></span>
- <span data-ttu-id="0d72b-110">Non ci sono problemi che bloccano la fase operativa.</span><span class="sxs-lookup"><span data-stu-id="0d72b-110">There are no blocking issues for go-live.</span></span> 

<span data-ttu-id="0d72b-111">Quando i clienti idonei si trovano in questa fase, il team Microsoft FastTrack lavorerà con il team di progetto per eseguire una valutazione della fase operativa.</span><span class="sxs-lookup"><span data-stu-id="0d72b-111">When qualified customers are at this stage, the Microsoft FastTrack team will work with the project team to do a go-live assessment.</span></span> 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a><span data-ttu-id="0d72b-112">Quali sono i prerequisiti per la distribuzione di un ambiente di produzione?</span><span class="sxs-lookup"><span data-stu-id="0d72b-112">What are the prerequisites to deploying a production environment?</span></span> 

<span data-ttu-id="0d72b-113">Per un elenco dei prerequisiti, vedere  [Preparazione per la fase operativa](hr-admin-go-live-prepare.md).</span><span class="sxs-lookup"><span data-stu-id="0d72b-113">For a list of the prerequisites, see [Prepare for go-live](hr-admin-go-live-prepare.md).</span></span> 

## <a name="what-is-a-go-live-assessment"></a><span data-ttu-id="0d72b-114">Cos'è una valutazione della fase operativa?</span><span class="sxs-lookup"><span data-stu-id="0d72b-114">What is a go-live assessment?</span></span>  

<span data-ttu-id="0d72b-115">La valutazione della fase operativa fa parte del  [programma Microsoft FastTrack](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview).</span><span class="sxs-lookup"><span data-stu-id="0d72b-115">The go-live assessment is part of the [Microsoft FastTrack program](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview).</span></span> <span data-ttu-id="0d72b-116">Durante questa revisione, un solution architect valuta se un progetto di implementazione è pronto per il passaggio e la fase operativa di successo.</span><span class="sxs-lookup"><span data-stu-id="0d72b-116">During this review, a solution architect assesses whether an implementation project is ready for a successful cutover and go-live.</span></span> <span data-ttu-id="0d72b-117">Questa revisione è obbligatoria per ogni progetto di implementazione prima di poter richiedere la fase operativa in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="0d72b-117">This review is mandatory for every implementation project before you can request to go live in a production environment.</span></span> 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a><span data-ttu-id="0d72b-118">I nostri ambienti Sandbox vengono distribuiti nel data center degli Stati Uniti centrali.</span><span class="sxs-lookup"><span data-stu-id="0d72b-118">Our Sandbox environments are deployed in the Central US datacenter.</span></span> <span data-ttu-id="0d72b-119">Vogliamo che i nostri ambienti di produzione vengano distribuiti nel data center degli Stati Uniti occidentali.</span><span class="sxs-lookup"><span data-stu-id="0d72b-119">We want our Production environments to be deployed in the West US datacenter.</span></span> <span data-ttu-id="0d72b-120">È possibile selezionare Stati Uniti occidentali come data center nella configurazione di produzione?</span><span class="sxs-lookup"><span data-stu-id="0d72b-120">Can I select West US as the datacenter in my Production configuration?</span></span> 

<span data-ttu-id="0d72b-121">LCS non impedisce di selezionare un data center diverso quando si distribuisce un ambiente Human Resources, ma consigliamo vivamente di non selezionare un data center diverso.</span><span class="sxs-lookup"><span data-stu-id="0d72b-121">LCS doesn't restrict you from selecting a different data center when you deploy a Human Resources environment, but we strongly recommend not selecting a different data center.</span></span>  

<span data-ttu-id="0d72b-122">Se si desidera che l'ambiente di produzione si trovi nel data center degli Stati Uniti occidentali, è necessario prima ridistribuire gli ambienti Sandbox nel data center degli Stati Uniti occidentali, testarli e disconnetterli.</span><span class="sxs-lookup"><span data-stu-id="0d72b-122">If you want your Production environment to be in the West US datacenter, you should first redeploy your Sandbox environments to the West US datacenter, test them, and sign off.</span></span> 

<span data-ttu-id="0d72b-123">Per informazioni sulla selezione del data center corretto, vedere [Requisiti di rete](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements).</span><span class="sxs-lookup"><span data-stu-id="0d72b-123">For information about selecting the correct datacenter, see [Network requirements](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements).</span></span> 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a><span data-ttu-id="0d72b-124">Quale livello di accesso alle risorse di Azure è disponibile per gli ambienti Human Resources?</span><span class="sxs-lookup"><span data-stu-id="0d72b-124">What level of access do I have to the Azure resources for my Human Resources environments?</span></span>  

<span data-ttu-id="0d72b-125">L'accesso agli ambienti Human Resources è limitato.</span><span class="sxs-lookup"><span data-stu-id="0d72b-125">Access to the Human Resources environments is limited.</span></span> <span data-ttu-id="0d72b-126">Non è possibile accedere alla macchina virtuale (VM) o a Microsoft Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="0d72b-126">You can't access the virtual machine (VM) or Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="0d72b-127">Inoltre non è possibile accedere al database tramite Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="0d72b-127">You also can't access the database through Microsoft SQL Server Management Studio.</span></span> 

<span data-ttu-id="0d72b-128">Sebbene non sia possibile accedere alle risorse di Azure o all'ambiente Dynamics 365 Human Resources direttamente, ci sono funzionalità aggiuntive che è possibile utilizzare per accedere ai dati:</span><span class="sxs-lookup"><span data-stu-id="0d72b-128">Although you can't access your Azure resources or Dynamics 365 Human Resources environment directly, there are additional features you can use to access your data:</span></span>

- <span data-ttu-id="0d72b-129">È possibile distribuire un database SQL di Azure nel proprio tenant di Azure e usare la funzionalità per portare il proprio database (BYOD) per sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="0d72b-129">You can deploy an Azure SQL database in your own Azure tenant and use the Bring Your Own Database (BYOD) feature to synchronize data.</span></span> <span data-ttu-id="0d72b-130">Per ulteriori informazioni, vedere [Portare il proprio database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span><span class="sxs-lookup"><span data-stu-id="0d72b-130">For more information, see [Bring your own database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span></span>

- <span data-ttu-id="0d72b-131">È possibile usare l'integrazione di Dataverse per sincronizzare le entità selezionate nel database Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0d72b-131">You can use Dataverse integration to synchronize select entities into the Dataverse database.</span></span> <span data-ttu-id="0d72b-132">Per ulteriori informazioni, vedi [Tabelle Dataverse](hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="0d72b-132">For more information, see [Dataverse tables](hr-developer-entities.md).</span></span> 

## <a name="how-often-is-my-production-database-backed-up"></a><span data-ttu-id="0d72b-133">Con quale frequenza viene eseguito il backup del database di produzione?</span><span class="sxs-lookup"><span data-stu-id="0d72b-133">How often is my production database backed up?</span></span> 

<span data-ttu-id="0d72b-134">I database sono protetti da backup automatici con le seguenti frequenze:</span><span class="sxs-lookup"><span data-stu-id="0d72b-134">Databases are protected by automatic backups at the following frequencies:</span></span>

| <span data-ttu-id="0d72b-135">Tipo di backup</span><span class="sxs-lookup"><span data-stu-id="0d72b-135">Type of backup</span></span> | <span data-ttu-id="0d72b-136">Frequenza</span><span class="sxs-lookup"><span data-stu-id="0d72b-136">Frequency</span></span> |
| --- | --- |
| <span data-ttu-id="0d72b-137">Backup completo del database</span><span class="sxs-lookup"><span data-stu-id="0d72b-137">Full database backup</span></span> | <span data-ttu-id="0d72b-138">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="0d72b-138">Weekly</span></span> |
| <span data-ttu-id="0d72b-139">Backup differenziale del database</span><span class="sxs-lookup"><span data-stu-id="0d72b-139">Differential database backup</span></span> | <span data-ttu-id="0d72b-140">Ogni 12-24 ore</span><span class="sxs-lookup"><span data-stu-id="0d72b-140">Every 12-24 hours</span></span> |
| <span data-ttu-id="0d72b-141">Backup del registro delle transazioni</span><span class="sxs-lookup"><span data-stu-id="0d72b-141">Transaction log backup</span></span> | <span data-ttu-id="0d72b-142">Ogni 5-10 minuti</span><span class="sxs-lookup"><span data-stu-id="0d72b-142">Every 5 to 10 minutes</span></span> |

<span data-ttu-id="0d72b-143">Microsoft conserva backup sufficienti per consentire il ripristino temporizzato (PITR) negli ultimi 14 giorni.</span><span class="sxs-lookup"><span data-stu-id="0d72b-143">Microsoft retains sufficient backups to allow for Point in Time Restore (PITR) within the last 14 days.</span></span> 

<span data-ttu-id="0d72b-144">Per ulteriori informazioni, vedere  [Informazioni sui backup automatici del database SQL](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span><span class="sxs-lookup"><span data-stu-id="0d72b-144">For more information, see [Learn about automatic SQL Database backups](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span></span> 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a><span data-ttu-id="0d72b-145">È possibile richiedere una copia del backup del database di produzione?</span><span class="sxs-lookup"><span data-stu-id="0d72b-145">Can I request a copy of the backup of my production database?</span></span> 

<span data-ttu-id="0d72b-146">N.</span><span class="sxs-lookup"><span data-stu-id="0d72b-146">No.</span></span> <span data-ttu-id="0d72b-147">Tuttavia, è possibile inviare una richiesta di servizio di aggiornamento del database per copiare l'ambiente di produzione nell'ambiente Sandbox.</span><span class="sxs-lookup"><span data-stu-id="0d72b-147">You can submit a database refresh service request to copy your Production environment to your Sandbox environment, however.</span></span> <span data-ttu-id="0d72b-148">È possibile distribuire un database SQL di Azure nel proprio tenant di Azure e usare la funzionalità BYOD per sincronizzare i dati dall'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="0d72b-148">You can deploy an Azure SQL database in your own Azure tenant and use the BYOD feature to synchronize data from your Production environment.</span></span> <span data-ttu-id="0d72b-149">Per ulteriori informazioni, vedere [Portare il proprio database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span><span class="sxs-lookup"><span data-stu-id="0d72b-149">For more information, see [Bring your own database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span></span> 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a><span data-ttu-id="0d72b-150">Come è possibile spostare l'ambiente Sandbox in Produzione per la fase operativa?</span><span class="sxs-lookup"><span data-stu-id="0d72b-150">How do I move my Sandbox environment to Production for go-live?</span></span> 

<span data-ttu-id="0d72b-151">Poiché una funzione di copia non è disponibile per spostare l'ambiente da un Sandbox a un ambiente di produzione, è necessario utilizzare i pacchetti di dati per spostare i dati nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="0d72b-151">Because a copy feature isn't available to move your environment from a Sandbox to a Production environment, you must use data packages to move data into your Production environment.</span></span>  

<span data-ttu-id="0d72b-152">Si consiglia di mantenere un elenco chiaro di entità configurate nell'ambiente Sandbox durante tutto il progetto.</span><span class="sxs-lookup"><span data-stu-id="0d72b-152">We recommend maintaining a clear list of entities configured in your Sandbox throughout the project.</span></span> <span data-ttu-id="0d72b-153">Quindi testare il processo di passaggio e migrazione di tutti i pacchetti di dati necessari per la fase operativa.</span><span class="sxs-lookup"><span data-stu-id="0d72b-153">Then test the process of cutover and migration of any data packages needed for your go-live.</span></span> <span data-ttu-id="0d72b-154">È necessario spostare manualmente tutti i pacchetti di dati nell'ambiente di produzione quando si è pronti per la fase operativa.</span><span class="sxs-lookup"><span data-stu-id="0d72b-154">You must manually move any data packages into the Production environment when you are ready to go live.</span></span> 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a><span data-ttu-id="0d72b-155">Cosa fare se l'ambiente di produzione non funziona?</span><span class="sxs-lookup"><span data-stu-id="0d72b-155">What should I do if my Production environment is down?</span></span> 

<span data-ttu-id="0d72b-156">Per segnalare un'interruzione di produzione, seguire la procedura descritta in  [Segnalare un'interruzione di produzione](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage).</span><span class="sxs-lookup"><span data-stu-id="0d72b-156">To report a Production outage, follow the process described in [Report a production outage](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage).</span></span> 

 ## <a name="see-also"></a><span data-ttu-id="0d72b-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d72b-157">See also</span></span>

 [<span data-ttu-id="0d72b-158">Prepararsi per la fase operativa</span><span class="sxs-lookup"><span data-stu-id="0d72b-158">Prepare for go-live</span></span>](hr-admin-go-live-prepare.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]