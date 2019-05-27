---
title: Rimuovere ambienti Talent
description: Questo argomento descrive il processo di rimozione di un ambiente test drive o di produzione per Microsoft Dynamics 365 for Talent.
author: andreabichsel
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: 904c8eb1254a65e1627c33f14488a1a8e12f7c2b
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518371"
---
# <a name="remove-talent-environments"></a><span data-ttu-id="7d889-103">Rimuovere ambienti Talent</span><span class="sxs-lookup"><span data-stu-id="7d889-103">Remove Talent environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7d889-104">Questo argomento descrive il processo di rimozione di un ambiente test drive o di produzione per Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="7d889-104">This topic walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 for Talent.</span></span>

## <a name="removing-a-test-drive-environment"></a><span data-ttu-id="7d889-105">Rimozione di un ambiente test drive</span><span class="sxs-lookup"><span data-stu-id="7d889-105">Removing a test drive environment</span></span>

<span data-ttu-id="7d889-106">Il provisioning dei test drive di Talent viene effettuato con criteri di scadenza di 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="7d889-106">Talent test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="7d889-107">I proprietari di ambienti di test drive, tuttavia, hanno la possibilità di terminare la propria verifica in anticipo completando i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="7d889-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="7d889-108">Accedere all'[interfaccia di amministrazione di PowerApps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="7d889-108">Navigate to the [PowerApps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="7d889-109">Selezionare **Ambienti**.</span><span class="sxs-lookup"><span data-stu-id="7d889-109">Select **Environments**.</span></span>
3. <span data-ttu-id="7d889-110">Selezionare l'ambiente test drive, che ha un criterio di denominazione simile al seguente: TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="7d889-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="7d889-111">Selezionare **Elimina** e confermare la decisione.</span><span class="sxs-lookup"><span data-stu-id="7d889-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="7d889-112">L'ambiente test drive esistente verrà rimosso.</span><span class="sxs-lookup"><span data-stu-id="7d889-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="7d889-113">Quando viene rimosso, è possibile eseguire l'iscrizione a un nuovo ambiente test drive.</span><span class="sxs-lookup"><span data-stu-id="7d889-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="removing-a-production-environment"></a><span data-ttu-id="7d889-114">Rimozione di un ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="7d889-114">Removing a production environment</span></span>

<span data-ttu-id="7d889-115">In questo argomento si presuppone che Talent sia già stato acquistato tramite un provider di soluzioni cloud o un contratto Enterprise Architecture (EA).</span><span class="sxs-lookup"><span data-stu-id="7d889-115">This topic assumes that you've purchased Talent through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="7d889-116">Poiché un unico ambiente Talent è "contenuto" in unico ambiente PowerApps, è necessario considerare due opzioni.</span><span class="sxs-lookup"><span data-stu-id="7d889-116">Since a single Talent environment is “contained” within a single PowerApps environment, there are two options to consider.</span></span> <span data-ttu-id="7d889-117">La prima opzione implica prima di tutto la rimozione dell'intero ambiente PowerApps. La seconda opzione implica la rimozione solo di Talent.</span><span class="sxs-lookup"><span data-stu-id="7d889-117">The first option involves removing the entire PowerApps environment; the second option involves removing only Talent.</span></span> <span data-ttu-id="7d889-118">La prima opzione è preferibile se si è creato un ambiente PowerApps appositamente per il provisioning di Talent e l'implementazione è appena stata iniziata, oppure se non si hanno integrazioni stabilite.</span><span class="sxs-lookup"><span data-stu-id="7d889-118">The first option is preferred when you have created a PowerApps environment expressly for the purpose of provisioning Talent, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="7d889-119">La seconda opzione è appropriata quando si è stabilito un ambiente PowerApps con dati complessi utilizzati in PowerApps e in flussi.</span><span class="sxs-lookup"><span data-stu-id="7d889-119">The second option is appropriate when you have an established PowerApps environment populated with rich data that's leveraged in PowerApps and Flows.</span></span>

> [!Important]
> <span data-ttu-id="7d889-120">Prima di rimuovere l'ambiente PowerApps, assicurarsi che non sia utilizzato per integrazioni di dati complessi al di fuori dell'ambito di Talent.</span><span class="sxs-lookup"><span data-stu-id="7d889-120">Before removing the PowerApps environment, ensure it is not being used for rich data integrations outside the scope of Talent.</span></span> <span data-ttu-id="7d889-121">Inoltre si noti che, gli ambienti PowerApps predefiniti non possono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="7d889-121">Also note that the default PowerApps environments cannot be removed.</span></span> 

<span data-ttu-id="7d889-122">Per rimuovere l'intero ambiente PowerApps, inclusi Talent nonché le app e i flussi associati:</span><span class="sxs-lookup"><span data-stu-id="7d889-122">To remove the entire PowerApps environment, including Talent and the associated Apps and Flows:</span></span>

1. <span data-ttu-id="7d889-123">Accedere all'[interfaccia di amministrazione di PowerApps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="7d889-123">Navigate to the [PowerApps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="7d889-124">Selezionare **Ambienti**.</span><span class="sxs-lookup"><span data-stu-id="7d889-124">Select **Environments**.</span></span>
3. <span data-ttu-id="7d889-125">Selezionare l'ambiente da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="7d889-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="7d889-126">Selezionare **Elimina** e confermare la decisione.</span><span class="sxs-lookup"><span data-stu-id="7d889-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="7d889-127">Attendere fino al completamento dell'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="7d889-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="7d889-128">Accedere a [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) utilizzando l'account usato per iscriversi a Talent.</span><span class="sxs-lookup"><span data-stu-id="7d889-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Talent.</span></span> 
7. <span data-ttu-id="7d889-129">Selezionare il progetto Talent contenente l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="7d889-129">Select the Talent Project that contains the environment.</span></span> 
8. <span data-ttu-id="7d889-130">Nel progetto LCS selezionare il riquadro **Gestione app Talent**.</span><span class="sxs-lookup"><span data-stu-id="7d889-130">In your LCS project, select the **Talent App Management** tile.</span></span> 
9. <span data-ttu-id="7d889-131">Selezionare l'istanza da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="7d889-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="7d889-132">Selezionare **Rimuovere istanza** e confermare la decisione.</span><span class="sxs-lookup"><span data-stu-id="7d889-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="7d889-133">Per rimuovere un ambiente Talent da un ambiente PowerApps esistente, completare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="7d889-133">To remove a Talent environment from an existing PowerApps environment, complete the following steps.</span></span> <span data-ttu-id="7d889-134">Si noti che la necessità di coinvolgere il supporto e contattare il team Talent DevOps è temporanea fino a che questa funzionalità è attivata direttamente in LCS.</span><span class="sxs-lookup"><span data-stu-id="7d889-134">Note that the need to involve support and contact the Talent DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="7d889-135">Contattare il Supporto per avviare una richiesta di rimozione.</span><span class="sxs-lookup"><span data-stu-id="7d889-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="7d889-136">Il team di supporto avvierà una richiesta di rimozione con il team Talent DevOps.</span><span class="sxs-lookup"><span data-stu-id="7d889-136">The Support team will initiate a removal request with the Talent DevOps team.</span></span> 
3. <span data-ttu-id="7d889-137">Continuare dopo aver ricevuto conferma che l'ambiente è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="7d889-137">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="7d889-138">Accedere a LCS utilizzando l'account usato per iscriversi a Talent.</span><span class="sxs-lookup"><span data-stu-id="7d889-138">Sign in to LCS using the account that you used to subscribe to Talent.</span></span> 
5. <span data-ttu-id="7d889-139">Selezionare il progetto Talent contenente l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="7d889-139">Select the Talent project that contains the environment.</span></span> 
6. <span data-ttu-id="7d889-140">Nel progetto LCS selezionare il riquadro **Gestione app Talent**.</span><span class="sxs-lookup"><span data-stu-id="7d889-140">In your LCS project, select the **Talent App Management** tile.</span></span> 
7. <span data-ttu-id="7d889-141">Selezionare l'istanza che si desidera rimuovere, che deve essere contrassegnata con lo stato di distribuzione **Non riuscita**.</span><span class="sxs-lookup"><span data-stu-id="7d889-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="7d889-142">Selezionare **Rimuovere istanza** e confermare la decisione.</span><span class="sxs-lookup"><span data-stu-id="7d889-142">Select **Remove instance** and confirm your decision.</span></span> 

