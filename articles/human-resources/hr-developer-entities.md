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
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 325bd8a9de07e3978ff6c513975a0e8db22854e0
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054358"
---
# <a name="dataverse-tables"></a><span data-ttu-id="88455-103">Tabelle Dataverse</span><span class="sxs-lookup"><span data-stu-id="88455-103">Dataverse tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="88455-104">Microsoft Dynamics 365 Human Resources utilizza Dataverse per abilitare scenari di estendibilità e integrazione.</span><span class="sxs-lookup"><span data-stu-id="88455-104">Microsoft Dynamics 365 Human Resources uses Dataverse to enable extensibility and integration scenarios.</span></span>

> [!NOTE]
> <span data-ttu-id="88455-105">Le entità di Human Resources corrispondono alle tabelle Dataverse.</span><span class="sxs-lookup"><span data-stu-id="88455-105">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="88455-106">Per ulteriori informazioni su Dataverse (in precedenza Common Data Service) e aggiornamenti terminologici, vedi [ Cosa è Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="88455-106">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="88455-107">Le seguenti tabelle Dataverse sono disponibili in base alle entità di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="88455-107">The following Dataverse tables are available based on Human Resources entities.</span></span>

## <a name="benefit-tables"></a><span data-ttu-id="88455-108">Tabelle dei benefit</span><span class="sxs-lookup"><span data-stu-id="88455-108">Benefit tables</span></span>

| <span data-ttu-id="88455-109">Nome</span><span class="sxs-lookup"><span data-stu-id="88455-109">Name</span></span> | <span data-ttu-id="88455-110">Tabella</span><span class="sxs-lookup"><span data-stu-id="88455-110">Table</span></span> |
| --- | --- |
| <span data-ttu-id="88455-111">Frequenza di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="88455-111">Benefit Calculation Frequency</span></span> | <span data-ttu-id="88455-112">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="88455-112">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="88455-113">Periodo retributivo della frequenza di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="88455-113">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="88455-114">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="88455-114">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="88455-115">Coefficiente di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="88455-115">Benefit Calculation Rate</span></span> | <span data-ttu-id="88455-116">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="88455-116">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="88455-117">Dettagli dei coefficienti di calcolo benefit</span><span class="sxs-lookup"><span data-stu-id="88455-117">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="88455-118">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="88455-118">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="88455-119">Opzione benefit</span><span class="sxs-lookup"><span data-stu-id="88455-119">Benefit Option</span></span> | <span data-ttu-id="88455-120">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="88455-120">cdm_benefitoption</span></span> |
| <span data-ttu-id="88455-121">Piano benefit</span><span class="sxs-lookup"><span data-stu-id="88455-121">Benefit Plan</span></span> | <span data-ttu-id="88455-122">cdm_benefitplan (Non abilitato per il supporto del campo personalizzato)</span><span class="sxs-lookup"><span data-stu-id="88455-122">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="88455-123">Tipo di benefit</span><span class="sxs-lookup"><span data-stu-id="88455-123">Benefit Type</span></span> | <span data-ttu-id="88455-124">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="88455-124">cdm_benefittype</span></span> |

## <a name="business-process-tasks-tables"></a><span data-ttu-id="88455-125">Tabelle attività di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="88455-125">Business process tasks tables</span></span>

| <span data-ttu-id="88455-126">Nome</span><span class="sxs-lookup"><span data-stu-id="88455-126">Name</span></span> | <span data-ttu-id="88455-127">Tabella</span><span class="sxs-lookup"><span data-stu-id="88455-127">Table</span></span> |
| --- | --- |
| <span data-ttu-id="88455-128">Calendario di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="88455-128">Business Process Calendar</span></span> | <span data-ttu-id="88455-129">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="88455-129">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="88455-130">Assegnazione gruppo di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="88455-130">Business Process Group Assignment</span></span> | <span data-ttu-id="88455-131">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="88455-131">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="88455-132">Gruppo di attività libreria processi aziendali</span><span class="sxs-lookup"><span data-stu-id="88455-132">Business Process Library Task Group</span></span> | <span data-ttu-id="88455-133">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="88455-133">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="88455-134">Fase di processi aziendali</span><span class="sxs-lookup"><span data-stu-id="88455-134">Business Process Stage</span></span> | <span data-ttu-id="88455-135">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="88455-135">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="88455-136">Intestazione modello elenco di controllo</span><span class="sxs-lookup"><span data-stu-id="88455-136">Checklist Template Header</span></span> | <span data-ttu-id="88455-137">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="88455-137">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="88455-138">Attività del modello elenco di controllo</span><span class="sxs-lookup"><span data-stu-id="88455-138">Checklist Template Task</span></span> | <span data-ttu-id="88455-139">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="88455-139">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-tables"></a><span data-ttu-id="88455-140">Tabelle retribuzioni</span><span class="sxs-lookup"><span data-stu-id="88455-140">Compensation tables</span></span>

| <span data-ttu-id="88455-141">Nome</span><span class="sxs-lookup"><span data-stu-id="88455-141">Name</span></span> | <span data-ttu-id="88455-142">Tabella</span><span class="sxs-lookup"><span data-stu-id="88455-142">Table</span></span> |
| --- | --- |
| <span data-ttu-id="88455-143">Piano di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="88455-143">Compensation Fixed Plan</span></span> | <span data-ttu-id="88455-144">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="88455-144">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="88455-145">Griglia di retribuzione</span><span class="sxs-lookup"><span data-stu-id="88455-145">Compensation Grid</span></span> | <span data-ttu-id="88455-146">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="88455-146">cdm_compensationgrid</span></span> |
| <span data-ttu-id="88455-147">Livello retributivo</span><span class="sxs-lookup"><span data-stu-id="88455-147">Compensation Level</span></span> | <span data-ttu-id="88455-148">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="88455-148">cdm_compensationlevel</span></span> |
| <span data-ttu-id="88455-149">Frequenza della retribuzione</span><span class="sxs-lookup"><span data-stu-id="88455-149">Compensation Pay Frequency</span></span> | <span data-ttu-id="88455-150">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="88455-150">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="88455-151">Impostazione punti di riferimento per le retribuzioni</span><span class="sxs-lookup"><span data-stu-id="88455-151">Compensation Reference Point Setup</span></span> | <span data-ttu-id="88455-152">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="88455-152">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="88455-153">Riga impostazione punti di riferimento per le retribuzioni</span><span class="sxs-lookup"><span data-stu-id="88455-153">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="88455-154">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="88455-154">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="88455-155">Paese di retribuzione</span><span class="sxs-lookup"><span data-stu-id="88455-155">Compensation Region</span></span> | <span data-ttu-id="88455-156">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="88455-156">cdm_compensationregion</span></span> |
| <span data-ttu-id="88455-157">Struttura retributiva</span><span class="sxs-lookup"><span data-stu-id="88455-157">Compensation Structure</span></span> | <span data-ttu-id="88455-158">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="88455-158">cdm_compensationstructure</span></span> |
| <span data-ttu-id="88455-159">Piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="88455-159">Compensation Variable Plan</span></span> | <span data-ttu-id="88455-160">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="88455-160">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="88455-161">Livello del piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="88455-161">Compensation Variable Plan Level</span></span> | <span data-ttu-id="88455-162">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="88455-162">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="88455-163">Tipo di piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="88455-163">Compensation Variable Plan Type</span></span> | <span data-ttu-id="88455-164">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="88455-164">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="88455-165">Evento di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="88455-165">Fixed Compensation Event</span></span> | <span data-ttu-id="88455-166">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="88455-166">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="88455-167">Regola di distribuzione incentivi</span><span class="sxs-lookup"><span data-stu-id="88455-167">Vesting Rule</span></span> | <span data-ttu-id="88455-168">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="88455-168">cdm_vestingrule</span></span> |
| <span data-ttu-id="88455-169">Retribuzione fissa del lavoratore</span><span class="sxs-lookup"><span data-stu-id="88455-169">Worker Fixed Compensation</span></span> | <span data-ttu-id="88455-170">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="88455-170">cdm_workerfixedcompensation</span></span> |

## <a name="organization-tables"></a><span data-ttu-id="88455-171">Tabelle organizzazione</span><span class="sxs-lookup"><span data-stu-id="88455-171">Organization tables</span></span>

| <span data-ttu-id="88455-172">Nome</span><span class="sxs-lookup"><span data-stu-id="88455-172">Name</span></span> | <span data-ttu-id="88455-173">Tabella</span><span class="sxs-lookup"><span data-stu-id="88455-173">Table</span></span> |
| --- | --- |
| <span data-ttu-id="88455-174">Reparto</span><span class="sxs-lookup"><span data-stu-id="88455-174">Department</span></span> | <span data-ttu-id="88455-175">cdm_department</span><span class="sxs-lookup"><span data-stu-id="88455-175">cdm_department</span></span> |
| <span data-ttu-id="88455-176">Impiego</span><span class="sxs-lookup"><span data-stu-id="88455-176">Employment</span></span> | <span data-ttu-id="88455-177">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="88455-177">cdm_employment</span></span> |
| <span data-ttu-id="88455-178">Società</span><span class="sxs-lookup"><span data-stu-id="88455-178">Company</span></span> | <span data-ttu-id="88455-179">cdm_company</span><span class="sxs-lookup"><span data-stu-id="88455-179">cdm_company</span></span> |
| <span data-ttu-id="88455-180">Posizione</span><span class="sxs-lookup"><span data-stu-id="88455-180">Job</span></span> | <span data-ttu-id="88455-181">cdm_job</span><span class="sxs-lookup"><span data-stu-id="88455-181">cdm_job</span></span> |
| <span data-ttu-id="88455-182">Funzione lavorativa</span><span class="sxs-lookup"><span data-stu-id="88455-182">Job Function</span></span> | <span data-ttu-id="88455-183">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="88455-183">cdm_jobfunction</span></span> |
| <span data-ttu-id="88455-184">Posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="88455-184">Job Position</span></span> | <span data-ttu-id="88455-185">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="88455-185">cdm_jobposition</span></span> |
| <span data-ttu-id="88455-186">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="88455-186">Position Type</span></span> | <span data-ttu-id="88455-187">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="88455-187">cdm_positiontype</span></span> |
| <span data-ttu-id="88455-188">Assegnazione lavoratore posizione</span><span class="sxs-lookup"><span data-stu-id="88455-188">Position Worker Assignment</span></span> | <span data-ttu-id="88455-189">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="88455-189">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="88455-190">Dimensione posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="88455-190">Job Position Dimension</span></span> | <span data-ttu-id="88455-191">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="88455-191">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="88455-192">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="88455-192">Job Type</span></span> | <span data-ttu-id="88455-193">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="88455-193">cdm_jobtype</span></span> |
| <span data-ttu-id="88455-194">Lingua</span><span class="sxs-lookup"><span data-stu-id="88455-194">Language</span></span> | <span data-ttu-id="88455-195">cdm_language</span><span class="sxs-lookup"><span data-stu-id="88455-195">cdm_language</span></span> |
| <span data-ttu-id="88455-196">Funzione</span><span class="sxs-lookup"><span data-stu-id="88455-196">Title</span></span> | <span data-ttu-id="88455-197">cdm_title</span><span class="sxs-lookup"><span data-stu-id="88455-197">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="88455-198">Le dimensioni finanziarie per **Tipo di posizione**, **Assegnazione lavoratore posizione** e **Impiego** forniscono l'integrazione in una direzione per Dataverse.</span><span class="sxs-lookup"><span data-stu-id="88455-198">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Dataverse.</span></span> <span data-ttu-id="88455-199">Gli aggiornamenti sulle dimensioni finanziarie al momento non vengono sincronizzati da Dataverse a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="88455-199">Financial dimensions updates currently can't synchronize from Dataverse to Human Resources.</span></span> 

## <a name="leave-and-absence-tables"></a><span data-ttu-id="88455-200">Tabelle congedi e assenze</span><span class="sxs-lookup"><span data-stu-id="88455-200">Leave and absence tables</span></span>

| <span data-ttu-id="88455-201">Nome</span><span class="sxs-lookup"><span data-stu-id="88455-201">Name</span></span> | <span data-ttu-id="88455-202">Tabella</span><span class="sxs-lookup"><span data-stu-id="88455-202">Table</span></span> |
| --- | --- |
| <span data-ttu-id="88455-203">Transazione bancaria per congedo</span><span class="sxs-lookup"><span data-stu-id="88455-203">Leave Bank Transaction</span></span> | <span data-ttu-id="88455-204">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="88455-204">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="88455-205">Iscrizione al piano di congedo</span><span class="sxs-lookup"><span data-stu-id="88455-205">Leave Enrollment</span></span> | <span data-ttu-id="88455-206">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="88455-206">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="88455-207">Piano di congedo</span><span class="sxs-lookup"><span data-stu-id="88455-207">Leave Plan</span></span> | <span data-ttu-id="88455-208">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="88455-208">cdm_leaveplan</span></span> |
| <span data-ttu-id="88455-209">Richiesta di congedo</span><span class="sxs-lookup"><span data-stu-id="88455-209">Leave Request</span></span> | <span data-ttu-id="88455-210">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="88455-210">cdm_leaverequest</span></span> |
| <span data-ttu-id="88455-211">Dettagli richiesta congedo</span><span class="sxs-lookup"><span data-stu-id="88455-211">Leave Request Detail</span></span> | <span data-ttu-id="88455-212">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="88455-212">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="88455-213">Tipo di congedo</span><span class="sxs-lookup"><span data-stu-id="88455-213">Leave Type</span></span> | <span data-ttu-id="88455-214">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="88455-214">cdm_leavetype</span></span> |
| <span data-ttu-id="88455-215">Codice motivo del tipo di congedo</span><span class="sxs-lookup"><span data-stu-id="88455-215">Leave Type Reason Code</span></span> | <span data-ttu-id="88455-216">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="88455-216">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-tables"></a><span data-ttu-id="88455-217">Tabelle retribuzioni</span><span class="sxs-lookup"><span data-stu-id="88455-217">Payroll tables</span></span>

| <span data-ttu-id="88455-218">Nome</span><span class="sxs-lookup"><span data-stu-id="88455-218">Name</span></span> | <span data-ttu-id="88455-219">Tabella</span><span class="sxs-lookup"><span data-stu-id="88455-219">Table</span></span> |
| --- | --- |
| <span data-ttu-id="88455-220">Ciclo retributivo</span><span class="sxs-lookup"><span data-stu-id="88455-220">Pay Cycle</span></span> | <span data-ttu-id="88455-221">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="88455-221">cdm_paycycle</span></span> |
| <span data-ttu-id="88455-222">Periodo retributivo</span><span class="sxs-lookup"><span data-stu-id="88455-222">Pay Period</span></span> | <span data-ttu-id="88455-223">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="88455-223">cdm_payperiod</span></span> |
| <span data-ttu-id="88455-224">Codice di reddito retribuzioni</span><span class="sxs-lookup"><span data-stu-id="88455-224">Payroll Earning Code</span></span> | <span data-ttu-id="88455-225">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="88455-225">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="88455-226">Esborso conto bancario</span><span class="sxs-lookup"><span data-stu-id="88455-226">Bank Account Disbursement</span></span> | <span data-ttu-id="88455-227">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="88455-227">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="88455-228">Regione fiscale</span><span class="sxs-lookup"><span data-stu-id="88455-228">Tax Region</span></span> | <span data-ttu-id="88455-229">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="88455-229">cdm_taxregion</span></span> |

## <a name="worker-tables"></a><span data-ttu-id="88455-230">Tabelle lavoratori</span><span class="sxs-lookup"><span data-stu-id="88455-230">Worker tables</span></span>

| <span data-ttu-id="88455-231">Nome</span><span class="sxs-lookup"><span data-stu-id="88455-231">Name</span></span> | <span data-ttu-id="88455-232">Tabella</span><span class="sxs-lookup"><span data-stu-id="88455-232">Table</span></span> |
| --- | --- |
| <span data-ttu-id="88455-233">Lavoro</span><span class="sxs-lookup"><span data-stu-id="88455-233">Worker</span></span> | <span data-ttu-id="88455-234">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="88455-234">cdm_worker</span></span> |
| <span data-ttu-id="88455-235">Indirizzo del lavoratore</span><span class="sxs-lookup"><span data-stu-id="88455-235">Worker Address</span></span> | <span data-ttu-id="88455-236">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="88455-236">cdm_workeraddress</span></span> |
| <span data-ttu-id="88455-237">Dati personali lavoratore</span><span class="sxs-lookup"><span data-stu-id="88455-237">Worker Personal Detail</span></span> | <span data-ttu-id="88455-238">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="88455-238">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="88455-239">Numero di identificazione lavoratore</span><span class="sxs-lookup"><span data-stu-id="88455-239">Worker Person Identification Number</span></span> | <span data-ttu-id="88455-240">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="88455-240">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="88455-241">Tipo di identificazione lavoratore</span><span class="sxs-lookup"><span data-stu-id="88455-241">Worker Person Identification Type</span></span> | <span data-ttu-id="88455-242">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="88455-242">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="88455-243">Calendario lavorativo</span><span class="sxs-lookup"><span data-stu-id="88455-243">Work Calendar</span></span> | <span data-ttu-id="88455-244">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="88455-244">cdm_workcalendar</span></span> |
| <span data-ttu-id="88455-245">Giorno calendario di lavoro</span><span class="sxs-lookup"><span data-stu-id="88455-245">Work Calendar Day</span></span> | <span data-ttu-id="88455-246">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="88455-246">cdm_workcalendarday</span></span> |
| <span data-ttu-id="88455-247">Festività calendario lavorativo</span><span class="sxs-lookup"><span data-stu-id="88455-247">Work Calendar Holiday</span></span> |<span data-ttu-id="88455-248">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="88455-248">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="88455-249">Riga festività del calendario di lavoro</span><span class="sxs-lookup"><span data-stu-id="88455-249">Work Calendar Holiday Line</span></span> | <span data-ttu-id="88455-250">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="88455-250">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="88455-251">Intervallo orario calendario di lavoro</span><span class="sxs-lookup"><span data-stu-id="88455-251">Work Calendar Time Interval</span></span> | <span data-ttu-id="88455-252">cdm_workcalendartimeinterval (Non abilitato per il supporto del campo personalizzato)</span><span class="sxs-lookup"><span data-stu-id="88455-252">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="88455-253">Conto bancario del lavoratore</span><span class="sxs-lookup"><span data-stu-id="88455-253">Worker Bank Account</span></span> | <span data-ttu-id="88455-254">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="88455-254">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-tables"></a><span data-ttu-id="88455-255">Tabelle di configurazione dei lavoratori</span><span class="sxs-lookup"><span data-stu-id="88455-255">Worker setup tables</span></span>

| <span data-ttu-id="88455-256">Nome</span><span class="sxs-lookup"><span data-stu-id="88455-256">Name</span></span> | <span data-ttu-id="88455-257">Tabella</span><span class="sxs-lookup"><span data-stu-id="88455-257">Table</span></span> |
| --- | --- |
| <span data-ttu-id="88455-258">Stato veterano</span><span class="sxs-lookup"><span data-stu-id="88455-258">Veteran Status</span></span> | <span data-ttu-id="88455-259">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="88455-259">cdm_veteranstatus</span></span> |
| <span data-ttu-id="88455-260">Origine etnica</span><span class="sxs-lookup"><span data-stu-id="88455-260">Ethnic Origin</span></span> | <span data-ttu-id="88455-261">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="88455-261">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="88455-262">Codice causale</span><span class="sxs-lookup"><span data-stu-id="88455-262">Reason Code</span></span> | <span data-ttu-id="88455-263">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="88455-263">cdm_reasoncode</span></span> |
| <span data-ttu-id="88455-264">Agenzia emittente dell'identificazione personale.</span><span class="sxs-lookup"><span data-stu-id="88455-264">Person Identification Issuing Agency</span></span> | <span data-ttu-id="88455-265">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="88455-265">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-tables"></a><span data-ttu-id="88455-266">Tabelle delle competenze</span><span class="sxs-lookup"><span data-stu-id="88455-266">Competency tables</span></span>

| <span data-ttu-id="88455-267">Nome</span><span class="sxs-lookup"><span data-stu-id="88455-267">Name</span></span> | <span data-ttu-id="88455-268">Tabella</span><span class="sxs-lookup"><span data-stu-id="88455-268">Table</span></span> |
| --- | --- |
| <span data-ttu-id="88455-269">Tipo di competenza</span><span class="sxs-lookup"><span data-stu-id="88455-269">Skill Type</span></span> | <span data-ttu-id="88455-270">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="88455-270">cdm_skilltype</span></span> |

## <a name="table-relationship-models"></a><span data-ttu-id="88455-271">Modelli di relazioni tra tabelle</span><span class="sxs-lookup"><span data-stu-id="88455-271">Table relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="88455-272">Lavoro</span><span class="sxs-lookup"><span data-stu-id="88455-272">Worker</span></span>

![Lavoro](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="88455-274">Lavoro e posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="88455-274">Job and Job Position</span></span>

![Lavoro e posizione lavorativa](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="88455-276">Benefit</span><span class="sxs-lookup"><span data-stu-id="88455-276">Benefits</span></span>

![Benefit](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="88455-278">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="88455-278">Compensation</span></span>

![Retribuzione](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="88455-280">Uscire</span><span class="sxs-lookup"><span data-stu-id="88455-280">Leave</span></span>

![Uscire](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="88455-282">Calendario lavorativo</span><span class="sxs-lookup"><span data-stu-id="88455-282">Work Calendar</span></span>

![Calendario lavorativo](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="88455-284">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88455-284">See also</span></span>

[<span data-ttu-id="88455-285">Scegliere una tecnologia di integrazione dei dati</span><span class="sxs-lookup"><span data-stu-id="88455-285">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)<br>
[<span data-ttu-id="88455-286">Configurare l'integrazione di Dataverse</span><span class="sxs-lookup"><span data-stu-id="88455-286">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)<br>
[<span data-ttu-id="88455-287">Configurare tabelle virtuali in Dataverse</span><span class="sxs-lookup"><span data-stu-id="88455-287">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="88455-288">Domande frequenti sulle tabelle virtuali in Human Resources</span><span class="sxs-lookup"><span data-stu-id="88455-288">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="88455-289">Che cos'è Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="88455-289">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="88455-290">Aggiornamenti terminologici</span><span class="sxs-lookup"><span data-stu-id="88455-290">Terminology updates</span></span>](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]