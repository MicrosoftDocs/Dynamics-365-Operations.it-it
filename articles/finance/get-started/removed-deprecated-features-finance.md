---
title: Funzionalità rimosse o deprecate in Dynamics 365 Finance
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Dynamics 365 Finance.
author: roschlom
manager: AnnBe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: aebce032d7d780b296ba74fea4467425a3cbe1a7
ms.sourcegitcommit: 4e9b3746790355f9f72bbfddc099c4065a49ad63
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "3175110"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a><span data-ttu-id="6e22c-103">Funzionalità rimosse o deprecate in Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="6e22c-103">Removed or deprecated features in Dynamics 365 Finance</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6e22c-104">In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="6e22c-104">This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Finance.</span></span>

- <span data-ttu-id="6e22c-105">Una funzionalità *rimossa* non è più disponibile nel prodotto.</span><span class="sxs-lookup"><span data-stu-id="6e22c-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="6e22c-106">Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.</span><span class="sxs-lookup"><span data-stu-id="6e22c-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="6e22c-107">Questo elenco ha lo scopo di aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="6e22c-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="6e22c-108">Informazioni dettagliate sugli oggetti nella app Finance and Operations sono disponibili nei [Report tecnici di riferimento](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="6e22c-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="6e22c-109">È possibile confrontare le diverse versioni dei report per ottenere informazioni sugli oggetti che sono stati modificati o rimossi in ogni versione delle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6e22c-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a><span data-ttu-id="6e22c-110">Funzionalità rimosse o deprecate nella versione Finance and Operations 10.0.12</span><span class="sxs-lookup"><span data-stu-id="6e22c-110">Features removed or deprecated in the Finance 10.0.12 release</span></span>

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a><span data-ttu-id="6e22c-111">Report SSRS polacchi: registro IVA vendite, registro IVA acquisti, registro IVA riepilogativo UE - Riferimento funzione PL-00014</span><span class="sxs-lookup"><span data-stu-id="6e22c-111">Polish SSRS reports: Sales VAT register, Purchase VAT register, EU summary VAT register – Feature reference PL-00014</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="6e22c-112">**Motivo del deprecamento/rimozione**</span><span class="sxs-lookup"><span data-stu-id="6e22c-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="6e22c-113">Non obbligatorio per legge.</span><span class="sxs-lookup"><span data-stu-id="6e22c-113">Not legally required.</span></span>  |
| <span data-ttu-id="6e22c-114">**Sostituita da un'altra funzionalità?**</span><span class="sxs-lookup"><span data-stu-id="6e22c-114">**Replaced by another feature?**</span></span>   | <span data-ttu-id="6e22c-115">Sì (formato Excel per file di controllo standard con dichiarazione IVA - JPK_VDEK)</span><span class="sxs-lookup"><span data-stu-id="6e22c-115">Yes (Excel format for Standard Audit File with VAT declaration - JPK_VDEK)</span></span> |
| <span data-ttu-id="6e22c-116">**Aree del prodotto interessate**</span><span class="sxs-lookup"><span data-stu-id="6e22c-116">**Product areas affected**</span></span>         | <span data-ttu-id="6e22c-117">Richiesta</span><span class="sxs-lookup"><span data-stu-id="6e22c-117">Application</span></span> |
| <span data-ttu-id="6e22c-118">**Opzione di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="6e22c-118">**Deployment option**</span></span>              | <span data-ttu-id="6e22c-119">Tutti</span><span class="sxs-lookup"><span data-stu-id="6e22c-119">All</span></span> |
| <span data-ttu-id="6e22c-120">**Stato**</span><span class="sxs-lookup"><span data-stu-id="6e22c-120">**Status**</span></span>                         | <span data-ttu-id="6e22c-121">Deprecato: entro il 1° luglio 2021 non verranno più supportati i report SSRS: **Registro IVA vendite, Registro IVA acquisti, Registro IVA riepilogativo UE - Riferimento funzione PL-00014**.</span><span class="sxs-lookup"><span data-stu-id="6e22c-121">Deprecated: By July 1, 2021, we plan to no longer support the SSRS reports: **Sales VAT register, Purchase VAT register, EU summary VAT register – Feature reference PL-00014**.</span></span> <span data-ttu-id="6e22c-122">Verrà introdotto un esempio di formato Excel per il file di audit standard con dichiarazione IVA (JPK_VDEK).</span><span class="sxs-lookup"><span data-stu-id="6e22c-122">Excel format example for Standard Audit File with VAT declaration (JPK_VDEK) will be introduced instead.</span></span> |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a><span data-ttu-id="6e22c-123">Funzionalità rimosse o deprecate nella versione Finance and Operations 10.0.11</span><span class="sxs-lookup"><span data-stu-id="6e22c-123">Features removed or deprecated in the Finance 10.0.11 release</span></span>

### <a name="norwegian-standard-main-accounts"></a><span data-ttu-id="6e22c-124">Conti principali standard per la Norvegia</span><span class="sxs-lookup"><span data-stu-id="6e22c-124">Norwegian Standard main accounts</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="6e22c-125">**Motivo del deprecamento/rimozione**</span><span class="sxs-lookup"><span data-stu-id="6e22c-125">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="6e22c-126">Riprogettazione</span><span class="sxs-lookup"><span data-stu-id="6e22c-126">Redesign</span></span>  |
| <span data-ttu-id="6e22c-127">**Sostituita da un'altra funzionalità?**</span><span class="sxs-lookup"><span data-stu-id="6e22c-127">**Replaced by another feature?**</span></span>   | <span data-ttu-id="6e22c-128">Sì (sostituito con parametri specifici dell'applicazione in formato ER)</span><span class="sxs-lookup"><span data-stu-id="6e22c-128">Yes (Replaced with ER format application-specific parameters)</span></span> |
| <span data-ttu-id="6e22c-129">**Aree del prodotto interessate**</span><span class="sxs-lookup"><span data-stu-id="6e22c-129">**Product areas affected**</span></span>         | <span data-ttu-id="6e22c-130">Richiesta</span><span class="sxs-lookup"><span data-stu-id="6e22c-130">Application</span></span> |
| <span data-ttu-id="6e22c-131">**Opzione di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="6e22c-131">**Deployment option**</span></span>              | <span data-ttu-id="6e22c-132">Tutti</span><span class="sxs-lookup"><span data-stu-id="6e22c-132">All</span></span> |
| <span data-ttu-id="6e22c-133">**Stato**</span><span class="sxs-lookup"><span data-stu-id="6e22c-133">**Status**</span></span>                         | <span data-ttu-id="6e22c-134">Deprecato: entro il 1° aprile 2021, prevediamo di non supportare più la funzionalità relativa ai conti principali standard: campo di riferimento, tabella correlata, entità dei dati.</span><span class="sxs-lookup"><span data-stu-id="6e22c-134">Deprecated: By April 1, 2021, we plan to no longer support functionality related to Standard main accounts: Reference field, related table, data entity.</span></span> |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a><span data-ttu-id="6e22c-135">Funzionalità rimosse o deprecate nella versione Finance and Operations 10.0.7</span><span class="sxs-lookup"><span data-stu-id="6e22c-135">Features removed or deprecated in the Finance 10.0.7 release</span></span>

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a><span data-ttu-id="6e22c-136">La finestra di dialogo per la modifica della richiesta del flusso di lavoro non include più l'elenco a discesa per la selezione dell'utente</span><span class="sxs-lookup"><span data-stu-id="6e22c-136">Workflow request change dialog box no longer includes user selection drop-down list</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="6e22c-137">**Motivo del deprecamento/rimozione**</span><span class="sxs-lookup"><span data-stu-id="6e22c-137">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="6e22c-138">Modificato nella funzionalità con selezione di gruppi di conti.</span><span class="sxs-lookup"><span data-stu-id="6e22c-138">Changed to the feature with account groups selection.</span></span>  |
| <span data-ttu-id="6e22c-139">**Sostituita da un'altra funzionalità?**</span><span class="sxs-lookup"><span data-stu-id="6e22c-139">**Replaced by another feature?**</span></span>   | <span data-ttu-id="6e22c-140">Sì</span><span class="sxs-lookup"><span data-stu-id="6e22c-140">Yes</span></span> |
| <span data-ttu-id="6e22c-141">**Aree del prodotto interessate**</span><span class="sxs-lookup"><span data-stu-id="6e22c-141">**Product areas affected**</span></span>         | <span data-ttu-id="6e22c-142">Flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6e22c-142">Workflow</span></span> |
| <span data-ttu-id="6e22c-143">**Opzione di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="6e22c-143">**Deployment option**</span></span>              | <span data-ttu-id="6e22c-144">Tutti</span><span class="sxs-lookup"><span data-stu-id="6e22c-144">All</span></span> |
| <span data-ttu-id="6e22c-145">**Stato**</span><span class="sxs-lookup"><span data-stu-id="6e22c-145">**Status**</span></span>                         | <span data-ttu-id="6e22c-146">Deprecato: Dal 1° dicembre 2020, prevediamo di non supportare più l'impostazione dei tipi di giustificativi cinesi senza la selezione dei gruppi di conti.</span><span class="sxs-lookup"><span data-stu-id="6e22c-146">Deprecated: By December 1, 2020, we plan to no longer support Chinese voucher types setup without Account groups selection.</span></span> <span data-ttu-id="6e22c-147">Ulteriori dettagli relativi alla nuova progettazione della funzionalità sono disponibili in [Novità di 10.0.7](whats-new-changed-10-0-7.md).</span><span class="sxs-lookup"><span data-stu-id="6e22c-147">Find more details about the new design in [What's new in 10.0.7](whats-new-changed-10-0-7.md).</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="6e22c-148">Annunci precedenti sulle funzionalità rimosse o deprecate</span><span class="sxs-lookup"><span data-stu-id="6e22c-148">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="6e22c-149">Per ulteriori informazioni sulle funzionalità che sono state rimosse o deprecate nelle versioni precedenti, vedere [Funzionalità rimosse o deprecate nelle versioni precedenti](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="6e22c-149">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span></span>
