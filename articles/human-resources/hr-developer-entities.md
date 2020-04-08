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
ms.openlocfilehash: c8e0288da16829c04a9b97c0a52caa8bd27cddf8
ms.sourcegitcommit: fde8045ea49d0cf26d5e7ac5a0da5c0d3d69d5bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2020
ms.locfileid: "3166500"
---
# <a name="common-data-service-entities"></a>Entità di Common Data Service

Microsoft Dynamics 365 Human Resources utilizza Common Data Service per abilitare scenari di estendibilità e integrazione.

Per ulteriori informazioni su Common Data Service, vedere [Che cos'è Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Le seguenti entità di Human Resources sono disponibili in Common Data Service.

## <a name="benefit-entities"></a>Entità Benefit

| Nome | Entità |
| --- | --- |
| Frequenza di calcolo benefit | cdm_benefitcalculationfrequency |
| Periodo retributivo della frequenza di calcolo benefit | cdm_benefitcalculationfrequencypayperiod |
| Coefficiente di calcolo benefit | cdm_benefitcalculationrate |
| Dettagli dei coefficienti di calcolo benefit | cdm_benefitcalculationratedetail |
| Opzione benefit | cdm_benefitoption |
| Piano benefit | cdm_benefitplan (Non abilitato per il supporto del campo personalizzato) |
| Tipo di benefit | cdm_benefittype |

## <a name="business-process-tasks-entities"></a>Entità attività di processi aziendali

| Nome | Entità |
| --- | --- |
| Calendario di processi aziendali | cdm_businessprocesscalendar |
| Assegnazione gruppo di processi aziendali | cdm_businessprocessgroupassignment |
| Gruppo di attività libreria processi aziendali | cdm_businessprocesslibrarytaskgroup |
| Fase di processi aziendali | cdm_businessprocessstage |
| Intestazione modello elenco di controllo | cdm_businessprocesstemplateheader |
| Attività del modello elenco di controllo | cdm_businessprocesstemplatetask |

## <a name="compensation-entities"></a>Entità retribuzione

| Nome | Entità |
| --- | --- |
| Piano di retribuzione fissa | cdm_compensationfixedplan |
| Griglia di retribuzione | cdm_compensationgrid |
| Livello retributivo | cdm_compensationlevel |
| Frequenza della retribuzione | cdm_compensationpayfrequency |
| Impostazione punti di riferimento per le retribuzioni | cdm_compensationreferencepointsetup |
| Riga impostazione punti di riferimento per le retribuzioni | cdm_compensationreferencepointsetupline |
| Paese di retribuzione | cdm_compensationregion |
| Struttura retributiva | cdm_compensationstructure |
| Piano di retribuzione variabile | cdm_compensationvariableplan |
| Livello del piano di retribuzione variabile | cdm_compensationvariableplanlevel |
| Tipo di piano di retribuzione variabile | cdm_compensationvariableplantype |
| Evento di retribuzione fissa | cdm_fixedcompensationevent |
| Regola di distribuzione incentivi | cdm_vestingrule |
| Retribuzione fissa lavoratore | cdm_workerfixedcompensation |

## <a name="organization-entities"></a>Entità Organizzazione

| Nome | Entità |
| --- | --- |
| Reparto | cdm_department |
| Impiego | cdm_employment |
| Società | cdm_company |
| Posizione | cdm_job |
| Funzione lavorativa | cdm_jobfunction |
| Posizione lavorativa | cdm_jobposition |
| Tipo di posizione | cdm_positiontype |
| Assegnazione lavoratore posizione | cdm_positionworkerassignmentmap |
| Dimensione posizione lavorativa | cdm_jobpositiondimension|
| Tipo di posizione | cdm_jobtype |
| Lingua | cdm_language |
| Funzione | cdm_title |

> [!NOTE]
> Le dimensioni finanziarie per **Tipo di posizione**, **Assegnazione lavoratore posizione** e **Impiego** forniscono l'integrazione in una direzione per Common Data Service. Gli aggiornamenti sulle dimensioni finanziarie al momento non vengono sincronizzati da Common Data Service a Human Resources. 

## <a name="leave-and-absence-entities"></a>Entità Congedo e assenza

| Nome | Entità |
| --- | --- |
| Transazione bancaria per congedo | cdm_leavebanktransaction |
| Iscrizione congedo | cdm_leaveenrollment |
| Piano di congedo | cdm_leaveplan |
| Richiesta di congedo | cdm_leaverequest |
| Dettagli richiesta congedo | cdm_leaverequestdetail |
| Tipo di congedo | cdm_leavetype |
| Codice motivo del tipo di congedo | cdm_leavetypereasoncode |

## <a name="payroll-entities"></a>Entità Retribuzioni

| Nome | Entità |
| --- | --- |
| Ciclo retributivo | cdm_paycycle |
| Periodo retributivo | cdm_payperiod |
| Codice di reddito per retribuzione | cdm_payrollearningcode |
| Esborso conto bancario | cdm_bankaccountdisbursement |
| Regione fiscale | cdm_taxregion |

## <a name="worker-entities"></a>Persone giuridiche - Lavoratore

| Nome | Entità |
| --- | --- |
| Lavoro | cdm_worker |
| Indirizzo lavoratore | cdm_workeraddress |
| Dati personali lavoratore | cdm_workerpersonaldetail |
| Numero di identificazione lavoratore | cdm_workerpersonidentificationnumber |
| Tipo di identificazione lavoratore | cdm_workerpersonidentificationtype |
| Calendario lavorativo | cdm_workcalendar |
| Giorno calendario di lavoro | cdm_workcalendarday |
| Festività calendario lavorativo |cdm_workcalendarholiday |
| Riga festività del calendario di lavoro | cdm_workcalendarholidayline |
| Intervallo orario calendario di lavoro | cdm_workcalendartimeinterval (Non abilitato per il supporto del campo personalizzato) |
| Conto bancario del lavoratore | cdm_workerbankaccount |

## <a name="worker-setup-entities"></a>Entità impostazione lavoratore

| Nome | Entità |
| --- | --- |
| Stato di veterano | cdm_veteranstatus |
| Origine etnica | cdm_ethnicorigin |
| Codice causale | cdm_reasoncode |
| Agenzia di rilascio dell'identificazione della persona | cdm_personidentificationissuingagency |

## <a name="competency-entities"></a>Entità competenza

| Nome | Entità |
| --- | --- |
| Tipo di competenza | cdm_skilltype |

## <a name="entity-relationship-models"></a>Modelli di relazioni tra entità

### <a name="worker"></a>Lavoro

![Lavoro](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Lavoro e posizione lavorativa

![Lavoro e posizione lavorativa](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Benefit

![Benefit](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Retribuzione

![Retribuzione](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Uscire

![Uscire](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Calendario lavorativo

![Calendario lavorativo](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>Vedere anche

[Scegliere una tecnologia di integrazione dei dati](hr-admin-integration-choose-technology.md)</br>
[Configurare l'integrazione di Common Data Service](hr-admin-integration-common-data-service.md)
