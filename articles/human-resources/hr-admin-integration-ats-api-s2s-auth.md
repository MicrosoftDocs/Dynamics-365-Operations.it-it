---
title: Autenticazione da server a server per l'API di integrazione ATS
description: Questo argomento descrive come impostare l'autenticazione da server a server per le integrazioni rispetto all'API di integrazione ATS (Applicant Tracking System, sistema di tracciabilità dei candidati) di Dynamics 365 Human Resources.
author: jaredha
ms.date: 06/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 350fb5a00b85f28fa8aef2ca50cf1f277b8f635e
ms.sourcegitcommit: e4cc43b06ef3f0f562849e2c960025cb244d6017
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2022
ms.locfileid: "8743543"
---
# <a name="server-to-server-authentication-for-the-ats-integration-api"></a>Autenticazione da server a server per l'API di integrazione ATS


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive come impostare l'autenticazione da server a server per le integrazioni rispetto all'API di integrazione ATS (Applicant Tracking System, sistema di tracciabilità dei candidati) di Dynamics 365 Human Resources. È necessario gestire due livelli di sicurezza per l'entità servizio per accedere ai dati associati e alla tabella virtuale di Microsoft Dataverse. L'utente deve ottenere l'accesso alla tabella virtuale di Dataverse in Microsoft Power Platform e l'accesso ai dati in Dynamics 365 Human Resources.

## <a name="enable-access-to-dataverse-virtual-tables-in-power-platform"></a>Abilitare l'accesso alle tabelle virtuali di Dataverse in Power Platform

Il primo passaggio per abilitare l'accesso alle tabelle virtuali di Dataverse in Power Platform consiste nel configurare l'applicazione in Power Platform per l'autenticazione rispetto agli endpoint delle tabelle virtuali di Dataverse. I passaggi per eseguire questa operazioni sono descritti nellla [guida per gli sviluppatori di Microsoft Dataverse](/powerapps/developer/data-platform).

  - Per le registrazioni app a singolo tenant: [utilizzare l'autenticazione da server a server a singolo tenant](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication)
  - Per le registrazioni app multi-tenant: [utilizzare l'autenticazione da server a server multi-tenant](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication)

### <a name="creating-a-security-role-for-ats-integrations"></a>Creazione di un ruolo di sicurezza per le integrazioni ATS

Uno dei passaggi successivi alla creazione dell'utente dell'applicazione consiste nell'assegnare all'utente un ruolo di sicurezza che definisca l'accesso che l'applicazione avrà agli endpoint. Questo è il passaggio 7 in [Creazione dell'utente dell'applicazione](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication#application-user-creation) per le registrazioni app a singolo tenant e [Creare un ruolo di sicurezza per l'utente dell'applicazione](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication#create-a-security-role-for-the-application-user) per le registrazioni multi-tenant. 

Il ruolo a cui si assegna l'utente dell'applicazione dovrebbe avere accesso alle entità di dati utilizzate per l'integrazione ATS. Questo non è immediatamente disponibile, pertanto sarà necessario creare un nuovo ruolo di sicurezza. Il nuovo ruolo può essere creato seguendo i passaggi descritti in [Creare un ruolo di sicurezza](/power-platform/admin/create-edit-security-role#create-a-security-role).

Per il nuovo ruolo, l'accesso appropriato deve essere assegnato, come minimo, alle seguenti entità nella scheda **Entità personalizzate** del nuovo ruolo. Potrebbero esistere entità aggiuntive da aggiungere se l'integrazione utilizza dati dell'applicazione più estesi. Dopo essere stato creato, il nuovo ruolo potrà essere assegnato all'utente dell'applicazione.

  - Lavoratore base (mshr)
  - Candidato da assumere (mshr)
  - Competenza certificato (mshr)
  - Tipo certificato (mshr)
  - Società
  - Funzione lavorativa compensazione (mshr)
  - Tipo mansione compensazione (mshr)
  - Paese/aree geografiche (mshr)
  - Reparto (mshr)
  - Competenza istruzione (mshr)
  - Grado di istruzione (mshr)
  - Discipline didattiche (mshr)
  - Requisiti istruttivi (mshr)
  - Identificazione (mshr)
  - Tipo di identificazione (mshr)
  - Istituto (mshr)
  - Agenzia emittente (mshr)
  - Retribuzione mansione (mshr)
  - Mansioni (mshr)
  - Livello di istruzione (mshr)
  - Contatti parti (mshr)
  - Persone (mshr)
  - Indirizzi persone (mshr)
  - Screening persone (mshr)
  - Tipo posizione (mshr)
  - Posizioni V2 (mshr)
  - Competenza esperienza professionale (mshr)
  - Livello di valutazione (mshr)
  - Modelli di valutazione (mshr)
  - Codici motivo (mshr)
  - Richiesta selezione (mshr)
  - Percorso richiesta selezione (mshr)
  - Posizione richiesta selezione (mshr)
  - Competenze richiesta selezione (mshr)
  - Tipo di screening (mshr)
  - Competenza abilità (mshr)
  - Abilità (mshr)
  - Titoli (mshr)
  - Stato veterano (mshr)
  - Lavoratore (mshr)

## <a name="granting-application-permissions-to-human-resources-data"></a>Concessione delle autorizzazioni dell'applicazione ai dati delle Risorse umane

Il secondo passaggio consiste nell'assicurare che all'applicazione vengano concesse le autorizzazioni appropriate per i dati delle Risorse umane collegandola a un utente nell'applicazione delle Risorse umane. Per un utente dell'applicazione, le chiamate da server a server tramite le tabelle virtuali di Dataverse vengono eseguite nel contesto dell'identità dell'utente (app) in Dataverse che sta chiamando l'azione. Il servizio adattatore della tabella virtuale cerca l'utente associato nelle Risorse umane ed esegue la query nel contesto di quell'utente. Ciò significa che è necessario creare un utente nelle Risorse umane con i ruoli corretti assegnati per fornire l'accesso ai dati di cui necessiterà l'applicazione di integrazione.

L'utente delle Risorse umane dovrà inoltre ricevere le autorizzazioni corrette per i dati nelle Risorse umane. Il ruolo **Applicazione di selezione** (HcmRecruitingIntegrator) è disponibile con privilegi per le entità primarie necessarie per l'integrazione con i dati di selezione. Questo ruolo può essere assegnato all'utente dell'applicazione nella pagina **Utenti** per concedere l'accesso appropriato ai dati. Per ulteriori informazioni sui ruoli di sicurezza delle Risorse umane, vedere [Sicurezza basata sui ruoli](/dynamics365/fin-ops-core/dev-itpro/sysadmin/role-based-security).

### <a name="set-up-the-new-user-with-appropriate-permissions"></a>Configurare il nuovo utente con le autorizzazioni appropriate

Per configurare il nuovo utente con le autorizzazioni appropriate, procedere come segue:

  1. Aprire la pagina **Utenti** nelle Risorse umane e selezionare **Nuovo**.
  2. Immettere un **ID utente** e un **nome utente** per il nuovo utente dell'applicazione. Ad esempio, è possibile immettere "RecruitingIntegration".

      > [!NOTE]
      > Se l'app non dispone di un indirizzo e-mail o di un account utente di Microsoft Azure Active Directory (Azure AD), è possibile inserire qualcosa come "RecruitingApp" nei campi indirizzo e-mail e provider dell'utente.

  3. Nella Scheda dettaglio **Ruoli utente** selezionare l'azione **Assegna ruoli**.
  4. Nel riquadro **Assegna ruoli all'utente** selezionare **Applicazione di selezione** e selezionare **OK**.
  5. Salvare il nuovo record utente.

### <a name="link-the-new-human-resources-user-to-the-application"></a>Collegare il nuovo utente delle Risorse Umane all'applicazione

Dopo che l'utente è stato creato, è necessario creare un record per l'applicazione nel modulo Applicazioni di **Azure Active Directory** per collegare l'app all'utente delle Risorse umane.

  1. Aprire il modulo **Applicazioni di Azure Active Directory** e selezionare **Nuovo**.
  2. Nel campo **ID client** immettere l'ID client dellutente dell'applicazione creato per l'applicazione.
  3. Nel campo **Nome** immettere il nome dell'applicazione di integrazione.
  4. Nel campo **ID utente** selezionare il nuovo utente delle Risorse umane creato per l'integrazione di selezione.
  5. Salvare il nuovo record.

L'applicazione potrà ora accedere ai dati delle Risorse Umane, limitatamente ai soli dati necessari per le integrazioni dell'applicazione di selezione.

## <a name="see-also"></a>Vedere anche

[Selezione dei candidati](hr-personnel-recruit.md)<br>
[Che cos'è Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Usa l'API Web Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>
[Crea e aggiorna i set di opzioni utilizzando l'API Web](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
