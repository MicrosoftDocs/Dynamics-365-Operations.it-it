---
title: Entità di Common Data Service
description: Microsoft Dynamics 365 Human Resources utilizza Common Data Service per abilitare scenari di estendibilità e integrazione.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 6879a45dd1fcc1ba718747aaaf0d7936c2eac49f
ms.sourcegitcommit: 3cad15f8ecc257d3a45c1bc1fada7c094ff4bcec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087348"
---
# <a name="common-data-service-entities"></a><span data-ttu-id="95a05-103">Entità di Common Data Service</span><span class="sxs-lookup"><span data-stu-id="95a05-103">Common Data Service entities</span></span>

<span data-ttu-id="95a05-104">Microsoft Dynamics 365 Human Resources utilizza Common Data Service per abilitare scenari di estendibilità e integrazione.</span><span class="sxs-lookup"><span data-stu-id="95a05-104">Microsoft Dynamics 365 Human Resources uses Common Data Service to enable extensibility and integration scenarios.</span></span>

<span data-ttu-id="95a05-105">Per ulteriori informazioni su Common Data Service, vedere [Che cos'è Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="95a05-105">For more information about Common Data Service, see [What is Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span>

<span data-ttu-id="95a05-106">Le seguenti entità di Human Resources sono disponibili in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="95a05-106">The following Human Resources entities are available in Common Data Service.</span></span>

## <a name="benefit-entities"></a><span data-ttu-id="95a05-107">Entità Benefit</span><span class="sxs-lookup"><span data-stu-id="95a05-107">Benefit entities</span></span>

| <span data-ttu-id="95a05-108">Nome</span><span class="sxs-lookup"><span data-stu-id="95a05-108">Name</span></span> | <span data-ttu-id="95a05-109">Entità</span><span class="sxs-lookup"><span data-stu-id="95a05-109">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="95a05-110">Frequenza di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="95a05-110">Benefit Calculation Frequency</span></span> | <span data-ttu-id="95a05-111">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="95a05-111">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="95a05-112">Periodo retributivo della frequenza di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="95a05-112">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="95a05-113">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="95a05-113">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="95a05-114">Coefficiente di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="95a05-114">Benefit Calculation Rate</span></span> | <span data-ttu-id="95a05-115">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="95a05-115">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="95a05-116">Dettagli dei coefficienti di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="95a05-116">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="95a05-117">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="95a05-117">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="95a05-118">Opzione benefit</span><span class="sxs-lookup"><span data-stu-id="95a05-118">Benefit Option</span></span> | <span data-ttu-id="95a05-119">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="95a05-119">cdm_benefitoption</span></span> |
| <span data-ttu-id="95a05-120">Piano benefit</span><span class="sxs-lookup"><span data-stu-id="95a05-120">Benefit Plan</span></span> | <span data-ttu-id="95a05-121">cdm_benefitplan (Non abilitato per il supporto del campo personalizzato)</span><span class="sxs-lookup"><span data-stu-id="95a05-121">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="95a05-122">Tipo di benefit</span><span class="sxs-lookup"><span data-stu-id="95a05-122">Benefit Type</span></span> | <span data-ttu-id="95a05-123">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="95a05-123">cdm_benefittype</span></span> |

## <a name="business-process-tasks-entities"></a><span data-ttu-id="95a05-124">Entità attività di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="95a05-124">Business process tasks entities</span></span>

| <span data-ttu-id="95a05-125">Nome</span><span class="sxs-lookup"><span data-stu-id="95a05-125">Name</span></span> | <span data-ttu-id="95a05-126">Entità</span><span class="sxs-lookup"><span data-stu-id="95a05-126">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="95a05-127">Calendario di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="95a05-127">Business Process Calendar</span></span> | <span data-ttu-id="95a05-128">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="95a05-128">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="95a05-129">Assegnazione gruppo di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="95a05-129">Business Process Group Assignment</span></span> | <span data-ttu-id="95a05-130">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="95a05-130">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="95a05-131">Gruppo di attività libreria processi aziendali</span><span class="sxs-lookup"><span data-stu-id="95a05-131">Business Process Library Task Group</span></span> | <span data-ttu-id="95a05-132">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="95a05-132">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="95a05-133">Fase di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="95a05-133">Business Process Stage</span></span> | <span data-ttu-id="95a05-134">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="95a05-134">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="95a05-135">Intestazione modello elenco di controllo</span><span class="sxs-lookup"><span data-stu-id="95a05-135">Checklist Template Header</span></span> | <span data-ttu-id="95a05-136">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="95a05-136">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="95a05-137">Attività del modello elenco di controllo</span><span class="sxs-lookup"><span data-stu-id="95a05-137">Checklist Template Task</span></span> | <span data-ttu-id="95a05-138">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="95a05-138">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-entities"></a><span data-ttu-id="95a05-139">Entità retribuzione</span><span class="sxs-lookup"><span data-stu-id="95a05-139">Compensation entities</span></span>

| <span data-ttu-id="95a05-140">Nome</span><span class="sxs-lookup"><span data-stu-id="95a05-140">Name</span></span> | <span data-ttu-id="95a05-141">Entità</span><span class="sxs-lookup"><span data-stu-id="95a05-141">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="95a05-142">Piano di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="95a05-142">Compensation Fixed Plan</span></span> | <span data-ttu-id="95a05-143">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="95a05-143">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="95a05-144">Griglia di retribuzione</span><span class="sxs-lookup"><span data-stu-id="95a05-144">Compensation Grid</span></span> | <span data-ttu-id="95a05-145">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="95a05-145">cdm_compensationgrid</span></span> |
| <span data-ttu-id="95a05-146">Livello retributivo</span><span class="sxs-lookup"><span data-stu-id="95a05-146">Compensation Level</span></span> | <span data-ttu-id="95a05-147">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="95a05-147">cdm_compensationlevel</span></span> |
| <span data-ttu-id="95a05-148">Frequenza della retribuzione</span><span class="sxs-lookup"><span data-stu-id="95a05-148">Compensation Pay Frequency</span></span> | <span data-ttu-id="95a05-149">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="95a05-149">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="95a05-150">Impostazione punti di riferimento per le retribuzioni</span><span class="sxs-lookup"><span data-stu-id="95a05-150">Compensation Reference Point Setup</span></span> | <span data-ttu-id="95a05-151">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="95a05-151">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="95a05-152">Riga impostazione punti di riferimento per le retribuzioni</span><span class="sxs-lookup"><span data-stu-id="95a05-152">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="95a05-153">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="95a05-153">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="95a05-154">Paese di retribuzione</span><span class="sxs-lookup"><span data-stu-id="95a05-154">Compensation Region</span></span> | <span data-ttu-id="95a05-155">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="95a05-155">cdm_compensationregion</span></span> |
| <span data-ttu-id="95a05-156">Struttura retributiva</span><span class="sxs-lookup"><span data-stu-id="95a05-156">Compensation Structure</span></span> | <span data-ttu-id="95a05-157">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="95a05-157">cdm_compensationstructure</span></span> |
| <span data-ttu-id="95a05-158">Piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="95a05-158">Compensation Variable Plan</span></span> | <span data-ttu-id="95a05-159">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="95a05-159">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="95a05-160">Livello del piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="95a05-160">Compensation Variable Plan Level</span></span> | <span data-ttu-id="95a05-161">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="95a05-161">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="95a05-162">Tipo di piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="95a05-162">Compensation Variable Plan Type</span></span> | <span data-ttu-id="95a05-163">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="95a05-163">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="95a05-164">Evento di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="95a05-164">Fixed Compensation Event</span></span> | <span data-ttu-id="95a05-165">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="95a05-165">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="95a05-166">Regola di distribuzione incentivi</span><span class="sxs-lookup"><span data-stu-id="95a05-166">Vesting Rule</span></span> | <span data-ttu-id="95a05-167">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="95a05-167">cdm_vestingrule</span></span> |
| <span data-ttu-id="95a05-168">Retribuzione fissa lavoratore</span><span class="sxs-lookup"><span data-stu-id="95a05-168">Worker Fixed Compensation</span></span> | <span data-ttu-id="95a05-169">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="95a05-169">cdm_workerfixedcompensation</span></span> |

## <a name="organization-entities"></a><span data-ttu-id="95a05-170">Entità Organizzazione</span><span class="sxs-lookup"><span data-stu-id="95a05-170">Organization entities</span></span>

| <span data-ttu-id="95a05-171">Nome</span><span class="sxs-lookup"><span data-stu-id="95a05-171">Name</span></span> | <span data-ttu-id="95a05-172">Entità</span><span class="sxs-lookup"><span data-stu-id="95a05-172">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="95a05-173">Reparto</span><span class="sxs-lookup"><span data-stu-id="95a05-173">Department</span></span> | <span data-ttu-id="95a05-174">cdm_department</span><span class="sxs-lookup"><span data-stu-id="95a05-174">cdm_department</span></span> |
| <span data-ttu-id="95a05-175">Impiego</span><span class="sxs-lookup"><span data-stu-id="95a05-175">Employment</span></span> | <span data-ttu-id="95a05-176">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="95a05-176">cdm_employment</span></span> |
| <span data-ttu-id="95a05-177">Società</span><span class="sxs-lookup"><span data-stu-id="95a05-177">Company</span></span> | <span data-ttu-id="95a05-178">cdm_company</span><span class="sxs-lookup"><span data-stu-id="95a05-178">cdm_company</span></span> |
| <span data-ttu-id="95a05-179">Posizione</span><span class="sxs-lookup"><span data-stu-id="95a05-179">Job</span></span> | <span data-ttu-id="95a05-180">cdm_job</span><span class="sxs-lookup"><span data-stu-id="95a05-180">cdm_job</span></span> |
| <span data-ttu-id="95a05-181">Funzione lavorativa</span><span class="sxs-lookup"><span data-stu-id="95a05-181">Job Function</span></span> | <span data-ttu-id="95a05-182">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="95a05-182">cdm_jobfunction</span></span> |
| <span data-ttu-id="95a05-183">Posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="95a05-183">Job Position</span></span> | <span data-ttu-id="95a05-184">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="95a05-184">cdm_jobposition</span></span> |
| <span data-ttu-id="95a05-185">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="95a05-185">Position Type</span></span> | <span data-ttu-id="95a05-186">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="95a05-186">cdm_positiontype</span></span> |
| <span data-ttu-id="95a05-187">Assegnazione lavoratore posizione</span><span class="sxs-lookup"><span data-stu-id="95a05-187">Position Worker Assignment</span></span> | <span data-ttu-id="95a05-188">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="95a05-188">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="95a05-189">Tipo di mansione</span><span class="sxs-lookup"><span data-stu-id="95a05-189">Job Type</span></span> | <span data-ttu-id="95a05-190">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="95a05-190">cdm_jobtype</span></span> |
| <span data-ttu-id="95a05-191">Lingua</span><span class="sxs-lookup"><span data-stu-id="95a05-191">Language</span></span> | <span data-ttu-id="95a05-192">cdm_language</span><span class="sxs-lookup"><span data-stu-id="95a05-192">cdm_language</span></span> |

## <a name="leave-and-absence-entities"></a><span data-ttu-id="95a05-193">Entità Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="95a05-193">Leave and absence entities</span></span>

| <span data-ttu-id="95a05-194">Nome</span><span class="sxs-lookup"><span data-stu-id="95a05-194">Name</span></span> | <span data-ttu-id="95a05-195">Entità</span><span class="sxs-lookup"><span data-stu-id="95a05-195">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="95a05-196">Transazione bancaria di congedo</span><span class="sxs-lookup"><span data-stu-id="95a05-196">Leave Bank Transaction</span></span> | <span data-ttu-id="95a05-197">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="95a05-197">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="95a05-198">Iscrizione congedo</span><span class="sxs-lookup"><span data-stu-id="95a05-198">Leave Enrollment</span></span> | <span data-ttu-id="95a05-199">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="95a05-199">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="95a05-200">Piano di congedo</span><span class="sxs-lookup"><span data-stu-id="95a05-200">Leave Plan</span></span> | <span data-ttu-id="95a05-201">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="95a05-201">cdm_leaveplan</span></span> |
| <span data-ttu-id="95a05-202">Richiesta di congedo</span><span class="sxs-lookup"><span data-stu-id="95a05-202">Leave Request</span></span> | <span data-ttu-id="95a05-203">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="95a05-203">cdm_leaverequest</span></span> |
| <span data-ttu-id="95a05-204">Dettagli richiesta congedo</span><span class="sxs-lookup"><span data-stu-id="95a05-204">Leave Request Detail</span></span> | <span data-ttu-id="95a05-205">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="95a05-205">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="95a05-206">Tipo di congedo</span><span class="sxs-lookup"><span data-stu-id="95a05-206">Leave Type</span></span> | <span data-ttu-id="95a05-207">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="95a05-207">cdm_leavetype</span></span> |
| <span data-ttu-id="95a05-208">Codice motivo del tipo di congedo</span><span class="sxs-lookup"><span data-stu-id="95a05-208">Leave Type Reason Code</span></span> | <span data-ttu-id="95a05-209">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="95a05-209">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-entities"></a><span data-ttu-id="95a05-210">Entità Retribuzioni</span><span class="sxs-lookup"><span data-stu-id="95a05-210">Payroll entities</span></span>

| <span data-ttu-id="95a05-211">Nome</span><span class="sxs-lookup"><span data-stu-id="95a05-211">Name</span></span> | <span data-ttu-id="95a05-212">Entità</span><span class="sxs-lookup"><span data-stu-id="95a05-212">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="95a05-213">Ciclo retributivo</span><span class="sxs-lookup"><span data-stu-id="95a05-213">Pay Cycle</span></span> | <span data-ttu-id="95a05-214">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="95a05-214">cdm_paycycle</span></span> |
| <span data-ttu-id="95a05-215">Periodo retributivo</span><span class="sxs-lookup"><span data-stu-id="95a05-215">Pay Period</span></span> | <span data-ttu-id="95a05-216">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="95a05-216">cdm_payperiod</span></span> |
| <span data-ttu-id="95a05-217">Codice di reddito per retribuzione</span><span class="sxs-lookup"><span data-stu-id="95a05-217">Payroll Earning Code</span></span> | <span data-ttu-id="95a05-218">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="95a05-218">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="95a05-219">Esborso conto bancario</span><span class="sxs-lookup"><span data-stu-id="95a05-219">Bank Account Disbursement</span></span> | <span data-ttu-id="95a05-220">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="95a05-220">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="95a05-221">Regione fiscale</span><span class="sxs-lookup"><span data-stu-id="95a05-221">Tax Region</span></span> | <span data-ttu-id="95a05-222">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="95a05-222">cdm_taxregion</span></span> |

## <a name="worker-entities"></a><span data-ttu-id="95a05-223">Persone giuridiche - Lavoratore</span><span class="sxs-lookup"><span data-stu-id="95a05-223">Worker entities</span></span>

| <span data-ttu-id="95a05-224">Nome</span><span class="sxs-lookup"><span data-stu-id="95a05-224">Name</span></span> | <span data-ttu-id="95a05-225">Entità</span><span class="sxs-lookup"><span data-stu-id="95a05-225">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="95a05-226">Lavoro</span><span class="sxs-lookup"><span data-stu-id="95a05-226">Worker</span></span> | <span data-ttu-id="95a05-227">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="95a05-227">cdm_worker</span></span> |
| <span data-ttu-id="95a05-228">Indirizzo lavoratore</span><span class="sxs-lookup"><span data-stu-id="95a05-228">Worker Address</span></span> | <span data-ttu-id="95a05-229">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="95a05-229">cdm_workeraddress</span></span> |
| <span data-ttu-id="95a05-230">Dati personali lavoratore</span><span class="sxs-lookup"><span data-stu-id="95a05-230">Worker Personal Detail</span></span> | <span data-ttu-id="95a05-231">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="95a05-231">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="95a05-232">Numero di identificazione lavoratore</span><span class="sxs-lookup"><span data-stu-id="95a05-232">Worker Person Identification Number</span></span> | <span data-ttu-id="95a05-233">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="95a05-233">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="95a05-234">Tipo di identificazione lavoratore</span><span class="sxs-lookup"><span data-stu-id="95a05-234">Worker Person Identification Type</span></span> | <span data-ttu-id="95a05-235">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="95a05-235">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="95a05-236">Calendario lavorativo</span><span class="sxs-lookup"><span data-stu-id="95a05-236">Work Calendar</span></span> | <span data-ttu-id="95a05-237">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="95a05-237">cdm_workcalendar</span></span> |
| <span data-ttu-id="95a05-238">Giorno calendario di lavoro</span><span class="sxs-lookup"><span data-stu-id="95a05-238">Work Calendar Day</span></span> | <span data-ttu-id="95a05-239">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="95a05-239">cdm_workcalendarday</span></span> |
| <span data-ttu-id="95a05-240">Festività calendario lavorativo</span><span class="sxs-lookup"><span data-stu-id="95a05-240">Work Calendar Holiday</span></span> |<span data-ttu-id="95a05-241">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="95a05-241">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="95a05-242">Riga festività del calendario di lavoro</span><span class="sxs-lookup"><span data-stu-id="95a05-242">Work Calendar Holiday Line</span></span> | <span data-ttu-id="95a05-243">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="95a05-243">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="95a05-244">Intervallo orario calendario di lavoro</span><span class="sxs-lookup"><span data-stu-id="95a05-244">Work Calendar Time Interval</span></span> | <span data-ttu-id="95a05-245">cdm_workcalendartimeinterval (Non abilitato per il supporto del campo personalizzato)</span><span class="sxs-lookup"><span data-stu-id="95a05-245">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="95a05-246">Conto bancario del lavoratore</span><span class="sxs-lookup"><span data-stu-id="95a05-246">Worker Bank Account</span></span> | <span data-ttu-id="95a05-247">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="95a05-247">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-entities"></a><span data-ttu-id="95a05-248">Entità impostazione lavoratore</span><span class="sxs-lookup"><span data-stu-id="95a05-248">Worker setup entities</span></span>

| <span data-ttu-id="95a05-249">Nome</span><span class="sxs-lookup"><span data-stu-id="95a05-249">Name</span></span> | <span data-ttu-id="95a05-250">Entità</span><span class="sxs-lookup"><span data-stu-id="95a05-250">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="95a05-251">Stato di veterano</span><span class="sxs-lookup"><span data-stu-id="95a05-251">Veteran Status</span></span> | <span data-ttu-id="95a05-252">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="95a05-252">cdm_veteranstatus</span></span> |
| <span data-ttu-id="95a05-253">Origine etnica</span><span class="sxs-lookup"><span data-stu-id="95a05-253">Ethnic Origin</span></span> | <span data-ttu-id="95a05-254">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="95a05-254">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="95a05-255">Codice causale</span><span class="sxs-lookup"><span data-stu-id="95a05-255">Reason Code</span></span> | <span data-ttu-id="95a05-256">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="95a05-256">cdm_reasoncode</span></span> |
| <span data-ttu-id="95a05-257">Agenzia di rilascio dell'identificazione della persona</span><span class="sxs-lookup"><span data-stu-id="95a05-257">Person Identification Issuing Agency</span></span> | <span data-ttu-id="95a05-258">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="95a05-258">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-entities"></a><span data-ttu-id="95a05-259">Entità competenza</span><span class="sxs-lookup"><span data-stu-id="95a05-259">Competency entities</span></span>

| <span data-ttu-id="95a05-260">Nome</span><span class="sxs-lookup"><span data-stu-id="95a05-260">Name</span></span> | <span data-ttu-id="95a05-261">Entità</span><span class="sxs-lookup"><span data-stu-id="95a05-261">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="95a05-262">Tipo di competenza</span><span class="sxs-lookup"><span data-stu-id="95a05-262">Skill Type</span></span> | <span data-ttu-id="95a05-263">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="95a05-263">cdm_skilltype</span></span> |

## <a name="entity-relationship-models"></a><span data-ttu-id="95a05-264">Modelli di relazioni tra entità</span><span class="sxs-lookup"><span data-stu-id="95a05-264">Entity relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="95a05-265">Lavoro</span><span class="sxs-lookup"><span data-stu-id="95a05-265">Worker</span></span>

![Lavoro](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="95a05-267">Lavoro e posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="95a05-267">Job and Job Position</span></span>

![Lavoro e posizione lavorativa](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="95a05-269">Benefit</span><span class="sxs-lookup"><span data-stu-id="95a05-269">Benefits</span></span>

![Benefit](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="95a05-271">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="95a05-271">Compensation</span></span>

![Retribuzione](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="95a05-273">Uscire</span><span class="sxs-lookup"><span data-stu-id="95a05-273">Leave</span></span>

![Uscire](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="95a05-275">Calendario lavorativo</span><span class="sxs-lookup"><span data-stu-id="95a05-275">Work Calendar</span></span>

![Calendario lavorativo](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="95a05-277">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95a05-277">See also</span></span>

[<span data-ttu-id="95a05-278">Scegliere una tecnologia di integrazione dei dati</span><span class="sxs-lookup"><span data-stu-id="95a05-278">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)</br>
[<span data-ttu-id="95a05-279">Configurare l'integrazione di Common Data Service</span><span class="sxs-lookup"><span data-stu-id="95a05-279">Configure Common Data Service integration</span></span>](hr-admin-integration-common-data-service.md)