---
title: Domande frequenti sul client
description: Questo articolo fornisce risposte alle domande frequenti sul client Finance and Operations.
author: jasongre
manager: AnnBe
ms.date: 09/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8a7d311bfcd65e23e4062f105435d05cb1ceda6b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567042"
---
# <a name="client-faq"></a><span data-ttu-id="d0142-103">Domande frequenti sul client</span><span class="sxs-lookup"><span data-stu-id="d0142-103">Client FAQ</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d0142-104">Questo articolo fornisce risposte alle domande frequenti sul client Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d0142-104">This article provides answers to frequently asked questions about the Finance and Operations client.</span></span>

## <a name="why-arent-symbols-loaded"></a><span data-ttu-id="d0142-105">Perché i simboli non vengono caricati?</span><span class="sxs-lookup"><span data-stu-id="d0142-105">Why aren't symbols loaded?</span></span>

<span data-ttu-id="d0142-106">Le impostazioni di sicurezza nel browser potrebbero impedire ai simboli di caricarsi correttamente.</span><span class="sxs-lookup"><span data-stu-id="d0142-106">The security settings on your browser might prevent the symbols from being loaded correctly.</span></span> <span data-ttu-id="d0142-107">Per risolvere questo problema, tentare di procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="d0142-107">To resolve this issue, try the following steps:</span></span>

- <span data-ttu-id="d0142-108">Se questo problema si verifica in Internet Explorer, fare clic su **Strumenti**, quindi su **Opzioni Internet**.</span><span class="sxs-lookup"><span data-stu-id="d0142-108">If you're experiencing this issue in Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span> <span data-ttu-id="d0142-109">Nella finestra di dialogo Opzioni Internet, nella scheda **Privacy**, fare clic su **Livello personalizzato** e assicurarsi che l'opzione **Download dei caratteri** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="d0142-109">In the Internet Options dialog box, on the **Privacy** tab, click **Custom level**, and make sure the **Font download** option is selected.</span></span>
- <span data-ttu-id="d0142-110">In caso contrario, potrebbe essere necessario aggiungere il sito dell'app all'elenco dei siti attendibili.</span><span class="sxs-lookup"><span data-stu-id="d0142-110">Otherwise, you might have to add the app site to the list of trusted sites.</span></span>

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a><span data-ttu-id="d0142-111">La barra multifunzione di Dynamics AX 2012 non è visibile.</span><span class="sxs-lookup"><span data-stu-id="d0142-111">I miss the ribbon from Dynamics AX 2012.</span></span> <span data-ttu-id="d0142-112">Posso mantenere sempre aperte le schede del riquadro azioni?</span><span class="sxs-lookup"><span data-stu-id="d0142-112">Can I keep Action Pane tabs open all the time?</span></span>

<span data-ttu-id="d0142-113">Implementeremo presto questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d0142-113">We are planning to implement this feature soon.</span></span> <span data-ttu-id="d0142-114">Gli utenti potranno a quel punto scegliere di tenere le schede sempre aperte nei riquadri azioni.</span><span class="sxs-lookup"><span data-stu-id="d0142-114">Users will then be able to choose to keep the tabs on Action Panes open all the time.</span></span> <span data-ttu-id="d0142-115">In caso contrario, le schede verranno compresse quando non saranno utilizzate, per ottenere maggiore spazio sullo schermo per la pagina.</span><span class="sxs-lookup"><span data-stu-id="d0142-115">Otherwise, the tabs will be collapsed when they aren't being used, to gain more screen space for the page.</span></span>

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-right-click"></a><span data-ttu-id="d0142-116">Perché talvolta vedo menu di scelta rapida diversi quando faccio clic con il pulsante destro del mouse?</span><span class="sxs-lookup"><span data-stu-id="d0142-116">Why do I sometimes see different shortcut menus when I right click?</span></span>

<span data-ttu-id="d0142-117">Se si fa clic con il pulsante destro del mouse in un campo modificabile (o se il testo viene selezionato), verrà visualizzato il menu di scelta rapida del browser.</span><span class="sxs-lookup"><span data-stu-id="d0142-117">If you right-click in an editable field (or if text is selected), the browser's shortcut menu is displayed.</span></span> <span data-ttu-id="d0142-118">Questo menu consente l'accesso ai comandi **Taglia**, **Copia** e **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="d0142-118">This menu gives you access to the **Cut**, **Copy**, and **Paste** commands.</span></span> <span data-ttu-id="d0142-119">Non è possibile includere questi comandi nei menu di scelta rapida poiché, per motivi di sicurezza, i browser non concedono di accedere a livello di codice agli Appunti del sistema.</span><span class="sxs-lookup"><span data-stu-id="d0142-119">We can't embed these commands into the shortcut menus because, for security reasons, browsers don't allow us to programmatically access the system clipboard.</span></span>

<span data-ttu-id="d0142-120">Se si fa clic con il pulsante destro del mouse su un'etichetta di campo o sul valore di un controllo di sola lettura, verrà visualizzato il menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="d0142-120">If you right-click a field label or the value of a read-only control, you'll see the shortcut menu.</span></span>

<span data-ttu-id="d0142-121">Per rendere l'accesso alla tastiera più semplice, si ha in programma di implementare in futuro tasti di scelta rapida che apriranno il menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="d0142-121">To make keyboard access easier, we plan to implement a keyboard shortcut in the future that will open the shortcut menu.</span></span>

## <a name="where-is-the-view-details-functionality"></a><span data-ttu-id="d0142-122">Dov'è la funzionalità Visualizza dettagli?</span><span class="sxs-lookup"><span data-stu-id="d0142-122">Where is the View details functionality?</span></span>

<span data-ttu-id="d0142-123">L'opzione **Visualizza dettagli** è disponibile in un paio di modi:</span><span class="sxs-lookup"><span data-stu-id="d0142-123">The **View details** option is available in a couple of ways:</span></span>

- <span data-ttu-id="d0142-124">Se un controllo ha le funzionalità **Visualizza dettagli** e se il controllo ha un valore, il valore viene visualizzato come collegamento ipertestuale.</span><span class="sxs-lookup"><span data-stu-id="d0142-124">If a control has **View details** capabilities, and if the control has a value, that value is displayed as a hyperlink.</span></span> <span data-ttu-id="d0142-125">È possibile fare clic sul collegamento ipertestuale per aprire la pagina contenente dettagli aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="d0142-125">You can click the hyperlink to open a page that contains additional details.</span></span>
- <span data-ttu-id="d0142-126">**Visualizza dettagli** è anche un'opzione dei menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="d0142-126">**View details** is also an option on shortcut menus.</span></span> <span data-ttu-id="d0142-127">Per ulteriori informazioni su quando i menu di scelta rapida vengono visualizzati quando si fa clic con il pulsante destro del mouse, vedere la sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="d0142-127">For more information about when shortcut menus are displayed when you right-click, see the previous section.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]