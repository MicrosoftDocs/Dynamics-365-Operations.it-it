---
title: Servizio di calcolo delle imposte (anteprima)
description: In questo argomento vengono illustrati l'ambito e le funzionalità generali del servizio di calcolo delle imposte.
author: wangchen
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 518d3fda7b97e55d23beea6a1ba0e50b44a7aa0e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818226"
---
# <a name="tax-calculation-service-preview"></a><span data-ttu-id="2d25d-103">Servizio di calcolo delle imposte (anteprima)</span><span class="sxs-lookup"><span data-stu-id="2d25d-103">Tax calculation service (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="2d25d-104">Il servizio di calcolo delle imposte è un servizio multitenant iperscalabile che consente al Global Tax Engine di automatizzare e semplificare il processo di determinazione e calcolo delle imposte.</span><span class="sxs-lookup"><span data-stu-id="2d25d-104">The tax calculation service is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="2d25d-105">Il motore fiscale è completamente configurabile.</span><span class="sxs-lookup"><span data-stu-id="2d25d-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="2d25d-106">Gli elementi che possono essere configurati includono, tra gli altri, il modello di dati imponibili, il codice imposta, la matrice di applicabilità fiscale e la formula di calcolo dell'imposta.</span><span class="sxs-lookup"><span data-stu-id="2d25d-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="2d25d-107">Il motore fiscale funziona sulla piattaforma di servizi di base Microsoft Azure e offre una tecnologia moderna e la scalabilità esponenziale.</span><span class="sxs-lookup"><span data-stu-id="2d25d-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="2d25d-108">Il servizio di calcolo delle imposte si integra con Dynamics 365 Finance e Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2d25d-108">The tax calculation service integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="2d25d-109">Alla fine, si integrerà anche con Dynamics 365 Project Operations, Dynamics 365 Commerce e altre applicazioni proprietarie e di terze parti.</span><span class="sxs-lookup"><span data-stu-id="2d25d-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="2d25d-110">Il servizio di calcolo delle imposte è un motore fiscale basato su Microsoft che offre scalabilità esponenziale.</span><span class="sxs-lookup"><span data-stu-id="2d25d-110">The tax calculation service is a Microsoft-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="2d25d-111">Ti consente di eseguire le attività descritte di seguito:</span><span class="sxs-lookup"><span data-stu-id="2d25d-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="2d25d-112">Configura il servizio di calcolo delle imposte tramite Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="2d25d-112">Configure the tax calculation service through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="2d25d-113">RCS è una versione avanzata dello strumento di progettazione per la creazione di report elettronici (ER) ed è disponibile come servizio autonomo.</span><span class="sxs-lookup"><span data-stu-id="2d25d-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="2d25d-114">Configura la matrice fiscale per determinare automaticamente i codici e le aliquote fiscali.</span><span class="sxs-lookup"><span data-stu-id="2d25d-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="2d25d-115">Configura la matrice fiscale per determinare automaticamente il numero di registrazione fiscale.</span><span class="sxs-lookup"><span data-stu-id="2d25d-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="2d25d-116">Configura lo strumento di progettazione del calcolo delle imposte per definire le formule e le condizioni.</span><span class="sxs-lookup"><span data-stu-id="2d25d-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="2d25d-117">Condividi la determinazione delle imposte e la soluzione di calcolo tra le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="2d25d-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="2d25d-118">Per utilizzare il servizio di calcolo delle imposte, installa il componente aggiuntivo del servizio di calcolo delle imposte dal progetto in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="2d25d-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="2d25d-119">Quindi completa la configurazione in RCS e abilita il servizio di calcolo delle imposte in Finance and Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2d25d-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="2d25d-120">Per altre informazioni, vedi [Introduzione al servizio per le imposte](https://go.microsoft.com/fwlink/?linkid=2138482).</span><span class="sxs-lookup"><span data-stu-id="2d25d-120">For more information, see [Get started with tax service](https://go.microsoft.com/fwlink/?linkid=2138482).</span></span>

## <a name="availability"></a><span data-ttu-id="2d25d-121">Disponibilità</span><span class="sxs-lookup"><span data-stu-id="2d25d-121">Availability</span></span>

<span data-ttu-id="2d25d-122">Il servizio di calcolo delle imposte è disponibile solo in ambienti sandbox e per clienti selezionati, attraverso un programma di anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="2d25d-122">The tax calculation service is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="2d25d-123">Alla fine, diventerà generalmente disponibile per tutti i clienti e negli ambienti di produzione.</span><span class="sxs-lookup"><span data-stu-id="2d25d-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="2d25d-124">Nuove funzionalità continueranno a essere aggiunte nel servizio di calcolo delle imposte.</span><span class="sxs-lookup"><span data-stu-id="2d25d-124">New features will continue to be delivered in the tax calculation service.</span></span> <span data-ttu-id="2d25d-125">Pertanto, assicurati di controllare spesso la documentazione più aggiornata per conoscere la copertura e l'ambito delle funzionalità supportate.</span><span class="sxs-lookup"><span data-stu-id="2d25d-125">Therefore, be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="2d25d-126">Il servizio di calcolo delle imposte viene distribuito nelle seguenti aree geografiche di Azure.</span><span class="sxs-lookup"><span data-stu-id="2d25d-126">The tax calculation service is deployed in the following Azure geographies.</span></span> <span data-ttu-id="2d25d-127">Verrà inoltre distribuito in più aree geografiche di Azure, in base alle esigenze del cliente:</span><span class="sxs-lookup"><span data-stu-id="2d25d-127">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="2d25d-128">Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="2d25d-128">United States</span></span>
- <span data-ttu-id="2d25d-129">Europa</span><span class="sxs-lookup"><span data-stu-id="2d25d-129">Europe</span></span>
- <span data-ttu-id="2d25d-130">Francia</span><span class="sxs-lookup"><span data-stu-id="2d25d-130">France</span></span>
- <span data-ttu-id="2d25d-131">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="2d25d-131">United Kingdom</span></span>

> [!NOTE]
> <span data-ttu-id="2d25d-132">Il servizio di calcolo delle imposte non supporta le distribuzioni locali di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="2d25d-132">The tax calculation service doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="2d25d-133">Inoltre non supporta le versioni precedenti, come Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="2d25d-133">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="2d25d-134">Caratteristiche principali</span><span class="sxs-lookup"><span data-stu-id="2d25d-134">Feature highlights</span></span>

- <span data-ttu-id="2d25d-135">Una matrice fiscale configurabile per determinare automaticamente e calcolare le imposte</span><span class="sxs-lookup"><span data-stu-id="2d25d-135">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="2d25d-136">Supporto per più numeri di registrazione dell'IVA</span><span class="sxs-lookup"><span data-stu-id="2d25d-136">Support for multiple value-added tax (VAT) registration numbers</span></span>
- <span data-ttu-id="2d25d-137">Supporto dell'ordine di trasferimento per la determinazione e il calcolo delle imposte</span><span class="sxs-lookup"><span data-stu-id="2d25d-137">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="2d25d-138">Supporto per ordini di trasferimento per la determinazione di più numeri di registrazione dell'IVA</span><span class="sxs-lookup"><span data-stu-id="2d25d-138">Transfer order support for determination of multiple VAT registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="2d25d-139">Transazioni supportate</span><span class="sxs-lookup"><span data-stu-id="2d25d-139">Supported transactions</span></span>

<span data-ttu-id="2d25d-140">Il servizio di calcolo delle imposte può essere abilitato per persona giuridica e transazione.</span><span class="sxs-lookup"><span data-stu-id="2d25d-140">The tax calculation service can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="2d25d-141">Sono supportate le transazioni che seguono:</span><span class="sxs-lookup"><span data-stu-id="2d25d-141">The following transactions are supported:</span></span>

- <span data-ttu-id="2d25d-142">Processo di vendita</span><span class="sxs-lookup"><span data-stu-id="2d25d-142">Sales process</span></span>

    - <span data-ttu-id="2d25d-143">Offerta di vendita</span><span class="sxs-lookup"><span data-stu-id="2d25d-143">Sales quotation</span></span>
    - <span data-ttu-id="2d25d-144">Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="2d25d-144">Sales order</span></span>
    - <span data-ttu-id="2d25d-145">Conferma</span><span class="sxs-lookup"><span data-stu-id="2d25d-145">Confirmation</span></span>
    - <span data-ttu-id="2d25d-146">Distinta di prelievo</span><span class="sxs-lookup"><span data-stu-id="2d25d-146">Picking list</span></span>
    - <span data-ttu-id="2d25d-147">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="2d25d-147">Packing slip</span></span>
    - <span data-ttu-id="2d25d-148">Fattura di vendita</span><span class="sxs-lookup"><span data-stu-id="2d25d-148">Sales invoice</span></span>
    - <span data-ttu-id="2d25d-149">Nota di accredito</span><span class="sxs-lookup"><span data-stu-id="2d25d-149">Credit note</span></span>
    - <span data-ttu-id="2d25d-150">Ordine di reso</span><span class="sxs-lookup"><span data-stu-id="2d25d-150">Return order</span></span>
    - <span data-ttu-id="2d25d-151">Spese varie intestazione</span><span class="sxs-lookup"><span data-stu-id="2d25d-151">Header miscellaneous charge</span></span>
    - <span data-ttu-id="2d25d-152">Spese varie riga</span><span class="sxs-lookup"><span data-stu-id="2d25d-152">Line miscellaneous charge</span></span>

- <span data-ttu-id="2d25d-153">Processo di acquisto</span><span class="sxs-lookup"><span data-stu-id="2d25d-153">Purchase process</span></span>

    - <span data-ttu-id="2d25d-154">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="2d25d-154">Purchase order</span></span>
    - <span data-ttu-id="2d25d-155">Conferma</span><span class="sxs-lookup"><span data-stu-id="2d25d-155">Confirmation</span></span>
    - <span data-ttu-id="2d25d-156">Elenco entrate</span><span class="sxs-lookup"><span data-stu-id="2d25d-156">Receipts list</span></span>
    - <span data-ttu-id="2d25d-157">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="2d25d-157">Product receipt</span></span>
    - <span data-ttu-id="2d25d-158">Fattura acquisto</span><span class="sxs-lookup"><span data-stu-id="2d25d-158">Purchase invoice</span></span>
    - <span data-ttu-id="2d25d-159">Spese varie intestazione</span><span class="sxs-lookup"><span data-stu-id="2d25d-159">Header miscellaneous charge</span></span>
    - <span data-ttu-id="2d25d-160">Spese varie riga</span><span class="sxs-lookup"><span data-stu-id="2d25d-160">Line miscellaneous charge</span></span>
    - <span data-ttu-id="2d25d-161">Nota di accredito</span><span class="sxs-lookup"><span data-stu-id="2d25d-161">Credit note</span></span>
    - <span data-ttu-id="2d25d-162">Ordine di reso</span><span class="sxs-lookup"><span data-stu-id="2d25d-162">Return order</span></span>
    - <span data-ttu-id="2d25d-163">Richiesta di acquisto</span><span class="sxs-lookup"><span data-stu-id="2d25d-163">Purchase requisition</span></span>
    - <span data-ttu-id="2d25d-164">Spese varie riga di richiesta di acquisto</span><span class="sxs-lookup"><span data-stu-id="2d25d-164">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="2d25d-165">Richiesta di offerta</span><span class="sxs-lookup"><span data-stu-id="2d25d-165">Request for quotation</span></span>
    - <span data-ttu-id="2d25d-166">Spese varie intestazione richiesta di offerta</span><span class="sxs-lookup"><span data-stu-id="2d25d-166">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="2d25d-167">Spese varie riga richiesta di offerta</span><span class="sxs-lookup"><span data-stu-id="2d25d-167">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="2d25d-168">Processo magazzino</span><span class="sxs-lookup"><span data-stu-id="2d25d-168">Inventory process</span></span>

    - <span data-ttu-id="2d25d-169">Ordine di trasferimento - spedizione</span><span class="sxs-lookup"><span data-stu-id="2d25d-169">Transfer order – ship</span></span>
    - <span data-ttu-id="2d25d-170">Ordine di trasferimento - ricezione</span><span class="sxs-lookup"><span data-stu-id="2d25d-170">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="2d25d-171">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="2d25d-171">Related resources</span></span>

[<span data-ttu-id="2d25d-172">Introduzione al servizio per le imposte</span><span class="sxs-lookup"><span data-stu-id="2d25d-172">Get started with tax service</span></span>](https://go.microsoft.com/fwlink/?linkid=2138482)

[<span data-ttu-id="2d25d-173">Più numeri di registrazione IVA</span><span class="sxs-lookup"><span data-stu-id="2d25d-173">Multiple VAT registration number</span></span>](https://go.microsoft.com/fwlink/?linkid=2153387)

[<span data-ttu-id="2d25d-174">Supporto della funzione fiscale per l'ordine di trasferimento</span><span class="sxs-lookup"><span data-stu-id="2d25d-174">Tax feature support for transfer order</span></span>](https://go.microsoft.com/fwlink/?linkid=2153388)

[<span data-ttu-id="2d25d-175">Come creare l'estensione nel servizio per le imposte</span><span class="sxs-lookup"><span data-stu-id="2d25d-175">How to build extension in tax service</span></span>](https://go.microsoft.com/fwlink/?linkid=2138483)
