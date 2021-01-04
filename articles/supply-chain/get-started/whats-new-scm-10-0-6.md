---
title: Novità o modifiche in Dynamics 365 Supply Chain Management 10.0.6 (novembre 2019)
description: Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Supply Chain Management 10.0.6.
author: josaw1
manager: tfehr
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 9ee25036488d2f7f24c1691d36239f3f34caf0cb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431197"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a><span data-ttu-id="8198c-103">Novità o modifiche in Dynamics 365 Supply Chain Management 10.0.6 (novembre 2019)</span><span class="sxs-lookup"><span data-stu-id="8198c-103">What's new or changed in Dynamics 365 Supply Chain Management 10.0.6 (November 2019)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8198c-104">Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management 10.0.6.</span><span class="sxs-lookup"><span data-stu-id="8198c-104">This topic describes features that are either new or changed in Microsoft Dynamics 365 Supply Chain Management 10.0.6.</span></span> <span data-ttu-id="8198c-105">Questa versione ha il numero di build 10.0.234.</span><span class="sxs-lookup"><span data-stu-id="8198c-105">This version has a build number of 10.0.234.</span></span> <span data-ttu-id="8198c-106">Mentre la data di disponibilità generale è a novembre, le nuove funzionalità sono disponibili per la versione anticipata a ottobre.</span><span class="sxs-lookup"><span data-stu-id="8198c-106">While the general availability date is in November, the new features are available for early release in October.</span></span> <span data-ttu-id="8198c-107">Per ulteriori informazioni sulla versione 10.0.6, veder [Risorse aggiuntive](whats-new-scm-10-0-6.md#additional-resources).</span><span class="sxs-lookup"><span data-stu-id="8198c-107">For more information about version 10.0.6, see [Additional resources](whats-new-scm-10-0-6.md#additional-resources).</span></span>

## <a name="product-configuration-models-v2-data-entity"></a><span data-ttu-id="8198c-108">Entità di dati modelli di configurazione prodotto V2</span><span class="sxs-lookup"><span data-stu-id="8198c-108">Product configuration models V2 data entity</span></span>

<span data-ttu-id="8198c-109">Viene rilasciata una seconda versione per l'entità di dati "Modelli di configurazione prodotto" (denominata "Modelli di configurazione prodotto V2").</span><span class="sxs-lookup"><span data-stu-id="8198c-109">A second version for the "product configuration models" data entity is released (called "products configuration models V2").</span></span> <span data-ttu-id="8198c-110">Il modello predefinito "Modelli di configurazione prodotto 418" deve essere tale da utilizzare l'entità dati "Modelli di configurazione prodotto V2" nei modelli di framework di importazione/esportazione.</span><span class="sxs-lookup"><span data-stu-id="8198c-110">The default template "418-product configuration models" is also needs to be so that it uses the new "product configuration models V2" data entity in the import/export framework templates.</span></span> <span data-ttu-id="8198c-111">Il modello non verrà aggiornato automaticamente, quindi è necessario caricarlo manualmente dal valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="8198c-111">The template will not be auto-updated so that you will have to load the template from the default manually.</span></span> <span data-ttu-id="8198c-112">L'entità V2 esporta una riga come file separato in un allegato anziché in linea, risolvendo i limiti di dimensione dell'entità V1.</span><span class="sxs-lookup"><span data-stu-id="8198c-112">The V2 entity exports one row as separate file in an attachment instead of inline, solving the size limitations of the V1 entity.</span></span> 
 
<span data-ttu-id="8198c-113">Cosa è necessario fare per ottenere questo cambiamento?</span><span class="sxs-lookup"><span data-stu-id="8198c-113">What do you need to do to take this change?</span></span>
-    <span data-ttu-id="8198c-114">Poiché l'entità V1 è stata deprecata, è necessario iniziare la migrazione da V1 a V2.</span><span class="sxs-lookup"><span data-stu-id="8198c-114">As the V1 entity has been deprecated, you should start migrating from V1 to V2.</span></span> <span data-ttu-id="8198c-115">Se si utilizza il modello "Modelli di configurazione prodotto 418", è possibile fare clic sul pulsante "Carica modelli predefiniti" e ricaricare il modello "418 - Modelli di configurazione del prodotto"</span><span class="sxs-lookup"><span data-stu-id="8198c-115">If you are using the  "418-product configuration models" template, you can click on "load default templates" button and reload the template "418 – product configuration models"</span></span>
-    <span data-ttu-id="8198c-116">Se è necessario mantenere la compatibilità con i sistemi esistenti, per ora è possibile continuare a utilizzare il modello esistente e l'entità (deprecata) V1 fino a quando non si spostano le integrazioni nel nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="8198c-116">If you need to keep compatibility with existing systems, you can for now continue using the existing template and the (deprecated) V1 entity until you move your integrations to the new template.</span></span> 

## <a name="feature-management-enhancements"></a><span data-ttu-id="8198c-117">Miglioramenti di gestione delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="8198c-117">Feature management enhancements</span></span>
<span data-ttu-id="8198c-118">La gestione delle funzionalità ora consente di abilitare tutte le nuove funzionalità per impostazione predefinita, richiedere la conferma per abilitare una funzionalità e abilitare tutte le funzionalità che non sono già state abilitate.</span><span class="sxs-lookup"><span data-stu-id="8198c-118">Feature management now allows you to enable all new features by default, require confirmation to enable a feature, and enable all features that have not already been enabled.</span></span> 


## <a name="purchase-agreement-responsible-party"></a><span data-ttu-id="8198c-119">Parte responsabile del contratto di acquisto</span><span class="sxs-lookup"><span data-stu-id="8198c-119">Purchase agreement responsible party</span></span>
<span data-ttu-id="8198c-120">Ora è possibile definire le parti responsabili primarie e secondarie nel modulo di classificazione del contratto di acquisto e nei contratti di acquisto risultanti.</span><span class="sxs-lookup"><span data-stu-id="8198c-120">You now have the ability to define primary and secondary responsible parties on the Purchase agreement classification form and resulting Purchase agreements.</span></span>  <span data-ttu-id="8198c-121">Ciò fornisce all'utente l'accesso a chi supervisiona i contatti.</span><span class="sxs-lookup"><span data-stu-id="8198c-121">This provides the user access to who oversees the agreements.</span></span>

## <a name="rfq-link-on-the-purchase-order-line"></a><span data-ttu-id="8198c-122">Collegamento RdO nella riga ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="8198c-122">RFQ link on the Purchase order line</span></span>
<span data-ttu-id="8198c-123">È possibile aggiungere un collegamento di riferimento dalle righe dell'ordine fornitore alle righe RdO corrispondenti da cui hanno origine, consentendo all'utente di ricevere facilmente la richiesta di supporto per il documento di offerta.</span><span class="sxs-lookup"><span data-stu-id="8198c-123">You can add a reference link from the Purchase order lines back to the corresponding RFQ lines they originated from, allowing the user to easily be provided with the supporting request for quotation document.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8198c-124">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8198c-124">Additional resources</span></span>

### <a name="bug-fixes"></a><span data-ttu-id="8198c-125">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="8198c-125">Bug fixes</span></span>
<span data-ttu-id="8198c-126">Per informazioni sulle correzioni di bug incluse in ciascuno degli aggiornamenti che fanno parte di 10.0.6, accedere a Lifecycle Services (LCS) e visualizzare l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).</span><span class="sxs-lookup"><span data-stu-id="8198c-126">For information about the bug fixes included in each of the updates that are part of 10.0.6, sign in to Lifecycle Services (LCS) and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).</span></span>

### <a name="platform-update-30"></a><span data-ttu-id="8198c-127">Update 30 della piattaforma</span><span class="sxs-lookup"><span data-stu-id="8198c-127">Platform update 30</span></span>
<span data-ttu-id="8198c-128">Microsoft Dynamics 365 Supply Chain Management 10.0.6 include l'aggiornamento della piattaforma 30.</span><span class="sxs-lookup"><span data-stu-id="8198c-128">Microsoft Dynamics 365 Supply Chain Management 10.0.6 includes Platform update 30.</span></span> <span data-ttu-id="8198c-129">Per ulteriori informazioni sull'aggiornamento 30 della piattaforma, vedere [Novità o modifiche nell'aggiornamento 30 della piattaforma](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).</span><span class="sxs-lookup"><span data-stu-id="8198c-129">To learn more about Platform update 30, see [What's new or changed in Platform update 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).</span></span>

### <a name="dynamics-365-2019-release-wave-2-plan"></a><span data-ttu-id="8198c-130">Piano di rilascio della seconda ondata 2019 di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8198c-130">Dynamics 365: 2019 release wave 2 plan</span></span>
<span data-ttu-id="8198c-131">Desideri sapere quali sono le funzionalità imminenti e rilasciate di recente nella nostra piattaforma o in una delle app aziendali?</span><span class="sxs-lookup"><span data-stu-id="8198c-131">Wondering about upcoming and recently released capabilities in any of our business apps or platform?</span></span>

<span data-ttu-id="8198c-132">Consultare il [piano di rilascio della seconda ondata 2019 di Dynamics 365](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/).</span><span class="sxs-lookup"><span data-stu-id="8198c-132">Check out the [Dynamics 365: 2019 release wave 2 plan](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/).</span></span> <span data-ttu-id="8198c-133">Tutti i dettagli più completi sono stati raccolti in un unico documento utilizzabile per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8198c-133">We've captured all the details, end to end, top to bottom, in a single document that you can use for planning.</span></span>

### <a name="removed-and-deprecated-supply-chain-management-features"></a><span data-ttu-id="8198c-134">Funzionalità di Supply Chain Management rimosse e deprecate</span><span class="sxs-lookup"><span data-stu-id="8198c-134">Removed and deprecated Supply Chain Management features</span></span>

<span data-ttu-id="8198c-135">L'argomento [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descrive le funzionalità che sono state o sono pianificate per essere rimosse o deprecate per Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8198c-135">The [Removed or deprecated features in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) topic describes features that have been or are scheduled to be removed or deprecated for Supply Chain Management.</span></span>

- <span data-ttu-id="8198c-136">Una funzionalità *rimossa* non è più disponibile nel prodotto.</span><span class="sxs-lookup"><span data-stu-id="8198c-136">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="8198c-137">Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.</span><span class="sxs-lookup"><span data-stu-id="8198c-137">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="8198c-138">Prima che qualsiasi funzionalità venga rimossa dal prodotto, l'avviso di deprecazione verrà annunciato nell'argomento [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mesi prima della rimozione.</span><span class="sxs-lookup"><span data-stu-id="8198c-138">Before any feature is removed from the product, the deprecation notice will be announced in the [Removed or deprecated features in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) topic 12 months prior to the removal.</span></span>

<span data-ttu-id="8198c-139">Per le modifiche significative che influiscono solo sui tempi di compilazione, ma che sono binari compatibili con sandbox e ambienti di produzione, il tempo di deprecazione sarà inferiore a 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="8198c-139">For breaking changes that only affect compilation time, but are binary compatible with sandbox and production environments, the deprecation time will be less than 12 months.</span></span> <span data-ttu-id="8198c-140">In genere, si tratta di aggiornamenti funzionali che è necessario apportare al compilatore.</span><span class="sxs-lookup"><span data-stu-id="8198c-140">Typically, these are functional updates that need to be made to the compiler.</span></span>
