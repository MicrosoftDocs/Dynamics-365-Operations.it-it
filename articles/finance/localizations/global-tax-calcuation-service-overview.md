---
title: Calcolo imposte (anteprima)
description: In questo argomento vengono illustrati l'ambito e le funzionalità generali di Calcolo imposte.
author: wangchen
ms.date: 04/12/2021
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
ms.openlocfilehash: 3df952e0632807e55f176e63dc2047be5e622ec2
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892351"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="9c372-103">Calcolo imposte (anteprima)</span><span class="sxs-lookup"><span data-stu-id="9c372-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="9c372-104">Calcolo imposte è un servizio multitenant iperscalabile che consente al Global Tax Engine di automatizzare e semplificare il processo di determinazione e calcolo delle imposte.</span><span class="sxs-lookup"><span data-stu-id="9c372-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="9c372-105">Il motore fiscale è completamente configurabile.</span><span class="sxs-lookup"><span data-stu-id="9c372-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="9c372-106">Gli elementi che possono essere configurati includono, tra gli altri, il modello di dati imponibili, il codice imposta, la matrice di applicabilità fiscale e la formula di calcolo dell'imposta.</span><span class="sxs-lookup"><span data-stu-id="9c372-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="9c372-107">Il motore fiscale funziona sulla piattaforma di servizi di base Microsoft Azure e offre una tecnologia moderna e la scalabilità esponenziale.</span><span class="sxs-lookup"><span data-stu-id="9c372-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="9c372-108">Calcolo imposte si integra con Dynamics 365 Finance e Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9c372-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="9c372-109">Alla fine, si integrerà anche con Dynamics 365 Project Operations, Dynamics 365 Commerce e altre applicazioni proprietarie e di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9c372-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="9c372-110">Calcolo imposte è un motore fiscale basato su microservizi che offre scalabilità esponenziale.</span><span class="sxs-lookup"><span data-stu-id="9c372-110">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="9c372-111">Ti consente di eseguire le attività descritte di seguito:</span><span class="sxs-lookup"><span data-stu-id="9c372-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="9c372-112">Configura Calcolo imposte tramite Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="9c372-112">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="9c372-113">RCS è una versione avanzata dello strumento di progettazione per la creazione di report elettronici (ER) ed è disponibile come servizio autonomo.</span><span class="sxs-lookup"><span data-stu-id="9c372-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="9c372-114">Configura la matrice fiscale per determinare automaticamente i codici e le aliquote fiscali.</span><span class="sxs-lookup"><span data-stu-id="9c372-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="9c372-115">Configura la matrice fiscale per determinare automaticamente la partita IVA.</span><span class="sxs-lookup"><span data-stu-id="9c372-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="9c372-116">Configura lo strumento di progettazione del calcolo delle imposte per definire le formule e le condizioni.</span><span class="sxs-lookup"><span data-stu-id="9c372-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="9c372-117">Condividi la determinazione delle imposte e la soluzione di calcolo tra le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="9c372-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="9c372-118">Per utilizzare il servizio di calcolo delle imposte, installa il componente aggiuntivo del servizio di calcolo delle imposte dal progetto in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="9c372-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="9c372-119">Quindi completa la configurazione in RCS e abilita il servizio di calcolo delle imposte in Finance and Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9c372-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="9c372-120">Per altre informazioni, vedi [Introduzione al servizio per le imposte](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="9c372-120">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="9c372-121">Disponibilità</span><span class="sxs-lookup"><span data-stu-id="9c372-121">Availability</span></span>

<span data-ttu-id="9c372-122">Calcolo imposte è disponibile solo in ambienti sandbox e per clienti selezionati, attraverso un programma di anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="9c372-122">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="9c372-123">Alla fine, diventerà generalmente disponibile per tutti i clienti e negli ambienti di produzione.</span><span class="sxs-lookup"><span data-stu-id="9c372-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="9c372-124">In seguito, verranno fornite continuamente nuove funzionalità, pertanto assicurati di controllare spesso la documentazione più aggiornata per conoscere la copertura e l'ambito delle funzionalità supportate.</span><span class="sxs-lookup"><span data-stu-id="9c372-124">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="9c372-125">Calcolo imposte viene distribuito nelle seguenti aree geografiche di Azure.</span><span class="sxs-lookup"><span data-stu-id="9c372-125">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="9c372-126">Verrà inoltre distribuito in più aree geografiche di Azure, in base alle esigenze del cliente:</span><span class="sxs-lookup"><span data-stu-id="9c372-126">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="9c372-127">Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="9c372-127">United States</span></span>
- <span data-ttu-id="9c372-128">Europa</span><span class="sxs-lookup"><span data-stu-id="9c372-128">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="9c372-129">Calcolo imposte non supporta le distribuzioni locali di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9c372-129">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="9c372-130">Inoltre non supporta le versioni precedenti, come Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="9c372-130">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="9c372-131">Caratteristiche principali</span><span class="sxs-lookup"><span data-stu-id="9c372-131">Feature highlights</span></span>

- <span data-ttu-id="9c372-132">Una matrice fiscale configurabile per determinare automaticamente e calcolare le imposte</span><span class="sxs-lookup"><span data-stu-id="9c372-132">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="9c372-133">Supporto per più partite IVA</span><span class="sxs-lookup"><span data-stu-id="9c372-133">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="9c372-134">Supporto dell'ordine di trasferimento per la determinazione e il calcolo delle imposte</span><span class="sxs-lookup"><span data-stu-id="9c372-134">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="9c372-135">Supporto per ordini di trasferimento per la determinazione di più partite IVA</span><span class="sxs-lookup"><span data-stu-id="9c372-135">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="9c372-136">Transazioni supportate</span><span class="sxs-lookup"><span data-stu-id="9c372-136">Supported transactions</span></span>

<span data-ttu-id="9c372-137">Calcolo imposte può essere abilitato per persona giuridica e transazione.</span><span class="sxs-lookup"><span data-stu-id="9c372-137">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="9c372-138">Sono supportate le transazioni che seguono:</span><span class="sxs-lookup"><span data-stu-id="9c372-138">The following transactions are supported:</span></span>

- <span data-ttu-id="9c372-139">Processo di vendita</span><span class="sxs-lookup"><span data-stu-id="9c372-139">Sales process</span></span>

    - <span data-ttu-id="9c372-140">Offerta di vendita</span><span class="sxs-lookup"><span data-stu-id="9c372-140">Sales quotation</span></span>
    - <span data-ttu-id="9c372-141">Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="9c372-141">Sales order</span></span>
    - <span data-ttu-id="9c372-142">Conferma</span><span class="sxs-lookup"><span data-stu-id="9c372-142">Confirmation</span></span>
    - <span data-ttu-id="9c372-143">Distinta di prelievo</span><span class="sxs-lookup"><span data-stu-id="9c372-143">Picking list</span></span>
    - <span data-ttu-id="9c372-144">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="9c372-144">Packing slip</span></span>
    - <span data-ttu-id="9c372-145">Fattura di vendita</span><span class="sxs-lookup"><span data-stu-id="9c372-145">Sales invoice</span></span>
    - <span data-ttu-id="9c372-146">Nota di accredito</span><span class="sxs-lookup"><span data-stu-id="9c372-146">Credit note</span></span>
    - <span data-ttu-id="9c372-147">Ordine di reso</span><span class="sxs-lookup"><span data-stu-id="9c372-147">Return order</span></span>
    - <span data-ttu-id="9c372-148">Spese varie intestazione</span><span class="sxs-lookup"><span data-stu-id="9c372-148">Header miscellaneous charge</span></span>
    - <span data-ttu-id="9c372-149">Spese varie riga</span><span class="sxs-lookup"><span data-stu-id="9c372-149">Line miscellaneous charge</span></span>

- <span data-ttu-id="9c372-150">Processo di acquisto</span><span class="sxs-lookup"><span data-stu-id="9c372-150">Purchase process</span></span>

    - <span data-ttu-id="9c372-151">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="9c372-151">Purchase order</span></span>
    - <span data-ttu-id="9c372-152">Conferma</span><span class="sxs-lookup"><span data-stu-id="9c372-152">Confirmation</span></span>
    - <span data-ttu-id="9c372-153">Elenco entrate</span><span class="sxs-lookup"><span data-stu-id="9c372-153">Receipts list</span></span>
    - <span data-ttu-id="9c372-154">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="9c372-154">Product receipt</span></span>
    - <span data-ttu-id="9c372-155">Fattura acquisto</span><span class="sxs-lookup"><span data-stu-id="9c372-155">Purchase invoice</span></span>
    - <span data-ttu-id="9c372-156">Spese varie intestazione</span><span class="sxs-lookup"><span data-stu-id="9c372-156">Header miscellaneous charge</span></span>
    - <span data-ttu-id="9c372-157">Spese varie riga</span><span class="sxs-lookup"><span data-stu-id="9c372-157">Line miscellaneous charge</span></span>
    - <span data-ttu-id="9c372-158">Nota di accredito</span><span class="sxs-lookup"><span data-stu-id="9c372-158">Credit note</span></span>
    - <span data-ttu-id="9c372-159">Ordine di reso</span><span class="sxs-lookup"><span data-stu-id="9c372-159">Return order</span></span>
    - <span data-ttu-id="9c372-160">Richiesta di acquisto</span><span class="sxs-lookup"><span data-stu-id="9c372-160">Purchase requisition</span></span>
    - <span data-ttu-id="9c372-161">Spese varie riga di richiesta di acquisto</span><span class="sxs-lookup"><span data-stu-id="9c372-161">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="9c372-162">Richiesta di offerta</span><span class="sxs-lookup"><span data-stu-id="9c372-162">Request for quotation</span></span>
    - <span data-ttu-id="9c372-163">Spese varie intestazione richiesta di offerta</span><span class="sxs-lookup"><span data-stu-id="9c372-163">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="9c372-164">Spese varie riga richiesta di offerta</span><span class="sxs-lookup"><span data-stu-id="9c372-164">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="9c372-165">Processo magazzino</span><span class="sxs-lookup"><span data-stu-id="9c372-165">Inventory process</span></span>

    - <span data-ttu-id="9c372-166">Ordine di trasferimento - spedizione</span><span class="sxs-lookup"><span data-stu-id="9c372-166">Transfer order – ship</span></span>
    - <span data-ttu-id="9c372-167">Ordine di trasferimento - ricezione</span><span class="sxs-lookup"><span data-stu-id="9c372-167">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="9c372-168">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="9c372-168">Related resources</span></span>

[<span data-ttu-id="9c372-169">Introduzione al servizio per le imposte</span><span class="sxs-lookup"><span data-stu-id="9c372-169">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="9c372-170">Più numeri di registrazione IVA</span><span class="sxs-lookup"><span data-stu-id="9c372-170">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="9c372-171">Supporto della funzione fiscale per l'ordine di trasferimento</span><span class="sxs-lookup"><span data-stu-id="9c372-171">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="9c372-172">Come creare l'estensione nel servizio per le imposte</span><span class="sxs-lookup"><span data-stu-id="9c372-172">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)