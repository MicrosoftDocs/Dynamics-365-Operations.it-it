---
title: Aprire un URL nel POS
description: Questo argomento fornisce una panoramica dei miglioramenti apportati alla funzionalità di ricerca prodotti e clienti in Microsoft Dynamics 365 for Retail.
author: AamirAllaq
manager: AnnBe
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: b07406b4e218b45bdde87c4a579814fe0edbc286
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "327092"
---
# <a name="open-url-in-pos"></a><span data-ttu-id="e15a0-103">Aprire l'URL nel POS</span><span class="sxs-lookup"><span data-stu-id="e15a0-103">Open URL in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e15a0-104">In questo argomento viene descritto come configurare un pulsante nel Retail POS per aprire un URL.</span><span class="sxs-lookup"><span data-stu-id="e15a0-104">This topic describes how you can configure a button in Retail point of sale (POS) to open a URL.</span></span> <span data-ttu-id="e15a0-105">Questa funzionalità non richiede una personalizzazione del codice e può essere configurata da qualcuno cha ha un ruolo non sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="e15a0-105">This feature does not require a code customization, and can be configured by someone in a non-developer role.</span></span> <span data-ttu-id="e15a0-106">Questa funzionalità è disponibile solo nella versione Dynamics 365 for Finance and Operations versione 8.1.3 (build 8.1.227.10014) e successive.</span><span class="sxs-lookup"><span data-stu-id="e15a0-106">This feature is available as part of the Dynamics 365 for Finance and Operations version 8.1.3 release (build 8.1.227.10014) and later.</span></span> 

<span data-ttu-id="e15a0-107">Questa funzionalità consente la configurazione di un pulsante nel POS, utilizzando la finestra di progettazione della griglia dei pulsanti per aprire un URL.</span><span class="sxs-lookup"><span data-stu-id="e15a0-107">This feature allows configuration of a button in POS, using the button grid designer to open a URL.</span></span> <span data-ttu-id="e15a0-108">Attualmente, è supportata nelle seguenti configurazioni:</span><span class="sxs-lookup"><span data-stu-id="e15a0-108">Currently, this is supported in the following configurations:</span></span>

- <span data-ttu-id="e15a0-109">Apertura in una nuova finestra</span><span class="sxs-lookup"><span data-stu-id="e15a0-109">Open in new window.</span></span>
- <span data-ttu-id="e15a0-110">Apertura nel POS</span><span class="sxs-lookup"><span data-stu-id="e15a0-110">Open within POS.</span></span>
- <span data-ttu-id="e15a0-111">Apertura di un'app nativa</span><span class="sxs-lookup"><span data-stu-id="e15a0-111">Open a native app.</span></span>

## <a name="open-in-new-window"></a><span data-ttu-id="e15a0-112">Apertura in nuova finestra</span><span class="sxs-lookup"><span data-stu-id="e15a0-112">Open in new window</span></span>

<span data-ttu-id="e15a0-113">Questa configurazione definisce se aprire l'URL in una nuova finestra o nell'app.</span><span class="sxs-lookup"><span data-stu-id="e15a0-113">This configuration defines whether to open the URL in a new window or within the app.</span></span> <span data-ttu-id="e15a0-114">Quando la configurazione prevede l'apertura di un URL Web nell'app, il pannello di navigazione laterale e la barra superiore del POS sono visibili e disponibili per l'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e15a0-114">When configured to open a web URL within the app, the side navigation panel and top bar of POS are visible and available for user interaction.</span></span> <span data-ttu-id="e15a0-115">Quando la configurazione prevede l'apertura in una nuova finestra, l'URL verrà aperto in Modern POS per Windows e in una nuova scheda del browser in tutti gli altri client del POS.</span><span class="sxs-lookup"><span data-stu-id="e15a0-115">When configured to open in a new window, the URL will open in a new app window on Modern POS for Windows, and in a new browser tab in all other POS clients.</span></span> <span data-ttu-id="e15a0-116">Per attivare questa funzionalità, è necessario configurare l'URL con l'opzione **Apri in una nuova finestra** selezionata.</span><span class="sxs-lookup"><span data-stu-id="e15a0-116">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

## <a name="open-within-pos"></a><span data-ttu-id="e15a0-117">Apertura nel POS</span><span class="sxs-lookup"><span data-stu-id="e15a0-117">Open within POS</span></span>

<span data-ttu-id="e15a0-118">L'apertura di un URL Web nel POS è attualmente supportata solo per Modern POS per Windows.</span><span class="sxs-lookup"><span data-stu-id="e15a0-118">Opening a web URL within POS is currently only supported for Modern POS on Windows.</span></span> <span data-ttu-id="e15a0-119">In altri client, questa funzionalità è in fase di sviluppo e verrà integrata con aggiornamenti futuri.</span><span class="sxs-lookup"><span data-stu-id="e15a0-119">On other clients, this capability is under development and planned for release in future updates.</span></span> <span data-ttu-id="e15a0-120">Per attivare questa funzionalità, è necessario configurare l'URL con l'opzione **Apri in una nuova finestra** non selezionata.</span><span class="sxs-lookup"><span data-stu-id="e15a0-120">To enable this, you must configure the URL with the **Open in new window** option not selected.</span></span>

## <a name="open-a-native-app"></a><span data-ttu-id="e15a0-121">Apertura di un'app nativa</span><span class="sxs-lookup"><span data-stu-id="e15a0-121">Open a native app</span></span>

<span data-ttu-id="e15a0-122">Questa configurazione consente inoltre di specificare URL non Web per aprire un'app nativa.</span><span class="sxs-lookup"><span data-stu-id="e15a0-122">This feature also allows you to specify non-web URLs to open a native app.</span></span> <span data-ttu-id="e15a0-123">Ad esempio, è possibile specificare protocolli URL come MailTo, SIP, IM o MSTEAMS, che potranno quindi essere gestiti dalle app native rispettive nel dispositivo host.</span><span class="sxs-lookup"><span data-stu-id="e15a0-123">For example, you can specify URL protocols such as MailTo, SIP, IM, or MSTEAMS, which can then be handled by respective native apps on the host device.</span></span> <span data-ttu-id="e15a0-124">Per attivare questa funzionalità, è necessario configurare l'URL con l'opzione **Apri in una nuova finestra** selezionata.</span><span class="sxs-lookup"><span data-stu-id="e15a0-124">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

- <span data-ttu-id="e15a0-125">Per i computer Windows, vedere [Esportare o importare per impostare associazioni di applicazioni predefinite](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) per impostare le associazioni di protocollo predefinite se si configura il computer mediante DISM.</span><span class="sxs-lookup"><span data-stu-id="e15a0-125">For Windows computers, see [Export or Import Default Application Associations](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) to set the default protocol associations if you are setting up your computer using Deployment Image Servicing and Management (DISM).</span></span>
- <span data-ttu-id="e15a0-126">Se si utilizza MDM, ad esempio Intune per gestire i computer Windows, vedere [CSP criteri - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span><span class="sxs-lookup"><span data-stu-id="e15a0-126">If you are using MDM, such as Intune to manage your Windows computers, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span></span>
- <span data-ttu-id="e15a0-127">Se si è uno sviluppatore che crea un sito Web personalizzato, vedere [Avvio di un'app predefinita per un URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span><span class="sxs-lookup"><span data-stu-id="e15a0-127">If you are a developer building a custom website, see [Launch the default app for a URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span></span>

## <a name="open-a-native-app-seamlessly"></a><span data-ttu-id="e15a0-128">Apertura più agevole di un'app nativa</span><span class="sxs-lookup"><span data-stu-id="e15a0-128">Open a native app seamlessly</span></span>

<span data-ttu-id="e15a0-129">Windows, Android e IOS consentono inoltre un'apertura più agevole delle app, in base all'associazione di protocollo dell'app.</span><span class="sxs-lookup"><span data-stu-id="e15a0-129">Windows, iOS, and Android also allow opening of apps more seamlessly, based on app protocol association.</span></span> <span data-ttu-id="e15a0-130">Se l'app in uso non è già configurata per gestire l'apertura da un browser Web, è possibile che questa operazione debba essere eseguita da uno sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="e15a0-130">If your app is not already configured to handle opening from a web browser, you may need a developer to configure this.</span></span>

- <span data-ttu-id="e15a0-131">Per Windows, vedere [Abilitare le app per i siti Web usando i gestori degli URI delle app](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span><span class="sxs-lookup"><span data-stu-id="e15a0-131">For Windows, see [Enable apps for websites using app URI handlers](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span></span>
- <span data-ttu-id="e15a0-132">Per IOS, vedere [Universal Links for Developers](https://developer.apple.com/ios/universal-links/)..</span><span class="sxs-lookup"><span data-stu-id="e15a0-132">For iOS, see [Universal Links for Developers](https://developer.apple.com/ios/universal-links/).</span></span>
- <span data-ttu-id="e15a0-133">Per Android, vedere [Handling Android App Links](https://developer.android.com/training/app-links/)</span><span class="sxs-lookup"><span data-stu-id="e15a0-133">For Android, see [Handling Android App Links](https://developer.android.com/training/app-links/).</span></span>

| <span data-ttu-id="e15a0-134">Cliente</span><span class="sxs-lookup"><span data-stu-id="e15a0-134">Client</span></span>                | <span data-ttu-id="e15a0-135">Apri in nuova finestra</span><span class="sxs-lookup"><span data-stu-id="e15a0-135">Open in new window</span></span> | <span data-ttu-id="e15a0-136">Apertura di un'app nativa</span><span class="sxs-lookup"><span data-stu-id="e15a0-136">Open native app</span></span> | <span data-ttu-id="e15a0-137">Apertura nel POS</span><span class="sxs-lookup"><span data-stu-id="e15a0-137">Open within POS</span></span> | <span data-ttu-id="e15a0-138">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e15a0-138">Details</span></span>                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| <span data-ttu-id="e15a0-139">Modern POS per Windows</span><span class="sxs-lookup"><span data-stu-id="e15a0-139">Modern POS on Windows</span></span> | <span data-ttu-id="e15a0-140">✓\*</span><span class="sxs-lookup"><span data-stu-id="e15a0-140">✓\*</span></span>                | <span data-ttu-id="e15a0-141">✓</span><span class="sxs-lookup"><span data-stu-id="e15a0-141">✓</span></span>               | <span data-ttu-id="e15a0-142">✓</span><span class="sxs-lookup"><span data-stu-id="e15a0-142">✓</span></span>              | <span data-ttu-id="e15a0-143">\*Apertura in una nuova finestra di Modern POS</span><span class="sxs-lookup"><span data-stu-id="e15a0-143">\* Opens in new Modern POS window</span></span> |
| <span data-ttu-id="e15a0-144">POS cloud</span><span class="sxs-lookup"><span data-stu-id="e15a0-144">Cloud POS</span></span>             | <span data-ttu-id="e15a0-145">✓\*</span><span class="sxs-lookup"><span data-stu-id="e15a0-145">✓\*</span></span>                | <span data-ttu-id="e15a0-146">✓</span><span class="sxs-lookup"><span data-stu-id="e15a0-146">✓</span></span>               | <span data-ttu-id="e15a0-147">X</span><span class="sxs-lookup"><span data-stu-id="e15a0-147">X</span></span>              | <span data-ttu-id="e15a0-148">\*Apertura in una nuova scheda del browser</span><span class="sxs-lookup"><span data-stu-id="e15a0-148">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="e15a0-149">Modern POS per IOS</span><span class="sxs-lookup"><span data-stu-id="e15a0-149">Modern POS on iOS</span></span>     | <span data-ttu-id="e15a0-150">✓\*</span><span class="sxs-lookup"><span data-stu-id="e15a0-150">✓\*</span></span>                | <span data-ttu-id="e15a0-151">✓</span><span class="sxs-lookup"><span data-stu-id="e15a0-151">✓</span></span>               | <span data-ttu-id="e15a0-152">X</span><span class="sxs-lookup"><span data-stu-id="e15a0-152">X</span></span>              | <span data-ttu-id="e15a0-153">\*Apertura in una nuova scheda del browser</span><span class="sxs-lookup"><span data-stu-id="e15a0-153">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="e15a0-154">Modern POS per Android</span><span class="sxs-lookup"><span data-stu-id="e15a0-154">Modern POS on Android</span></span> | <span data-ttu-id="e15a0-155">✓\*</span><span class="sxs-lookup"><span data-stu-id="e15a0-155">✓\*</span></span>                | <span data-ttu-id="e15a0-156">✓</span><span class="sxs-lookup"><span data-stu-id="e15a0-156">✓</span></span>               | <span data-ttu-id="e15a0-157">X</span><span class="sxs-lookup"><span data-stu-id="e15a0-157">X</span></span>              | <span data-ttu-id="e15a0-158">\*Apertura in una nuova scheda del browser</span><span class="sxs-lookup"><span data-stu-id="e15a0-158">\* Opens in new browser tab</span></span>        |

## <a name="before-you-begin"></a><span data-ttu-id="e15a0-159">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e15a0-159">Before you begin</span></span>

<span data-ttu-id="e15a0-160">Prima di iniziare, leggere [Layout delle schermate per il POS](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="e15a0-160">Before you begin, review how to configure [Screen layouts for the point of sale (POS)](pos-screen-layouts.md).</span></span>

## <a name="open-url-in-pos"></a><span data-ttu-id="e15a0-161">Aprire un URL nel POS</span><span class="sxs-lookup"><span data-stu-id="e15a0-161">Open URL in POS</span></span>

<span data-ttu-id="e15a0-162">Per configurare un URL per l'apertura nel POS, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e15a0-162">To configure a URL to be opened in POS, perform the following steps.</span></span>

1. <span data-ttu-id="e15a0-163">Nella sede centrale, accedere a **Vendita al dettaglio \> Impostazione canale \> Impostazione POS \> POS \> Layout schermo**.</span><span class="sxs-lookup"><span data-stu-id="e15a0-163">In head office, go to **Retail \> Channel Setup \> POS Setup \> POS \> Screen Layouts**.</span></span>
2. <span data-ttu-id="e15a0-164">Selezionare **Griglie dei pulsanti \> Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="e15a0-164">Select **Button Grids \> Designer**.</span></span>
3. <span data-ttu-id="e15a0-165">Creare un nuovo pulsante.</span><span class="sxs-lookup"><span data-stu-id="e15a0-165">Create a new button.</span></span>
4. <span data-ttu-id="e15a0-166">Selezionare le proprietà **Pulsante**.</span><span class="sxs-lookup"><span data-stu-id="e15a0-166">Select **Button** properties.</span></span>
5. <span data-ttu-id="e15a0-167">Selezionare **Apri URL** come azione.</span><span class="sxs-lookup"><span data-stu-id="e15a0-167">Select **Open URL** as the action.</span></span>
6. <span data-ttu-id="e15a0-168">Immettere l'URL che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e15a0-168">Enter the URL that you want to use.</span></span>
7. <span data-ttu-id="e15a0-169">Specificare se aprire l'URL in una nuova finestra.</span><span class="sxs-lookup"><span data-stu-id="e15a0-169">Configure whether to open the URL in a new window.</span></span>
