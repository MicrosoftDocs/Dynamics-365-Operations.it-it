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
ms.openlocfilehash: 988fa0b6d39a49b973626a8a0abe83c546f42297
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4530008"
---
# <a name="common-data-service-entities"></a><span data-ttu-id="907b2-103">Entità di Common Data Service</span><span class="sxs-lookup"><span data-stu-id="907b2-103">Common Data Service entities</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="907b2-104">Microsoft Dynamics 365 Human Resources utilizza Common Data Service per abilitare scenari di estendibilità e integrazione.</span><span class="sxs-lookup"><span data-stu-id="907b2-104">Microsoft Dynamics 365 Human Resources uses Common Data Service to enable extensibility and integration scenarios.</span></span>

<span data-ttu-id="907b2-105">Per ulteriori informazioni su Common Data Service, vedere [Che cos'è Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="907b2-105">For more information about Common Data Service, see [What is Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span>

<span data-ttu-id="907b2-106">Le seguenti entità di Human Resources sono disponibili in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="907b2-106">The following Human Resources entities are available in Common Data Service.</span></span>

## <a name="benefit-entities"></a><span data-ttu-id="907b2-107">Entità Benefit</span><span class="sxs-lookup"><span data-stu-id="907b2-107">Benefit entities</span></span>

| <span data-ttu-id="907b2-108">Nome</span><span class="sxs-lookup"><span data-stu-id="907b2-108">Name</span></span> | <span data-ttu-id="907b2-109">Entità</span><span class="sxs-lookup"><span data-stu-id="907b2-109">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="907b2-110">Frequenza di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="907b2-110">Benefit Calculation Frequency</span></span> | <span data-ttu-id="907b2-111">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="907b2-111">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="907b2-112">Periodo retributivo della frequenza di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="907b2-112">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="907b2-113">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="907b2-113">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="907b2-114">Coefficiente di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="907b2-114">Benefit Calculation Rate</span></span> | <span data-ttu-id="907b2-115">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="907b2-115">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="907b2-116">Dettagli dei coefficienti di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="907b2-116">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="907b2-117">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="907b2-117">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="907b2-118">Opzione benefit</span><span class="sxs-lookup"><span data-stu-id="907b2-118">Benefit Option</span></span> | <span data-ttu-id="907b2-119">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="907b2-119">cdm_benefitoption</span></span> |
| <span data-ttu-id="907b2-120">Piano benefit</span><span class="sxs-lookup"><span data-stu-id="907b2-120">Benefit Plan</span></span> | <span data-ttu-id="907b2-121">cdm_benefitplan (Non abilitato per il supporto del campo personalizzato)</span><span class="sxs-lookup"><span data-stu-id="907b2-121">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="907b2-122">Tipo di benefit</span><span class="sxs-lookup"><span data-stu-id="907b2-122">Benefit Type</span></span> | <span data-ttu-id="907b2-123">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="907b2-123">cdm_benefittype</span></span> |

## <a name="business-process-tasks-entities"></a><span data-ttu-id="907b2-124">Entità attività di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="907b2-124">Business process tasks entities</span></span>

| <span data-ttu-id="907b2-125">Nome</span><span class="sxs-lookup"><span data-stu-id="907b2-125">Name</span></span> | <span data-ttu-id="907b2-126">Entità</span><span class="sxs-lookup"><span data-stu-id="907b2-126">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="907b2-127">Calendario di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="907b2-127">Business Process Calendar</span></span> | <span data-ttu-id="907b2-128">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="907b2-128">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="907b2-129">Assegnazione gruppo di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="907b2-129">Business Process Group Assignment</span></span> | <span data-ttu-id="907b2-130">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="907b2-130">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="907b2-131">Gruppo di attività libreria processi aziendali</span><span class="sxs-lookup"><span data-stu-id="907b2-131">Business Process Library Task Group</span></span> | <span data-ttu-id="907b2-132">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="907b2-132">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="907b2-133">Fase di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="907b2-133">Business Process Stage</span></span> | <span data-ttu-id="907b2-134">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="907b2-134">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="907b2-135">Intestazione modello elenco di controllo</span><span class="sxs-lookup"><span data-stu-id="907b2-135">Checklist Template Header</span></span> | <span data-ttu-id="907b2-136">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="907b2-136">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="907b2-137">Attività del modello elenco di controllo</span><span class="sxs-lookup"><span data-stu-id="907b2-137">Checklist Template Task</span></span> | <span data-ttu-id="907b2-138">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="907b2-138">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-entities"></a><span data-ttu-id="907b2-139">Entità retribuzione</span><span class="sxs-lookup"><span data-stu-id="907b2-139">Compensation entities</span></span>

| <span data-ttu-id="907b2-140">Nome</span><span class="sxs-lookup"><span data-stu-id="907b2-140">Name</span></span> | <span data-ttu-id="907b2-141">Entità</span><span class="sxs-lookup"><span data-stu-id="907b2-141">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="907b2-142">Piano di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="907b2-142">Compensation Fixed Plan</span></span> | <span data-ttu-id="907b2-143">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="907b2-143">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="907b2-144">Griglia di retribuzione</span><span class="sxs-lookup"><span data-stu-id="907b2-144">Compensation Grid</span></span> | <span data-ttu-id="907b2-145">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="907b2-145">cdm_compensationgrid</span></span> |
| <span data-ttu-id="907b2-146">Livello retributivo</span><span class="sxs-lookup"><span data-stu-id="907b2-146">Compensation Level</span></span> | <span data-ttu-id="907b2-147">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="907b2-147">cdm_compensationlevel</span></span> |
| <span data-ttu-id="907b2-148">Frequenza della retribuzione</span><span class="sxs-lookup"><span data-stu-id="907b2-148">Compensation Pay Frequency</span></span> | <span data-ttu-id="907b2-149">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="907b2-149">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="907b2-150">Impostazione punti di riferimento per le retribuzioni</span><span class="sxs-lookup"><span data-stu-id="907b2-150">Compensation Reference Point Setup</span></span> | <span data-ttu-id="907b2-151">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="907b2-151">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="907b2-152">Riga impostazione punti di riferimento per le retribuzioni</span><span class="sxs-lookup"><span data-stu-id="907b2-152">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="907b2-153">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="907b2-153">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="907b2-154">Paese di retribuzione</span><span class="sxs-lookup"><span data-stu-id="907b2-154">Compensation Region</span></span> | <span data-ttu-id="907b2-155">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="907b2-155">cdm_compensationregion</span></span> |
| <span data-ttu-id="907b2-156">Struttura retributiva</span><span class="sxs-lookup"><span data-stu-id="907b2-156">Compensation Structure</span></span> | <span data-ttu-id="907b2-157">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="907b2-157">cdm_compensationstructure</span></span> |
| <span data-ttu-id="907b2-158">Piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="907b2-158">Compensation Variable Plan</span></span> | <span data-ttu-id="907b2-159">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="907b2-159">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="907b2-160">Livello del piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="907b2-160">Compensation Variable Plan Level</span></span> | <span data-ttu-id="907b2-161">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="907b2-161">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="907b2-162">Tipo di piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="907b2-162">Compensation Variable Plan Type</span></span> | <span data-ttu-id="907b2-163">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="907b2-163">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="907b2-164">Evento di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="907b2-164">Fixed Compensation Event</span></span> | <span data-ttu-id="907b2-165">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="907b2-165">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="907b2-166">Regola di distribuzione incentivi</span><span class="sxs-lookup"><span data-stu-id="907b2-166">Vesting Rule</span></span> | <span data-ttu-id="907b2-167">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="907b2-167">cdm_vestingrule</span></span> |
| <span data-ttu-id="907b2-168">Retribuzione fissa lavoratore</span><span class="sxs-lookup"><span data-stu-id="907b2-168">Worker Fixed Compensation</span></span> | <span data-ttu-id="907b2-169">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="907b2-169">cdm_workerfixedcompensation</span></span> |

## <a name="organization-entities"></a><span data-ttu-id="907b2-170">Entità Organizzazione</span><span class="sxs-lookup"><span data-stu-id="907b2-170">Organization entities</span></span>

| <span data-ttu-id="907b2-171">Nome</span><span class="sxs-lookup"><span data-stu-id="907b2-171">Name</span></span> | <span data-ttu-id="907b2-172">Entità</span><span class="sxs-lookup"><span data-stu-id="907b2-172">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="907b2-173">Reparto</span><span class="sxs-lookup"><span data-stu-id="907b2-173">Department</span></span> | <span data-ttu-id="907b2-174">cdm_department</span><span class="sxs-lookup"><span data-stu-id="907b2-174">cdm_department</span></span> |
| <span data-ttu-id="907b2-175">Impiego</span><span class="sxs-lookup"><span data-stu-id="907b2-175">Employment</span></span> | <span data-ttu-id="907b2-176">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="907b2-176">cdm_employment</span></span> |
| <span data-ttu-id="907b2-177">Società</span><span class="sxs-lookup"><span data-stu-id="907b2-177">Company</span></span> | <span data-ttu-id="907b2-178">cdm_company</span><span class="sxs-lookup"><span data-stu-id="907b2-178">cdm_company</span></span> |
| <span data-ttu-id="907b2-179">Posizione</span><span class="sxs-lookup"><span data-stu-id="907b2-179">Job</span></span> | <span data-ttu-id="907b2-180">cdm_job</span><span class="sxs-lookup"><span data-stu-id="907b2-180">cdm_job</span></span> |
| <span data-ttu-id="907b2-181">Funzione lavorativa</span><span class="sxs-lookup"><span data-stu-id="907b2-181">Job Function</span></span> | <span data-ttu-id="907b2-182">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="907b2-182">cdm_jobfunction</span></span> |
| <span data-ttu-id="907b2-183">Posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="907b2-183">Job Position</span></span> | <span data-ttu-id="907b2-184">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="907b2-184">cdm_jobposition</span></span> |
| <span data-ttu-id="907b2-185">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="907b2-185">Position Type</span></span> | <span data-ttu-id="907b2-186">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="907b2-186">cdm_positiontype</span></span> |
| <span data-ttu-id="907b2-187">Assegnazione lavoratore posizione</span><span class="sxs-lookup"><span data-stu-id="907b2-187">Position Worker Assignment</span></span> | <span data-ttu-id="907b2-188">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="907b2-188">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="907b2-189">Dimensione posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="907b2-189">Job Position Dimension</span></span> | <span data-ttu-id="907b2-190">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="907b2-190">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="907b2-191">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="907b2-191">Job Type</span></span> | <span data-ttu-id="907b2-192">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="907b2-192">cdm_jobtype</span></span> |
| <span data-ttu-id="907b2-193">Lingua</span><span class="sxs-lookup"><span data-stu-id="907b2-193">Language</span></span> | <span data-ttu-id="907b2-194">cdm_language</span><span class="sxs-lookup"><span data-stu-id="907b2-194">cdm_language</span></span> |
| <span data-ttu-id="907b2-195">Funzione</span><span class="sxs-lookup"><span data-stu-id="907b2-195">Title</span></span> | <span data-ttu-id="907b2-196">cdm_title</span><span class="sxs-lookup"><span data-stu-id="907b2-196">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="907b2-197">Le dimensioni finanziarie per **Tipo di posizione**, **Assegnazione lavoratore posizione** e **Impiego** forniscono l'integrazione in una direzione per Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="907b2-197">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Common Data Service.</span></span> <span data-ttu-id="907b2-198">Gli aggiornamenti sulle dimensioni finanziarie al momento non vengono sincronizzati da Common Data Service a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="907b2-198">Financial dimensions updates currently can't synchronize from Common Data Service to Human Resources.</span></span> 

## <a name="leave-and-absence-entities"></a><span data-ttu-id="907b2-199">Entità Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="907b2-199">Leave and absence entities</span></span>

| <span data-ttu-id="907b2-200">Nome</span><span class="sxs-lookup"><span data-stu-id="907b2-200">Name</span></span> | <span data-ttu-id="907b2-201">Entità</span><span class="sxs-lookup"><span data-stu-id="907b2-201">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="907b2-202">Transazione bancaria per congedo</span><span class="sxs-lookup"><span data-stu-id="907b2-202">Leave Bank Transaction</span></span> | <span data-ttu-id="907b2-203">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="907b2-203">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="907b2-204">Iscrizione congedo</span><span class="sxs-lookup"><span data-stu-id="907b2-204">Leave Enrollment</span></span> | <span data-ttu-id="907b2-205">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="907b2-205">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="907b2-206">Piano di congedo</span><span class="sxs-lookup"><span data-stu-id="907b2-206">Leave Plan</span></span> | <span data-ttu-id="907b2-207">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="907b2-207">cdm_leaveplan</span></span> |
| <span data-ttu-id="907b2-208">Richiesta di congedo</span><span class="sxs-lookup"><span data-stu-id="907b2-208">Leave Request</span></span> | <span data-ttu-id="907b2-209">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="907b2-209">cdm_leaverequest</span></span> |
| <span data-ttu-id="907b2-210">Dettagli richiesta congedo</span><span class="sxs-lookup"><span data-stu-id="907b2-210">Leave Request Detail</span></span> | <span data-ttu-id="907b2-211">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="907b2-211">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="907b2-212">Tipo di congedo</span><span class="sxs-lookup"><span data-stu-id="907b2-212">Leave Type</span></span> | <span data-ttu-id="907b2-213">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="907b2-213">cdm_leavetype</span></span> |
| <span data-ttu-id="907b2-214">Codice motivo del tipo di congedo</span><span class="sxs-lookup"><span data-stu-id="907b2-214">Leave Type Reason Code</span></span> | <span data-ttu-id="907b2-215">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="907b2-215">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-entities"></a><span data-ttu-id="907b2-216">Entità Retribuzioni</span><span class="sxs-lookup"><span data-stu-id="907b2-216">Payroll entities</span></span>

| <span data-ttu-id="907b2-217">Nome</span><span class="sxs-lookup"><span data-stu-id="907b2-217">Name</span></span> | <span data-ttu-id="907b2-218">Entità</span><span class="sxs-lookup"><span data-stu-id="907b2-218">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="907b2-219">Ciclo retributivo</span><span class="sxs-lookup"><span data-stu-id="907b2-219">Pay Cycle</span></span> | <span data-ttu-id="907b2-220">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="907b2-220">cdm_paycycle</span></span> |
| <span data-ttu-id="907b2-221">Periodo retributivo</span><span class="sxs-lookup"><span data-stu-id="907b2-221">Pay Period</span></span> | <span data-ttu-id="907b2-222">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="907b2-222">cdm_payperiod</span></span> |
| <span data-ttu-id="907b2-223">Codice di reddito per retribuzione</span><span class="sxs-lookup"><span data-stu-id="907b2-223">Payroll Earning Code</span></span> | <span data-ttu-id="907b2-224">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="907b2-224">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="907b2-225">Esborso conto bancario</span><span class="sxs-lookup"><span data-stu-id="907b2-225">Bank Account Disbursement</span></span> | <span data-ttu-id="907b2-226">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="907b2-226">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="907b2-227">Regione fiscale</span><span class="sxs-lookup"><span data-stu-id="907b2-227">Tax Region</span></span> | <span data-ttu-id="907b2-228">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="907b2-228">cdm_taxregion</span></span> |

## <a name="worker-entities"></a><span data-ttu-id="907b2-229">Persone giuridiche - Lavoratore</span><span class="sxs-lookup"><span data-stu-id="907b2-229">Worker entities</span></span>

| <span data-ttu-id="907b2-230">Nome</span><span class="sxs-lookup"><span data-stu-id="907b2-230">Name</span></span> | <span data-ttu-id="907b2-231">Entità</span><span class="sxs-lookup"><span data-stu-id="907b2-231">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="907b2-232">Lavoro</span><span class="sxs-lookup"><span data-stu-id="907b2-232">Worker</span></span> | <span data-ttu-id="907b2-233">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="907b2-233">cdm_worker</span></span> |
| <span data-ttu-id="907b2-234">Indirizzo lavoratore</span><span class="sxs-lookup"><span data-stu-id="907b2-234">Worker Address</span></span> | <span data-ttu-id="907b2-235">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="907b2-235">cdm_workeraddress</span></span> |
| <span data-ttu-id="907b2-236">Dati personali lavoratore</span><span class="sxs-lookup"><span data-stu-id="907b2-236">Worker Personal Detail</span></span> | <span data-ttu-id="907b2-237">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="907b2-237">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="907b2-238">Numero di identificazione lavoratore</span><span class="sxs-lookup"><span data-stu-id="907b2-238">Worker Person Identification Number</span></span> | <span data-ttu-id="907b2-239">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="907b2-239">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="907b2-240">Tipo di identificazione lavoratore</span><span class="sxs-lookup"><span data-stu-id="907b2-240">Worker Person Identification Type</span></span> | <span data-ttu-id="907b2-241">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="907b2-241">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="907b2-242">Calendario lavorativo</span><span class="sxs-lookup"><span data-stu-id="907b2-242">Work Calendar</span></span> | <span data-ttu-id="907b2-243">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="907b2-243">cdm_workcalendar</span></span> |
| <span data-ttu-id="907b2-244">Giorno calendario di lavoro</span><span class="sxs-lookup"><span data-stu-id="907b2-244">Work Calendar Day</span></span> | <span data-ttu-id="907b2-245">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="907b2-245">cdm_workcalendarday</span></span> |
| <span data-ttu-id="907b2-246">Festività calendario lavorativo</span><span class="sxs-lookup"><span data-stu-id="907b2-246">Work Calendar Holiday</span></span> |<span data-ttu-id="907b2-247">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="907b2-247">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="907b2-248">Riga festività del calendario di lavoro</span><span class="sxs-lookup"><span data-stu-id="907b2-248">Work Calendar Holiday Line</span></span> | <span data-ttu-id="907b2-249">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="907b2-249">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="907b2-250">Intervallo orario calendario di lavoro</span><span class="sxs-lookup"><span data-stu-id="907b2-250">Work Calendar Time Interval</span></span> | <span data-ttu-id="907b2-251">cdm_workcalendartimeinterval (Non abilitato per il supporto del campo personalizzato)</span><span class="sxs-lookup"><span data-stu-id="907b2-251">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="907b2-252">Conto bancario del lavoratore</span><span class="sxs-lookup"><span data-stu-id="907b2-252">Worker Bank Account</span></span> | <span data-ttu-id="907b2-253">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="907b2-253">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-entities"></a><span data-ttu-id="907b2-254">Entità impostazione lavoratore</span><span class="sxs-lookup"><span data-stu-id="907b2-254">Worker setup entities</span></span>

| <span data-ttu-id="907b2-255">Nome</span><span class="sxs-lookup"><span data-stu-id="907b2-255">Name</span></span> | <span data-ttu-id="907b2-256">Entità</span><span class="sxs-lookup"><span data-stu-id="907b2-256">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="907b2-257">Stato di veterano</span><span class="sxs-lookup"><span data-stu-id="907b2-257">Veteran Status</span></span> | <span data-ttu-id="907b2-258">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="907b2-258">cdm_veteranstatus</span></span> |
| <span data-ttu-id="907b2-259">Origine etnica</span><span class="sxs-lookup"><span data-stu-id="907b2-259">Ethnic Origin</span></span> | <span data-ttu-id="907b2-260">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="907b2-260">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="907b2-261">Codice causale</span><span class="sxs-lookup"><span data-stu-id="907b2-261">Reason Code</span></span> | <span data-ttu-id="907b2-262">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="907b2-262">cdm_reasoncode</span></span> |
| <span data-ttu-id="907b2-263">Agenzia di rilascio dell'identificazione della persona</span><span class="sxs-lookup"><span data-stu-id="907b2-263">Person Identification Issuing Agency</span></span> | <span data-ttu-id="907b2-264">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="907b2-264">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-entities"></a><span data-ttu-id="907b2-265">Entità competenza</span><span class="sxs-lookup"><span data-stu-id="907b2-265">Competency entities</span></span>

| <span data-ttu-id="907b2-266">Nome</span><span class="sxs-lookup"><span data-stu-id="907b2-266">Name</span></span> | <span data-ttu-id="907b2-267">Entità</span><span class="sxs-lookup"><span data-stu-id="907b2-267">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="907b2-268">Tipo di competenza</span><span class="sxs-lookup"><span data-stu-id="907b2-268">Skill Type</span></span> | <span data-ttu-id="907b2-269">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="907b2-269">cdm_skilltype</span></span> |

## <a name="entity-relationship-models"></a><span data-ttu-id="907b2-270">Modelli di relazioni tra entità</span><span class="sxs-lookup"><span data-stu-id="907b2-270">Entity relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="907b2-271">Lavoro</span><span class="sxs-lookup"><span data-stu-id="907b2-271">Worker</span></span>

![Lavoro](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="907b2-273">Lavoro e posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="907b2-273">Job and Job Position</span></span>

![Lavoro e posizione lavorativa](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="907b2-275">Benefit</span><span class="sxs-lookup"><span data-stu-id="907b2-275">Benefits</span></span>

![Benefit](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="907b2-277">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="907b2-277">Compensation</span></span>

![Retribuzione](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="907b2-279">Uscire</span><span class="sxs-lookup"><span data-stu-id="907b2-279">Leave</span></span>

![Uscire](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="907b2-281">Calendario lavorativo</span><span class="sxs-lookup"><span data-stu-id="907b2-281">Work Calendar</span></span>

![Calendario lavorativo](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="907b2-283">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="907b2-283">See also</span></span>

[<span data-ttu-id="907b2-284">Scegliere una tecnologia di integrazione dei dati</span><span class="sxs-lookup"><span data-stu-id="907b2-284">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)</br>
[<span data-ttu-id="907b2-285">Configurare l'integrazione di Common Data Service</span><span class="sxs-lookup"><span data-stu-id="907b2-285">Configure Common Data Service integration</span></span>](hr-admin-integration-common-data-service.md)
