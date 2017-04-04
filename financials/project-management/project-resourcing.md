---
title: Risorse progetti
description: In questo argomento vengono fornite informazioni su resourcing di progetto.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: cmercado
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: c29c95fc6abd13e668c44d3ccf437bb0e879e46b
ms.lasthandoff: 03/31/2017


---

# <a name="project-resourcing"></a>Risorse progetti

In questo argomento vengono fornite informazioni su resourcing di progetto.

Una sfida per i manager di progetto e responsabili delle risorse durante la fase di progettazione del progetto viene allocazione delle risorse, in cui è necessario determinare e prenotare la risorsa corretta per un progetto. In Microsoft Dynamics 365 per le operazioni, funzionalità di resourcing per i progetti consentono di definire i ruoli che vengono considerati come temporanee le risorse che possono essere prenotate per un impegno specifico, o parte di un impegno. L'assegnazione delle risorse consente ai manager di progetto e di risorse di completare le seguenti attività:

-   Definire un ruolo con le competenze necessarie per semplificare l'abbinamento delle risorse.
-   Utilizzare i ruoli per definire una programmazione iniziale di impegno in base alle risorse prenotate.
-   Stimare i costi e determinare un budget iniziale, in base ai ruoli e alle risorse assegnati per un progetto.
-   Utilizzare i ruoli per stimare il numero delle prenotazioni delle risorse necessarie per ogni impegno.
-   Stimare il numero di risorse necessarie per l'intero ciclo di vita di un progetto.
-   Abbozzare una struttura di suddivisione del lavoro (WBS) mediante le assegnazioni delle risorse iniziali.

[ciclo di vita del progetto![(]. /media/projectresourcing02-1024x812.jpg)](. /media/projectresourcing02.jpg) 

Durante la pianificazione dei progetti continua, le risorse previste possono essere sostituite con la risorsa specificata. Il manager di progetto può inoltre possibile tornare e aggiornare le prenotazioni di resourcing durante l'esecuzione di una delle fasi di progetto.

## <a name="set-up-project-resources"></a>Impostare le risorse del progetto
È necessario impostare un calendario e associarlo a un dipendente o un lavoratore. Il calendario viene utilizzato per programmare il progetto e l'orario di lavoro delle risorse che sono stati prenotati per il progetto. Durante l'impostazione del calendario, i manager di progetto possono eseguire il livellamento delle risorse nell'ambito della relativa ottimizzazione. In base alla programmazione del calendario, è possibile porre restrizioni sulle risorse. È possibile impostare un calendario ** calendari ** nella pagina. 

Quando si imposta un lavoratore come risorsa di progetto, è possibile effettuare uno dei lavoratori impegnati nella società per il quale si desidera impostare le risorse o, è possibile selezionare i lavoratori da altre società della propria organizzazione. Si tratta di risorse interaziendale. Nelle procedure indicate di seguito viene descritto come impostare un lavoratore come risorsa di progetto nella società e su come impostare una risorsa di progetto interaziendale.

### <a name="set-up-a-worker-as-a-project-resource"></a>Impostare un lavoratore come risorsa del progetto

1.  In ** lavoratori ** pagina, in ** lavoratori **elenco di lavoro, selezionare il lavoratore che si desidera aggiungere come risorsa di progetto e quindi aprire il record lavoratore.
2.  Nel riquadro azioni, fare clic su ** progetto ** &gt; ** l'impostazione ** &gt; ** impostato ** progetto.
3.  Selezionare un calendario fiscale e chiudere la pagina.

È anche possibile specificare progetti predefiniti per una risorsa come tipo di pre-assegnazione. Le pre-assegnazioni possono essere utilizzate quando il manager di risorse o progetto sa in anticipo su quali progetti la risorsa lavorerà. Le pre-assegnazioni possono anche essere basate sulla richiesta di uno sponsor o di un cliente del progetto. Per pre-assegnare un progetto, nella pagina **Assegna progetti**, scheda **Progetti**, elenco **Progetti rimanenti**, selezionare il progetto appropriato.

### <a name="set-up-an-intercompany-resource"></a>Impostare una risorsa interaziendale

Quando si imposta un lavoratore come risorsa interaziendale, è necessario completare l'impostazione della società in combinazione con la società di prestito. 

** Nella società di concessione: **

1.  In Dynamics 365 per le operazioni, verificare che la società di concessione sia selezionata e quindi completare la procedura precedente, "Impostare un lavoratore come risorsa di progetto".
2.  Va ** contabilità generale **&gt; ** impostazioni della registrazione **&gt; ** la contabilità interaziendale **. Click **New**.
3.  In ** identificazione della persona giuridica ** sistemi, selezionare la società di concessione. Completare i campi rimanenti come appropriati e fare clic su Salva ** **.
4.  Va ** Gestione progetti e contabilità **&gt; ** l'impostazione **&gt; ** prezzi ** &gt; ** prezzo di trasferimento **. ** **
5.  ** Nel prezzo di trasferimento ** il modulo, fare clic su ** nuovo ** e in ** prende in prestito persona giuridica ** sistemi, selezionare la società pertinente.
6.  Se si desidera consegnare solo nella società di prestito la risorsa creato all'inizio di questa sezione, in ** risorsa ** sistemi, selezionare il nome della risorsa creati. Se si desidera apportare le risorse nella società disponibile nella società di prestito, lasciare ** risorsa ** vuoto il campo.
7.  Va ** Gestione progetti e contabilità **&gt; ** l'impostazione **&gt; ** parametri Gestione progetti e contabilità e ** ** interaziendale ** nella scheda, immettere ** attivare la programmazione risorse e ai fogli presenze interaziendali ** il campo ** Sì **.

** Nella società di prestito: **

1.  Vanno ** Gestione progetti e contabilità ** &gt; ** le risorse di progetto ** &gt; ** le risorse ** elenco.
2.  Nel filtro ricerca, il nome della risorsa nella procedura precedente per la società di concessione verificare che il nome sia incluso nell'elenco di risorse per la società di prestito.

## <a name="manage-resource-competencies"></a>Gestire le competenze delle risorse
Competenze risorsa fanno parte essenziale di gestione delle risorse. Le competenze possono essere utilizzate come riferimento per determinare le risorse con il giusto equilibrio tra competenze, istruzioni, certificazioni acquisite ed esperienza sul progetto. È necessario impostare queste informazioni per ogni risorsa e aggiornarle periodicamente. In questo modo, è possibile ottimizzare le capacità quando durante l'assegnazione delle risorse del progetto vengono abbinate le competenze delle risorse. [esempi![delle competenze, le certificazioni, istruzione e delle esperienze di progetto (]. /media/projectresourcing06-1024x383.jpg)](. /media/projectresourcing06.jpg) 

Nelle procedure indicate di seguito viene descritto come impostare alcune competenze per una risorsa. 

Per impostare le competenze di un lavoratore, è possibile utilizzare la pagina elenco **Lavoratori** in Risorse umane o la pagina elenco **Risorse** in Gestione progetti e contabilità. Per le procedure, ** lavoratori ** la pagina elenco in Risorse umane è utilizzata.

### <a name="set-up-competencies-certificates"></a>Impostare le competenze: Certificati

1.  Nella pagina elenco **Lavoratori** selezionare la riga del lavoratore per cui si desidera aggiungere i certificati.
2.  Nel riquadro azioni, scheda **Lavoratore**, gruppo **Competenze** fare clic su **Certificati**.
3.  Fare clic su **Nuovo**.
4.  Nel campo **Tipo di certificato** selezionare **PMP**.
5.  Nel campo **Data di inizio** selezionare **10/1/2015**.
6.  Fare clic su **Salva**, quindi chiudere la pagina.

### <a name="set-up-competencies-skills"></a>Impostare le competenze: Competenze

1.  Nella pagina elenco **Lavoratori** assicurarsi che il lavoratore utilizzato nella procedura precedente sia ancora selezionato. Nel riquadro azioni, scheda **Lavoratore**, gruppo **Competenze** fare clic su **Competenze**.
2.  Fare clic su **Nuovo**.
3.  Nel campo **Competenza** selezionare **Gestione progetti**.
4.  Nel campo **Livello** selezionare **5 Esperto**.
5.  Nel campo **Data livello** selezionare **1/14/2014**.
6.  Nel campo **Anni di esperienza** immettere **10**.
7.  Fare clic su **Salva**, quindi chiudere la pagina.

## <a name="create-a-new-project"></a>Crea un nuovo progetto
1.  ** Fare clic su Gestione progetti e contabilità ** &gt; ** aree di lavoro ** &gt; ** gestione di progetti **.
2.  Fare clic su **Nuovo progetto** e immettere i seguenti valori:
    -   ** Tipo di progetto ** di tempistica e materiali
    -   ** Nome del progetto ** 2 - fase di aggiornamento XYZ
    -   ** Gruppo di progetti ** il WIP TM\_
    -   ** Identificazione del contratto di progetto ** - 00000002
3.  Fare clic su **Crea progetto**.

### <a name="assign-a-resource-to-a-project"></a>Assegnare una risorsa a un progetto

1.  Fare clic su ** Risorse umane ** &gt; ** lavoratori ** &gt; ** ** lavoratori.
2.  Nell'elenco **Lavoratori** selezionare il record per il lavoratore di cui sono state impostate le competenze e aprire il relativo record.
3.  Nel riquadro azioni, scheda **Progetto**, gruppo **Impostazione**, fare clic su **Assegna progetti**.
4.  Nella pagina **Assegnazioni progetto convalida risorsa** fare clic sulla scheda **Progetti**.
5.  In ** aggiungere il progetto con i progetti selezionati, ** filtro nel progetto 2, fase di aggiornamento XYZ
6.  Nel riquadro **Progetti rimanenti** selezionare un progetto e fare clic sulla freccia per aggiungerlo al riquadro **Progetti selezionati**.
7.  Chiudere la pagina.

Se necessario, è anche possibile assegnare categorie per una risorsa. Il tipo di categoria è Costo o Ricavi. Questo dipende dall'organizzazione. Se non sono presenti categorie assegnate per la risorsa, Dynamics 365 per le operazioni verranno cercati categoria predefinita sui prezzi di costo per ora e ricavi.

### <a name="set-up-project-resource-and-role-characteristics"></a>Impostare le caratteristiche dei ruoli e delle risorse del progetto

Un manager di progetto può utilizzare la funzionalità di assegnazione delle risorse al progetto per creare i ruoli necessari per il progetto. I ruoli è possibile utilizzare le risorse non sono ancora sconosciute quando riservando le risorse. I ruoli possono essere risorse come previsto temporaneamente prenotate, in modo da poter continuare le fasi di progettazione di progetto. 

[esempio![del ruolo (]. /media/projectresourcing05.jpg)](. /media/projectresourcing05.jpg) 

**Scenario**: Contoso è stato assunto per completare un progetto di tempistica e materiali con uno statuto di progetto approvato. Il secondo manager di progetto sta ancora completando l'ambito del progetto. Il responsabile delle risorse sta identificando le risorse specifiche che verranno prenotate per il nuovo progetto. Uno dei ruoli che il garante di progetto ha richiesto, a causa della natura del progetto, è il manager di progetto senior. Il responsabile delle risorse abbia la nuova risorsa e definire il ruolo del sistema del caso il manager di progetto minore richiedere informazioni su una risorsa durante la pianificazione dei progetti. 

Nei passaggi seguenti viene illustrato come responsabile delle risorse può impostare il ruolo Manager progetto senior e associare le caratteristiche delle risorse. Successivamente, il ruolo può essere utilizzato per cercare le risorse disponibili che corrispondono alle competenze delle risorse richieste.

1.  ** Fare clic su Gestione progetti e contabilità ** &gt; ** impostazione ** &gt; ** risorse ** &gt; ** ruoli di attrezzaggio **.
2.  Fare clic su **Nuovo** e immettere i seguenti valori:
    -   ** ID ruolo ** - senior manager di progetto
    -   ** Descrizione ** - senior manager di progetto
3.  Fare clic su **Crea**.
4.  Selezionare il ruolo **Responsabile di progetto principale** e fare clic su **Configurare le caratteristiche**.
5.  Nel campo **Tipo caratteristiche** selezionare **Competenza**.
6.  Nel campo **Caratteristiche disponibili** immettere la competenza che si sta cercando.
7.  Nel campo **Tipo di caratteristica** selezionare **Certificato**.
8.  Nel campo **Caratteristiche disponibili** immettere il tipo di certificato che si sta cercando.
9.  Fare clic su **OK** e chiudere la pagina.

### <a name="assign-a-project-resource-to-a-project"></a>Assegnare una risorsa a un progetto

1.  ** Fare clic su Gestione progetti e contabilità ** &gt; ** Ordinarie ** &gt; ** progetti ** &gt; ** tutti i progetti ** e aprire ** 2 fase di aggiornamento XYZ ** il progetto.
2.  Nella scheda **Team progetto e programmazione** fare clic su **Aggiungi**.
3.  Nel campo **Ruolo** selezionare **Membro del team**.
4.  Fare clic su **Prenota da calendario**.
5.  Nella pagina **Disponibilità risorse** fare clic su **Impostazioni visualizzazione**.
6.  Nella pagina **Modifica impostazioni visualizzazione** immettere i seguenti valori:
    -   ** Formato per la visualizzazione dell'intervallo di date ** il giorno
    -   ** Descrizioni di disponibilità di visualizzazione consente Sì **
    -   ** Capacità di visualizzazione rimanente - Sì **
7.  Nell'elenco di risorse, selezionare una risorsa.
8.  Fare clic su libro ** definitivo ** &gt; ** piena ** capacità.
9.  Chiudere la pagina.

### <a name="assign-a-resource-to-a-default-role"></a>Assegnare una risorsa a un ruolo predefinito

Per contribuire al progetto o responsabili delle risorse, è possibile eseguire il drill-down per spostare delle risorse che possono essere prenotate per un progetto. È possibile associare un ruolo predefinito a una risorsa esistente o una risorsa appena acquisita. Ad esempio, quando Daniel è stato assunto, è necessario l'esperienza e le competenze per rifornire il ruolo di business analyst. Il responsabile delle risorse ha assegnato il ruolo come ruolo standard di Daniel. Di conseguenza, il responsabile delle risorse sono stati aggiunti Daniel a un gruppo di analisti aziendali che sono disponibili a lavorare ai progetti. 

Durante la prenotazione di risorse, i manager di progetto possono filtrare le risorse gestione ruolo disponibili per lavorare ai progetti. Possono utilizzare queste informazioni come criterio quando eseguono analisi decisionali basate su più criteri per soddisfare la capacità delle risorse. Possono anche aggiungere altre caratteristiche di risorse al filtro per cercare le risorse con competenze, istruzione ed esperienze specifiche per un determinato progetto. 

** Scenario: ** Il progetto è stato approvato e senior il ruolo Manager progetto è stato prenotato come risorsa prevista durante la fase di progettazione di progetto. Il manager delle risorse ha ora acquisito una risorsa per ricoprire il ruolo di manager di progetto principale.

1.  ** Fare clic su Gestione progetti e contabilità ** &gt; ** risorse di progetto ** &gt; ** le risorse ** elenco.
2.  Nell'elenco **Risorsa** selezionare **Daniel Goldschmidt**.
3.  Fare clic su ** risorsa di progetto ** &gt; ** gestire ** &gt; ** ruolo di risorse **.
4.  Fare clic su **Nuovo** e immettere i seguenti valori:
    -   ** Validità ** - (la data corrente)
    -   ** Data di scadenza - mai **
    -   ** Ruolo ** - senior manager di progetto
5.  Fare clic su **Salva**, quindi chiudere la pagina.
6.  Nella scheda **Competenze** aggiungere la competenza **PMP** e il certificato **PMP**.

## <a name="set-up-role-based-pricing"></a>Impostare prezzi basati su ruolo
Tutti i costi e i prezzi di vendita e trasferimento possono essere impostati per i ruoli.

1.  ** Fare clic su Gestione progetti e contabilità ** &gt; ** impostazione ** &gt; ** prezzi ** &gt; ** prezzo di vendita (ore) **.
2.  Click **New**.
3.  Immettere una data di validità.
4.  Nella colonna **Ruolo** selezionare un ruolo.
5.  Nella colonna **Determinazione prezzo** immettere un prezzo per il ruolo risorsa selezionato.

## <a name="form-a-project-team"></a>Modulo un membro del personale addetto al programma
Per utilizzare i ruoli in precedenza sono stati impostati in un progetto, un manager di progetto deve associare i ruoli al progetto. In questo caso è possibile concedere per un progetto e Dynamics 365 per le operazioni Etichette automaticamente tali ruoli durante la prenotazione per evitare confusione. Ad esempio, se il manager di progetto dura tre Software Engineei, tre ruoli del Registro di Engineer dotate di Engineer 1, la Engineer di 2 e 3 di Engineer mentre le relative etichette vengono generate automaticamente. Se per il ruolo sono già state impostate caratteristiche, vengono applicate come filtro durante le ricerche di una risorsa. È possibile aggiungere caratteristiche aggiuntive per ridefinire ulteriormente la ricerca. 

Le impostazioni di visualizzazione possono anche essere personalizzate per dare una visione migliore della disponibilità delle risorse. Sono disponibili opzioni per visualizzare la disponibilità oraria, giornaliera, settimanale, mensile, trimestrale e annuale. È anche disponibile un'opzione per mostrare la capacità disponibile e rimanente sulle risorse. Questa opzione è utile per la gestione del tempo quando si stima il tempo disponibile per le attività o la disponibilità delle risorse. 

Il manager di progetto può selezionare un ruolo nella pagina quindi, se si creano risorse disponibili che soddisfa il fabbisogno, selezionare per prenotare la risorsa per rifornire il ruolo. Tenere presente che le risorse non devono essere prenotate al momento della fase di pianificazione. Quando si crea un WBS, è possibile sostituire i ruoli alla risorsa specificata per il progetto. Se i ruoli vengono sostituiti con la risorsa specificata nel WBS, la risorsa installata automaticamente aggiornare l'elenco e la programmazione del personale addetto al programma. 

[elenco personale addetto al programma![che include sia i ruoli che le risorse effettivi (]. /media/projectresourcing03-1024x368.jpg)](. /media/projectresourcing03.jpg) 

Il manager di progetto dispone di diverse opzioni per prenotare una risorsa per un progetto, ad esempio **Capacità rimanente**, **Intera capacità**, **Percentuale capacità** e **Specifica ore**. Queste opzioni di prenotazione possono essere annullate in qualsiasi momento se cambiano le assegnazioni delle risorse. Sono supportati due tipi di prenotazione:

-   ** Il libro definitivo ** la prenotazione della risorsa è stato approvato e confermata per lavorare all'iscrizione della durata specificata.
-   ** Il libro molle ** le prenotazioni della risorsa è stato impostato provvisoriamente per lavorare all'iscrizione della durata specificata.

La seguente procedura spiega come creare un team di progetto.

### <a name="create-a-project-team"></a>Crea un team di progetto

1.  Nella pagina elenco **Tutti i progetti** selezionare un progetto e fare clic su **Modifica**.
2.  ** Nel personale addetto al programma e programmazione ** cataloghi, ** data di fine di programmazione ** nel campo, immettere la data di inizio della programmazione più un mese. Ad esempio, se la data di inizio di programmazione costituisce la 24 giugno 2017 (24/06/2017), immettere 24/07/2017 ** **.
3.  Click **Add**.
4.  Nel riquadro **Aggiungi ruoli al progetto**, campo **Ruolo**, selezionare **Manager di progetto principale**.
5.  Fare clic su **Competenze richieste**.
6.  Nella pagina **Scegli caratteristiche** le caratteristiche precedentemente impostate per il ruolo di manager di progetto principale vengono selezionate per impostazione predefinita. Scegliere **OK**.
7.  Nella pagina **Aggiungi ruoli al progetto**, campo**numero di risorse**, immettere **1**.
8.  Nel campo **Risorsa** la ricerca mostra tutte le risorse con le competenze richieste. Selezionare **Daniel Goldschmidt** e fare clic su **Crea**.
9.  Nella pagina **Progetto** fare clic su **Aggiungi**.
10. Nel riquadro **Aggiungi ruoli al progetto**, campo **Ruolo**, selezionare **Membro del team**. Nel campo **Numero di risorse** immettere **5**.
11. Fare clic su **Crea**.
12. Nella pagina **Progetti** fare clic su **Soddisfa capacità risorsa**.

## <a name="resource-capacity-synchronization"></a>Sincronizzazione capacità per risorsa
I processi per la sincronizzazione delle risorse consentono di garantire che il calendario e le informazioni del calendario di base vengano inseriti nella pianificazione delle risorse del progetto. Se il calendario viene modificato, i processi eseguono gli aggiornamenti necessari alla pianificazione delle risorse di progetto. I processi consentono anche di migliorare le prestazioni, poiché le informazioni sulle risorse del calendario vengono sincronizzate in anticipo, in modo che gli aggiornamenti alle informazioni sulla pianificazione delle risorse si verifichino più rapidamente. È consigliabile pianificare i processi come batch e non uno alla volta. In caso contrario, esiste il rischio che qualcuno dimentichi le date in cui le informazioni sono state sincronizzate l'ultima volta. Se le date incluse non vengono utilizzate, possono verificarsi dei vuoti durante la sincronizzazione delle date.

### <a name="calendar-synchronizationmediaprojectresourcing04-1024x471jpg"></a>![Calendario la sincronizzazione](./media/projectresourcing04-1024x471.jpg)

**Synchronize resource capacity roll-ups**

Il processo di sincronizzazione è progettato per sincronizzare tutte le informazioni sul calendario delle risorse. Queste informazioni includono le informazioni sul calendario di base su tutte le modifiche alla tabella della capacità del calendario risorse del progetto. Per fare in modo che le risorse vengono aggiunte nel progetto, guide di sincronizzazione garantisce che le informazioni aggiornate il calendario siano disponibili. Questa sincronizzazione può essere eseguita in qualsiasi momento. 

Si consiglia di utilizzare un batch. Le opzioni sono disponibili nella sincronizzazione delle prenotazioni della capacità.

-   ** Fare clic su Gestione progetti e contabilità ** &gt; ** periodico ** &gt; ** sincronizzazione di capacità ** &gt; ** sincronizzare la capacità rotolo- UPS risorse **.

| Opzione | descrizione                                                                                                                                                                                          |
|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Sì    | Sincronizzare tutti i dati delle risorse con le informazioni del calendario di base e del calendario e sostituire tutte le informazioni nel calendario della capacità delle risorse del progetto.                                                  |
| No     | Sincronizzare i dati delle risorse, in base al codice intervallo di date e alle date di inizio e fine specificate. Questa opzione non rimuove i dati esistenti e aggiornare le informazioni solo per le risorse appena aggiunte. |

[processo di sincronizzazione![(]. /media/projectresourcing09.jpg)](. /media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>Impostare ruoli sui modelli WBS
I manager di progetto possono impostare i modelli WBS che possono applicare quando creano una struttura di suddivisione lavoro per nuovi progetti. I manager di progetto possono aggiungere i ruoli quando si crea un modello. Utilizzare la seguente procedura per assegnare un ruolo a un modello di WBS. ** **

1.  ** Fare clic su Gestione progetti e contabilità ** &gt; ** impostazione ** &gt; ** progetti ** &gt; ** modelli della struttura di suddivisione del lavoro **.
2.  Fare clic su **Dettagli** per un modello WBS selezionato.
3.  Selezionare un'attività nell'elenco, quindi nel campo **Ruolo** selezionare un ruolo da assegnare all'attività.

### <a name="work-with-a-wbs"></a>Utilizzare una struttura di suddivisione del lavoro

È possibile creare una nuova struttura di suddivisione del lavoro oppure copiare una struttura di suddivisione del lavoro da un modello WBS. Un manager di progetto può gestire facilmente le risorse assegnando ruoli a nuove attività sulla struttura di suddivisione del lavoro. I ruoli possono essere sostituiti dopo l'acquisizione della risorsa o dopo l'identificazione di una risorsa confermata a lavorare sull'attività. Questa flessibilità consente ai manager di progetto di eseguire le attività seguenti:

-   Identificare il numero di risorse richieste per i pacchetti di lavoro WBS.
-   Stimare i costi del progetto.
-   Determinare un budget preliminare.
-   Stimare la durata dell'attività, in base a ruoli e risorse.
-   Elaborare alcuni piani di gestione progetti, in base alle informazioni sul progetto disponibili.

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
<td>Aggiungere automaticamente le risorse programmate usando i ruoli associati a un'attività. Dynamics 365 per le operazioni suggerisce automaticamente le risorse previste l'analisi decisionale di multicriteri basata sui ruoli. Dopo l'impostazione dei ruoli e del lavoro (ore) per le attività in una struttura di suddivisione del lavoro e dopo che la struttura è stata rilasciata, fare clic su <strong>Genera automaticamente team</strong>. Il numero obbligatorio risorse pianificate viene aggiunto alla struttura di suddivisione del lavoro e alla scheda <strong>Team progetto e programmazione</strong>.</td>
</tr>
<tr class="odd">
<td>Risorsa (elenco a discesa)</td>
<td>Nella pagina <strong>Avvia modulo di assegnazione risorse </strong>è possibile selezionare le risorse per prenotarle in modo definitivo o preliminare, in base alla durata specificata. È possibile modificare le impostazioni di visualizzazione per visualizzare e impostare la durata delle attività delle risorse. È possibile selezionare e assegnare le risorse a livello di pacchetto di lavoro usando le seguenti opzioni:
<ul>
<li><strong>Accetta</strong>: consente di confermare le modifiche alla risorsa assegnata a un'attività.</li>
<li><strong>Annulla</strong>: consente di annullare le modifiche alla risorsa assegnata a un'attività.</li>
<li><strong>Assegna automaticamente</strong> Questa opzione consente di selezionare una risorsa a disponibile un ruolo corrispondente all'attività selezionata.</li>
</ul></td>
</tr>
</tbody>
</table>

1.  ** Fare clic su Gestione progetti e contabilità ** &gt; ** progetti ** &gt; ** tutti i progetti **.
2.  Nell'elenco selezionare il progetto **Fase 2 di aggiornamento di XYZ**.
3.  Fare clic su ** piano ** &gt; ** attività ** &gt; ** struttura di suddivisione del lavoro **.
4.  Fare clic su **Nuovo** per aggiungere le seguenti attività di livello uno a struttura di suddivisione del lavoro:
    -   Inizio
    -   Pianificazione
    -   Esecuzione
    -   Monitoraggio e controllo
    -   Chiudi

5.  Imposta date e lavoro (ore), come illustrato nella schermata. [![che fissa le date e lavoro (]. /media/projectresourcing10.jpg)](. /media/projectresourcing10.jpg)
6.  Selezionare la riga attività **Avvio**, quindi, nel campo **Ruolo** selezionare **Manager di progetto principale**.
7.  Fare clic su **Pubblica**.
8.  Sulla stessa riga, nel campo **Risorsa** selezionare **Daniel Goldschmidt**.
9.  Fare clic su **Accetta**.
10. Selezionare la riga attività **Pianificazione**, quindi, nel campo **Ruolo** selezionare **Analista aziendale**.
11. Fare clic su **Pubblica**, quindi su **Genera automaticamente team**.
12. Nella finestra di dialogo che viene visualizzata fare clic su **Sì**.
13. Nel campo **Risorsa** verificare che il valore sia **Analista aziendale 1**.
14. Per la risorsa **Analista aziendale 1**, aprire la ricerca e fare clic su **Avvia modulo di assegnazione risorse**.
15. Selezionare un lavoratore per l'attività.
16. Fare clic su Flessibile ** assegni ** &gt; ** piena ** capacità.
17. Fare clic su **Salva** e chiudere la pagina. 

> [!NOTE] 
> Non viene visualizzato un avviso che la risorsa specificata sarà pari a 2, ovvero il numero di risorse rimane a 1.
18. Nella pagina **Struttura di suddivisione lavoro**, convalidare l'assegnazione delle risorse sulla WBS, quindi fare clic su **Salva**.

## <a name="resource-fulfillment-for-planned-resources"></a>Soddisfare la capacità delle risorse pianificate
Un manager di progetto può pianificare i ruoli risorse necessari per un progetto. Il responsabile delle risorse vedrà queste risorse pianificate come richieste nella pagina **Soddisfare la capacità delle risorse pianificate** e potrà assegnare le risorse effettive.

1.  ** Fare clic su Gestione progetti e contabilità ** &gt; ** progetti ** &gt; ** tutti i progetti **.
2.  Nell'elenco selezionare il progetto **Fase 2 di aggiornamento di XYZ**.
3.  Fare clic su **Progetto**.
4.  Fare clic su **Modifica**.
5.  ** Personale addetto al programma e programmazione ** nella scheda, fare clic su ** ** ** aggiungere **.
6.  Nella finestra di dialogo **Aggiungi ruoli** selezionare il ruolo **Sviluppatore software**.
7.  Fare clic su **Crea**.
8.  Chiudere la pagina del progetto.
9.  ** Fare clic su Gestione progetti e contabilità ** &gt; ** risorse di progetto ** &gt; ** soddisfazione di risorse **.
10. Selezionare **Sviluppatore software 1** per il progetto **Fase 2 di aggiornamento di XYZ**.
11. Selezionare un lavoratore e fare clic su **Assegna**.
12. Verificare che la riga per **Sviluppatore software 1** sia stata rimossa per il progetto **Fase 2 di aggiornamento di XYZ**.
13. Nella scheda **Team progetto e programmazione**, per il progetto **Fase 2 di aggiornamento di XYZ**, verificare che il lavoratore selezionato al punto 11 sia stato aggiunto come **Sviluppatore software**.

## <a name="requests-for-project-resources"></a>Risposte alle risorse di progetto
I responsabili delle risorse di uso della funzionalità di programmazione risorse di progetto solo da distribuire sono state immesse la risorsa per gli impegni o progetti. Per attivare questa funzionalità, è necessario completare le seguenti attività, o verificare che siano soddisfatti.

-   Consente di impostare sequenze numeriche.
-   Flussi di lavoro di Gestione progetti e contabilità dei progetti.
-   Attivare il flusso di lavoro di richiesta della risorsa.

Una volta verificate o completate le attività precedente, è possibile effettuare le seguenti attività necessarie.

-   Creare una richiesta delle risorse da una risorsa specificata in modo temporaneo prenotata.
-   Verificare i requisiti risorsa.
-   Gestione dei requisiti risorsa.
-   Richiedere una risorsa fornito da WBS.
-   Prenoti le risorse a un progetto senza una richiesta per una risorsa specifica.

## <a name="monitor-project-teams"></a>Verificare il personale addetto al programma
1.  ** Fare clic su Gestione progetti e contabilità ** &gt; ** progetti ** &gt; ** tutti i progetti **.
2.  Nell'elenco di progetti, fare clic sul collegamento **ID progetto** per il progetto **Fase 2 di aggiornamento di XYZ**.
3.  Nella Scheda dettaglio **Team progetto e programmazione** verificare che le risorse del progetto elencate siano corrette.



