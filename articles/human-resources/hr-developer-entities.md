---
title: Tabelle Dataverse
description: Microsoft Dynamics 365 Human Resources utilizza Dataverse per abilitare scenari di estendibilità e integrazione.
author: twheeloc
ms.date: 12/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 51be30f10c8e5f5e962f54f720f66c712a785835
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838584"
---
# <a name="dataverse-tables"></a>Tabelle Dataverse


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources utilizza Dataverse per abilitare scenari di estendibilità e integrazione.

> [!NOTE]
> Le entità di Human Resources corrispondono alle tabelle Dataverse. Per ulteriori informazioni su Dataverse (in precedenza Common Data Service) e aggiornamenti terminologici, vedi [ Cosa è Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)

Le seguenti tabelle Dataverse sono disponibili in base alle entità di Human Resources.

Per ulteriori informazioni sui problemi noti, vedi [Ricerca argomento in Lifecycle Services (LCS)](/dev-itpro/lifecycle-services/issue-search-lcs).

## <a name="benefit-tables"></a>Tabelle dei benefit

| Name | Tabella | Problemi noti  | Status |
| --- | --- |    --------|----------  |
| Frequenza di calcolo benefit | cdm_benefitcalculationfrequency |     |     |
| Periodo retributivo della frequenza di calcolo benefit | cdm_benefitcalculationfrequencypayperiod |     |     |
| Coefficiente di calcolo benefit | cdm_benefitcalculationrate |    |     |
| Dettagli dei coefficienti di calcolo benefit | cdm_benefitcalculationratedetail |753225 | Risolto  |
| Opzione benefit | cdm_benefitoption |    |     |
| Piano benefit | cdm_benefitplan (Non abilitato per il supporto del campo personalizzato) |    |     |
| Tipo di benefit | cdm_benefittype |    |     |

## <a name="business-process-tasks-tables"></a>Tabelle attività di processi aziendali

| Name | Tabella |Problemi noti  | Status |
| --- | --- |   --------|----------   |
| Calendario di processi aziendali | cdm_businessprocesscalendar | 751867 | Risolto |
| Assegnazione gruppo di processi aziendali | cdm_businessprocessgroupassignment | 751869 751863 | Attivi|
| Gruppo di attività libreria processi aziendali | cdm_businessprocesslibrarytaskgroup |751866 | Chiuse |
| Fase di processi aziendali | cdm_businessprocessstage |      |     |
| Intestazione modello elenco di controllo | cdm_businessprocesstemplateheader |     |     |
| Attività del modello elenco di controllo | cdm_businessprocesstemplatetask |      |     |

## <a name="compensation-tables"></a>Tabelle retribuzioni

| Name | Tabella |Problemi noti  | Status |
| --- | --- | ----------      | -------    |
| Piano di retribuzione fissa | cdm_compensationfixedplan |754453 | Chiuse |
| Griglia di retribuzione | cdm_compensationgrid |             |     |
| Livello retributivo | cdm_compensationlevel |           |     |
| Frequenza della retribuzione | cdm_compensationpayfrequency |                  |     |
| Impostazione punti di riferimento per le retribuzioni | cdm_compensationreferencepointsetup |               |     |
| Riga impostazione punti di riferimento per le retribuzioni | cdm_compensationreferencepointsetupline |             |     |
| Paese di retribuzione | cdm_compensationregion |                   |     |
| Struttura retributiva | cdm_compensationstructure |    754456        | Chiuse    |
| Piano di retribuzione variabile | cdm_compensationvariableplan |               |     |
| Livello del piano di retribuzione variabile | cdm_compensationvariableplanlevel |                |     |
| Tipo di piano di retribuzione variabile | cdm_compensationvariableplantype |               |     |
| Evento di retribuzione fissa | cdm_fixedcompensationevent |               |     |
| Regola di distribuzione incentivi | cdm_vestingrule |              |     |
| Retribuzione fissa del lavoratore | cdm_workerfixedcompensation |              |     |

## <a name="organization-tables"></a>Tabelle organizzazione

| Name | Tabella |Problemi noti  | Status |
| --- | --- | ----------      | -------    |
| Reparto | cdm_department |  752194    | Chiuse    |
| Impiego | cdm_employment | 762414  |  Chiuse  |
| Società | cdm_company |  |     |
| Posizione | cdm_job |  |     |
| Funzione lavorativa | cdm_jobfunction |        |     |
| Posizione lavorativa | cdm_jobposition | 752214      | Chiuse    |
| Tipo di posizione | cdm_positiontype |            |     |
| Assegnazione lavoratore posizione | cdm_positionworkerassignmentmap | 752224    |  Chiuse   |
| Dimensione posizione lavorativa | cdm_jobpositiondimension|       |     |
| Tipo di posizione | cdm_jobtype |      |     |
| Lingua | cdm_language |        |     |
| Funzione | cdm_title |       |     |

> [!NOTE]
> Le dimensioni finanziarie per **Tipo di posizione**, **Assegnazione lavoratore posizione** e **Impiego** forniscono l'integrazione in una direzione per Dataverse. Gli aggiornamenti sulle dimensioni finanziarie al momento non vengono sincronizzati da Dataverse a Human Resources. 

## <a name="leave-and-absence-tables"></a>Tabelle congedi e assenze

| Name | Tabella | Problemi noti  | Status |
| --- | --- |   ----------      | -------    |
| Transazione bancaria per congedo | cdm_leavebanktransaction |  752252    |    Risolto |
| Iscrizione al piano di congedo | cdm_leaveenrollment |  752934    |Chiuse     |
| Piano di congedo | cdm_leaveplan |   752232   |   Chiuse  |
| Richiesta di congedo | cdm_leaverequest | 753207     | Chiuse    |
| Dettagli richiesta congedo | cdm_leaverequestdetail | 753207     |   Chiuse  |
| Tipo di congedo | cdm_leavetype |      |     |
| Codice motivo del tipo di congedo | cdm_leavetypereasoncode |         |     |

>[!NOTE]
>L'integrazione a doppia scrittura utilizzando le tabelle di Dataverse per congedi e assenze è disponibile solo quando la funzione **Configura più tipi di congedo in un piano di congedo singolo** è abilitata in Microsoft Dynamics 365 Finance utilizzando **Gestione funzionalità**. 

## <a name="payroll-tables"></a>Tabelle retribuzioni

| Name | Tabella |Problemi noti  | Status |
| --- | --- |  ----------      | -------    |
| Ciclo retributivo | cdm_paycycle |    |     |
| Periodo retributivo | cdm_payperiod |          |     |
| Codice di reddito retribuzioni | cdm_payrollearningcode |   754458        |   Chiuse  |
| Esborso conto bancario | cdm_bankaccountdisbursement |    751904     |   Chiuse  |
| Regione fiscale | cdm_taxregion |          |     |

## <a name="worker-tables"></a>Tabelle lavoratori

| Name | Tabella |Problemi noti  | Status |
| --- | --- |----------      | -------    |
| Lavoro | cdm_worker |    751906    |    Chiuse |
| Indirizzo del lavoratore | cdm_workeraddress |   754465     |Chiuse     |
| Dati personali lavoratore | cdm_workerpersonaldetail |   751906     |   Chiuse  |
| Numero di identificazione lavoratore | cdm_workerpersonidentificationnumber |  766704      |   Chiuse  |
| Tipo di identificazione lavoratore | cdm_workerpersonidentificationtype |        |     |
| Calendario lavorativo | cdm_workcalendar |        |     |
| Giorno calendario di lavoro | cdm_workcalendarday |        |     |
| Festività calendario lavorativo |cdm_workcalendarholiday |        |     |
| Riga festività del calendario di lavoro | cdm_workcalendarholidayline |        |     |
| Intervallo orario calendario di lavoro | cdm_workcalendartimeinterval (Non abilitato per il supporto del campo personalizzato) |        |     |
| Conto bancario del lavoratore | cdm_workerbankaccount |        |     |

## <a name="worker-setup-tables"></a>Tabelle di configurazione dei lavoratori

| Nome | Tabella |
| --- | --- |
| Stato veterano | cdm_veteranstatus |
| Origine etnica | cdm_ethnicorigin |
| Codice causale | cdm_reasoncode |
| Agenzia emittente dell'identificazione personale. | cdm_personidentificationissuingagency |

## <a name="competency-tables"></a>Tabelle delle competenze

| Nome | Tabella |
| --- | --- |
| Tipo di competenza | cdm_skilltype |

## <a name="table-relationship-models"></a>Modelli di relazioni tra tabelle

### <a name="worker"></a>Lavoro

![Lavoratore.](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Lavoro e posizione lavorativa

![Lavoro e posizione lavorativa.](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Benefit

![Benefit.](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Retribuzione

![Retribuzione.](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Esci

![Congedo.](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Calendario lavorativo

![Calendario lavorativo.](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>Vedere anche

[Scegliere una tecnologia di integrazione dei dati](hr-admin-integration-choose-technology.md)<br>
[Configurare l'integrazione di Dataverse](hr-admin-integration-common-data-service.md)<br>
[Configurare tabelle virtuali in Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Domande frequenti sulle tabelle virtuali in Human Resources](hr-admin-virtual-entity-faq.md)<br>
[Che cos'è Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Aggiornamenti terminologici](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
