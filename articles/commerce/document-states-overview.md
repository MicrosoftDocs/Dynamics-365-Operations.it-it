---
title: Stato e ciclo di vita documento
description: In questo argomento vengono descritti i diversi stati documento di elementi pagina in Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
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
ms.openlocfilehash: 8aad7ef8425e46182c669686710dfc178abc418f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413461"
---
# <a name="document-states-and-lifecycle"></a><span data-ttu-id="2f867-103">Stato e ciclo di vita documento</span><span class="sxs-lookup"><span data-stu-id="2f867-103">Document states and lifecycle</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2f867-104">In questo argomento vengono descritti i diversi stati documento di elementi pagina in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2f867-104">This topic covers the various document states of page elements in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="document-state-descriptions"></a><span data-ttu-id="2f867-105">Descrizioni di stati documento</span><span class="sxs-lookup"><span data-stu-id="2f867-105">Document state descriptions</span></span>

<span data-ttu-id="2f867-106">L'argomento [Elementi pagina](page-elements-overview.md) elenca vari tipi di documenti nel sistema di gestione dei contenuti (CMS).</span><span class="sxs-lookup"><span data-stu-id="2f867-106">The [Page elements](page-elements-overview.md) topic lists various documents types in the content management system (CMS).</span></span> <span data-ttu-id="2f867-107">Questi tipi di documenti possono avere vari stati nello strumento di creazione.</span><span class="sxs-lookup"><span data-stu-id="2f867-107">These document types can have several states in the authoring tool.</span></span> <span data-ttu-id="2f867-108">Gli stati documento impediscono conflitti di dati e applicano il controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="2f867-108">The document states help prevent data conflicts and enforce version control.</span></span> <span data-ttu-id="2f867-109">Determinano chi può modificare i documenti, quando i documenti possono essere modificati e quando le modifiche possono essere visualizzate da altre persone.</span><span class="sxs-lookup"><span data-stu-id="2f867-109">They determine who can change the documents, when the documents can be changed, and when changes can be viewed by other people.</span></span>

<span data-ttu-id="2f867-110">Nella tabella seguente vengono illustrati gli stati documento possibili degli elementi pagina in Commerce.</span><span class="sxs-lookup"><span data-stu-id="2f867-110">The following table shows the possible document states of page elements in Commerce.</span></span>

| <span data-ttu-id="2f867-111">Stato documento</span><span class="sxs-lookup"><span data-stu-id="2f867-111">Document state</span></span>      | <span data-ttu-id="2f867-112">Azione di Creazione di siti Web</span><span class="sxs-lookup"><span data-stu-id="2f867-112">Site builder action</span></span>        | <span data-ttu-id="2f867-113">descrizione</span><span class="sxs-lookup"><span data-stu-id="2f867-113">Description</span></span>                                                  |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="2f867-114">Check out</span><span class="sxs-lookup"><span data-stu-id="2f867-114">Checked out</span></span>         | <span data-ttu-id="2f867-115">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2f867-115">Select **Edit**.</span></span>           | <span data-ttu-id="2f867-116">Il documento applicabile è stato estratto.</span><span class="sxs-lookup"><span data-stu-id="2f867-116">The applicable document is checked out to you.</span></span> <span data-ttu-id="2f867-117">Mentre un documento si trova in questo stato, non può essere modificato da altri utenti di sistema autenticati e qualsiasi modifica apportata al documento è visibile solo all'utente.</span><span class="sxs-lookup"><span data-stu-id="2f867-117">While a document is in this state, it can't be changed by other authenticated system users, and any changes that you make to the document are visible only to you.</span></span> |
| <span data-ttu-id="2f867-118">Salvato</span><span class="sxs-lookup"><span data-stu-id="2f867-118">Saved</span></span>               | <span data-ttu-id="2f867-119">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2f867-119">Select **Save**.</span></span>           | <span data-ttu-id="2f867-120">Le modifiche apportate a un documento estratto vengono salvate nel database, ma il documento non è ancora archiviato o pubblicato.</span><span class="sxs-lookup"><span data-stu-id="2f867-120">Changes that have been made to a checked-out document are saved to the database, but the document isn't yet checked in or published.</span></span> <span data-ttu-id="2f867-121">Le modifiche salvate non sono visibili ad altri utenti di sistema autenticati fino a che l'autore seleziona **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="2f867-121">The saved changes aren't visible to other authenticated system users until the author selects **Finish editing**.</span></span> <span data-ttu-id="2f867-122">Non sono visibili agli utenti esterni fino a che l'articolo non viene pubblicato.</span><span class="sxs-lookup"><span data-stu-id="2f867-122">They aren't visible to external users until the item is published.</span></span> |
| <span data-ttu-id="2f867-123">Estrazione annullata</span><span class="sxs-lookup"><span data-stu-id="2f867-123">Discarded check out</span></span> | <span data-ttu-id="2f867-124">Selezionare **Ignora modifiche**.</span><span class="sxs-lookup"><span data-stu-id="2f867-124">Select **Discard edits**.</span></span>  | <span data-ttu-id="2f867-125">Tutte le modifiche al documento estratto vengono eliminate e l'elemento torna all'ultima versione archiviata.</span><span class="sxs-lookup"><span data-stu-id="2f867-125">All changes to the checked-out document are discarded, and the item reverts to the last version that was checked in.</span></span> |
| <span data-ttu-id="2f867-126">Elemento archiviato</span><span class="sxs-lookup"><span data-stu-id="2f867-126">Checked in</span></span>          | <span data-ttu-id="2f867-127">Selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="2f867-127">Select **Finish editing**.</span></span> | <span data-ttu-id="2f867-128">Il documento modificato è archiviato.</span><span class="sxs-lookup"><span data-stu-id="2f867-128">The edited document is checked in.</span></span> <span data-ttu-id="2f867-129">Tutte le modifiche sono visibili agli altri utenti del sistema autenticati e tali utenti possono quindi modificare il documento.</span><span class="sxs-lookup"><span data-stu-id="2f867-129">All changes are visible to other authenticated system users, and those users can then edit the document.</span></span> <span data-ttu-id="2f867-130">Ogni archiviazione crea un record delle versioni del documento nello storico dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="2f867-130">Each check-in creates a document version record in the item's history.</span></span> |
| <span data-ttu-id="2f867-131">Pubblicata</span><span class="sxs-lookup"><span data-stu-id="2f867-131">Published</span></span>           | <span data-ttu-id="2f867-132">Selezionare **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="2f867-132">Select **Publish**.</span></span>        | <span data-ttu-id="2f867-133">Il documento viene pubblicato e le modifiche vengono inviate al sito live e diventano rilevabili da utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="2f867-133">The document is published, and the changes are pushed to your live site and become discoverable by external users.</span></span> <span data-ttu-id="2f867-134">Gli articoli possono essere pubblicati solo se sono stati prima archiviati selezionando **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="2f867-134">Items can be published only if they have first been checked in by selecting **Finish editing**.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="2f867-135">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2f867-135">Additional resources</span></span>

[<span data-ttu-id="2f867-136">Modalità di aggiungere contenuti</span><span class="sxs-lookup"><span data-stu-id="2f867-136">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="2f867-137">Glossario del modello di pagina</span><span class="sxs-lookup"><span data-stu-id="2f867-137">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="2f867-138">Utilizzare i gruppi di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="2f867-138">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="2f867-139">Abilitare e utilizzare la condivisione multicanale</span><span class="sxs-lookup"><span data-stu-id="2f867-139">Enable and use cross-channel sharing</span></span>](cross-channel-sharing.md)

[<span data-ttu-id="2f867-140">Utilizzare i moduli</span><span class="sxs-lookup"><span data-stu-id="2f867-140">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="2f867-141">Utilizzare i frammenti</span><span class="sxs-lookup"><span data-stu-id="2f867-141">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="2f867-142">Panoramica modelli e layout</span><span class="sxs-lookup"><span data-stu-id="2f867-142">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="2f867-143">Personalizzare la navigazione del sito</span><span class="sxs-lookup"><span data-stu-id="2f867-143">Customize site navigation</span></span>](customize-site-navigation.md)
