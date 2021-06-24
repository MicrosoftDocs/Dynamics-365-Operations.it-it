---
title: Applicazione POS e impostazioni della lingua dell'utente
description: In questo argomento viene descritto come modificare le impostazioni della lingua in Modern POS (MPOS) e Cloud POS.
author: jblucher
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: bdd03dff359e7c2799eff53b0e999580ce8b1c06
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193105"
---
# <a name="point-of-sale-pos-application-and-user-language-settings"></a><span data-ttu-id="827cc-103">Applicazione POS e impostazioni della lingua dell'utente</span><span class="sxs-lookup"><span data-stu-id="827cc-103">Point of sale (POS) application and user language settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="827cc-104">In questo argomento viene descritto come modificare le impostazioni della lingua in Modern POS (MPOS) e Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="827cc-104">This topic describes how to change language settings in Modern POS (MPOS) and Cloud POS.</span></span>

## <a name="overview"></a><span data-ttu-id="827cc-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="827cc-105">Overview</span></span>
<span data-ttu-id="827cc-106">Modern POS (MPOS) e Cloud POS supportano ambienti in cui le impostazioni di lingua e le traduzioni possono variare tra il punto vendita e le impostazioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="827cc-106">Modern POS (MPOS) and Cloud POS support environments where language settings and translations can vary between the store and user settings.</span></span> <span data-ttu-id="827cc-107">Ad esempio, il punto vendita può trovarsi in uno stato/regione in cui l'inglese è più comune per i propri clienti, ma alcuni lavoratori preferiscono utilizzare l'applicazione con le traduzioni francesi.</span><span class="sxs-lookup"><span data-stu-id="827cc-107">For example, the store could be located in a region where English is most common for their customers, but some workers prefer to use the application with French translations.</span></span>

## <a name="data-language"></a><span data-ttu-id="827cc-108">Lingua dei dati</span><span class="sxs-lookup"><span data-stu-id="827cc-108">Data language</span></span>

<span data-ttu-id="827cc-109">Indipendentemente dalle impostazioni utente, MPOS e Cloud POS useranno sempre le impostazioni di lingua del punto vendita per determinare le traduzioni utilizzate per i dati.</span><span class="sxs-lookup"><span data-stu-id="827cc-109">Regardless of the user's settings, MPOS and Cloud POS will always use the store's language settings to determine the translations used for data.</span></span> <span data-ttu-id="827cc-110">In questo modo, vi sarà uniformità di esperienza tra tutti gli utenti e i clienti.</span><span class="sxs-lookup"><span data-stu-id="827cc-110">This will ensure that all users and customers will have a consistent experience.</span></span> <span data-ttu-id="827cc-111">Di seguito sono riportati alcuni esempi di dati:</span><span class="sxs-lookup"><span data-stu-id="827cc-111">Examples of data include:</span></span>

- <span data-ttu-id="827cc-112">Prodotti</span><span class="sxs-lookup"><span data-stu-id="827cc-112">Products</span></span>
- <span data-ttu-id="827cc-113">Attributi e valori</span><span class="sxs-lookup"><span data-stu-id="827cc-113">Attributes and values</span></span>
- <span data-ttu-id="827cc-114">Nomi di categoria</span><span class="sxs-lookup"><span data-stu-id="827cc-114">Category names</span></span>
- <span data-ttu-id="827cc-115">Ricevute di transazioni stampate o inviate tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="827cc-115">Printed or emailed transaction receipts</span></span>
- <span data-ttu-id="827cc-116">Nomi di metodi di pagamento</span><span class="sxs-lookup"><span data-stu-id="827cc-116">Payment method names</span></span>
- <span data-ttu-id="827cc-117">Messaggi di visualizzazione riga</span><span class="sxs-lookup"><span data-stu-id="827cc-117">Line display messages</span></span>

<span data-ttu-id="827cc-118">La lingua del punto vendita verrà utilizzata per la schermata di accesso principale al POS, poiché l'utente non è noto prima dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="827cc-118">The store's language will also be used for the main POS login screen, since the user is not known before logging in.</span></span> <span data-ttu-id="827cc-119">Se per la lingua del punto vendita non è disponibile una traduzione, il POS utilizzerà la lingua della società.</span><span class="sxs-lookup"><span data-stu-id="827cc-119">If a translation is not available for the store's language, the POS will revert to the company's language.</span></span>

### <a name="configuring-the-stores-language-setting"></a><span data-ttu-id="827cc-120">Configurazione dell'impostazione della lingua del punto vendita</span><span class="sxs-lookup"><span data-stu-id="827cc-120">Configuring the store's language setting</span></span>

<span data-ttu-id="827cc-121">La lingua del punto vendita viene impostata da **Tutti i punti vendita** nella pagina **Punto vendita** in **Generale &gt; Impostazioni internazionali &gt; Lingua**.</span><span class="sxs-lookup"><span data-stu-id="827cc-121">The store's language setting is set from **All stores** on the **Store** page under **General &gt; Regional Settings &gt; Language**.</span></span> <span data-ttu-id="827cc-122">Usare l'elenco a discesa per scegliere la lingua per ciascun punto vendita.</span><span class="sxs-lookup"><span data-stu-id="827cc-122">Use the drop-down list to choose the language for each store.</span></span>

## <a name="user-interface-language"></a><span data-ttu-id="827cc-123">Lingua dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="827cc-123">User interface language</span></span>

<span data-ttu-id="827cc-124">L'impostazione della lingua dell'utente del POS determina le traduzioni utilizzate nell'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="827cc-124">The POS user's language setting determines the translations used in the application user interface.</span></span> <span data-ttu-id="827cc-125">Sono inclusi tutti i menu, le etichette e gli elenchi che non sono considerati come dati.</span><span class="sxs-lookup"><span data-stu-id="827cc-125">This includes all labels, menus, and lists that are not considered data.</span></span> <span data-ttu-id="827cc-126">Fa eccezione il testo che viene visualizzato nelle griglie dei pulsanti del POS.</span><span class="sxs-lookup"><span data-stu-id="827cc-126">One exception is the text that is displayed on POS button grids.</span></span> <span data-ttu-id="827cc-127">Le griglie dei pulsanti non supportano le traduzioni, pertanto il testo sarà sempre visualizzato così come è definito sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="827cc-127">The button grids don't support translations, so they will always show the text as defined on the button.</span></span> <span data-ttu-id="827cc-128">Per supportare i pulsanti tradotti, sarà necessario copiare e gestire griglie di pulsanti separate e assegnarle agli utenti nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="827cc-128">In order to support translated buttons, you'll have to copy and maintain separate button grids and assign them to the users as appropriate.</span></span>

### <a name="configuring-the-users-language-setting"></a><span data-ttu-id="827cc-129">Configurazione dell'impostazione della lingua dell'utente</span><span class="sxs-lookup"><span data-stu-id="827cc-129">Configuring the user's language setting</span></span>

<span data-ttu-id="827cc-130">L'impostazione della lingua dell'utente viene impostata in **Tutti i lavoratori** nella pagina **Lavoratore** in **Retail e Commerce &gt; Lingua**.</span><span class="sxs-lookup"><span data-stu-id="827cc-130">The POS user's language setting is set from **All workers** on the **Worker** page under **Retail and Commerce &gt; Language**.</span></span> <span data-ttu-id="827cc-131">Non viene impostata nella scheda Profilo. Questa impostazione non viene utilizzata dal POS.</span><span class="sxs-lookup"><span data-stu-id="827cc-131">It is not set on the main Profile tab. This setting is not used by POS.</span></span> <span data-ttu-id="827cc-132">Se la lingua dell'utente non è impostata o è impostata una lingua per cui le traduzioni non sono disponibili, il POS tornerà alla lingua del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="827cc-132">If the user's language is not set or it is set to a language where translations are not available, the POS will revert to the store's language.</span></span>

| &nbsp;      | <span data-ttu-id="827cc-133">Lingua dell'interfaccia utente   </span><span class="sxs-lookup"><span data-stu-id="827cc-133">UI language</span></span>                | <span data-ttu-id="827cc-134">Lingua dei dati (prodotti, formati ricevuta, visualizzazione riga e così via).</span><span class="sxs-lookup"><span data-stu-id="827cc-134">Data language (products, receipt formats, line display, etc.)</span></span> |
|-------------|----------------------------|---------------------------------------------------------------|
| <span data-ttu-id="827cc-135">**Società**</span><span class="sxs-lookup"><span data-stu-id="827cc-135">**Company**</span></span> | <span data-ttu-id="827cc-136">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="827cc-136">Default</span></span>                    | <span data-ttu-id="827cc-137">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="827cc-137">Default</span></span>                                                       |
| <span data-ttu-id="827cc-138">**Punto vendita**</span><span class="sxs-lookup"><span data-stu-id="827cc-138">**Store**</span></span>   | <span data-ttu-id="827cc-139">Sovrascrive la società</span><span class="sxs-lookup"><span data-stu-id="827cc-139">Overrides company</span></span>          | <span data-ttu-id="827cc-140">Sovrascrive la società</span><span class="sxs-lookup"><span data-stu-id="827cc-140">Overrides company</span></span>                                             |
| <span data-ttu-id="827cc-141">**Utente**</span><span class="sxs-lookup"><span data-stu-id="827cc-141">**User**</span></span>    | <span data-ttu-id="827cc-142">Sovrascrive il punto vendita o la società</span><span class="sxs-lookup"><span data-stu-id="827cc-142">Overrides store or company</span></span> | <span data-ttu-id="827cc-143">Mai</span><span class="sxs-lookup"><span data-stu-id="827cc-143">Never</span></span>                                                         |


[!INCLUDE[footer-include](../includes/footer-banner.md)]