---
title: Tabelle Dataverse
description: Microsoft Dynamics 365 Human Resources utilizza Dataverse per abilitare scenari di estendibilità e integrazione.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8ddb74a2f0b6265c5be3c13a009211455ea862da
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893402"
---
# <a name="dataverse-tables"></a><span data-ttu-id="1afa3-103">Tabelle Dataverse</span><span class="sxs-lookup"><span data-stu-id="1afa3-103">Dataverse tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1afa3-104">Microsoft Dynamics 365 Human Resources utilizza Dataverse per abilitare scenari di estendibilità e integrazione.</span><span class="sxs-lookup"><span data-stu-id="1afa3-104">Microsoft Dynamics 365 Human Resources uses Dataverse to enable extensibility and integration scenarios.</span></span>

> [!NOTE]
> <span data-ttu-id="1afa3-105">Le entità di Human Resources corrispondono alle tabelle Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1afa3-105">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="1afa3-106">Per ulteriori informazioni su Dataverse (in precedenza Common Data Service) e aggiornamenti terminologici, vedi [ Cosa è Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="1afa3-106">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="1afa3-107">Le seguenti tabelle Dataverse sono disponibili in base alle entità di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1afa3-107">The following Dataverse tables are available based on Human Resources entities.</span></span>

## <a name="benefit-tables"></a><span data-ttu-id="1afa3-108">Tabelle dei benefit</span><span class="sxs-lookup"><span data-stu-id="1afa3-108">Benefit tables</span></span>

| <span data-ttu-id="1afa3-109">Nome</span><span class="sxs-lookup"><span data-stu-id="1afa3-109">Name</span></span> | <span data-ttu-id="1afa3-110">Tabella</span><span class="sxs-lookup"><span data-stu-id="1afa3-110">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1afa3-111">Frequenza di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="1afa3-111">Benefit Calculation Frequency</span></span> | <span data-ttu-id="1afa3-112">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="1afa3-112">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="1afa3-113">Periodo retributivo della frequenza di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="1afa3-113">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="1afa3-114">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="1afa3-114">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="1afa3-115">Coefficiente di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="1afa3-115">Benefit Calculation Rate</span></span> | <span data-ttu-id="1afa3-116">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="1afa3-116">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="1afa3-117">Dettagli dei coefficienti di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="1afa3-117">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="1afa3-118">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="1afa3-118">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="1afa3-119">Opzione benefit</span><span class="sxs-lookup"><span data-stu-id="1afa3-119">Benefit Option</span></span> | <span data-ttu-id="1afa3-120">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="1afa3-120">cdm_benefitoption</span></span> |
| <span data-ttu-id="1afa3-121">Piano benefit</span><span class="sxs-lookup"><span data-stu-id="1afa3-121">Benefit Plan</span></span> | <span data-ttu-id="1afa3-122">cdm_benefitplan (Non abilitato per il supporto del campo personalizzato)</span><span class="sxs-lookup"><span data-stu-id="1afa3-122">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="1afa3-123">Tipo di benefit</span><span class="sxs-lookup"><span data-stu-id="1afa3-123">Benefit Type</span></span> | <span data-ttu-id="1afa3-124">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="1afa3-124">cdm_benefittype</span></span> |

## <a name="business-process-tasks-tables"></a><span data-ttu-id="1afa3-125">Tabelle attività di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="1afa3-125">Business process tasks tables</span></span>

| <span data-ttu-id="1afa3-126">Nome</span><span class="sxs-lookup"><span data-stu-id="1afa3-126">Name</span></span> | <span data-ttu-id="1afa3-127">Tabella</span><span class="sxs-lookup"><span data-stu-id="1afa3-127">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1afa3-128">Calendario di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="1afa3-128">Business Process Calendar</span></span> | <span data-ttu-id="1afa3-129">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="1afa3-129">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="1afa3-130">Assegnazione gruppo di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="1afa3-130">Business Process Group Assignment</span></span> | <span data-ttu-id="1afa3-131">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="1afa3-131">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="1afa3-132">Gruppo di attività libreria processi aziendali</span><span class="sxs-lookup"><span data-stu-id="1afa3-132">Business Process Library Task Group</span></span> | <span data-ttu-id="1afa3-133">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="1afa3-133">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="1afa3-134">Fase di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="1afa3-134">Business Process Stage</span></span> | <span data-ttu-id="1afa3-135">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="1afa3-135">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="1afa3-136">Intestazione modello elenco di controllo</span><span class="sxs-lookup"><span data-stu-id="1afa3-136">Checklist Template Header</span></span> | <span data-ttu-id="1afa3-137">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="1afa3-137">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="1afa3-138">Attività del modello elenco di controllo</span><span class="sxs-lookup"><span data-stu-id="1afa3-138">Checklist Template Task</span></span> | <span data-ttu-id="1afa3-139">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="1afa3-139">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-tables"></a><span data-ttu-id="1afa3-140">Tabelle retribuzioni</span><span class="sxs-lookup"><span data-stu-id="1afa3-140">Compensation tables</span></span>

| <span data-ttu-id="1afa3-141">Nome</span><span class="sxs-lookup"><span data-stu-id="1afa3-141">Name</span></span> | <span data-ttu-id="1afa3-142">Tabella</span><span class="sxs-lookup"><span data-stu-id="1afa3-142">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1afa3-143">Piano di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="1afa3-143">Compensation Fixed Plan</span></span> | <span data-ttu-id="1afa3-144">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="1afa3-144">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="1afa3-145">Griglia di retribuzione</span><span class="sxs-lookup"><span data-stu-id="1afa3-145">Compensation Grid</span></span> | <span data-ttu-id="1afa3-146">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="1afa3-146">cdm_compensationgrid</span></span> |
| <span data-ttu-id="1afa3-147">Livello retributivo</span><span class="sxs-lookup"><span data-stu-id="1afa3-147">Compensation Level</span></span> | <span data-ttu-id="1afa3-148">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="1afa3-148">cdm_compensationlevel</span></span> |
| <span data-ttu-id="1afa3-149">Frequenza della retribuzione</span><span class="sxs-lookup"><span data-stu-id="1afa3-149">Compensation Pay Frequency</span></span> | <span data-ttu-id="1afa3-150">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="1afa3-150">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="1afa3-151">Impostazione punti di riferimento per le retribuzioni</span><span class="sxs-lookup"><span data-stu-id="1afa3-151">Compensation Reference Point Setup</span></span> | <span data-ttu-id="1afa3-152">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="1afa3-152">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="1afa3-153">Riga impostazione punti di riferimento per le retribuzioni</span><span class="sxs-lookup"><span data-stu-id="1afa3-153">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="1afa3-154">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="1afa3-154">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="1afa3-155">Paese di retribuzione</span><span class="sxs-lookup"><span data-stu-id="1afa3-155">Compensation Region</span></span> | <span data-ttu-id="1afa3-156">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="1afa3-156">cdm_compensationregion</span></span> |
| <span data-ttu-id="1afa3-157">Struttura retributiva</span><span class="sxs-lookup"><span data-stu-id="1afa3-157">Compensation Structure</span></span> | <span data-ttu-id="1afa3-158">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="1afa3-158">cdm_compensationstructure</span></span> |
| <span data-ttu-id="1afa3-159">Piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="1afa3-159">Compensation Variable Plan</span></span> | <span data-ttu-id="1afa3-160">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="1afa3-160">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="1afa3-161">Livello del piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="1afa3-161">Compensation Variable Plan Level</span></span> | <span data-ttu-id="1afa3-162">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="1afa3-162">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="1afa3-163">Tipo di piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="1afa3-163">Compensation Variable Plan Type</span></span> | <span data-ttu-id="1afa3-164">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="1afa3-164">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="1afa3-165">Evento di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="1afa3-165">Fixed Compensation Event</span></span> | <span data-ttu-id="1afa3-166">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="1afa3-166">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="1afa3-167">Regola di distribuzione incentivi</span><span class="sxs-lookup"><span data-stu-id="1afa3-167">Vesting Rule</span></span> | <span data-ttu-id="1afa3-168">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="1afa3-168">cdm_vestingrule</span></span> |
| <span data-ttu-id="1afa3-169">Retribuzione fissa del lavoratore</span><span class="sxs-lookup"><span data-stu-id="1afa3-169">Worker Fixed Compensation</span></span> | <span data-ttu-id="1afa3-170">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="1afa3-170">cdm_workerfixedcompensation</span></span> |

## <a name="organization-tables"></a><span data-ttu-id="1afa3-171">Tabelle organizzazione</span><span class="sxs-lookup"><span data-stu-id="1afa3-171">Organization tables</span></span>

| <span data-ttu-id="1afa3-172">Nome</span><span class="sxs-lookup"><span data-stu-id="1afa3-172">Name</span></span> | <span data-ttu-id="1afa3-173">Tabella</span><span class="sxs-lookup"><span data-stu-id="1afa3-173">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1afa3-174">Reparto</span><span class="sxs-lookup"><span data-stu-id="1afa3-174">Department</span></span> | <span data-ttu-id="1afa3-175">cdm_department</span><span class="sxs-lookup"><span data-stu-id="1afa3-175">cdm_department</span></span> |
| <span data-ttu-id="1afa3-176">Impiego</span><span class="sxs-lookup"><span data-stu-id="1afa3-176">Employment</span></span> | <span data-ttu-id="1afa3-177">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="1afa3-177">cdm_employment</span></span> |
| <span data-ttu-id="1afa3-178">Società</span><span class="sxs-lookup"><span data-stu-id="1afa3-178">Company</span></span> | <span data-ttu-id="1afa3-179">cdm_company</span><span class="sxs-lookup"><span data-stu-id="1afa3-179">cdm_company</span></span> |
| <span data-ttu-id="1afa3-180">Posizione</span><span class="sxs-lookup"><span data-stu-id="1afa3-180">Job</span></span> | <span data-ttu-id="1afa3-181">cdm_job</span><span class="sxs-lookup"><span data-stu-id="1afa3-181">cdm_job</span></span> |
| <span data-ttu-id="1afa3-182">Funzione lavorativa</span><span class="sxs-lookup"><span data-stu-id="1afa3-182">Job Function</span></span> | <span data-ttu-id="1afa3-183">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="1afa3-183">cdm_jobfunction</span></span> |
| <span data-ttu-id="1afa3-184">Posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="1afa3-184">Job Position</span></span> | <span data-ttu-id="1afa3-185">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="1afa3-185">cdm_jobposition</span></span> |
| <span data-ttu-id="1afa3-186">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="1afa3-186">Position Type</span></span> | <span data-ttu-id="1afa3-187">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="1afa3-187">cdm_positiontype</span></span> |
| <span data-ttu-id="1afa3-188">Assegnazione lavoratore posizione</span><span class="sxs-lookup"><span data-stu-id="1afa3-188">Position Worker Assignment</span></span> | <span data-ttu-id="1afa3-189">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="1afa3-189">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="1afa3-190">Dimensione posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="1afa3-190">Job Position Dimension</span></span> | <span data-ttu-id="1afa3-191">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="1afa3-191">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="1afa3-192">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="1afa3-192">Job Type</span></span> | <span data-ttu-id="1afa3-193">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="1afa3-193">cdm_jobtype</span></span> |
| <span data-ttu-id="1afa3-194">Lingua</span><span class="sxs-lookup"><span data-stu-id="1afa3-194">Language</span></span> | <span data-ttu-id="1afa3-195">cdm_language</span><span class="sxs-lookup"><span data-stu-id="1afa3-195">cdm_language</span></span> |
| <span data-ttu-id="1afa3-196">Funzione</span><span class="sxs-lookup"><span data-stu-id="1afa3-196">Title</span></span> | <span data-ttu-id="1afa3-197">cdm_title</span><span class="sxs-lookup"><span data-stu-id="1afa3-197">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="1afa3-198">Le dimensioni finanziarie per **Tipo di posizione**, **Assegnazione lavoratore posizione** e **Impiego** forniscono l'integrazione in una direzione per Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1afa3-198">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Dataverse.</span></span> <span data-ttu-id="1afa3-199">Gli aggiornamenti sulle dimensioni finanziarie al momento non vengono sincronizzati da Dataverse a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1afa3-199">Financial dimensions updates currently can't synchronize from Dataverse to Human Resources.</span></span> 

## <a name="leave-and-absence-tables"></a><span data-ttu-id="1afa3-200">Tabelle congedi e assenze</span><span class="sxs-lookup"><span data-stu-id="1afa3-200">Leave and absence tables</span></span>

| <span data-ttu-id="1afa3-201">Nome</span><span class="sxs-lookup"><span data-stu-id="1afa3-201">Name</span></span> | <span data-ttu-id="1afa3-202">Tabella</span><span class="sxs-lookup"><span data-stu-id="1afa3-202">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1afa3-203">Transazione bancaria per congedo</span><span class="sxs-lookup"><span data-stu-id="1afa3-203">Leave Bank Transaction</span></span> | <span data-ttu-id="1afa3-204">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="1afa3-204">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="1afa3-205">Iscrizione al piano di congedo</span><span class="sxs-lookup"><span data-stu-id="1afa3-205">Leave Enrollment</span></span> | <span data-ttu-id="1afa3-206">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="1afa3-206">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="1afa3-207">Piano di congedo</span><span class="sxs-lookup"><span data-stu-id="1afa3-207">Leave Plan</span></span> | <span data-ttu-id="1afa3-208">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="1afa3-208">cdm_leaveplan</span></span> |
| <span data-ttu-id="1afa3-209">Richiesta di congedo</span><span class="sxs-lookup"><span data-stu-id="1afa3-209">Leave Request</span></span> | <span data-ttu-id="1afa3-210">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="1afa3-210">cdm_leaverequest</span></span> |
| <span data-ttu-id="1afa3-211">Dettagli richiesta congedo</span><span class="sxs-lookup"><span data-stu-id="1afa3-211">Leave Request Detail</span></span> | <span data-ttu-id="1afa3-212">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="1afa3-212">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="1afa3-213">Tipo di congedo</span><span class="sxs-lookup"><span data-stu-id="1afa3-213">Leave Type</span></span> | <span data-ttu-id="1afa3-214">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="1afa3-214">cdm_leavetype</span></span> |
| <span data-ttu-id="1afa3-215">Codice motivo del tipo di congedo</span><span class="sxs-lookup"><span data-stu-id="1afa3-215">Leave Type Reason Code</span></span> | <span data-ttu-id="1afa3-216">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="1afa3-216">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-tables"></a><span data-ttu-id="1afa3-217">Tabelle retribuzioni</span><span class="sxs-lookup"><span data-stu-id="1afa3-217">Payroll tables</span></span>

| <span data-ttu-id="1afa3-218">Nome</span><span class="sxs-lookup"><span data-stu-id="1afa3-218">Name</span></span> | <span data-ttu-id="1afa3-219">Tabella</span><span class="sxs-lookup"><span data-stu-id="1afa3-219">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1afa3-220">Ciclo retributivo</span><span class="sxs-lookup"><span data-stu-id="1afa3-220">Pay Cycle</span></span> | <span data-ttu-id="1afa3-221">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="1afa3-221">cdm_paycycle</span></span> |
| <span data-ttu-id="1afa3-222">Periodo retributivo</span><span class="sxs-lookup"><span data-stu-id="1afa3-222">Pay Period</span></span> | <span data-ttu-id="1afa3-223">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="1afa3-223">cdm_payperiod</span></span> |
| <span data-ttu-id="1afa3-224">Codice di reddito retribuzioni</span><span class="sxs-lookup"><span data-stu-id="1afa3-224">Payroll Earning Code</span></span> | <span data-ttu-id="1afa3-225">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="1afa3-225">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="1afa3-226">Esborso conto bancario</span><span class="sxs-lookup"><span data-stu-id="1afa3-226">Bank Account Disbursement</span></span> | <span data-ttu-id="1afa3-227">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="1afa3-227">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="1afa3-228">Regione fiscale</span><span class="sxs-lookup"><span data-stu-id="1afa3-228">Tax Region</span></span> | <span data-ttu-id="1afa3-229">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="1afa3-229">cdm_taxregion</span></span> |

## <a name="worker-tables"></a><span data-ttu-id="1afa3-230">Tabelle lavoratori</span><span class="sxs-lookup"><span data-stu-id="1afa3-230">Worker tables</span></span>

| <span data-ttu-id="1afa3-231">Nome</span><span class="sxs-lookup"><span data-stu-id="1afa3-231">Name</span></span> | <span data-ttu-id="1afa3-232">Tabella</span><span class="sxs-lookup"><span data-stu-id="1afa3-232">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1afa3-233">Lavoro</span><span class="sxs-lookup"><span data-stu-id="1afa3-233">Worker</span></span> | <span data-ttu-id="1afa3-234">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="1afa3-234">cdm_worker</span></span> |
| <span data-ttu-id="1afa3-235">Indirizzo del lavoratore</span><span class="sxs-lookup"><span data-stu-id="1afa3-235">Worker Address</span></span> | <span data-ttu-id="1afa3-236">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="1afa3-236">cdm_workeraddress</span></span> |
| <span data-ttu-id="1afa3-237">Dati personali lavoratore</span><span class="sxs-lookup"><span data-stu-id="1afa3-237">Worker Personal Detail</span></span> | <span data-ttu-id="1afa3-238">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="1afa3-238">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="1afa3-239">Numero di identificazione lavoratore</span><span class="sxs-lookup"><span data-stu-id="1afa3-239">Worker Person Identification Number</span></span> | <span data-ttu-id="1afa3-240">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="1afa3-240">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="1afa3-241">Tipo di identificazione lavoratore</span><span class="sxs-lookup"><span data-stu-id="1afa3-241">Worker Person Identification Type</span></span> | <span data-ttu-id="1afa3-242">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="1afa3-242">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="1afa3-243">Calendario lavorativo</span><span class="sxs-lookup"><span data-stu-id="1afa3-243">Work Calendar</span></span> | <span data-ttu-id="1afa3-244">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="1afa3-244">cdm_workcalendar</span></span> |
| <span data-ttu-id="1afa3-245">Giorno calendario di lavoro</span><span class="sxs-lookup"><span data-stu-id="1afa3-245">Work Calendar Day</span></span> | <span data-ttu-id="1afa3-246">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="1afa3-246">cdm_workcalendarday</span></span> |
| <span data-ttu-id="1afa3-247">Festività calendario lavorativo</span><span class="sxs-lookup"><span data-stu-id="1afa3-247">Work Calendar Holiday</span></span> |<span data-ttu-id="1afa3-248">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="1afa3-248">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="1afa3-249">Riga festività del calendario di lavoro</span><span class="sxs-lookup"><span data-stu-id="1afa3-249">Work Calendar Holiday Line</span></span> | <span data-ttu-id="1afa3-250">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="1afa3-250">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="1afa3-251">Intervallo orario calendario di lavoro</span><span class="sxs-lookup"><span data-stu-id="1afa3-251">Work Calendar Time Interval</span></span> | <span data-ttu-id="1afa3-252">cdm_workcalendartimeinterval (Non abilitato per il supporto del campo personalizzato)</span><span class="sxs-lookup"><span data-stu-id="1afa3-252">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="1afa3-253">Conto bancario del lavoratore</span><span class="sxs-lookup"><span data-stu-id="1afa3-253">Worker Bank Account</span></span> | <span data-ttu-id="1afa3-254">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="1afa3-254">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-tables"></a><span data-ttu-id="1afa3-255">Tabelle di configurazione dei lavoratori</span><span class="sxs-lookup"><span data-stu-id="1afa3-255">Worker setup tables</span></span>

| <span data-ttu-id="1afa3-256">Nome</span><span class="sxs-lookup"><span data-stu-id="1afa3-256">Name</span></span> | <span data-ttu-id="1afa3-257">Tabella</span><span class="sxs-lookup"><span data-stu-id="1afa3-257">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1afa3-258">Stato veterano</span><span class="sxs-lookup"><span data-stu-id="1afa3-258">Veteran Status</span></span> | <span data-ttu-id="1afa3-259">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="1afa3-259">cdm_veteranstatus</span></span> |
| <span data-ttu-id="1afa3-260">Origine etnica</span><span class="sxs-lookup"><span data-stu-id="1afa3-260">Ethnic Origin</span></span> | <span data-ttu-id="1afa3-261">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="1afa3-261">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="1afa3-262">Codice causale</span><span class="sxs-lookup"><span data-stu-id="1afa3-262">Reason Code</span></span> | <span data-ttu-id="1afa3-263">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="1afa3-263">cdm_reasoncode</span></span> |
| <span data-ttu-id="1afa3-264">Agenzia emittente dell'identificazione personale.</span><span class="sxs-lookup"><span data-stu-id="1afa3-264">Person Identification Issuing Agency</span></span> | <span data-ttu-id="1afa3-265">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="1afa3-265">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-tables"></a><span data-ttu-id="1afa3-266">Tabelle delle competenze</span><span class="sxs-lookup"><span data-stu-id="1afa3-266">Competency tables</span></span>

| <span data-ttu-id="1afa3-267">Nome</span><span class="sxs-lookup"><span data-stu-id="1afa3-267">Name</span></span> | <span data-ttu-id="1afa3-268">Tabella</span><span class="sxs-lookup"><span data-stu-id="1afa3-268">Table</span></span> |
| --- | --- |
| <span data-ttu-id="1afa3-269">Tipo di competenza</span><span class="sxs-lookup"><span data-stu-id="1afa3-269">Skill Type</span></span> | <span data-ttu-id="1afa3-270">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="1afa3-270">cdm_skilltype</span></span> |

## <a name="table-relationship-models"></a><span data-ttu-id="1afa3-271">Modelli di relazioni tra tabelle</span><span class="sxs-lookup"><span data-stu-id="1afa3-271">Table relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="1afa3-272">Lavoro</span><span class="sxs-lookup"><span data-stu-id="1afa3-272">Worker</span></span>

![Lavoro](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="1afa3-274">Lavoro e posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="1afa3-274">Job and Job Position</span></span>

![Lavoro e posizione lavorativa](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="1afa3-276">Benefit</span><span class="sxs-lookup"><span data-stu-id="1afa3-276">Benefits</span></span>

![Benefit](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="1afa3-278">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="1afa3-278">Compensation</span></span>

![Retribuzione](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="1afa3-280">Uscire</span><span class="sxs-lookup"><span data-stu-id="1afa3-280">Leave</span></span>

![Uscire](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="1afa3-282">Calendario lavorativo</span><span class="sxs-lookup"><span data-stu-id="1afa3-282">Work Calendar</span></span>

![Calendario lavorativo](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="1afa3-284">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1afa3-284">See also</span></span>

[<span data-ttu-id="1afa3-285">Scegliere una tecnologia di integrazione dei dati</span><span class="sxs-lookup"><span data-stu-id="1afa3-285">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)<br>
[<span data-ttu-id="1afa3-286">Configurare l'integrazione di Dataverse</span><span class="sxs-lookup"><span data-stu-id="1afa3-286">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)<br>
[<span data-ttu-id="1afa3-287">Configurare tabelle virtuali in Dataverse</span><span class="sxs-lookup"><span data-stu-id="1afa3-287">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="1afa3-288">Domande frequenti sulle tabelle virtuali in Human Resources</span><span class="sxs-lookup"><span data-stu-id="1afa3-288">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="1afa3-289">Che cos'è Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="1afa3-289">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="1afa3-290">Aggiornamenti terminologici</span><span class="sxs-lookup"><span data-stu-id="1afa3-290">Terminology updates</span></span>](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]