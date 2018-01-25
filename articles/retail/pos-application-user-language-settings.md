---
title: Applicazione POS e impostazioni della lingua dell'utente
description: In questo argomento viene descritto come modificare le impostazioni della lingua in Retail Modern POS (MPOS) e Cloud POS.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 8075abccdcdde21df967dcc9948a738895f35cef
ms.openlocfilehash: b49450a7deab94c62e173f730007bc40de23b267
ms.contentlocale: it-it
ms.lasthandoff: 01/25/2018

---

# <a name="pos-application-and-user-language-settings"></a><span data-ttu-id="8dce8-103">Applicazione POS e impostazioni della lingua dell'utente</span><span class="sxs-lookup"><span data-stu-id="8dce8-103">POS application and user language settings</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="8dce8-104">In questo argomento viene descritto come modificare le impostazioni della lingua in Retail Modern POS (MPOS) e Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="8dce8-104">This topic describes how to change language settings in Retail Modern POS (MPOS) and Cloud POS.</span></span>

## <a name="overview"></a><span data-ttu-id="8dce8-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8dce8-105">Overview</span></span>
<span data-ttu-id="8dce8-106">Retail Modern POS (MPOS) e Cloud POS supportano ambienti in cui le impostazioni di lingua e le traduzioni possono variare tra il punto vendita e le impostazioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8dce8-106">Retail Modern POS (MPOS) and Cloud POS support environments where language settings and translations can vary between the store and user settings.</span></span> <span data-ttu-id="8dce8-107">Ad esempio, il punto vendita può trovarsi in uno stato/regione in cui l'inglese è più comune per i propri clienti, ma alcuni lavoratori preferiscono utilizzare l'applicazione con le traduzioni francesi.</span><span class="sxs-lookup"><span data-stu-id="8dce8-107">For example, the store could be located in a region where English is most common for their customers, but some workers prefer to use the application with French translations.</span></span>

## <a name="data-language"></a><span data-ttu-id="8dce8-108">Lingua dei dati</span><span class="sxs-lookup"><span data-stu-id="8dce8-108">Data language</span></span>
<span data-ttu-id="8dce8-109">Indipendentemente dalle impostazioni utente, MPOS e Cloud POS useranno sempre le impostazioni di lingua del punto vendita per determinare le traduzioni utilizzate per i dati.</span><span class="sxs-lookup"><span data-stu-id="8dce8-109">Regardless of the user’s settings, MPOS and Cloud POS will always use the store's language settings to determine the translations used for data.</span></span> <span data-ttu-id="8dce8-110">In questo modo, vi sarà uniformità di esperienza tra tutti gli utenti e i clienti.</span><span class="sxs-lookup"><span data-stu-id="8dce8-110">This will ensure that all users and customers will have a consistent experience.</span></span>  <span data-ttu-id="8dce8-111">Di seguito sono riportati alcuni esempi di dati:</span><span class="sxs-lookup"><span data-stu-id="8dce8-111">Examples of data include:</span></span>

-   <span data-ttu-id="8dce8-112">Prodotti</span><span class="sxs-lookup"><span data-stu-id="8dce8-112">Products</span></span>
-   <span data-ttu-id="8dce8-113">Attributi e valori</span><span class="sxs-lookup"><span data-stu-id="8dce8-113">Attributes and values</span></span>
-   <span data-ttu-id="8dce8-114">Nomi di categoria</span><span class="sxs-lookup"><span data-stu-id="8dce8-114">Category names</span></span>
-   <span data-ttu-id="8dce8-115">Ricevute di transazioni stampate o inviate tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="8dce8-115">Printed or emailed transaction receipts</span></span>
-   <span data-ttu-id="8dce8-116">Nomi di metodi di pagamento</span><span class="sxs-lookup"><span data-stu-id="8dce8-116">Payment method names</span></span>
-   <span data-ttu-id="8dce8-117">Messaggi di visualizzazione riga</span><span class="sxs-lookup"><span data-stu-id="8dce8-117">Line display messages</span></span>

<span data-ttu-id="8dce8-118">La lingua del punto vendita verrà utilizzata per la schermata di accesso principale al POS, poiché l'utente non è noto prima dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="8dce8-118">The store’s language will also be used for the main POS login screen, since the user is not known before logging in.</span></span> <span data-ttu-id="8dce8-119">Se per la lingua del punto vendita non è disponibile una traduzione, il POS utilizzerà la lingua della società.</span><span class="sxs-lookup"><span data-stu-id="8dce8-119">If a translation is not available for the store’s language, the POS will revert to the company’s language.</span></span>

### <a name="configuring-the-stores-language-setting"></a><span data-ttu-id="8dce8-120">Configurazione dell'impostazione della lingua del punto vendita</span><span class="sxs-lookup"><span data-stu-id="8dce8-120">Configuring the store’s language setting</span></span>

<span data-ttu-id="8dce8-121">La lingua del punto vendita viene impostata da **Tutti i punti vendita al dettaglio** nella pagina **Punto vendita al dettaglio** in **Generale &gt; Impostazioni internazionali &gt; Lingua.</span><span class="sxs-lookup"><span data-stu-id="8dce8-121">The store’s language setting is set from **All retail stores** on the **Retail Store** page under **General &gt; Regional Settings &gt; Language.</span></span> <span data-ttu-id="8dce8-122">**Usare il menu a discesa per scegliere la lingua per ciascun punto vendita.</span><span class="sxs-lookup"><span data-stu-id="8dce8-122">**Use the drop down to choose the language for each store.</span></span>

## <a name="user-interface-language"></a><span data-ttu-id="8dce8-123">Lingua dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8dce8-123">User interface language</span></span>
<span data-ttu-id="8dce8-124">L'impostazione della lingua dell'utente del POS determina le traduzioni utilizzate nell'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8dce8-124">The POS user’s language setting determines the translations used in the application user interface.</span></span> <span data-ttu-id="8dce8-125">Sono inclusi tutti i menu, le etichette e gli elenchi che non sono considerati come dati.</span><span class="sxs-lookup"><span data-stu-id="8dce8-125">This includes all labels, menus, and lists that are not considered data.</span></span> <span data-ttu-id="8dce8-126">Fa eccezione il testo che viene visualizzato nelle griglie dei pulsanti del POS.</span><span class="sxs-lookup"><span data-stu-id="8dce8-126">One exception is the text that is displayed on POS button grids.</span></span> <span data-ttu-id="8dce8-127">Le griglie dei pulsanti non supportano le traduzioni, pertanto il testo sarà sempre visualizzato così come è definito sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="8dce8-127">The button grids don't support translations, so they will always show the text as defined on the button.</span></span> <span data-ttu-id="8dce8-128">Per supportare i pulsanti tradotti, sarà necessario copiare e gestire griglie di pulsanti separate e assegnarle agli utenti nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="8dce8-128">In order to support translated buttons, you'll have to copy and maintain separate button grids and assign them to the users as appropriate.</span></span>

### <a name="configuring-the-users-language-setting"></a><span data-ttu-id="8dce8-129">Configurazione dell'impostazione della lingua dell'utente</span><span class="sxs-lookup"><span data-stu-id="8dce8-129">Configuring the user’s language setting</span></span>

<span data-ttu-id="8dce8-130">La lingua dell'utente del POS viene impostata da **Tutti i lavoratori** nella pagina **Lavoratore** in **Vendita al dettaglio &gt; Lingua**.</span><span class="sxs-lookup"><span data-stu-id="8dce8-130">The POS user’s language setting is set from **All workers** on the **Worker** page under **Retail &gt; Language**.</span></span>  <span data-ttu-id="8dce8-131">Non viene impostata nella scheda Profilo. Questa impostazione non viene utilizzata dal POS.</span><span class="sxs-lookup"><span data-stu-id="8dce8-131">It is not set on the main Profile tab.  This setting is not used by POS.</span></span> <span data-ttu-id="8dce8-132">Se la lingua dell'utente non è impostata o è impostata una lingua per cui le traduzioni non sono disponibili, il POS tornerà alla lingua del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="8dce8-132">If the user’s language is not set or it is set to a language where translations are not available, the POS will revert to the store’s language.</span></span>  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| <span data-ttu-id="8dce8-133">** **</span><span class="sxs-lookup"><span data-stu-id="8dce8-133">** **</span></span>       | <span data-ttu-id="8dce8-134">**Lingua dell'interfaccia utente** ** **</span><span class="sxs-lookup"><span data-stu-id="8dce8-134">**UI language** ** **</span></span>      | <span data-ttu-id="8dce8-135">**Lingua dei dati (prodotti, formati ricevuta, visualizzazione riga e così via).**</span><span class="sxs-lookup"><span data-stu-id="8dce8-135">**Data language (products, receipt formats, line display, etc.)**</span></span> |
| <span data-ttu-id="8dce8-136">**Società**</span><span class="sxs-lookup"><span data-stu-id="8dce8-136">**Company**</span></span> | <span data-ttu-id="8dce8-137">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="8dce8-137">Default</span></span>                    | <span data-ttu-id="8dce8-138">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="8dce8-138">Default</span></span>                                                           |
| <span data-ttu-id="8dce8-139">**Punto vendita**</span><span class="sxs-lookup"><span data-stu-id="8dce8-139">**Store**</span></span>   | <span data-ttu-id="8dce8-140">Sovrascrive la società</span><span class="sxs-lookup"><span data-stu-id="8dce8-140">Overrides company</span></span>          | <span data-ttu-id="8dce8-141">Sovrascrive la società</span><span class="sxs-lookup"><span data-stu-id="8dce8-141">Overrides company</span></span>                                                 |
| <span data-ttu-id="8dce8-142">**Utente**</span><span class="sxs-lookup"><span data-stu-id="8dce8-142">**User**</span></span>    | <span data-ttu-id="8dce8-143">Sovrascrive il punto vendita o la società</span><span class="sxs-lookup"><span data-stu-id="8dce8-143">Overrides store or company</span></span> | <span data-ttu-id="8dce8-144">Mai</span><span class="sxs-lookup"><span data-stu-id="8dce8-144">Never</span></span>                                                             |






