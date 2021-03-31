---
title: Approvazioni fatture per dispositivi mobili
description: Questo argomento è destinato a fornire un approccio pratico alla progettazione di scenari mobili utilizzando l'approvazione delle fatture fornitore come caso d'uso.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: abf5c2735834537fdc72f2e73fe6a415bd1b67c0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227524"
---
# <a name="mobile-invoice-approvals"></a><span data-ttu-id="d47ff-103">Approvazioni fatture per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="d47ff-103">Mobile invoice approvals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d47ff-104">Le funzionalità mobili consentono agli utenti aziendali di progettare esperienze mobili.</span><span class="sxs-lookup"><span data-stu-id="d47ff-104">Mobile capabilities let a business user design mobile experiences.</span></span> <span data-ttu-id="d47ff-105">Per gli scenari avanzati, la piattaforma anche consente agli sviluppatori di estendere le funzionalità nel modo desiderato.</span><span class="sxs-lookup"><span data-stu-id="d47ff-105">For advanced scenarios, the platform also lets developers extend the capabilities as they desire.</span></span> <span data-ttu-id="d47ff-106">Il modo più efficace di apprendere alcuni dei nuovi concetti sulle funzionalità mobili è di esaminare il processo di progettazione di alcuni scenari.</span><span class="sxs-lookup"><span data-stu-id="d47ff-106">The most effective way to learn some of the new concepts on mobile is to go through the process of designing a few scenarios.</span></span> <span data-ttu-id="d47ff-107">Questo argomento è destinato a fornire un approccio pratico alla progettazione di scenari mobili utilizzando l'approvazione delle fatture fornitore come caso d'uso.</span><span class="sxs-lookup"><span data-stu-id="d47ff-107">This topic is intended to provide a practical approach to designing mobile scenarios by taking vendor invoice approvals for mobile as a use case.</span></span> <span data-ttu-id="d47ff-108">Questo argomento dovrebbe aiutare nella progettazione di altre variazioni degli scenari e può essere applicato anche ad altri scenari non correlati alle fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="d47ff-108">This topic should help you design other variations of the scenarios and can also be applied to other scenarios that aren’t related to vendor invoices.</span></span>

<a name="prerequisites"></a><span data-ttu-id="d47ff-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d47ff-109">Prerequisites</span></span>
-------------

| <span data-ttu-id="d47ff-110">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="d47ff-110">Prerequisite</span></span>                                                                                            | <span data-ttu-id="d47ff-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d47ff-111">Description</span></span>                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d47ff-112">Lettura preventiva del manuale sulle funzionalità mobili</span><span class="sxs-lookup"><span data-stu-id="d47ff-112">Mobile handbook pre-read</span></span>                                                                                |[<span data-ttu-id="d47ff-113">Piattaforma mobile</span><span class="sxs-lookup"><span data-stu-id="d47ff-113">Mobile platform</span></span>](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| <span data-ttu-id="d47ff-114">Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="d47ff-114">Dynamics 365 Finance</span></span>                                                                              | <span data-ttu-id="d47ff-115">Un ambiente con versione 1611 e aggiornamento 3 della piattaforma (novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="d47ff-115">An environment that has version 1611 and Platform update 3 (November 2016)</span></span>                   |
| <span data-ttu-id="d47ff-116">Installare l'aggiornamento rapido KB 3204341.</span><span class="sxs-lookup"><span data-stu-id="d47ff-116">Install hotfix KB 3204341.</span></span>                                                                              | <span data-ttu-id="d47ff-117">Registrazione attività può registrare per errore due comandi di chiusura per le finestre di dialogo a discesa. Incluso nell'aggiornamento 3 della piattaforma (aggiornamento di novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="d47ff-117">Task recorder can erroneously record two Close commands for dropdown dialogs; this is included in Platform update 3 (November 2016 update).</span></span> |
| <span data-ttu-id="d47ff-118">Installare l'aggiornamento rapido KB 3207800.</span><span class="sxs-lookup"><span data-stu-id="d47ff-118">Install hotfix KB 3207800.</span></span>                                                                              | <span data-ttu-id="d47ff-119">Questo aggiornamento rapido consente agli allegati di essere visualizzati sul client mobile. Incluso nell'aggiornamento 3 della piattaforma (aggiornamento di novembre 2016).</span><span class="sxs-lookup"><span data-stu-id="d47ff-119">This hotfix enables attachments to be viewed on the mobile client; this is included in Platform update 3 (November 2016 update).</span></span>           |
| <span data-ttu-id="d47ff-120">Installare l'aggiornamento rapido KB 3208224.</span><span class="sxs-lookup"><span data-stu-id="d47ff-120">Install hotfix KB 3208224.</span></span>                                                                              | <span data-ttu-id="d47ff-121">Codice dell'applicazione mobile di approvazione fatture fornitore. Incluso nella versione 7.0.1 (maggio 2016).</span><span class="sxs-lookup"><span data-stu-id="d47ff-121">Application code for the mobile vendor invoice approval application; this is included in version 7.0.1 (May 2016).</span></span>                          |
| <span data-ttu-id="d47ff-122">Un dispositivo Android o iOS o Windows su cui è installata l'applicazione mobile.</span><span class="sxs-lookup"><span data-stu-id="d47ff-122">An Android or iOS or a Windows device that has the mobile app installed.</span></span> | <span data-ttu-id="d47ff-123">Cercare l'app nell'app store appropriato.</span><span class="sxs-lookup"><span data-stu-id="d47ff-123">Search for the app in the appropriate app store.</span></span>                                                                                                                     |

## <a name="introduction"></a><span data-ttu-id="d47ff-124">Introduzione</span><span class="sxs-lookup"><span data-stu-id="d47ff-124">Introduction</span></span>
<span data-ttu-id="d47ff-125">Le approvazioni mobili per le fatture fornitore richiedono i tre aggiornamenti rapidi indicati nella sezione "Prerequisiti".</span><span class="sxs-lookup"><span data-stu-id="d47ff-125">Mobile approvals for vendor invoices require the three hotfixes that are mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="d47ff-126">Questi aggiornamenti rapidi non forniscono un'area di lavoro per le approvazioni fatture.</span><span class="sxs-lookup"><span data-stu-id="d47ff-126">These hotfixes don’t provide a workspace for the invoice approvals.</span></span> <span data-ttu-id="d47ff-127">Per informazioni su cos'è un'area di lavoro nel contesto delle funzionalità mobili, leggere il relativo manuale indicato nella sezione "Prerequisiti".</span><span class="sxs-lookup"><span data-stu-id="d47ff-127">To learn what a workspace is in the context of mobile, read the mobile handbook that is mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="d47ff-128">L'area di lavoro di approvazione fatture deve essere progettata.</span><span class="sxs-lookup"><span data-stu-id="d47ff-128">The invoice approvals workspace must be designed.</span></span> 

<span data-ttu-id="d47ff-129">Ogni organizzazione orchestra e definisce il proprio processo aziendale per le fatture fornitore in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="d47ff-129">Every organization orchestrates and defines its business process for vendor invoices differently.</span></span> <span data-ttu-id="d47ff-130">Prima di iniziare a progettare un'esperienza mobile per le approvazioni fatture fornitore, valutare i seguenti aspetti del processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="d47ff-130">Before you design a mobile experience for vendor invoice approvals, you should consider the following aspects of the business process.</span></span> <span data-ttu-id="d47ff-131">Il concetto di base è di utilizzare questi punti dati il più possibile per ottimizzare l'esperienza utente sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d47ff-131">The idea is to use these data points as much as possible to optimize the user experience on the device.</span></span>

-   <span data-ttu-id="d47ff-132">Quali campi dall'intestazione fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</span><span class="sxs-lookup"><span data-stu-id="d47ff-132">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="d47ff-133">Quali campi delle righe fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</span><span class="sxs-lookup"><span data-stu-id="d47ff-133">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="d47ff-134">Quante righe fattura sono presenti in una fattura?</span><span class="sxs-lookup"><span data-stu-id="d47ff-134">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="d47ff-135">Applicare la regola 80-20 qui e ottimizzare per l'80%.</span><span class="sxs-lookup"><span data-stu-id="d47ff-135">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span>
-   <span data-ttu-id="d47ff-136">Gli utenti vorranno visualizzare le distribuzioni contabili (codifica della fattura) sul dispositivo mobile nelle revisioni?</span><span class="sxs-lookup"><span data-stu-id="d47ff-136">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span> <span data-ttu-id="d47ff-137">Se la risposta a questa domanda è affermativa, considerare le domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="d47ff-137">If the answer to this question is yes, consider the following questions:</span></span>
    -   <span data-ttu-id="d47ff-138">Quante distribuzioni contabili (prezzo esteso, IVA, spese, suddivisioni e così via) esistono per una riga della fattura?</span><span class="sxs-lookup"><span data-stu-id="d47ff-138">How many accounting distributions (extended price, sales tax, charges, splits, and so on) are there for an invoice line?</span></span> <span data-ttu-id="d47ff-139">Anche in questo caso, applicare la regola 80-20.</span><span class="sxs-lookup"><span data-stu-id="d47ff-139">Again, apply the 80-20 rule.</span></span>
    -   <span data-ttu-id="d47ff-140">Le fatture hanno distribuzioni contabili anche nell'intestazione?</span><span class="sxs-lookup"><span data-stu-id="d47ff-140">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="d47ff-141">In tal caso, queste distribuzioni contabili devono essere disponibili sul dispositivo?</span><span class="sxs-lookup"><span data-stu-id="d47ff-141">If so, should these accounting distributions be available on the device?</span></span>

    > [!NOTE]
    > <span data-ttu-id="d47ff-142">In questo argomento non viene illustrato come modificare le distribuzioni contabili, poiché questa funzionalità non è attualmente supportata per scenari mobili.</span><span class="sxs-lookup"><span data-stu-id="d47ff-142">This topic doesn’t explain how to edit accounting distributions, because this functionality isn’t currently supported for mobile scenarios.</span></span>

-   <span data-ttu-id="d47ff-143">Gli utenti vorranno visualizzare gli allegati della fattura sul dispositivo?</span><span class="sxs-lookup"><span data-stu-id="d47ff-143">Will users want to see attachments for the invoice on the device?</span></span>

<span data-ttu-id="d47ff-144">La progettazione dell'esperienza mobile per le approvazioni fatture varierà in base alle risposte a queste domande.</span><span class="sxs-lookup"><span data-stu-id="d47ff-144">The design of the mobile experience for invoice approvals will differ, depending on the answers to these questions.</span></span> <span data-ttu-id="d47ff-145">L'obiettivo è di ottimizzare l'esperienza utente del processo aziendale sui dispositivi mobili di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d47ff-145">The objective is to optimize the user experience for the business process on mobile in an organization.</span></span> <span data-ttu-id="d47ff-146">Nel resto di questo argomento, esamineremo due variazioni allo scenario basate sulle diverse risposte alle domande precedenti.</span><span class="sxs-lookup"><span data-stu-id="d47ff-146">In the rest of this topic, we will look at two scenario variations that are based on different answers to the preceding questions.</span></span> 

<span data-ttu-id="d47ff-147">In generale quando si lavora con lo strumento di progettazione mobile, assicurarsi di "pubblicare" le modifiche per evitare la perdita degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="d47ff-147">As a general guidance, when working with the mobile designer, make sure to 'publish' the changes to prevent losing the updates.</span></span>

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a><span data-ttu-id="d47ff-148">Progettazione di uno scenario semplice di approvazione fatture per Contoso</span><span class="sxs-lookup"><span data-stu-id="d47ff-148">Designing a simple invoice approval scenario for Contoso</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d47ff-149">Attributo scenario</span><span class="sxs-lookup"><span data-stu-id="d47ff-149">Scenario attribute</span></span></th>
<th><span data-ttu-id="d47ff-150">Risposta</span><span class="sxs-lookup"><span data-stu-id="d47ff-150">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d47ff-151">Quali campi dall'intestazione fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</span><span class="sxs-lookup"><span data-stu-id="d47ff-151">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="d47ff-152">Nome fornitore</span><span class="sxs-lookup"><span data-stu-id="d47ff-152">Vendor name</span></span></li>
<li><span data-ttu-id="d47ff-153">Totale fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-153">Invoice total</span></span></li>
<li><span data-ttu-id="d47ff-154">Conto fatture</span><span class="sxs-lookup"><span data-stu-id="d47ff-154">Invoice account</span></span></li>
<li><span data-ttu-id="d47ff-155">Numero fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-155">Invoice number</span></span></li>
<li><span data-ttu-id="d47ff-156">Data fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-156">Invoice date</span></span></li>
<li><span data-ttu-id="d47ff-157">Descrizione fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-157">Invoice description</span></span></li>
<li><span data-ttu-id="d47ff-158">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="d47ff-158">Due date</span></span></li>
<li><span data-ttu-id="d47ff-159">Valuta della fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-159">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d47ff-160">Quali campi delle righe fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</span><span class="sxs-lookup"><span data-stu-id="d47ff-160">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="d47ff-161">Categoria di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="d47ff-161">Procurement category</span></span></li>
<li><span data-ttu-id="d47ff-162">Quantità</span><span class="sxs-lookup"><span data-stu-id="d47ff-162">Quantity</span></span></li>
<li><span data-ttu-id="d47ff-163">Prezzo unitario</span><span class="sxs-lookup"><span data-stu-id="d47ff-163">Unit price</span></span></li>
<li><span data-ttu-id="d47ff-164">Importo netto riga</span><span class="sxs-lookup"><span data-stu-id="d47ff-164">Line net amount</span></span></li>
<li><span data-ttu-id="d47ff-165">Importo 1099</span><span class="sxs-lookup"><span data-stu-id="d47ff-165">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d47ff-166">Quante righe fattura sono presenti in una fattura?</span><span class="sxs-lookup"><span data-stu-id="d47ff-166">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="d47ff-167">Applicare la regola 80-20 qui e ottimizzare per l'80%.</span><span class="sxs-lookup"><span data-stu-id="d47ff-167">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="d47ff-168">1</span><span class="sxs-lookup"><span data-stu-id="d47ff-168">1</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d47ff-169">Gli utenti vorranno visualizzare le distribuzioni contabili (codifica della fattura) sul dispositivo mobile nelle revisioni?</span><span class="sxs-lookup"><span data-stu-id="d47ff-169">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="d47ff-170">Sì</span><span class="sxs-lookup"><span data-stu-id="d47ff-170">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d47ff-171">Quante distribuzioni contabili (prezzo esteso, IVA, spese e così via) esistono per una riga della fattura?</span><span class="sxs-lookup"><span data-stu-id="d47ff-171">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="d47ff-172">Anche in questo caso, applicare la regola 80-20.</span><span class="sxs-lookup"><span data-stu-id="d47ff-172">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="d47ff-173">Prezzo esteso: 2 IVA: 0 Spese: 0</span><span class="sxs-lookup"><span data-stu-id="d47ff-173">Extended price: 2 Sales tax: 0 Charges: 0</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d47ff-174">Le fatture hanno distribuzioni contabili anche nell'intestazione?</span><span class="sxs-lookup"><span data-stu-id="d47ff-174">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="d47ff-175">In tal caso, queste distribuzioni contabili devono essere disponibili sul dispositivo?</span><span class="sxs-lookup"><span data-stu-id="d47ff-175">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="d47ff-176">Non utilizzato</span><span class="sxs-lookup"><span data-stu-id="d47ff-176">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d47ff-177">Gli utenti vorranno visualizzare gli allegati della fattura sul dispositivo?</span><span class="sxs-lookup"><span data-stu-id="d47ff-177">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="d47ff-178">Sì</span><span class="sxs-lookup"><span data-stu-id="d47ff-178">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a><span data-ttu-id="d47ff-179">Creare l'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="d47ff-179">Create the workspace</span></span>

1.  <span data-ttu-id="d47ff-180">In un browser, accedere all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d47ff-180">In a browser, and sign in to the application.</span></span>
2.  <span data-ttu-id="d47ff-181">Effettuato l'accesso. aggiungere **&mode=mobile** all'URL come mostrato nell'esempio seguente e aggiornare la pagina: https://&lt;urlutente&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span><span class="sxs-lookup"><span data-stu-id="d47ff-181">After you’ve signed in, append **&mode=mobile** to the URL as shown in the following example, and refresh the page: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span></span>
3.  <span data-ttu-id="d47ff-182">Fare clic sul pulsante **Impostazioni** (ingranaggio) in alto a destra nella pagina e fare clic su **App per dispositivi mobili**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-182">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**.</span></span> <span data-ttu-id="d47ff-183">Lo strumento di progettazione app per dispositivo mobili deve apparire come Registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="d47ff-183">The mobile app designer must show up just as Task recorder shows up.</span></span>
4.  <span data-ttu-id="d47ff-184">Fare clic su **Aggiungi** per creare una nuova area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-184">Click **Add** to create a new workspace.</span></span> <span data-ttu-id="d47ff-185">Per questo esempio, chiamare l'area di lavoro **Approvazioni personali**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-185">For this example, name the workspace **My approvals**.</span></span>
5.  <span data-ttu-id="d47ff-186">Immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="d47ff-186">Enter a description.</span></span>
6.  <span data-ttu-id="d47ff-187">Seleziona un colore per l'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-187">Select a workspace color.</span></span> <span data-ttu-id="d47ff-188">IL colore dell'area di lavoro verrà utilizzato per lo stile globale dell'esperienza mobile per l'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-188">The workspace color will be used for the overall style of the mobile experience for this workspace.</span></span>
7.  <span data-ttu-id="d47ff-189">Selezionare un'icona per l'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-189">Select an icon for the workspace.</span></span>
8.  <span data-ttu-id="d47ff-190">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-190">Click **Done**</span></span>
9.  <span data-ttu-id="d47ff-191">Fare clic su **Pubblica area di lavoro** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d47ff-191">Click **Publish workspace** to save the changes</span></span>

### <a name="vendor-invoices-assigned-to-me"></a><span data-ttu-id="d47ff-192">Fatture fornitore assegnate all'utente</span><span class="sxs-lookup"><span data-stu-id="d47ff-192">Vendor invoices assigned to me</span></span>

<span data-ttu-id="d47ff-193">La prima pagina in versione mobile che è consigliabile progettare è l'elenco di fatture assegnate all'utente per la revisione.</span><span class="sxs-lookup"><span data-stu-id="d47ff-193">The first mobile page that you should design is the list of invoices that are assigned to the user for review.</span></span> <span data-ttu-id="d47ff-194">Per progettare questa pagina in versione mobile, utilizzare la pagina **VendMobileInvoiceAssignedToMeListPage**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-194">To design this mobile page, use the **VendMobileInvoiceAssignedToMeListPage** page.</span></span> <span data-ttu-id="d47ff-195">Prima di completare questa procedura, assicurarsi di avere almeno una fattura fornitore assegnata per la revisione e che la riga fattura abbia due distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="d47ff-195">Before you complete this procedure, make sure that at least one vendor invoice is assigned to you for review, and that the invoice line has two distributions.</span></span> <span data-ttu-id="d47ff-196">Questa impostazione soddisfa i requisiti di questo scenario.</span><span class="sxs-lookup"><span data-stu-id="d47ff-196">This setup meets the requirements for this scenario.</span></span>

1.  <span data-ttu-id="d47ff-197">Nell'URL, sostituire il nome della voce di menu con **VendMobileInvoiceAssignedToMeListPage** per aprire la versione mobile della pagina elenco **Fatture fornitore in sospeso assegnate all'utente** nel modulo **Contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-197">In the URL, replace the name of the menu item with **VendMobileInvoiceAssignedToMeListPage** to open the mobile version of the **Pending vendor invoices assigned to me** list page in the **Accounts payable** module.</span></span> <span data-ttu-id="d47ff-198">A seconda del numero delle fatture assegnate all'utente, questa pagina mostrerà tali fatture.</span><span class="sxs-lookup"><span data-stu-id="d47ff-198">Depending on the number of invoices that you have in your system assigned to you, this page will show those invoices.</span></span> <span data-ttu-id="d47ff-199">È possibile usare il filtro a sinistra per trovare una fattura specifica.</span><span class="sxs-lookup"><span data-stu-id="d47ff-199">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="d47ff-200">Tuttavia, non è richiesta una fattura specifica per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="d47ff-200">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="d47ff-201">È solo necessario avere qualche fattura assegnata in modo da poter progettare la pagina in versione mobile.</span><span class="sxs-lookup"><span data-stu-id="d47ff-201">We just require some invoice assigned to you which is going to allow you to design the mobile page.</span></span> <span data-ttu-id="d47ff-202">Le nuove pagine disponibili sono state progettate appositamente per sviluppare scenari mobili per la fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d47ff-202">The new pages that are available have been designed specifically for developing mobile scenarios for vendor invoice.</span></span> <span data-ttu-id="d47ff-203">Di conseguenza, è necessario utilizzare queste pagine.</span><span class="sxs-lookup"><span data-stu-id="d47ff-203">Therefore, you must use these pages.</span></span> <span data-ttu-id="d47ff-204">L'URL deve essere simile al seguente e dopo l'immissione la pagina indicata nella figura deve essere visualizzata: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile</span><span class="sxs-lookup"><span data-stu-id="d47ff-204">The URL should resemble the following URL, and after you enter it, the page that is shown in the illustration must appear: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile</span></span> 

    <span data-ttu-id="d47ff-205">[![Pagina Fatture fornitore in sospeso assegnate all'utente](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span><span class="sxs-lookup"><span data-stu-id="d47ff-205">[![Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span></span>
    
2.  <span data-ttu-id="d47ff-206">Fare clic sul pulsante **Impostazioni** (ingranaggio) in alto a destra nella pagina e fare clic su **App per dispositivi mobili**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-206">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
3.  <span data-ttu-id="d47ff-207">Selezionare l'area di lavoro e fare clic su **Modifica**</span><span class="sxs-lookup"><span data-stu-id="d47ff-207">Select your workspace and click **Edit**</span></span>
4.  <span data-ttu-id="d47ff-208">Fare clic su **Aggiungi pagina** per creare la prima pagina in versione mobile.</span><span class="sxs-lookup"><span data-stu-id="d47ff-208">Click **Add page** to create the first mobile page.</span></span>
5.  <span data-ttu-id="d47ff-209">Immettere un nome, ad esempio **My vendor invoices** e una descrizione, ad esempio **Vendor invoices assigned to me for review**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-209">Enter a name, such as **My vendor invoices**, and a description, such as **Vendor invoices assigned to me for review**.</span></span>
6.  <span data-ttu-id="d47ff-210">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-210">Click **Done**.</span></span>
7.  <span data-ttu-id="d47ff-211">Nello strumento di progettazione mobile, nella scheda **Campi** fare clic su **Seleziona campi**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-211">In the mobile designer, on the **Fields** tab, click **Select fields**.</span></span> <span data-ttu-id="d47ff-212">Le colonne della pagina elenco devono essere simili alla figura seguente.</span><span class="sxs-lookup"><span data-stu-id="d47ff-212">The columns on the list page must resemble the following illustration.</span></span> 

    <span data-ttu-id="d47ff-213">[![Colonne nella pagina Fatture fornitore in sospeso assegnate all'utente](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span><span class="sxs-lookup"><span data-stu-id="d47ff-213">[![Columns on the Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span></span>
    
8.  <span data-ttu-id="d47ff-214">Aggiungere le colonne necessarie dalla pagina elenco che devono essere visualizzate agli utenti nella pagina in versione mobile.</span><span class="sxs-lookup"><span data-stu-id="d47ff-214">Add the required columns from the list page that must be shown to the users in the mobile page.</span></span> <span data-ttu-id="d47ff-215">L'ordine di aggiunta è l'ordine in cui i campi verranno visualizzati all'utente finale.</span><span class="sxs-lookup"><span data-stu-id="d47ff-215">The order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="d47ff-216">Il solo modo per modificare l'ordine dei campi è riselezionarli tutti.</span><span class="sxs-lookup"><span data-stu-id="d47ff-216">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> <span data-ttu-id="d47ff-217">In base ai requisiti di questo scenario, sono necessari i seguenti otto campi.</span><span class="sxs-lookup"><span data-stu-id="d47ff-217">Based on the requirements for this scenario, the following eight fields are required.</span></span> <span data-ttu-id="d47ff-218">Tuttavia, alcuni utenti potrebbero considerare otto campi troppe informazioni da avere su un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="d47ff-218">However, some users might consider eight fields too much information to have on a mobile device.</span></span> <span data-ttu-id="d47ff-219">Di conseguenza, mostreremo solo i campi più importanti nella visualizzazione elenco mobile.</span><span class="sxs-lookup"><span data-stu-id="d47ff-219">Therefore, we will show only the most important fields in the mobile list view.</span></span> <span data-ttu-id="d47ff-220">I campi rimanenti sembreranno appariranno nella visualizzazione dettagli che progetteremo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="d47ff-220">The remaining fields will appear in the details view that we will design later.</span></span> <span data-ttu-id="d47ff-221">Per ora, aggiungeremo i seguenti campi.</span><span class="sxs-lookup"><span data-stu-id="d47ff-221">For now, we will add the following fields.</span></span> <span data-ttu-id="d47ff-222">Fare clic sul segno (**+**) nelle colonne da aggiungere alla pagina mobile.</span><span class="sxs-lookup"><span data-stu-id="d47ff-222">Click the plus sign (**+**) in these columns to add to the mobile page.</span></span>
    - <span data-ttu-id="d47ff-223">Nome fornitore</span><span class="sxs-lookup"><span data-stu-id="d47ff-223">Vendor name</span></span>
    - <span data-ttu-id="d47ff-224">Totale fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-224">Invoice total</span></span>
    - <span data-ttu-id="d47ff-225">Conto fatture</span><span class="sxs-lookup"><span data-stu-id="d47ff-225">Invoice account</span></span>
    - <span data-ttu-id="d47ff-226">Numero fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-226">Invoice number</span></span>
    - <span data-ttu-id="d47ff-227">Data fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-227">Invoice date</span></span>

    <span data-ttu-id="d47ff-228">Dopo che i campi vengono aggiunti, la pagina mobile deve somigliare alla figura seguente.</span><span class="sxs-lookup"><span data-stu-id="d47ff-228">After the fields are added, the mobile page must resemble the following illustration.</span></span> 
    
    <span data-ttu-id="d47ff-229">[![Pagina dopo l'aggiunta dei campi](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span><span class="sxs-lookup"><span data-stu-id="d47ff-229">[![Page after fields are added](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span></span>

9.  <span data-ttu-id="d47ff-230">È inoltre necessario aggiungere le seguenti colonne ora, in modo da abilitare le azioni del flusso di lavoro successivamente.</span><span class="sxs-lookup"><span data-stu-id="d47ff-230">You must also add the following columns now, so that we can enable workflow actions later.</span></span>
    - <span data-ttu-id="d47ff-231">Mostra attività completare</span><span class="sxs-lookup"><span data-stu-id="d47ff-231">Show complete task</span></span>
    - <span data-ttu-id="d47ff-232">Mostra attività delegare</span><span class="sxs-lookup"><span data-stu-id="d47ff-232">Show delegate task</span></span>
    - <span data-ttu-id="d47ff-233">Mostra attività richiamare</span><span class="sxs-lookup"><span data-stu-id="d47ff-233">Show recall task</span></span>
    - <span data-ttu-id="d47ff-234">Mostra attività rifiutare</span><span class="sxs-lookup"><span data-stu-id="d47ff-234">Show reject task</span></span>
    - <span data-ttu-id="d47ff-235">Mostra attività richiedere completamento</span><span class="sxs-lookup"><span data-stu-id="d47ff-235">Show request completion task</span></span>
    - <span data-ttu-id="d47ff-236">Mostra attività inviare nuovamente</span><span class="sxs-lookup"><span data-stu-id="d47ff-236">Show resubmit task</span></span>

10. <span data-ttu-id="d47ff-237">Fare clic su **Fine** per uscire dalla modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="d47ff-237">Click **Done** to exit edit mode.</span></span>
11. <span data-ttu-id="d47ff-238">Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="d47ff-238">Click **Back** and then **Done** to exit the workspace</span></span>
12. <span data-ttu-id="d47ff-239">Fare clic su **Pubblica area di lavoro** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-239">Click **Publish workspace** to save your work.</span></span>
13. <span data-ttu-id="d47ff-240">Abilitare **Visualizza totale fatture su elenco fatture fornitore in sospeso** nel modulo dei parametri contabilità fornitori in **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-240">Enable **Display invoice total on pending vendor invoices list** in accounts payable parameters form under **Invoice**.</span></span> <span data-ttu-id="d47ff-241">Tenere presente che solo abilitando questo parametro, i totali fattura verranno calcolati e visualizzati nella pagina elenco delle fatture fornitore in sospeso.</span><span class="sxs-lookup"><span data-stu-id="d47ff-241">Note that, only by enabling this parameter, invoice totals will be calculated to be displayed on the pending vendor invoices list page.</span></span> <span data-ttu-id="d47ff-242">Si tratta di una nuova funzionalità nell'ambito dell'aggiornamento rapido 3208224.</span><span class="sxs-lookup"><span data-stu-id="d47ff-242">This is a new capability as part of the pre-requisite hot fix 3208224.</span></span>

### <a name="vendor-invoice-details"></a><span data-ttu-id="d47ff-243">Dettagli fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="d47ff-243">Vendor invoice details</span></span>

<span data-ttu-id="d47ff-244">Per progettare la pagina dei dettagli fattura per l'ambiente mobile, utilizzare la pagina **VendMobileInvoiceHeaderDetails**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-244">To design the invoice details page for mobile, use the **VendMobileInvoiceHeaderDetails** page.</span></span> <span data-ttu-id="d47ff-245">Tenere presente che, a seconda del numero di fatture nel sistema, la pagina mostra la fattura più vecchia (la fattura creata per prima).</span><span class="sxs-lookup"><span data-stu-id="d47ff-245">Note that, depending on the number of invoices that you have in your system, this page shows the oldest invoice (the invoice that was created first).</span></span> <span data-ttu-id="d47ff-246">È possibile usare il filtro a sinistra per trovare una fattura specifica.</span><span class="sxs-lookup"><span data-stu-id="d47ff-246">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="d47ff-247">Tuttavia, non è richiesta una fattura specifica per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="d47ff-247">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="d47ff-248">Sono neecssari solo alcuni dati della fattura per progettare la pagina in versione mobile.</span><span class="sxs-lookup"><span data-stu-id="d47ff-248">We just require some invoice data so that we can design the mobile page.</span></span> 

<span data-ttu-id="d47ff-249">[![Pagina Flusso di lavoro](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span><span class="sxs-lookup"><span data-stu-id="d47ff-249">[![Workflow page](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span></span>

1. <span data-ttu-id="d47ff-250">Nell'URL, sostituire il nome della voce di menu con **VendMobileInvoiceHeaderDetails** per aprire il modulo</span><span class="sxs-lookup"><span data-stu-id="d47ff-250">In the URL, replace the name of the menu item with **VendMobileInvoiceHeaderDetails** to open the form</span></span>

2. <span data-ttu-id="d47ff-251">Aprire lo strumento di progettazione mobile dal pulsante **Impostazioni** (ingranaggio).</span><span class="sxs-lookup"><span data-stu-id="d47ff-251">Open the mobile designer from the **Settings** (gear) button.</span></span>

3. <span data-ttu-id="d47ff-252">Fare clic sul pulsante **Modifica** per avviare la modalità di modifica nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-252">Click the **Edit** button to start edit mode in the workspace.</span></span>

4. <span data-ttu-id="d47ff-253">Selezionare la pagina **My vendor invoices** creata in precedenza, quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-253">Select the **My vendor invoices** page that you created earlier, and then click **Edit**.</span></span>

5. <span data-ttu-id="d47ff-254">Nella scheda **Campi** fare clic sull'intestazione di colonna **Griglia**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-254">On the **Fields** tab, click the **Grid** column heading.</span></span>

6. <span data-ttu-id="d47ff-255">Fare clic su **Proprietà &gt; Aggiungi pagina**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-255">Click **Properties &gt; Add page**.</span></span> <span data-ttu-id="d47ff-256">**Nota:** Quando si fa clic su l'intestazione **Griglia** e si aggiunge una pagina, la relazione con la pagina dei dettagli è impostata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d47ff-256">**Note:** When you click the **Grid** heading and add a page, the relationship with the details page is established automatically.</span></span>

7. <span data-ttu-id="d47ff-257">Immettere un titolo della pagina, ad esempio **Invoice details** e una descrizione, ad esempio **View invoice header and line details**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-257">Enter a page title, such as **Invoice details**, and a description, such as **View invoice header and line details**.</span></span>

8. <span data-ttu-id="d47ff-258">Fare clic su **Seleziona campi**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-258">Click **Select fields**.</span></span> <span data-ttu-id="d47ff-259">Notare che l'ordine di aggiunta è l'ordine in cui i campi verranno visualizzati all'utente finale.</span><span class="sxs-lookup"><span data-stu-id="d47ff-259">Note that, the order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="d47ff-260">Il solo modo per modificare l'ordine dei campi è riselezionarli tutti.</span><span class="sxs-lookup"><span data-stu-id="d47ff-260">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> 

9. <span data-ttu-id="d47ff-261">Aggiungere i campi seguenti dall'intestazione in base ai requisiti di questo scenario:</span><span class="sxs-lookup"><span data-stu-id="d47ff-261">Add the following fields from the header, based on the requirements for this scenario:</span></span>
   - <span data-ttu-id="d47ff-262">Nome fornitore</span><span class="sxs-lookup"><span data-stu-id="d47ff-262">Vendor name</span></span>
   - <span data-ttu-id="d47ff-263">Totale fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-263">Invoice total</span></span>
   - <span data-ttu-id="d47ff-264">Conto fatture</span><span class="sxs-lookup"><span data-stu-id="d47ff-264">Invoice account</span></span>
   - <span data-ttu-id="d47ff-265">Numero fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-265">Invoice number</span></span>
   - <span data-ttu-id="d47ff-266">Data fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-266">Invoice date</span></span>
   - <span data-ttu-id="d47ff-267">Descrizione fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-267">Invoice description</span></span>
   - <span data-ttu-id="d47ff-268">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="d47ff-268">Due date</span></span>
   - <span data-ttu-id="d47ff-269">Valuta della fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-269">Invoice currency</span></span>

10. <span data-ttu-id="d47ff-270">Aggiungere i seguenti campi dalla griglia di righe nella pagina:</span><span class="sxs-lookup"><span data-stu-id="d47ff-270">Add the following fields from the lines grid on the page:</span></span>
    - <span data-ttu-id="d47ff-271">Categoria di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="d47ff-271">Procurement category</span></span>
    - <span data-ttu-id="d47ff-272">Quantità</span><span class="sxs-lookup"><span data-stu-id="d47ff-272">Quantity</span></span>
    - <span data-ttu-id="d47ff-273">Prezzo unitario</span><span class="sxs-lookup"><span data-stu-id="d47ff-273">Unit price</span></span>
    - <span data-ttu-id="d47ff-274">Importo netto riga</span><span class="sxs-lookup"><span data-stu-id="d47ff-274">Line net amount</span></span>
    - <span data-ttu-id="d47ff-275">Importo 1099</span><span class="sxs-lookup"><span data-stu-id="d47ff-275">1099 amount</span></span>

11. <span data-ttu-id="d47ff-276">Dopo che tutti i campi dai due passaggi precedenti sono stati aggiunti, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-276">After all the fields from the previous two steps have been added, click **Done**.</span></span> <span data-ttu-id="d47ff-277">La pagina deve essere simili alla figura seguente.</span><span class="sxs-lookup"><span data-stu-id="d47ff-277">The page must resemble the following illustration.</span></span>
    
    <span data-ttu-id="d47ff-278">[![Pagina dopo l'aggiunta dei campi](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span><span class="sxs-lookup"><span data-stu-id="d47ff-278">[![Page after fields are added](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span></span>

12. <span data-ttu-id="d47ff-279">Fare clic su **Fine** per uscire dalla modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="d47ff-279">Click **Done** to exit edit mode.</span></span>

13. <span data-ttu-id="d47ff-280">Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="d47ff-280">Click **Back** and then **Done** to exit the workspace</span></span>

14. <span data-ttu-id="d47ff-281">Fare clic su **Pubblica area di lavoro** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-281">Click **Publish workspace** to save your work</span></span>

### <a name="workflow-actions"></a><span data-ttu-id="d47ff-282">Azioni flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d47ff-282">Workflow actions</span></span>

<span data-ttu-id="d47ff-283">Per aggiungere le azioni del flusso di lavoro, utilizzare la pagina **VendMobileInvoiceHeaderDetails**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-283">To add workflow actions, use the **VendMobileInvoiceHeaderDetails** page.</span></span> <span data-ttu-id="d47ff-284">Per visualizzare questa pagina, sostituire il nome della voce di menu nell'URL, come fatto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d47ff-284">To open this page, replace the name of the menu item in the URL, as you did earlier.</span></span> <span data-ttu-id="d47ff-285">Quindi aprire lo strumento di progettazione mobile dal pulsante **Impostazioni** (ingranaggio).</span><span class="sxs-lookup"><span data-stu-id="d47ff-285">Then open the mobile designer from the **Settings** (gear) button.</span></span> <span data-ttu-id="d47ff-286">Seguire questi passaggi per aggiungere le azioni del flusso di lavoro nella pagina dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="d47ff-286">Follow these steps to add workflow actions on the details page.</span></span> <span data-ttu-id="d47ff-287">È obbligatorio avere fatture assegnate che si trovato in uno stato tale da rendere disponibili le azioni del flusso di lavoro per l'utente per la progettazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="d47ff-287">You must have invoices assigned to you that are in the appropriate state to make the workflow actions available to you that you are going to design for.</span></span>

#### <a name="record-workflow-actions"></a><span data-ttu-id="d47ff-288">Registrare azioni del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d47ff-288">Record workflow actions</span></span>
1.  <span data-ttu-id="d47ff-289">Fare clic sul pulsante **Modifica** per avviare la modalità di modifica nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-289">Click the **Edit** button to start edit mode in the workspace.</span></span>
2.  <span data-ttu-id="d47ff-290">Selezionare la pagina **Invoice details** creata in precedenza quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-290">Select the **Invoice details** page that you created earlier, and then click **Edit**.</span></span>
3.  <span data-ttu-id="d47ff-291">Nella scheda **Azioni** fare clic su **Aggiungi azione**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-291">On the **Actions** tab, click **Add action**.</span></span>
4.  <span data-ttu-id="d47ff-292">Immettere un titolo dell'azione, come **Approve** e una descrizione, ad esempio **Approve invoice**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-292">Enter an action title, such as **Approve**, and a description, such as **Approve invoice**.</span></span> <span data-ttu-id="d47ff-293">Si noti che il titolo di azione immesso in questo campo diventa il nome dell'azione che verrà visualizzata all'utente nell'app per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="d47ff-293">Note that the action title that you enter here becomes the name of the action that is shown to the user in the mobile app.</span></span>
5.  <span data-ttu-id="d47ff-294">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-294">Click **Done**.</span></span>
6.  <span data-ttu-id="d47ff-295">Fare clic su **Seleziona campi**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-295">Click **Select fields**.</span></span>
7.  <span data-ttu-id="d47ff-296">Procedere lungo il processo del flusso di lavoro nella pagina **VendMobileInvoiceHeaderDetails** e completare l'azione che si è voluta registrare.</span><span class="sxs-lookup"><span data-stu-id="d47ff-296">Go through the workflow process on the **VendMobileInvoiceHeaderDetails** page, and complete the action that you wanted to record.</span></span> <span data-ttu-id="d47ff-297">Assicurarsi di immettere commenti del flusso di lavoro durante il processo, in modo che un campo di commenti viene anche incluso nell'esperienza mobile.</span><span class="sxs-lookup"><span data-stu-id="d47ff-297">Make sure that you enter workflow comments during this process, so that a comments field is also included in the mobile experience.</span></span>
8.  <span data-ttu-id="d47ff-298">Dopo che l'azione del flusso di lavoro viene eseguita, fare clic su **Fine** per completare l'attività Seleziona campi.</span><span class="sxs-lookup"><span data-stu-id="d47ff-298">After the workflow action is run, click **Done** to complete the Select fields task.</span></span>
9.  <span data-ttu-id="d47ff-299">Fare clic su **Fine** per uscire dalla modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="d47ff-299">Click **Done** to exit edit mode.</span></span>
10. <span data-ttu-id="d47ff-300">Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="d47ff-300">Click **Back** and then **Done** to exit the workspace</span></span>
11. <span data-ttu-id="d47ff-301">Fare clic su **Pubblica area di lavoro** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-301">Click **Publish workspace** to save your work</span></span>
12. <span data-ttu-id="d47ff-302">Ripetere i passaggi precedenti per registrare tutte le azioni necessarie del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-302">Repeat the previous steps to record all the required workflow actions.</span></span> 

#### <a name="create-a-js-file"></a><span data-ttu-id="d47ff-303">Creare un file .js</span><span class="sxs-lookup"><span data-stu-id="d47ff-303">Create a .js file</span></span>
1. <span data-ttu-id="d47ff-304">Aprire il Blocco note o Microsoft Visual Studio e incollare il seguente codice.</span><span class="sxs-lookup"><span data-stu-id="d47ff-304">Open Notepad or Microsoft Visual Studio, and paste the following code.</span></span> <span data-ttu-id="d47ff-305">Salvare il file come file .js.</span><span class="sxs-lookup"><span data-stu-id="d47ff-305">Save the file as a .js file.</span></span> <span data-ttu-id="d47ff-306">Il codice effettua quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d47ff-306">This code does the following:</span></span>
    - <span data-ttu-id="d47ff-307">Nasconde le colonne extra correlate ai flussi di lavoro che abbiamo aggiunto in precedenza nella pagina elenco in versione mobile.</span><span class="sxs-lookup"><span data-stu-id="d47ff-307">It hides the extra workflow-related columns that we added earlier on the mobile list page.</span></span> <span data-ttu-id="d47ff-308">Abbiamo aggiunto le colonne in modo che l'app abbia quelle informazioni nel contesto e possa eseguire il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="d47ff-308">We added these columns so that the app has that information in context and can do the next step.</span></span>
    - <span data-ttu-id="d47ff-309">In base al passaggio del flusso di lavoro attivo, viene applicata la logica per visualizzare solo queste azioni.</span><span class="sxs-lookup"><span data-stu-id="d47ff-309">Based on the workflow step that is active, it applies logic to show only those actions.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d47ff-310">Il nome delle pagine e altri controlli nel codice devono essere gli stessi dell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-310">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }
    ```

2.  <span data-ttu-id="d47ff-311">Caricare il file del codice nell'area di lavoro selezionando la scheda **Logica**</span><span class="sxs-lookup"><span data-stu-id="d47ff-311">Upload the code file to the workspace by selecting the **Logic** tab</span></span>
3.  <span data-ttu-id="d47ff-312">Fare clic su **Fine** per uscire dalla modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="d47ff-312">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="d47ff-313">Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="d47ff-313">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="d47ff-314">Fare clic su **Pubblica area di lavoro** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-314">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-attachments"></a><span data-ttu-id="d47ff-315">Allegati della fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="d47ff-315">Vendor invoice attachments</span></span>

1. <span data-ttu-id="d47ff-316">Fare clic sul pulsante **Impostazioni** (ingranaggio) in alto a destra nella pagina e fare clic su **App per dispositivi mobili**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-316">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>

2. <span data-ttu-id="d47ff-317">Fare clic sul pulsante **Modifica** per avviare la modalità di modifica nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-317">Click the **Edit** button to start edit mode in the workspace.</span></span>

3. <span data-ttu-id="d47ff-318">Selezionare la pagina <strong>Invoice detailsv **creata in precedenza, quindi fare clic su** Modifica</strong>.</span><span class="sxs-lookup"><span data-stu-id="d47ff-318">Select the <strong>Invoice details \*\*page that you created earlier, and then click \*\*Edit</strong>.</span></span>

4. <span data-ttu-id="d47ff-319">Impostare l'opzione **Gestione documenti** su **Sì** come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d47ff-319">Set the **Document management** option to **Yes** as shown below.</span></span> <span data-ttu-id="d47ff-320">**Nota:** Se non sono presenti esigenze di visualizzare gli allegati sul dispositivo mobile, è possibile lasciare questa opzione impostata su **No**, che è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d47ff-320">**Note:** If there are no requirements to show attachments on the mobile device, you can leave this option set to **No**, which is the default setting.</span></span>
   
   ![Gestione documenti](./media/docmanagement-216x300.png)

5. <span data-ttu-id="d47ff-322">Fare clic su **Fine** per uscire dalla modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="d47ff-322">Click **Done** to exit edit mode.</span></span>

6. <span data-ttu-id="d47ff-323">Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="d47ff-323">Click **Back** and then **Done** to exit the workspace</span></span>

7. <span data-ttu-id="d47ff-324">Fare clic su **Pubblica area di lavoro** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-324">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-line-distributions"></a><span data-ttu-id="d47ff-325">Distribuzioni a livello di riga fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="d47ff-325">Vendor invoice line distributions</span></span>

<span data-ttu-id="d47ff-326">I requisiti di questo scenario confermano che ci saranno solo distribuzioni a livello di riga e che una fattura conterrà sempre una sola riga.</span><span class="sxs-lookup"><span data-stu-id="d47ff-326">The requirements for this scenario confirm that there will be only line-level distributions, and that an invoice will always have only one line.</span></span> <span data-ttu-id="d47ff-327">Poiché questo scenario è semplice, anche l'esperienza utente sul dispositivo mobile deve essere abbastanza semplice da evitare che l'utente debba eseguire il drill-down di più livelli per visualizzare le distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="d47ff-327">Because this scenario is simple, the user experience on the mobile device must also be simple enough that the user doesn’t have to drill down several levels to view the distributions.</span></span> <span data-ttu-id="d47ff-328">Le fatture fornitore includono l'opzione di mostrare tutte le distribuzioni dall'intestazione della fattura.</span><span class="sxs-lookup"><span data-stu-id="d47ff-328">Vendor invoices include the option of showing all distributions from the invoice header.</span></span> <span data-ttu-id="d47ff-329">Questa esperienza è quello che serve per lo scenario mobile.</span><span class="sxs-lookup"><span data-stu-id="d47ff-329">This experience is what we need for the mobile scenario.</span></span> <span data-ttu-id="d47ff-330">Di conseguenza, useremo la pagina **VendMobileInvoiceAllDistributionTree** per progettare questa parte dello scenario mobile.</span><span class="sxs-lookup"><span data-stu-id="d47ff-330">Therefore, we will use the **VendMobileInvoiceAllDistributionTree** page to design this part of the mobile scenario.</span></span> 

> [!NOTE] 
> <span data-ttu-id="d47ff-331">Conoscere i requisiti aiuta a decidere quale pagina specifica utilizzare come esattamente ottimizzare l'esperienza mobile per l'utente nella progettazione dello scenario.</span><span class="sxs-lookup"><span data-stu-id="d47ff-331">Knowing the requirements helps us decide which specific page to use and how exactly to optimize the mobile experience for the user when we design the scenario.</span></span> <span data-ttu-id="d47ff-332">Nel secondo scenario, useremo una pagina diversa per visualizzare le distribuzioni, poiché i requisiti di quello scenario sono diversi.</span><span class="sxs-lookup"><span data-stu-id="d47ff-332">In the second scenario, we will use a different page to show the distributions, because the requirements for that scenario differ.</span></span>

1.  <span data-ttu-id="d47ff-333">Nell'URL, sostituire il nome della voce di menu, come fatto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d47ff-333">In the URL, replace the name of the menu item, as you did before.</span></span> <span data-ttu-id="d47ff-334">Verrà visualizzata una che deve essere simile alla figura seguente.</span><span class="sxs-lookup"><span data-stu-id="d47ff-334">The page that appears should resemble the following illustration.</span></span>

    <span data-ttu-id="d47ff-335">[![Pagina Tutte le distribuzioni](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span><span class="sxs-lookup"><span data-stu-id="d47ff-335">[![All distributions page](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span></span>

2.  <span data-ttu-id="d47ff-336">Aprire lo strumento di progettazione mobile dal pulsante **Impostazioni** (ingranaggio).</span><span class="sxs-lookup"><span data-stu-id="d47ff-336">Open the mobile designer from the **Settings** (gear) button.</span></span>

3.  <span data-ttu-id="d47ff-337">Fare clic sul pulsante **Modifica** per avviare la modalità di modifica nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-337">Click the **Edit** button to start edit mode in the workspace.</span></span> <span data-ttu-id="d47ff-338">**Nota:**  Vedrete che due pagine sono state create automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d47ff-338">**Note:** You will see that two new pages were created automatically.</span></span> <span data-ttu-id="d47ff-339">Il sistema crea queste pagine, poiché è stata abilitata la gestione dei documenti nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="d47ff-339">The system creates these pages, because you turned on document management in the previous section.</span></span> <span data-ttu-id="d47ff-340">È possibile ignorare tali nuove pagine.</span><span class="sxs-lookup"><span data-stu-id="d47ff-340">You can ignore these new pages.</span></span>

4.  <span data-ttu-id="d47ff-341">Fare clic su **Aggiungi pagina**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-341">Click **Add page**.</span></span>

5.  <span data-ttu-id="d47ff-342">Immettere un titolo della pagina, ad esempio **Visualizza contabilità** e una descrizione, ad esempio **View accounting for the invoice**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-342">Enter a page title, such as **View accounting**, and a description, such as **View accounting for the invoice**.</span></span>

6.  <span data-ttu-id="d47ff-343">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-343">Click **Done**.</span></span>

7.  <span data-ttu-id="d47ff-344">Nella scheda **Campi** fare clic su **Seleziona campi**, selezionare i campi seguenti dalla pagina delle sitribuzioni e fare clic su **Fine**:</span><span class="sxs-lookup"><span data-stu-id="d47ff-344">On the **Fields** tab, click **Select fields**, select the following fields from the distributions page, and then click **Done**:</span></span>
    1.  <span data-ttu-id="d47ff-345">Importo</span><span class="sxs-lookup"><span data-stu-id="d47ff-345">Amount</span></span>
    2.  <span data-ttu-id="d47ff-346">Valuta</span><span class="sxs-lookup"><span data-stu-id="d47ff-346">Currency</span></span>
    3.  <span data-ttu-id="d47ff-347">Conto CoGe</span><span class="sxs-lookup"><span data-stu-id="d47ff-347">Ledger account</span></span>

    > [!NOTE] 
    > <span data-ttu-id="d47ff-348">Non abbiamo selezionato la colonna **Descrizione** nella griglia di distribuzioni, poiché i requisiti di questo scenario hanno confermato che il prezzo esteso è l'unico importo per cui ci saranno distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="d47ff-348">We didn’t select the **Description** column from the distributions grid, because the requirements for this scenario confirmed that the extended price is the only amount that there will be distributions for.</span></span> <span data-ttu-id="d47ff-349">Pertanto, l'utente non avrà bisogno di un altro campo per determinare il tipo di importo per cui è la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d47ff-349">Therefore, the user won’t require another field to determine the amount type that the distribution is for.</span></span> <span data-ttu-id="d47ff-350">Tuttavia, nello scenario successivo, queste informazioni **verranno** utilizzate, poiché i requisiti di quello scenario specificano che altri tipi di importo hanno distribuzioni, ad esempio IVA.</span><span class="sxs-lookup"><span data-stu-id="d47ff-350">However, in the next scenario, we **will** use this information, because the requirements for that scenario specify that other amount types have distributions (for example, sales tax).</span></span>

8.  <span data-ttu-id="d47ff-351">Fare clic su **Fine** per uscire dalla modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="d47ff-351">Click **Done** to exit edit mode.</span></span>

9.  <span data-ttu-id="d47ff-352">Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="d47ff-352">Click **Back** and then **Done** to exit the workspace</span></span>

10. <span data-ttu-id="d47ff-353">Fare clic su **Pubblica area di lavoro** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-353">Click **Publish workspace** to save your work</span></span>

#### <a name="adding-navigation-to-view-accounting-page"></a><span data-ttu-id="d47ff-354">Aggiunto lo spostamento alla pagina "Visualizza contabilità"</span><span class="sxs-lookup"><span data-stu-id="d47ff-354">Adding navigation to "View accounting" page</span></span>

<span data-ttu-id="d47ff-355">La pagina in versione mobile **Visualizza contabilità** non è attualmente collegata a nessuna delle pagine mobili disponibili progettate fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="d47ff-355">The **View accounting** mobile page isn’t currently linked to any of the mobile pages that we have designed so far.</span></span> <span data-ttu-id="d47ff-356">Poiché l'utente deve poter accedere alla pagina **Visualizza contabilità** dalla pagina **Dettagli fattura** sul dispositivo mobile, dobbiamo specificare lo spostamento dalla pagina **Dettagli fattura** alla pagina **Visualizza contabilità** .</span><span class="sxs-lookup"><span data-stu-id="d47ff-356">Because the user should be able to navigate to the **View accounting** page from the **Invoice details** page on the mobile device, we must provide navigation from the **Invoice details** page to the **View accounting** page.</span></span> <span data-ttu-id="d47ff-357">Stabiliamo questo spostamento utilizzando la logica aggiuntiva tramite JavaScript.</span><span class="sxs-lookup"><span data-stu-id="d47ff-357">We establish this navigation by using additional logic via JavaScript.</span></span>

1.  <span data-ttu-id="d47ff-358">Apre il file .js creato in precedenza e aggiungere le righe che vengono evidenziate nel codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d47ff-358">Open the .js file that you created earlier, and add the lines that are highlighted in the following code.</span></span> <span data-ttu-id="d47ff-359">Questo codice fa due cose:</span><span class="sxs-lookup"><span data-stu-id="d47ff-359">This code does two things:</span></span>
    1.  <span data-ttu-id="d47ff-360">Aiuta a garantire che gli utenti non possono accedere direttamente dall'area di lavoro alla pagina **Visualizza contabilità**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-360">It helps guarantee that users can’t navigate directly from the workspace to the **View accounting** page.</span></span>
    2.  <span data-ttu-id="d47ff-361">Stabilisce un controllo di spostamento dalla pagina **Invoice details** alla pagina **View accounting**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-361">It establishes a navigation control from the **Invoice details** page to the **View accounting** page.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="d47ff-362">Il nome delle pagine e altri controlli nel codice devono essere gli stessi dell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-362">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }
    ```
    
2.  <span data-ttu-id="d47ff-363">Caricare il file del codice nell'area di lavoro selezionando la scheda **Logica** per sovrascrivere il codice precedente</span><span class="sxs-lookup"><span data-stu-id="d47ff-363">Upload the code file to the workspace by selecting the **Logic** tab to overwrite the previous code</span></span>
3.  <span data-ttu-id="d47ff-364">Fare clic su **Fine** per uscire dalla modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="d47ff-364">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="d47ff-365">Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="d47ff-365">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="d47ff-366">Fare clic su **Pubblica area di lavoro** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-366">Click **Publish workspace** to save your work</span></span>

### <a name="validation"></a><span data-ttu-id="d47ff-367">Convalida</span><span class="sxs-lookup"><span data-stu-id="d47ff-367">Validation</span></span>

<span data-ttu-id="d47ff-368">Dal dispositivo mobile, aprire l'app e connettersi all'istanza.</span><span class="sxs-lookup"><span data-stu-id="d47ff-368">From your mobile device, open the app, and connect to your instance.</span></span> <span data-ttu-id="d47ff-369">Verificare di accedere alla società in cui le fatture fornitore sono assegnate a se stessi per la revisione.</span><span class="sxs-lookup"><span data-stu-id="d47ff-369">Make sure that you sign in to the company where vendor invoices are assigned to you for review.</span></span> <span data-ttu-id="d47ff-370">Dovrebbe esssere possibile eseguire le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="d47ff-370">You should be able to perform the following actions:</span></span>

-   <span data-ttu-id="d47ff-371">Vedere l'area di lavoro **My approvals**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-371">See the **My approvals** workspace.</span></span>
-   <span data-ttu-id="d47ff-372">Analizzare l'area di lavoro **My approvals** e vedere la pagina **My vendor invoices**.</span><span class="sxs-lookup"><span data-stu-id="d47ff-372">Drill into the **My approvals** workspace and see the **My vendor invoices** page.</span></span>
-   <span data-ttu-id="d47ff-373">Analizzare la pagina **My vendor invoices** e visualizzare l'elenco delle fatture assegnate all'utente.</span><span class="sxs-lookup"><span data-stu-id="d47ff-373">Drill into the **My vendor invoices** page and see the list of invoices that are assigned to you.</span></span>
-   <span data-ttu-id="d47ff-374">Analizzare una delle fatture e visualizzare i dettagli dell'intestazione della fattura e delle righe.</span><span class="sxs-lookup"><span data-stu-id="d47ff-374">Drill into one of the invoices, and see the invoice header details and line details.</span></span>
-   <span data-ttu-id="d47ff-375">Nella pagina dei dettagli, vedere un collegamento agli allegati e utilizzare questo collegamento per spostarsi all'elenco degli allegati e visualizzare gli allegati.</span><span class="sxs-lookup"><span data-stu-id="d47ff-375">On the details page, see a link to attachments, and use this link to navigate to the attachments list and view the attachments.</span></span>
-   <span data-ttu-id="d47ff-376">Nella pagina dei dettagli, vedere un collegamento alla pagina **Visualizza contabilità** e utilizzare questo collegamento per spostarsi alla pagina delle distribuzioni e visualizzare le distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="d47ff-376">On the details page, see a link to the **View accounting** page, and use this link to navigate to the distributions page and view the distributions.</span></span>
-   <span data-ttu-id="d47ff-377">Nella pagina dei dettagli, fare clic sul menu **Azioni** nella parte inferiore ed eseguire le azioni del flusso di lavoro applicabili al passaggio del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d47ff-377">On the details page, click the **Actions** menu at the bottom, and perform workflow actions that are applicable to the workflow step.</span></span>

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a><span data-ttu-id="d47ff-378">Progettazione di uno scenario complesso di approvazione fatture per Fabrikam</span><span class="sxs-lookup"><span data-stu-id="d47ff-378">Designing a complex invoice approval scenario for Fabrikam</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d47ff-379">Attributo scenario</span><span class="sxs-lookup"><span data-stu-id="d47ff-379">Scenario attribute</span></span></th>
<th><span data-ttu-id="d47ff-380">Risposta</span><span class="sxs-lookup"><span data-stu-id="d47ff-380">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d47ff-381">Quali campi dall'intestazione fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</span><span class="sxs-lookup"><span data-stu-id="d47ff-381">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="d47ff-382">Nome fornitore</span><span class="sxs-lookup"><span data-stu-id="d47ff-382">Vendor name</span></span></li>
<li><span data-ttu-id="d47ff-383">Importo fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-383">Invoice amount</span></span></li>
<li><span data-ttu-id="d47ff-384">Conto fatture</span><span class="sxs-lookup"><span data-stu-id="d47ff-384">Invoice account</span></span></li>
<li><span data-ttu-id="d47ff-385">Numero fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-385">Invoice number</span></span></li>
<li><span data-ttu-id="d47ff-386">Data fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-386">Invoice date</span></span></li>
<li><span data-ttu-id="d47ff-387">Descrizione fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-387">Invoice description</span></span></li>
<li><span data-ttu-id="d47ff-388">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="d47ff-388">Due date</span></span></li>
<li><span data-ttu-id="d47ff-389">Valuta della fattura</span><span class="sxs-lookup"><span data-stu-id="d47ff-389">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d47ff-390">Quali campi delle righe fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</span><span class="sxs-lookup"><span data-stu-id="d47ff-390">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="d47ff-391">Categoria di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="d47ff-391">Procurement category</span></span></li>
<li><span data-ttu-id="d47ff-392">Quantità</span><span class="sxs-lookup"><span data-stu-id="d47ff-392">Quantity</span></span></li>
<li><span data-ttu-id="d47ff-393">Prezzo unitario</span><span class="sxs-lookup"><span data-stu-id="d47ff-393">Unit price</span></span></li>
<li><span data-ttu-id="d47ff-394">Importo netto riga</span><span class="sxs-lookup"><span data-stu-id="d47ff-394">Line net amount</span></span></li>
<li><span data-ttu-id="d47ff-395">Importo 1099</span><span class="sxs-lookup"><span data-stu-id="d47ff-395">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d47ff-396">Quante righe fattura sono presenti in una fattura?</span><span class="sxs-lookup"><span data-stu-id="d47ff-396">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="d47ff-397">Applicare la regola 80-20 qui e ottimizzare per l'80%.</span><span class="sxs-lookup"><span data-stu-id="d47ff-397">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="d47ff-398">5</span><span class="sxs-lookup"><span data-stu-id="d47ff-398">5</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d47ff-399">Gli utenti vorranno visualizzare le distribuzioni contabili (codifica della fattura) sul dispositivo mobile nelle revisioni?</span><span class="sxs-lookup"><span data-stu-id="d47ff-399">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="d47ff-400">Sì</span><span class="sxs-lookup"><span data-stu-id="d47ff-400">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d47ff-401">Quante distribuzioni contabili (prezzo esteso, IVA, spese e così via) esistono per una riga della fattura?</span><span class="sxs-lookup"><span data-stu-id="d47ff-401">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="d47ff-402">Anche in questo caso, applicare la regola 80-20.</span><span class="sxs-lookup"><span data-stu-id="d47ff-402">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="d47ff-403">Prezzo esteso: 2 IVA: 2 Spese: 2</span><span class="sxs-lookup"><span data-stu-id="d47ff-403">Extended price: 2 Sales tax: 2 Charges: 2</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d47ff-404">Le fatture hanno distribuzioni contabili anche nell'intestazione?</span><span class="sxs-lookup"><span data-stu-id="d47ff-404">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="d47ff-405">In tal caso, queste distribuzioni contabili devono essere disponibili sul dispositivo?</span><span class="sxs-lookup"><span data-stu-id="d47ff-405">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="d47ff-406">Non utilizzato</span><span class="sxs-lookup"><span data-stu-id="d47ff-406">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d47ff-407">Gli utenti vorranno visualizzare gli allegati della fattura sul dispositivo?</span><span class="sxs-lookup"><span data-stu-id="d47ff-407">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="d47ff-408">Sì</span><span class="sxs-lookup"><span data-stu-id="d47ff-408">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a><span data-ttu-id="d47ff-409">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d47ff-409">Next steps</span></span>

<span data-ttu-id="d47ff-410">Le variazioni seguenti possono essere effettuate per lo scenario 1, in base ai requisiti dello scenario 2.</span><span class="sxs-lookup"><span data-stu-id="d47ff-410">The following variations can be done for scenario 1, based on the requirements for scenario 2.</span></span> <span data-ttu-id="d47ff-411">È possibile utilizzare questa sezione migliorare l'esperienza con l'app mobile.</span><span class="sxs-lookup"><span data-stu-id="d47ff-411">You can use this section to improve your mobile app experience.</span></span>

1.  <span data-ttu-id="d47ff-412">Poiché più righe fattura sono previste nello scenario 2, le seguenti modifiche alla progettazione aiuteranno a ottimizzare l'esperienza utente sul dispositivo mobile:</span><span class="sxs-lookup"><span data-stu-id="d47ff-412">Because more invoice lines are expected in scenario 2, the following changes to the design will help optimize the user experience on the mobile device:</span></span>
    1.  <span data-ttu-id="d47ff-413">Anziché visualizzare le righe fattura nella pagina dei dettagli (come nello scenario 1), gli utenti possono scegliere di visualizzare le righe in una pagina in versione mobile separata.</span><span class="sxs-lookup"><span data-stu-id="d47ff-413">Instead of viewing invoice lines on the details page (as in scenario 1), users can choose to view lines on a separate mobile page.</span></span>
    2.  <span data-ttu-id="d47ff-414">Poiché più righe fattura sono previste in questo scenario, se la pagina **VendMobileInvoiceAllDistributionTree** viene utilizzata per progettare la pagina delle distribuzioni per l'ambiente mobile (come nello scenario 1), potrebbe confondere l'utente correlare le righe alle distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="d47ff-414">Because more than one invoice line is expected in this scenario, if the **VendMobileInvoiceAllDistributionTree** page is used to design the distributions page for mobile (as in scenario 1), it might be confusing for the user to correlate lines to distributions.</span></span> <span data-ttu-id="d47ff-415">Di conseguenza, utilizzare la pagina **VendMobileInvoiceLineDistributionTree** per progettare la pagina delle distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="d47ff-415">Therefore, use the **VendMobileInvoiceLineDistributionTree** page to design the distributions page.</span></span>
    3.  <span data-ttu-id="d47ff-416">A livello ideale, le distribuzioni devono essere visualizzate nel contesto di una riga della fattura in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="d47ff-416">Ideally, the distributions should be shown in the context of an invoice line in this scenario.</span></span> <span data-ttu-id="d47ff-417">Di conseguenza, assicurarsi che l'utente possa eseguire il drill-down in una riga per visualizzare la pagina delle distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="d47ff-417">Therefore, make sure that the user can drill into a line to see the distributions page.</span></span> <span data-ttu-id="d47ff-418">Utilizzare la funzionalità di collegamento pagina per stabilire il drill-through, esattamente come fatto per l'intestazione e le pagine dei dettagli nello scenario 1.</span><span class="sxs-lookup"><span data-stu-id="d47ff-418">Use the page link capability to establish the drill-through, just as you did for the header and details pages in scenario 1.</span></span>

2.  <span data-ttu-id="d47ff-419">Poiché sono previsti più tipi di importo nelle distribuzioni nello scenario 2 (IVA, spese e così via), sarà utile visualizzare la descrizione del tipo di importo.</span><span class="sxs-lookup"><span data-stu-id="d47ff-419">Because more than one amount type is expected on the distributions in scenario 2 (sales tax, charges, and so on), it will be useful to show the description of the amount type.</span></span> <span data-ttu-id="d47ff-420">(Abbiamo omesso queste informazioni nello scenario 1).</span><span class="sxs-lookup"><span data-stu-id="d47ff-420">(We omitted this information in scenario 1.)</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]