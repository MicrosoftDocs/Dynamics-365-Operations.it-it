---
title: Rimuovere un'istanza
description: In questo argomento viene descritto il processo di rimozione di un ambiente test drive o di produzione per Microsoft Dynamics 365 Human Resources.
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
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a40b9619e92b81272208ad4241a2455330a342a7
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124430"
---
# <a name="remove-an-instance"></a><span data-ttu-id="5b503-103">Rimuovere un'istanza</span><span class="sxs-lookup"><span data-stu-id="5b503-103">Remove an instance</span></span>

<span data-ttu-id="5b503-104">In questo argomento viene descritto il processo di rimozione di un ambiente test drive o di produzione per Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5b503-104">This article walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Human Resources.</span></span>

## <a name="remove-a-test-drive-environment"></a><span data-ttu-id="5b503-105">Rimuovere un ambiente test drive</span><span class="sxs-lookup"><span data-stu-id="5b503-105">Remove a test drive environment</span></span>

<span data-ttu-id="5b503-106">Il provisioning dei test drive di Human Resources viene effettuato con criteri di scadenza di 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="5b503-106">Human Resources test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="5b503-107">I proprietari di ambienti di test drive, tuttavia, hanno la possibilità di terminare la propria verifica in anticipo completando i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="5b503-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="5b503-108">Accedere all'[Interfaccia di amministrazione di Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="5b503-108">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="5b503-109">Selezionare **Ambienti**.</span><span class="sxs-lookup"><span data-stu-id="5b503-109">Select **Environments**.</span></span>
3. <span data-ttu-id="5b503-110">Selezionare l'ambiente test drive, che ha un criterio di denominazione simile al seguente: TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="5b503-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="5b503-111">Selezionare **Elimina** e confermare la decisione.</span><span class="sxs-lookup"><span data-stu-id="5b503-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="5b503-112">L'ambiente test drive esistente verrà rimosso.</span><span class="sxs-lookup"><span data-stu-id="5b503-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="5b503-113">Quando viene rimosso, è possibile eseguire l'iscrizione a un nuovo ambiente test drive.</span><span class="sxs-lookup"><span data-stu-id="5b503-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="remove-a-production-environment"></a><span data-ttu-id="5b503-114">Rimuovere un ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="5b503-114">Remove a production environment</span></span>

<span data-ttu-id="5b503-115">In questo articolo si presuppone che Human Resources sia già stato acquistato tramite un provider di soluzioni cloud o un contratto Enterprise Architecture (EA).</span><span class="sxs-lookup"><span data-stu-id="5b503-115">This article assumes that you've purchased Human Resources through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="5b503-116">Poiché un unico ambiente Human Resources è contenuto in unico ambiente Power Apps, è necessario considerare due opzioni.</span><span class="sxs-lookup"><span data-stu-id="5b503-116">Since a single Human Resources environment is contained within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="5b503-117">La prima opzione implica prima di tutto la rimozione dell'intero ambiente Power Apps. La seconda opzione implica la rimozione solo di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5b503-117">The first option involves removing the entire Power Apps environment; the second option involves removing only Human Resources.</span></span> <span data-ttu-id="5b503-118">La prima opzione è preferibile se si è creato un ambiente Power Apps appositamente per il provisioning di Human Resources e l'implementazione è appena stata iniziata, oppure se non si hanno integrazioni stabilite.</span><span class="sxs-lookup"><span data-stu-id="5b503-118">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Human Resources, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="5b503-119">La seconda opzione è appropriata quando si è stabilito un ambiente Power Apps con dati complessi utilizzati in Power Apps e Power Automate..</span><span class="sxs-lookup"><span data-stu-id="5b503-119">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="5b503-120">Prima di rimuovere l'ambiente Power Apps, assicurarsi che non sia utilizzato per integrazioni di dati complessi al di fuori dell'ambito di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5b503-120">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Human Resources.</span></span> <span data-ttu-id="5b503-121">Inoltre si noti che, gli ambienti Power Apps predefiniti non possono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="5b503-121">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="5b503-122">Per rimuovere l'intero ambiente Power Apps, inclusi Human Resources nonché le app e i flussi associati:</span><span class="sxs-lookup"><span data-stu-id="5b503-122">To remove the entire Power Apps environment, including Human Resources and the associated apps and flows:</span></span>

1. <span data-ttu-id="5b503-123">Accedere all'[Interfaccia di amministrazione di Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="5b503-123">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="5b503-124">Selezionare **Ambienti**.</span><span class="sxs-lookup"><span data-stu-id="5b503-124">Select **Environments**.</span></span>
3. <span data-ttu-id="5b503-125">Selezionare l'ambiente da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="5b503-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="5b503-126">Selezionare **Elimina** e confermare la decisione.</span><span class="sxs-lookup"><span data-stu-id="5b503-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="5b503-127">Attendere fino al completamento dell'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="5b503-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="5b503-128">Accedere a [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) utilizzando l'account usato per iscriversi a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5b503-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Human Resources.</span></span> 
7. <span data-ttu-id="5b503-129">Selezionare il progetto Human Resources contenente l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="5b503-129">Select the Human Resources Project that contains the environment.</span></span> 
8. <span data-ttu-id="5b503-130">Nel progetto LCS selezionare il riquadro **Gestione app Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="5b503-130">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
9. <span data-ttu-id="5b503-131">Selezionare l'istanza da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="5b503-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="5b503-132">Selezionare **Rimuovere istanza** e confermare la decisione.</span><span class="sxs-lookup"><span data-stu-id="5b503-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="5b503-133">Per rimuovere un ambiente Human Resources da un ambiente Power Apps esistente, completare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5b503-133">To remove a Human Resources environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="5b503-134">Si noti che la necessità di coinvolgere il supporto e contattare il team Human Resources DevOps è temporanea fino a che questa funzionalità è attivata direttamente in LCS.</span><span class="sxs-lookup"><span data-stu-id="5b503-134">Note that the need to involve support and contact the Human Resources DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="5b503-135">Contattare il Supporto per avviare una richiesta di rimozione.</span><span class="sxs-lookup"><span data-stu-id="5b503-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="5b503-136">Il team di supporto avvierà una richiesta di rimozione con il team Human Resources DevOps.</span><span class="sxs-lookup"><span data-stu-id="5b503-136">The Support team will initiate a removal request with the Human Resources DevOps team.</span></span> 
3. <span data-ttu-id="5b503-137">Continuare dopo aver ricevuto conferma che l'ambiente è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="5b503-137">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="5b503-138">Accedere a LCS utilizzando l'account usato per iscriversi a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5b503-138">Sign in to LCS using the account that you used to subscribe to Human Resources.</span></span> 
5. <span data-ttu-id="5b503-139">Selezionare il progetto Human Resources contenente l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="5b503-139">Select the Human Resources project that contains the environment.</span></span> 
6. <span data-ttu-id="5b503-140">Nel progetto LCS selezionare il riquadro **Gestione app Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="5b503-140">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
7. <span data-ttu-id="5b503-141">Selezionare l'istanza che si desidera rimuovere, che deve essere contrassegnata con lo stato di distribuzione **Non riuscita**.</span><span class="sxs-lookup"><span data-stu-id="5b503-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="5b503-142">Selezionare **Rimuovere istanza** e confermare la decisione.</span><span class="sxs-lookup"><span data-stu-id="5b503-142">Select **Remove instance** and confirm your decision.</span></span> 
