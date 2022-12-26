---
title: Configurare l'integrazione con le tabelle di Dataverse
description: Questo articolo descrive l'integrazione tra Microsoft Dynamics 365 Human Resources e Dataverse.
author: anschmidt
ms.date: 12/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63c25020b7026a76ecc6e2c3563f8299627ec8a8
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838626"
---
# <a name="configure-integration-with-dataverse-tables"></a>Configurare l'integrazione con le tabelle di Dataverse

>[!Important]
>La funzionalità indicata in questo articolo è attualmente disponibile per i clienti di Dynamics 365 Human Resources nell'infrastruttura delle app per la finanza e le operazioni. 


Per integrare Microsoft Dynamics 365 Human Resources con Dataverse, puoi utilizzare il [Servizio di integrazione di dati](/powerapps/administrator/data-integrator). Il modello Da Human Resources a Dataverse consente ai dati relativi a lavori, posizioni, lavoratori e altri di fluire da Human Resources a Dataverse e da Dataverse a Human Resources, creando una scrittura in entrambi i sistemi.

## <a name="system-requirements-for-human-resources"></a>Requisiti di sistema per Human Resources

La soluzione di integrazione richiede le seguenti versioni di Human Resources e Dynamics 365 Finance: 

- Dynamics 365 Finance versione 7.2 e successive
- Ambiente Dynamics CRM in cui è stato creato un database e sono consentite le app Dynamics 365

## <a name="template-and-tasks"></a>Modello e attività

Segui questi passaggi per accedere al modello da Human Resources a Finance.

1. Apri l'[interfaccia di amministrazione di Power Apps](https://admin.powerapps.com/). 
2. Nel tuo ambiente, seleziona **App Dynamics 365**, quindi seleziona **Origine app** sulla barra degli strumenti.
3. Per installare il modello, cerca "Human Resources a doppia scrittura" o vai direttamente al seguente indirizzo: <https://appsource.microsoft.com/product/dynamics-365/mscrm.hcm_dualwrite>.
3. Al termine dell'installazione, apri Dynamics 365 Finance.
4. Aprire l'area di lavoro **Gestione dati**. 
5. Seleziona **Doppia scrittura**. 
6. Segui il processo per collegare il tuo ambiente per almeno un'azienda nella tua organizzazione. 
7. Quando hai finito di impostare un collegamento al tuo ambiente Dataverse seleziona **Applica soluzione**. La soluzione viene applicata e le mappature vengono installate nell'app dell'integratore.

## <a name="template-mappings"></a>Mapping del modello

Nelle seguenti tabelle di mapping dei modelli, il nome dell'attività indica le entità utilizzate in ciascuna applicazione. Finance è a sinistra e Dataverse è a destra.

### <a name="bank-account-disbursements-dual-write-to-bank-account-disbursement"></a>Esborsi conto bancario (doppia scrittura) in esborso conto bancario

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACCOUNTIDENTIFICATIONID        | cdm\_bankaccountid.cdm\_accountidentification        |
| IMPORTO                         | cdm\_amount                                         |
| PRIORITY                       | cdm\_disbursementpriority                           |
| PERSONNELNUMBER                | cdm\_bankaccountid.cdm\_workerid.cdm\_workernumber    |
| REMAINDER                      | cdm\_isremainder                                    |

### <a name="benefit-calculation-rate-detail-dual-write-to-benefit-calculation-rate-detail"></a>Dettagli dei coefficienti di calcolo benefit (scrittura doppia) in Dettagli dei coefficienti di calcolo benefit

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CONTRIBUTIONMETHOD             | cdm\_contributionmethod                             |
| EFFECTIVE                      | cdm\_effective                                      |
| EMPLOYERCONTRIBUTION           | cdm\_employercontribution                           |
| EXPIRATION                     | cdm\_expiration                                     |
| WORKERDEDUCTION                | cdm\_workerdeduction                                |
| NAME                           | cdm\_calculationrateid.cdm\_name                     |

### <a name="benefit-calculation-rate-header-to-benefit-calculation-rate"></a>Intestazione coefficienti di calcolo benefit in Coefficiente di calcolo benefit

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIZIONE                    | cdm\_description                                    |
| NAME                           | cdm\_name                                           |
| TIERTYPE                       | cdm\_tiertype                                       |

### <a name="benefit-option-to-benefit-option"></a>Opzione benefit in Opzione benefit

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ALLOWBENEFICIARYDESIGNATIONS   | cdm\_allowbeneficiarydesignations                   |
| ALLOWDEPENDENTCOVERAGE         | cdm\_allowdependentcoverage                         |
| BENEFITOPTIONID                | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| ISWAIVE                        | cdm\_iswaived                                       |

### <a name="benefit-type-to-benefit-type"></a>Tipo di benefit in Tipo di benefit

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| BENEFITTYPEID                  | cdm\_name                                           |
| CONCURRENTENROLLMENT           | cdm\_concurrentenrollment                           |
| DESCRIZIONE                    | cdm\_description                                    |
| PAYROLLCATEGORY                | cdm\_payrollcategory                                |

### <a name="business-calendar-to-business-process-calendar"></a>Calendario aziendale in Calendario di processi aziendali

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARID                     | cdm\_name                                           |
| NAME                           | cdm\_calendarname                                   |
| STARTDATE                      | cdm\_startdate                                      |
| ENDDATE                        | cdm\_enddate                                        |
| ISOPENMONDAY                   | cdm\_ismondayopen                                   |
| ISOPENTUESDAY                  | cdm\_istuesdayopen                                  |
| ISOPENWEDNESDAY                | cdm\_iswednesdayopen                                |
| ISOPENTHURSDAY                 | cdm\_isthursdayopen                                 |
| ISOPENFRIDAY                   | cdm\_isfridayopen                                   |
| ISOPENSATURDAY                 | cdm\_issaturdayopen                                 |
| ISOPENSUNDAY                   | cdm\_issundayopen                                   |

### <a name="business-process-to-business-process-header"></a>Processo aziendale in Intestazione di processo aziendale

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSID                      | cdm\_processid                                      |
| PROCESSTYPE                    | cdm\_processtype                                    |
| GENERICSUBTYPE                 | cdm\_genericsubtype                                 |
| NAME                           | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| STATO                         | cdm\_status                                         |
| TARGETDATE                     | cdm\_targetdate                                     |
| STARTDATETIME                  | cdm\_startdatetime                                  |
| ENDDATETIME                    | cdm\_enddatetime                                    |
| RESOLVEDBYPERSONNELNUMBER      | cdm\_resolvedbyid.cdm\_workernumber                  |
| PROCESSOWNERPERSONNELNUMBER    | cdm\_processownerid.cdm\_workernumber                |
| SOURCETEMPLATENAME             | cdm\_sourcetemplateid.cdm\_name                      |
| SOURCETEMPLATEPROCESSTYPE      | cdm\_sourcetemplateid.cdm\_businessprocesstype       |
| SOURCETEMPLATEGENERICSUBTYPE   | cdm\_sourcetemplateid.cdm\_genericsubtype            |

### <a name="business-process-library-task-group-to-business-process-library-task-group"></a>Gruppo di attività libreria processi aziendali in Gruppo di attività libreria processi aziendali

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_processtype                                    |
| NAME                           | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |

### <a name="business-process-stage-to-business-process-stage"></a>Fase processo aziendale in Fase processo aziendale

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_businessprocesstype                            |
| NAME                           | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| SEQUENCENUMBER                 | cdm\_sequencenumber                                 |

### <a name="business-process-task-to-business-process-task"></a>Attività processo aziendale in Attività processo aziendale

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIZIONE                    | cdm\_description                                    |
| DUEDATE                        | cdm\_duedate                                        |
| TASKID                         | cdm\_taskid                                         |
| INSTRUCTIONS                   | cdm\_instructions                                   |
| COMPLETIONDATETIME             | cdm\_completiondatetime                             |
| ASSIGNMENTTYPE                 | cdm\_assignmenttype                                 |
| ISOPTIONAL                     | cdm\_isoptional                                     |
| NAME                           | cdm\_name                                           |
| STATO                         | cdm\_status                                         |
| RESOLVEDBY\_PERSONNELNUMBER     | cdm\_resolvedbyid.cdm\_workernumber                  |
| TEMPLATETASKID                 | cdm\_templatetaskid.cdm\_taskid                      |
| ASSIGNEDWORKER\_PERSONNELNUMBER | cdm\_assignedworkerid.cdm\_workernumber              |
| PROCESSID                      | cdm\_processheaderid.cdm\_processid                  |
| ASSIGNEDGROUP\_NAME             | cdm\_assignedgroupid.cdm\_name                       |
| ASSIGNEDPOSITION\_POSITIONID    | cdm\_assignedposition.cdm\_jobpositionnumber         |

### <a name="business-process-template-to-checklist-template-header"></a>Modello di processo aziendale in Intestazione modello elenco di controllo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_businessprocesstype                            |
| GENERICSUBTYPE                 | cdm\_genericsubtype                                 |
| NAME                           | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| CALENDARID                     | cdm\_businessprocesscalendarid.cdm\_name             |
| PERSONNELNUMBER                | cdm\_processownerid.cdm\_workernumber                |
| ISACTIVE                       | cdm\_isactive                                       |

### <a name="business-process-template-task-to-checklist-template-task"></a>Attività modello di processo aziendale in Attività del modello elenco di controllo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TASKID                         | cdm\_taskid                                         |
| NAME                           | cdm\_name                                           |
| TEMPLATEHEADER\_PROCESSTYPE     | cdm\_businessprocesstemplateheaderid.cdm\_businessprocesstype |
| TEMPLATEHEADER\_GENERICSUBTYPE  | cdm\_businessprocesstemplateheaderid.cdm\_genericsubtype |
| TEMPLATEHEADER\_NAME            | cdm\_businessprocesstemplateheaderid.cdm\_name       |
| DESCRIZIONE                    | cdm\_description                                    |
| DUEDATEOFFSETDAYS              | cdm\_duedateoffsetdays                              |
| MENUITEMTYPE                   | cdm\_tasklinktype                                   |
| MENUITEM                       | cdm\_tasklink                                       |
| CONTACTPERSON\_PERSONNELNUMBER  | cdm\_contactpersonid.cdm\_workernumber               |
| ASSIGNMENTTYPE                 | cdm\_assignmenttype                                 |
| ASSIGNEDWORKER\_PERSONNELNUMBER | cdm\_assignedworkerid.cdm\_workernumber              |
| ASSIGNEDPOSITION\_POSITIONID    | cdm\_assignedpositionid.cdm\_jobpositionnumber       |
| ASSIGNEDGROUP\_NAME             | cdm\_assignedgroupid.cdm\_name                       |
| ISOPTIONAL                     | cdm\_isoptional                                     |
| INSTRUCTIONS                   | cdm\_instructions                                   |

### <a name="calculation-frequency-to-benefit-calculation-frequency"></a>Frequenza di calcolo in Frequenza di calcolo benefit

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIZIONE                    | cdm\_description                                    |
| FREQUENCY                      | cdm\_name                                           |
| FREQUENCYCONTROL               | cdm\_frequencycontrol                               |
| ISIMMUTABLE                    | cdm\_isimmutable                                    |

### <a name="calculation-frequency-pay-period-to-benefit-calculation-frequency-pay-period"></a>Periodo retributivo da aggiungere alla frequenza di calcolo in Periodo retributivo della frequenza di calcolo benefit

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALCULATIONFREQUENCYID         | cdm\_benefitcalculationfrequencyid.cdm\_name         |
| PERIODSTARTDATE                | cdm\_payperiodid.cdm\_periodstartdate                |
| PAYCYCLEID                     | cdm\_payperiodid.cdm\_paycycleid.cdm\_name            |

### <a name="calendar-to-work-calendar"></a>Calendario in Calendario lavorativo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARID                     | cdm\_name                                           |
| CALENDARNAME                   | cdm\_description                                    |
| WORKCALENDARHOLIDAYID          | cdm\_workcalendarholidayid.cdm\_name                 |

### <a name="compensation-fixed-action-table-to-fixed-compensation-event"></a>Tabella azioni di retribuzione fissa in Evento di retribuzione fissa

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACTION                         | cdm\_name                                           |
| ACTIVE                         | cdm\_isactive                                       |
| DESCRIZIONE                    | cdm\_description                                    |
| TIPO                           | cdm\_eventtype                                      |

### <a name="compensation-fixed-plan-to-compensation-fixed-plan"></a>Piano di retribuzione fissa in Piano di retribuzione fissa

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PLAN                           | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| TIPO                           | cdm\_type                                           |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| VALUTA                       | cdm\_transactioncurrencyid.isocurrencycode          |
| PAYFREQUENCY                   | cdm\_payfrequency.cdm\_name                          |
| HIRERULE                       | cdm\_hirerule                                       |
| OUTOFRANGETOLERANCE            | cdm\_outofrangetolerance                            |
| RECOMMENDATIONALLOWED          | cdm\_recommendationallowed                          |
| COMPENSATIONSTRUCTURE          | cdm\_compensationgrid.cdm\_name                      |
| REFPOINTSETUPID                | cdm\_referencepointsetupline.cdm\_referencepointsetupid.cdm\_name |
| CONTROLPOINT                   | cdm\_referencepointsetupline.cdm\_name               |

### <a name="compensation-grids-to-compensation-grid"></a>Griglie retributive in Griglia retributiva

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| GRIDID                         | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| REFERENCESETUP                 | cdm\_referencepointsetupid.cdm\_name                 |
| TIPO                           | cdm\_type                                           |
| VALUTA                       | cdm\_transactioncurrencyid.isocurrencycode          |

### <a name="compensation-job-function-to-job-function"></a>Funzione lavorativa retribuzione in Funzione lavorativa

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| JOBFUNCTIONID                  | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |

### <a name="compensation-job-type-to-job-type"></a>Tipo di posizione lavorativa retribuzione in Tipo di posizione lavorativa

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| JOBTYPEID                      | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| EXEMPTSTATUS                   | cdm\_exemptstatus                                   |

### <a name="compensation-pay-frequency-to-compensation-pay-frequency"></a>Frequenza di retribuzione in Frequenza di retribuzione

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PAYRATECONVERSION              | cdm\_name                                           |
| PERIOD                         | cdm\_period                                         |
| DESCRIZIONE                    | cdm\_description                                    |
| ANNUALCONVERSIONFACTOR         | cdm\_annualconversionfactor                         |
| HOURLYCONVERSIONFACTOR         | cdm\_hourlyconversionfactor                         |
| MONTHLYCONVERSIONFACTOR        | cdm\_monthlyconversionfactor                        |
| WEEKLYCONVERSIONFACTOR         | cdm\_weeklyconversionfactor                         |

### <a name="compensation-regions-to-compensation-region"></a>Paesi di retribuzione a Paese di retribuzione

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIZIONE                    | cdm\_description                                    |
| UBICAZIONE                       | cdm\_name                                           |

### <a name="compensation-variable-plan-v2-to-compensation-variable-plan"></a>Piano di retribuzione variabile V2 in Piano di retribuzione variabile

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| VARIABLEAWARDBASIS             | cdm\_awardbasis                                     |
| AWARDBASISCALCULATION          | cdm\_awardbasiscalculation                          |
| CALCULATIONTYPE                | cdm\_calculationtype                                |
| DESCRIZIONE                    | cdm\_description                                    |
| ENABLEENROLLMENT               | cdm\_enableenrollment                               |
| ENABLELEVELS                   | cdm\_enablelevels                                   |
| ENABLERECOMMENDATION           | cdm\_enablerecommendation                           |
| HIRERULE                       | cdm\_hirerule                                       |
| LEVERAGE100PERCENT             | cdm\_leverage100percent                             |
| LEVERAGEMAXIMUM                | cdm\_leveragemaximum                                |
| LEVERAGEMINIMUM                | cdm\_leverageminimum                                |
| LEVERAGEOVEROBJECTIVE          | cdm\_leverageoverobjective                          |
| LEVERAGEUNDEROBJECTIVE         | cdm\_leverageunderobjective                         |
| PERCENTOFBASIS                 | cdm\_percentofbasis                                 |
| PLANID                         | cdm\_name                                           |
| VARIABLECOMPENSATIONTYPE       | cdm\_variablecompensationtypeid.cdm\_name            |
| UNITCURRENCYCODE               | transactioncurrencyid.isocurrencycode              |
| UNITRELATIONSHIP               | cdm\_unitrelationship                               |
| UNITVALUE                      | cdm\_unitvalue                                      |
| NUMBEROFUNITSREAL              | cdm\_numberofunits                                  |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| VESTINGRULE                    | cdm\_vestingruleid.cdm\_name                         |
| LEVERAGETOLERANCEMAX           | cdm\_leveragetolerancemax                           |
| LEVERAGETOLERANCEMIN           | cdm\_leveragetolerancemin                           |

### <a name="compensation-variable-type-to-compensation-variable-plan-type"></a>Tipo di retribuzione variabile in Tipo di piano di retribuzione variabile

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIZIONE                    | cdm\_description                                    |
| TIPO                           | cdm\_awardtype                                      |
| VARIABLECOMPENSATIONTYPE       | cdm\_name                                           |

### <a name="compensation-vesting-rules-to-vesting-rule"></a>Regole di distribuzione incentivi retribuzione in Regola di distribuzione incentivi

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIZIONE                    | cdm\_description                                    |
| NOTA                           | cdm\_notes                                          |
| VESTINGRULE                    | cdm\_name                                           |

### <a name="department-v2-to-department"></a>Reparto V2 in Reparto

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| OPERATINGUNITNUMBER            | cdm\_departmentnumber                               |
| NAME                           | cdm\_name                                           |
| SEARCHNAME                     | cdm\_description                                    |
| PARTYTYPE                      | cdm\_partytype                                      |

### <a name="dual-write-tax-region-to-tax-region"></a>Regione fiscale doppia scrittura in Regione fiscale

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CITY                           | cdm\_city                                           |
| COUNTRYORREGION                | cdm\_countryorregion                                |
| COUNTY                         | cdm\_county                                         |
| STATE                          | cdm\_stateorprovince                                |
| TAXREGIONNAME                  | cdm\_name                                           |

### <a name="dual-write-worker-identification-to-worker-person-identification-number"></a>Identificazione lavoratore doppia scrittura in Numero di identificazione lavoratore

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIZIONE                    | cdm\_description                                    |
| ENTRYTYPE                      | cdm\_entrytype                                      |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| IDENTIFICATIONNUMBER           | cdm\_identificationnumber                           |
| IDENTIFICATIONTYPEID           | cdm\_identificationtypeid.cdm\_name                  |
| ISPRIMARY                      | cdm\_isprimary                                      |
| ISSUEDATE                      | cdm\_issuedate                                      |
| ISSUINGAGENCYID                | cdm\_issuingagencyid.cdm\_name                       |
| WORKERNUMBER                   | cdm\_workerid.cdm\_workernumber                      |

### <a name="compensation-structure-to-compensation-structure"></a>Struttura retributiva in Struttura retributiva

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IMPORTO                         | cdm\_amount                                         |
| GRID                           | cdm\_compensationgridid.cdm\_name                    |
| LEVELID                        | cdm\_compensationlevelid.cdm\_name                   |
| REFERENCEPOINTLINENUMBER       | cdm\_referencepointid.cdm\_linenumber                |
| REFERENCESETUP                 | cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_name |
| REFERENCEPOINT                 | cdm\_referencepointid.cdm\_name                      |

### <a name="earning-code-to-payroll-earning-code"></a>Codice di reddito in Codice di reddito retribuzioni

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| EARNINGCODE                    | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| INCLUDEINPAYMENTTYPE           | cdm\_includeinpaymenttype                           |
| QUANTITYUNIT                   | cdm\_quantityunit                                   |
| TRACKFMLAHOURS                 | cdm\_trackfmlahours                                 |
| ISPRODUCTIVE                   | cdm\_isproductive                                   |

### <a name="employee-fixed-compensation-to-worker-fixed-compensation"></a>Retribuzione fissa dipendente in Retribuzione fissa dipendente

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| COMPENSATIONLEVELID            | cdm\_compensationlevelid.cdm\_name                   |
| TIPO                           | cdm\_compensationtype                               |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| LINENUMBER                     | cdm\_linenumber                                     |
| PAYFREQUENCY                   | cdm\_payfrequencyid.cdm\_name                        |
| PAYRATE                        | cdm\_payrate                                        |
| PLAN                           | cdm\_planid.cdm\_name                                |
| POSITIONID                     | cdm\_positionid.cdm\_jobpositionnumber               |
| PROCESSTYPE                    | cdm\_processtype                                    |
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |
| ACTION                         | cdm\_eventid.cdm\_name                               |
| STEP                           | cdm\_referencepointsetuplineid.cdm\_name             |
| REFPOINTSETUPID                | cdm\_referencepointsetuplineid.cdm\_referencepointsetupid.cdm\_name |

### <a name="employment-per-company-to-employment"></a>Impiego per società in Impiego

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| EMPLOYMENTENDDATE              | cdm\_employmentenddate                              |
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |
| EMPLOYMENTSTARTDATE            | cdm\_employmentstartdate                            |
| WORKERTYPE                     | cdm\_workertype                                     |
| DIMENSIONDISPLAYVALUE          | cdm\_dimensiondisplayvalue                          |
| ADJUSTEDWORKERSTARTDATE        | cdm\_adjustedworkerstartdate                        |
| EMPLOYERNOTICEAMOUNT           | cdm\_employernoticeamount                           |
| EMPLOYERUNITOFNOTICE           | cdm\_employerunitofnotice                           |
| WORKERUNITOFNOTICE             | cdm\_workerunitofnotice                             |
| WORKERNOTICEAMOUNT             | cdm\_workernoticeamount                             |
| LASTDATEWORKED                 | cdm\_lastdateworked                                 |
| PROBATIONENDDATE               | cdm\_probationenddate                               |
| TRANSITIONDATE                 | cdm\_transitiondate                                 |
| TRANSITIONREASONCODENAME       | cdm\_transitionreasoncode.cdm\_name                  |
| WORKERSTARTDATE                | cdm\_workerstartdate                                |
| VALIDTO                        | cdm\_validto                                        |
| VALIDFROM                      | cdm\_validfrom                                      |

### <a name="ethnic-origins-to-ethnic-origin"></a>Origini etniche in Origine etnica

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ETHNICORIGINID                 | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |

### <a name="group-assignment-to-business-process-group-assignment"></a>Assegnazione gruppo in Assegnazione gruppo di processi aziendali

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NAME                           | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| ISACTIVE                       | cdm\_isactive                                       |

### <a name="identification-type-to-worker-person-identification-type"></a>Tipo di identificazione in Tipo di identificazione lavoratore

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIZIONE                    | cdm\_description                                    |
| IDENTIFICATIONTYPEID           | cdm\_name                                           |
| ALLOWEDVALUES                  | cdm\_allowedvalues                                  |
| FIXEDLENGTH                    | cdm\_fixedlength                                    |
| IDENTIFICATIONNUMBERFORMAT     | cdm\_identificationnumberformat                     |

### <a name="issuing-agency-to-person-identification-issuing-agency"></a>Agenzia emittente in Agenzia emittente dell'identificazione personale

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| POSTA ELETTRONICA                          | cdm\_email                                          |
| EXTENSION                      | cdm\_extension                                      |
| FAX                            | cdm\_fax                                            |
| ISSUINGAGENCY                  | cdm\_name                                           |
| MOBILEPHONE                    | cdm\_mobilephone                                    |
| INTERNETADDRESS                | cdm\_websiteurl                                     |
| NAME                           | cdm\_description                                    |
| PAGER                          | cdm\_pager                                          |
| SMS                            | cdm\_sms                                            |
| TELEPHONE                      | cdm\_telephone                                      |
| TELEXNUMBER                    | cdm\_telex                                          |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTY                  | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_addressdescription                             |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSSTREET                  | cdm\_street                                         |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| ADDRESSCOUNTRYREGIONISOCODE    | cdm\_countryregion                                  |

### <a name="job-positions-dual-write-to-job-position"></a>Doppia scrittura dimensioni predefinite posizione in Posizione lavorativa

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| POSITIONID                     | cdm\_jobpositionnumber                              |
| ACTIVATION                     | cdm\_activation                                     |
| AVAILABLEFORASSIGNMENT         | cdm\_availableforassignment                         |
| COMPENSATIONREGIONID           | cdm\_compensationregionid.cdm\_name                  |
| DEPARTMENTID                   | cdm\_departmentid.cdm\_departmentnumber              |
| DESCRIZIONE                    | cdm\_description                                    |
| FULLTIMEEQUIVALENT             | cdm\_fulltimeequivalent                             |
| JOBID                          | cdm\_jobid.cdm\_name                                 |
| PARENTPOSITIONID               | cdm\_parentjobpositionid.cdm\_jobpositionnumber      |
| POSITIONTYPEID                 | cdm\_positiontypeid.cdm\_name                        |
| RETIREMENT                     | cdm\_retirement                                     |
| TITLEID                        | cdm\_titleid.cdm\_name                               |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |

### <a name="jobs-dual-write-to-job"></a>Doppia scrittura posizioni lavorative in Posizione lavorativa

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| JOBID                          | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| JOBDESCRIPTION                 | cdm\_jobdescription                                 |
| ALLOWUNLIMITEDPOSITIONS        | cdm\_allowunlimitedpositions                        |
| MAXIMUMNUMBEROFPOSITIONS       | cdm\_maximumnumberofpositions                       |
| JOBFUNCTIONID                  | cdm\_jobfunctionid.cdm\_name                         |
| JOBTYPEID                      | cdm\_jobtypeid.cdm\_name                             |
| TITLEID                        | cdm\_titleid.cdm\_name                               |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| DEFAULTFULLTIMEEQUIVALENCY     | cdm\_defaultfulltimeequivalent                      |

### <a name="language-codes-to-language"></a>Codici lingua in Lingua

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| LANGUAGECODEID                 | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |

### <a name="leave-and-absence-bank-transaction-v2-to-leave-bank-transaction"></a>Transazione bancaria per congedo e assenza V2 in Transazione bancaria per congedo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IMPORTO                         | cdm\_amount                                         |
| LEAVETYPEID                    | cdm\_leavetypeid.cdm\_type                           |
| LEAVEPLANID                    | cdm\_leaveplanid.cdm\_name                           |
| TRANSACTIONDATE                | cdm\_transactiondate                                |
| TRANSACTIONNUMBER              | cdm\_transactionnumber                              |
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |
| TRANSACTIONTYPE                | cdm\_transactiontype                                |

### <a name="leave-and-absence-enrollment-v2-to-leave-enrollment"></a>Iscrizione per congedo e assenza V2 in Iscrizione al piano di congedo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| STARTDATE                      | cdm\_startdate                                      |
| ENDDATE                        | cdm\_enddate                                        |
| CUSTOMDATE                     | cdm\_customdate                                     |
| ACCRUALSTARTDATE               | cdm\_accrualstartdate                               |
| ACCRUALDATEBASIS               | cdm\_accrualdatebasis                               |
| ISACCRUALSUSPENDED             | cdm\_isaccrualsuspended                             |
| LEAVEPLANID                    | cdm\_leaveplanid.cdm\_name                           |
| TIERBASIS                      | cdm\_tierbasis                                      |
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |

### <a name="leave-and-absence-plan-v2-to-leave-plan"></a>Piano di congedo e assenza V2 in Piano di congedo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACCRUALFREQUENCY               | cdm\_accrualfrequency                               |
| NAME                           | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| STARTDATE                      | cdm\_startdate                                      |
| LEAVETYPEID                    | cdm\_leavetypeid.cdm\_type                           |

### <a name="leave-and-absence-type-to-leave-type"></a>Tipo di congedo e assenza in Tipo di congedo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIZIONE                    | cdm\_description                                    |
| TIPO                           | cdm\_type                                           |
| EARNINGCODEID                  | cdm\_earningcodeid.cdm\_name                         |

### <a name="leave-and-absence-type-reason-code-to-leave-type-reason-code"></a>Codice motivo tipo di congedo e assenza in Codice motivo del tipo di congedo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| LEAVETYPE                      | cdm\_typeid.cdm\_type                                |
| REASONCODEID                   | cdm\_reasoncodeid.cdm\_name                          |

### <a name="leave-time-off-request-detail-to-leave-request-detail"></a>Richiesta dettagliata di permesso di congedo in Dettagli richiesta congedo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IMPORTO                         | cdm\_amount                                         |
| LEAVEDATE                      | cdm\_leavedate                                      |
| REQUESTID                      | cdm\_leaverequestid.cdm\_leaverequestnumber          |
| TIPO                           | cdm\_leavetypeid.cdm\_type                           |

### <a name="leave-time-off-request-header-to-leave-request"></a>LIntestazione richiesta di permesso di congedo in Richiesta di congedo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| REQUESTID                      | cdm\_leaverequestnumber                             |
| REQUESTDATE                    | cdm\_requestdate                                    |
| STATO                         | cdm\_status                                         |
| COMMENT                        | cdm\_comment                                        |
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |

### <a name="levels-to-compensation-level"></a>Livelli in Livello retributivo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TIPO                           | cdm\_type                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| LEVEL                          | cdm\_name                                           |

### <a name="onboarding-process-header-to-onboard-process-header"></a>Intestazione processo integrazione in Intestazione processo di onboarding

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSID                      | cdm\_processheaderid.cdm\_processid                  |
| ONBOARDEDEMPLOYEEPERSONNELNUMBER | cdm\_onboardedemployeeid.cdm\_workernumber           |
| EMPLOYMENTPERSONNELNUMBER      | cdm\_employmentid.cdm\_workerid.cdm\_workernumber     |
| LEGALENTITYID                  | cdm\_employmentid.cdm\_companyid.cdm\_companycode     |
| EMPLOYMENTSTARTDATE            | cdm\_employmentid.cdm\_employmentstartdate           |

### <a name="pay-cycle-to-pay-cycle"></a>Ciclo retributivo in Ciclo retributivo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PAYCYCLEID                     | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| PAYCYCLEFREQUENCY              | cdm\_frequency                                      |

### <a name="pay-period-to-pay-period"></a>Periodo retributivo in Periodo retributivo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| COMMENTS                       | cdm\_description                                    |
| DEFAULTPAYMENTDATE             | cdm\_defaultpaymentdate                             |
| PAYCYCLEID                     | cdm\_paycycleid.cdm\_name                            |
| PERIODENDDATE                  | cdm\_periodenddate                                  |
| PERIODSTARTDATE                | cdm\_periodstartdate                                |
| STATO                         | cdm\_status                                         |

### <a name="payroll-details-for-positions-to-payroll-position-detail"></a>Dettagli retribuzione per posizioni in Dettagli posizione di retribuzione

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PAYCYCLEID                     | cdm\_paycycle.cdm\_name                              |
| POSITIONID                     | cdm\_position.cdm\_jobpositionnumber                 |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| ANNUALREGULARHOURS             | cdm\_annualregularhours                             |
| PAIDBYLEGALENTITY              | cdm\_paidby.cdm\_companycode                         |

### <a name="position-default-dimensions-dual-write-to-job-position-dimension"></a>Doppia scrittura dimensioni predefinite posizione in Dimensione posizione lavorativa

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DIMENSIONDISPLAYVALUE          | cdm\_dimensiondisplayvalue                          |
| POSITIONID                     | cdm\_jobpositionid.cdm\_jobpositionnumber            |

### <a name="position-type-to-position-type"></a>Tipi di posizione in Tipo di posizione

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| POSITIONTYPEID                 | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| CLASSIFICATION                 | cdm\_classification                                 |

### <a name="position-worker-assignments-v2-to-position-worker-assignment"></a>Assegnazioni lavoratori a posizioni V2 in Assegnazione lavoratore posizione

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |
| POSITIONID                     | cdm\_jobpositionid.cdm\_jobpositionnumber            |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| IsPrimaryPosition              | cdm\_isprimaryposition                              |

### <a name="reason-codes-to-reason-code"></a>Codici motivo in Codice motivo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| REASONCODEID                   | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| ISABSENCEAPPLICABLE            | cdm\_isabsenceapplicable                            |
| ISAPPLICATIONAPPLICABLE        | cdm\_isapplicationapplicable                        |
| ISCOMPENSATIONAPPLICABLE       | cdm\_iscompensationapplicable                       |
| ISCREATENEWPOSITIONAPPLICABLE  | cdm\_iscreatenewpositionapplicable                  |
| ISEDITPOSITIONAPPLICABLE       | cdm\_iseditpositionapplicable                       |
| ISHIREAPPLICABLE               | cdm\_ishireapplicable                               |
| ISSKILLMAPPINGAPPLICABLE       | cdm\_isskillmappingapplicable                       |
| ISTERMINATIONAPPLICABLE        | cdm\_isterminationapplicable                        |
| ISTRANSFERAPPLICABLE           | cdm\_istransferapplicable                           |

### <a name="reference-point-setup-line-dual-write-to-compensation-reference-point-setup-line"></a>Riga di impostazione del punto di riferimento (doppia scrittura) in Riga impostazione punti di riferimento per le retribuzioni

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIZIONE                    | cdm\_description                                    |
| LINENUM                        | cdm\_linenumber                                     |
| REFPOINTID                     | cdm\_name                                           |
| REFPOINTSETUPID                | cdm\_referencepointsetupid.cdm\_name                 |

### <a name="reference-point-setups-to-compensation-reference-point-setup"></a>Impostazioni punti di riferimento in Impostazione punti di riferimento per le retribuzioni

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| REFERENCESETUP                 | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| TIPO                           | cdm\_compensationtype                               |

### <a name="skill-types-to-skill-type"></a>Tipi di competenza in Tipo di competenza

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| SKILLTYPE                      | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |

### <a name="titles-to-title"></a>Titoli in Titolo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TITLEID                        | cdm\_name                                           |

### <a name="variable-compensation-level-v2-to-compensation-variable-plan-level"></a>Livello retributivo variabile V2 in Livello del piano di retribuzione variabile

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| AWARDAMOUNT                    | cdm\_awardamount                                    |
| AWARDPERCENT                   | cdm\_awardpercent                                   |
| AWARDUNITSREAL                 | cdm\_awardunits                                     |
| COMPENSATIONLEVELID            | cdm\_compensationlevelid.cdm\_name                   |
| PLANID                         | cdm\_compensationvariableplanid.cdm\_name            |

### <a name="veteran-status-to-veteran-status"></a>Stato veterano in Stato veterano

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| VETERANSTATUSID                | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |
| ISPROTECTEDVETERAN             | cdm\_isprotectedveteran                             |

### <a name="work-calendar-enrollments-to-work-calendar-enrollment"></a>Iscrizioni al calendario lavorativo in Iscrizione al calendario lavorativo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| STARTDATE                      | cdm\_employmentid.cdm\_employmentstartdate           |
| PERSONNELNUMBER                | cdm\_employmentid.cdm\_workerid.cdm\_workernumber     |
| CALENDARID                     | cdm\_workcalendarid.cdm\_name                        |
| COMPANYID                      | cdm\_employmentid.cdm\_companyid.cdm\_companycode     |

### <a name="work-calendar-holiday-to-work-calendar-holiday"></a>Festività calendario lavorativo in Festività calendario lavorativo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ID                             | cdm\_name                                           |
| DESCRIZIONE                    | cdm\_description                                    |

### <a name="work-calendar-holiday-line-to-work-calendar-holiday-line"></a>Riga festività calendario lavorativo in Riga festività calendario lavorativo

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| HOLIDAYID                      | cdm\_workcalendarholidayid.cdm\_name                 |
| NAME                           | cdm\_name                                           |
| HOLIDAYDATE                    | cdm\_holidaydate                                    |

### <a name="worker-to-worker"></a>Lavoratore in Lavoratore

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PERSONNELNUMBER                | cdm\_workernumber                                   |
| FIRSTNAME                      | cdm\_firstname                                      |
| MIDDLENAME                     | cdm\_middlename                                     |
| LASTNAME                       | cdm\_lastname                                       |
| WORKERTYPE                     | cdm\_type                                           |
| WORKERSTATUS                   | cdm\_status                                         |
| PRIMARYCONTACTEMAIL            | cdm\_primaryemailaddress                            |
| PRIMARYCONTACTPHONE            | cdm\_primarytelephone                               |
| PRIMARYCONTACTFACEBOOK         | cdm\_facebookidentity                               |
| PRIMARYCONTACTTWITTER          | cdm\_twitteridentity                                |
| PRIMARYCONTACTLINKEDIN         | cdm\_linkedinidentity                               |
| PRIMARYCONTACTURL              | cdm\_websiteurl                                     |
| GENDER                         | cdm\_gender                                         |
| BIRTHDATE                      | cdm\_birthdate                                      |
| NAME                           | cdm\_fullname                                       |

### <a name="worker-bank-accounts-to-worker-bank-account"></a>Conti bancari del lavoratore in Conto bancario del lavoratore

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACCOUNTIDENTIFICATION          | cdm\_accountidentification                          |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTRYREGIONID         | cdm\_countryorregion                                |
| ADDRESSCOUNTY                  | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_addressdescription                             |
| ADDRESSDISTRICTNAME            | cdm\_districtname                                   |
| ADDRESSPOSTBOX                 | cdm\_postofficebox                                  |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |
| BANKACCOUNTNUMBER              | cdm\_bankaccountnumber                              |
| BANKACCOUNTTYPE                | cdm\_bankaccounttype                                |
| POSTA ELETTRONICA                          | cdm\_email                                          |
| EXTENSION                      | cdm\_extension                                      |
| FAX                            | cdm\_fax                                            |
| INTERNETADDRESS                | cdm\_websiteurl                                     |
| MOBILEPHONE                    | cdm\_mobilephone                                    |
| ROUTINGNUMBER                  | cdm\_routingnumber                                  |
| TELEPHONE                      | cdm\_telephone                                      |
| TELEXNUMBER                    | cdm\_telexnumber                                    |
| BANKIBAN                       | cdm\_iban                                           |
| SWIFTNO                        | cdm\_swiftcode                                      |
| BANKLOCATIONCODE               | cdm\_banklocationcode                               |
| BRANCHNAME                     | cdm\_branchname                                     |
| BRANCHNUMBER                   | cdm\_branchnumber                                   |
| ROUTINGNUMBERTYPE              | cdm\_routingnumbertype                              |
| ACCOUNTHOLDER                  | cdm\_accountholder                                  |
| NAMEOFPERSON                   | cdm\_nameofperson                                   |
| NAME                           | cdm\_description                                    |
| ADDRESSSTREET                  | cdm\_line1                                          |
| ADDRESSSTREETNUMBER            | cdm\_line2                                          |

### <a name="worker-personal-details-to-worker-personal-detail"></a>Dettagli personali lavoratore in Dettagli personali lavoratore

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |
| BIRTHDATE                      | cdm\_birthdate                                      |
| PERSONBIRTHCITY                | cdm\_birthcity                                      |
| GENDER                         | cdm\_gender                                         |
| EXPATRIATEENDDATE              | cdm\_expatriateenddate                              |
| EXPATRIATESTARTDATE            | cdm\_expatriatestartdate                            |
| DISABLEDVETERAN                | cdm\_isdisabledveteran                              |
| DECEASEDDATE                   | cdm\_deceaseddate                                   |
| DISABLEDVERIFICATIONDATE       | cdm\_disabledveteranverificationdate                |
| EDUCATION                      | cdm\_education                                      |
| ETHNICORIGINID                 | cdm\_ethnicoriginid.cdm\_name                        |
| ISDISABLED                     | cdm\_isdisabled                                     |
| ISFULLTIMESTUDENT              | cdm\_isfulltimestudent                              |
| ISEXPATRIATERULINGAPPLICABLE   | cdm\_isexpatriaterulingapplicable                   |
| MARITALSTATUS                  | cdm\_maritalstatus                                  |
| MILITARYSERVICESTARTDATE       | cdm\_militaryservicestartdate                       |
| MILITARYSERVICEENDDATE         | cdm\_militaryserviceenddate                         |
| NUMBEROFDEPENDENTS             | cdm\_numberofdependents                             |
| NATIVELANGUAGEID               | cdm\_nativelanguageidid.cdm\_name                    |
| NATIONALITYCOUNTRYREGION       | cdm\_nationalitycountryregion                       |
| PERSONBIRTHCOUNTRYREGION       | cdm\_birthcountryregion                             |
| FATHERBIRTHCOUNTRYREGION       | cdm\_fatherbirthcountryregion                       |
| MOTHERBIRTHCOUNTRYREGION       | cdm\_motherbirthcountryregion                       |
| CITIZENSHIPCOUNTRYREGION       | cdm\_citizenshipcountryregion                       |
| VETERANSTATUSID                | cdm\_veteranstatusid.cdm\_name                       |

### <a name="worker-postal-addresses-dual-write-to-worker-address"></a>Doppia scrittura indirizzi postali lavoratore in Indirizzo lavoratore

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |
| ADDRESSLOCATIONID              | cdm\_addressnumber                                  |
| ADDRESSLOCATIONROLES           | cdm\_addresstype                                    |
| EFFECTIVE                      | cdm\_effectivedate                                  |
| EXPIRATION                     | cdm\_expirationdate                                 |
| ADDRESSSTREET                  | cdm\_street                                         |
| ADDRESSSTREETNUMBER            | cdm\_streetnumber                                   |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTRYREGIONISOCODE    | cdm\_countryregion                                  |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSCOUNTYID                | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_description                                    |
| ADDRESSLATITUDE                | cdm\_latitude                                       |
| ADDRESSLONGITUDE               | cdm\_longitude                                      |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| ADDRESSPOSTBOX                 | cdm\_postofficebox                                  |
| ISPRIMARY                      | cdm\_ispreferred                                    |

### <a name="working-time-to-work-calendar-time-interval"></a>Orario di lavoro in Intervallo orario calendario di lavoro

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ENDTIME                        | cdm\_endtime                                        |
| STARTTIME                      | cdm\_starttime                                      |
| WORKCALENDARDATE               | cdm\_workcalendardayid.cdm\_calendardate             |
| WORKCALENDARID                 | cdm\_workcalendarid.cdm\_name                        |
| WORKCALENDARID                 | cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_name  |

### <a name="working-times-to-work-calendar-day"></a>Orari di lavoro in Giorno calendario di lavoro

| Entità Finance                 | Tabella Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARDATE                   | cdm\_calendardate                                   |
| WORKCALENDARID                 | cdm\_workcalendarid.cdm\_name                        |
| WORKINGDAYDEFINITION           | cdm\_status                                         |

## <a name="integration-considerations"></a>Considerazioni sull'integrazione

- Tutte le modifiche apportate ai dati in uno dei due sistemi saranno soggette alla convalida da parte dell'altro sistema. Se si verifica un errore, i dati non verranno scritti in nessuno dei due sistemi. 
- Tutte le scritture sono soggette all'impostazione predefinita dei dati (se la logica personalizzata si verifica in Finance).
- L'app dell'integratore a doppia scrittura utilizza le chiavi di integrazione per eseguire la mappatura tra i due sistemi. A volte è difficile scegliere la chiave di integrazione corretta, soprattutto se più chiavi di integrazione soddisfano i requisiti. Per facilitare questa scelta, la tabella seguente elenca le chiavi di integrazione suggerite per le tue mappature.

| Tabella Dataverse                          | Chiavi di integrazione |
|------------------------------------------|------------------|
| Esborso conto bancario                | cdm\_bankaccountid.cdm\_accountidentification, cdm\_bankaccountid.cdm\_workerid.cdm\_workernumber, cdm\_companyid.cdm\_companycode |
| Frequenza di calcolo benefit            | cdm\_name |
| Periodo retributivo della frequenza di calcolo benefit | cdm\_payperiodid.cdm\_periodstartdate, cdm\_payperiodid.cdm\_paycycleid.cdm\_name, cdm\_benefitcalculationfrequencyid.cdm\_name |
| Coefficiente di calcolo benefit                 | cdm\_name |
| Dettagli dei coefficienti di calcolo benefit          | cdm\_workerdeduction, cdm\_effective, cdm\_calculationrateid.cdm\_name |
| Opzione benefit                           | cdm\_name |
| Tipo di benefit                             | cdm\_name |
| Calendario di processi aziendali                | cdm\_name |
| Assegnazione gruppo di processi aziendali        | cdm\_name |
| Intestazione di processo aziendale                  | cdm\_processid |
| Gruppo di attività libreria processi aziendali      | cdm\_processtype, cdm\_name |
| Fase di processi aziendali                   | cdm\_name, cdm\_businessprocesstype, cdm\_companyid.cdm\_companycode |
| Attività processo aziendale                    | cdm\_taskid |
| Business Unit                            | |
| Intestazione modello elenco di controllo                | cdm\_businessprocesstype, cdm\_name, cdm\_genericsubtype |
| Attività del modello elenco di controllo                  | cdm\_taskid |
| Società                                  | cdm\_companycode |
| Piano di retribuzione fissa                  | cdm\_name, cdm\_company.cdm\_companycode |
| Griglia di retribuzione                        | cdm\_name, cdm\_companyid.cdm\_companycode |
| Livello retributivo                       | cdm\_name |
| Frequenza della retribuzione               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Impostazione punti di riferimento per le retribuzioni       | cdm\_name, cdm\_companyid.cdm\_companycode |
| Riga impostazione punti di riferimento per le retribuzioni  | cdm\_name, cdm\_referencepointsetupid.cdm\_name, cdm\_referencepointsetupid.cdm\_companyid.cdm\_companycode |
| Paese di retribuzione                      | cdm\_name |
| Struttura retributiva                   | cdm\_compensationlevelid.cdm\_name, cdm\_referencepointid.cdm\_name, cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_name, cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_compensationgridid.cdm\_name, cdm\_compensationgridid.cdm\_companyid.cdm\_companycode |
| Piano di retribuzione variabile               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Livello del piano di retribuzione variabile         | cdm\_companyid.cdm\_companycode, cdm\_compensationvariableplanid.cdm\_name, cdm\_compensationvariableplanid.cdm\_companyid.cdm\_companycode, cdm\_compensationlevelid.cdm\_name |
| Tipo di piano di retribuzione variabile          | cdm\_name, cdm\_companyid.cdm\_companycode |
| Valuta                                 | isocurrencycode |
| Reparto                               | cdm\_departmentnumber |
| Impiego                               | cdm\_employmentstartdate, cdm\_workerid.cdm\_workernumber, cdm\_companyid.cdm\_companycode |
| Origine etnica                            | cdm\_name |
| Evento di retribuzione fissa                 | cdm\_name, cdm\_companyid.cdm\_companycode |
| Posizione                                      | cdm\_name |
| Funzione lavorativa                             | cdm\_name |
| Posizione lavorativa                             | cdm\_jobpositionnumber |
| Dimensione posizione lavorativa                   | cdm\_jobpositionid.cdm\_jobpositionnumber, cdm\_companyid.cdm\_companycode |
| Tipo di posizione                                 | cdm\_name |
| Lingua                                 | cdm\_name |
| Transazione bancaria per congedo                   | cdm\_transactiondate, cdm\_transactiontype, cdm\_transactionnumber, cdm\_leavetypeid.cdm\_type, cdm\_leavetypeid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workerid.cdm\_workernumber |
| Iscrizione al piano di congedo                         | cdm\_startdate, cdm\_leaveplanid.cdm\_name, cdm\_leaveplanid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workerid.cdm\_workernumber |
| Piano di congedo                               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Richiesta di congedo                            | cdm\_leaverequestnumber, cdm\_companyid.cdm\_companycode |
| Dettagli richiesta congedo                     | cdm\_leavedate, cdm\_leavetypeid.cdm\_type, cdm\_leavetypeid.cdm\_companyid.cdm\_companycode, cdm\_leaverequestid.cdm\_leaverequestnumber, cdm\_leaverequestid.cdm\_companyid.cdm\_companycode |
| Tipo di congedo                               | cdm\_type, cdm\_companyid.cdm\_companycode |
| Codice motivo del tipo di congedo                   | cdm\_reasoncodeid.cdm\_name, cdm\_typeid.cdm\_type, cdm\_typeid.cdm\_companyid.cdm\_companycode |
| Intestazione processo di onboarding                   | cdm\_processheaderid.cdm\_processid |
| Organizzazione                             | |
| Ciclo retributivo                                | cdm\_name |
| Periodo retributivo                               | cdm\_periodstartdate, cdm\_paycycleid.cdm\_name, cdm\_periodenddate |
| Codice di reddito retribuzioni                     | cdm\_name |
| Dettagli posizione di retribuzione                  | cdm\_validfrom, cdm\_validto, cdm\_position.cdm\_jobpositionnumber |
| Agenzia emittente dell'identificazione personale.     | cdm\_name |
| Tipo di posizione                            | cdm\_name |
| Assegnazione lavoratore posizione               | cdm\_validfrom, cdm\_jobpositionid.cdm\_jobpositionnumber |
| Codice motivo                              | cdm\_name |
| Tipo di competenza                               | cdm\_name |
| Regione fiscale                               | cdm\_stateorprovince, cdm\_name, cdm\_countryorregion, cdm\_county, cdm\_city |
| Team                                     | azureactivedirectoryobjectid, membershiptype |
| Titolo                                    | cdm\_name |
| User                                     | azureactivedirectoryobjectid |
| Regola di distribuzione incentivi                             | cdm\_name, cdm\_companyid.cdm\_companycode |
| Stato veterano                           | cdm\_name |
| Calendario lavorativo                            | cdm\_name, cdm\_companyid.cdm\_companycode |
| Giorno calendario di lavoro                        | cdm\_calendardate, cdm\_companyid.cdm\_companycode, cdm\_workcalendarid.cdm\_name, cdm\_workcalendarid.cdm\_companyid.cdm\_companycode |
| Iscrizione al calendario lavorativo                 | cdm\_employmentid.cdm\_employmentstartdate, cdm\_employmentid.cdm\_workerid.cdm\_workernumber, cdm\_employmentid.cdm\_companyid.cdm\_companycode |
| Festività calendario lavorativo                    | cdm\_name |
| Riga festività del calendario di lavoro               | cdm\_holidaydate, cdm\_workcalendarholidayid.cdm\_name |
| Intervallo orario calendario di lavoro              | cdm\_starttime, cdm\_workcalendardayid.cdm\_calendardate, cdm\_workcalendardayid.cdm\_companyid.cdm\_companycode, cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_name, cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workcalendarid.cdm\_name, cdm\_workcalendarid.cdm\_companyid.cdm\_companycode |
| Lavoro                                   | cdm\_workernumber |
| Indirizzo del lavoratore                           | cdm\_addressnumber, cdm\_addresstype, cdm\_workerid.cdm\_workernumber |
| Conto bancario del lavoratore                      | cdm\_accountidentification, cdm\_workerid.cdm\_workernumber |
| Retribuzione fissa del lavoratore                | cdm\_linenumber, cdm\_effectivedate, cdm\_companyid.cdm\_companycode, cdm\_positionid.cdm\_jobpositionnumber, cdm\_workerid.cdm\_workernumber, cdm\_eventid.cdm\_name, cdm\_eventid.cdm\_companyid.cdm\_companycode, cdm\_planid.cdm\_name, cdm\_planid.cdm\_company.cdm\_companycode |
| Numero di identificazione lavoratore      | cdm\_identificationnumber, cdm\_workerid.cdm\_workernumber, cdm\_identificationtypeid.cdm\_name |
| Tipo di identificazione lavoratore        | cdm\_name |
| Dati personali lavoratore                   | cdm\_workerid.cdm\_workernumber |
