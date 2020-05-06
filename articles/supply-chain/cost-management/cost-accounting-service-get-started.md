---
title: Introduzione al servizio di contabilità industriale
description: Questo argomento fornisce dettagli sulla licenza e istruzioni di installazione per il servizio di contabilità industriale.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: cbbce7eaac264973bf0b95ad5175bf70ed2b4ae9
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "3276932"
---
# <a name="get-started-with-the-cost-accounting-service"></a><span data-ttu-id="4be75-103">Introduzione al servizio di contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="4be75-103">Get started with the cost accounting service</span></span>

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="4be75-104">La funzionalità descritta in questo argomento è disponibile nell'ambito di una versione di anteprima privata.</span><span class="sxs-lookup"><span data-stu-id="4be75-104">The functionality that is described in this topic is available as part of a private preview release.</span></span> <span data-ttu-id="4be75-105">Il contenuto di questo argomento e le funzionalità che descrive sono soggetti a modifiche.</span><span class="sxs-lookup"><span data-stu-id="4be75-105">The content of this topic and the functionality that it describes are subject to change.</span></span> <span data-ttu-id="4be75-106">Per ulteriori informazioni sui rilasci di anteprima, vedi [Domande frequenti aggiornamenti del servizio versione uno](../../fin-ops-core/fin-ops/get-started/one-version.md).</span><span class="sxs-lookup"><span data-stu-id="4be75-106">For more information about preview releases, see [One version service updates FAQ](../../fin-ops-core/fin-ops/get-started/one-version.md).</span></span>

<span data-ttu-id="4be75-107">Il servizio di contabilità industriale consente di eseguire più contabilità di inventario nei movimenti CoGe di contabilità industriale impostati.</span><span class="sxs-lookup"><span data-stu-id="4be75-107">The cost accounting service lets you do multiple inventory accounting in the cost accounting ledgers that you've set up.</span></span> <span data-ttu-id="4be75-108">Associare ogni movimento CoGe di contabilità industriale a una *convenzione*.</span><span class="sxs-lookup"><span data-stu-id="4be75-108">You associate each cost accounting ledger with a *convention*.</span></span> <span data-ttu-id="4be75-109">Una convenzione è la raccolta dei seguenti tipi di principi contabili:</span><span class="sxs-lookup"><span data-stu-id="4be75-109">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="4be75-110">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="4be75-110">Cost object</span></span>
- <span data-ttu-id="4be75-111">Base di misura di input</span><span class="sxs-lookup"><span data-stu-id="4be75-111">Input measurement basis</span></span>
- <span data-ttu-id="4be75-112">Presupposto per flussi di costo</span><span class="sxs-lookup"><span data-stu-id="4be75-112">Cost flow assumption</span></span>
- <span data-ttu-id="4be75-113">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="4be75-113">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="4be75-114">Anche dopo aver attivato il servizio di contabilità industriale, è ancora possibile eseguire la contabilità di inventario in Microsoft Dynamics 365 Supply Chain Management, come di consueto.</span><span class="sxs-lookup"><span data-stu-id="4be75-114">Even after you've turned on the cost accounting service, you can still do  inventory accounting in Microsoft Dynamics 365 Supply Chain Management, as usual.</span></span>

<span data-ttu-id="4be75-115">Il servizio di contabilità industriale è un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="4be75-115">The cost accounting service is an add-in.</span></span> <span data-ttu-id="4be75-116">Per rendere disponibili le funzionalità, è necessario installarlo da Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4be75-116">To makes its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="4be75-117">Pertanto, è possibile scegliere di valutarlo in un ambiente di test prima di attivarlo per gli ambienti di produzione.</span><span class="sxs-lookup"><span data-stu-id="4be75-117">Therefore, you can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="4be75-118">Il servizio di contabilità industriale non supporta attualmente tutte le funzionalità di gestione dei costi integrate in Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4be75-118">The cost accounting service doesn't currently support all the cost management features that are built into Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="4be75-119">Pertanto, è importante valutare se il set di funzionalità attualmente disponibile soddisfa i requisiti.</span><span class="sxs-lookup"><span data-stu-id="4be75-119">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="4be75-120">Licenze</span><span class="sxs-lookup"><span data-stu-id="4be75-120">Licensing</span></span>

<span data-ttu-id="4be75-121">Il servizio di contabilità industriale è concesso in licenza insieme alle funzionalità standard della contabilità di magazzino disponibili per Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4be75-121">The cost accounting service is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="4be75-122">Non è necessario acquistare una licenza aggiuntiva per utilizzare il servizio di contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="4be75-122">You don't have to purchase an additional license to use the cost accounting service.</span></span>

## <a name="install-the-add-in"></a><span data-ttu-id="4be75-123">Installare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="4be75-123">Install the add-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4be75-124">Per utilizzare il servizio di contabilità industriale, è necessario disporre di un ambiente ad alta disponibilità abilitato per LCS (non un ambiente OneBox) e deve essere in esecuzione Dynamics 365 Supply Chain Management versione 10.0.11 o successiva.</span><span class="sxs-lookup"><span data-stu-id="4be75-124">To use the cost accounting service, you must have an LCS-enabled high-availability environment (not a OneBox environment), and you must be running Dynamics 365 Supply Chain Management version 10.0.11 or later.</span></span>

<span data-ttu-id="4be75-125">Per utilizzare il servizio di contabilità industriale, installare il componente aggiuntivo del servizio di contabilità industriale per Supply Chain Management come descritto nella seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="4be75-125">To use the cost accounting service, install the cost accounting service add-in for Supply Chain Management as described in the following procedure.</span></span>

1. <span data-ttu-id="4be75-126">Accedere a LCS.</span><span class="sxs-lookup"><span data-stu-id="4be75-126">Sign in to LCS.</span></span>

1. <span data-ttu-id="4be75-127">Accedere a **Gestione funzionalità di anteprima**.</span><span class="sxs-lookup"><span data-stu-id="4be75-127">Go to **Preview feature management**.</span></span>

1. <span data-ttu-id="4be75-128">Selezionare il segno più (**+**).</span><span class="sxs-lookup"><span data-stu-id="4be75-128">Select the plus sign (**+**).</span></span>

1. <span data-ttu-id="4be75-129">Nel campo **Codice**, inserire la chiave beta del componente aggiuntivo per il servizio di contabilità industriale.</span><span class="sxs-lookup"><span data-stu-id="4be75-129">In the **Code** field, enter your add-in beta key for the cost accounting service.</span></span> <span data-ttu-id="4be75-130">La chiave viene ricevuta tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4be75-130">(You should have received your key by email.)</span></span>

1. <span data-ttu-id="4be75-131">Selezionare **Sblocca**.</span><span class="sxs-lookup"><span data-stu-id="4be75-131">Select **Unblock**.</span></span>

1. <span data-ttu-id="4be75-132">Aprire l'ambiente LCS in cui si desidera aggiungere il servizio.</span><span class="sxs-lookup"><span data-stu-id="4be75-132">Open the LCS environment where you want to add the service.</span></span>

1. <span data-ttu-id="4be75-133">Andare a **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="4be75-133">Go to **Full details**.</span></span>

1. <span data-ttu-id="4be75-134">Scorrere verso il basso fino alla scheda dettaglio **Componenti aggiuntivi dell'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="4be75-134">Scroll down to the **Environment add-ins** FastTab.</span></span>

1. <span data-ttu-id="4be75-135">Selezionare **Installare un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="4be75-135">Select **Install a new add-in**.</span></span>

1. <span data-ttu-id="4be75-136">Selezionare **Servizio di contabilità industriale**.</span><span class="sxs-lookup"><span data-stu-id="4be75-136">Select **Cost accounting service**.</span></span>

1. <span data-ttu-id="4be75-137">Seguire la guida all'installazione e accettare le condizioni.</span><span class="sxs-lookup"><span data-stu-id="4be75-137">Follow the installation guide, and agree to the terms and conditions.</span></span>

1. <span data-ttu-id="4be75-138">Selezionare **Installa**.</span><span class="sxs-lookup"><span data-stu-id="4be75-138">Select **Install**.</span></span>

1. <span data-ttu-id="4be75-139">Nella scheda dettaglio **Componenti aggiuntivi dell'ambiente** viene indicato che il servizio di contabilità industriale è stato installato.</span><span class="sxs-lookup"><span data-stu-id="4be75-139">On the **Environment add-ins** FastTab, you should see that the cost accounting service is being installed.</span></span> <span data-ttu-id="4be75-140">Dopo alcuni minuti, lo stato cambia da **Installazione in corso** in **Installato**.</span><span class="sxs-lookup"><span data-stu-id="4be75-140">After a few minutes, the status should change from **Installing** to **Installed**.</span></span> <span data-ttu-id="4be75-141">Potrebbe essere necessario aggiornare la pagina per vedere questa modifica. A quel punto, il servizio di contabilità industriale è pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="4be75-141">(You might have to refresh the page to see this change.) At that point, the cost accounting service is ready for use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="4be75-142">Impostare l'integrazione</span><span class="sxs-lookup"><span data-stu-id="4be75-142">Set up the integration</span></span>

<span data-ttu-id="4be75-143">Per impostare l'integrazione tra il servizio di contabilità industriale e Dynamics 365 Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="4be75-143">To set up the integration between the cost accounting service and Dynamics 365 Supply Chain Management:</span></span>

1. <span data-ttu-id="4be75-144">Andare a **Amministrazione sistema > Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="4be75-144">Go to **System administration > Feature Management**.</span></span>

1. <span data-ttu-id="4be75-145">Selezionare **Controlla aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="4be75-145">Select **Check for updates**.</span></span>

1. <span data-ttu-id="4be75-146">Aprire la scheda **Tutto** e cercare la funzionalità denominata *Servizio di contabilità industriale*.</span><span class="sxs-lookup"><span data-stu-id="4be75-146">Open the **All** tab and search for the feature named *Cost accounting service*.</span></span>

1. <span data-ttu-id="4be75-147">Selezionare **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="4be75-147">Select **Enable now**.</span></span>

1. <span data-ttu-id="4be75-148">Andare a **Gestione costi> Servizio contabilità industriale > Impostazione > Parametri servizio contabilità industriale > Parametri integrazioni**.</span><span class="sxs-lookup"><span data-stu-id="4be75-148">Go to **Cost management > Cost accounting service > Setup > Cost accounting service parameters > Integrations parameters**.</span></span>

1. <span data-ttu-id="4be75-149">Nel campo **ID applicazione** immettere il seguente codice:</span><span class="sxs-lookup"><span data-stu-id="4be75-149">In the **Application ID** field, enter the following code:</span></span><br> <span data-ttu-id="4be75-150">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span><span class="sxs-lookup"><span data-stu-id="4be75-150">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span></span>

1. <span data-ttu-id="4be75-151">Nel campo **Endpoint del servizio dati** immettere il seguente URL:</span><span class="sxs-lookup"><span data-stu-id="4be75-151">In the **Data service endpoint** field, enter the following URL:</span></span><br>https://operationsdataservice.operations365.dynamics.com/

1. <span data-ttu-id="4be75-152">Nel campo **Endpoint del servizio contabilità industriale** immettere il seguente URL:</span><span class="sxs-lookup"><span data-stu-id="4be75-152">In the **Cost accounting service endpoint** field, enter the following URL:</span></span><br>https://costaccountingservice.operations365.dynamics.com/

1. <span data-ttu-id="4be75-153">Il servizio di contabilità industriale è ora pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="4be75-153">The cost accounting service is now ready for use.</span></span>

## <a name="related-resources"></a><span data-ttu-id="4be75-154">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="4be75-154">Related resources</span></span>

[<span data-ttu-id="4be75-155">Home page del servizio contabilità industriale</span><span class="sxs-lookup"><span data-stu-id="4be75-155">Cost accounting service home page</span></span>](cost-accounting-service-home.md)
