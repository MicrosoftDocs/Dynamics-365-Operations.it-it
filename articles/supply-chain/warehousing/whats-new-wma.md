---
title: Novità o modifiche nell'app per dispositivi mobili Warehouse Management
description: Questo argomento elenca le funzionalità nuove e modificate per ogni versione rilasciata dell'app per dispositivi mobili Warehouse Management per Microsoft Dynamics 365 Supply Chain Management.
author: ivanv-microsoft
ms.date: 06/07/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 61124728942c0b8162de9f687ae752773c47d07e
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261784"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="dfc28-103">Novità o modifiche nell'app per dispositivi mobili Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="dfc28-103">What's new or changed in the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dfc28-104">Questo argomento elenca le funzionalità nuove, le correzioni, i miglioramenti e i problemi noti per ogni versione rilasciata dell'app per dispositivi mobili Warehouse Management per Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="dfc28-104">This topic lists new features, fixes, improvements, and known issues for each released version of the Warehouse Management mobile app for Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="version-2060"></a><span data-ttu-id="dfc28-105">Versione 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="dfc28-105">Version 2.0.6.0</span></span>

### <a name="new-features-fixes-and-improvements-in-version-2060"></a><span data-ttu-id="dfc28-106">Nuove funzionalità, correzioni e miglioramenti nella versione 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="dfc28-106">New features, fixes, and improvements in version 2.0.6.0</span></span>

<span data-ttu-id="dfc28-107">Questa versione introduce le seguenti nuove funzionalità, correzioni e miglioramenti:</span><span class="sxs-lookup"><span data-stu-id="dfc28-107">This version introduces the following new features, fixes, and improvements:</span></span>

- <span data-ttu-id="dfc28-108">La modalità demo ora mostra tutte le etichette nella lingua del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dfc28-108">Demo mode now shows all labels in the device language.</span></span>
- <span data-ttu-id="dfc28-109">È meno probabile che venga visualizzato il seguente messaggio di errore: "Impossibile trovare una vista adatta per la dimensione specificata".</span><span class="sxs-lookup"><span data-stu-id="dfc28-109">You're less likely to receive the following error message: "Cannot find a suitable view for the specified size."</span></span>
- <span data-ttu-id="dfc28-110">L'altezza minima per le schede di lavoro è stata aumentata (nei casi in cui sono configurati al massimo tre campi per la visualizzazione nell'elenco di lavoro).</span><span class="sxs-lookup"><span data-stu-id="dfc28-110">The minimum height for work cards has been increased (for cases where three or fewer fields are configured to appear in the work list).</span></span>
- <span data-ttu-id="dfc28-111">I margini (dissolvenza) nella parte inferiore delle schede dei dettagli sono stati migliorati.</span><span class="sxs-lookup"><span data-stu-id="dfc28-111">Margins (fade out) at the bottom of details cards have been improved.</span></span>
- <span data-ttu-id="dfc28-112">I simboli non validi nei file XML scambiati con il server ora vengono gestiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="dfc28-112">Invalid symbols in XML files that are exchanged with the server are now handled gracefully.</span></span> <span data-ttu-id="dfc28-113">Ad esempio, i caratteri non stampabili ora vengono gestiti correttamente e non causano più il blocco dell'app.</span><span class="sxs-lookup"><span data-stu-id="dfc28-113">(For example, non-printable characters are now handled gracefully and no longer cause the app to stop responding.)</span></span>
- <span data-ttu-id="dfc28-114">Gli errori HTTP (come "errore 503") quando viene inviata una richiesta al server ora vengono gestiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="dfc28-114">HTTP errors (such as "error 503") when a server request is submitted are now handled gracefully.</span></span>
- <span data-ttu-id="dfc28-115">Mentre viene visualizzato un errore, l'elenco delle opzioni non viene più visualizzato automaticamente per i controlli della casella combinata.</span><span class="sxs-lookup"><span data-stu-id="dfc28-115">While an error is being shown, the options list is no longer automatically shown for combo box controls.</span></span>
- <span data-ttu-id="dfc28-116">L'app non smette più di rispondere a causa dell'orientamento dello schermo selezionato nelle impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="dfc28-116">The app no longer stops responding because of the display orientation that is selected in user settings.</span></span>
- <span data-ttu-id="dfc28-117">Le immagini dei prodotti vengono ora mostrate negli ambienti self-service.</span><span class="sxs-lookup"><span data-stu-id="dfc28-117">Product images are now shown in self-service environments.</span></span> <span data-ttu-id="dfc28-118">Questa modifica si applica solo alle versioni a bassa risoluzione.</span><span class="sxs-lookup"><span data-stu-id="dfc28-118">(This change applies to low-resolution versions only.</span></span> <span data-ttu-id="dfc28-119">Il servizio di gestione dei file non supporta le immagini a grandezza naturale negli ambienti self-service.</span><span class="sxs-lookup"><span data-stu-id="dfc28-119">The file management service doesn't support full-sized images in self-service environments.)</span></span>
- <span data-ttu-id="dfc28-120">È stato risolto un problema che riguardava il prelievo breve a quantità zero.</span><span class="sxs-lookup"><span data-stu-id="dfc28-120">An issue that involved zero-quantity short picks has been fixed.</span></span>
- <span data-ttu-id="dfc28-121">L'app non si interrompe più quando una scheda dei dettagli mostra più campi identici.</span><span class="sxs-lookup"><span data-stu-id="dfc28-121">The app no longer stops responding when a details card shows multiple identical fields.</span></span>

### <a name="known-issues-in-version-2060"></a><span data-ttu-id="dfc28-122">Problemi noti nella versione 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="dfc28-122">Known issues in version 2.0.6.0</span></span>

<span data-ttu-id="dfc28-123">In questa versione sono presenti i seguenti problemi noti:</span><span class="sxs-lookup"><span data-stu-id="dfc28-123">The following known issues exist in this version:</span></span>

- <span data-ttu-id="dfc28-124">L'app (in particolare l'elenco di lavoro) diventa più lenta nel tempo.</span><span class="sxs-lookup"><span data-stu-id="dfc28-124">The app (especially the work list) becomes slower over time.</span></span>
- <span data-ttu-id="dfc28-125">**Versione Windows:** Quando si utilizza una pistola USB per la scansione su Windows, i risultati incoerenti causano la confusione dei simboli scansionati.</span><span class="sxs-lookup"><span data-stu-id="dfc28-125">**Windows version:** When a USB gun is used for scanning on Windows, inconsistent results cause scanned symbols to be mixed up.</span></span>

## <a name="version-2050"></a><span data-ttu-id="dfc28-126">Versione 2.0.5.0</span><span class="sxs-lookup"><span data-stu-id="dfc28-126">Version 2.0.5.0</span></span>

<span data-ttu-id="dfc28-127">Questa versione introduce le seguenti nuove funzionalità, correzioni e miglioramenti:</span><span class="sxs-lookup"><span data-stu-id="dfc28-127">This version introduces the following new features, fixes, and improvements:</span></span>

- <span data-ttu-id="dfc28-128">Il segreto del client non è più nascosto nella configurazione delle impostazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="dfc28-128">The client secret is no longer hidden in the connection settings setup.</span></span>
- <span data-ttu-id="dfc28-129">Ora puoi premere a lungo su qualsiasi testo per vederlo completamente.</span><span class="sxs-lookup"><span data-stu-id="dfc28-129">You can now long-press on any text to see it fully.</span></span>
- <span data-ttu-id="dfc28-130">Il messaggio di errore quando mancano le autorizzazioni di archiviazione è stato migliorato.</span><span class="sxs-lookup"><span data-stu-id="dfc28-130">The error message when storage permissions are missing has been improved.</span></span>
- <span data-ttu-id="dfc28-131">Sono state aggiunte nuove sequenze di controllo per alcuni flussi.</span><span class="sxs-lookup"><span data-stu-id="dfc28-131">New control sequences have been added for some flows.</span></span>
- <span data-ttu-id="dfc28-132">Il pulsante di invio non diventa più erroneamente disponibile a causa delle dimensioni della finestra.</span><span class="sxs-lookup"><span data-stu-id="dfc28-132">The submit button no longer incorrectly becomes available because of the window size.</span></span>
- <span data-ttu-id="dfc28-133">I dispositivi di scorrimento ora possono procedere su schermi più piccoli quando vengono utilizzati pulsanti di dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="dfc28-133">Sliders can now proceed on smaller screens when larger button sizes are used.</span></span>
- <span data-ttu-id="dfc28-134">La sovrapposizione di quattro pulsanti non viene più tagliata.</span><span class="sxs-lookup"><span data-stu-id="dfc28-134">The four-button overlay is no longer cut off.</span></span>
- <span data-ttu-id="dfc28-135">La tastiera ora supporta il pulsante di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="dfc28-135">The keyboard now supports the delete button.</span></span>
- <span data-ttu-id="dfc28-136">È stato risolto un problema di luminosità che poteva verificarsi quando si preme la tastiera.</span><span class="sxs-lookup"><span data-stu-id="dfc28-136">A brightness issue that could occur when the keyboard is pressed has been fixed.</span></span>
- <span data-ttu-id="dfc28-137">Sono stati risolti vari problemi relativi ai dati demo.</span><span class="sxs-lookup"><span data-stu-id="dfc28-137">Various demo data issues have been fixed.</span></span>
- <span data-ttu-id="dfc28-138">È stato risolto un problema che riguardava i campi numerici nella pagina dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="dfc28-138">An issue that affected numeric fields on the details page has been fixed.</span></span>
- <span data-ttu-id="dfc28-139">La tastiera a schermo non scompare più occasionalmente su alcuni dispositivi.</span><span class="sxs-lookup"><span data-stu-id="dfc28-139">The screen keyboard no longer occasionally disappears on some devices.</span></span>
- <span data-ttu-id="dfc28-140">Sono stati corretti vari bug dell'interfaccia utente (UI), come i bug che interessavano il colore e il posizionamento dello sfondo.</span><span class="sxs-lookup"><span data-stu-id="dfc28-140">Various user interface (UI) bugs have been fixed, such as bugs that affected the background color and positioning.</span></span>
- <span data-ttu-id="dfc28-141">L'interfaccia utente in lingua russa è stata migliorata.</span><span class="sxs-lookup"><span data-stu-id="dfc28-141">The Russian-language UI has been improved.</span></span>
- <span data-ttu-id="dfc28-142">Sono stati risolti vari problemi che causavano il blocco del sistema.</span><span class="sxs-lookup"><span data-stu-id="dfc28-142">Various issues that caused the system to stop responding have been fixed.</span></span>
- <span data-ttu-id="dfc28-143">È stato risolto un problema relativo alla riapertura della calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="dfc28-143">An issue that was related to reopening the calculator has been fixed.</span></span>
- <span data-ttu-id="dfc28-144">**Versione Android:** Un problema che causava l'interruzione di Android 4.4 all'avvio è stato corretto.</span><span class="sxs-lookup"><span data-stu-id="dfc28-144">**Android version:** An issue that caused Android 4.4 to stop responding on startup has been fixed.</span></span>
- <span data-ttu-id="dfc28-145">**Versione Android:** Il ridimensionamento minimo è stato ridotto al 50 percento.</span><span class="sxs-lookup"><span data-stu-id="dfc28-145">**Android version:** Minimum scaling has been reduced to 50 percent.</span></span>

## <a name="version-2040"></a><span data-ttu-id="dfc28-146">Versione 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="dfc28-146">Version 2.0.4.0</span></span>

<span data-ttu-id="dfc28-147">La versione 2.0.4.0 è stata la prima versione generalmente disponibile dell'app per dispositivi mobili Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="dfc28-147">Version 2.0.4.0 was the first generally available release of the Warehouse Management mobile app.</span></span>

### <a name="new-features-fixes-and-improvements-in-version-2040"></a><span data-ttu-id="dfc28-148">Nuove funzionalità, correzioni e miglioramenti nella versione 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="dfc28-148">New features, fixes, and improvements in version 2.0.4.0</span></span>

<span data-ttu-id="dfc28-149">Questa versione introduce le seguenti nuove funzionalità, correzioni e miglioramenti che non erano disponibili nella versione di anteprima:</span><span class="sxs-lookup"><span data-stu-id="dfc28-149">This version introduces the following new features, fixes, and improvements that weren't available in the preview version:</span></span>

- <span data-ttu-id="dfc28-150">Se una scheda dettagli include due etichette con dati identici, una delle etichette è nascosta.</span><span class="sxs-lookup"><span data-stu-id="dfc28-150">If a details card includes two labels that have identical data, one of the labels is hidden.</span></span>
- <span data-ttu-id="dfc28-151">I caratteri speciali ora vengono mostrati per impostazione predefinita e l'opzione per nasconderli è stata rimossa dalle impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="dfc28-151">Special characters are now shown by default, and the option to hide them has been removed from user settings.</span></span>
- <span data-ttu-id="dfc28-152">I pulsanti di invio disabilitati ora vengono mostrati come non disponibili nella visualizzazione compatta dei palmari.</span><span class="sxs-lookup"><span data-stu-id="dfc28-152">Disabled submit buttons are now shown as unavailable in compact arm-held view.</span></span>
- <span data-ttu-id="dfc28-153">Una modifica alla logica di sequenza per i controlli garantisce un ridimensionamento più fluido tra i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="dfc28-153">A change to the sequencing logic for controls ensures smoother scaling across devices.</span></span> <span data-ttu-id="dfc28-154">Pertanto, è meno necessario regolare la scala dei caratteri o dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="dfc28-154">Therefore, there is less need to adjust the scaling of fonts or buttons.</span></span>
- <span data-ttu-id="dfc28-155">Il tema del colore predefinito è stato modificato in *Scuro*.</span><span class="sxs-lookup"><span data-stu-id="dfc28-155">The default color theme has been changed to *Dark*.</span></span>
- <span data-ttu-id="dfc28-156">L'icona mancante per il pulsante di invio disabilitato è stata aggiunta nella vista della barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="dfc28-156">The missing icon for the disabled submit button has been added in ribbon view.</span></span>
- <span data-ttu-id="dfc28-157">Le eccezioni di timeout ora aprono la pagina di connessione invece di mostrare un errore in linea.</span><span class="sxs-lookup"><span data-stu-id="dfc28-157">Time-out exceptions now take you to the connection page instead of showing an in-line error.</span></span>
- <span data-ttu-id="dfc28-158">Se non è disponibile alcuna azione di invio (come **OK**, **Sì**, **Accetta**, **Fatto**, o **Finito**), il pulsante di invio sarà disabilitato.</span><span class="sxs-lookup"><span data-stu-id="dfc28-158">If no submit action is available (such as **OK**, **Yes**, **Accept**, **Done**, or **Finished**), the submit button will be disabled.</span></span>
- <span data-ttu-id="dfc28-159">La stabilità dell'app è stata migliorata.</span><span class="sxs-lookup"><span data-stu-id="dfc28-159">App stability has been improved.</span></span>
- <span data-ttu-id="dfc28-160">C'è una correzione per la vulnerabilità della sicurezza [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).</span><span class="sxs-lookup"><span data-stu-id="dfc28-160">There is a fix for security vulnerability [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).</span></span>
- <span data-ttu-id="dfc28-161">**Versione Windows:** È stato risolto un problema su Windows, per cui i menu non rispondevano dopo il ridimensionamento della finestra.</span><span class="sxs-lookup"><span data-stu-id="dfc28-161">**Windows version:** An issue on Windows, where menus were unresponsive after the window was resized, has been fixed.</span></span>

### <a name="known-issue-in-version-2040"></a><span data-ttu-id="dfc28-162">Problema noto nella versione 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="dfc28-162">Known issue in version 2.0.4.0</span></span>

<span data-ttu-id="dfc28-163">In questa versione è presente il seguente problema noto:</span><span class="sxs-lookup"><span data-stu-id="dfc28-163">The following known issue exists in this version:</span></span>

- <span data-ttu-id="dfc28-164">Questa versione ha un problema con i dispositivi che utilizzano Android 4.4.</span><span class="sxs-lookup"><span data-stu-id="dfc28-164">This version has an issue with devices that use Android 4.4.</span></span> <span data-ttu-id="dfc28-165">Potresti riscontrare problemi quando usi l'app su questa versione di Android.</span><span class="sxs-lookup"><span data-stu-id="dfc28-165">You might experience issues when you use the app on this Android version.</span></span>
