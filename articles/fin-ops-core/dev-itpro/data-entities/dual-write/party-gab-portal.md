---
title: Utilizzo di Power Portal con il modello di dati parte
description: In questo argomento vengono descritte le modifiche ai ruoli Web di Power Portal a causa del modello di dati della parte in doppia scrittura.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: a2ea914344341ee26138e853727c551bdd5d733e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833092"
---
# <a name="using-power-portal-with-the-party-data-model"></a><span data-ttu-id="05d95-103">Utilizzo di Power Portal con il modello di dati parte</span><span class="sxs-lookup"><span data-stu-id="05d95-103">Using Power Portal with the Party data model</span></span>

[!INCLUDE[banner](../../includes/banner.md)]

[!INCLUDE[rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="05d95-104">La versione della soluzione di orchestrazione delle applicazioni a doppia scrittura 2.0.999.0 e successive include le modifiche al modello di dati della parte e alla rubrica globale per le tabelle Conto e Contatto.</span><span class="sxs-lookup"><span data-stu-id="05d95-104">The Dual-write application orchestration solution version 2.0.999.0 and later includes data model changes to party and global address book for the Account and Contact tables.</span></span> <span data-ttu-id="05d95-105">Le modifiche consentono le relazioni molti-a-molti che supportano scenari aziendali avanzati.</span><span class="sxs-lookup"><span data-stu-id="05d95-105">The changes allow many-to-many relationships that support advanced business scenarios.</span></span> <span data-ttu-id="05d95-106">Queste modifiche non sono supportate dai ruoli Web del portale, incluso il portale del cliente, forniti in modo predefinito o esistenti nell'ambiente prima dell'installazione della doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="05d95-106">These changes are not supported by portal web roles, including the customer portal, that are shipped out-of-the-box or that existed in your environment before you installed dual-write.</span></span> <span data-ttu-id="05d95-107">Affinché i ruoli Web funzionino come previsto, è necessario creare nuovi ruoli Web utilizzando il nuovo modello di dati.</span><span class="sxs-lookup"><span data-stu-id="05d95-107">For the web roles to work as expected, you need to create new web roles using the new data model.</span></span> 

<span data-ttu-id="05d95-108">In sintesi, il modo in cui le tabelle interagiscono è cambiato, ma le autorizzazioni delle tabelle nel portale dei clienti non sono cambiate.</span><span class="sxs-lookup"><span data-stu-id="05d95-108">In summary, the way the tables interact has changed, but the table permissions in the customer portal haven't changed.</span></span> <span data-ttu-id="05d95-109">Questo argomento spiega come creare nuovi ruoli Web che funzionano con il nuovo modello di dati avanzato.</span><span class="sxs-lookup"><span data-stu-id="05d95-109">This topic explains how to create new web roles that work with the new advanced data model.</span></span>

<span data-ttu-id="05d95-110">Questo diagramma mostra la relazione tra le tabelle **senza** il modello dei dati la parte e della rubrica globale:</span><span class="sxs-lookup"><span data-stu-id="05d95-110">This diagram shows the table relationship **without** the party and global address book data model:</span></span>

   ![senza modello di parte](media/without-party-model.PNG)

<span data-ttu-id="05d95-112">Questo diagramma mostra la relazione tra le tabelle **con** il modello dei dati la parte e della rubrica globale:</span><span class="sxs-lookup"><span data-stu-id="05d95-112">This diagram shows the table relationship **with** the party and global address book data model:</span></span>

   ![con il modello di parte](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a><span data-ttu-id="05d95-114">Creare una nuova autorizzazione per la tabella</span><span class="sxs-lookup"><span data-stu-id="05d95-114">Create a new table permission</span></span>

<span data-ttu-id="05d95-115">Per creare queste nuove autorizzazioni per la tabella, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="05d95-115">To create these new table permissions, follow these steps:</span></span>

1. <span data-ttu-id="05d95-116">Accedi a [Power Apps](https://make.powerapps.com) e vai alle tue app.</span><span class="sxs-lookup"><span data-stu-id="05d95-116">Sign in to [Power Apps](https://make.powerapps.com), and go to your apps.</span></span>
2. <span data-ttu-id="05d95-117">Seleziona la tua app di gestione del portale.</span><span class="sxs-lookup"><span data-stu-id="05d95-117">Select your Portal Management app.</span></span>
3. <span data-ttu-id="05d95-118">Nella barra laterale, seleziona **Sicurezza > Autorizzazioni tabella**.</span><span class="sxs-lookup"><span data-stu-id="05d95-118">In the side bar, select **Security > Table permissions**.</span></span>

    <span data-ttu-id="05d95-119">Devi creare tre nuove autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="05d95-119">You must create three new permissions:</span></span>

    + <span data-ttu-id="05d95-120">Connessione da contatto a parte</span><span class="sxs-lookup"><span data-stu-id="05d95-120">Contact to Party connection</span></span>
    + <span data-ttu-id="05d95-121">Connessione da parte a conto</span><span class="sxs-lookup"><span data-stu-id="05d95-121">Party to Account connection</span></span>
    + <span data-ttu-id="05d95-122">Connessione da conto a ordine</span><span class="sxs-lookup"><span data-stu-id="05d95-122">Account to Order connection</span></span>

4. <span data-ttu-id="05d95-123">Crea e salva una nuova autorizzazione per la connessione da contatto a parte, impostando questi parametri:</span><span class="sxs-lookup"><span data-stu-id="05d95-123">Create and save a new permission for the Contact to Party connection, setting these parameters:</span></span>

    + <span data-ttu-id="05d95-124">**Nome**: Connessione da parte a conto (o a tua scelta)</span><span class="sxs-lookup"><span data-stu-id="05d95-124">**Name**: Party to Account Connection (or your choice)</span></span>
    + <span data-ttu-id="05d95-125">**Nome tabella**: msdyn_contactforparty</span><span class="sxs-lookup"><span data-stu-id="05d95-125">**Table Name**: msdyn_contactforparty</span></span>
    + <span data-ttu-id="05d95-126">**Sito Web**: portale del cliente</span><span class="sxs-lookup"><span data-stu-id="05d95-126">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="05d95-127">**Ambito**: Contatto</span><span class="sxs-lookup"><span data-stu-id="05d95-127">**Scope**: Contact</span></span>
    + <span data-ttu-id="05d95-128">**Privilegi**: Seleziona tutto</span><span class="sxs-lookup"><span data-stu-id="05d95-128">**Privileges**: Select all</span></span>
    + <span data-ttu-id="05d95-129">**Ruoli Web**: Utenti autenticati, rappresentante clienti (o a scelta)</span><span class="sxs-lookup"><span data-stu-id="05d95-129">**Web roles**: Authenticated Users, Customer Representative (or your choice)</span></span>

5. <span data-ttu-id="05d95-130">Crea e salva una nuova autorizzazione per la connessione da parte a conto, impostando questi parametri:</span><span class="sxs-lookup"><span data-stu-id="05d95-130">Create and save a new permission for the Party to Account connection, setting these parameters:</span></span>

    + <span data-ttu-id="05d95-131">**Nome**: Connessione da parte a conto (o a tua scelta)</span><span class="sxs-lookup"><span data-stu-id="05d95-131">**Name**: Party to Account Connection (or your choice)</span></span>
    + <span data-ttu-id="05d95-132">**Nome tabella**: conto</span><span class="sxs-lookup"><span data-stu-id="05d95-132">**Table Name**: account</span></span>
    + <span data-ttu-id="05d95-133">**Sito Web**: portale del cliente</span><span class="sxs-lookup"><span data-stu-id="05d95-133">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="05d95-134">**Ambito**: padre</span><span class="sxs-lookup"><span data-stu-id="05d95-134">**Scope**: Parent</span></span>
    + <span data-ttu-id="05d95-135">**Privilegi**: Seleziona tutto</span><span class="sxs-lookup"><span data-stu-id="05d95-135">**Privileges**: Select all</span></span>
    + <span data-ttu-id="05d95-136">**Autorizzazione tabella padre**: connessione da contatto a parte</span><span class="sxs-lookup"><span data-stu-id="05d95-136">**Parent Table Permission**: Contact to Party Connection</span></span>

6. <span data-ttu-id="05d95-137">Crea e salva una nuova autorizzazione per la connessione da conto a ordine, impostando questi parametri:</span><span class="sxs-lookup"><span data-stu-id="05d95-137">Create and save a new permission for the Account to Order connection, setting these parameters:</span></span>

    + <span data-ttu-id="05d95-138">**Nome**: Connessione da conto a ordine (o a tua scelta)</span><span class="sxs-lookup"><span data-stu-id="05d95-138">**Name**: Account to Order Connection (or your choice)</span></span>
    + <span data-ttu-id="05d95-139">**Nome tabella**: ordine cliente</span><span class="sxs-lookup"><span data-stu-id="05d95-139">**Table Name**: salesorder</span></span>
    + <span data-ttu-id="05d95-140">**Sito Web**: portale del cliente</span><span class="sxs-lookup"><span data-stu-id="05d95-140">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="05d95-141">**Ambito**: padre</span><span class="sxs-lookup"><span data-stu-id="05d95-141">**Scope**: Parent</span></span>
    + <span data-ttu-id="05d95-142">**Privilegi**: Seleziona tutto</span><span class="sxs-lookup"><span data-stu-id="05d95-142">**Privileges**: Select all</span></span>
    + <span data-ttu-id="05d95-143">**Autorizzazione tabella padre**: connessione da parte a conto</span><span class="sxs-lookup"><span data-stu-id="05d95-143">**Parent Table Permission**: Party to Account Connection</span></span>

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
