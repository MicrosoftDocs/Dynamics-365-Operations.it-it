---
title: Impostare e gestire la collaborazione fornitore
description: In questo argomento viene spiegato come impostare la collaborazione fornitore in Dynamics 365 Supply Chain Management. Spiega inoltre come eseguire il provisioning di nuovi utenti di collaborazione fornitore e gestire i ruoli di sicurezza per tali utenti.
author: GalynaFedorova
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirExternalRole, SysUserRequestListPage, VendVendorPortalUsers, WorkflowTableListPageRnr
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 220774
ms.assetid: 69d05e8b-7dc2-48ea-bc24-bea9ac963579
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4b59513d86426d3c1bfd759b9aabc331e58d5423
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677564"
---
# <a name="set-up-and-maintain-vendor-collaboration"></a>Impostare e gestire la collaborazione fornitore

[!include [banner](../includes/banner.md)]

L'interfaccia di collaborazione fornitore mostra un set limitato di informazioni sugli ordini fornitore, fatture e scorte di spedizione agli utenti fornitori esterni. Da questa interfaccia, un fornitore può anche rispondere alle richieste di offerta (RdO) e visualizzare e modificare le informazioni aziendali di base.

In questo argomento viene spiegato come impostare la collaborazione fornitore in Dynamics 365 Supply Chain Management. Spiega inoltre come impostare un flusso di lavoro per eseguire il provisioning di nuovi utenti di collaborazione fornitore e come gestire i ruoli di sicurezza per tali utenti.

> [!NOTE]
> Le informazioni sull'impostazione dei ruoli di sicurezza per la collaborazione fornitore si applicano solo alla versione corrente di Finance and Operations. In Microsoft Dynamics AX 7.0 (febbraio 2016) e Microsoft Dynamics AX versione applicazione 7.0.1 (maggio 2016), è possibile collaborare con i fornitori tramite il modulo del **Portale fornitori**. Per informazioni sulle autorizzazioni utente per il portale fornitori in Microsoft Dynamics AX, vedi [Sicurezza degli utenti del portale per fornitori](configure-security-vendor-portal-users.md).

## <a name="set-up-vendor-collaboration-security-roles"></a>Impostare i ruoli di sicurezza della collaborazione fornitore

Un responsabile approvvigionamenti o un fornitore che dispone di autorizzazioni sufficienti può richiedere che una persona di contatto venga fornita come utente abilitando **Fornitura utente fornitore** sul record della persona di contatto. Durante il processo di provisioning, vengono selezionate le autorizzazioni utente per il nuovo utente esterno e viene inviata la richiesta del nuovo utente fornitore. È importante impostare correttamente le autorizzazioni utente disponibili per la selezione nella richiesta utente fornitore. In caso contrario, ai fornitori potrebbe essere concesso l'accesso a informazioni a cui non dovrebbero avere accesso in Supply Chain Management.

### <a name="set-up-the-security-roles-that-are-available-for-selection-when-a-new-user-request-is-used-for-a-contact-person"></a>Impostare i ruoli di sicurezza disponibili per la selezione quando viene utilizzata una nuova richiesta utente per una persona di contatto

1. Seleziona **Amministrazione di sistema** &gt; **Sicurezza** &gt; **Ruoli esterni**.
2. Seleziona **Nuovo**, quindi seleziona un ruolo di sicurezza e il ruolo di parte **Fornitore**.

Potresti voler aggiungere i ruoli **Amministratore fornitore (esterno)** e **Fornitore (esterno)** forniti in Supply Chain Management. In alternativa, puoi utilizzare i ruoli di sicurezza creati dalla tua azienda.

Dovresti accertarti che il ruolo **Amministratore fornitore (esterno)** sia disponibile solo se i fornitori devono essere in grado di creare nuovi contatti, inviare richieste utente di collaborazione fornitore per nuovi utenti e modifiche alle informazioni utente e gestire tali richieste tramite un flusso di lavoro.

Se prevedi di impostare manualmente i contatti e gli utenti del fornitore, puoi rendere solo il **Ruolo fornitore (esterno)** disponibile. Questo ruolo sarà quindi l'unico ruolo che può essere richiesto tramite una richiesta utente del fornitore.

> [!NOTE]
> Il ruolo **SystemUser** viene concesso automaticamente quando si crea manualmente un nuovo account utente. Pertanto, è necessario rimuovere quel ruolo e assegnare il ruolo **SystemExternalUser**. Se vengono creati nuovi account utente tramite il flusso di lavoro avviato da una richiesta utente del fornitore per il provisioning di un nuovo utente, uno o più ruoli che hai impostato per la collaborazione fornitore e il ruolo **SystemExternalUser** saranno assegnati.

#### <a name="vendor-admin-external-security-role"></a>Ruolo di sicurezza amministratore fornitore (esterno)

Il ruolo **Amministratore fornitore (esterno)** può essere utilizzato per fornitori esterni che gestiscono le informazioni di contatto del fornitore ed effettuano richieste per il provisioning di nuovi utenti di collaborazione fornitore. Gli utenti esterni che hanno questo ruolo di sicurezza possono eseguire le seguenti attività:

- Visualizza e modifica le informazioni sul contatto, come la posizione lavorativa, l'indirizzo e-mail e il numero di telefono della persona.
- Aggiungi un contatto nuovo o esistente agli account fornitore per cui è contatto.
- Elimina qualsiasi contatto creato.
- Attiva o disattiva l'associazione tra un contatto e un conto fornitore. Dopo che l'associazione tra un contatto e un conto fornitore è stata disattivata, non è possibile fare riferimento al contatto nei nuovi ordini di acquisto o altri documenti.
- Nega o consenti a un contatto l'accesso ai documenti dell'interfaccia di collaborazione fornitore specifici per il conto fornitore. Dopo che l'associazione tra un contatto e un conto fornitore è stata disattivata, l'accesso ai documenti specifici del conto fornitore viene sempre negato.
- Richiedi un nuovo account utente per un contatto utilizzando l'azione **Provisioning utente**.
- Richiedi la disattivazione dell'account utente del contatto.
- Richiedi che l'account utente del contatto venga modificato per aggiungere o rimuovere ruoli di sicurezza.
- Visualizza le RdO.

#### <a name="vendor-external-security-role"></a>Ruolo di sicurezza fornitore (esterno)

Il **Ruolo fornitore (esterno)** può essere utilizzato per fornitori esterni che lavoreranno con gli ordini fornitore. Gli utenti esterni che hanno questo ruolo di sicurezza possono eseguire le seguenti attività:

- Rispondi e visualizza le informazioni sugli ordini fornitore.
- Gestisci fatture di collaborazione fornitore.
- Visualizza inventario spedizione.
- Visualizza e rispondi alle RdO.
- Visualizza le informazioni sul fornitore.

## <a name="set-up-security-roles-that-are-used-when-prospective-vendors-are-onboarded"></a>Imposta i ruoli di sicurezza che vengono utilizzati quando i potenziali fornitori sono inseriti

Per eseguire l'onboarding di fornitori avviati tramite una richiesta di registrazione fornitore potenziale, è necessario configurare un ruolo di sicurezza esterno. Questo ruolo verrà assegnato ai nuovi utenti durante il processo di provisioning controllato dal flusso di lavoro di tipo **Flusso di lavoro richiesta utente (piattaforma)**. Per ulteriori informazioni, vedi la sezione [Imposta flussi di lavoro per elaborare le richieste utente di collaborazione fornitore](#set-up-workflows-to-process-vendor-collaboration-user-requests) più avanti in questo argomento.

Per informazioni su come integrare fornitori potenziali, vedi [Eseguire l'onboarding di fornitori](vendor-onboarding.md).

### <a name="set-up-a-security-role-that-is-used-when-a-new-prospective-vendor-user-request-is-submitted"></a>Imposta un ruolo di sicurezza che viene utilizzato quando viene inviata una nuova richiesta utente di fornitore potenziale

1. Seleziona **Amministrazione di sistema** > **Sicurezza** > **Ruoli esterni**.
2. Seleziona **Nuovo**, quindi seleziona un ruolo di sicurezza e il ruolo di parte **Fornitore potenziale**.

Dovresti aggiungere il ruolo **Prospect fornitore (esterno)** fornito in Supply Chain Management.

Il ruolo di sicurezza concederà l'accesso solo alla nuova procedura guidata di registrazione fornitore.

## <a name="set-up-workflows-to-process-vendor-collaboration-user-requests"></a>Imposta flussi di lavoro per elaborare le richieste utente di collaborazione fornitore

Per garantire che tutte le attività pertinenti siano completate e che vengano fornite le approvazioni appropriate, è necessario impostare flussi di lavoro per gestire le richieste utente di collaborazione fornitore.

Le richieste utente di collaborazione fornitore vengono inviate da fornitori esterni che hanno il ruolo di sicurezza **Amministratore fornitore (esterno)** o autorizzazioni simili, o dai responsabili di approvvigionamento nella tua azienda. Possono anche essere generati dalle richieste di registrazione fornitore potenziale durante il processo di onboarding del fornitore.

Sono disponibili tre tipi di richieste:

- Richieste di provisioning di un nuovo utente
- Richieste di disattivazione di un utente esistente
- Richieste di modifica dei ruoli di sicurezza di un utente esistente

Per ulteriori informazioni sulle richieste utente di collaborazione fornitore, vedi [Gestire gli utenti di collaborazione fornitore](manage-vendor-collaboration-users.md).

È necessario creare due o più flussi di lavoro per elaborare tutti e tre i tipi di richieste utente di collaborazione fornitore. I nuovi flussi di lavoro vengono creati nella pagina **Flussi di lavoro utente**.

### <a name="example-of-a-workflow-for-provisioning-new-users-and-modifying-security-roles"></a>Esempio di un flusso di lavoro per il provisioning di nuovi utenti e la modifica dei ruoli di sicurezza

Per gestire le richieste utente fornitore per creare nuovi utenti e modificare i ruoli di sicurezza, è possibile inserire una condizione di ramificazione all'inizio del flusso di lavoro. In questo modo viene utilizzato un ramo diverso del flusso di lavoro, a seconda che la richiesta sia creare un nuovo utente o modificare un utente esistente.

Per impostare questa ramificazione, crea un nuovo flusso di lavoro di tipo **Flusso di lavoro richiesta utente (piattaforma)**. I rami di questo flusso di lavoro possono contenere i seguenti elementi.

#### <a name="branch-to-provision-new-users"></a>Ramo per il provisioning di nuovi utenti

1. Assegna un'attività di approvazione alla persona responsabile dell'approvazione che ai nuovi utenti venga concesso l'accesso alle informazioni sulla collaborazione fornitore.
2. Assegna un'attività alla persona responsabile della richiesta del nuovo account utente Microsoft Azure Active Directory (Azure AD) nel portale di Azure. Usa l'attività predefinita **Invia invito utente B2B Azure** per questo passaggio. Gli utenti B2B possono essere esportati automaticamente in Azure AD. Usa il predefinito **Provisioning utente B2B Azure AD**. Per ulteriori informazioni, vedi [Esportare utenti B2B in Azure AD](../../fin-ops-core/dev-itpro/sysadmin/implement-b2b.md).
3. Assegna un'attività di approvazione alla persona che esegue il caricamento in Azure. Se un account non viene creato correttamente, questa persona rifiuta l'attività e termina il flusso di lavoro. Questa attività di approvazione può essere ignorata se è stato incluso il passaggio che esporta automaticamente i nuovi account utente in Azure tramite l'API B2B.
4. Aggiungi un'attività automatizzata che esegue il provisioning di un nuovo utente. Usa l'attività predefinita **Provisioning automatico utente** per questo passaggio.
5. Aggiungi un'attività che invia una notifica al nuovo utente. Potresti voler inviare al nuovo utente un'e-mail di benvenuto che includa un URL per Supply Chain Management. Questa e-mail può utilizzare un modello che crei nella pagina **Messaggi e-mail** e quindi selezioni nella pagina **Parametri flusso di lavoro utente**. Il modello può includere il tag **%portalURL%**. Quando viene generata l'e-mail di benvenuto, questo tag verrà sostituito dall'URL del tenant di Supply Chain Management.

    > [!NOTE]
    > Questo flusso di lavoro può essere utilizzato in più scenari che coinvolgono l'onboarding dell'utente. Ad esempio, può essere utilizzato quando fornitori potenziali o contatti richiedono un account di collaborazione fornitore. Pertanto, dovresti formulare l'e-mail come una dichiarazione generale che può essere utilizzata per molteplici scopi.

#### <a name="branch-to-modify-security-roles"></a>Ramo per modificare i ruoli di sicurezza

1. Assegna un'attività di approvazione alla persona responsabile dell'approvazione delle modifiche ai ruoli di sicurezza.
2. Aggiungi un'attività automatizzata che aggiunga o rimuova i ruoli di sicurezza pertinenti. Usa l'attività **Provisioning automatico utente** per questo passaggio.

### <a name="example-of-a-workflow-for-inactivating-a-user"></a>Esempio di flusso di lavoro per la disattivazione di un utente

Crea un flusso di lavoro di tipo **Disattiva piattaforma flusso di lavoro richiesta utente** e quindi aggiungi le seguenti attività.

1. Assegna un'attività di approvazione alla persona responsabile dell'accettazione delle richieste di disattivazione di utenti. Puoi aggiungere condizioni per automatizzare questo passaggio di approvazione.
2. Aggiungi un'attività automatizzata che disattivi l'utente. Usa l'attività **Disattivazione automatica utente** per questo passaggio.
3. Aggiungi le eventuali attività di pulizia necessarie. Ad esempio, è possibile aggiungere un'attività che rimuove l'account dalla directory nel portale di Azure.

## <a name="enable-vendor-collaboration-for-a-specific-vendor"></a>Abilitare la collaborazione fornitore per un fornitore specifico

Prima di creare un account utente per una persona che utilizzerà la collaborazione fornitore, è necessario impostare il fornitore e consentire l'uso della collaborazione fornitore. Nella pagina **Fornitori** nella scheda **Generale** impostare il campo **Attivazione collaborazione**. Di seguito vengono illustrate le opzioni disponibili.

- **Attiva (con conferma automatica OF)**- Gli ordini fornitore vengono confermati automaticamente se il fornitore li accetta senza richiedere modifiche.
- **Attiva (senza conferma automatica OF)**- Gli ordini fornitore devono essere confermati manualmente dall'organizzazione dopo che il fornitore li ha accettati.

> [!NOTE]
> Anche i responsabili dell'approvvigionamento della tua azienda possono completare questa attività.

## <a name="troubleshoot-the-provisioning-of-new-vendor-collaboration-users"></a>Risolvere i problemi relativi al provisioning di nuovi utenti di collaborazione fornitore

Il provisioning dei nuovi utenti di collaborazione fornitore avviene tramite il flusso di lavoro impostato per elaborare le richieste utente della collaborazione fornitore di tipo **Provisioning utente fornitore**.

Se l'indirizzo e-mail di un nuovo utente di collaborazione fornitore appartiene a un dominio registrato con Azure come tenant (ovvero, se si tratta di un account di dominio gestito), l'indirizzo e-mail deve essere un account Azure AD. In caso contrario, il processo di provisioning non può essere completato.

Per ulteriori informazioni sul processo utilizzato nell'attività **Invia invito utente B2B Azure** nel flusso di lavoro per la gestione di account Azure AD, vedi [Collaborazione B2B di Azure Active Directory](/azure/active-directory/external-identities/what-is-b2b).

## <a name="additional-resources"></a>Risorse aggiuntive

[Collaborazione fornitore con i fornitori esterni](vendor-collaboration-work-external-vendors.md)

Guarda un breve video sul processo di onboarding del fornitore: [Onboarding di un nuovo fornitore](https://www.youtube.com/watch?v=0KUc3AGaTKk&feature=youtu.be)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
