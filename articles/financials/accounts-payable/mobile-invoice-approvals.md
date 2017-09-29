---
title: Approvazioni fatture per dispositivi mobili
description: "Questo argomento è destinato a fornire un approccio pratico alla progettazione di scenari mobili in in Dynamics 365 for Finance and Operations utilizzando l'approvazione delle fatture fornitore come caso d'uso."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 0e1b3382bc244996231bfb20f6d65ef2d07aef3a
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---

# <a name="mobile-invoice-approvals"></a><span data-ttu-id="0debe-103">Approvazioni fatture per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="0debe-103">Mobile invoice approvals</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0debe-104">Le funzionalità mobili in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition consentono agli utenti aziendali di progettare esperienze mobili.</span><span class="sxs-lookup"><span data-stu-id="0debe-104">Mobile capabilities in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition let a business user design mobile experiences.</span></span> <span data-ttu-id="0debe-105">Per gli scenari avanzati, la piattaforma anche consente agli sviluppatori di estendere le funzionalità nel modo desiderato.</span><span class="sxs-lookup"><span data-stu-id="0debe-105">For advanced scenarios, the platform also lets developers extend the capabilities as they desire.</span></span> <span data-ttu-id="0debe-106">Il modo più efficace di apprendere alcuni dei nuovi concetti sulle funzionalità mobili è di esaminare il processo di progettazione di alcuni scenari.</span><span class="sxs-lookup"><span data-stu-id="0debe-106">The most effective way to learn some of the new concepts on mobile is to go through the process of designing a few scenarios.</span></span> <span data-ttu-id="0debe-107">Questo argomento è destinato a fornire un approccio pratico alla progettazione di scenari mobili utilizzando l'approvazione delle fatture fornitore come caso d'uso.</span><span class="sxs-lookup"><span data-stu-id="0debe-107">This topic is intended to provide a practical approach to designing mobile scenarios by taking vendor invoice approvals for mobile as a use case.</span></span> <span data-ttu-id="0debe-108">Questo argomento dovrebbe aiutare nella progettazione di altre variazioni degli scenari e può essere applicato anche ad altri scenari non correlati alle fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="0debe-108">This topic should help you design other variations of the scenarios and can also be applied to other scenarios that aren’t related to vendor invoices.</span></span>

<a name="prerequisites"></a><span data-ttu-id="0debe-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0debe-109">Prerequisites</span></span>
-------------

| <span data-ttu-id="0debe-110">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="0debe-110">Prerequisite</span></span>                                                                                            | <span data-ttu-id="0debe-111">descrizione</span><span class="sxs-lookup"><span data-stu-id="0debe-111">Description</span></span>                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="0debe-112">Lettura preventiva del manuale sulle funzionalità mobili</span><span class="sxs-lookup"><span data-stu-id="0debe-112">Mobile handbook pre-read</span></span>                                                                                |[<span data-ttu-id="0debe-113">Piattaforma mobile</span><span class="sxs-lookup"><span data-stu-id="0debe-113">Mobile platform</span></span>](/dynamics365/unified-operations/dev-itpro/mobile-apps/platform/mobile-platform-home-page)                                                                                                  |
| <span data-ttu-id="0debe-114">Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0debe-114">Dynamics 365 for Finance and Operations</span></span>                                                                             | <span data-ttu-id="0debe-115">Un ambiente con Microsoft Dynamics 365 for Operations versione 1611 e aggiornamento 3 della piattaforma di Microsoft Dynamics for Operations (novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="0debe-115">An environment that has Microsoft Dynamics 365 for Operations version 1611 and Microsoft Dynamics for Operations platform update 3 (November 2016)</span></span>                   |
| <span data-ttu-id="0debe-116">Installare l'aggiornamento rapido KB 3204341.</span><span class="sxs-lookup"><span data-stu-id="0debe-116">Install hotfix KB 3204341.</span></span>                                                                              | <span data-ttu-id="0debe-117">Registrazione attività può registrare per errore due comandi di chiusura per le finestre di dialogo a discesa. Incluso nell'aggiornamento 3 della piattaforma di Dynamics 365 for Operations (aggiornamento di novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="0debe-117">Task recorder can erroneously record two Close commands for dropdown dialogs this is included in Dynamics 365 for Operation platform update 3 (November 2016 update)</span></span> |
| <span data-ttu-id="0debe-118">Installare l'aggiornamento rapido KB 3207800.</span><span class="sxs-lookup"><span data-stu-id="0debe-118">Install hotfix KB 3207800.</span></span>                                                                              | <span data-ttu-id="0debe-119">Questo aggiornamento rapido consente agli allegati di essere visualizzati sul client mobile. Incluso nell'aggiornamento 3 della piattaforma di Dynamics 365 for Operations (aggiornamento di novembre 2016).</span><span class="sxs-lookup"><span data-stu-id="0debe-119">This hotfix enables attachments to be viewed on the mobile client this is included in Dynamics 365 for Operation platform update 3 (November 2016 update).</span></span>           |
| <span data-ttu-id="0debe-120">Installare l'aggiornamento rapido KB 3208224.</span><span class="sxs-lookup"><span data-stu-id="0debe-120">Install hotfix KB 3208224.</span></span>                                                                              | <span data-ttu-id="0debe-121">Codice dell'applicazione mobile di approvazione fatture fornitore. Incluso nell'applicazione Microsoft Dynamics AX 7.0.1 (maggio 2016).</span><span class="sxs-lookup"><span data-stu-id="0debe-121">Application code for the mobile vendor invoice approval application this is included in Microsoft Dynamics AX application 7.0.1 (May 2016).</span></span>                          |
| <span data-ttu-id="0debe-122">Un dispositivo Android o iOS o Windows su cui è installata l'applicazione mobile di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0debe-122">An Android or iOS or a Windows device that has the mobile app installed for Finance and Operations</span></span> | <span data-ttu-id="0debe-123">Cercare l'app nell'app store appropriato.</span><span class="sxs-lookup"><span data-stu-id="0debe-123">Search for the app in the appropriate app store.</span></span>                                                                                                                     |

## <a name="introduction"></a><span data-ttu-id="0debe-124">Introduzione</span><span class="sxs-lookup"><span data-stu-id="0debe-124">Introduction</span></span>
<span data-ttu-id="0debe-125">Le approvazioni mobili per le fatture fornitore richiedono i tre aggiornamenti rapidi indicati nella sezione "Prerequisiti".</span><span class="sxs-lookup"><span data-stu-id="0debe-125">Mobile approvals for vendor invoices require the three hotfixes that are mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="0debe-126">Questi aggiornamenti rapidi non forniscono un'area di lavoro per le approvazioni fatture.</span><span class="sxs-lookup"><span data-stu-id="0debe-126">These hotfixes don’t provide a workspace for the invoice approvals.</span></span> <span data-ttu-id="0debe-127">Per informazioni su cos'è un'area di lavoro nel contesto delle funzionalità mobili, leggere il relativo manuale indicato nella sezione "Prerequisiti".</span><span class="sxs-lookup"><span data-stu-id="0debe-127">To learn what a workspace is in the context of mobile, read the mobile handbook that is mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="0debe-128">L'area di lavoro di approvazione fatture deve essere progettata.</span><span class="sxs-lookup"><span data-stu-id="0debe-128">The invoice approvals workspace must be designed.</span></span> 

<span data-ttu-id="0debe-129">Ogni organizzazione orchestra e definisce il proprio processo aziendale per le fatture fornitore in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="0debe-129">Every organization orchestrates and defines its business process for vendor invoices differently.</span></span> <span data-ttu-id="0debe-130">Prima di iniziare a progettare un'esperienza mobile per le approvazioni fatture fornitore, valutare i seguenti aspetti del processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="0debe-130">Before you design a mobile experience for vendor invoice approvals, you should consider the following aspects of the business process.</span></span> <span data-ttu-id="0debe-131">Il concetto di base è di utilizzare questi punti dati il più possibile per ottimizzare l'esperienza utente sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0debe-131">The idea is to use these data points as much as possible to optimize the user experience on the device.</span></span>

-   <span data-ttu-id="0debe-132">Quali campi dall'intestazione fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</span><span class="sxs-lookup"><span data-stu-id="0debe-132">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="0debe-133">Quali campi delle righe fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</span><span class="sxs-lookup"><span data-stu-id="0debe-133">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="0debe-134">Quante righe fattura sono presenti in una fattura?</span><span class="sxs-lookup"><span data-stu-id="0debe-134">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="0debe-135">Applicare la regola 80-20 qui e ottimizzare per l'80%.</span><span class="sxs-lookup"><span data-stu-id="0debe-135">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span>
-   <span data-ttu-id="0debe-136">Gli utenti vorranno visualizzare le distribuzioni contabili (codifica della fattura) sul dispositivo mobile nelle revisioni?</span><span class="sxs-lookup"><span data-stu-id="0debe-136">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span> <span data-ttu-id="0debe-137">Se la risposta a questa domanda è affermativa, considerare le domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="0debe-137">If the answer to this question is yes, consider the following questions:</span></span>
    -   <span data-ttu-id="0debe-138">Quante distribuzioni contabili (prezzo esteso, IVA, spese, suddivisioni e così via) esistono per una riga della fattura?</span><span class="sxs-lookup"><span data-stu-id="0debe-138">How many accounting distributions (extended price, sales tax, charges, splits, and so on) are there for an invoice line?</span></span> <span data-ttu-id="0debe-139">Anche in questo caso, applicare la regola 80-20.</span><span class="sxs-lookup"><span data-stu-id="0debe-139">Again, apply the 80-20 rule.</span></span>
    -   <span data-ttu-id="0debe-140">Le fatture hanno distribuzioni contabili anche nell'intestazione?</span><span class="sxs-lookup"><span data-stu-id="0debe-140">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="0debe-141">In tal caso, queste distribuzioni contabili devono essere disponibili sul dispositivo?</span><span class="sxs-lookup"><span data-stu-id="0debe-141">If so, should these accounting distributions be available on the device?</span></span>

> [!NOTE]
> <span data-ttu-id="0debe-142">In questo argomento non viene illustrato come modificare le distribuzioni contabili, poiché questa funzionalità non è attualmente supportata per scenari mobili.</span><span class="sxs-lookup"><span data-stu-id="0debe-142">This topic doesn’t explain how to edit accounting distributions, because this functionality isn’t currently supported for mobile scenarios.</span></span>

-   <span data-ttu-id="0debe-143">Gli utenti vorranno visualizzare gli allegati della fattura sul dispositivo?</span><span class="sxs-lookup"><span data-stu-id="0debe-143">Will users want to see attachments for the invoice on the device?</span></span>

<span data-ttu-id="0debe-144">La progettazione dell'esperienza mobile per le approvazioni fatture varierà in base alle risposte a queste domande.</span><span class="sxs-lookup"><span data-stu-id="0debe-144">The design of the mobile experience for invoice approvals will differ, depending on the answers to these questions.</span></span> <span data-ttu-id="0debe-145">L'obiettivo è di ottimizzare l'esperienza utente del processo aziendale sui dispositivi mobili di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0debe-145">The objective is to optimize the user experience for the business process on mobile in an organization.</span></span> <span data-ttu-id="0debe-146">Nel resto di questo argomento, esamineremo due variazioni allo scenario basate sulle diverse risposte alle domande precedenti.</span><span class="sxs-lookup"><span data-stu-id="0debe-146">In the rest of this topic, we will look at two scenario variations that are based on different answers to the preceding questions.</span></span> 

<span data-ttu-id="0debe-147">In generale quando si lavora con lo strumento di progettazione mobile, assicurarsi di "pubblicare" le modifiche per evitare la perdita degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="0debe-147">As a general guidance, when working with the mobile designer, make sure to 'publish' the changes to prevent losing the updates.</span></span>

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a><span data-ttu-id="0debe-148">Progettazione di uno scenario semplice di approvazione fatture per Contoso</span><span class="sxs-lookup"><span data-stu-id="0debe-148">Designing a simple invoice approval scenario for Contoso</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0debe-149">Attributo scenario</span><span class="sxs-lookup"><span data-stu-id="0debe-149">Scenario attribute</span></span></th>
<th><span data-ttu-id="0debe-150">Risposta</span><span class="sxs-lookup"><span data-stu-id="0debe-150">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0debe-151">Quali campi dall'intestazione fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</span><span class="sxs-lookup"><span data-stu-id="0debe-151">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="0debe-152">Nome fornitore</span><span class="sxs-lookup"><span data-stu-id="0debe-152">Vendor name</span></span></li>
<li><span data-ttu-id="0debe-153">Totale fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-153">Invoice total</span></span></li>
<li><span data-ttu-id="0debe-154">Conto fatture</span><span class="sxs-lookup"><span data-stu-id="0debe-154">Invoice account</span></span></li>
<li><span data-ttu-id="0debe-155">Numero fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-155">Invoice number</span></span></li>
<li><span data-ttu-id="0debe-156">Data fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-156">Invoice date</span></span></li>
<li><span data-ttu-id="0debe-157">Descrizione fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-157">Invoice description</span></span></li>
<li><span data-ttu-id="0debe-158">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="0debe-158">Due date</span></span></li>
<li><span data-ttu-id="0debe-159">Valuta della fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-159">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0debe-160">Quali campi delle righe fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</span><span class="sxs-lookup"><span data-stu-id="0debe-160">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="0debe-161">Categoria di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="0debe-161">Procurement category</span></span></li>
<li><span data-ttu-id="0debe-162">Quantità</span><span class="sxs-lookup"><span data-stu-id="0debe-162">Quantity</span></span></li>
<li><span data-ttu-id="0debe-163">Prezzo unitario</span><span class="sxs-lookup"><span data-stu-id="0debe-163">Unit price</span></span></li>
<li><span data-ttu-id="0debe-164">Importo netto riga</span><span class="sxs-lookup"><span data-stu-id="0debe-164">Line net amount</span></span></li>
<li><span data-ttu-id="0debe-165">Importo 1099</span><span class="sxs-lookup"><span data-stu-id="0debe-165">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0debe-166">Quante righe fattura sono presenti in una fattura?</span><span class="sxs-lookup"><span data-stu-id="0debe-166">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="0debe-167">Applicare la regola 80-20 qui e ottimizzare per l'80%.</span><span class="sxs-lookup"><span data-stu-id="0debe-167">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="0debe-168">1</span><span class="sxs-lookup"><span data-stu-id="0debe-168">1</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0debe-169">Gli utenti vorranno visualizzare le distribuzioni contabili (codifica della fattura) sul dispositivo mobile nelle revisioni?</span><span class="sxs-lookup"><span data-stu-id="0debe-169">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="0debe-170">Sì</span><span class="sxs-lookup"><span data-stu-id="0debe-170">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0debe-171">Quante distribuzioni contabili (prezzo esteso, IVA, spese e così via) esistono per una riga della fattura?</span><span class="sxs-lookup"><span data-stu-id="0debe-171">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="0debe-172">Anche in questo caso, applicare la regola 80-20.</span><span class="sxs-lookup"><span data-stu-id="0debe-172">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="0debe-173">Prezzo esteso: 2 IVA: 0 Spese: 0</span><span class="sxs-lookup"><span data-stu-id="0debe-173">Extended price: 2 Sales tax: 0 Charges: 0</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0debe-174">Le fatture hanno distribuzioni contabili anche nell'intestazione?</span><span class="sxs-lookup"><span data-stu-id="0debe-174">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="0debe-175">In tal caso, queste distribuzioni contabili devono essere disponibili sul dispositivo?</span><span class="sxs-lookup"><span data-stu-id="0debe-175">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="0debe-176">Non utilizzato</span><span class="sxs-lookup"><span data-stu-id="0debe-176">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0debe-177">Gli utenti vorranno visualizzare gli allegati della fattura sul dispositivo?</span><span class="sxs-lookup"><span data-stu-id="0debe-177">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="0debe-178">Sì</span><span class="sxs-lookup"><span data-stu-id="0debe-178">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a><span data-ttu-id="0debe-179">Creare l'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="0debe-179">Create the workspace</span></span>

1.  <span data-ttu-id="0debe-180">In un browser, aprire Finance and Operations e accedere.</span><span class="sxs-lookup"><span data-stu-id="0debe-180">In a browser, open Finance and Operations, and sign in.</span></span>
2.  <span data-ttu-id="0debe-181">Effettuato l'accesso. aggiungere **&mode=mobile** all'URL come mostrato nell'esempio seguente e aggiornare la pagina: https://&lt;urlutente&gt;/?cmp=usmf&mi=DefaultDashboard**&mode=mobile**</span><span class="sxs-lookup"><span data-stu-id="0debe-181">After you’ve signed in, append **&mode=mobile** to the URL as shown in the following example, and refresh the page: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard**&mode=mobile**</span></span>
3.  <span data-ttu-id="0debe-182">Fare clic sul pulsante **Impostazioni** (ingranaggio) in alto a destra nella pagina e fare clic su **App per dispositivi mobili**.</span><span class="sxs-lookup"><span data-stu-id="0debe-182">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**.</span></span> <span data-ttu-id="0debe-183">Lo strumento di progettazione app per dispositivo mobili deve apparire come Registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="0debe-183">The mobile app designer must show up just as Task recorder shows up.</span></span>
4.  <span data-ttu-id="0debe-184">Fare clic su **Aggiungi** per creare una nuova area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-184">Click **Add** to create a new workspace.</span></span> <span data-ttu-id="0debe-185">Per questo esempio, chiamare l'area di lavoro **Approvazioni personali**.</span><span class="sxs-lookup"><span data-stu-id="0debe-185">For this example, name the workspace **My approvals**.</span></span>
5.  <span data-ttu-id="0debe-186">Immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="0debe-186">Enter a description.</span></span>
6.  <span data-ttu-id="0debe-187">Seleziona un colore per l'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-187">Select a workspace color.</span></span> <span data-ttu-id="0debe-188">IL colore dell'area di lavoro verrà utilizzato per lo stile globale dell'esperienza mobile per l'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-188">The workspace color will be used for the overall style of the mobile experience for this workspace.</span></span>
7.  <span data-ttu-id="0debe-189">Selezionare un'icona per l'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-189">Select an icon for the workspace.</span></span>
8.  <span data-ttu-id="0debe-190">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="0debe-190">Click **Done**</span></span>
9.  <span data-ttu-id="0debe-191">Fare clic su **Pubblica area di lavoro** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="0debe-191">Click **Publish workspace** to save the changes</span></span>

### <a name="vendor-invoices-assigned-to-me"></a><span data-ttu-id="0debe-192">Fatture fornitore assegnate all'utente</span><span class="sxs-lookup"><span data-stu-id="0debe-192">Vendor invoices assigned to me</span></span>

<span data-ttu-id="0debe-193">La prima pagina in versione mobile che è consigliabile progettare è l'elenco di fatture assegnate all'utente per la revisione.</span><span class="sxs-lookup"><span data-stu-id="0debe-193">The first mobile page that you should design is the list of invoices that are assigned to the user for review.</span></span> <span data-ttu-id="0debe-194">Per progettare questa pagina in versione mobile, utilizzare la pagina **VendMobileInvoiceAssignedToMeListPage** di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0debe-194">To design this mobile page, use the **VendMobileInvoiceAssignedToMeListPage** page in Finance and Operations.</span></span> <span data-ttu-id="0debe-195">Prima di completare questa procedura, assicurarsi di avere almeno una fattura fornitore assegnata per la revisione e che la riga fattura abbia due distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="0debe-195">Before you complete this procedure, make sure that at least one vendor invoice is assigned to you for review, and that the invoice line has two distributions.</span></span> <span data-ttu-id="0debe-196">Questa impostazione soddisfa i requisiti di questo scenario.</span><span class="sxs-lookup"><span data-stu-id="0debe-196">This setup meets the requirements for this scenario.</span></span>

1.  <span data-ttu-id="0debe-197">Nell'URL di Finance and Operations, sostituire il nome della voce di menu con **VendMobileInvoiceAssignedToMeListPage** per aprire la versione  mobile della pagina elenco **Fatture fornitore in sospeso assegnate all'utente** nel modulo **Contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="0debe-197">In the Finance and Operations URL, replace the name of the menu item with **VendMobileInvoiceAssignedToMeListPage** to open the mobile version of the **Pending vendor invoices assigned to me** list page in the **Accounts payable** module.</span></span> <span data-ttu-id="0debe-198">A seconda del numero delle fatture assegnate all'utente, questa pagina mostrerà tali fatture.</span><span class="sxs-lookup"><span data-stu-id="0debe-198">Depending on the number of invoices that you have in your system assigned to you, this page will show those invoices.</span></span> <span data-ttu-id="0debe-199">È possibile usare il filtro a sinistra per trovare una fattura specifica.</span><span class="sxs-lookup"><span data-stu-id="0debe-199">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="0debe-200">Tuttavia, non è richiesta una fattura specifica per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="0debe-200">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="0debe-201">È solo necessario avere qualche fattura assegnata in modo da poter progettare la pagina in versione mobile.</span><span class="sxs-lookup"><span data-stu-id="0debe-201">We just require some invoice assigned to you which is going to allow you to design the mobile page.</span></span> <span data-ttu-id="0debe-202">Le nuove pagine disponibili sono state progettate appositamente per sviluppare scenari mobili per la fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="0debe-202">The new pages that are available have been designed specifically for developing mobile scenarios for vendor invoice.</span></span> <span data-ttu-id="0debe-203">Di conseguenza, è necessario utilizzare queste pagine.</span><span class="sxs-lookup"><span data-stu-id="0debe-203">Therefore, you must use these pages.</span></span> <span data-ttu-id="0debe-204">L'URL deve essere simile al seguente e dopo l'immissione la pagina indicata nella figura deve essere visualizzata: https://&lt;URLutente&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile [![Pagina Fatture fornitore in sospeso assegnate all'utente](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span><span class="sxs-lookup"><span data-stu-id="0debe-204">The URL should resemble the following URL, and after you enter it, the page that is shown in the illustration must appear: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile [![Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span></span>
2.  <span data-ttu-id="0debe-205">Fare clic sul pulsante **Impostazioni** (ingranaggio) in alto a destra nella pagina e fare clic su **App per dispositivi mobili**.</span><span class="sxs-lookup"><span data-stu-id="0debe-205">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
3.  <span data-ttu-id="0debe-206">Selezionare l'area di lavoro e fare clic su **Modifica**</span><span class="sxs-lookup"><span data-stu-id="0debe-206">Select your workspace and click **Edit**</span></span>
4.  <span data-ttu-id="0debe-207">Fare clic su **Aggiungi pagina** per creare la prima pagina in versione mobile.</span><span class="sxs-lookup"><span data-stu-id="0debe-207">Click **Add page** to create the first mobile page.</span></span>
5.  <span data-ttu-id="0debe-208">Immettere un nome, ad esempio **My vendor invoices** e una descrizione, ad esempio **Vendor invoices assigned to me for review**.</span><span class="sxs-lookup"><span data-stu-id="0debe-208">Enter a name, such as **My vendor invoices**, and a description, such as **Vendor invoices assigned to me for review**.</span></span>
6.  <span data-ttu-id="0debe-209">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="0debe-209">Click **Done**.</span></span>
7.  <span data-ttu-id="0debe-210">Nello strumento di progettazione mobile, nella scheda **Campi** fare clic su **Seleziona campi**.</span><span class="sxs-lookup"><span data-stu-id="0debe-210">In the mobile designer, on the **Fields** tab, click **Select fields**.</span></span> <span data-ttu-id="0debe-211">Le colonne della pagina elenco devono essere simili alla figura seguente.</span><span class="sxs-lookup"><span data-stu-id="0debe-211">The columns on the list page must resemble the following illustration.</span></span> <span data-ttu-id="0debe-212">[![Colonne nella pagina Fatture fornitore in sospeso assegnate all'utente](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span><span class="sxs-lookup"><span data-stu-id="0debe-212">[![Columns on the Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span></span>
8.  <span data-ttu-id="0debe-213">Aggiungere le colonne necessarie dalla pagina elenco che devono essere visualizzate agli utenti nella pagina in versione mobile.</span><span class="sxs-lookup"><span data-stu-id="0debe-213">Add the required columns from the list page that must be shown to the users in the mobile page.</span></span> <span data-ttu-id="0debe-214">L'ordine di aggiunta è l'ordine in cui i campi verranno visualizzati all'utente finale.</span><span class="sxs-lookup"><span data-stu-id="0debe-214">The order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="0debe-215">Il solo modo per modificare l'ordine dei campi è riselezionarli tutti.</span><span class="sxs-lookup"><span data-stu-id="0debe-215">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> <span data-ttu-id="0debe-216">In base ai requisiti di questo scenario, sono necessari i seguenti otto campi.</span><span class="sxs-lookup"><span data-stu-id="0debe-216">Based on the requirements for this scenario, the following eight fields are required.</span></span> <span data-ttu-id="0debe-217">Tuttavia, alcuni utenti potrebbero considerare otto campi troppe informazioni da avere su un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="0debe-217">However, some users might consider eight fields too much information to have on a mobile device.</span></span> <span data-ttu-id="0debe-218">Di conseguenza, mostreremo solo i campi più importanti nella visualizzazione elenco mobile.</span><span class="sxs-lookup"><span data-stu-id="0debe-218">Therefore, we will show only the most important fields in the mobile list view.</span></span> <span data-ttu-id="0debe-219">I campi rimanenti sembreranno appariranno nella visualizzazione dettagli che progetteremo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="0debe-219">The remaining fields will appear in the details view that we will design later.</span></span> <span data-ttu-id="0debe-220">Per ora, aggiungeremo i seguenti campi.</span><span class="sxs-lookup"><span data-stu-id="0debe-220">For now, we will add the following fields.</span></span> <span data-ttu-id="0debe-221">Fare clic sul segno (**+**) nelle colonne da aggiungere alla pagina mobile.</span><span class="sxs-lookup"><span data-stu-id="0debe-221">Click the plus sign (**+**) in these columns to add to the mobile page.</span></span>
    - <span data-ttu-id="0debe-222">Nome fornitore</span><span class="sxs-lookup"><span data-stu-id="0debe-222">Vendor name</span></span>
    - <span data-ttu-id="0debe-223">Totale fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-223">Invoice total</span></span>
    - <span data-ttu-id="0debe-224">Conto fatture</span><span class="sxs-lookup"><span data-stu-id="0debe-224">Invoice account</span></span>
    - <span data-ttu-id="0debe-225">Numero fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-225">Invoice number</span></span>
    - <span data-ttu-id="0debe-226">Data fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-226">Invoice date</span></span>

    <span data-ttu-id="0debe-227">Dopo che i campi vengono aggiunti, la pagina mobile deve somigliare alla figura seguente.</span><span class="sxs-lookup"><span data-stu-id="0debe-227">After the fields are added, the mobile page must resemble the following illustration.</span></span> 
    <span data-ttu-id="0debe-228">[![Pagina dopo l'aggiunta dei campi](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span><span class="sxs-lookup"><span data-stu-id="0debe-228">[![Page after fields are added](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span></span>
9.  <span data-ttu-id="0debe-229">È inoltre necessario aggiungere le seguenti colonne ora, in modo da abilitare le azioni del flusso di lavoro successivamente.</span><span class="sxs-lookup"><span data-stu-id="0debe-229">You must also add the following columns now, so that we can enable workflow actions later.</span></span>
    - <span data-ttu-id="0debe-230">Mostra attività completare</span><span class="sxs-lookup"><span data-stu-id="0debe-230">Show complete task</span></span>
    - <span data-ttu-id="0debe-231">Mostra attività delegare</span><span class="sxs-lookup"><span data-stu-id="0debe-231">Show delegate task</span></span>
    - <span data-ttu-id="0debe-232">Mostra attività richiamare</span><span class="sxs-lookup"><span data-stu-id="0debe-232">Show recall task</span></span>
    - <span data-ttu-id="0debe-233">Mostra attività rifiutare</span><span class="sxs-lookup"><span data-stu-id="0debe-233">Show reject task</span></span>
    - <span data-ttu-id="0debe-234">Mostra attività richiedere completamento</span><span class="sxs-lookup"><span data-stu-id="0debe-234">Show request completion task</span></span>
    - <span data-ttu-id="0debe-235">Mostra attività inviare nuovamente</span><span class="sxs-lookup"><span data-stu-id="0debe-235">Show resubmit task</span></span>

10. <span data-ttu-id="0debe-236">Fare clic su **Fine** per uscire dalla modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="0debe-236">Click **Done** to exit edit mode.</span></span>
11. <span data-ttu-id="0debe-237">Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="0debe-237">Click **Back** and then **Done** to exit the workspace</span></span>
12. <span data-ttu-id="0debe-238">Fare clic su **Pubblica area di lavoro** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-238">Click **Publish workspace** to save your work.</span></span>
13. <span data-ttu-id="0debe-239">Abilitare **Visualizza totale fatture su elenco fatture fornitore in sospeso** nel modulo dei parametri contabilità fornitori in **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="0debe-239">Enable **Display invoice total on pending vendor invoices list** in accounts payable parameters form under **Invoice**.</span></span> <span data-ttu-id="0debe-240">Tenere presente che solo abilitando questo parametro, i totali fattura verranno calcolati e visualizzati nella pagina elenco delle fatture fornitore in sospeso.</span><span class="sxs-lookup"><span data-stu-id="0debe-240">Note that, only by enabling this parameter, invoice totals will be calculated to be displayed on the pending vendor invoices list page.</span></span> <span data-ttu-id="0debe-241">Si tratta di una nuova funzionalità nell'ambito dell'aggiornamento rapido 3208224.</span><span class="sxs-lookup"><span data-stu-id="0debe-241">This is a new capability as part of the pre-requisite hot fix 3208224.</span></span>

### <a name="vendor-invoice-details"></a><span data-ttu-id="0debe-242">Dettagli fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="0debe-242">Vendor invoice details</span></span>

<span data-ttu-id="0debe-243">Per progettare la pagina dei dettagli fattura per l'ambiente mobile, utilizzare la pagina **VendMobileInvoiceHeaderDetails** in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0debe-243">To design the invoice details page for mobile, use the **VendMobileInvoiceHeaderDetails** page in Finance and Operations.</span></span> <span data-ttu-id="0debe-244">Tenere presente che, a seconda del numero di fatture nel sistema, la pagina mostra la fattura più vecchia (la fattura creata per prima).</span><span class="sxs-lookup"><span data-stu-id="0debe-244">Note that, depending on the number of invoices that you have in your system, this page shows the oldest invoice (the invoice that was created first).</span></span> <span data-ttu-id="0debe-245">È possibile usare il filtro a sinistra per trovare una fattura specifica.</span><span class="sxs-lookup"><span data-stu-id="0debe-245">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="0debe-246">Tuttavia, non è richiesta una fattura specifica per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="0debe-246">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="0debe-247">Sono neecssari solo alcuni dati della fattura per progettare la pagina in versione mobile.</span><span class="sxs-lookup"><span data-stu-id="0debe-247">We just require some invoice data so that we can design the mobile page.</span></span> <span data-ttu-id="0debe-248">[![Pagina Flusso di lavoro](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span><span class="sxs-lookup"><span data-stu-id="0debe-248">[![Workflow page](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span></span>

1.  <span data-ttu-id="0debe-249">Nell'URL di Finance and Operations, sostituire il nome della voce di menu con **VendMobileInvoiceHeaderDetails** per aprire il modulo</span><span class="sxs-lookup"><span data-stu-id="0debe-249">In the Finance and Operations URL, replace the name of the menu item with **VendMobileInvoiceHeaderDetails** to open the form</span></span>
2.  <span data-ttu-id="0debe-250">Aprire lo strumento di progettazione mobile dal pulsante **Impostazioni** (ingranaggio).</span><span class="sxs-lookup"><span data-stu-id="0debe-250">Open the mobile designer from the **Settings** (gear) button.</span></span>
3.  <span data-ttu-id="0debe-251">Fare clic sul pulsante **Modifica** per avviare la modalità di modifica nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-251">Click the **Edit** button to start edit mode in the workspace.</span></span>
4.  <span data-ttu-id="0debe-252">Selezionare la pagina **My vendor invoices** creata in precedenza quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0debe-252">Select the **My vendor invoices **page that you created earlier, and then click **Edit**.</span></span>
5.  <span data-ttu-id="0debe-253">Nella scheda **Campi** fare clic sull'intestazione di colonna **Griglia**.</span><span class="sxs-lookup"><span data-stu-id="0debe-253">On the **Fields** tab, click the **Grid** column heading.</span></span>
6.  <span data-ttu-id="0debe-254">Fare clic su **Proprietà** &gt; **Aggiungi pagina**.</span><span class="sxs-lookup"><span data-stu-id="0debe-254">Click **Properties** &gt; **Add page**.</span></span> <span data-ttu-id="0debe-255">**Nota:** Quando si fa clic su l'intestazione **Griglia** e si aggiunge una pagina, la relazione con la pagina dei dettagli è impostata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0debe-255">**Note:** When you click the **Grid** heading and add a page, the relationship with the details page is established automatically.</span></span>
7.  <span data-ttu-id="0debe-256">Immettere un titolo della pagina, ad esempio **Invoice details** e una descrizione, ad esempio **View invoice header and line details**.</span><span class="sxs-lookup"><span data-stu-id="0debe-256">Enter a page title, such as **Invoice details**, and a description, such as **View invoice header and line details**.</span></span>
8.  <span data-ttu-id="0debe-257">Fare clic su **Seleziona campi**.</span><span class="sxs-lookup"><span data-stu-id="0debe-257">Click **Select fields**.</span></span> <span data-ttu-id="0debe-258">Notare che l'ordine di aggiunta è l'ordine in cui i campi verranno visualizzati all'utente finale.</span><span class="sxs-lookup"><span data-stu-id="0debe-258">Note that, the order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="0debe-259">Il solo modo per modificare l'ordine dei campi è riselezionarli tutti.</span><span class="sxs-lookup"><span data-stu-id="0debe-259">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> 
9.  <span data-ttu-id="0debe-260">Aggiungere i campi seguenti dall'intestazione in base ai requisiti di questo scenario:</span><span class="sxs-lookup"><span data-stu-id="0debe-260">Add the following fields from the header, based on the requirements for this scenario:</span></span>
    - <span data-ttu-id="0debe-261">Nome fornitore</span><span class="sxs-lookup"><span data-stu-id="0debe-261">Vendor name</span></span>
    - <span data-ttu-id="0debe-262">Totale fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-262">Invoice total</span></span>
    - <span data-ttu-id="0debe-263">Conto fatture</span><span class="sxs-lookup"><span data-stu-id="0debe-263">Invoice account</span></span>
    - <span data-ttu-id="0debe-264">Numero fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-264">Invoice number</span></span>
    - <span data-ttu-id="0debe-265">Data fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-265">Invoice date</span></span>
    - <span data-ttu-id="0debe-266">Descrizione fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-266">Invoice description</span></span>
    - <span data-ttu-id="0debe-267">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="0debe-267">Due date</span></span>
    - <span data-ttu-id="0debe-268">Valuta della fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-268">Invoice currency</span></span>

10. <span data-ttu-id="0debe-269">Aggiungere i seguenti campi dalla griglia di righe nella pagina:</span><span class="sxs-lookup"><span data-stu-id="0debe-269">Add the following fields from the lines grid on the page:</span></span>
    - <span data-ttu-id="0debe-270">Categoria di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="0debe-270">Procurement category</span></span>
    - <span data-ttu-id="0debe-271">Quantità</span><span class="sxs-lookup"><span data-stu-id="0debe-271">Quantity</span></span>
    - <span data-ttu-id="0debe-272">Prezzo unitario</span><span class="sxs-lookup"><span data-stu-id="0debe-272">Unit price</span></span>
    - <span data-ttu-id="0debe-273">Importo netto riga</span><span class="sxs-lookup"><span data-stu-id="0debe-273">Line net amount</span></span>
    - <span data-ttu-id="0debe-274">Importo 1099</span><span class="sxs-lookup"><span data-stu-id="0debe-274">1099 amount</span></span>

11. <span data-ttu-id="0debe-275">Dopo che tutti i campi dai due passaggi precedenti sono stati aggiunti, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="0debe-275">After all the fields from the previous two steps have been added, click **Done**.</span></span> <span data-ttu-id="0debe-276">La pagina deve essere simili alla figura seguente.</span><span class="sxs-lookup"><span data-stu-id="0debe-276">The page must resemble the following illustration.</span></span>
<span data-ttu-id="0debe-277">[![Pagina dopo l'aggiunta dei campi](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span><span class="sxs-lookup"><span data-stu-id="0debe-277">[![Page after fields are added](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span></span>
12. <span data-ttu-id="0debe-278">Fare clic su **Fine** per uscire dalla modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="0debe-278">Click **Done** to exit edit mode.</span></span>
13. <span data-ttu-id="0debe-279">Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="0debe-279">Click **Back** and then **Done** to exit the workspace</span></span>
14. <span data-ttu-id="0debe-280">Fare clic su **Pubblica area di lavoro** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-280">Click **Publish workspace** to save your work</span></span>

### <a name="workflow-actions"></a><span data-ttu-id="0debe-281">Azioni flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0debe-281">Workflow actions</span></span>

<span data-ttu-id="0debe-282">Per aggiungere le azioni del flusso di lavoro, utilizzare la pagina **VendMobileInvoiceHeaderDetails** in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0debe-282">To add workflow actions, use the **VendMobileInvoiceHeaderDetails** page in Finance and Operations.</span></span> <span data-ttu-id="0debe-283">Per visualizzare questa pagina, sostituire il nome della voce di menu nell'URL, come fatto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0debe-283">To open this page, replace the name of the menu item in the URL, as you did earlier.</span></span> <span data-ttu-id="0debe-284">Quindi aprire lo strumento di progettazione mobile dal pulsante **Impostazioni** (ingranaggio).</span><span class="sxs-lookup"><span data-stu-id="0debe-284">Then open the mobile designer from the **Settings** (gear) button.</span></span> <span data-ttu-id="0debe-285">Seguire questi passaggi per aggiungere le azioni del flusso di lavoro nella pagina dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="0debe-285">Follow these steps to add workflow actions on the details page.</span></span> <span data-ttu-id="0debe-286">È obbligatorio avere fatture assegnate che si trovato in uno stato tale da rendere disponibili le azioni del flusso di lavoro per l'utente per la progettazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="0debe-286">You must have invoices assigned to you that are in the appropriate state to make the workflow actions available to you that you are going to design for.</span></span>

#### <a name="record-workflow-actions"></a><span data-ttu-id="0debe-287">Registrare azioni del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0debe-287">Record workflow actions</span></span>
1.  <span data-ttu-id="0debe-288">Fare clic sul pulsante **Modifica** per avviare la modalità di modifica nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-288">Click the **Edit** button to start edit mode in the workspace.</span></span>
2.  <span data-ttu-id="0debe-289">Selezionare la pagina **Invoice details** creata in precedenza quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0debe-289">Select the **Invoice details** page that you created earlier, and then click **Edit**.</span></span>
3.  <span data-ttu-id="0debe-290">Nella scheda **Azioni** fare clic su **Aggiungi azione**.</span><span class="sxs-lookup"><span data-stu-id="0debe-290">On the **Actions** tab, click **Add action**.</span></span>
4.  <span data-ttu-id="0debe-291">Immettere un titolo dell'azione, come **Approve** e una descrizione, ad esempio **Approve invoice**.</span><span class="sxs-lookup"><span data-stu-id="0debe-291">Enter an action title, such as **Approve**, and a description, such as **Approve invoice**.</span></span> <span data-ttu-id="0debe-292">Si noti che il titolo di azione immesso in questo campo diventa il nome dell'azione che verrà visualizzata all'utente nell'app per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="0debe-292">Note that the action title that you enter here becomes the name of the action that is shown to the user in the mobile app.</span></span>
5.  <span data-ttu-id="0debe-293">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="0debe-293">Click **Done**.</span></span>
6.  <span data-ttu-id="0debe-294">Fare clic su **Seleziona campi**.</span><span class="sxs-lookup"><span data-stu-id="0debe-294">Click **Select fields**.</span></span>
7.  <span data-ttu-id="0debe-295">Procedere lungo il processo del flusso di lavoro nella pagina **VendMobileInvoiceHeaderDetails** e completare l'azione che si è voluta registrare.</span><span class="sxs-lookup"><span data-stu-id="0debe-295">Go through the workflow process on the **VendMobileInvoiceHeaderDetails** page, and complete the action that you wanted to record.</span></span> <span data-ttu-id="0debe-296">Assicurarsi di immettere commenti del flusso di lavoro durante il processo, in modo che un campo di commenti viene anche incluso nell'esperienza mobile.</span><span class="sxs-lookup"><span data-stu-id="0debe-296">Make sure that you enter workflow comments during this process, so that a comments field is also included in the mobile experience.</span></span>
8.  <span data-ttu-id="0debe-297">Dopo che l'azione del flusso di lavoro viene eseguita, fare clic su **Fine** per completare l'attività Seleziona campi.</span><span class="sxs-lookup"><span data-stu-id="0debe-297">After the workflow action is run, click **Done** to complete the Select fields task.</span></span>
9.  <span data-ttu-id="0debe-298">Fare clic su **Fine** per uscire dalla modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="0debe-298">Click **Done** to exit edit mode.</span></span>
10. <span data-ttu-id="0debe-299">Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="0debe-299">Click **Back** and then **Done** to exit the workspace</span></span>
11. <span data-ttu-id="0debe-300">Fare clic su **Pubblica area di lavoro** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-300">Click **Publish workspace** to save your work</span></span>
12. <span data-ttu-id="0debe-301">Ripetere i passaggi precedenti per registrare tutte le azioni necessarie del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-301">Repeat the previous steps to record all the required workflow actions.</span></span> 

#### <a name="create-a-js-file"></a><span data-ttu-id="0debe-302">Creare un file .js</span><span class="sxs-lookup"><span data-stu-id="0debe-302">Create a .js file</span></span>
1. <span data-ttu-id="0debe-303">Aprire il Blocco note o Microsoft Visual Studio e incollare il seguente codice.</span><span class="sxs-lookup"><span data-stu-id="0debe-303">Open Notepad or Microsoft Visual Studio, and paste the following code.</span></span> <span data-ttu-id="0debe-304">Salvare il file come file .js.</span><span class="sxs-lookup"><span data-stu-id="0debe-304">Save the file as a .js file.</span></span> <span data-ttu-id="0debe-305">Il codice effettua quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0debe-305">This code does the following:</span></span>
    - <span data-ttu-id="0debe-306">Nasconde le colonne extra correlate ai flussi di lavoro che abbiamo aggiunto in precedenza nella pagina elenco in versione mobile.</span><span class="sxs-lookup"><span data-stu-id="0debe-306">It hides the extra workflow-related columns that we added earlier on the mobile list page.</span></span> <span data-ttu-id="0debe-307">Abbiamo aggiunto le colonne in modo che l'app abbia quelle informazioni nel contesto e possa eseguire il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="0debe-307">We added these columns so that the app has that information in context and can do the next step.</span></span>
    - <span data-ttu-id="0debe-308">In base al passaggio del flusso di lavoro attivo, viene applicata la logica per visualizzare solo queste azioni.</span><span class="sxs-lookup"><span data-stu-id="0debe-308">Based on the workflow step that is active, it applies logic to show only those actions.</span></span>

> [!NOTE]
> <span data-ttu-id="0debe-309">Il nome delle pagine e altri controlli nel codice devono essere gli stessi dell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-309">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

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

2.  <span data-ttu-id="0debe-310">Caricare il file del codice nell'area di lavoro selezionando la scheda **Logica**</span><span class="sxs-lookup"><span data-stu-id="0debe-310">Upload the code file to the workspace by selecting the **Logic** tab</span></span>
3.  <span data-ttu-id="0debe-311">Fare clic su **Fine** per uscire dalla modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="0debe-311">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="0debe-312">Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="0debe-312">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="0debe-313">Fare clic su **Pubblica area di lavoro** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-313">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-attachments"></a><span data-ttu-id="0debe-314">Allegati della fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="0debe-314">Vendor invoice attachments</span></span>

1.  <span data-ttu-id="0debe-315">Fare clic sul pulsante **Impostazioni** (ingranaggio) in alto a destra nella pagina e fare clic su **App per dispositivi mobili**.</span><span class="sxs-lookup"><span data-stu-id="0debe-315">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
2.  <span data-ttu-id="0debe-316">Fare clic sul pulsante **Modifica** per avviare la modalità di modifica nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-316">Click the **Edit** button to start edit mode in the workspace.</span></span>
3.  <span data-ttu-id="0debe-317">Selezionare la pagina  **Invoice details** creata in precedenza quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0debe-317">Select the **Invoice details **page that you created earlier, and then click **Edit**.</span></span>
4.  <span data-ttu-id="0debe-318">Impostare l'opzione **Gestione documenti** su **Sì** come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0debe-318">Set the **Document management** option to **Yes** as shown below.</span></span> <span data-ttu-id="0debe-319">**Nota:** Se non sono presenti esigenze di visualizzare gli allegati sul dispositivo mobile, è possibile lasciare questa opzione impostata su **No**, che è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0debe-319">**Note:** If there are no requirements to show attachments on the mobile device, you can leave this option set to **No**, which is the default setting.</span></span>
<span data-ttu-id="0debe-320">![Gestione documenti](./media/docmanagement-216x300.png)</span><span class="sxs-lookup"><span data-stu-id="0debe-320">![Document management](./media/docmanagement-216x300.png)</span></span>
6.  <span data-ttu-id="0debe-321">Fare clic su **Fine** per uscire dalla modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="0debe-321">Click **Done** to exit edit mode.</span></span>
7.  <span data-ttu-id="0debe-322">Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="0debe-322">Click **Back** and then **Done** to exit the workspace</span></span>
8.  <span data-ttu-id="0debe-323">Fare clic su **Pubblica area di lavoro** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-323">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-line-distributions"></a><span data-ttu-id="0debe-324">Distribuzioni a livello di riga fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="0debe-324">Vendor invoice line distributions</span></span>

<span data-ttu-id="0debe-325">I requisiti di questo scenario confermano che ci saranno solo distribuzioni a livello di riga e che una fattura conterrà sempre una sola riga.</span><span class="sxs-lookup"><span data-stu-id="0debe-325">The requirements for this scenario confirm that there will be only line-level distributions, and that an invoice will always have only one line.</span></span> <span data-ttu-id="0debe-326">Poiché questo scenario è semplice, anche l'esperienza utente sul dispositivo mobile deve essere abbastanza semplice da evitare che l'utente debba eseguire il drill-down di più livelli per visualizzare le distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="0debe-326">Because this scenario is simple, the user experience on the mobile device must also be simple enough that the user doesn’t have to drill down several levels to view the distributions.</span></span> <span data-ttu-id="0debe-327">Le fatture fornitore in Finance and Operations includono l'opzione di mostrare tutte le distribuzioni dall'intestazione della fattura.</span><span class="sxs-lookup"><span data-stu-id="0debe-327">Vendor invoices in Finance and Operations include the option of showing all distributions from the invoice header.</span></span> <span data-ttu-id="0debe-328">Questa esperienza è quello che serve per lo scenario mobile.</span><span class="sxs-lookup"><span data-stu-id="0debe-328">This experience is what we need for the mobile scenario.</span></span> <span data-ttu-id="0debe-329">Di conseguenza, useremo la pagina **VendMobileInvoiceAllDistributionTree** per progettare questa parte dello scenario mobile.</span><span class="sxs-lookup"><span data-stu-id="0debe-329">Therefore, we will use the **VendMobileInvoiceAllDistributionTree** page to design this part of the mobile scenario.</span></span> 

> [!NOTE] 
> <span data-ttu-id="0debe-330">Conoscere i requisiti aiuta a decidere quale pagina specifica utilizzare come esattamente ottimizzare l'esperienza mobile per l'utente nella progettazione dello scenario.</span><span class="sxs-lookup"><span data-stu-id="0debe-330">Knowing the requirements helps us decide which specific page to use and how exactly to optimize the mobile experience for the user when we design the scenario.</span></span> <span data-ttu-id="0debe-331">Nel secondo scenario, useremo una pagina diversa per visualizzare le distribuzioni, poiché i requisiti di quello scenario sono diversi.</span><span class="sxs-lookup"><span data-stu-id="0debe-331">In the second scenario, we will use a different page to show the distributions, because the requirements for that scenario differ.</span></span>

1.  <span data-ttu-id="0debe-332">Nell'URL, sostituire il nome della voce di menu, come fatto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0debe-332">In the URL, replace the name of the menu item, as you did before.</span></span> <span data-ttu-id="0debe-333">Verrà visualizzata una che deve essere simile alla figura seguente.</span><span class="sxs-lookup"><span data-stu-id="0debe-333">The page that appears should resemble the following illustration.</span></span>
<span data-ttu-id="0debe-334">[![Pagina Tutte le distribuzioni](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span><span class="sxs-lookup"><span data-stu-id="0debe-334">[![All distributions page](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span></span>
2.  <span data-ttu-id="0debe-335">Aprire lo strumento di progettazione mobile dal pulsante **Impostazioni** (ingranaggio).</span><span class="sxs-lookup"><span data-stu-id="0debe-335">Open the mobile designer from the **Settings** (gear) button.</span></span>
3.  <span data-ttu-id="0debe-336">Fare clic sul pulsante **Modifica** per avviare la modalità di modifica nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-336">Click the **Edit** button to start edit mode in the workspace.</span></span> <span data-ttu-id="0debe-337">**Nota:**  Vedrete che due pagine sono state create automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0debe-337">**Note:** You will see that two new pages were created automatically.</span></span> <span data-ttu-id="0debe-338">Il sistema crea queste pagine, poiché è stata abilitata la gestione dei documenti nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="0debe-338">The system creates these pages, because you turned on document management in the previous section.</span></span> <span data-ttu-id="0debe-339">È possibile ignorare tali nuove pagine.</span><span class="sxs-lookup"><span data-stu-id="0debe-339">You can ignore these new pages.</span></span>
4.  <span data-ttu-id="0debe-340">Fare clic su **Aggiungi pagina**.</span><span class="sxs-lookup"><span data-stu-id="0debe-340">Click **Add page**.</span></span>
5.  <span data-ttu-id="0debe-341">Immettere un titolo della pagina, ad esempio **View accounting** e una descrizione, ad esempio **View accounting for the invoice**.</span><span class="sxs-lookup"><span data-stu-id="0debe-341">Enter a page title, such as **View accounting**, and a description, such as **View accounting for the invoice**.</span></span>
6.  <span data-ttu-id="0debe-342">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="0debe-342">Click **Done**.</span></span>
7.  <span data-ttu-id="0debe-343">Nella scheda **Campi** fare clic su **Seleziona campi**, selezionare i campi seguenti dalla pagina delle sitribuzioni e fare clic su **Fine**:</span><span class="sxs-lookup"><span data-stu-id="0debe-343">On the **Fields** tab, click **Select fields**, select the following fields from the distributions page, and then click **Done**:</span></span>
    1.  <span data-ttu-id="0debe-344">Importo</span><span class="sxs-lookup"><span data-stu-id="0debe-344">Amount</span></span>
    2.  <span data-ttu-id="0debe-345">Valuta</span><span class="sxs-lookup"><span data-stu-id="0debe-345">Currency</span></span>
    3.  <span data-ttu-id="0debe-346">Conto CoGe</span><span class="sxs-lookup"><span data-stu-id="0debe-346">Ledger account</span></span>

    > [!NOTE] 
    > <span data-ttu-id="0debe-347">Non abbiamo selezionato la colonna **Descrizione** nella griglia di distribuzioni, poiché i requisiti di questo scenario hanno confermato che il prezzo esteso è l'unico importo per cui ci saranno distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="0debe-347">We didn’t select the **Description** column from the distributions grid, because the requirements for this scenario confirmed that the extended price is the only amount that there will be distributions for.</span></span> <span data-ttu-id="0debe-348">Pertanto, l'utente non avrà bisogno di un altro campo per determinare il tipo di importo per cui è la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0debe-348">Therefore, the user won’t require another field to determine the amount type that the distribution is for.</span></span> <span data-ttu-id="0debe-349">Tuttavia, nello scenario successivo, queste informazioni **verranno** utilizzate, poiché i requisiti di quello scenario specificano che altri tipi di importo hanno distribuzioni, ad esempio IVA.</span><span class="sxs-lookup"><span data-stu-id="0debe-349">However, in the next scenario, we **will** use this information, because the requirements for that scenario specify that other amount types have distributions (for example, sales tax).</span></span>
8.  <span data-ttu-id="0debe-350">Fare clic su **Fine** per uscire dalla modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="0debe-350">Click **Done** to exit edit mode.</span></span>
9.  <span data-ttu-id="0debe-351">Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="0debe-351">Click **Back** and then **Done** to exit the workspace</span></span>
10. <span data-ttu-id="0debe-352">Fare clic su **Pubblica area di lavoro** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-352">Click **Publish workspace** to save your work</span></span>

> [!NOTE] 
> <span data-ttu-id="0debe-353">La pagina in versione mobile **Visualizza contabilità** non è attualmente collegata a nessuna delle pagine mobili disponibili progettate fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="0debe-353">The **View accounting** mobile page isn’t currently linked to any of the mobile pages that we have designed so far.</span></span> <span data-ttu-id="0debe-354">Poiché l'utente deve poter accedere alla pagina **Visualizza contabilità** dalla pagina **Dettagli fattura** sul dispositivo mobile, dobbiamo specificare lo spostamento dalla pagina **Dettagli fattura** alla pagina **Visualizza contabilità** .</span><span class="sxs-lookup"><span data-stu-id="0debe-354">Because the user should be able to navigate to the **View accounting** page from the **Invoice details** page on the mobile device, we must provide navigation from the **Invoice details** page to the **View accounting** page.</span></span> <span data-ttu-id="0debe-355">Stabiliamo questo spostamento utilizzando la logica aggiuntiva tramite JavaScript.</span><span class="sxs-lookup"><span data-stu-id="0debe-355">We establish this navigation by using additional logic via JavaScript.</span></span>

1.  <span data-ttu-id="0debe-356">Apre il file .js creato in precedenza e aggiungere le righe che vengono evidenziate nel codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0debe-356">Open the .js file that you created earlier, and add the lines that are highlighted in the following code.</span></span> <span data-ttu-id="0debe-357">Questo codice fa due cose:</span><span class="sxs-lookup"><span data-stu-id="0debe-357">This code does two things:</span></span>
    1.  <span data-ttu-id="0debe-358">Aiuta a garantire che gli utenti non possono accedere direttamente dall'area di lavoro alla pagina **View accounting**.</span><span class="sxs-lookup"><span data-stu-id="0debe-358">It helps guarantee that users can’t navigate directly from the workspace to the **View accounting** page.</span></span>
    2.  <span data-ttu-id="0debe-359">Stabilisce un controllo di spostamento dalla pagina **Invoice details** alla pagina **View accounting**.</span><span class="sxs-lookup"><span data-stu-id="0debe-359">It establishes a navigation control from the **Invoice details** page to the **View accounting** page.</span></span>

> [!NOTE] 
> <span data-ttu-id="0debe-360">Il nome delle pagine e altri controlli nel codice devono essere gli stessi dell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-360">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

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

2.  <span data-ttu-id="0debe-361">Caricare il file del codice nell'area di lavoro selezionando la scheda **Logica** per sovrascrivere il codice precedente</span><span class="sxs-lookup"><span data-stu-id="0debe-361">Upload the code file to the workspace by selecting the **Logic** tab to overwrite the previous code</span></span>
3.  <span data-ttu-id="0debe-362">Fare clic su **Fine** per uscire dalla modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="0debe-362">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="0debe-363">Fare clic su **Indietro** e quindi su **Fine** per uscire dall'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="0debe-363">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="0debe-364">Fare clic su **Pubblica area di lavoro** per salvare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-364">Click **Publish workspace** to save your work</span></span>

### <a name="validation"></a><span data-ttu-id="0debe-365">Convalida</span><span class="sxs-lookup"><span data-stu-id="0debe-365">Validation</span></span>

<span data-ttu-id="0debe-366">Dal dispositivo mobile, aprire l'app e connettersi all'istanza di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0debe-366">From your mobile device, open the app, and connect to your Finance and Operations instance.</span></span> <span data-ttu-id="0debe-367">Verificare di accedere alla società in cui le fatture fornitore sono assegnate a se stessi per la revisione.</span><span class="sxs-lookup"><span data-stu-id="0debe-367">Make sure that you sign in to the company where vendor invoices are assigned to you for review.</span></span> <span data-ttu-id="0debe-368">Dovrebbe esssere possibile eseguire le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="0debe-368">You should be able to perform the following actions:</span></span>

-   <span data-ttu-id="0debe-369">Vedere l'area di lavoro **My approvals**.</span><span class="sxs-lookup"><span data-stu-id="0debe-369">See the **My approvals** workspace.</span></span>
-   <span data-ttu-id="0debe-370">Analizzare l'area di lavoro **My approvals** e vedere la pagina **My vendor invoices**.</span><span class="sxs-lookup"><span data-stu-id="0debe-370">Drill into the **My approvals** workspace and see the **My vendor invoices** page.</span></span>
-   <span data-ttu-id="0debe-371">Analizzare la pagina **My vendor invoices** e visualizzare l'elenco delle fatture assegnate all'utente.</span><span class="sxs-lookup"><span data-stu-id="0debe-371">Drill into the **My vendor invoices** page and see the list of invoices that are assigned to you.</span></span>
-   <span data-ttu-id="0debe-372">Analizzare una delle fatture e visualizzare i dettagli dell'intestazione della fattura e delle righe.</span><span class="sxs-lookup"><span data-stu-id="0debe-372">Drill into one of the invoices, and see the invoice header details and line details.</span></span>
-   <span data-ttu-id="0debe-373">Nella pagina dei dettagli, vedere un collegamento agli allegati e utilizzare questo collegamento per spostarsi all'elenco degli allegati e visualizzare gli allegati.</span><span class="sxs-lookup"><span data-stu-id="0debe-373">On the details page, see a link to attachments, and use this link to navigate to the attachments list and view the attachments.</span></span>
-   <span data-ttu-id="0debe-374">Nella pagina dei dettagli, vedere un collegamento alla pagina **View accounting** e utilizzare questo collegamento per spostarsi alla pagina delle distribuzioni e visualizzare le distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="0debe-374">On the details page, see a link to the **View accounting** page, and use this link to navigate to the distributions page and view the distributions.</span></span>
-   <span data-ttu-id="0debe-375">Nella pagina dei dettagli, fare clic sul menu **Azioni** nella parte inferiore ed eseguire le azioni del flusso di lavoro applicabili al passaggio del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0debe-375">On the details page, click the **Actions** menu at the bottom, and perform workflow actions that are applicable to the workflow step.</span></span>

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a><span data-ttu-id="0debe-376">Progettazione di uno scenario complesso di approvazione fatture per Fabrikam</span><span class="sxs-lookup"><span data-stu-id="0debe-376">Designing a complex invoice approval scenario for Fabrikam</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0debe-377">Attributo scenario</span><span class="sxs-lookup"><span data-stu-id="0debe-377">Scenario attribute</span></span></th>
<th><span data-ttu-id="0debe-378">Risposta</span><span class="sxs-lookup"><span data-stu-id="0debe-378">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0debe-379">Quali campi dall'intestazione fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</span><span class="sxs-lookup"><span data-stu-id="0debe-379">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="0debe-380">Nome fornitore</span><span class="sxs-lookup"><span data-stu-id="0debe-380">Vendor name</span></span></li>
<li><span data-ttu-id="0debe-381">Importo fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-381">Invoice amount</span></span></li>
<li><span data-ttu-id="0debe-382">Conto fatture</span><span class="sxs-lookup"><span data-stu-id="0debe-382">Invoice account</span></span></li>
<li><span data-ttu-id="0debe-383">Numero fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-383">Invoice number</span></span></li>
<li><span data-ttu-id="0debe-384">Data fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-384">Invoice date</span></span></li>
<li><span data-ttu-id="0debe-385">Descrizione fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-385">Invoice description</span></span></li>
<li><span data-ttu-id="0debe-386">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="0debe-386">Due date</span></span></li>
<li><span data-ttu-id="0debe-387">Valuta della fattura</span><span class="sxs-lookup"><span data-stu-id="0debe-387">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0debe-388">Quali campi delle righe fattura l'utente vorrà visualizzare nell'esperienza mobile e in che ordine?</span><span class="sxs-lookup"><span data-stu-id="0debe-388">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="0debe-389">Categoria di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="0debe-389">Procurement category</span></span></li>
<li><span data-ttu-id="0debe-390">Quantità</span><span class="sxs-lookup"><span data-stu-id="0debe-390">Quantity</span></span></li>
<li><span data-ttu-id="0debe-391">Prezzo unitario</span><span class="sxs-lookup"><span data-stu-id="0debe-391">Unit price</span></span></li>
<li><span data-ttu-id="0debe-392">Importo netto riga</span><span class="sxs-lookup"><span data-stu-id="0debe-392">Line net amount</span></span></li>
<li><span data-ttu-id="0debe-393">Importo 1099</span><span class="sxs-lookup"><span data-stu-id="0debe-393">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0debe-394">Quante righe fattura sono presenti in una fattura?</span><span class="sxs-lookup"><span data-stu-id="0debe-394">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="0debe-395">Applicare la regola 80-20 qui e ottimizzare per l'80%.</span><span class="sxs-lookup"><span data-stu-id="0debe-395">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="0debe-396">5</span><span class="sxs-lookup"><span data-stu-id="0debe-396">5</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0debe-397">Gli utenti vorranno visualizzare le distribuzioni contabili (codifica della fattura) sul dispositivo mobile nelle revisioni?</span><span class="sxs-lookup"><span data-stu-id="0debe-397">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="0debe-398">Sì</span><span class="sxs-lookup"><span data-stu-id="0debe-398">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0debe-399">Quante distribuzioni contabili (prezzo esteso, IVA, spese e così via) esistono per una riga della fattura?</span><span class="sxs-lookup"><span data-stu-id="0debe-399">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="0debe-400">Anche in questo caso, applicare la regola 80-20.</span><span class="sxs-lookup"><span data-stu-id="0debe-400">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="0debe-401">Prezzo esteso: 2 IVA: 2 Spese: 2</span><span class="sxs-lookup"><span data-stu-id="0debe-401">Extended price: 2 Sales tax: 2 Charges: 2</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0debe-402">Le fatture hanno distribuzioni contabili anche nell'intestazione?</span><span class="sxs-lookup"><span data-stu-id="0debe-402">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="0debe-403">In tal caso, queste distribuzioni contabili devono essere disponibili sul dispositivo?</span><span class="sxs-lookup"><span data-stu-id="0debe-403">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="0debe-404">Non utilizzato</span><span class="sxs-lookup"><span data-stu-id="0debe-404">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0debe-405">Gli utenti vorranno visualizzare gli allegati della fattura sul dispositivo?</span><span class="sxs-lookup"><span data-stu-id="0debe-405">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="0debe-406">Sì</span><span class="sxs-lookup"><span data-stu-id="0debe-406">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a><span data-ttu-id="0debe-407">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0debe-407">Next steps</span></span>

<span data-ttu-id="0debe-408">Le variazioni seguenti possono essere effettuate per lo scenario 1, in base ai requisiti dello scenario 2.</span><span class="sxs-lookup"><span data-stu-id="0debe-408">The following variations can be done for scenario 1, based on the requirements for scenario 2.</span></span> <span data-ttu-id="0debe-409">È possibile utilizzare questa sezione migliorare l'esperienza con l'app mobile.</span><span class="sxs-lookup"><span data-stu-id="0debe-409">You can use this section to improve your mobile app experience.</span></span>

1.  <span data-ttu-id="0debe-410">Poiché più righe fattura sono previste nello scenario 2, le seguenti modifiche alla progettazione aiuteranno a ottimizzare l'esperienza utente sul dispositivo mobile:</span><span class="sxs-lookup"><span data-stu-id="0debe-410">Because more invoice lines are expected in scenario 2, the following changes to the design will help optimize the user experience on the mobile device:</span></span>
    1.  <span data-ttu-id="0debe-411">Anziché visualizzare le righe fattura nella pagina dei dettagli (come nello scenario 1), gli utenti possono scegliere di visualizzare le righe in una pagina in versione mobile separata.</span><span class="sxs-lookup"><span data-stu-id="0debe-411">Instead of viewing invoice lines on the details page (as in scenario 1), users can choose to view lines on a separate mobile page.</span></span>
    2.  <span data-ttu-id="0debe-412">Poiché più righe fattura sono previste in questo scenario, se la pagina **VendMobileInvoiceAllDistributionTree** viene utilizzata per progettare la pagina delle distribuzioni per l'ambiente mobile (come nello scenario 1), potrebbe confondere l'utente correlare le righe alle distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="0debe-412">Because more than one invoice line is expected in this scenario, if the **VendMobileInvoiceAllDistributionTree** page is used to design the distributions page for mobile (as in scenario 1), it might be confusing for the user to correlate lines to distributions.</span></span> <span data-ttu-id="0debe-413">Di conseguenza, utilizzare la pagina **VendMobileInvoiceLineDistributionTree** per progettare la pagina delle distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="0debe-413">Therefore, use the **VendMobileInvoiceLineDistributionTree** page to design the distributions page.</span></span>
    3.  <span data-ttu-id="0debe-414">A livello ideale, le distribuzioni devono essere visualizzate nel contesto di una riga della fattura in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="0debe-414">Ideally, the distributions should be shown in the context of an invoice line in this scenario.</span></span> <span data-ttu-id="0debe-415">Di conseguenza, assicurarsi che l'utente possa eseguire il drill-down in una riga per visualizzare la pagina delle distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="0debe-415">Therefore, make sure that the user can drill into a line to see the distributions page.</span></span> <span data-ttu-id="0debe-416">Utilizzare la funzionalità di collegamento pagina per stabilire il drill-through, esattamente come fatto per l'intestazione e le pagine dei dettagli nello scenario 1.</span><span class="sxs-lookup"><span data-stu-id="0debe-416">Use the page link capability to establish the drill-through, just as you did for the header and details pages in scenario 1.</span></span>

2.  <span data-ttu-id="0debe-417">Poiché sono previsti più tipi di importo nelle distribuzioni nello scenario 2 (IVA, spese e così via), sarà utile visualizzare la descrizione del tipo di importo.</span><span class="sxs-lookup"><span data-stu-id="0debe-417">Because more than one amount type is expected on the distributions in scenario 2 (sales tax, charges, and so on), it will be useful to show the description of the amount type.</span></span> <span data-ttu-id="0debe-418">(Abbiamo omesso queste informazioni nello scenario 1).</span><span class="sxs-lookup"><span data-stu-id="0debe-418">(We omitted this information in scenario 1.)</span></span>





