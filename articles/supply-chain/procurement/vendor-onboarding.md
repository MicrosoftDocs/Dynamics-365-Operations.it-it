---
title: Inserimento di fornitori
description: In questa sezione viene descritto il processo per l'integrazione di nuovi fornitori. Descrive le azioni necessarie per diversi ruoli durante il processo.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests,SysUserRequestListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: b1290617cc691f88f517a4f3cae5c20668173b0d
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250153"
---
# <a name="onboard-vendors"></a>Inserimento di fornitori
[!include [banner](../includes/banner.md)]

---

I nuovi fornitori possono essere inseriti e registrati come fornitori in Microsoft Dynamics 365 Supply Chain Management, in base alle informazioni raccolte da una persona che rappresenta il fornitore.

Il processo è costituito dai seguenti passaggi, in cui vari ruoli eseguono le azioni nel sistema.

1. **Gestione dati OData** - Importazione di entità - La domanda iniziale è la richiesta di registrazione del fornitore potenziale. In genere, questa richiesta proviene da un'origine come un sito Web ospitato dal cliente che consente l'accesso anonimo. I fornitori possono registrarsi tramite l'immissione delle informazioni di base, ad esempio il nome del fornitore, la motivazione aziendale, il numero di organizzazione e il nome e l'indirizzo di posta elettronica del contatto. Le richieste vengono importate tramite l'interfaccia per la gestione dei dati.
2. **Pagina elenco di richiesta registrazione del fornitore potenziale** - In base alle informazioni che vengono fornite nella richiesta di registrazione del fornitore potenziale, un professionista di approvvigionamento determina se il fornitore deve essere integrato o meno. Il responsabile di approvvigionamento visualizzare la richiesta in arrivo nella pagina elenco **Richieste di registrazione di fornitori potenziali**.
3. **Flusso di lavoro di approvvigionamento dell'utente** - Quando un professionista di approvvigionamento ha verificato le informazioni nella richiesta ricevuta e ha deciso di proseguire il processo di integrazione fornitori, il flusso di lavoro di richiesta dell'utente effettua il provisioning del nuovo utente e invia un'email di invito per accettare la persona di contatto come utente autenticato di Microsoft Dynamics 365.
4. **Procedura guidata di registrazione fornitore** - La persona di contatto del fornitore accede utilizzando il nuovo account utente. Deve completare una procedura guidata di registrazione del fornitore per fornire informazioni quali indirizzi, informazioni commerciali, categorie di approvvigionamento e risposte al questionario.
5. **Flusso di lavoro di approvazione** - Viene creata una richiesta fornitore che include le informazioni di registrazione. La richiesta del fornitore viene inviata a un flusso di lavoro e viene inoltrata per la revisione e l'approvazione.
6. **Creazione di un master del fornitore e modifica del ruolo utente** - Quando viene approvata la richiesta del fornitore, viene creato un record del fornitore. L'account utente della persona di contatto del fornitore viene autorizzato alla collaborare fornitore o disattivato.

Nella seguente tabella sono riportati i passaggi e ruoli inclusi nel processo.

| Ruolo e processo       | Gestione dati OData - Importazione di entità | Pagina elenco richieste di registrazione fornitore potenziale | Flusso di lavoro provisioning utente | Registrazione guidata fornitore | Flusso di lavoro di approvazione | Creazione di un master fornitore e modifica del ruolo dell'utente |
|--------------------------|---|---|---|---|---|---|
| System                   | La richiesta per un nuovo fornitore viene importata. | | | | | Dopo che la richiesta fornitore viene accettata, viene creato il record del fornitore. |
| Professionista di approvvigionamento | | Avviare il processo di integrazione. | | | Verificare e accettare o rifiutare la richiesta fornitore. | |
| Amministratore            | | | Creare un utente in Supply Chain Management e Microsoft Azure. | | | |
| Contatto del fornitore    | | | Inviare un messaggio di posta elettronica al contatto. | Registrare le informazioni sul fornitore. | | |

Per una dimostrazione rapida del processo di inserimento del fornitore, vedere questo breve video su YouTube: [Come aggiungere un nuovo fornitore in Finance and Operations](https://www.youtube.com/watch?v=0KUc3AGaTKk).

## <a name="importing-the-prospective-vendor-registration-request"></a>Importare la richiesta di registrazione di fornitori potenziali

La richiesta di registrazione del fornitore potenziale è un'entità di Supply Chain Management. È possibile impostare il sistema per importare i dati tramite questa entità. 

Nella seguente tabella sono riportate le informazioni che contiene questa entità e che possono essere importate.

| Campo                        | descrizione |
|------------------------------|-------------|
| Nome fornitore                  | Nome del fornitore. |
| Motivazione aziendale       | Motivazione o motivazioni per la richiesta. |
| Numero organizzazione          | Numero di registrazione ufficialmente noto. |
| Linea di business             | Linea di business in cui opera il fornitore. |
| Nome del contatto  | Nome della persona che verrà invitata a registrare le informazioni sul fornitore. |
| Secondo nome del contatto | Secondo nome della persona che verrà invitata a registrare le informazioni sul fornitore. |
| Cognome del contatto.   | Cognome della persona che verrà invitata a registrare le informazioni sul fornitore. |
| Indirizzo di posta elettronica del contatto       | Indirizzo di posta elettronica che verrà utilizzato per creare un nuovo utente in Supply Chain Management e che verrà registrato nel tenant dell'account Azure Active Directory (Azure AD). |
| Data di invio               | Data in cui la richiesta è stata creata in un sistema esterno. |
| Persona giuridica                 | Persona giuridica con cui il fornitore sta richiedendo di diventare un fornitore. Il valore deve essere un codice della persona giuridica registrato in Supply Chain Management. Se non viene ricevuto alcun valore attraverso il processo di importazione, vengono applicati i parametri di Approvvigionamento. |
| Tipo di fornitore                  | Una fornitore può essere un'organizzazioni o una persona. Il tipo di fornitore determina come fornitore viene creato. |

Dopo aver importato la richiesta di registrazione del fornitore potenziale, questa appare nella pagina elenco **Richiesta di registrazione fornitore potenziale**. In questa pagina elenco, un professionista di approvvigionamento può invitare l'utente. Una richiesta utente per il provisioning dell'utente viene inviata a un flusso di lavoro.

## <a name="submitting-a-prospective-vendor-user-request"></a>Inoltro di una richiesta utente fornitore potenziale

Lo scopo di una richiesta utente fornitore potenziale è effettuare il provisioning della persona che ha inviato la richiesta iniziale, in modo che possa accedere a Supply Chain Management utilizzando l'account di posta elettronica fornito nella richiesta di registrazione del fornitore potenziale.

La richiesta utente fornitore potenziale viene elaborata dal flusso di lavoro di richiesta utente. Questo flusso di lavoro deve comunicare tramite la collaborazione B2B di Azure AD. Crea un utente in Supply Chain Management con le impostazioni di protezione appropriate.

I nuovi utenti vengono impostati con i seguenti ruoli di sicurezza:

- Utente esterno di sistema
- Fornitore potenziale (esterno)

Il nuovo utente riceverà un messaggio di posta elettronica generato dal flusso di lavoro di richiesta utente. Questo messaggio invita l'utente ad accedere al sistema.

Per informazioni sulla configurazione dell'e-mail e del flusso di lavoro in generale, vedere la descrizione di un flusso di lavoro di richiesta utente in [Impostare e gestire la collaborazione fornitore](set-up-maintain-vendor-collaboration.md).

## <a name="vendor-registration"></a>Registrazione fornitore

Un utente fornitore potenziale che accede a Supply Chain Management visualizzerà la prima pagina di una procedura guidata di registrazione fornitore, in si possono immettere le informazioni sul fornitore.

La procedura guidata riflette la configurazione della richiesta fornitore. Il paese o la regione in cui il fornitore opera determina le informazioni necessarie per la procedura guidata e le informazioni obbligatorie.

Per ulteriori informazioni sulla configurazione della richiesta fornitore, vedere [Impostare e gestire la collaborazione fornitore](set-up-maintain-vendor-collaboration.md). Nella seguente tabella viene fornita una panoramica delle finestre della procedura guidata e lo scopo di ogni pagina.

| Pagina                       | descrizione |
|----------------------------|-------------|
| Paese             | Il paese determina la configurazione delle richieste fornitore applicata alle pagine rimanenti della procedura guidata. Vengono inoltre determinati i valori della ricerca **Stato imposta**. |
| Termini e condizioni       | Questa pagina potrebbe essere disponibile, a seconda della configurazione della richiesta fornitore. Se è disponibile, l'utente deve accettare i termini e le condizioni per continuare. |
| Informazioni fornitore         | In questa pagina viene riportato il nome del fornitore, immesso automaticamente dalla richiesta originale di registrazione del fornitore potenziale. È incluso inoltre il numero di organizzazione, il numero di telefono del fornitore, il numero di fax e l'indirizzo di posta elettronica e gli indirizzi del fornitore per diversi scopi. |
| Informazioni contatto | In questa pagina viene riportato il nome del contatto, immesso automaticamente dalla richiesta originale di registrazione del fornitore potenziale. È incluso inoltre il numero di telefono e l'indirizzo di posta elettronica del contatto e gli indirizzi del contatto per diversi scopi. |
| Informazioni aziendali       | In questa pagina vengono inclusi i numeri di partita IVA (per vari paesi) e i numeri di dipendenti. Viene inoltre indicato se l'azienda è di proprietà di minoranza. |
| Categorie di approvvigionamento     | Questa pagina contiene le categorie di approvvigionamento per le quali il fornitore richiede l'approvazione. L'utente può selezionare le categorie nella gerarchia delle categorie di approvvigionamento. È possibile configurare il numero di livelli visualizzati nella gerarchia in &gt; **Parametri di approvvigionamento** **Collaborazione fornitore**, in **Approvvigionamento** &gt; **Impostazione** |
| Questionari             | La procedura guidata può includere un insieme di questionari per il fornitore. I questionari che vengono visualizzati nella procedura guidata vengono configurati nella richiesta fornitore o per categoria di approvvigionamento. Se i questionari sono configurati per categoria di approvvigionamento, le categorie di approvvigionamento per cui il fornitore richiede l'approvazione determinano i questionari che sono visualizzati nella procedura guidata. Nella pagina **Categorie di approvvigionamento**, è possibile aggiungere un questionario nella categoria rilevante e impostare il tipo di attività come **Integrazione fornitori**. |

Quando l'utente fornitore potenziale completa la procedura guidata di registrazione fornitore, una richiesta fornitore viene creata.

## <a name="manually-or-automatically-submit-a-vendor-request"></a>Inviare manualmente o automaticamente una richiesta fornitore

Una richiesta fornitore può essere creata come bozza e inviata manualmente a un flusso di lavoro. In alternativa, la richiesta fornitore può essere inviata automaticamente a un flusso di lavoro quando la procedura guidata di registrazione fornitore è completata. Una richiesta può essere inviata manualmente se, ad esempio, un professionista di approvvigionamento desidera valutare se la richiesta deve essere inviata tramite un processo di approvazione prima che venga inviata al flusso di lavoro.

- Selezionare **Parametri di approvvigionamento** &gt; **Collaborazione fornitore** e quindi selezionare **Invia automaticamente la registrazione del fornitore potenziale al flusso di lavoro** per configurare la richiesta fornitore in modo che venga inviata automaticamente a un flusso di lavoro quando la procedura guidata di registrazione fornitore è completata.

## <a name="vendor-requests"></a>Richieste fornitore

Le richieste fornitore sono disponibili nella pagina **Richieste utente collaborazione fornitore**.

Una richiesta fornitore contiene le informazioni per cui l'utente fornitore potenziale ha fornito nella procedura guidata di registrazione fornitore.

La richiesta consente di esaminare le informazioni sul fornitore e decidere se il fornitore deve diventare fornitore registrato.

La richiesta fornitore deve essere inviata a un flusso di lavoro e deve essere inviata ai revisori e agli approvatori rilevanti. Per informazioni di base su come impostare i flussi di lavoro, vedere [Flussi di lavoro di approvvigionamento](procurement-sourcing-workflows.md).

La seguente tabella mostra gli stati che possono avere le richieste del fornitore.

| Stato                     | descrizione |
|----------------------------|-------------|
| Bozze                      | La richiesta fornitore non è stata ancora inviata. |
| Rich. inviata          | La richiesta fornitore è stata inviata e la prima fase del flusso di lavoro è di elaborazione. |
| Revisione in sospeso             | Se sono presenti più revisori in un'attività del flusso di lavoro, un revisore può accettare l'attività di revisione della richiesta fornitore e quindi completare la revisione. Se è presente solo un revisore, il partecipante può completare la revisione selezionando **Completato** nell'azione del flusso di lavoro. Non è necessario che la persona accetti prima l'elemento di lavoro. |
| Richiesta in attesa dell'approvazione   | La richiesta fornitore è stata inoltrata ai partecipanti per l'approvazione ed è disponibile un'opzione per richiedere informazioni aggiuntive. Una richiesta di informazioni aggiuntive fa sì che l'oggetto di lavoro sia inviato di nuovo al mittente. La richiesta fornitore può anche essere approvata o rifiutata quando si trova in questo stato. |
| Richiesta di modifica della domanda | Ulteriori informazioni sono state richieste dall'approvatore e la richiesta fornitore è stata inoltrata alla persona che ha inviato la richiesta fornitore. Il mittente può aggiungere le informazioni richieste e quindi inviare di nuovo la richiesta del fornitore. Se una richiesta fornitore viene inviata nuovamente, lo stato verrà modificato di nuovo in **Richiesta in attesa dell'approvazione**. |
| Richiesta approvata           | Questo stato è uno stato finale. |
| Rich. rifiutata           | Questo stato è uno stato finale. |

## <a name="approving-a-vendor-request"></a>Approvare una richiesta fornitore

Quando una richiesta fornitore viene approvata, viene creato un account fornitore e lo stato **Approvato** viene visualizzato sulla richiesta di registrazione iniziale del fornitore potenziale e sulla richiesta fornitore.

Prima di approvare una richiesta fornitore, nella pagina **Nuovo fornitore** nella scheda dettaglio **Generale** selezionare **Gruppo di fornitori** per selezionare un gruppo di fornitori.

Se l'utente del fornitore potenziale può accedere a Supply Chain Management come utente di collaborazione fornitore che rappresenta il fornitore, impostare l'autorizzazione di accesso di collaborazione su **Sì**. Per disattivare l'account utente che il fornitore potenziale ha usato per la registrazione, impostare questa autorizzazione su **No**.

Se l'autorizzazione di accesso di collaborazione fornitore è impostata su **Sì**, quando la richiesta fornitore viene approvata, viene inviata una richiesta di modifica dei ruoli utente in modo che l'utente disponga di ruoli definiti per il tipo **Fornitore** in **Ruoli esterni**. Se l'autorizzazione è impostata su **No**, quando la richiesta fornitore viene approvata, viene inviata una richiesta di disattivazione dell'utente. In questo caso, il flusso di lavoro per disattivare una richiesta utente deve essere configurato.

Affinché un account fornitore possa essere creato quando viene approvata la richiesta fornitore, la sequenza numerica per la creazione di fornitori dalle richieste fornitore deve essere impostata su **Automatica**.

Per una panoramica delle autorizzazioni di accesso di un utente di collaborazione fornitore, vedere [Impostare e gestire la collaborazione fornitore](set-up-maintain-vendor-collaboration.md).

## <a name="rejecting-a-vendor-request"></a>Rifiutare una richiesta fornitore

Se una richiesta fornitore viene rifiutata, è necessario selezionare una motivazione nella richiesta fornitore.

Quando una richiesta fornitore viene rifiutata, viene inviata una richiesta per disattivare l'utente. In questo caso, il flusso di lavoro per disattivare una richiesta utente deve essere configurato. Per ulteriori informazioni, vedere [Impostare e gestire la collaborazione fornitore](set-up-maintain-vendor-collaboration.md).

Quando una richiesta fornitore viene rifiutata, lo stato **Rifiutato** viene visualizzato sulla richiesta di registrazione iniziale del fornitore potenziale e sulla richiesta fornitore.

## <a name="deleting-a-prospective-vendor-registration-request-in-various-statuses"></a>Eliminare una richiesta di registrazione del fornitore potenziale nei diversi stati

Lo stato di una richiesta di registrazione del fornitore potenziale offre una panoramica dello stato di avanzamento della richiesta.

Se si utilizza l'azione **Elimina** nella richiesta di registrazione del fornitore potenziale, è possibile eliminare e rimuovere la catena di record che è stata creata ed è possibile disattivare l'account utente. Il risultato dell'azione **Elimina** varia a seconda dello stato della richiesta di registrazione del fornitore potenziale, come illustrato nella seguente tabella.


|          Stato          |                                                                                     Descrizione stato                                                                                      |                                                                                                                                                            Risultato dell'azione di eliminazione                                                                                                                                                             |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|           Nuovo            |                                                                         Nessuna azione è stata applicata alla richiesta.                                                                          |                                                                                                                                              La richiesta di registrazione di fornitori potenziali viene eliminata.                                                                                                                                               |
|      Utente richiesto      | Quando si seleziona <strong>Invita utente</strong>, lo stato viene modificato in <strong>Utente richiesto</strong> e una richiesta utente potenziale viene creata e inviata a un flusso di lavoro di richiesta utente. |                                                                                                          Non è possibile eliminare una richiesta di registrazione fornitore potenziale con questo stato, in quanto il flusso di lavoro di richiesta utente non è stato completato.                                                                                                          |
|       Utente invitato       |                                                               Il flusso di lavoro di richiesta utente viene approvato e l'utente viene creato.                                                               |                                                                                                                      Viene creata una richiesta di disattivazione dell'utente e la richiesta di registrazione del fornitore potenziale viene eliminata.                                                                                                                      |
| Registrazione in corso |                                                         Il nuovo utente ha effettuato l'accesso e ha avviato la procedura guidata di registrazione fornitore.                                                          |                                                                                     Viene creata una richiesta di disattivazione dell'utente e la richiesta di registrazione del fornitore potenziale e i dati inseriti nella procedura guidata di registrazione del fornitore vengono eliminati.                                                                                      |
|  Richiesta fornitore creata  |                                                                     La procedura guidata di registrazione fornitore è stata completata.                                                                      | Viene creata una richiesta di disattivazione dell'utente e la richiesta di registrazione del fornitore potenziale, i dati inseriti nella procedura guidata di registrazione del fornitore e la richiesta del fornitore vengono eliminati.<blockquote>[!NOTE]<br>Non è possibile utilizzare l'azione <strong>Elimina</strong> quando la richiesta fornitore si trova in un processo di revisione del flusso di lavoro.</blockquote> |
|         Approvate         |                                                                               La richiesta del fornitore viene approvata.                                                                               |                                                                                                   La richiesta di registrazione del fornitore potenziale, i dati inseriti nella procedura guidata di registrazione del fornitore e la richiesta fornitore vengono eliminati.                                                                                                    |
|         Rifiutato         |                                                                               La richiesta del fornitore viene rifiutata.                                                                               |                                                                                                   La richiesta di registrazione del fornitore potenziale, i dati inseriti nella procedura guidata di registrazione del fornitore e la richiesta fornitore vengono eliminati.                                                                                                    |

