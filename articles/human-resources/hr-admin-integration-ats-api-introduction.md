---
title: Introduzione all'API di integrazione del sistema di tracciabilità dei candidati
description: Questo argomento descrive l'API di integrazione del sistema di tracciabilità dei candidati (ATS) Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 48e368fe69443a5105ddba78a887bf9159bfe52a
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125595"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a>Introduzione all'API di integrazione del sistema di tracciabilità dei candidati

Questo argomento descrive l'API di integrazione del sistema di tracciabilità dei candidati (ATS) Dynamics 365 Human Resources. Lo scopo dell'API è abilitare le integrazioni semplificate tra Dynamics 365 Human Resources e i sistemi ATS dei partner.

![Flusso di integrazione ATS](media/hr-admin-integration-ats-api-introduction-flow.png)

L'esperienza integrata inizia in Human Resources quando un responsabile delle assunzioni crea una richiesta di reclutamento. Quando la richiesta viene attivata, l'ATS estrae i dettagli della richiesta per creare un progetto di reclutamento. Quindi segue la pipeline di reclutamento per selezionare e assumere un candidato per le posizioni. Infine, l'ATS completa l'integrazione round trip inviando il record del candidato selezionato in Human Resources. Il record del candidato può quindi passare attraverso più convalide e flussi di lavoro di onboarding per creare il record del dipendente.

Per abilitare l'integrazione, Human Resources ha aggiunto i seguenti componenti:

1.  Funzionalità per creare una richiesta di reclutamento.
2.  Un profilo candidato ampliato e flussi di lavoro correlati.
3.  Un'API di integrazione che apre le nuove funzionalità alle applicazioni di integrazione.

Per ulteriori informazioni sulla configurazione e l'utilizzo della richiesta di reclutamento e della funzionalità candidato, vedi [Selezione dei candidati](hr-personnel-recruit.md).

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

Questa API è creata su Microsoft Dataverse (in precedenza Common Data Service). Tutta l'interazione RESTful con questa API viene eseguita tramite l'API Web Microsoft Dataverse, che utilizza OData. Questa API è un sottoinsieme di API Web Dataverse. L'API Web Dataverse definisce caratteristiche quali autenticazione, SLA, batch, controllo della concorrenza e gestione degli errori.

Per ulteriori informazioni generali sull'API Web Microsoft Dataverse, vedi:

- [Che cos'è Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)
- [Usa l'API Web Microsoft Dataverse](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)
- [Guida per gli sviluppatori Microsoft Dataverse](https://docs.microsoft.com/powerapps/developer/data-platform)

La documentazione di cui sopra include dettagli e indicazioni per sviluppatori sull'utilizzo dell'API Web Dataverse, ad esempio [gestione dell'autenticazione](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/authenticate-web-api), [esecuzione delle operazioni](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/perform-operations-web-api), [uso di Postman con l'API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/use-postman-web-api) e [uso del rilevamento delle modifiche o i token delta](https://docs.microsoft.com/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) con l'API.

### <a name="option-sets"></a>Set di opzioni

Il modello di dati per l'API di integrazione ATS descritto in questo documento include set di opzioni che forniscono valori enumerati associati alle proprietà dell'entità. Per i dettagli su come lavorare con i set di opzioni nell'API Web Dataverse, vedi [Crea e aggiorna i set di opzioni utilizzando l'API Web](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets). I set di opzioni sono definiti per ciascun ambiente Dataverse.

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Tabelle virtuali per Human Resources in Dataverse

Gli endpoint per l'API di integrazione ATS utilizzano le funzionalità della piattaforma di tabelle virtuali di Microsoft Dataverse. Per impostazione predefinita, le tabelle virtuali e gli endpoint API associati non vengono distribuiti per gli ambienti Human Resources, consentendo alle organizzazioni di determinare quali endpoint OData saranno esposti per l'ambiente. Per utilizzare l'API, le tabelle virtuali per le entità Human Resources devono essere generate per l'ambiente. 

Per informazioni sulla generazione delle tabelle virtuali per l'API, vedi [Configura tabelle virtuali Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

## <a name="data-model"></a>Modello dati

Il modello di dati è incentrato su due entità principali:

- **RecruitingRequest** rappresenta una richiesta a un ATS di reclutare per una o più posizioni aperte. Per una query di esempio, vedi [Query di esempio per richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-example-query.md).
- **CandidateToHire** rappresenta i dettagli di un candidato che ha accettato un'offerta per una posizione. **Person** rappresenta l'individuo che è il candidato. Una persona può avere più ruoli nell'azienda, come candidato, lavoratore, dipendente o terzista. Per una query di esempio, vedi [Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).

Nel diagramma riportato di seguito vengono illustrate le relazioni all'interno dell'API. Diversi tipi hanno chiavi esterne per altre entità preesistenti in Human Resources che non sono illustrate qui. Questo documento fornisce informazioni sulle entità specifiche per gli scenari di integrazione della selezione. Tuttavia, ci sono molte altre entità nell'API Web Dataverse per Dynamics 365 Human Resources potrebbe anche essere rilevante per la tua integrazione. Ad esempio, potresti anche aver bisogno di dettagli per lavoratori, lavori, posizioni o altre entità non definite qui. Molte di queste entità sono referenziate in relazioni di chiavi esterne o proprietà di navigazione.

![Modello di dati dell'API di integrazione ATS](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a>Richiesta di selezione ed entità correlate e set di opzioni

Query di esempio: 

- [Query di esempio per la richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-example-query.md)

Entità:

- [Richiesta di selezione](hr-admin-integration-ats-api-recruiting-request.md)
- [Posizione richieste di selezione](hr-admin-integration-ats-api-recruiting-request-position.md)
- [Competenza di richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [Istruzione richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-education.md)
- [Percorso richieste di selezione](hr-admin-integration-ats-api-recruiting-request-location.md)

Set di opzioni:

- [Stato esenzione mansione](hr-admin-integration-ats-api-job-exempt-status.md)
- [Stato della posizione della richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [Stato della richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-status.md)
- [Categoria di lavoro normativa](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a>Candidato da assumere ed entità correlate e set di opzioni

Query di esempio:

- [Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

Entità:

- [Candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire.md)
- [Persona](hr-admin-integration-ats-api-person.md)
- [Educazione della persona](hr-admin-integration-ats-api-person-education.md)
- [Esperienza professionale persona](hr-admin-integration-ats-api-person-professional-experience.md)
- [Indirizzo della persona](hr-admin-integration-ats-api-person-address.md)
- [Contatto parte](hr-admin-integration-ats-api-party-contact.md)
- [Competenza della persona](hr-admin-integration-ats-api-person-skill.md)
- [Livello di valutazione](hr-admin-integration-ats-api-rating-level.md)
- [Certificato della persona](hr-admin-integration-ats-api-person-certificate.md)
- [Tipo di certificato](hr-admin-integration-ats-api-certificate-type.md)
- [Screening persona](hr-admin-integration-ats-api-person-screening.md)
- [Tipi di screening](hr-admin-integration-ats-api-screening-types.md)
- [Numero di identificazione persona](hr-admin-integration-ats-api-person-identification-number.md)

Set di opzioni:

- [Risultati integrazione candidato](hr-admin-integration-ats-api-applicant-integration-result.md)
- [Vuoto Sì No](hr-admin-integration-ats-api-blank-yes-no.md)
- [Stato di completamento](hr-admin-integration-ats-api-completion-status.md)
- [Tipo di contatto](hr-admin-integration-ats-api-contact-type.md)
- [Base di credito per l'istruzione](hr-admin-integration-ats-api-education-credit-basis.md)
- [Genere](hr-admin-integration-ats-api-gender.md)
- [Stato civile](hr-admin-integration-ats-api-marital-status.md)
- [Mesi dell'anno](hr-admin-integration-ats-api-months-of-year.md)
- [No/Sì](hr-admin-integration-ats-api-no-yes.md)
- [Unità del periodo](hr-admin-integration-ats-api-period-unit.md)
- [Frequenza di screening](hr-admin-integration-ats-api-screening-frequency.md)
- [Frequenza di screening generata da](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [Tipo di livello di competenza](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a>Vedere anche

[Selezione dei candidati](hr-personnel-recruit.md)<br>
[Che cos'è Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[Usa l'API Web Microsoft Dataverse](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)<br>
[Crea e aggiorna i set di opzioni utilizzando l'API Web](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]