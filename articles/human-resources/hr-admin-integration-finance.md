---
title: Configurare l'integrazione con Finance
description: Questo articolo descrive l'integrazione tra Dynamics 365 Human Resources e Dynamics 365 Finance.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8be7cbf92c11036d334516116f0895c426380954
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875860"
---
# <a name="configure-integration-with-finance"></a>Configurare l'integrazione con Finance


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Per integrare Dynamics 365 Human Resources con Dynamics 365 Finance, è possibile utilizzare il modello da Human Resources a Finance in [Integratore di dati](/powerapps/administrator/data-integrator). Il modello da Human Resources a Finance consente il flusso di dati per lavori, posizioni e lavoratori. Il modello consente ai dati di passare da Human Resources a Finance, ma non consente ai dati di passare da Finance a Human Resources.

![Flusso di integrazione da Human Resources a Finance.](./media/hr-admin-integration-finance-flow.png)

La soluzione da Human Resources a Finance fornisce i seguenti tipi di sincronizzazione dei dati:

- Gestire posizioni lavorative in Human Resources e sincronizzarle da Human Resources a Finance
- Gestire posizioni e assegnazioni di posizioni in Human Resources e sincronizzarle da Human Resources a Finance
- Gestire impieghi in Human Resources e sincronizzarli da Human Resources a Finance
- Gestire lavoratori e indirizzi di lavoratori in Human Resources e sincronizzarli da Human Resources a Finance

## <a name="system-requirements-for-human-resources"></a>Requisiti di sistema per Human Resources

La soluzione di integrazione richiede le seguenti versioni di Human Resources e Finance: 

- Dynamics 365 Human Resources su Dataverse
- Dynamics 365 Finance versione 7.2 e successive

## <a name="template-and-tasks"></a>Modello e attività

Per accedere al modello da Human Resources a Finance.

1. Aprire l'[interfaccia di amministrazione di Power Apps](https://admin.powerapps.com/). 

2. Selezionare **Progetti**, quindi selezionare **Nuovo progetto** nell'angolo in alto a destra. Creare un nuovo progetto per ogni persona giuridica che si desidera integrare in Finance.

3. Selezionare **Human Resources (da Human Resources Dataverse a Finance)** per sincronizzare i record da Human Resources a Finance.

Il modello utilizza le seguenti attività sottostanti per sincronizzare i record da Human Resources a Finance:

- **Funzioni lavorative a Funzione lavorativa retribuzione**
- **Reparti a Unità operativa**
- **Tipi di posizione lavorativa a Tipo di posizione lavorativa retribuzione**
- **Posizioni lavorative a Posizioni lavorative**
- **Posizioni lavorative a Dettagli posizione lavorativa**
- **Tipi di posizione a Tipo di posizione**
- **Posizioni a Posizione di base**
- **Posizioni a Dettagli posizione**
- **Posizioni a Durate posizione**
- **Posizioni a Gerarchie posizioni**
- **Lavoratori a Lavoratore**
- **Impieghi a Impiego**
- **Impieghi a Dettaglio impiego**
- **Assegnazione lavoratore posizione a Assegnazioni lavoratori posizioni**
- **Indirizzi lavoratore a Indirizzo postale lavoratore V2**

## <a name="template-mappings"></a>Mapping del modello

Nelle seguenti tabelle di mapping dei modelli, il nome dell'attività contiene le entità utilizzate in ciascuna applicazione. L'origine (Human Resources) è a sinistra e la destinazione (Finance) è a destra.

### <a name="job-functions-to-compensation-job-function"></a>Funzioni lavorative a Funzione lavorativa retribuzione

| Tabella Dataverse (origine) | Entità di Finance (destinazione) |
|-------------------------------------|---------------------------------------------|
| cdm_name (cdm_Job   Nome funzione)  | JOBFUNCTIONID   (JOBFUNCTIONID)            |
| cdm_description   (cdm_description) | DESCRIPTION   (DESCRIPTION)                 |

### <a name="departments-to-operating-unit"></a>Reparti a Unità operativa

| Tabella Dataverse (origine)           | Entità di Finance (destinazione) |
|-----------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                           | NAME (NAME)                                 |
| cdm_departmentnumber   (cdm_departmentnumber) | OPERATINGUNITNUMBER   (OPERATINGUNITNUMBER) |
|                                               | OPERATINGUNITTYPE   (OPERATINGUNITTYPE)     |
| cdm_description   (cdm_description)           | NAMEALIAS   (NAMEALIAS)                     |

### <a name="job-types-to-compensation-job-type"></a>Tipi di posizione lavorativa a Tipo di posizione lavorativa retribuzione

| Tabella Dataverse (origine)   | Entità di Finance (destinazione) |
|---------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                   | JOBTYPEID   (JOBTYPEID)                     |
| cdm_description   (cdm_description)   | DESCRIPTION   (DESCRIPTION)                 |
| cdm_exemptstatus   (cdm_exemptstatus) | EXEMPTSTATUS   (EXEMPTSTATUS)               |

### <a name="jobs-to-jobs"></a>Posizioni lavorative a Posizioni lavorative

| Tabella Dataverse (origine)                           | Entità di Finance (destinazione)           |
|---------------------------------------------------------------|-------------------------------------------------------|
| cdm_name (cdm_name)                                           | JOBID (JOBID)                                         |
| cdm_maximumnumberofpositions   (cdm_maximumnumberofpositions) | MAXIMUMNUMBEROFPOSITIONS   (MAXIMUMNUMBEROFPOSITIONS) |
| cdm_allowedunlimitedpositions   (cdm_allowunlimitedpositions) | ALLOWUNLIMITEDPOSITIONS   (ALLOWUNLIMITEDPOSITIONS)   |
| cdm_description   (cdm_description)                           | DESCRIPTION   (DESCRIPTION)                           |
| cdm_jobdescription   (cdm_jobdescription)                     | JOBDESCRIPTION   (JOBDESCRIPTIONS)                    |

### <a name="jobs-to-job-detail"></a>Posizioni lavorative a Dettagli posizione lavorativa

| Tabella Dataverse (origine)                             | Entità di Finance (destinazione) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                                             | JOBID (JOBID)                               |
| cdm_jobtypeid.cdm_name   (Tipo di posizione lavorativa (Nome tipo di posizione lavorativa))             | JOBTYPEID   (JOBTYPEID)                     |
| cdm_jobfunctionid.cdm_name   (Funzione lavorativa (Nome funzione lavorativa)) | FUNCTIONID   (FUCNTIONID)                   |
| cdm_validfrom   (Data di inizio validità)                                    | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (Data di fine validità)                                        | VALIDTO (VALIDTO)                           |
| cdm_defaultfulltimeequivalent   (Equivalente a tempo pieno predefinito)   | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)   |

### <a name="position-types-to-position-type"></a>Tipi di posizione a Tipo di posizione

| Tabella Dataverse (origine)       | Entità di Finance (destinazione) |
|-------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                       | POSITIONTYPEID   (POSITIONTYPEID)           |
| cdm_description   (cdm_description)       | DESCRIPTION   (DESCRIPTION)                 |
| cdm_classification   (cdm_classification) | CLASSIFICATION   (CLASSIFICATION)           |

### <a name="job-positions-to-base-position"></a>Posizioni a Posizione di base

| Tabella Dataverse (origine)           | Entità di Finance (destinazione) |
|-----------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Numero posizione) | POSITIONID (POSITIONID)                      |

### <a name="job-positions-to-position-details"></a>Posizioni a Dettagli posizione

| Tabella Dataverse (origine)              | Entità di Finance (destinazione)       |
|--------------------------------------------------------------------------|---------------------------------------------------|
| cdm_jobpositionnumber  (Numero posizione)                            | POSITIONID (POSITIONID)                             |
| cdm_jobid.cdm_name   (Posizione lavorativa (Nome))                                        | JOBID (JOBID)                                    |
| cdm_description   (cdm_description)                                        | DESCRIPTION   (DESCRIPTION)                       |
| cdm_departmentid.cdm_departmentnumber   (Reparto (Numero reparto)) | DEPARTMENTNUMBER   (DEPARTMENTNUMBER)             |
| cdm_positiontypeid.cdm_name   (Tipo di posizione (Nome))                     | POSITIONTYPEID   (POSITIONTYPEID)                 |
| cdm_avaialableforassignment   (Disponibile per l'assegnazione)                 | AVAILABLEFORASSIGNMENT   (AVAILABLEFORASSIGNMENT) |
| cdm_validfrom   (Data di inizio validità)                                            | VALIDFROM   (VALIDFROM)                           |
| cdm_validto (Data di fine validità)                                                 | VALIDTO (VALIDTO)                               |
| cdm_fulltimeequivalent   (Equivalente a tempo pieno)                           | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)         |

### <a name="job-positions-to-position-durations"></a>Posizioni a Durate posizione

| Tabella Dataverse (origine)             | Entità di Finance (destinazione) |
|-------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Numero posizione)   | POSITIONID (POSITIONID)                      |
| Attivazione   calcolata (Attivazione calcolata) | VALIDFROM (VALIDFROM)                        |
| Pensione   calcolata (Pensione calcolata) | VALIDTO (VALIDTO)                         |

### <a name="job-positions-to-position-hierarchies"></a>Posizioni a Gerarchie posizioni

| Tabella Dataverse (origine)        | Entità di Finance (destinazione) |
|-----------------------------------------------------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Numero posizione)                                                 | POSITIONID(POSITIONID)                      |
| cdm_parentjobpositionid.cdmjobpositionnumber   (cdm_parentjobpositionid.cdmjobpositionnumber) | PARENTPOSITIONID (PARENTPOSITIONID)         |
| cdm_validfrom   (Data di inizio validità)                                                                  | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (Data di fine validità)                                                                      | VALIDTO (VALIDTO)                           |
| HIERARCHYTYPENAME   (HIERARCHYTYPENAME)                                                       | HIERARCHYTYPENAME   (HIERARCHYTYPENAME)     |


### <a name="workers-to-worker"></a>Lavoratori a Lavoratore
| Tabella Dataverse (origine)           | Entità di Finance (destinazione)       |
|-----------------------------------------------|---------------------------------------------------|
| cdm_birthdate   (cdm_birthdate)               | BIRTHDATE   (BIRTHDATE)                           |
| cdm_gender   (cdm_gender)                     | GENDER (GENDER)                                   |
| cdm_primaryaddress   (cdm_primaryaddress)     | PRIMARYCONTACTEMAIL   (PRIMARYCONTACTEMAIL )      |
| cdm_primarytelephone   (cdm_primarytelephone) | PRIMARYCONTACTPHONE   (PRIMARYCONTACTPHONE)       |
| cdm_facebookidentity   (cdm_facebookidentity) | PRIMARYCONTACTFACEBOOK   (PRIMARYCONTACTFACEBOOK) |
| cdm_twitteridentity   (cdm_twitteridentity)   | PRIMARYCONTACTTWITTER   (PRIMARYCONTACTTWITTER)   |
| cdm_linkedinIdentity   (cdm_linkedinIdentity) | PRIMARYCONTACTLINKEDIN   (PRIMARYCONTACTLINKEDIN) |
| cdm_websiteurl   (cdm_websiteurl)             | PRIMARYCONTACTURL   (PRIMARYCONTACTURL)           |
| cdm_firstname   (cdm_firstname)               | FIRSTNAME   (FIRSTNAME)                           |
| cdm_middlename   (cdm_middlename)             | MIDDLENAME   (MIDDLENAME)                         |
| cdm_lastname   (cdm_lastname)                 | LASTNAME (LASTNAME)                               |
| cdm_workernumber   (cdm_workernumber)         | PERSONNELNUMBER   (PERSONNELNUMBER)               |
| cdm_type (cdm_type)                           | WORKERTYPE   (WORKERTYPE)                         |
| cdm_state   (cdm_state)                       | WORKSTATUS   (WORKERSTATUS)                       |

### <a name="employments-to-employment"></a>Impieghi a Impiego

| Tabella Dataverse (origine)                             | Entità di Finance (destinazione) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE   (EMPLOYMENTSTARTDATE) |
| cdm_employmentenddate   (cdm_employmentenddate)                 | EMPLOYMENTENDDATE   (EMPLOYMENTENDDATE)     |
| cdm_workertype   (cdm_workertype)                               | WORKERTYPE   (WORKERTYPE)                   |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)         |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | LEGALENTITYID   (LEGALENTITYID)             |

### <a name="employments-to-employment-detail"></a>Impieghi a Dettaglio impiego

| Tabella Dataverse (origine)                             | Entità di Finance (destinazione)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE   (EMPLOYMENTSTARTDATE)   |
| cdm_employmentenddate   (cdm_employmentenddate)                 | EMPLOYMENTENDDATE   (EMPLOYMENTENDDATE)       |
| cdm_validfrom   (Data di inizio validità)                                    | VALIDFROM   (VALIDFROM)                       |
| cdm_validto (Data di fine validità)                                        | VALIDTO (VALIDTO)                             |
| cdm_workerstartdate   (cdm_workerstartdate)                     | WORKERSTARTDATE   (WORKERSTARTDATE)           |
| cdm_lastdateworked   (cdm_lastdateworked)                       | LASTDATEWORKED   (LASTDATEWORKED)             |
| cdm_transitiondate   (cdm_transitiondate)                       | TRANSITIONDATE   (TRANSITIONDATE)             |
| cdm_employerunitofnotice   (cdm_employerunitofnotice)           | EMPLOYERUNITOFNOTICE   (EMPLOYERUNITOFNOTICE) |
| cdm_workerunitofnotice   (cdm_workerunitofnotice)               | WORKERUNITOFNOTICE   (WORKERUNITOFNOTICE)     |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | LEGALENTITYID   (LEGALENTITYID)               |
| cdm_employernoticeamount   (cdm_employernoticeamount)           | EMPLOYERNOTICEAMOUNT   (EMPLOYERNOTICEAMOUNT) |
| cdm_workernoticeamount   (cdm_workernoticeamount )              | WORKERNOTICEAMOUNT   (WORKERNOTICEAMOUNT)     |

### <a name="position-worker-assignment-to-position-worker-assignments"></a>Assegnazione lavoratore posizione a Assegnazioni lavoratori posizioni

| Tabella Dataverse (origine)                             | Entità di Finance (destinazione)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_jobpositionnumber   (Numero posizione)                   | POSITIONID(POSITIONID)                        |
| cdm_validfrom   (Data di inizio validità)                                    | VALIDFROM   (VALIDFROM)                       |
| cdm_validto (Data di fine validità)                                        | VALIDTO (VALIDTO)                             |

### <a name="worker-addresses-to-worker-postal-address-v2"></a>Indirizzi lavoratore a Indirizzo postale lavoratore V2

| Tabella Dataverse (origine)                             | Entità di Finance (destinazione)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_addresstype   (cdm_addresstype)                             | ADDRESSLOCATIONROLES   (ADDRESSLOCATIONROLES) |
| cdm_line1   (cdm_line1)                                         | ADDRESSSTREET   (ADDRESSSTREET)               |
| cdm_city (cdm_city)                                             | ADDRESSCITY   (ADDRESSCITY)                   |
| cdm_stateorprovince   (cdm_stateorprovince)                     | ADDRESSSTATE   (ADDRESSSTATE)                 |
| cdm_postalcode   (cdm_postalcode)                               | ADDRESSZIPCODE(ADDRESSZIPCODE)                |
| cdm_countryregion   (cdm_countryregion)                         | ADDRESSCOUNTRYREGION(ADDRESSCOUNTRYREGION)    |
| cdm_addressnumber   (cdm_addressnumber)                         | ADDRESSLOCATIONID(ADDRESSLOCATIONID)          |
| cdm_ispreferred   (cdm_ispreferred)                             | ISPRIMARY   (ISPRIMARY)                       |
| cdm_county   (cdm_county)                                       | ADDRESSCOUNTYID(ADDRESSCOUNTYID)              |
| cdm_addresstype   (cdm_addresstype)                             | ADDRESSDESCRIPTION(ADDRESSDESCRIPTION)        |

## <a name="integration-considerations"></a>Considerazioni sull'integrazione

L'integrazione da Human Resources a Finance tenta di abbinare i record in base all'ID. Se i record corrispondono, l'integrazione dei dati sovrascrive i dati in Finance con i valori in Human Resources. Tuttavia, può verificarsi un problema se logicamente si tratta di record differenti e lo stesso ID è stato generato in Human Resources o Finance in base alla rispettiva sequenza numerica.

Questo problema si può verificare con **Lavoratore**, che utilizza **Numero dipendente** per creare la corrispondenza e **Posizioni**. Le posizioni lavorative non utilizzano sequenze numeriche. Di conseguenza, se lo stesso ID posizione lavorativa è presente in Human Resources e Finance, le informazioni di Human Resources sovrascrivono quelle di Dynamics 365 Finance. 

Per evitare problemi con ID duplicati, è possibile aggiungere un prefisso nella [sequenza numerica](/dynamics365/unified-operations/fin-and-ops/organization-administration/number-sequence-overview?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json) oppure impostare un numero iniziale nella sequenza numerica che non rientra nell'intervallo dell'altro sistema. 

L'ID ubicazione utilizzato per l'indirizzo del lavoratore non fa parte di una sequenza numerica. Quando si integra un indirizzo di lavoratore da Human Resources a Finance, se l'indirizzo esiste già in Finance, è possibile che venga creato un record di indirizzo duplicato. 

Nelle figura seguenti viene illustrato un esempio di mapping di modello nel servizio di integrazione di dati. 

![Mapping modello.](./media/IntegrationMapping.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
