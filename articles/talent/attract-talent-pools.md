---
title: Selezionare i candidati utilizzando i pool di talenti in Attract
description: In questo argomento viene descritto come creare e configurare pool di talenti in Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 97385da9d258cc169a9976be7c7798faa41661c3
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527695"
---
# <a name="source-candidates-with-talent-pools-in-attract"></a>Selezionare i candidati utilizzando i pool di talenti in Attract

[!include [banner](includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

I selezionatori e responsabili delle assunzioni possono organizzare i candidati utilizzando la funzionalità Pool di talenti in Attract. I pool di talenti consentono di tenere traccia e stabilire un contatto con tutti i candidati che fanno domanda per mansioni nella società.

## <a name="create-and-share-a-talent-pool"></a>Creare e condividere un pool di talenti

Qualsiasi utente con il ruolo di selezionatore, responsabile delle assunzioni o amministratore di Attract possono creare pool di talenti. Il proprietario di un pool di talenti può inoltre condividere il pool con altri utenti in modo che gruppi di utenti, soprattutto selezionatori, possano esaminare un pool comune di candidati.

I contributori in un pool di talenti possono visualizzare l'elenco dei candidati nel pool. Possono inoltre aggiungere candidati al pool o rimuovere i candidati.

Utilizzare la procedura riportata di seguito per creare e condividere un pool di talenti.

1. Nella home page di Attract, nel riquadro di spostamento a sinistra, selezionare **Pool di talenti**.

    Scheda **Pool di talenti personali** mostra tutti i pool di talenti a cui si ha accesso, con i dettagli relativi a ciascuno. I dettagli includono il proprietario del pool e il numero dei candidati in esso.

1. Nella parte superiore destra della pagina, scegliere **Nuovo** per aprire la finestra di dialogo **Crea pool di talenti**.
1. Immettere un nome univoco per il pool di talenti.
1. Per aggiungere persone come contributori nel pool, individuare i relativi nomi utilizzando lo strumento di selezione persone e quindi aggiungerli all'elenco. È possibile condividere un pool di talenti solo con utenti con il ruolo di selezionatore, responsabile assunzioni o amministratore di Attract.
1. Selezionare **Aggiungi** per creare il pool di talenti.
     > [!NOTE]
     > In alternativa, è possibile aggiungere contributori in un pool di talenti dopo averlo creato. È inoltre possibile gestire l'accesso a un pool di talenti. Ad esempio, è possibile revocare l'accesso di un utente al pool di talenti.
     > - Per aggiungere i contributori in un pool di talenti esistente di tua proprietà, nella scheda **Pool di talenti personali**, in alto a destra della scheda del pool di talenti, selezionare il pulsante con i puntini di sospensione (**…**) e quindi **Modifica**. Individuare le persone utilizzando lo strumento di selezione persone e aggiungerle all'elenco. 
     > - Per revocare l'accesso di un utente al pool di talenti, in alto a destra della scheda del pool di talenti, selezionare il pulsante con i puntini di sospensione (**…**) e quindi **Modifica**. Nella scheda **Gestisci accesso**, selezionare il pulsante del cestino accanto all'utente.

6. Selezionare **Aggiorna** per completare e salvare l'operazione.

> [!NOTE]
> Per creare più pool di talenti, l'organizzazione deve avere il componente aggiuntivo per l'assunzione a livello globale.

## <a name="add-and-remove-candidates"></a>Aggiungere e rimuovere i candidati

Il proprietario e i contributori nel pool di talenti possono aggiungere candidati nel pool di talenti, visualizzare i candidati in esso e rimuovere i candidati.

1. Nella scheda **Pool di talenti personali**, selezionare un pool di talenti per aprirlo.

    Un elenco dei candidati che fanno parte del pool di talenti viene visualizzato.

1. Per aggiungere i candidati nel pool di talenti, selezionare **+ Nuovo** nell'in alto a destra per aprire la finestra di dialogo **Aggiungi candidato** e quindi effettuare una delle seguenti operazioni.

    - Per aggiungere un candidato interno, è possibile cercare la persona in base all'indirizzo di posta elettronica. Dopo una ricerca riuscita, l'indirizzo di posta elettronica del candidato, il nome e cognome vengono compilati. Se sono disponibili il curriculum o documenti correlati del candidato, è possibile caricarli adesso. Quindi selezionare **Aggiungi** per aggiungere il candidato nel pool di talenti.
    - Per aggiungere un candidato esterno, immettere manualmente indirizzo di posta elettronica, nome e cognome. Se sono disponibili il curriculum o documenti correlati, è possibile caricarli adesso. Quindi selezionare **Aggiungi** per aggiungere il candidato nel pool di talenti.
    - Per aggiungere più candidati, selezionare la scheda **Da Excel**. È possibile scaricare il modello appropriato di Microsoft Excel, immettere i dettagli relativi ai candidati, salvare il foglio di lavoro di Excel e caricarlo nella domanda di lavoro.

        Se vengono trovati errori nel foglio di lavoro, si riceverà i messaggi relativi. È quindi possibile correggere gli errori e provare a caricare di nuovo il foglio di lavoro. Quando più non vengono rilevati errori, selezionare **Aggiungi** per caricare il foglio di lavoro. Il foglio di lavoro viene elaborato in background e verrà inviata una notifica quando tutti i candidati sono stati aggiunti al pool di talenti.

1. Per rimuovere un candidato esistente dal pool di talenti, nella colonna **Azione**, selezionare il pulsante del cestino per il candidato.

## <a name="search-and-view-candidate-profiles"></a>Cercare e visualizzare profili di candidati

> [!NOTE] 
> Questa funzionalità è attualmente in anteprima. Se si desidera provarla, è necessario [attivarla nelle impostazioni di amministrazione di Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature). 

I pool di talenti consentono di visualizzare il profilo di un candidato, le informazioni di LinkedIn, i documenti correlati e lo storico dell'applicazione. È possibile cercare nell'intero database tutti i candidati aggiunti a qualsiasi pool di talenti, inclusi i candidati chiusi e attivi.

>[!NOTE]
> Quando si aggiungono nuovi candidati, l'indicizzazione degli stessi per la ricerca può richiedere fino a 15 minuti.

Con l'esperienza di ricerca migliorata, è possibile eseguire la ricerca in tutti i documenti dei candidati e filtrare per medaglie d'argento, origini, competenze, formazione e altro. Nelle versioni precedenti, è necessario specificare l'entità in cui si desidera effettuare la ricerca. Attract può ora effettuare la ricerca nei campi correlati ai candidati e classificare i risultati.

1. Per avviare una nuova ricerca nel database dei candidati, immettere il testo che si desidera cercare nella casella di ricerca della scheda **Pool di talenti**. 

È possibile digitare il nome del candidato o qualsiasi attributo che si intende cercare. Per separare gli attributi, immettere uno spazio.

È possibile limitare i risultati modificando la query di ricerca o utilizzando i filtri avanzati nella parte sinistra della pagina.

I risultati della ricerca includono evidenziazioni per i vari attributi corrispondenti alla query di ricerca. Selezionare qualsiasi candidato per visualizzarne il profilo.

### <a name="syntax-highlights"></a>Evidenziazioni della sintassi 

| Operatore | Uso                                                      | Esempio              |
|----------|------------------------------------------------------------|----------------------|
| \*       | Cerca sottostringhe; può essere utilizzato per restituire tutti i record | Input: Mi\* <br></br> Risultato: tutti i record contenenti campi che iniziano con "Mi" ad esempio Microsoft, microsistemi, Midtown Enterprises o Middleton <br></br>Input: \* <br></br> Risultato: tutti i record nel database |
| “”       | Cerca una corrispondenza esatta                                | Input: “Microsoft” <br></br> Risultato: tutti i record contenenti “Microsoft”                    |

>[!WARNING]
> Non disattivare la ricerca per pertinenza per l'istanza di Common Data Service. Questa operazione disabiliterà l'esperienza di ricerca in Attract.

Tutti gli utenti dispongono di una visualizzazione condivisa dei profili dei candidati. Nella scheda **Profilo** vengono visualizzate le informazioni su competenze, esperienze di lavoro e formazione che il candidato ha fornito nelle domande di lavoro utilizzando il portale di avanzamento professionale.

- È possibile visualizzare i dettagli di contatto per il candidato. È inoltre possibile modificare e aggiornare informazioni come necessario tramite il pulsante **Modifica dettagli**.

- È possibile visualizzare l'intero storico delle domande di lavoro del candidato. È possibile visualizzare tutte le mansioni per cui il candidato ha presentato domanda nell'organizzazione e lo stato di tali domande. Se si è parte del team di assunzione per una mansione, è possibile selezionare **Visualizza** per esaminare la domanda in dettaglio.

- Scheda **Documenti** mostra tutti i documenti che il candidato ha aggiunto dal proprio profilo o durante le domande di lavoro. È possibile utilizzare questa scheda per gestire i curriculum, lettere di presentazione, portfolio e altro del candidato. È possibile utilizzare questa scheda per aggiungere documenti.

    Per visualizzare un documento, selezionare il nome del documento nell'elenco dei documenti. È possibile visualizzare i documenti di Microsoft Word nella domanda di lavoro utilizzando Microsoft 365. È inoltre possibile scaricare i documenti nel computer locale tramite l'opzione **Download** per ogni documento.

- Nella scheda **LinkedIn** vengono visualizzate le informazioni LinkedIn del candidato. Per utilizzare questa scheda, è necessario connettere l'account LinkedIn nelle impostazioni utente e stabilire la connessione a LinkedIn Recruiter nel proprio ambiente. Per ulteriori informazioni, vedere [Selezionare i candidati con LinkedIn Recruiter in Microsoft Dynamics 365 Talent - Attract](./attract-linkedin-recruiter.md).

> [!NOTE]
> Solo i candidati possono aggiornare le competenze, lo storico del percorso formativo e le esperienze di lavoro ad essi relativi.

## <a name="add-candidates-from-a-talent-pool-to-a-job"></a>Aggiungere candidati da un pool di talenti a una mansione

Dai risultati della ricerca o un pool di talenti, è possibile inserire un candidato in qualsiasi mansione attiva per cui si assume. Per inserire un candidato in una mansione specifica, effettuare le seguenti operazioni.

1. Individuare il candidato tramite l'opzione di ricerca e aprirne il profilo. In alternativa, aprire il pool di talenti nella scheda **Pool di talenti personali**, cercare il candidato nel pool di talenti e infine aprirne il profilo.

1. Nella pagina del profilo del candidato, selezionare **Aggiungi al processo** nell'angolo superiore destro. 
     
     Un elenco delle mansioni al cui team di assunzione si appartiene, come selezionatore o responsabile assunzioni, viene visualizzato.

1. Selezionare la mansione a cui aggiungere al candidato quindi selezionare **Aggiungi**. È inoltre possibile cercare la mansione mediante il campo di ricerca nella parte superiore della finestra di dialogo **Aggiungere il candidato al processo**.

    Se il prospect è stato abilitato per la mansione, il candidato verrà aggiunto alla fase **Candidato**.

    Se il prospect non è stato abilitato per la mansione, il candidato verrà aggiunto alla fase **Domanda di lavoro**. A seconda della configurazione della mansione, il candidato può inoltre ricevere un messaggio di posta elettronica in cui può visualizzare la domanda di lavoro.

## <a name="add-candidates-from-a-job-to-a-talent-pool"></a>Aggiungere candidati da una mansione a un pool di talenti

Spesso, diversi candidati validi per una mansione non vengono selezionati, ma non si desidera perdere tracce di essi. In questo caso, è possibile aggiungere i candidati in un pool di talenti per invitarli a fare domanda per altre mansioni future.

1. Passare alla mansione da cui si desidera aggiungere un candidato.

1. Selezionare il candidato e aprire la relativa domanda di lavoro.

1. Nella pagina della domanda di lavoro, selezionare **Aggiungi a pool di talenti**. Un elenco dei pool di talenti a cui si ha accesso viene visualizzato.

1. Selezionare o cercare il pool di talenti quindi selezionare **Aggiungi** per aggiungere il candidato a tale pool.


[!INCLUDE[footer-include](../includes/footer-banner.md)]