---
title: Calcolo imposte (anteprima)
description: In questo argomento vengono illustrati l'ambito e le funzionalità generali di Calcolo imposte.
author: wangchen
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 9daa6e001200d03a2639974fb6de618d77ddf09d
ms.sourcegitcommit: cb282e8d2306ab71adf80a84346a6863d2d019e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "6184103"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="c4500-103">Calcolo imposte (anteprima)</span><span class="sxs-lookup"><span data-stu-id="c4500-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="c4500-104">Calcolo imposte è un servizio multitenant iperscalabile che consente al Global Tax Engine di automatizzare e semplificare il processo di determinazione e calcolo delle imposte.</span><span class="sxs-lookup"><span data-stu-id="c4500-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="c4500-105">Il motore fiscale è completamente configurabile.</span><span class="sxs-lookup"><span data-stu-id="c4500-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="c4500-106">Gli elementi che possono essere configurati includono, tra gli altri, il modello di dati imponibili, il codice imposta, la matrice di applicabilità fiscale e la formula di calcolo dell'imposta.</span><span class="sxs-lookup"><span data-stu-id="c4500-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="c4500-107">Il motore fiscale funziona sulla piattaforma di servizi di base Microsoft Azure e offre una tecnologia moderna e la scalabilità esponenziale.</span><span class="sxs-lookup"><span data-stu-id="c4500-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="c4500-108">Calcolo imposte si integra con Dynamics 365 Finance e Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c4500-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="c4500-109">Alla fine, si integrerà anche con Dynamics 365 Project Operations, Dynamics 365 Commerce e altre applicazioni proprietarie e di terze parti.</span><span class="sxs-lookup"><span data-stu-id="c4500-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4500-110">Quando si abilita il servizio di calcolo delle imposte, alcune operazioni sui dati correlati potrebbero essere eseguite in un data center diverso da quello che gestisce i dati del servizio.</span><span class="sxs-lookup"><span data-stu-id="c4500-110">When you enable the Tax Calculation service, some operations on related data might be performed in a data center other than the data center that maintains your service data.</span></span> <span data-ttu-id="c4500-111">Rivedere i [termini e condizioni](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) prima di abilitare il servizio di calcolo delle imposte.</span><span class="sxs-lookup"><span data-stu-id="c4500-111">Review the [Terms and Conditions](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) before you enable the Tax Calculation service.</span></span> <span data-ttu-id="c4500-112">La privacy è molto importante.</span><span class="sxs-lookup"><span data-stu-id="c4500-112">Your privacy is important to us.</span></span> <span data-ttu-id="c4500-113">Per ulteriori informazioni, leggere l'[Informativa sulla privacy](https://go.microsoft.com/fwlink/?LinkId=521839) di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4500-113">To learn more, read our [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=521839).</span></span>

<span data-ttu-id="c4500-114">Calcolo imposte è un motore fiscale basato su microservizi che offre scalabilità esponenziale.</span><span class="sxs-lookup"><span data-stu-id="c4500-114">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="c4500-115">Ti consente di eseguire le attività descritte di seguito:</span><span class="sxs-lookup"><span data-stu-id="c4500-115">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="c4500-116">Configura Calcolo imposte tramite Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="c4500-116">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="c4500-117">RCS è una versione avanzata dello strumento di progettazione per la creazione di report elettronici (ER) ed è disponibile come servizio autonomo.</span><span class="sxs-lookup"><span data-stu-id="c4500-117">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="c4500-118">Configura la matrice fiscale per determinare automaticamente i codici e le aliquote fiscali.</span><span class="sxs-lookup"><span data-stu-id="c4500-118">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="c4500-119">Configura la matrice fiscale per determinare automaticamente la partita IVA.</span><span class="sxs-lookup"><span data-stu-id="c4500-119">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="c4500-120">Configura lo strumento di progettazione del calcolo delle imposte per definire le formule e le condizioni.</span><span class="sxs-lookup"><span data-stu-id="c4500-120">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="c4500-121">Condividi la determinazione delle imposte e la soluzione di calcolo tra le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="c4500-121">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="c4500-122">Per utilizzare il servizio di calcolo delle imposte, installa il componente aggiuntivo del servizio di calcolo delle imposte dal progetto in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c4500-122">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="c4500-123">Quindi completa la configurazione in RCS e abilita il servizio di calcolo delle imposte in Finance and Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c4500-123">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="c4500-124">Per altre informazioni, vedi [Introduzione al servizio per le imposte](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="c4500-124">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="c4500-125">Disponibilità</span><span class="sxs-lookup"><span data-stu-id="c4500-125">Availability</span></span>

<span data-ttu-id="c4500-126">Calcolo imposte è disponibile solo in ambienti sandbox e per clienti selezionati, attraverso un programma di anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="c4500-126">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="c4500-127">Alla fine, diventerà generalmente disponibile per tutti i clienti e negli ambienti di produzione.</span><span class="sxs-lookup"><span data-stu-id="c4500-127">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="c4500-128">In seguito, verranno fornite continuamente nuove funzionalità, pertanto assicurati di controllare spesso la documentazione più aggiornata per conoscere la copertura e l'ambito delle funzionalità supportate.</span><span class="sxs-lookup"><span data-stu-id="c4500-128">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="c4500-129">Calcolo imposte viene distribuito nelle seguenti aree geografiche di Azure.</span><span class="sxs-lookup"><span data-stu-id="c4500-129">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="c4500-130">Verrà inoltre distribuito in più aree geografiche di Azure, in base alle esigenze del cliente:</span><span class="sxs-lookup"><span data-stu-id="c4500-130">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="c4500-131">Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="c4500-131">United States</span></span>
- <span data-ttu-id="c4500-132">Europa</span><span class="sxs-lookup"><span data-stu-id="c4500-132">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="c4500-133">Calcolo imposte non supporta le distribuzioni locali di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c4500-133">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="c4500-134">Inoltre non supporta le versioni precedenti, come Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="c4500-134">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="c4500-135">Caratteristiche principali</span><span class="sxs-lookup"><span data-stu-id="c4500-135">Feature highlights</span></span>

- <span data-ttu-id="c4500-136">Una matrice fiscale configurabile per determinare automaticamente e calcolare le imposte</span><span class="sxs-lookup"><span data-stu-id="c4500-136">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="c4500-137">Supporto per più partite IVA</span><span class="sxs-lookup"><span data-stu-id="c4500-137">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="c4500-138">Supporto dell'ordine di trasferimento per la determinazione e il calcolo delle imposte</span><span class="sxs-lookup"><span data-stu-id="c4500-138">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="c4500-139">Supporto per ordini di trasferimento per la determinazione di più partite IVA</span><span class="sxs-lookup"><span data-stu-id="c4500-139">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="c4500-140">Transazioni supportate</span><span class="sxs-lookup"><span data-stu-id="c4500-140">Supported transactions</span></span>

<span data-ttu-id="c4500-141">Calcolo imposte può essere abilitato per persona giuridica e transazione.</span><span class="sxs-lookup"><span data-stu-id="c4500-141">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="c4500-142">Sono supportate le transazioni che seguono:</span><span class="sxs-lookup"><span data-stu-id="c4500-142">The following transactions are supported:</span></span>

- <span data-ttu-id="c4500-143">Processo di vendita</span><span class="sxs-lookup"><span data-stu-id="c4500-143">Sales process</span></span>

    - <span data-ttu-id="c4500-144">Offerta di vendita</span><span class="sxs-lookup"><span data-stu-id="c4500-144">Sales quotation</span></span>
    - <span data-ttu-id="c4500-145">Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="c4500-145">Sales order</span></span>
    - <span data-ttu-id="c4500-146">Conferma</span><span class="sxs-lookup"><span data-stu-id="c4500-146">Confirmation</span></span>
    - <span data-ttu-id="c4500-147">Distinta di prelievo</span><span class="sxs-lookup"><span data-stu-id="c4500-147">Picking list</span></span>
    - <span data-ttu-id="c4500-148">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="c4500-148">Packing slip</span></span>
    - <span data-ttu-id="c4500-149">Fattura di vendita</span><span class="sxs-lookup"><span data-stu-id="c4500-149">Sales invoice</span></span>
    - <span data-ttu-id="c4500-150">Nota di accredito</span><span class="sxs-lookup"><span data-stu-id="c4500-150">Credit note</span></span>
    - <span data-ttu-id="c4500-151">Ordine di reso</span><span class="sxs-lookup"><span data-stu-id="c4500-151">Return order</span></span>
    - <span data-ttu-id="c4500-152">Spese varie intestazione</span><span class="sxs-lookup"><span data-stu-id="c4500-152">Header miscellaneous charge</span></span>
    - <span data-ttu-id="c4500-153">Spese varie riga</span><span class="sxs-lookup"><span data-stu-id="c4500-153">Line miscellaneous charge</span></span>

- <span data-ttu-id="c4500-154">Processo di acquisto</span><span class="sxs-lookup"><span data-stu-id="c4500-154">Purchase process</span></span>

    - <span data-ttu-id="c4500-155">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="c4500-155">Purchase order</span></span>
    - <span data-ttu-id="c4500-156">Conferma</span><span class="sxs-lookup"><span data-stu-id="c4500-156">Confirmation</span></span>
    - <span data-ttu-id="c4500-157">Elenco entrate</span><span class="sxs-lookup"><span data-stu-id="c4500-157">Receipts list</span></span>
    - <span data-ttu-id="c4500-158">Entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="c4500-158">Product receipt</span></span>
    - <span data-ttu-id="c4500-159">Fattura acquisto</span><span class="sxs-lookup"><span data-stu-id="c4500-159">Purchase invoice</span></span>
    - <span data-ttu-id="c4500-160">Spese varie intestazione</span><span class="sxs-lookup"><span data-stu-id="c4500-160">Header miscellaneous charge</span></span>
    - <span data-ttu-id="c4500-161">Spese varie riga</span><span class="sxs-lookup"><span data-stu-id="c4500-161">Line miscellaneous charge</span></span>
    - <span data-ttu-id="c4500-162">Nota di accredito</span><span class="sxs-lookup"><span data-stu-id="c4500-162">Credit note</span></span>
    - <span data-ttu-id="c4500-163">Ordine di reso</span><span class="sxs-lookup"><span data-stu-id="c4500-163">Return order</span></span>
    - <span data-ttu-id="c4500-164">Richiesta di acquisto</span><span class="sxs-lookup"><span data-stu-id="c4500-164">Purchase requisition</span></span>
    - <span data-ttu-id="c4500-165">Spese varie riga di richiesta di acquisto</span><span class="sxs-lookup"><span data-stu-id="c4500-165">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="c4500-166">Richiesta di offerta</span><span class="sxs-lookup"><span data-stu-id="c4500-166">Request for quotation</span></span>
    - <span data-ttu-id="c4500-167">Spese varie intestazione richiesta di offerta</span><span class="sxs-lookup"><span data-stu-id="c4500-167">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="c4500-168">Spese varie riga richiesta di offerta</span><span class="sxs-lookup"><span data-stu-id="c4500-168">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="c4500-169">Processo magazzino</span><span class="sxs-lookup"><span data-stu-id="c4500-169">Inventory process</span></span>

    - <span data-ttu-id="c4500-170">Ordine di trasferimento - spedizione</span><span class="sxs-lookup"><span data-stu-id="c4500-170">Transfer order – ship</span></span>
    - <span data-ttu-id="c4500-171">Ordine di trasferimento - ricezione</span><span class="sxs-lookup"><span data-stu-id="c4500-171">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="c4500-172">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="c4500-172">Related resources</span></span>

[<span data-ttu-id="c4500-173">Introduzione al servizio per le imposte</span><span class="sxs-lookup"><span data-stu-id="c4500-173">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="c4500-174">Più numeri di registrazione IVA</span><span class="sxs-lookup"><span data-stu-id="c4500-174">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="c4500-175">Supporto della funzione fiscale per l'ordine di trasferimento</span><span class="sxs-lookup"><span data-stu-id="c4500-175">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="c4500-176">Come creare l'estensione nel servizio per le imposte</span><span class="sxs-lookup"><span data-stu-id="c4500-176">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)
