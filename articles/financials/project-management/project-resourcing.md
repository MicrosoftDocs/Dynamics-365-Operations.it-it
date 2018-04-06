---
title: Risorse progetti
description: Questo argomento fornisce informazioni sull'assegnazione delle risorse a un progetto.
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 2d31a5dfd16a4404e19c6c9693dacecff6f2f064
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="project-resourcing"></a>Risorse progetti

[!include[banner](../includes/banner.md)]

Questo argomento fornisce informazioni sull'assegnazione delle risorse a un progetto.

Una delle problematiche dei manager di progetto e di risorse durante la fase di progettazione del progetto è l'allocazione delle risorse, fase in cui devono determinare e prenotare la risorsa corretta a un progetto. In Microsoft Dynamics 365 for Finance and Operations, le funzionalità di assegnazione risorse per i progetti consentono di definire i ruoli che vengono trattati come risorse temporanee prenotabili per un impegno specifico o per una parte dell'impegno. L'assegnazione delle risorse consente ai manager di progetto e di risorse di completare le seguenti attività:

- Definire un ruolo con le competenze necessarie in modo da semplificare l'abbinamento delle risorse.
- Utilizzare i ruoli per definire una programmazione di impegno iniziale basata sulle prenotazioni delle risorse.
- Stimare i costi e determinare un budget iniziale, in base ai ruoli e alle risorse assegnati per un progetto.
- Utilizzare i ruoli per stimare il numero di prenotazioni risorse necessarie per ogni impegno.
- Stimare il numero di risorse necessarie per l'intero ciclo di vita di un progetto.
- Abbozzare una struttura di suddivisione del lavoro (WBS) mediante le assegnazioni delle risorse iniziali.

[![Ciclo di vita progetto](./media/projectresourcing02-1024x812.jpg)](./media/projectresourcing02.jpg)

Nel corso della pianificazione del progetto, è possibile sostituire le risorse pianificate con risorse con personale. Il manager di progetto può anche tornare indietro e aggiornare le prenotazioni delle risorse durante qualsiasi fase del progetto.

## <a name="set-up-project-resources"></a>Impostare le risorse del progetto
È necessario impostare un calendario e associarlo a un dipendente o un lavoratore. Il calendario viene utilizzato per programmare il progetto e l'orario di lavoro delle risorse per esso prenotate. Durante l'impostazione del calendario, i manager di progetto possono eseguire il livellamento delle risorse nell'ambito della relativa ottimizzazione. In base alla programmazione del calendario, è possibile porre restrizioni sulle risorse. È possibile impostare un calendario nella pagina **calendari**.

Quando si imposta un lavoratore come risorsa di progetto, è possibile selezionare uno dei lavoratori che lavorano nella società per il quale si desidera impostare le risorse. In alternativa, è possibile selezionare i lavoratori da altre società della propria organizzazione. Questi lavoratori sono noti come risorse interaziendali.

Nelle procedure indicate di seguito viene descritto come impostare un lavoratore come risorsa di progetto nella società e come impostare una risorsa di progetto interaziendale.

### <a name="set-up-a-worker-as-a-project-resource"></a>Impostare un lavoratore come risorsa del progetto

1. Nella pagina **Lavoratori**, in **Lavoratori** selezionare il lavoratore che si intende aggiungere come risorsa del progetto e aprire il relativo record.
2. Nel Riquadro azioni, selezionare **Progetto** &gt; **Impostazioni** &gt; **Impostazione progetto**.
3. Selezionare un calendario, quindi chiudere la pagina.

È anche possibile specificare progetti predefiniti per una risorsa come tipo di pre-assegnazione. Le pre-assegnazioni possono essere utilizzate quando il manager di risorse o progetto sa in anticipo su quali progetti la risorsa lavorerà. Le pre-assegnazioni possono anche essere basate sulla richiesta di uno sponsor o di un cliente del progetto. Per pre-assegnare un progetto, nella pagina **Assegna progetti**, scheda **Progetti**, elenco **Progetti rimanenti**, selezionare il progetto appropriato.

### <a name="set-up-an-intercompany-resource"></a>Impostare una risorsa interaziendale

Quando si imposta un lavoratore come risorsa interaziendale, è necessario completare l'impostazione nella società che concede in prestito la risorsa e nella società che la prende in prestito.

**Nella società che concede in prestito la risorsa**

1. In Finance and Operations, verificare che la società di concessione sia selezionata e quindi completare la procedura nella sezione precedente, "Impostare un lavoratore come risorsa del progetto".
2. Nella pagina **Contabilità interaziendale**, selezionare **Nuovo**.
3. Nel campo **ID persona giuridica** selezionare la società di concessione. Completare i campi rimanenti come appropriati e selezionare **Salva**.
4. Nella pagina **Prezzo di trasferimento**, selezionare **Nuovo**.
5. Nel campo **Persona giuridica richiedente** selezionare la società appropriata.
6. Per concedere alla società richiedente solo la risorsa creata all'inizio di questa sezione nel campo **Risorsa**, selezionare il nome della risorsa creata. Per redenre disponibili tutte le risorse nella società di concessione alla società richiedente, lasciare vuoto il campo **Risorsa**.
7. Nella pagina **Parametri Gestione progetti e contabilità**, nella scheda **Interaziendale**, impostare il campo **Abilita programmazione risorse interaziendale e fogli presenze** su **Sì**.

**Nella società che prende in prestito la risorsa**

- Nella pagina **Elenco risorse**, nel filtro di ricerca, immettere il nome della risorsa creata nella procedura precedente per la società di concessione per verificare che il nome sia incluso nell'elenco di risorse per la società di prestito.

## <a name="manage-resource-competencies"></a>Gestire le competenze delle risorse
Le competenze della risorsa sono una parte essenziale della gestione delle risorse. Le competenze possono essere utilizzate come riferimento per determinare le risorse con il giusto equilibrio tra competenze, istruzioni, certificazioni acquisite ed esperienza sul progetto. È necessario impostare queste informazioni per ogni risorsa e aggiornarle periodicamente. In questo modo, è possibile ottimizzare le capacità quando durante l'assegnazione delle risorse del progetto vengono abbinate le competenze delle risorse.

[![Esempi di competenze, certificazioni, istruzione ed esperienza sul progetto](./media/projectresourcing06-1024x383.jpg)](./media/projectresourcing06.jpg)

Nelle procedure indicate di seguito viene descritto come impostare alcune competenze per una risorsa.

Per impostare le competenze di un lavoratore, è possibile utilizzare la pagina elenco **Lavoratori** in Risorse umane o la pagina elenco **Risorse** in Gestione progetti e contabilità. Per le procedure riportate di seguito, utilizzeremo la pagina elenco **Lavoratori** in Risorse umane.

### <a name="set-up-competencies-certificates"></a>Impostare le competenze: Certificati

1. Nella pagina elenco **Lavoratori** selezionare la riga per il lavoratore per cui si desidera aggiungere i certificati.
2. Nel riquadro azioni, scheda **Lavoratore**, gruppo **Competenze** selezionare **Certificati**.
3. Selezionare **Nuovo**, quindi nel campo **Tipo di certificato**, selezionare **PMP**.
4. Nel campo **Data di inizio**, selezionare **10/1/2015** e quindi **Salva**.

### <a name="set-up-competencies-skills"></a>Impostare le competenze: Competenze

1. Nella pagina elenco **Lavoratori** assicurarsi che il lavoratore utilizzato nella procedura precedente sia ancora selezionato. Nel riquadro azioni, scheda **Lavoratore**, gruppo **Competenze** selezionare **Competenze**.
2. Selezionare **Nuovo**.
3. Nel campo **Competenza** selezionare **Gestione progetti**.
4. Nel campo **Livello** selezionare **5 Esperto**.
5. Nel campo **Data livello** selezionare **1/14/2014**.
6. Nel campo **Anni di esperienza** immettere **10**.
7. Selezionare **Salva**, quindi chiudere la pagina.

## <a name="create-a-new-project"></a>Crea un nuovo progetto
1. Nella pagina **Gestione progetti** selezionare **Nuovo progetto**, quindi immettere i valori seguenti:

    - **Tipo di progetto:** Tempistica e materiali
    - **Nome progetto:** Fase 2 di aggiornamento di XYZ
    - **Gruppo di progetti:** TM\_WIP
    - **ID contratto progetto:** 00000002

2. Selezionare **Crea progetto**.

### <a name="assign-a-resource-to-a-project"></a>Assegnare una risorsa a un progetto

1. Nella pagina **Lavoratori**, nell'elenco **Lavoratori**, selezionare il record per il lavoratore di cui sono state impostate le competenze e aprire il relativo record.
2. Nel riquadro azioni, scheda **Progetto**, gruppo **Impostazione**, selezionare **Assegna progetti**.
3. Nella pagina **Assegnazioni progetto convalida risorse**, nella scheda **Progetti**, nel campo **Aggiungere il progetto ai progetti selezionati**, filtrare in base al progetto **Fase 2 di aggiornamento di XYZ**.
4. Nel riquadro **Progetti rimanenti** selezionare un progetto e fare clic sul pulsante freccia per aggiungerlo al riquadro **Progetti selezionati**.

Se necessario, è anche possibile assegnare categorie per una risorsa. Il tipo di categoria è **Costo** o **Ricavi**. Il tipo di categoria viene determinato dall'organizzazione. Se per una risorsa non vi sono categorie assegnate, Finance and Operations cerca la categoria predefinita nei prezzi orari per costi e ricavi.

### <a name="set-up-project-resource-and-role-characteristics"></a>Impostare le caratteristiche dei ruoli e delle risorse del progetto

Un manager di progetto può utilizzare la funzionalità di assegnazione delle risorse al progetto per creare i ruoli necessari per il progetto. I ruoli possono essere utilizzati se le risorse confermate sono ancora sconosciute durante la prenotazione delle risorse. I ruoli possono essere utilizzare per prenotare temporaneamente le risorse come pianificate, in modo da poter continuare le fasi di pianificazione del progetto.

[![Esempio di un ruolo](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Scenario**: Contoso è stato assunto per completare un progetto di tempistica e materiali con uno statuto di progetto approvato. Il secondo manager di progetto sta ancora completando l'ambito del progetto. Il responsabile delle risorse sta al momento identificando le risorse specifiche che verranno prenotare per il nuovo progetto. A causa della natura fondamentale del progetto, uno dei ruoli richiesti dalla sponsor di progetto è Manager di progetto principale. Il responsabile delle risorse deve acquisire la nuova risorsa e definisce il ruolo del sistema, qualora il secondo manager di progetto minore richieda le informazioni sulle risorse durante la pianificazione del progetto.

La procedura seguente mostra come il manager di risorse può impostare il ruolo di manager di progetto principale e associare le caratteristiche delle risorse. Successivamente, il ruolo può essere utilizzato per cercare le risorse disponibili che corrispondono alle competenze delle risorse richieste.

1. Nella pagina **Impostazione ruoli** selezionare **Nuovo progetto**, quindi immettere i valori seguenti:

    - **ID ruolo:** Manager di progetto principale
    - **Descrizione:** Manager di progetto principale

2. Selezionare **Crea**.
3. Selezionare il ruolo **Manager di progetto principale** e quindi **Configurare le caratteristiche**.
4. Nel campo **Tipo caratteristiche** selezionare **Competenza**.
5. Nel campo **Caratteristiche disponibili** immettere la competenza che si sta cercando.
6. Nel campo **Tipo di caratteristica** selezionare **Certificato**.
7. Nel campo **Caratteristiche disponibili** immettere il tipo di certificato che si sta cercando.

### <a name="assign-a-project-resource-to-a-project"></a>Assegnare una risorsa a un progetto

1. Nella pagina **Tutti i progetti**, selezionare il progetto **Fase 2 di aggiornamento di XYZ**.
2. Nella scheda **Team progetto e programmazione**, selezionare **Aggiungi**.
3. Nel campo **Ruolo** selezionare **Membro del team**.
4. Selezionare **Prenota da calendario**.
5. Nella pagina **Disponibilità risorse** selezionare **Impostazioni visualizzazione**.
6. Nella pagina **Modifica impostazioni visualizzazione** immettere i seguenti valori:

    - **Formato per la visualizzazione dell'intervallo di date:** Giorno
    - **Visualizza descrizioni disponibili:** Sì
    - **Visualizza capacità rimanente:** Sì

7. Nell'elenco di risorse, selezionare una risorsa.
8. Selezionare **Prenotazione definitiva** e **Intera capacità**.


### <a name="assign-a-resource-to-a-default-role"></a>Assegnare una risorsa a un ruolo predefinito

Per aiutare i manager di progetto o risorse, è possibile analizzare ulteriormente le risorse prenotabili per un progetto. È possibile associare un ruolo predefinito a una risorsa esistente o una risorsa appena acquisita. Ad esempio, quando Daniel è stato assunto, aveva l'esperienza e le competenze per ricoprire il ruolo di business analyst. Il responsabile delle risorse ha assegnato questo ruolo come ruolo standard a Daniel. Di conseguenza, il responsabile delle risorse ha aggiunto Daniel a un gruppo di business analyst che sono disponibili per lavorare ai progetti.

Durante la prenotazione delle risorse, i manager di progetto possono filtrare le risorse disponibili a lavorare sui progetti. Possono utilizzare queste informazioni come criterio quando eseguono analisi decisionali basate su più criteri per soddisfare la capacità delle risorse. Possono anche aggiungere altre caratteristiche di risorse al filtro per cercare le risorse con competenze, istruzione ed esperienze specifiche per un determinato progetto.

**Scenario:** è stato avviato un progetto approvato e il ruolo di manager di progetto principale è stato prenotato come risorsa pianificata durante la fase di pianificazione del progetto. Il manager delle risorse ha ora acquisito una risorsa per ricoprire il ruolo di manager di progetto principale.

1. Nella pagina **Elenco risorse** selezionare **Daniel Goldschmidt**.
2. Nella pagina **Ruolo risorsa** selezionare **Nuovo**, quindi immettere i valori seguenti:

    - **Validità:** immettere la data corrente.
    - **Scadenza:** immettere **Mai**.
    - **Ruolo:** immettere **Manager di progetto principale**

3. Selezionare **Salva**, quindi chiudere la pagina.
4. Nella scheda **Competenze** aggiungere la competenza **PMP** e il certificato **PMP**.

## <a name="set-up-role-based-pricing"></a>Impostare prezzi basati su ruolo
Tutti i costi e i prezzi di vendita e trasferimento possono essere impostati per i ruoli.

1. Nella pagina **Prezzo di vendita (ora)** selezionare **Nuovo**, quindi immettere una data di validità.
2. Nella colonna **Ruolo** selezionare un ruolo.
3. Nella colonna **Determinazione prezzo** immettere un prezzo per il ruolo risorsa selezionato.

## <a name="form-a-project-team"></a>Formare un team di progetto
Per utilizzare i ruoli impostati in precedenza in un progetto, un manager di progetto deve associare i ruoli al progetto. È possibile assegnare molteplici ruoli a un progetto. Per evitare confusione, Finance and Operations etichetta automaticamente questi ruoli durante la prenotazione. Ad esempio, se il manager di progetto richiede tre programmatori, vengono generati automaticamente tre ruoli programmatore con le etichette **programmatore 1**, **programmatore 2** e **programmatore 3**. Se per il ruolo sono già state impostate caratteristiche, vengono applicate come filtro durante le ricerche di una risorsa. È possibile aggiungere caratteristiche aggiuntive per ridefinire ulteriormente la ricerca.

Le impostazioni di visualizzazione possono anche essere personalizzate per dare una visione migliore della disponibilità delle risorse. Sono disponibili opzioni per visualizzare la disponibilità oraria, giornaliera, settimanale, mensile, trimestrale e annuale. È anche disponibile un'opzione per mostrare la capacità disponibile e rimanente sulle risorse. Questa opzione è utile per la gestione del tempo quando si stima il tempo disponibile per le attività o la disponibilità delle risorse.

Il manager di progetto può selezionare un ruolo nella pagina e quindi, se sono presenti risorse disponibili in base ai requisiti, prenotare una risorsa per ricoprire il ruolo. Si noti che le risorse non devono essere prenotate a questo punto nella fase di pianificazione. Quando si crea una struttura di suddivisione lavoro, è possibile sostituire i ruoli con risorse con personale per il progetto. Se i ruoli vengono sostituiti con le risorse con personale nella struttura di suddivisione lavoro, l'impostazione della risorsa aggiorna automaticamente la pianificazione e l'elenco del team di progetto.

[![Elenco del team di progetto che include i ruoli e le risorse effettive](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

Il manager di progetto dispone di diverse opzioni per prenotare una risorsa per un progetto, ad esempio **Capacità rimanente**, **Intera capacità**, **Percentuale capacità** e **Specifica ore**. Queste opzioni di prenotazione possono essere annullate in qualsiasi momento se cambiano le assegnazioni delle risorse. Sono supportati due tipi di prenotazione:

- **Prenotazione definitiva**: la prenotazione delle risorse è stata approvata e confermata per l'impegno per la durata specificata.
- **Prenotazione preliminare**: la prenotazione delle risorse è stata impostata per l'impegno per la durata specificata.

La seguente procedura spiega come creare un team di progetto.

### <a name="create-a-project-team"></a>Crea un team di progetto

1. Nella pagina elenco **Tutti i progetti** selezionare un progetto e **Modifica**.
2. Nella scheda **Team progetto e programmazione**, campo **Programma data di fine**, immettere la data di inizio della programmazione più un mese. Ad esempio, se la data di inizio della programmazione è il 24 giugno 2017 (24/06/2017), immettere **24/07/2017**.
3. Selezionare **Aggiungi**.
4. Nel riquadro **Aggiungi ruoli al progetto**, campo **Ruolo**, selezionare **Manager di progetto principale**.
5. Selezionare **Competenze richieste**.
6. Nella pagina **Scegli caratteristiche** le caratteristiche precedentemente impostate per il ruolo di manager di progetto principale vengono selezionate per impostazione predefinita. Selezionare **OK**.
7. Nella pagina **Aggiungi ruoli al progetto**, campo **Numero di risorse**, immettere **1**.
8. Nel campo **Risorsa** la ricerca mostra tutte le risorse con le competenze richieste. Selezionare **Daniel Goldschmidt** e quindi **Crea**.
9. Nella pagina **Progetto** selezionare **Aggiungi**.
10. Nel riquadro **Aggiungi ruoli al progetto**, campo **Ruolo**, selezionare **Membro del team**. Nel campo **Numero di risorse** immettere **5**.
11. Selezionare **Crea**.
12. Nella pagina **Progetti** selezionare **Soddisfa capacità risorsa**.

## <a name="resource-capacity-synchronization"></a>Sincronizzazione capacità per risorsa
I processi per la sincronizzazione delle risorse garantiscono l'inserimento delle informazioni per il calendario e il calendario di base nella pianificazione delle risorse del progetto. Se il calendario viene modificato, i processi eseguono gli aggiornamenti necessari alla pianificazione delle risorse di progetto. I processi consentono anche di migliorare le prestazioni, poiché le informazioni sulle risorse del calendario vengono sincronizzate in anticipo. Di conseguenza, gli aggiornamenti alle informazioni sulla pianificazione delle risorse si verificano più rapidamente.. È consigliabile pianificare i processi come batch e non uno alla volta. In caso contrario, esiste il rischio che qualcuno dimentichi le date in cui le informazioni sono state sincronizzate l'ultima volta. Se le date incluse non vengono utilizzate, possono verificarsi dei vuoti durante la sincronizzazione delle date.

![Sincronizzazione del calendario](./media/projectresourcing04-1024x471.jpg)

### <a name="synchronize-resource-capacity-roll-ups"></a>Sincronizza rollup capacità risorse

Il processo di sincronizzazione è progettato per sincronizzare tutte le informazioni sul calendario delle risorse. Queste informazioni includono le informazioni sul calendario di base su tutte le modifiche alla tabella della capacità del calendario risorse del progetto. Se nuove risorse vengono aggiunte nel progetto, la sincronizzazione garantisce che le informazioni del calendario aggiornate siano disponibili. Questa sincronizzazione può essere eseguita in qualsiasi momento.

Si consiglia di utilizzare un batch. Le opzioni sono disponibili durante la sincronizzazione delle prenotazioni della capacità.

1. Selezionare **Gestione progetti e contabilità** &gt; **Periodico** &gt; **Sincronizzazione capacità** &gt; **Sincronizza rollup capacità risorse**.
2. Impostare le opzioni nella seguente tabella.

    | Opzione      | descrizione |
    |-------------|-------------|
    | Codice periodo | È possibile selezionare il codice intervallo date della contabilità generale per impostare le date di inizio e fine per il processo di sincronizzazione dei roll-up delle capacità delle risorse. |
    | Data di inizio  | Immettere la data di inizio del processo di sincronizzazione per i roll-up delle capacità delle risorse. |
    | Data di fine    | Immettere la data di fine del processo di sincronizzazione per i roll-up delle capacità delle risorse. |

[![Processo di sincronizzazione](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>Impostare ruoli sui modelli WBS
I manager di progetto possono impostare i modelli WBS che possono applicare quando creano una struttura di suddivisione lavoro per nuovi progetti. I manager di progetto possono aggiungere ruoli quando creano un modello. Utilizzare la procedura riportata di seguito per assegnare un ruolo a un modello WBS. 

1. Selezionare **Gestione progetti e contabilità** &gt; **Impostazioni** &gt; **Progetti** &gt; **Modelli di struttura di suddivisione del lavoro**.
2. Selezionare **Dettagli** per un modello WBS selezionato.
3. Selezionare un'attività nell'elenco, quindi nel campo **Ruolo** selezionare un ruolo da assegnare all'attività.

### <a name="work-with-a-wbs"></a>Utilizzare una struttura di suddivisione del lavoro

È possibile creare una nuova struttura di suddivisione del lavoro oppure copiare una struttura di suddivisione del lavoro da un modello WBS. Un manager di progetto può gestire facilmente le risorse assegnando ruoli a nuove attività sulla struttura di suddivisione del lavoro. I ruoli possono essere sostituiti dopo l'acquisizione della risorsa o dopo l'identificazione di una risorsa confermata a lavorare sull'attività. Questa flessibilità consente ai manager di progetto di eseguire le attività seguenti:

- Identificare il numero di risorse richieste per i pacchetti di lavoro WBS.
- Stimare i costi del progetto.
- Determinare un budget preliminare.
- Stimare la durata dell'attività, in base a ruoli e risorse.
- Elaborare alcuni piani di gestione progetti, in base alle informazioni sul progetto disponibili.

Le opzioni aggiuntive sono state aggiunte nella struttura di suddivisione del lavoro per utilizzare meglio la funzionalità di assegnazione risorse.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opzione</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Assegnazioni risorse</td>
<td>Visualizzare le risorse assegnate, le date, il numero di ore e il tipo di prenotazione per le attività nella struttura di suddivisione del lavoro.</td>
</tr>
<tr class="even">
<td>Genera automaticamente team</td>
<td>Aggiungere automaticamente le risorse programmate usando i ruoli associati a un'attività. Finance and Operations suggerisce automaticamente le risorse programmate usando le analisi decisionali basate su più criteri basate su ruoli. Dopo l'impostazione dei ruoli e del lavoro (ore) per le attività in una struttura di suddivisione del lavoro e dopo che la struttura è stata rilasciata, selezionare <strong>Genera automaticamente team</strong>. Il numero obbligatorio risorse pianificate viene aggiunto alla struttura di suddivisione del lavoro e alla scheda <strong>Team progetto e programmazione</strong>.</td>
</tr>
<tr class="odd">
<td>Risorsa (elenco a discesa)</td>
<td>Nella pagina <strong>Avvia modulo di assegnazione risorse </strong>è possibile selezionare le risorse per prenotarle in modo definitivo o preliminare, in base alla durata specificata. È possibile modificare le impostazioni di visualizzazione per visualizzare e impostare la durata delle attività delle risorse. È possibile selezionare e assegnare le risorse a livello di pacchetto di lavoro usando le seguenti opzioni:
<ul>
<li><strong>Accetta</strong>: consente di confermare le modifiche alla risorsa assegnata a un'attività.</li>
<li><strong>Annulla</strong>: consente di annullare le modifiche alla risorsa assegnata a un'attività.</li>
<li><strong>Assegna automaticamente</strong>: una risorsa con personale disponibile che ha un ruolo corrispondente viene automaticamente selezionata e assegnata all'attività selezionata.</li>
</ul></td>
</tr>
</tbody>
</table>

1. Nella pagina **Tutti i progetti**, selezionare il progetto **Fase 2 di aggiornamento di XYZ**.
2. Selezionare **Pianifica** &gt; **Attività** &gt; **Struttura di suddivisione del lavoro**.
3. Selezionare **Nuovo** per aggiungere le seguenti  attività di livello uno a struttura di suddivisione del lavoro:

    - Inizio
    - Pianificazione
    - Esecuzione
    - Monitoraggio e controllo
    - Chiusura

4. Impostare le date e l'impegno (ore), come mostrato nell'illustrazione seguente.

    [![Impostazione delle date e dell'impegno](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)

5. Selezionare la riga attività **Avvio**, quindi, nel campo **Ruolo** selezionare **Manager di progetto principale**.
6. Selezionare **Pubblica**
7. Sulla stessa riga, nel campo **Risorsa** selezionare **Daniel Goldschmidt** e quindi **Accetta**.
8. Selezionare la riga attività **Pianificazione**, quindi, nel campo **Ruolo** selezionare **Analista aziendale**.
9. Selezionare **Pubblica**, quindi **Genera automaticamente team**.
10. Nella finestra di messaggio visualizzata selezionare **Sì**.
11. Nel campo **Risorsa** verificare che il valore sia **Analista aziendale 1**.
12. Per la risorsa **Analista aziendale 1**, aprire la ricerca e selezionare **Avvia modulo di assegnazione risorse**. Quindi selezionare un lavoratore per l'attività.
13. Selezionare **Assegna in via preliminare** &gt; **Intera capacità**.

    > [!NOTE] 
    > Non si viene avvisati che la risorsa specificata è ora 2, poiché il numero di risorse rimane 1.

14. Nella pagina **Struttura di suddivisione lavoro**, convalidare l'assegnazione delle risorse sulla WBS, quindi selezionare **Salva**.

## <a name="resource-fulfillment-for-planned-resources"></a>Soddisfare la capacità delle risorse pianificate
Un manager di progetto può pianificare i ruoli risorse necessari per un progetto. Il responsabile delle risorse vedrà queste risorse pianificate come richieste nella pagina **Soddisfare la capacità delle risorse pianificate** e potrà assegnare le risorse effettive.

1. Nella pagina **Tutti i progetti**, selezionare il progetto **Fase 2 di aggiornamento di XYZ**.
2. Selezionare **Progetto**, quindi selezionare **Modifica**.
3. Nella scheda **Team progetto e programmazione**, selezionare **Aggiungi**.
4. Nella finestra di dialogo **Aggiungi ruoli** selezionare il ruolo **Sviluppatore software**.
5. Selezionare **Crea**, quindi chiudere la pagina del progetto.
6. Nella pagina **Possibilità di soddisfare la capacità delle risorse**, selezionare **Sviluppatore software 1** per il progetto **Fase 2 di aggiornamento di XYZ**.
7. Selezionare un lavoratore e quindi **Assegna**.
8. Verificare che la riga per **Sviluppatore software 1** sia stata rimossa per il progetto **Fase 2 di aggiornamento di XYZ**.
9. Nella scheda **Team progetto e programmazione**, per il progetto **Fase 2 di aggiornamento di XYZ**, verificare che il lavoratore selezionato nel passaggio precedente sia stato aggiunto come **Sviluppatore software**.

## <a name="requests-for-project-resources"></a>Richieste di risorse di progetto
La funzionalità per la programmazione di risorse di progetto consente solo ai manager di risorse di distribuire risorse con personale per gli impegni o progetti. Per attivare questa funzionalità, è necessario completare le seguenti attività o verificare che siano state completate:

- Consente di impostare sequenze numeriche.
- Impostare i flussi di lavoro di Gestione progetti e contabilità.
- Abilitare i flussi di lavoro della richiesta di risorse.

Una volta completate le attività precedenti, è possibile completare le seguenti attività come necessario:

- Creare una richiesta di risorse da una risorsa con personale e prenotazione preliminare.
- Monitorare le richieste risorsa.
- Completare le richieste risorsa.
- Richiedere una risorsa con personale da un WBS.
- Prenotare le risorse per un progetto senza avere una richiesta per una risorsa con personale.

## <a name="monitor-project-teams"></a>Monitorare i team di progetto
1. Nella pagina **Tutti i progetti**, selezionare il collegamento **ID progetto** per il progetto **Fase 2 di aggiornamento di XYZ**.
2. Nella Scheda dettaglio **Team progetto e programmazione** verificare che le risorse del progetto elencate siano corrette.

