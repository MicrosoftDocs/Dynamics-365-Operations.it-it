---
title: Aprire un URL nel POS
description: "Questo argomento fornisce una panoramica dei miglioramenti apportati alla funzionalità di ricerca prodotti e clienti in Microsoft Dynamics 365 for Retail."
author: AamirAllaq
manager: AnnBe
ms.date: 11/14/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.reviewer: sericks
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: d2b692ac86244eca31780a558112167391fc6d77
ms.contentlocale: it-it
ms.lasthandoff: 01/04/2019

---

# <a name="open-url-in-pos"></a><span data-ttu-id="46f2d-103">Aprire un URL nel POS</span><span class="sxs-lookup"><span data-stu-id="46f2d-103">Open URL in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="46f2d-104">In questo argomento viene descritto come configurare un pulsante nel Retail POS per aprire un URL.</span><span class="sxs-lookup"><span data-stu-id="46f2d-104">This topic describes how you can configure a button in Retail point of sale (POS) to open a URL.</span></span> <span data-ttu-id="46f2d-105">Questa funzionalità non richiede una personalizzazione del codice e può essere configurata da qualcuno cha ha un ruolo non sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="46f2d-105">This feature does not require a code customization, and can be configured by someone in a non-developer role.</span></span>

<span data-ttu-id="46f2d-106">Questa funzionalità consente la configurazione di un pulsante nel POS, utilizzando la finestra di progettazione della griglia dei pulsanti per aprire un URL.</span><span class="sxs-lookup"><span data-stu-id="46f2d-106">This feature allows configuration of a button in POS, using the button grid designer to open a URL.</span></span> <span data-ttu-id="46f2d-107">Attualmente, è supportata nelle seguenti configurazioni:</span><span class="sxs-lookup"><span data-stu-id="46f2d-107">Currently, this is supported in the following configurations:</span></span>

- <span data-ttu-id="46f2d-108">Apertura in una nuova finestra</span><span class="sxs-lookup"><span data-stu-id="46f2d-108">Open in new window.</span></span>
- <span data-ttu-id="46f2d-109">Apertura nel POS</span><span class="sxs-lookup"><span data-stu-id="46f2d-109">Open within POS.</span></span>
- <span data-ttu-id="46f2d-110">Apertura di un'app nativa</span><span class="sxs-lookup"><span data-stu-id="46f2d-110">Open a native app.</span></span>

## <a name="open-in-new-window"></a><span data-ttu-id="46f2d-111">Apertura in nuova finestra</span><span class="sxs-lookup"><span data-stu-id="46f2d-111">Open in new window</span></span>

<span data-ttu-id="46f2d-112">Questa configurazione definisce se aprire l'URL in una nuova finestra o nell'app.</span><span class="sxs-lookup"><span data-stu-id="46f2d-112">This configuration defines whether to open the URL in a new window or within the app.</span></span> <span data-ttu-id="46f2d-113">Quando la configurazione prevede l'apertura di un URL Web nell'app, il pannello di navigazione laterale e la barra superiore del POS sono visibili e disponibili per l'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="46f2d-113">When configured to open a web URL within the app, the side navigation panel and top bar of POS are visible and available for user interaction.</span></span> <span data-ttu-id="46f2d-114">Quando la configurazione prevede l'apertura in una nuova finestra, l'URL verrà aperto in Modern POS per Windows e in una nuova scheda del browser in tutti gli altri client del POS.</span><span class="sxs-lookup"><span data-stu-id="46f2d-114">When configured to open in a new window, the URL will open in a new app window on Modern POS for Windows, and in a new browser tab in all other POS clients.</span></span> <span data-ttu-id="46f2d-115">Per attivare questa funzionalità, è necessario configurare l'URL con l'opzione **Apri in una nuova finestra** selezionata.</span><span class="sxs-lookup"><span data-stu-id="46f2d-115">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

## <a name="open-within-pos"></a><span data-ttu-id="46f2d-116">Apertura nel POS</span><span class="sxs-lookup"><span data-stu-id="46f2d-116">Open within POS</span></span>

<span data-ttu-id="46f2d-117">L'apertura di un URL Web nel POS è attualmente supportata solo per Modern POS per Windows.</span><span class="sxs-lookup"><span data-stu-id="46f2d-117">Opening a web URL within POS is currently only supported for Modern POS on Windows.</span></span> <span data-ttu-id="46f2d-118">In altri client, questa funzionalità è in fase di sviluppo e verrà integrata con aggiornamenti futuri.</span><span class="sxs-lookup"><span data-stu-id="46f2d-118">On other clients, this capability is under development and planned for release in future updates.</span></span> <span data-ttu-id="46f2d-119">Per attivare questa funzionalità, è necessario configurare l'URL con l'opzione **Apri in una nuova finestra** non selezionata.</span><span class="sxs-lookup"><span data-stu-id="46f2d-119">To enable this, you must configure the URL with the **Open in new window** option not selected.</span></span>

## <a name="open-a-native-app"></a><span data-ttu-id="46f2d-120">Apertura di un'app nativa</span><span class="sxs-lookup"><span data-stu-id="46f2d-120">Open a native app</span></span>

<span data-ttu-id="46f2d-121">Questa configurazione consente inoltre di specificare URL non Web per aprire un'app nativa.</span><span class="sxs-lookup"><span data-stu-id="46f2d-121">This feature also allows you to specify non-web URLs to open a native app.</span></span> <span data-ttu-id="46f2d-122">Ad esempio, è possibile specificare protocolli URL come MailTo, SIP, IM o MSTEAMS, che potranno quindi essere gestiti dalle app native rispettive nel dispositivo host.</span><span class="sxs-lookup"><span data-stu-id="46f2d-122">For example, you can specify URL protocols such as MailTo, SIP, IM, or MSTEAMS, which can then be handled by respective native apps on the host device.</span></span> <span data-ttu-id="46f2d-123">Per attivare questa funzionalità, è necessario configurare l'URL con l'opzione **Apri in una nuova finestra** selezionata.</span><span class="sxs-lookup"><span data-stu-id="46f2d-123">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

- <span data-ttu-id="46f2d-124">Per i computer Windows, vedere [Esportare o importare per impostare associazioni di applicazioni predefinite](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) per impostare le associazioni di protocollo predefinite se si configura il computer mediante DISM.</span><span class="sxs-lookup"><span data-stu-id="46f2d-124">For Windows computers, see [Export or Import Default Application Associations](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) to set the default protocol associations if you are setting up your computer using Deployment Image Servicing and Management (DISM).</span></span>
- <span data-ttu-id="46f2d-125">Se si utilizza MDM, ad esempio Intune per gestire i computer Windows, vedere [CSP criteri - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span><span class="sxs-lookup"><span data-stu-id="46f2d-125">If you are using MDM, such as Intune to manage your Windows computers, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span></span>
- <span data-ttu-id="46f2d-126">Se si è uno sviluppatore che crea un sito Web personalizzato, vedere [Avvio di un'app predefinita per un URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span><span class="sxs-lookup"><span data-stu-id="46f2d-126">If you are a developer building a custom website, see [Launch the default app for a URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span></span>

## <a name="open-a-native-app-seamlessly"></a><span data-ttu-id="46f2d-127">Apertura più agevole di un'app nativa</span><span class="sxs-lookup"><span data-stu-id="46f2d-127">Open a native app seamlessly</span></span>

<span data-ttu-id="46f2d-128">Windows, Android e IOS consentono inoltre un'apertura più agevole delle app, in base all'associazione di protocollo dell'app.</span><span class="sxs-lookup"><span data-stu-id="46f2d-128">Windows, iOS, and Android also allow opening of apps more seamlessly, based on app protocol association.</span></span> <span data-ttu-id="46f2d-129">Se l'app in uso non è già configurata per gestire l'apertura da un browser Web, è possibile che questa operazione debba essere eseguita da uno sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="46f2d-129">If your app is not already configured to handle opening from a web browser, you may need a developer to configure this.</span></span>

- <span data-ttu-id="46f2d-130">Per Windows, vedere [Abilitare le app per i siti Web usando i gestori degli URI delle app](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span><span class="sxs-lookup"><span data-stu-id="46f2d-130">For Windows, see [Enable apps for websites using app URI handlers](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span></span>
- <span data-ttu-id="46f2d-131">Per IOS, vedere [Universal Links for Developers](https://developer.apple.com/ios/universal-links/)..</span><span class="sxs-lookup"><span data-stu-id="46f2d-131">For iOS, see [Universal Links for Developers](https://developer.apple.com/ios/universal-links/).</span></span>
- <span data-ttu-id="46f2d-132">Per Android, vedere [Handling Android App Links](https://developer.android.com/training/app-links/).</span><span class="sxs-lookup"><span data-stu-id="46f2d-132">For Android, see [Handling Android App Links](https://developer.android.com/training/app-links/).</span></span>

| <span data-ttu-id="46f2d-133">Client</span><span class="sxs-lookup"><span data-stu-id="46f2d-133">Client</span></span>                | <span data-ttu-id="46f2d-134">Apri in nuova finestra</span><span class="sxs-lookup"><span data-stu-id="46f2d-134">Open in new window</span></span> | <span data-ttu-id="46f2d-135">Apertura di un'app nativa</span><span class="sxs-lookup"><span data-stu-id="46f2d-135">Open native app</span></span> | <span data-ttu-id="46f2d-136">Apertura nel POS</span><span class="sxs-lookup"><span data-stu-id="46f2d-136">Open within POS</span></span> | <span data-ttu-id="46f2d-137">Dettagli</span><span class="sxs-lookup"><span data-stu-id="46f2d-137">Details</span></span>                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| <span data-ttu-id="46f2d-138">Modern POS per Windows</span><span class="sxs-lookup"><span data-stu-id="46f2d-138">Modern POS on Windows</span></span> | <span data-ttu-id="46f2d-139">✓\*</span><span class="sxs-lookup"><span data-stu-id="46f2d-139">✓\*</span></span>                | <span data-ttu-id="46f2d-140">✓</span><span class="sxs-lookup"><span data-stu-id="46f2d-140">✓</span></span>               | <span data-ttu-id="46f2d-141">✓</span><span class="sxs-lookup"><span data-stu-id="46f2d-141">✓</span></span>              | <span data-ttu-id="46f2d-142">\*Apertura in una nuova finestra di Modern POS</span><span class="sxs-lookup"><span data-stu-id="46f2d-142">\* Opens in new Modern POS window</span></span> |
| <span data-ttu-id="46f2d-143">POS cloud</span><span class="sxs-lookup"><span data-stu-id="46f2d-143">Cloud POS</span></span>             | <span data-ttu-id="46f2d-144">✓\*</span><span class="sxs-lookup"><span data-stu-id="46f2d-144">✓\*</span></span>                | <span data-ttu-id="46f2d-145">✓</span><span class="sxs-lookup"><span data-stu-id="46f2d-145">✓</span></span>               | <span data-ttu-id="46f2d-146">X</span><span class="sxs-lookup"><span data-stu-id="46f2d-146">X</span></span>              | <span data-ttu-id="46f2d-147">\*Apertura in una nuova scheda del browser</span><span class="sxs-lookup"><span data-stu-id="46f2d-147">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="46f2d-148">Modern POS per IOS</span><span class="sxs-lookup"><span data-stu-id="46f2d-148">Modern POS on iOS</span></span>     | <span data-ttu-id="46f2d-149">✓\*</span><span class="sxs-lookup"><span data-stu-id="46f2d-149">✓\*</span></span>                | <span data-ttu-id="46f2d-150">✓</span><span class="sxs-lookup"><span data-stu-id="46f2d-150">✓</span></span>               | <span data-ttu-id="46f2d-151">X</span><span class="sxs-lookup"><span data-stu-id="46f2d-151">X</span></span>              | <span data-ttu-id="46f2d-152">\*Apertura in una nuova scheda del browser</span><span class="sxs-lookup"><span data-stu-id="46f2d-152">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="46f2d-153">Modern POS per Android</span><span class="sxs-lookup"><span data-stu-id="46f2d-153">Modern POS on Android</span></span> | <span data-ttu-id="46f2d-154">✓\*</span><span class="sxs-lookup"><span data-stu-id="46f2d-154">✓\*</span></span>                | <span data-ttu-id="46f2d-155">✓</span><span class="sxs-lookup"><span data-stu-id="46f2d-155">✓</span></span>               | <span data-ttu-id="46f2d-156">X</span><span class="sxs-lookup"><span data-stu-id="46f2d-156">X</span></span>              | <span data-ttu-id="46f2d-157">\*Apertura in una nuova scheda del browser</span><span class="sxs-lookup"><span data-stu-id="46f2d-157">\* Opens in new browser tab</span></span>        |

## <a name="before-you-begin"></a><span data-ttu-id="46f2d-158">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="46f2d-158">Before you begin</span></span>

<span data-ttu-id="46f2d-159">Prima di iniziare, leggere [Layout delle schermate per il POS](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="46f2d-159">Before you begin, review how to configure [Screen layouts for the point of sale (POS)](pos-screen-layouts.md).</span></span>

## <a name="open-url-in-pos"></a><span data-ttu-id="46f2d-160">Aprire un URL nel POS</span><span class="sxs-lookup"><span data-stu-id="46f2d-160">Open URL in POS</span></span>

<span data-ttu-id="46f2d-161">Per configurare un URL per l'apertura nel POS, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="46f2d-161">To configure a URL to be opened in POS, perform the following steps.</span></span>

1. <span data-ttu-id="46f2d-162">Nella sede centrale, accedere a **Vendita al dettaglio \> Impostazione canale \> Impostazione POS \> POS \> Layout schermo**.</span><span class="sxs-lookup"><span data-stu-id="46f2d-162">In head office, go to **Retail \> Channel Setup \> POS Setup \> POS \> Screen Layouts**.</span></span>
2. <span data-ttu-id="46f2d-163">Selezionare **Griglie dei pulsanti \> Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="46f2d-163">Select **Button Grids \> Designer**.</span></span>
3. <span data-ttu-id="46f2d-164">Creare un nuovo pulsante.</span><span class="sxs-lookup"><span data-stu-id="46f2d-164">Create a new button.</span></span>
4. <span data-ttu-id="46f2d-165">Selezionare le proprietà **Pulsante**.</span><span class="sxs-lookup"><span data-stu-id="46f2d-165">Select **Button** properties.</span></span>
5. <span data-ttu-id="46f2d-166">Selezionare **Apri URL** come azione.</span><span class="sxs-lookup"><span data-stu-id="46f2d-166">Select **Open URL** as the action.</span></span>
6. <span data-ttu-id="46f2d-167">Immettere l'URL che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="46f2d-167">Enter the URL that you want to use.</span></span>
7. <span data-ttu-id="46f2d-168">Specificare se aprire l'URL in una nuova finestra.</span><span class="sxs-lookup"><span data-stu-id="46f2d-168">Configure whether to open the URL in a new window.</span></span>

