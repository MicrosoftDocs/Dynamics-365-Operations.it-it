---
title: Configurare un ambiente di sviluppo di e-commerce per eseguire il debug su una macchina virtuale Retail Server di livello 1
description: Questo argomento descrive come configurare un ambiente di sviluppo di e-commerce per eseguire il debug su una macchina virtuale (VM) Retail Server di livello 1
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 38a616c418c3b32490c9adaf69a69af0d47d3478
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019448"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a><span data-ttu-id="25936-103">Configurare un ambiente di sviluppo di e-commerce per eseguire il debug su una macchina virtuale Retail Server di livello 1</span><span class="sxs-lookup"><span data-stu-id="25936-103">Set up an e-commerce development environment to debug against a Tier 1 Retail Server virtual machine</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="25936-104">Questo argomento descrive come configurare un ambiente di sviluppo di e-commerce per eseguire il debug su una macchina virtuale (VM) Retail Server di livello 1</span><span class="sxs-lookup"><span data-stu-id="25936-104">This topic explains how to set up an e-commerce development environment to debug against a Tier 1 Retail Server virtual machine (VM).</span></span>

## <a name="description"></a><span data-ttu-id="25936-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25936-105">Description</span></span>

<span data-ttu-id="25936-106">Gli ambienti Microsoft Dynamics 365 Commerce di livello 1 sono in genere distribuiti per lo sviluppo di Commerce Runtime (CRT) e dell'estensione POS.</span><span class="sxs-lookup"><span data-stu-id="25936-106">Microsoft Dynamics 365 Commerce Tier 1 environments are typically deployed for Commerce runtime (CRT) and point of sale (POS) extension development.</span></span> <span data-ttu-id="25936-107">Si tratta di ambienti autonomi.</span><span class="sxs-lookup"><span data-stu-id="25936-107">They are standalone environments.</span></span> <span data-ttu-id="25936-108">A seguito della natura SaaS (Software as a Service) dell'architettura, non includono componenti di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="25936-108">Because of the software as a service (SaaS) nature of the architecture, they don't include e-commerce components.</span></span>

<span data-ttu-id="25936-109">In alcuni scenari, è possibile che si intenda testare le chiamate alle estensioni in un ambiente di livello 1, in modo da poter eseguire il debug delle estensioni dai componenti di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="25936-109">In some scenarios, you might want to test calls to extensions in a Tier 1 environment, so that you can debug extensions from e-commerce components.</span></span> <span data-ttu-id="25936-110">Per istruzioni generali, vedere [Debug di un ambiente di sviluppo di Commerce di livello 1](../e-commerce-extensibility/debug-tier-1.md).</span><span class="sxs-lookup"><span data-stu-id="25936-110">For general instructions, see [Debug against a Tier 1 Commerce development environment](../e-commerce-extensibility/debug-tier-1.md).</span></span>

<span data-ttu-id="25936-111">Quando si esegue il debug in un ambiente di livello 1, poiché il sito ora chiama un Retail Server diverso, le chiamate tra server potrebbero causare vari errori correlati ai criteri di protezione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="25936-111">When you debug against a Tier 1 environment, because the site is now calling a different Retail Server, cross-server calls might cause various errors that are related to the content security policy.</span></span>

<span data-ttu-id="25936-112">La seguente illustrazione mostra un esempio di errore che potrebbe verificarsi quando una variante viene selezionata in una pagina dei dettagli del prodotto.</span><span class="sxs-lookup"><span data-stu-id="25936-112">The following illustration shows an example of an error that might occur when a variant is selected on a product details page.</span></span>

![Errore durante la selezione di una variante in una pagina dei dettagli del prodotto](media/unhandled-rejection-error.jpg)

<span data-ttu-id="25936-114">L'illustrazione seguente mostra un esempio di errore simile negli strumenti di debug di un browser (Strumenti di sviluppo F12).</span><span class="sxs-lookup"><span data-stu-id="25936-114">The following illustration shows an example of a similar error in a browser's debugger tools (F12 Developer Tools).</span></span> <span data-ttu-id="25936-115">Il messaggio di errore menziona la violazione della direttiva sui criteri di sicurezza del contenuto.</span><span class="sxs-lookup"><span data-stu-id="25936-115">The error message mentions violation of the content security policy directive.</span></span>

![Errore degli strumenti di debug](media/debugger-tools-error.JPG)

## <a name="resolution"></a><span data-ttu-id="25936-117">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="25936-117">Resolution</span></span>

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a><span data-ttu-id="25936-118">Disabilitare i criteri di sicurezza del contenuto per il sito in Creazione di siti di Commerce</span><span class="sxs-lookup"><span data-stu-id="25936-118">Disable the content security policy for the site in Commerce site builder</span></span>

1. <span data-ttu-id="25936-119">Selezionare il sito sul quale si sta lavorando.</span><span class="sxs-lookup"><span data-stu-id="25936-119">Select the site that you're working on.</span></span>
1. <span data-ttu-id="25936-120">Selezionare **Impostazioni**, quindi selezionare **Estensioni**.</span><span class="sxs-lookup"><span data-stu-id="25936-120">Select **Settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="25936-121">Nella scheda **Criteri di sicurezza dei contenuti**, selezionare **Disabilita criteri di sicurezza del contenuto**.</span><span class="sxs-lookup"><span data-stu-id="25936-121">On the **Content security policy** tab, select **Disable content security policy**.</span></span>
1. <span data-ttu-id="25936-122">Seleziona **Salva e pubblica**.</span><span class="sxs-lookup"><span data-stu-id="25936-122">Select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="25936-123">L'accesso business-to-consumer (B2C) non funzionerà in un ambiente di sviluppo locale.</span><span class="sxs-lookup"><span data-stu-id="25936-123">Business-to-consumer (B2C) sign-in won't work in a local development environment.</span></span> <span data-ttu-id="25936-124">Tuttavia, è possibile utilizzare checkout guest o creare simulazioni di pagine per simulare l'accesso utente come richiesto.</span><span class="sxs-lookup"><span data-stu-id="25936-124">However, you can use guest checkouts or build page mocks to simulate a user sign-in as required.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25936-125">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="25936-125">Additional resources</span></span>

[<span data-ttu-id="25936-126">Introduzione allo sviluppo dell'estensibilità online dell'e-commerce</span><span class="sxs-lookup"><span data-stu-id="25936-126">Get started with e-commerce online extensibility development</span></span>](../e-commerce-extensibility/sdk-getting-started.md)

[<span data-ttu-id="25936-127">Gestire criteri di sicurezza dei contenuti nel sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="25936-127">Manage content security policy (CSP) on e-commerce site</span></span>](../manage-csp.md)
