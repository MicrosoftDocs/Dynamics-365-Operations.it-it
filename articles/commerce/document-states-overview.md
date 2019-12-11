---
title: Stato e ciclo di vita documento
description: In questo argomento vengono descritti i diversi stati documento di elementi pagina in Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a34d10edbf84ac1814afdc7107727aea68a303e0
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770437"
---
# <a name="document-states-and-lifecycle"></a><span data-ttu-id="77643-103">Stato e ciclo di vita documento</span><span class="sxs-lookup"><span data-stu-id="77643-103">Document states and lifecycle</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="77643-104">In questo argomento vengono descritti i diversi stati documento di elementi pagina in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="77643-104">This topic covers the various document states of page elements in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="document-state-descriptions"></a><span data-ttu-id="77643-105">Descrizioni di stati documento</span><span class="sxs-lookup"><span data-stu-id="77643-105">Document state descriptions</span></span>

<span data-ttu-id="77643-106">L'argomento [Elementi pagina](page-elements-overview.md) elenca vari tipi di documenti nel sistema di gestione dei contenuti (CMS).</span><span class="sxs-lookup"><span data-stu-id="77643-106">The [Page elements](page-elements-overview.md) topic lists various documents types in the content management system (CMS).</span></span> <span data-ttu-id="77643-107">Questi tipi di documenti possono avere vari stati nello strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="77643-107">These document types can have several states in the authoring tool.</span></span> <span data-ttu-id="77643-108">Gli stati documento impediscono conflitti di dati e applicano il controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="77643-108">The document states help prevent data conflicts and enforce version control.</span></span> <span data-ttu-id="77643-109">Determinano chi può modificare i documenti, quando i documenti possono essere modificati e quando le modifiche possono essere visualizzate da altre persone.</span><span class="sxs-lookup"><span data-stu-id="77643-109">They determine who can change the documents, when the documents can be changed, and when changes can be viewed by other people.</span></span>

<span data-ttu-id="77643-110">Nella tabella seguente vengono illustrati gli stati documento possibili degli elementi pagina in Commerce.</span><span class="sxs-lookup"><span data-stu-id="77643-110">The following table shows the possible document states of page elements in Commerce.</span></span>

| <span data-ttu-id="77643-111">Stato documento</span><span class="sxs-lookup"><span data-stu-id="77643-111">Document state</span></span> | <span data-ttu-id="77643-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77643-112">Description</span></span> |
|---|---|
| <span data-ttu-id="77643-113">Estratte</span><span class="sxs-lookup"><span data-stu-id="77643-113">Checked out</span></span> | <span data-ttu-id="77643-114">Quando un articolo CMS viene estratto, non può essere modificato da altri utenti di sistema autenticati.</span><span class="sxs-lookup"><span data-stu-id="77643-114">When a CMS item is checked out to you, it can't be edited by any other authenticated system users.</span></span> <span data-ttu-id="77643-115">Eventuali modifiche apportate all'articolo dall'utente sono visibili solo all'utente.</span><span class="sxs-lookup"><span data-stu-id="77643-115">Any changes that you make to the item are visible only to you.</span></span> |
| <span data-ttu-id="77643-116">Archiviate</span><span class="sxs-lookup"><span data-stu-id="77643-116">Checked in</span></span> | <span data-ttu-id="77643-117">Quando un articolo CMS viene archiviato, tutte le modifiche sono visibili agli altri utenti di sistema autenticati, che possono quindi estrarre l'articolo e modificarlo.</span><span class="sxs-lookup"><span data-stu-id="77643-117">When a CMS item is checked in, all changes are visible to other authenticated system users, and those users can then check out the item and edit it.</span></span> <span data-ttu-id="77643-118">Ogni archiviazione crea un record delle versioni del documento nello storico dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="77643-118">Each check-in creates a document version record in the item's history.</span></span> |
| <span data-ttu-id="77643-119">Pubblicata</span><span class="sxs-lookup"><span data-stu-id="77643-119">Published</span></span> | <span data-ttu-id="77643-120">Quando un articolo CMS viene pubblicato, viene inviato al sito live e diventa individuabile su Internet da utenti esterni non autenticati.</span><span class="sxs-lookup"><span data-stu-id="77643-120">When a CMS item is published, it's pushed to your live site and becomes discoverable on the internet by non-authenticated external users.</span></span> <span data-ttu-id="77643-121">Gli articoli possono essere pubblicati solo se sono stati archiviati.</span><span class="sxs-lookup"><span data-stu-id="77643-121">Items can be published only if they have been checked in.</span></span> |
| <span data-ttu-id="77643-122">Salvato</span><span class="sxs-lookup"><span data-stu-id="77643-122">Saved</span></span> | <span data-ttu-id="77643-123">Le modifiche apportate a un articolo CMS estratto possono essere salvate in CMS prima che l'articolo venga archiviato o pubblicato.</span><span class="sxs-lookup"><span data-stu-id="77643-123">Changes that have been made to a checked-out CMS item can be saved to the CMS before the item is checked in or published.</span></span> <span data-ttu-id="77643-124">Queste modifiche salvate non sono visibili ad altri utenti di sistema autenticati fino a che l'articolo non viene archiviato.</span><span class="sxs-lookup"><span data-stu-id="77643-124">These saved changes aren't visible to other authenticated system users until the item is checked in.</span></span> <span data-ttu-id="77643-125">Non sono visibili agli utenti esterni fino a che l'articolo non viene pubblicato.</span><span class="sxs-lookup"><span data-stu-id="77643-125">They aren't visible to external users until the item is published.</span></span> |
| <span data-ttu-id="77643-126">Estrazione annullata</span><span class="sxs-lookup"><span data-stu-id="77643-126">Discarded check out</span></span> | <span data-ttu-id="77643-127">Quando l'estrazione di un articolo CMS viene annullata, tutte le modifiche salvate vengono eliminate e viene ripristinata la versione archiviata più recente dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="77643-127">When a checked-out CMS item is discarded, all saved changes are deleted, and the item reverts to the version that was most recently checked in.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="77643-128">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="77643-128">Additional resources</span></span>

[<span data-ttu-id="77643-129">Modalità di aggiungere contenuti</span><span class="sxs-lookup"><span data-stu-id="77643-129">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="77643-130">Glossario del modello di pagina</span><span class="sxs-lookup"><span data-stu-id="77643-130">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="77643-131">Utilizzare i moduli</span><span class="sxs-lookup"><span data-stu-id="77643-131">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="77643-132">Utilizzare i frammenti</span><span class="sxs-lookup"><span data-stu-id="77643-132">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="77643-133">Panoramica modelli e layout</span><span class="sxs-lookup"><span data-stu-id="77643-133">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="77643-134">Personalizzare la navigazione del sito</span><span class="sxs-lookup"><span data-stu-id="77643-134">Customize site navigation</span></span>](customize-site-navigation.md)