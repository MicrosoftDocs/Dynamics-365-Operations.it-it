---
title: Novità o modifiche in Dynamics 365 for Talent (6 maggio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c541bac532e878c8493a60d95c05c9104d4b96e1
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741546"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-may-6-2019"></a><span data-ttu-id="48073-103">Novità o modifiche in Dynamics 365 for Talent (6 maggio 2019)</span><span class="sxs-lookup"><span data-stu-id="48073-103">What's new or changed in Dynamics 365 for Talent (May 6, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="48073-104">Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="48073-104">This topic describes features that are either new or changed in Dynamics 365 for Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="48073-105">Modifiche in Attract</span><span class="sxs-lookup"><span data-stu-id="48073-105">Changes in Attract</span></span>

### <a name="select-optional-documents-upon-offer-creation"></a><span data-ttu-id="48073-106">Selezione di documenti facoltativi durante la creazione di offerta</span><span class="sxs-lookup"><span data-stu-id="48073-106">Select optional documents upon offer creation</span></span>

<span data-ttu-id="48073-107">Quando si seleziona un modello di pacchetto di offerta, Attract ora richiede di selezionare i documenti facoltativi applicabili dal modello di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="48073-107">When you select an offer package template, Attract now prompts you to select the applicable, optional documents from that package template.</span></span> <span data-ttu-id="48073-108">È possibile aggiungere altri documenti come facoltativi mentre si prepara l'offerta.</span><span class="sxs-lookup"><span data-stu-id="48073-108">You can add other optional documents while preparing the offer.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="48073-109">Modifiche in Onboard</span><span class="sxs-lookup"><span data-stu-id="48073-109">Changes in Onboard</span></span>

<span data-ttu-id="48073-110">Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="48073-110">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="48073-111">Modifiche di Core HR</span><span class="sxs-lookup"><span data-stu-id="48073-111">Changes in Core HR</span></span>

<span data-ttu-id="48073-112">Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2282.</span><span class="sxs-lookup"><span data-stu-id="48073-112">Changes described in this section apply to build number 8.1.2282.</span></span> <span data-ttu-id="48073-113">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="48073-113">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="platform-update-26"></a><span data-ttu-id="48073-114">Update 26 della piattaforma</span><span class="sxs-lookup"><span data-stu-id="48073-114">Platform update 26</span></span>

<span data-ttu-id="48073-115">Per ulteriori dettagli sull'aggiornamento 26 della piattaforma, vedere [Funzionalità di anteprima nell'aggiornamento 26 della piattaforma Dynamics 365 for Finance and Operations (giugno 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26).</span><span class="sxs-lookup"><span data-stu-id="48073-115">For additional details about Platform update 26, see [Preview features in Dynamics 365 for Finance and Operations platform update 26 (May 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26).</span></span> 

### <a name="common-data-service-entity-support-for-custom-fields"></a><span data-ttu-id="48073-116">Support dell'entità Common Data Service per i campi personalizzati</span><span class="sxs-lookup"><span data-stu-id="48073-116">Common Data Service entity support for custom fields</span></span>

<span data-ttu-id="48073-117">Nella versione di questa settimana, le seguenti entità supportano i campi personalizzati: Frequenza calcolo benefit, Velocità calcolo benefit, Tipo di benefit, Calendario di lavoro, Vacanze del calendario di lavoro, Ciclo retributivo e Tipi di identificazione del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="48073-117">In this week's release, the following entities now support custom fields: Benefit calc frequency, Benefit calc rate, Benefit type, Work calendar, Work calendar holiday, Pay cycle, and Worker identification types.</span></span>

### <a name="leave-mass-enrollment-changing-the-tier-basis-to-seniority-date-doesnt-refresh-the-initial-accrual-rate-318526"></a><span data-ttu-id="48073-118">Lasciare l'iscrizione collettiva, cambiando la base di livello in "Data di anzianità" non aggiorna il coefficiente di accumulo iniziale (318526)</span><span class="sxs-lookup"><span data-stu-id="48073-118">Leave mass enrollment, changing the tier basis to "Seniority date" doesn't refresh the initial accrual rate (318526)</span></span>

<span data-ttu-id="48073-119">Quando si registrano in massa dipendenti e si modifica la base di livello, il coefficiente di accumulo iniziale riflette ora la base di livello selezionata.</span><span class="sxs-lookup"><span data-stu-id="48073-119">When you mass enroll employees and change the tier basis, the initial accrual now reflects the tier basis that you selected.</span></span>

### <a name="workflow-showing-duplicate-place-holders-313636"></a><span data-ttu-id="48073-120">Flusso di lavoro con segnaposti duplicati (313636)</span><span class="sxs-lookup"><span data-stu-id="48073-120">Workflow showing duplicate place holders (313636)</span></span>

<span data-ttu-id="48073-121">Le modifiche apportate a questa versione eliminano la duplicazione dei segnaposto quando vengono inviate notifiche del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="48073-121">Changes in this release eliminate duplication of placeholders when workflow notifications are sent.</span></span>

### <a name="dimension-fields-arent-updated-when-using-open-in-excel-176261"></a><span data-ttu-id="48073-122">I campi relativi alle dimensioni non vengono aggiornati quando si utilizza "Apri in Excel" (176261)</span><span class="sxs-lookup"><span data-stu-id="48073-122">Dimension fields aren't updated when using "Open in Excel" (176261)</span></span>

<span data-ttu-id="48073-123">Con questa versione, è ora possibile aggiornare la dimensione finanziaria utilizzando **Apri in Excel** dalla pagina **Lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="48073-123">With this release, you can now update financial dimension using **Open in Excel** from the **Worker** page.</span></span> 

### <a name="worker-address-created-in-common-data-service-isnt-synced-to-talent-317555"></a><span data-ttu-id="48073-124">L'indirizzo del lavoratore creato in Common Data Service non viene sincronizzato in Talent (317555)</span><span class="sxs-lookup"><span data-stu-id="48073-124">Worker address created in Common Data Service isn't synced to Talent (317555)</span></span>

<span data-ttu-id="48073-125">Con questa modifica, gli indirizzi creati Common Data Service vengono aggiornati in Talent Core HR.</span><span class="sxs-lookup"><span data-stu-id="48073-125">With this change, addresses created in Common Data Service are updated in Talent Core HR.</span></span>


## <a name="in-preview"></a><span data-ttu-id="48073-126">In anteprima</span><span class="sxs-lookup"><span data-stu-id="48073-126">In preview</span></span>

### <a name="new-page-to-validate-position-hierarchy-data"></a><span data-ttu-id="48073-127">Nuova pagina per convalidare i dati della gerarchia di posizioni</span><span class="sxs-lookup"><span data-stu-id="48073-127">New page to validate position hierarchy data</span></span>

<span data-ttu-id="48073-128">Le risorse umane (HR) e gli amministratori possono ora convalidare la gerarchia manageriale per tutti i riferimenti circolari che potrebbero essere stati inavvertitamente importati.</span><span class="sxs-lookup"><span data-stu-id="48073-128">Human resources (HR) and administrators can now validate the managerial hierarchy for any circular references that might have inadvertently been imported.</span></span> <span data-ttu-id="48073-129">È possibile accedere a questa nuova pagina da **Amministrazione organizzazione > Collegamenti> Posizioni> Convalida gerarchia posizioni**.</span><span class="sxs-lookup"><span data-stu-id="48073-129">You can access this new page from **Organizational administration > Links > Positions > Position hierarchy validation**.</span></span>

### <a name="specify-reason-codes-on-leave-types"></a><span data-ttu-id="48073-130">Specificare i codici motivo per i tipi di congedo</span><span class="sxs-lookup"><span data-stu-id="48073-130">Specify reason codes on leave types</span></span>

<span data-ttu-id="48073-131">Le organizzazioni potrebbero richiedere informazioni aggiuntive per le richieste di permesso.</span><span class="sxs-lookup"><span data-stu-id="48073-131">Organizations might require additional information about time-off requests.</span></span> <span data-ttu-id="48073-132">Ora è possibile specificare i codici motivo per i tipi di congedo e consentire ai dipendenti di selezionare un codice motivo nelle relative richieste di permesso.</span><span class="sxs-lookup"><span data-stu-id="48073-132">You can now specify reason codes for leave types and let employees select a reason code on their time-off requests.</span></span>

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a><span data-ttu-id="48073-133">Richiedere codici motivo per tipi di congedo specifici nelle richieste di permesso</span><span class="sxs-lookup"><span data-stu-id="48073-133">Require reason codes for specific leave types on time-off requests</span></span>

<span data-ttu-id="48073-134">Le organizzazioni potrebbero richiedere codici motivo per determinati tipi di congedo quando i dipendenti inviano richieste di permesso.</span><span class="sxs-lookup"><span data-stu-id="48073-134">Organizations might require reason codes for specific leave types when employees submit time-off requests.</span></span> <span data-ttu-id="48073-135">Questo requisito potrebbe esistere a causa di criteri aziendali o requisiti normativi.</span><span class="sxs-lookup"><span data-stu-id="48073-135">This requirement might exist because of company policy or regulatory requirements.</span></span> <span data-ttu-id="48073-136">Ora è possibile specificare quali tipi di congedo richiedono un codice motivo ed è possibile richiedere ai dipendenti di fornire un codice motivo per il tipo di congedo nelle relative richieste di permesso.</span><span class="sxs-lookup"><span data-stu-id="48073-136">You can now specify which leave types require a reason code, and you can require that employees provide a reason code for the leave type on their time-off requests.</span></span>

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a><span data-ttu-id="48073-137">Fornire un elenco di transazioni assenze e congedo per le Risorse umane</span><span class="sxs-lookup"><span data-stu-id="48073-137">Provide a leave and absence transaction list for HR</span></span>

<span data-ttu-id="48073-138">La possibilità di tracciare il tempo libero dei dipendenti e analizzare come tale tempo viene calcolato non solo consente alle Risorse umane di rispondere alle domande dei dipendenti, ma anche di garantire premi appropriati per i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="48073-138">The ability to track employee time off and understand how time off is calculated not only helps HR answer employee questions, but also helps ensure accurate time-off awards for employees.</span></span> <span data-ttu-id="48073-139">Ora le Risorse umane hanno una nuova visibilità sulle transazioni (concessioni, accumuli, rettifiche e richieste) in modo da poter determinare i motivi dei saldi.</span><span class="sxs-lookup"><span data-stu-id="48073-139">HR now has a new view into the transactions (grants, accruals, adjustments, and requests), so that HR staff can view the reasons behind balances.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="48073-140">Presto disponibili</span><span class="sxs-lookup"><span data-stu-id="48073-140">Coming soon</span></span>

### <a name="indicate-instance-type-when-provisioning-talent"></a><span data-ttu-id="48073-141">Indicare il tipo di istanza durante il provisioning di Talent</span><span class="sxs-lookup"><span data-stu-id="48073-141">Indicate instance type when provisioning Talent</span></span>

<span data-ttu-id="48073-142">Quando si esegue il provisioning di una nuova istanza di Talent, è possibile indicare se il tipo di istanza è **Produzione** o **Sandbox**, consentendo il test iniziale di nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="48073-142">When provisioning a new instance of Talent, you will be able to indicate whether the instance type is **Production** or **Sandbox**, allowing for early testing of new features.</span></span> <span data-ttu-id="48073-143">Tutte le istanze Talent esistenti verranno aggiornate al tipo di istanza di produzione.</span><span class="sxs-lookup"><span data-stu-id="48073-143">All existing Talent instances will be updated to the Production instance type.</span></span> <span data-ttu-id="48073-144">Se si desidera aggiornare una delle istanze esistenti al tipo di istanza di Sandbox, contattare il supporto tecnico per avviare la richiesta di modifica.</span><span class="sxs-lookup"><span data-stu-id="48073-144">If you want one of your existing instances to be updated to the Sandbox instance type, please contact Support to initiate the change request.</span></span>
