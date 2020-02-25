---
title: Aprire un URL nel POS
description: Questo argomento fornisce una panoramica dei miglioramenti apportati alla funzionalità di ricerca prodotti e clienti in Dynamics 365 Commerce.
author: AamirAllaq
manager: AnnBe
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 137b699d5f60b9b62a5ce9501e3b2a262e60a88f
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022988"
---
# <a name="open-url-in-pos"></a><span data-ttu-id="65f05-103">Aprire l'URL nel POS</span><span class="sxs-lookup"><span data-stu-id="65f05-103">Open URL in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="65f05-104">In questo argomento viene descritto come configurare un pulsante nel Retail POS per aprire un URL.</span><span class="sxs-lookup"><span data-stu-id="65f05-104">This topic describes how you can configure a button in Retail point of sale (POS) to open a URL.</span></span> <span data-ttu-id="65f05-105">Questa funzionalità non richiede una personalizzazione del codice e può essere configurata da qualcuno cha ha un ruolo non sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="65f05-105">This feature does not require a code customization, and can be configured by someone in a non-developer role.</span></span> 

<span data-ttu-id="65f05-106">Questa funzionalità consente la configurazione di un pulsante nel POS, utilizzando la finestra di progettazione della griglia dei pulsanti per aprire un URL.</span><span class="sxs-lookup"><span data-stu-id="65f05-106">This feature allows configuration of a button in POS, using the button grid designer to open a URL.</span></span> <span data-ttu-id="65f05-107">Attualmente, è supportata nelle seguenti configurazioni:</span><span class="sxs-lookup"><span data-stu-id="65f05-107">Currently, this is supported in the following configurations:</span></span>

- <span data-ttu-id="65f05-108">Apertura in una nuova finestra</span><span class="sxs-lookup"><span data-stu-id="65f05-108">Open in new window.</span></span>
- <span data-ttu-id="65f05-109">Apertura nel POS</span><span class="sxs-lookup"><span data-stu-id="65f05-109">Open within POS.</span></span>
- <span data-ttu-id="65f05-110">Apertura di un'app nativa</span><span class="sxs-lookup"><span data-stu-id="65f05-110">Open a native app.</span></span>

## <a name="open-in-new-window"></a><span data-ttu-id="65f05-111">Apertura in nuova finestra</span><span class="sxs-lookup"><span data-stu-id="65f05-111">Open in new window</span></span>

<span data-ttu-id="65f05-112">Questa configurazione definisce se aprire l'URL in una nuova finestra o nell'app.</span><span class="sxs-lookup"><span data-stu-id="65f05-112">This configuration defines whether to open the URL in a new window or within the app.</span></span> <span data-ttu-id="65f05-113">Quando la configurazione prevede l'apertura di un URL Web nell'app, il pannello di navigazione laterale e la barra superiore del POS sono visibili e disponibili per l'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="65f05-113">When configured to open a web URL within the app, the side navigation panel and top bar of POS are visible and available for user interaction.</span></span> <span data-ttu-id="65f05-114">Quando la configurazione prevede l'apertura in una nuova finestra, l'URL verrà aperto in Modern POS per Windows e in una nuova scheda del browser in tutti gli altri client del POS.</span><span class="sxs-lookup"><span data-stu-id="65f05-114">When configured to open in a new window, the URL will open in a new app window on Modern POS for Windows, and in a new browser tab in all other POS clients.</span></span> <span data-ttu-id="65f05-115">Per attivare questa funzionalità, è necessario configurare l'URL con l'opzione **Apri in una nuova finestra** selezionata.</span><span class="sxs-lookup"><span data-stu-id="65f05-115">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

## <a name="open-within-pos"></a><span data-ttu-id="65f05-116">Apertura nel POS</span><span class="sxs-lookup"><span data-stu-id="65f05-116">Open within POS</span></span>

<span data-ttu-id="65f05-117">L'apertura di un URL Web nel POS è attualmente supportata solo per Modern POS per Windows.</span><span class="sxs-lookup"><span data-stu-id="65f05-117">Opening a web URL within POS is currently only supported for Modern POS on Windows.</span></span> <span data-ttu-id="65f05-118">In altri client, questa funzionalità è in fase di sviluppo e verrà integrata con aggiornamenti futuri.</span><span class="sxs-lookup"><span data-stu-id="65f05-118">On other clients, this capability is under development and planned for release in future updates.</span></span> <span data-ttu-id="65f05-119">Per attivare questa funzionalità, è necessario configurare l'URL con l'opzione **Apri in una nuova finestra** non selezionata.</span><span class="sxs-lookup"><span data-stu-id="65f05-119">To enable this, you must configure the URL with the **Open in new window** option not selected.</span></span>

## <a name="open-a-native-app"></a><span data-ttu-id="65f05-120">Apertura di un'app nativa</span><span class="sxs-lookup"><span data-stu-id="65f05-120">Open a native app</span></span>

<span data-ttu-id="65f05-121">Questa configurazione consente inoltre di specificare URL non Web per aprire un'app nativa.</span><span class="sxs-lookup"><span data-stu-id="65f05-121">This feature also allows you to specify non-web URLs to open a native app.</span></span> <span data-ttu-id="65f05-122">Ad esempio, è possibile specificare protocolli URL come MailTo, SIP, IM o MSTEAMS, che potranno quindi essere gestiti dalle app native rispettive nel dispositivo host.</span><span class="sxs-lookup"><span data-stu-id="65f05-122">For example, you can specify URL protocols such as MailTo, SIP, IM, or MSTEAMS, which can then be handled by respective native apps on the host device.</span></span> <span data-ttu-id="65f05-123">Per attivare questa funzionalità, è necessario configurare l'URL con l'opzione **Apri in una nuova finestra** selezionata.</span><span class="sxs-lookup"><span data-stu-id="65f05-123">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

- <span data-ttu-id="65f05-124">Per i computer Windows, vedere [Esportare o importare per impostare associazioni di applicazioni predefinite](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) per impostare le associazioni di protocollo predefinite se si configura il computer mediante DISM.</span><span class="sxs-lookup"><span data-stu-id="65f05-124">For Windows computers, see [Export or Import Default Application Associations](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) to set the default protocol associations if you are setting up your computer using Deployment Image Servicing and Management (DISM).</span></span>
- <span data-ttu-id="65f05-125">Se si utilizza MDM, ad esempio Intune per gestire i computer Windows, vedere [CSP criteri - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span><span class="sxs-lookup"><span data-stu-id="65f05-125">If you are using MDM, such as Intune to manage your Windows computers, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span></span>
- <span data-ttu-id="65f05-126">Se si è uno sviluppatore che crea un sito Web personalizzato, vedere [Avvio di un'app predefinita per un URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span><span class="sxs-lookup"><span data-stu-id="65f05-126">If you are a developer building a custom website, see [Launch the default app for a URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span></span>

## <a name="open-a-native-app-seamlessly"></a><span data-ttu-id="65f05-127">Apertura più agevole di un'app nativa</span><span class="sxs-lookup"><span data-stu-id="65f05-127">Open a native app seamlessly</span></span>

<span data-ttu-id="65f05-128">Windows, Android e IOS consentono inoltre un'apertura più agevole delle app, in base all'associazione di protocollo dell'app.</span><span class="sxs-lookup"><span data-stu-id="65f05-128">Windows, iOS, and Android also allow opening of apps more seamlessly, based on app protocol association.</span></span> <span data-ttu-id="65f05-129">Se l'app in uso non è già configurata per gestire l'apertura da un browser Web, è possibile che questa operazione debba essere eseguita da uno sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="65f05-129">If your app is not already configured to handle opening from a web browser, you may need a developer to configure this.</span></span>

- <span data-ttu-id="65f05-130">Per Windows, vedere [Abilitare le app per i siti Web usando i gestori degli URI delle app](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span><span class="sxs-lookup"><span data-stu-id="65f05-130">For Windows, see [Enable apps for websites using app URI handlers](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span></span>
- <span data-ttu-id="65f05-131">Per IOS, vedere [Universal Links for Developers](https://developer.apple.com/ios/universal-links/)..</span><span class="sxs-lookup"><span data-stu-id="65f05-131">For iOS, see [Universal Links for Developers](https://developer.apple.com/ios/universal-links/).</span></span>
- <span data-ttu-id="65f05-132">Per Android, vedere [Handling Android App Links](https://developer.android.com/training/app-links/)</span><span class="sxs-lookup"><span data-stu-id="65f05-132">For Android, see [Handling Android App Links](https://developer.android.com/training/app-links/).</span></span>

| <span data-ttu-id="65f05-133">Cliente</span><span class="sxs-lookup"><span data-stu-id="65f05-133">Client</span></span>                | <span data-ttu-id="65f05-134">Apri in nuova finestra</span><span class="sxs-lookup"><span data-stu-id="65f05-134">Open in new window</span></span> | <span data-ttu-id="65f05-135">Apertura di un'app nativa</span><span class="sxs-lookup"><span data-stu-id="65f05-135">Open native app</span></span> | <span data-ttu-id="65f05-136">Apertura nel POS</span><span class="sxs-lookup"><span data-stu-id="65f05-136">Open within POS</span></span> | <span data-ttu-id="65f05-137">Dettagli</span><span class="sxs-lookup"><span data-stu-id="65f05-137">Details</span></span>                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| <span data-ttu-id="65f05-138">Modern POS per Windows</span><span class="sxs-lookup"><span data-stu-id="65f05-138">Modern POS on Windows</span></span> | <span data-ttu-id="65f05-139">✓\*</span><span class="sxs-lookup"><span data-stu-id="65f05-139">✓\*</span></span>                | <span data-ttu-id="65f05-140">✓</span><span class="sxs-lookup"><span data-stu-id="65f05-140">✓</span></span>               | <span data-ttu-id="65f05-141">✓</span><span class="sxs-lookup"><span data-stu-id="65f05-141">✓</span></span>              | <span data-ttu-id="65f05-142">\*Apertura in una nuova finestra di Modern POS</span><span class="sxs-lookup"><span data-stu-id="65f05-142">\* Opens in new Modern POS window</span></span> |
| <span data-ttu-id="65f05-143">POS cloud</span><span class="sxs-lookup"><span data-stu-id="65f05-143">Cloud POS</span></span>             | <span data-ttu-id="65f05-144">✓\*</span><span class="sxs-lookup"><span data-stu-id="65f05-144">✓\*</span></span>                | <span data-ttu-id="65f05-145">✓</span><span class="sxs-lookup"><span data-stu-id="65f05-145">✓</span></span>               | <span data-ttu-id="65f05-146">X</span><span class="sxs-lookup"><span data-stu-id="65f05-146">X</span></span>              | <span data-ttu-id="65f05-147">\*Apertura in una nuova scheda del browser</span><span class="sxs-lookup"><span data-stu-id="65f05-147">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="65f05-148">Modern POS per IOS</span><span class="sxs-lookup"><span data-stu-id="65f05-148">Modern POS on iOS</span></span>     | <span data-ttu-id="65f05-149">✓\*</span><span class="sxs-lookup"><span data-stu-id="65f05-149">✓\*</span></span>                | <span data-ttu-id="65f05-150">✓</span><span class="sxs-lookup"><span data-stu-id="65f05-150">✓</span></span>               | <span data-ttu-id="65f05-151">X</span><span class="sxs-lookup"><span data-stu-id="65f05-151">X</span></span>              | <span data-ttu-id="65f05-152">\*Apertura in una nuova scheda del browser</span><span class="sxs-lookup"><span data-stu-id="65f05-152">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="65f05-153">Modern POS per Android</span><span class="sxs-lookup"><span data-stu-id="65f05-153">Modern POS on Android</span></span> | <span data-ttu-id="65f05-154">✓\*</span><span class="sxs-lookup"><span data-stu-id="65f05-154">✓\*</span></span>                | <span data-ttu-id="65f05-155">✓</span><span class="sxs-lookup"><span data-stu-id="65f05-155">✓</span></span>               | <span data-ttu-id="65f05-156">X</span><span class="sxs-lookup"><span data-stu-id="65f05-156">X</span></span>              | <span data-ttu-id="65f05-157">\*Apertura in una nuova scheda del browser</span><span class="sxs-lookup"><span data-stu-id="65f05-157">\* Opens in new browser tab</span></span>        |

## <a name="before-you-begin"></a><span data-ttu-id="65f05-158">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="65f05-158">Before you begin</span></span>

<span data-ttu-id="65f05-159">Prima di iniziare, leggere [Layout delle schermate per il POS](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="65f05-159">Before you begin, review how to configure [Screen layouts for the point of sale (POS)](pos-screen-layouts.md).</span></span>

## <a name="open-url-in-pos"></a><span data-ttu-id="65f05-160">Aprire un URL nel POS</span><span class="sxs-lookup"><span data-stu-id="65f05-160">Open URL in POS</span></span>

<span data-ttu-id="65f05-161">Per configurare un URL per l'apertura nel POS, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="65f05-161">To configure a URL to be opened in POS, perform the following steps.</span></span>

1. <span data-ttu-id="65f05-162">Nella sede centrale, accedere a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> POS \> Layout schermo**.</span><span class="sxs-lookup"><span data-stu-id="65f05-162">In head office, go to **Retail and Commerce \> Channel Setup \> POS Setup \> POS \> Screen Layouts**.</span></span>
2. <span data-ttu-id="65f05-163">Selezionare **Griglie dei pulsanti \> Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="65f05-163">Select **Button Grids \> Designer**.</span></span>
3. <span data-ttu-id="65f05-164">Creare un nuovo pulsante.</span><span class="sxs-lookup"><span data-stu-id="65f05-164">Create a new button.</span></span>
4. <span data-ttu-id="65f05-165">Selezionare le proprietà **Pulsante**.</span><span class="sxs-lookup"><span data-stu-id="65f05-165">Select **Button** properties.</span></span>
5. <span data-ttu-id="65f05-166">Selezionare **Apri URL** come azione.</span><span class="sxs-lookup"><span data-stu-id="65f05-166">Select **Open URL** as the action.</span></span>
6. <span data-ttu-id="65f05-167">Immettere l'URL che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="65f05-167">Enter the URL that you want to use.</span></span>
7. <span data-ttu-id="65f05-168">Specificare se aprire l'URL in una nuova finestra.</span><span class="sxs-lookup"><span data-stu-id="65f05-168">Configure whether to open the URL in a new window.</span></span>
