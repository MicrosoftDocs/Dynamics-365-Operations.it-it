---
title: Creazione, approvazione e pubblicazione di annunci di mansioni in Attract
description: In questo argomento sono descritti gli elementi di una mansione in Attract. Viene illustrato anche come creare una mansione.
author: josaw
manager: AnnBe
ms.date: 12/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: 
ms.author: josaw
ms.search.validFrom: 2018-10-24
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 95031534c43dc0578e258bc3e5376c429d72b0ab
ms.openlocfilehash: 6c5daa4050d63303f1ac10c24901e5b1182cb62b
ms.contentlocale: it-it
ms.lasthandoff: 12/23/2018

---

# <a name="create-approve-and-post-jobs-in-attract"></a>Creazione, approvazione e pubblicazione di annunci di mansioni in Attract

[!include [banner](includes/banner.md)]

In questo argomento sono descritti gli elementi di una mansione in Microsoft Dynamics 365 for Talent: Attract. Viene illustrato anche come creare una mansione.

## <a name="job-creation"></a>Creazione mansione

Gli amministratori, i selezionatori e i responsabili delle assunzioni possono mansioni. Quando si crea una mansione, verrà chiesto di selezionare il ruolo nel processo: responsabile assunzioni o selezionatore. Dopo avere selezionato un ruolo, verrà chiesto di selezionare un modello di processo. Se si seleziona **Ignora**, il modello predefinito viene utilizzato. Per ulteriori informazioni sui modelli di processo, vedere [Creare un modello di processo in Attract](./process-templates-attract.md).

Una mansione in Attract include i dettagli della mansione, un team di assunzione, un processo di assunzione, gli annunci della mansione e l'analisi.

## <a name="job-details"></a>Dettagli mansione

La scheda **Dettagli mansione** include i dettagli relativi alle responsabilità e agli attributi della mansione. I campi del titolo, la descrizione e l'ubicazione della mansione sono obbligatori. Gli altri campi sono facoltativi.

Per impostazione predefinita, il campo **Numero di opportunità di lavoro** è impostato su **1**. È tuttavia possibile modificare tale valore. Se un'offerta è stata preparata per una mansione, il valore del campo **Numero di opportunità di lavoro disponibili** viene ridotto.

Se la gestione della posizione è stata abilitata nell'Interfaccia di amministrazione, la ricerca **Aggiorna posizioni** è disponibile. La ricerca legge l'entità JobPosition nel Common Data Service per le app e restituisce un elenco di posizioni che possono essere selezionate per la mansione. Se il numero di posizioni selezionato supera il numero di posizioni aperte, viene visualizzato un avviso. Si riceve un avviso anche se una posizione viene utilizzata per più mansioni.

> [!NOTE]
> La gestione delle posizioni è disponibile con il componente aggiuntivo per l'assunzione a livello globale.

A seconda delle impostazioni nell'attività di offerta del processo di assunzione, un numero di posizione può essere utilizzato due volte in un'offerta. Per ulteriori informazioni, vedere [Processo di assunzione](./activities-attract.md).

Attract include un set predefinito di **Competenze**. Queste competenze verranno visualizzate come suggerimenti mentre si digita. È possibile aggiungere più competenze digitando un nuovo testo relativo alle competenze nel campo e quindi premendo INVIO.

Attract include un set predefinito di **Funzioni di lavoro**. È possibile aggiungere fino a tre nuove funzioni di lavoro immettendo la nuova funzione lavorativa nel campo e quindi premendo INVIO.

Attract include un set predefinito di **Settore società**. È possibile aggiungere fino a tre nuovi settori società immettendo il nuovo settore società nel campo e quindi premendo INVIO.

## <a name="hiring-team"></a>Team di assunzione

La scheda **Team di assunzione** include l'elenco di utenti che verranno coinvolti nella mansione. Quando gli utenti vengono aggiunti a un team di assunzione, devono avere un ruolo nel team di assunzione. Il ruolo determina i dati che gli utenti possano accedere a e le notifiche che ricevono. I ruoli che possono essere selezionati sono **Selezionatore**, **Responsabile assunzioni**, **Delegato** e **Responsabile del colloquio**. Per ulteriori informazioni sui privilegi dei ruoli, vedere la documentazione "Gestione ruoli". I selezionatori e responsabili assunzioni possono nominare uno o più delegati per lavorare per loro conto. Per ulteriori informazioni sui delegati, vedere [Gestione della sicurezza e dei ruoli in Attract](./security-attract.md).

Il team di assunzione può essere aggiornato dopo che la mansione viene attivata.

## <a name="process"></a>Processo

Le informazioni predefinite relative al processo di assunzione si basano sul modello di processo selezionato durante la creazione della mansione. Se un modello specifico non è stato selezionato a questo punto, il modello predefinito viene utilizzato. Quando si definisce il processo di assunzione, è possibile aggiungere o rimuovere varie fasi, tranne Candidato, Domanda di lavoro e Offerta. Sebbene la fase Candidato non può essere rimossa, può essere disattivata. All'interno di ciascuna fase, è possibile aggiungere o rimuovere una o più attività predefinite.

Per ulteriori informazioni sulle attività che possono essere aggiunti al processo di assunzione, vedere [Attività del processo di assunzione in Attract](./activities-attract.md).

> [!NOTE]
> Il processo di assunzione non può essere aggiornato dopo che la mansione viene attivata.

## <a name="postings"></a>Registrazioni

Dopo che una mansione viene attivata, può essere pubblicata. Solo i selezionatori e gli amministratori possono pubblicare annunci di mansioni. La mansione può essere pubblicata in Talent - Avanzamento professionale (un sito di avanzamento professionale di Microsoft Dynamics 365 for Talent) o su LinkedIn. 

> [!NOTE]
> È necessario considerare tre cose importanti in relazione al processo di pubblicazione di annunci di mansioni in LinkedIn.
> 1. Le mansioni pubblicate in LinkedIn lo sono come mansioni di "Elenchi restrizioni". Le mansioni di elenchi restrizioni non possono essere promosse nel sito di LinkedIn. Se si desidera promuovere le mansioni di elenchi restrizioni pubblicate in LinkedIn da Attract, è necessario abilitare il wrapping delle mansioni in LinkedIn. Per ulteriori informazioni, fare riferimento ai collegamenti qui sotto e contattare il Supporto tecnico LinkedIn.
>
>    [Elenchi restrizioni e slot di mansioni premium per il wrapping di mansioni](https://www.linkedin.com/help/recruiter/answer/79049/limited-listings-vs-premium-job-slots-for-job-wrapping)
>
>    [Domande frequenti sul wrapping di mansioni](https://www.linkedin.com/help/recruiter/answer/79050/job-wrapping-frequently-asked-questions)
>
> 1. Quando si pubblicano mansioni in LinkedIn, Attract passa il nome dell'organizzazione Microsoft 365 per la mansione. LinkedIn collega le mansioni a una società sul lato LinkedIn in base al nome dell'organizzazione passato. Se la mansione è elencata per una società errata in LinkedIn, verificare che il nome dell'organizzazione Microsoft 365 corrisponda al nome della società in LinkedIn.  
>
>    [Modifica di indirizzo, contatto e altre informazioni](https://docs.microsoft.com/en-us/office365/admin/manage/change-address-contact-and-more)
>
>    In caso di problemi dopo questo passaggio, contattare il Supporto tecnico LinkedIn. 
> 
> 1. A causa del processo di registrazione corrente del processo batch di LinkedIn, è possibile che siano necessarie fino a 24 ore perché le mansioni registrate in LinkedIn siano visibili ai candidati in LinkedIn.

Il team di Attract opera continuamente per collaborare con aggregatori di bacheche di annunci lavorativi. Questo elenco si espanderà nel tempo.

Per ulteriori informazioni sulla pubblicazione di annunci di mansioni, vedere [Funzionalità del sito di avanzamento professionale in Attract](./career-site.md).

> [!NOTE]
> La funzionalità di pubblicazione di annunci di mansioni è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale di Attract.

## <a name="activate"></a>Attiva

Dopo che una mansione è attivata, può essere pubblicata e i prospect e i candidati vi possono essere aggiunti. L'opzione per aggiungere prospect a una mansione viene impostata nell'attività di prospect nel processo di assunzione.

> [!NOTE]
> Il processo di assunzione non può essere aggiornato dopo che la mansione viene attivata.

## <a name="prospects-and-applicants"></a>Prospect e candidati

L'opzione per aggiungere prospect a una mansione viene impostata nell'[attività di prospect](./activities-attract.md#prospect-activity) nel processo di assunzione. Questa opzione deve essere impostata prima di attivare la mansione. Dopo che una mansione è attivata, i prospect e i candidati vi possono essere aggiunti.

## <a name="approvals"></a>Approvazioni

Le mansioni di Attracy possono essere inviate per l'approvazione. Non tutte le mansioni richiedono l'approvazione. Il requisito viene impostato a livello del modello. Per impostazione predefinita, le approvazioni sono disattivate nel modello. Per impostare le approvazioni, passare a un modello di processo e impostare il campo **Approvazione** su Predefinita. Selezionare quindi il modello quando si crea la mansione.

Dopo che una mansione viene salvata può essere inviata per l'approvazione. Nella tabella riportata di seguito sono elencati gli stati di un documento in cui vengono utilizzate le approvazioni.

| Stato   | Stato/regione                                                               |
|----------|---------------------------------------------------------------------|
| Bozze    | La mansione è stata salvata, ma non è stata inviata a un flusso di lavoro. |
| In sospeso  | La mansione è stata inviata agli approvatori.                            |
| Approvate | La mansione è stata approvata, ma non è stata attivata.            |
| Rifiutato | La mansione è stata rifiutata e non può essere attivata.               |
| Attive   | La mansione è stata approvata e attivata.                            |

Nell'elenco delle mansioni, è possibile filtrare in base agli stati delle mansioni.

Le approvazioni possono essere inviate a qualsiasi utente Microsoft Azure Active Directory (Azure AD) nella società. Le approvazioni vengono inviate in parallelo a tutte le persone elencate come approvatori. Dopo che una mansione viene approvata, può essere attivata.

Le Persone elencate come approvatori riceveranno una notifica in Attract per informarle che hanno un elemento da approvare. Un elemento di approvazione verrà visualizzato anche nella sezione **Assegnati all'utente** nel dashboard. Dopo che qualcuno accetta o approva una mansione, il team di assunzione riceverà una notifica. Infine, il team di assunzione riceverà una notifica quando la mansione viene approvata.

## <a name="create-a-job"></a>Creare una mansione

Per creare una mansione, attenersi alla procedura seguente.

1. Passare a **Mansioni**.
2. Selezionare **Nuovo**.
3. Nel campo **Posizione lavorativa**, immettere la posizione. Nel campo **Ruolo** immettere il ruolo.
4. Nel campo **Modello** selezionare un modello. In alternativa, selezionare **Ignora**. Se si seleziona **Ignora**, il modello che viene contrassegnato come modello predefinito viene utilizzato.

    Se il documento deve essere sottoposto a un processo di approvazione, selezionare un modello in cui il campo **Processo di approvazione** è impostato su **Predefinito**.

5. Nella scheda **Dettagli** specificare i dettagli della mansione. I campi **Titolo**, **Descrizione mansione** e **Sede** sono obbligatori.
6. Selezionare **Salva**.
7. Nella scheda **Team di assunzione**, aggiungere un responsabile assunzioni, un selezionatore o un responsabile del colloquio.
8. Selezionare **Salva**.
9. Nella scheda **Processo**, aggiungere o rimuovere le fasi in base alle esigenze:

    - Per aggiungere una fase, selezionare **+ Nuova fase**.
    - Per rimuovere una fase, passare il puntatore sulla fase da rimuovere, quindi fare clic sul pulsante del cestino visualizzato.

        > [!NOTE]
        > Le fasi Candidato, Domanda di lavoro e Offerta non possono essere rimosse.

10. Aggiungere o rimuovere attività in base alle esigenze:

    - Per aggiungere un'attività, trascinarla dall'elenco a destra alla fase appropriata. In alternativa, fare doppio clic sull'attività quindi selezionare la fase a cui aggiungerla.
    - Per rimuovere un'attività, espanderla, quindi fare clic sul pulsante del cestino nell'intestazione dell'attività.

11. Selezionare **Salva**.
12. Se si sceglie di utilizzare un processo di approvazione, effettuare le seguenti operazioni:

    1. Selezionare **+ Aggiungi approvatore** e immettere un utente che dispone di un account Azure AD. È possibile aggiungere più approvatori.
    2. Selezionare **Invia agli approvatori**.

    Il campo **Stato del processo** della mansione viene impostato  su **In sospeso**. Dopo che il valore del campo **Stato del processo** cambia in **Approvato**, la mansione può essere attivata.

13. Per attivare la mansione, selezionare **Attiva**.
14. Per pubblicare la mansione, passare a **Registrazioni** e selezionare **Registra ora** nel sito Talent - Avanzamento professionale o su LinkedIn.

