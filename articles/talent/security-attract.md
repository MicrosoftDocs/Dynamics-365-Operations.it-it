---
title: Gestione della sicurezza e dei ruoli in Attract
description: In questo argomento vengono fornite informazioni sulla sicurezza dei ruoli in Microsoft Dynamics 365 for Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 9c0f9d3304b1b15aa84fd1a296267d606bf9c59d
ms.sourcegitcommit: 1653d1e28d02f8a9a4bea8df562ac98d7a350ed1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2019
ms.locfileid: "993693"
---
# <a name="security-and-role-management-in-attract"></a>Sicurezza e gestione dei ruoli in Attract

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Talent: Attract utilizza la sicurezza basata sui ruoli. Ovvero l'accesso non viene concesso ai singoli utenti, ma ai ruoli di sicurezza assegnati agli utenti. Un utente al quale viene assegnato un ruolo di sicurezza ha accesso all'insieme dei privilegi associato a tale ruolo.

Attract offre cinque ruoli utente base:

- Amministratore
- Responsabile assunzioni
- Selezionatore
- Responsabile del colloquio
- Sola lettura

Il ruolo di amministratore è l'unico ruolo con autorizzazione necessaria per aggiungere altri utenti e modificare le loro autorizzazioni.

- **Aggiungi** - Nella scheda **Autorizzazioni utente** dell'Interfaccia di amministrazione selezionare **Assegna ruoli**, cercare l'utente da aggiungere, quindi concedere le autorizzazioni a tale utente.
- **Modifica** - Cercare l'utente o trovare l'utente nell'elenco, qundi selezionare **Modifica** per cambiare le sue autorizzazioni.
- **Elimina** - Se si eliminano le autorizzazioni di un utente, l'utente non viene rimosso dal sistema. Tuttavia, è possibile limitare l'accesso e i privilegi dell'utente in Attract. Ad esempio, a Hilda è stato assegnato il ruolo di responsabile assunzioni e viene aggiunta a una posizione lavorativa come responsabile assunzioni. Se Hilda viene successivamente rimossa dal ruolo di responsabile assunzioni, resta un responsabile assunzioni nella posizione lavorativa e ha ancora accesso ad essa. Tuttavia, non può creare altre posizioni.

Nelle seguenti sezioni viene fornita una descrizione di alto livello di ciascun ruolo. Nelle tabelle più avanti nell'argomento sono riportate informazioni più dettagliate.

> [!NOTE]
> Alcune funzionalità sono disponibili solo con il componente aggiuntivo per l'assunzione a livello globale di Attract.

## <a name="administrator"></a>Amministratore

Gli utenti con il ruolo di amministratore possono accedere a tutti i dati in Attract e cambiarli. Gli amministratori possono creare, leggere, aggiornare ed eliminare dati. Possono anche accedere all'Interfaccia di amministrazione, dove possono configurare l'applicazione Attract e impostare le informazioni utente. Si consiglia di assegnare il ruolo di amministratore ad almeno un utente. Per impostazione predefinita, l'amministratore di ambiente in Microsoft PowerApps è impostato come amministratore in Attract. Se l'utente effettua la registrazione alla versione di valutazione di Attract, il ruolo di amministratore gli viene assegnato automaticamente. Attualmente, per creare posizioni lavorative, gli utenti con il ruolo di amministratore devono inoltre disporre del ruolo di selezionatore o del ruolo di responsabile assunzioni.

## <a name="hiring-manager"></a>Responsabile assunzioni

Gli utenti con il ruolo di responsabile assunzioni possono creare posizioni lavorative e aggiornare quelle create in precedenza. I responsabili assunzioni possono eseguire solo un gruppo limitato di azioni su una posizione lavorativa e sulle domande di lavoro associate a tale posizione. Solo gli utenti con il ruolo di responsabile assunzioni possono essere aggiunti a un team di assunzione come responsabili assunzioni.

## <a name="recruiter-role"></a>Ruolo di selezionatore

Gli utenti con il ruolo di selezionatore hanno pieni privilegi per leggere, creare, aggiornare ed eliminare le posizioni lavorative create. Hanno inoltre pieni privilegi per leggere, creare, aggiornare ed eliminare le domande di lavoro associate alle loro posizioni lavorative. Solo gli utenti con il ruolo di selezionatore possono essere aggiunti a un team di assunzione come selezionatori.

## <a name="interviewer"></a>Responsabile del colloquio

Qualsiasi utente che dispone di un account di Microsoft Azure Active Directory (Azure AD) nell'organizzazione può essere aggiunto a un team di assunzione come responsabile del colloquio. Gli utenti con il ruolo di responsabile del colloquio possono visualizzare i dettagli delle posizioni lavorative e i dati dei candidati per le posizioni per le quali fanno parte del team di assunzione. Per tali posizioni lavorative, i responsabili dei colloqui possono inoltre consigliare assunzioni e fornire un riscontro sui candidati. Tuttavia, non possono aggiornare i dettagli della posizione lavorativa né i dati del candidato.

## <a name="read-only"></a>Sola lettura

Gli utenti con il ruolo di sola lettura hanno accesso in sola lettura a tutti i dati dell'ambiente Attract. Tuttavia, non possono creare né modificare i dati.

## <a name="find-out-which-roles-you-have"></a>Scoprire i ruoli di cui si dispone

1.  In Attract, fare clic sul punto interrogativo (**?**) nell'angolo in alto a destra della pagina.

2.  Scegliere **Informazioni su**.

    Vengono visualizzati i ruoli di cui si dispone per Attract nella finestra visualizzata:

    ![Visualizzare il tipo di licenza di Attract](media/attract-license-types.png)
    
## <a name="delegated-roles"></a>Ruoli delegati

Per ciascuna posizione lavorativa per la quale fanno parte del team di assunzione, i selezionatori e responsabili assunzioni possono designare uno o più delegati al proprio posto. Tuttavia, non possono designare i delegati per altre persone del team di assunzione.

I delegati hanno gli stessi privilegi della persona che li ha designati. Ad esempio, se un responsabile assunzioni designa un delegato al suo posto per una posizione lavorativa, il delegato avrà gli stessi privilegi del responsabile assunzioni per tale posizione. I delegati non possono rimuovere altri delegati dal team di assunzione. Non possono nemmeno rimuovere le persone che le hanno designate come delegati.

## <a name="job-details-and-actions"></a>Dettagli e operazioni relative alle posizioni lavorative

Gli utenti con il ruolo di selezionatore o il ruolo di responsabile assunzioni possono creare posizioni lavorative. I seguenti privilegi sono applicabili ai dettagli delle posizioni lavorative e alle azioni che possono essere intraprese su tali posizioni.

| Dati o azione    | Selezionatore | Responsabile assunzioni | Responsabile del colloquio |
|-------------------|-----------|----------------|-------------|
| Dettagli mansione       | Creare, leggere, aggiornare ed eliminare per le posizioni lavorative per le quali l'utente fa parte del team di assunzione | Creare, leggere, aggiornare ed eliminare per le posizioni lavorative per le quali l'utente fa parte del team di assunzione | Sola lettura |
| Team di assunzione       | Creare, leggere, aggiornare ed eliminare per le posizioni lavorative per le quali l'utente fa parte del team di assunzione | Creare, leggere, aggiornare ed eliminare per le posizioni lavorative per le quali l'utente fa parte del team di assunzione | Sola lettura |
| Annunci di lavoro       | Creare, leggere, aggiornare ed eliminare per le posizioni lavorative per le quali l'utente fa parte del team di assunzione | Sola lettura | Sola lettura |
| Processo           | Creare, leggere, aggiornare ed eliminare per le posizioni lavorative per le quali l'utente fa parte del team di assunzione | Creare, leggere, aggiornare ed eliminare per le posizioni lavorative per le quali l'utente fa parte del team di assunzione | Sola lettura |
| Aggiungere candidati    | Aggiungere candidati per le posizioni lavorative per le quali l'utente fa parte del team di assunzione | Aggiungere candidati per le posizioni lavorative per le quali l'utente fa parte del team di assunzione | Non consentito |
| Aggiungere prospect     | Aggiungere prospect per le posizioni lavorative per le quali l'utente fa parte del team di assunzione | Un'opzione di configurazione nella [configurazione dell'attività dei prospect](./activities-attract.md#prospect-activity) controlla se i responsabili dei colloqui possono aggiungere e visualizzare i prospect. | Non consentito |
| Attivare posizioni lavorative      | Attivare posizioni lavorative per le quali l'utente fa parte del team di assunzione | Attivare posizioni lavorative per le quali l'utente fa parte del team di assunzione | Non consentito |
| Chiudi mansione         | Chiudere posizioni lavorative per le quali l'utente fa parte del team di assunzione | Non consentito | Non consentito |
| Elimina mansione        | Eliminare posizioni lavorative per le quali l'utente fa parte del team di assunzione | Solo se nessun candidato è stato aggiunto alla posizione | Non consentito |
| Elimina candidati | Eliminare candidati se l'utente fa parte del team di assunzione | Non consentito | Non consentito |

## <a name="application-details-and-actions"></a>Dettagli e azioni relative alle domande di lavoro

I seguenti privilegi sono applicabili ai dati specifici delle posizioni lavorative dei candidati e alle azioni che possono essere intraprese in merito alle domande di lavoro.

| Dati o azione          | Selezionatore | Responsabile assunzioni | Responsabile del colloquio |
|-------------------------|-----------|----------------|-------------|
| Documenti relativi alle domande di lavoro   | Creare, leggere, aggiornare ed eliminare per le posizioni lavorative per le quali l'utente fa parte del team di assunzione | Creare, leggere, aggiornare ed eliminare per le posizioni lavorative per le quali l'utente fa parte del team di assunzione | Sola lettura |
| Note sulle domande di lavoro       | Creare, leggere, aggiornare ed eliminare per le posizioni lavorative per le quali l'utente fa parte del team di assunzione | Creare, leggere, aggiornare ed eliminare per le posizioni lavorative per le quali l'utente fa parte del team di assunzione | Sola lettura|
| Attività per domande di lavoro    | Visualizzare, se l'utente fa parte del team di assunzione | Visualizzare, se l'utente fa parte del team di assunzione | Sola lettura |
| Riscontro sulle domande di lavoro    | Aggiungere e visualizzare tutto il riscontro se l'utente fa parte del team di assunzione | Aggiungere e visualizzare tutto il riscontro se l'utente fa parte del team di assunzione | Puo aggiungere il riscontro\*\* |
| Rifiutare la domanda di lavoro      | Può rifiutare se l'utente fa parte del team di assunzione | Non consentito | Non consentito |
| Avanza fase           | Può rifiutare se l'utente fa parte del team di assunzione | Può proseguire se l'utente fa parte del team di assunzione | Non consentito |
| Avviare la gestione di offerte | Può avviare la gestione di offerte | È disponibile un'opzione di configurazione sull'attività di offerta. | Non consentito |


\*\* Un'opzione di configurazione nella [configurazione dell'attività di riscontro](./activities-attract.md) controlla se i responsabili dei colloqui possono visualizzare il riscontro l'uno dall'altro.


## <a name="process-templates"></a>Modelli di processo

I seguenti privilegi si applicano ai modelli del processo di assunzione. La capacità dei membri del team di creare e modificare modelli è configurata in **Gestione modello** nell'Interfaccia di amministrazione. Se la gestione del modello è abilitata, i selezionatori e i responsabili assunzioni possono creare e modificare i propri modelli di processo. Se la gestione del modello è disattivata, solo gli amministratori possono creare e modificare i modelli di processo. Nella tabella riportata di seguito si presuppone che la gestione del modello è stata attivata.

| Dati              | Selezionatore                                           | Responsabile assunzioni                                      | Responsabile del colloquio |
|-------------------|-----------------------------------------------------|-----------------------------------------------------|-------------|
| Modelli di processo | Privilegi pieni per i modelli creati dall'utente | Privilegi pieni per i modelli creati dall'utente | Nessun accesso   |

## <a name="email-and-email-templates"></a>Posta elettronica e modelli di messaggi di posta elettronica

I seguenti privilegi sono applicabili ai modelli di messaggi di posta elettronica e alle azioni che possono essere intraprese su tali messaggi. Solo gli amministratori possono creare e modificare i modelli di messaggi di posta elettronica.

| Dati o azione     | Selezionatore          | Responsabile assunzioni     | Responsabile del colloquio |
|--------------------|--------------------|--------------------|-------------|
| Modelli di messaggio di posta elettronica    | Accesso in sola lettura   | Accesso in sola lettura   | Nessun accesso   |
| Invia posta elettronica         | Inviare per attività  | Inviare per attività  | Nessun accesso   |
| Modificare il contenuto del messaggio di posta elettronica | Modificare il contenuto del messaggio di posta elettronica | Modificare il contenuto del messaggio di posta elettronica | Nessun accesso   |

## <a name="talent-pools"></a>Pool di talenti

I seguenti privilegi sono applicabili al pool di competenze. I pool di competenze sono visibili solo alla persona che li ha creati, a meno che la persona non scelga di condividerli. La ricerca del candidato può essere utilizzata per cercare i candidati che non sono stati aggiunti a un pool denominato.

| Dati o azione   | Selezionatore                                       | Responsabile assunzioni                                  | Responsabile del colloquio |
|------------------|-------------------------------------------------|-------------------------------------------------|-------------|
| Pool denominato       | Privilegi pieni per i pool creati dall'utente | Privilegi pieni per i pool creati dall'utente | Nessun accesso   |
| Condividere pool       | Solo i pool creati dall'utente                | Solo i pool creati dall'utente                | Nessun accesso   |
| Ricerca del candidato | Funzionalità di ricerca complete                        | Funzionalità di ricerca complete                        | Nessun accesso   |

## <a name="candidates"></a>Candidati

I candidati rappresentano le persone principali aggiunte a un pool di competenze, ma non associate a una posizione lavorativa.

| Dati                        | Selezionatore                        | Responsabile assunzioni                   | Responsabile del colloquio |
|-----------------------------|----------------------------------|----------------------------------|-------------|
| Profilo: dettagli candidato | Creare, leggere, aggiornare ed eliminare | Creare, leggere, aggiornare ed eliminare | Nessun accesso   |
| Documenti                   | Creare, leggere, aggiornare ed eliminare | Creare, leggere, aggiornare ed eliminare | Nessun accesso   |
