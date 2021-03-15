---
title: Panoramica fedeltà
description: In questo argomento vengono descritte le funzionalità del programma fedeltà di Dynamics 365 Commerce e i passaggi di impostazione corrispondenti che aiutano il rivenditore a iniziare facilmente i propri programmi fedeltà.
author: scott-tucker
manager: AnnBe
ms.date: 07/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailLoyaltyPrograms, RetailPriceDiscGroup
audience: Application User
ms.reviewer: josaw
ms.custom: 16201
ms.assetid: f79559d2-bc2d-4f0b-a938-e7a61524ed80
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 085071cb7aa314dd8a8c19b8ef2ac926a6ab4103
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985813"
---
# <a name="loyalty-overview"></a>Panoramica fedeltà

[!include [banner](includes/banner.md)]

I programmi fedeltà possono contribuire ad aumentare la fedeltà dei clienti premiandoli per le loro interazioni con il brand del rivenditore. In Dynamics 365 Commerce è possibile impostare programmi fedeltà semplici o complessi applicabili tra le persone giuridiche in qualsiasi canale di commercio. In questo argomento vengono descritte le funzionalità del programma fedeltà di Commerce e i passaggi di impostazione corrispondenti che aiutano il rivenditore a iniziare facilmente i propri programmi fedeltà.

È possibile impostare il programma fedeltà in modo che comprenda le seguenti opzioni.

- Impostare i molteplici tipi di premi offerti nei programmi fedeltà e tenere traccia della partecipazione ai programmi fedeltà.
- Impostare i programmi fedeltà che rappresentano i diversi incentivi di premi offerti. È possibile includere i livelli del programma fedeltà per offrire maggiori incentivi e premi ai clienti che acquistano con maggiore frequenza o spendono più denaro nei punti vendita.
- Definire le regole di acquisizione per identificare le attività che un cliente deve completare per guadagnare premi. È inoltre possibile definire le regole di rimborso per identificare quando e come un cliente può riscattare i premi.
- Emettere carte fedeltà da qualsiasi canale che partecipa ai programmi fedeltà e collegare le carte fedeltà a uno o più programmi fedeltà a cui il cliente può partecipare. È inoltre possibile collegare un record cliente a una carta fedeltà, in modo che il cliente possa raccogliere i punti programma fedeltà da più carte e riscattarli.
- Rettificare manualmente le carte fedeltà o trasferire il saldo premi fedeltà da una carta a un'altra per soddisfare o premiare un cliente.

## <a name="setting-up-loyalty-programs"></a>Impostazione dei programmi fedeltà

È necessario impostare più componenti per abilitare la funzionalità di fedeltà in Commerce. Nel diagramma riportato di seguito vengono illustrati i componenti del programma fedeltà e viene indicato in quale modo fanno riferimento l'uno all'altro.

![Flusso del processo di impostazione del programma fedeltà](./media/loyaltyprocess.gif "Componenti del programma fedeltà e come sono correlati tra loro")

## <a name="loyalty-components"></a>Componenti del programma fedeltà

Nella seguente tabella viene descritto ciascun componente e viene indicato dove viene utilizzato nell'impostazione del programma fedeltà.

| Componente                                        | descrizione | Dove è usato |
|--------------------------------------------------|-------------|-----------------|
| Impostare gli sconti (prerequisito)                  | Impostare gli sconti offerti ai clienti del programma fedeltà. Ad esempio, il 5 percento di sconto su tutti i prodotti di abbigliamento. | È necessario aggiungere gli sconti ai gruppi di prezzi per poterli includere in un programma fedeltà. I gruppi di prezzi vengono assegnati ai programmi fedeltà e ai livelli di fedeltà. |
| Impostare i gruppi di prezzi (prerequisito)               | I gruppi di prezzi sono utilizzati per creare e gestire i prezzi e gli sconti per i prodotti. Impostare i gruppi di prezzi che includono gli sconti applicabili ai programmi fedeltà. | I gruppi di prezzi vengono assegnati ai programmi fedeltà e ai relativi livelli. |
| Impostare i canali (prerequisito)                   | I canali di commercio sono i punti vendita che partecipano ai programmi fedeltà, ad esempio un punto vendita fisico, un negozio online o un servizio clienti. È necessario impostare i canali prima di poter assegnare i relativi programmi fedeltà. | Assegnare i canali a un programma fedeltà se il canale partecipa al programma fedeltà. |
| Impostare il metodo di pagamento del programma fedeltà (prerequisito) | Per garantire che i punti fedeltà possano essere riscattati in qualsiasi canale, come punti vendita fisici, punti vendita online o call center, è necessario configurare l'intervallo di contenito per le carte fedeltà nella pagina **Numeri di carta**. | Impostare un metodo di pagamento del tipo carta fedeltà, quindi assegnare il metodo di pagamento del programma fedeltà ai canali che partecipano al programma fedeltà. |
| Impostare gli intervalli di date                            | Gli intervalli di date forniscono un metodo flessibile di impostazione dell'intervallo di tempo che si applica ai livelli di fedeltà. Utilizzare gli intervalli di date per specificare il tempo di permanenza di un cliente in un livello o il tempo previsto per il completamento di un'attività e passare al livello successivo. | Gli intervalli di date sono applicabili solo se si utilizzano i livelli nei programmi fedeltà. Selezionare l'intervallo di date applicabile ai livelli di programma e anche gli intervalli di date che si applicano alle regole del livello programma. |
| Impostare i punti premio                             | I punti premio sono i tipi di premio che si offrono ai clienti. I punti premio possono essere riscattabili o non riscattabili. I punti premio riscattabili possono essere scambiati con i prodotti. I punti premio non riscattabili vengono utilizzati a scopo di tracciabilità o per far passare un cliente al livello successivo in un programma fedeltà. | Ci si riferisce ai punti premio nelle regole di livello e vengono utilizzati per qualificare un cliente per un livello specifico. Ci si riferisce ai punti premio anche negli schemi del programma fedeltà nelle regole di acquisizione e di rimborso. Nelle regole di acquisizione, vengono specificati i premi che un cliente può ottenere per un'attività specifica. Nelle regole di rimborso, specificare il premio che il cliente può riscattare. |
| Impostare programmi fedeltà                          | I programmi fedeltà sono l'entità principale del programma fedeltà offerto. Ogni programma fedeltà può anche avere livelli di fedeltà assegnati. Gli sconti e i gruppi di prezzi vengono assegnati ai programmi fedeltà in base al programma o al livello. | Creare gli schemi di fedeltà per i programmi fedeltà. Assegnare le carte fedeltà ai programmi fedeltà, sarà quindi possibile assegnarle a un cliente. I canali partecipano ai programmi fedeltà assegnati agli schemi del programma fedeltà. Tutti i clienti che possiedono una carta fedeltà possono partecipare ai programmi fedeltà assegnati alla carta. |
| Impostare i livelli di fedeltà e le regole livello              | I livelli di fedeltà sono livelli facoltativi che è possibile definire per i programmi fedeltà. È possibile impostare gli sconti di base e i premi per tutti i clienti che partecipano al programma fedeltà ed è possibile impostare sconti aggiuntivi e premi per i clienti che raggiungono i diversi livelli del programma. Per ciascun livello di fedeltà definito, è possibile impostare le regole che qualificano un cliente per quel livello. È inoltre possibile definire per quanto tempo i clienti possono rimanere nel livello raggiunto. | I livelli di fedeltà e le regole di livello fedeltà vengono definiti nei programmi fedeltà. Se non vengono definiti i livelli di fedeltà, tutti i clienti che partecipano al programma fedeltà sono qualificati per gli sconti assegnati al gruppo di prezzi del programma fedeltà. Se si definiscono i livelli fedeltà, è possibile impostare le regole di acquisizione e di rimborso per i livelli fedeltà nello schema del programma fedeltà. |
| Impostare gli schemi programma fedeltà                           | Gli schemi del programma fedeltà specificano le regole di acquisizione e le regole di estinzione applicabili a un programma fedeltà selezionato. Assegnare i canali a uno schema del programma fedeltà per identificare quale programma fedeltà, regole di acquisizione e regole di rimborso si applicano a un punto vendita. | Uno schema del programma fedeltà viene assegnato a un programma fedeltà e ai canali. È possibile assegnare molti schemi del programma fedeltà allo stesso programma fedeltà ed è possibile assegnare molti schemi del programma fedeltà a più canali. |
| Impostare carte fedeltà                             | Una carta fedeltà autorizza il possessore a partecipare ai programmi fedeltà assegnati alla carta. Le carte fedeltà possono essere emesse in anonimato oppure possono essere assegnate a un cliente specifico. È possibile visualizzare le transazioni del programma fedeltà per una carta specifica ed è possibile visualizzare un riepilogo dei punti fedeltà che sono stati accumulati nella carta. È possibile emettere le carte fedeltà dai canali. È inoltre possibile rettificare manualmente una carta fedeltà per aggiornare il cliente a un altro livello, per aggiungere punti fedeltà o per trasferire il saldo dei punti fedeltà da una carta a un'altra. | Assegnare i programmi fedeltà a una carta fedeltà. |

## <a name="loyalty-processes"></a>Processi fedeltà

Nella seguente tabella sono descritti i processi che devono essere eseguiti per inviare le configurazioni e i dati del programma fedeltà agli archivi e per recuperare le transazioni dei programmi fedeltà dagli archivi.

| Nome processo                         | Descrizione | Nome pagina |
|--------------------------------------|-------------|-----------|
| 1050 (informazioni fedeltà)           | Eseguire questo processo per inviare i dati di configurazione fedeltà da Commerce ai punti vendita. È una buona idea programmare l'esecuzione del processo di frequente, in modo che i dati del programma fedeltà siano trasmessi a tutti gli archivi. | Programmazione della distribuzione |
| Elabora programmi fedeltà              | Eseguire questo processo per associare gli schemi del programma fedeltà ai canali a cui lo schema del programma fedeltà è assegnato. Questo processo può essere programmato per l'esecuzione come processo batch. È necessario eseguire questo processo se si modificano i dati di configurazione del programma fedeltà, ad esempio schemi del programma fedeltà, programmi fedeltà o i punti di ricompensa del programma fedeltà. | Elabora programmi fedeltà |
| Registra punti fedeltà ottenuti in batch | Eseguire questo processo per aggiornare le carte fedeltà in modo che includano le transazioni elaborate offline. Questo processo si applica solo se la casella di controllo **Registra punti ottenuti in batch** è selezionata nella pagina **Parametri condivisi di commercio**, in modo che le ricompense possano essere guadagnate offline. | Registra punti fedeltà ottenuti in batch |
| Aggiorna livelli carta fedeltà            | Eseguire questo processo per valutare l'attività di acquisizione del cliente rispetto alle regole di livello per un programma fedeltà e aggiornare lo stato del livello del cliente. Questo processo è necessario solo se si modificano le regole di livello nei programmi fedeltà e si desidera applicare le regole aggiornate con effetto retroattivo alle carte fedeltà già emesse. Questo processo può essere eseguito come processo batch o per le carte singole. | Aggiorna livelli carta fedeltà |

## <a name="loyalty-capabilities"></a>Capacità di fedeltà

- Utilizzando i gruppi di prezzi associati al programma fedeltà e ai livelli fedeltà, i rivenditori possono creare facilmente prezzi speciali e sconti per i membri del programma fedeltà.

- Nell'ambito di uno schema del programma fedeltà i rivenditori potevano creare regole di ricavo e rimborso differenti per livello per distinguere i premi dei clienti nei diversi livelli. I rivenditori possono anche includere "rapporti" nell'ambito delle regole di ricavo e rimborso in modo che un determinato gruppo di clienti possa essere parte dei livelli esistenti, ma essere tuttavia ricompensato diversamente. In tal modo si evita la necessità di creare livelli aggiuntivi.
    
    > [!NOTE]
    > Le regole dei ricavi nello schema del programma fedeltà sono aggiuntive. Ad esempio, se si crea una regola per ricompensare un membro di livello gold con 10 punti per ogni dollaro statunitense e si crea anche una regola per un cliente con un rapporto "veterano" per ricompensarlo con 5 punti per ogni dollaro statunitense, un veterano che è anche membro del livello gold guadagnerebbe 15 punti per 1 dollaro statunitense, poiché il cliente si qualifica per entrambe le righe. Tuttavia, se il cliente veterano non fosse un membro di livello gold, guadagnerebbe 5 punti per ogni dollaro. Per riflettere le modifiche apportate ai canali, eseguire i processi **Elabora programmi fedeltà** e **1050** (informazioni sui programma fedeltà).
    
    ![Ricavi basati sul rapporto](./media/Affiliation-based-earning.png "Ricavi basati sul rapporto")

- I rivenditori fanno spesso prezzi speciali per un determinato gruppo di clienti ai quali non desiderano applicare i programmi fedeltà. Ad esempio, grossisti o dipendenti che ottengono prezzi speciali e nessun punto programma fedeltà. Comunemente, "i rapporti" sono utilizzati per applicare i prezzi speciali a questi gruppi di clienti. Per limitare il guadagno di punti programma fedeltà di determinati gruppi di clienti, il rivenditore può specificare uno o più rapporti nella sezione **Report esclusi** dello schema programma fedeltà. In tal modo, quando i clienti che appartengono ai rapporti esclusi sono membri effettivi del programma fedeltà, non potranno ottenere i punti del programma fedeltà per gli acquisti. Per riflettere le modifiche apportate ai canali, eseguire i processi **Elabora programmi fedeltà** e **1050** (informazioni sui programma fedeltà).

    ![Rapporti esclusi](./media/Excluded-affiliations.png "Rapporti esclusi dai punti del programma fedeltà")
    
- Il punto vendita consente ai rivenditori la flessibilità di utilizzare le carte fedeltà fisiche o di generare automaticamente un numero di carta fedeltà univoco. Per abilitare la generazione automatica di carte fedeltà nei punti vendita, attivare **Genera numero carta fedeltà** nel profilo della funzionalità associato al punto vendita. Per i canali online, i rivenditori possono utilizzare l'API IssueLoyaltyCard per emettere le carte fedeltà ai clienti. I rivenditori possono fornire un numero di carta fedeltà a questa API, che verrà utilizzato per generare la carta fedeltà, o il sistema utilizzerà la sequenza numerica della carta fedeltà in Commerce. Tuttavia, se la sequenza numerica non è presente e il rivenditore non fornisce un numero di carta fedeltà mentre chiama l'API, verrà visualizzato un errore.

    ![Genera carta fedeltà](./media/Generate-loyalty-card.png "Il numero di carta fedeltà verrà generato automaticamente")

- I punti del programma fedeltà guadagnati o rimborsati possono ora essere salvati per ciascuna transazione e ordine cliente rispetto alla riga di vendita, in modo che lo stesso importo possa essere rimborsato o prelevato solo nel caso di resi completi o parziali. Inoltre, avere la visibilità dei punti a livello di riga di vendita garantisce agli utenti dei call center la possibilità di rispondere alle domande dei clienti in merito alla quantità di punti guadagnati o riscattati per ciascuna riga. Prima di questa modifica i punti premio venivano sempre ricalcolati durante i resi, il che generava una quantità diversa dall'originale, se le regole di ricavo o rimborso erano state modificate e inoltre gli utenti dei call center non avevano la visibilità sulla suddivisione dei punti. I punti possono essere visualizzati nel modulo **Transazioni carte** per ogni carta fedeltà. Per attivare questa funzionalità attivare la configurazione **Registra punti fedeltà per riga di vendita** nella scheda **Parametri condivisi di commercio** \> **Generale**.

    > [!NOTE]
    > Si consiglia vivamente di attivare questa funzionalità per garantire, nel caso di resi, la possibilità di rimborsare o togliere l'importo corretto di punti al cliente.

- I rivenditori possono ora definire il periodo della distribuzione degli incentivi per ogni punto premio. La configurazione di un periodo di distribuzione definirà la durata dalla data in cui vengono guadagnati, dopo la quale i punti premio diventerebbero disponibili ai clienti. I punti non distribuiti possono essere visualizzati nella colonna **Punti non distribuiti** della pagina **Carte fedeltà**. Quando i clienti restituiscono alcuni articoli per i quali sono stati guadagnati i punti fedeltà, per impostazione predefinita il sistema dedurrà prima i punti non investiti e poi detrarrà l'eventuale saldo dai punti disponibili. Tuttavia, è possibile configurare di detrarre solo i punti disponibili invece di detrarli dai punti non investiti.

Inoltre, i rivenditori possono definire il limite massimo di punti premio del programma fedeltà per carta fedeltà. Questo campo può essere utilizzato per ridurre l'impatto delle frodi del programma fedeltà. Quando la quantità massima di punti premio è stata raggiunta, l'utente non può ottenere altri punti. Il rivenditore può decidere di bloccare tali schede finché non avrà verificato l'assenza di una potenziale frode. Se il rivenditore determina la frode, il rivenditore può bloccare la carta fedeltà per il cliente e contrassegnare il cliente come bloccato. A questo scopo, impostare la proprietà **Blocca cliente per iscrizione al programma fedeltà** su **Sì** in **Tutti i clienti** nella scheda dettaglio **Commerce**. I clienti bloccati non potranno ricevere una carta fedeltà su alcuno dei canali.

   ![Distribuzione incentivi e quantità massima di punti premio](./media/Vesting-and-maximum-reward-points.png "Definizione della distribuzione incentivi e della quantità massima di punti premio")

- I rapporti vengono utilizzati per immettere prezzi e sconti speciali, ma vi sono alcuni rapporti che i rivenditori non desiderano mostrare ai propri clienti. Ad esempio, un rapporto denominato "Cliente con spesa elevata" potrebbe non essere accolto favorevolmente da alcuni . Inoltre, sono disponibili alcuni rapporti che non dovrebbero essere gestiti nel punto vendita, ad esempio, i dipendenti, in quanto non si desidera che i cassieri decidano chi è un dipendente e quindi offrano sconti in base al dipendente. I rivenditori possono ora selezionare i rapporti che devono essere nascosti nei canali. I rapporti contrassegnati come **Nascondi in canali** non possono essere visualizzati, aggiunti né rimossi nel POS. Tuttavia, i prezzi e gli sconti associati al rapporto verranno tuttavia applicati ai prodotti.

    ![Nascondi rapporti](./media/Hide-affiliations.png "Nascondere rapporti nei canali")
    
- Gli utenti dei call center possono ora cercare più facilmente un cliente utilizzando le informazioni sulla carta fedeltà e visualizzare le pagine della carta fedeltà e delle transazioni della carta fedeltà del cliente dalla pagina **Servizio clienti**.

    ![Servizio clienti](./media/Customer-service.png "Trovare informazioni sul programma fedeltà per il cliente")
    
- Se una carta fedeltà è compromessa, una scheda sostitutiva deve essere generata e i punti esistenti trasferiti nella nuova carta. Il flusso della scheda sostitutiva è stato semplificato in questa versione. Inoltre, i clienti possono donare alcuni o tutti i punti del programma fedeltà ad amici e alla famiglia. Quando i punti vengono trasferiti, voci di rettifica dei punti vengono create per ogni carta fedeltà. La carta sostitutiva e la funzionalità per trasferire il saldo possono essere accessibili dalla pagina **Carte fedeltà**.

    ![Sostituisci e trasferisci punti](./media/Replace-and-transfer-points.png "Sostituire la carta fedeltà o trasferire il saldo")
    
- I rivenditori possono voler acquisire l'efficacia di un canale specifico per registrare i clienti in un programma fedeltà. L'origine di iscrizione per le carte fedeltà viene ora salvata in modo che i rivenditori possano eseguire report su questi dati. L'origine delle iscrizioni è catturata automaticamente per tutte le carte fedeltà emesse da MPOS/CPOS o dai canali di commercio elettronico. Per le carte fedeltà emesse dall'applicazione di back office, l'utente dei call center può selezionare un canale appropriato.
- Nella versioni precedenti i rivenditori potevano utilizzare MPOS/CPOS per riscattare i punti programma fedeltà per i clienti in un punto vendita. Tuttavia, in quelle versioni, dato che il saldo del programma fedeltà appare sotto forma di punti programma fedeltà, il cassiere non poteva visualizzare l'importo del valore della valuta che poteva essere applicato alla transazione in corso. Il cassiere doveva effettuare la conversione da punti a valuta prima di pagare in base ai punti del programma fedeltà. Nella versione esistente, dopo l'aggiunta delle righe alla transazione, il cassiere può visualizzare l'importo che i punti del programma fedeltà possono coprire per la transazione in corso, facilitando l'applicazione di alcuni o tutti punti del programma fedeltà alla transazione. Inoltre, il cassiere può vedere i punti che scadono nei 30 giorni successivi, in modo da potere eseguire l'upselling o il cross-selling per motivare il cliente a spendere i punti in scadenza in quella transazione.

    ![Punti coperti dal saldo del programma fedeltà](./media/Points-covered-by-loyalty-balance.png "Mostrare il saldo coperto dai punti del programma fedeltà")

    ![Punti in scadenza](./media/Expiring-points.png "Visualizzare i punti in scadenza")

- Nella versione 8.1.3, l'opzione "pagamento con programma di fedeltà" è abilitata nel canale servizio clienti. Per abilitare questa opzione, creare un tipo di metodo di pagamento della carta fedeltà e associarlo al servizio clienti. 

    > [!NOTE]
    > Poiché i pagamenti del programma fedeltà sono impostati come pagamenti con carta, sarà necessario selezionare una carta nella pagina **Impostazione carta**. 

    ![Impostazione della carta fedeltà](./media/LoyaltyCardSetup.png "Impostazione della carta fedeltà")

    Dopo tale impostazione, i clienti possono riscattare i punti fedeltà nel servizio clienti. Inoltre, stiamo ottimizzando l'esperienza utente per visualizzare l'importo coperto dai punti fedeltà affinché gli utenti del servizio clienti non debbano accedere a un'altra schermata per visualizzare il saldo del programma fedeltà.

- Molti rivenditori assegnano punti fedeltà esclusivamente in base alle transazioni di vendita, ma i rivenditori più attenti ai clienti intendono ricompensarli per qualsiasi attività di engagement con il loro brand. Ad esempio, vogliono ricompensarli per la partecipazione a un sondaggio online, la visita a un punto vendita, l'aver messo mi piace ai rivenditori su Facebook o aver twittato sul rivenditore. A tale scopo, il rivenditore può definire un numero qualsiasi di "altri tipi di attività" e le regole di acquisizione corrispondenti per queste attività. Esiste inoltre l'API Commerce Scale Unit esposta, "PostNonTransactionalActivityLoyaltyPoints", che può essere chiamata quando viene identificata un'attività che deve ricompensare il cliente con punti fedeltà. Questa API comporta l'ID carta fedeltà, l'ID canale e l'ID altro tipo di attività, in modo da poter individuare il cliente che deve essere ricompensato e identificare la regola di acquisizione dell'attività. 

    L'ottenimento di punti fedeltà per attività non relative a transazioni include in genere due fasi principali:

    - La realizzazione di un'attività che deve essere ricompensata.
    - L'attribuzione dei punti appropriati.

    La prima fase è esterna a Commerce, ad esempio l'invio di tweet in relazione al brand o il gradimento del brand su Facebook. Dopo il riconoscimento di tale attività, i rivenditori possono chiamare l'API Commerce Scale Unit menzionata precedentemente e attribuire punti fedeltà in tempo reale. In tali scenari, non è necessario un'operazione di verifica in quanto un'attività è stata eseguita e i punti corrispondenti devono essere attribuiti. Tuttavia, vi sono scenari in cui il rivenditore intende esaminare i record prima di attribuire i punti. Ad esempio, il rivenditore ha organizzato un workshop nel punto vendita al quale i clienti si iscrivono sul sito Web e-commerce o tramite un'applicazione di registrazione. Tuttavia, solo i clienti effettivamente presenti otterranno punti fedeltà. Per tali scenari, nella versione 10.0, abbiamo introdotto un'entità di dati denominata **Righe altro tipo di attività fedeltà vendita al dettaglio**. Questa entità consente ai rivenditori di utilizzare il Framework di importazione/esportazione dati o l'API OData per registrare le attività che devono attribuire punti fedeltà ai clienti. L'entità di dati archivia le attività in un giornale denominato **Righe programma fedeltà per altre attività**, che può essere utilizzato per fini di verifica e modifica. Dopo che i dati sono stati esaminati, l'utente IT può registrare manualmente le righe dell'attività o eseguire un processo denominato **Elaborare altro tipo di attività per righe programma fedeltà**, che registrerà tutte le righe delle attività non registrate e attribuirà i punti ai clienti in base alle regole di acquisizione. Nello scenario descritto sopra, l'applicazione di registrazione all'evento chiamerebbe l'API OData per inviare le informazioni relative ai clienti a Commerce. Tuttavia, l'utente IT può registrare le righe attività solo per i clienti effettivamente presenti al workshop ed eliminare le righe attività relative agli altri clienti. 

    > [!NOTE]
    > Attualmente, il sistema forza gli utenti a impostare una sequenza numerica per "altri tipi di attività", ma ciò non sarà necessario nelle versioni future. Per impostare una sequenza numerica, andare a **Parametri condivisi di commercio** \> **Sequenze numeriche** e selezionare una sequenza numerica per **ID altro tipo di attività fedeltà**.

- Per fornire un servizio clienti ottimale e risolvere efficacemente le query dei clienti, è importante per i cassieri avere accesso al profilo completo di ogni cliente. Nella versione 10.0, i cassieri potranno visualizzare i dettagli dello storico del programma fedeltà insieme al programma fedeltà e ad altre informazioni nel POS.
- La spedizione gratuita o scontata è uno dei fattori che motiva particolarmente i clienti ad acquistare online. Per consentire ai rivenditori di impostare promozioni di spedizione, nella versione 10.0 è stato introdotto un nuovo tipo di promozione denominata "Sconto di soglia spedizione", in cui il rivenditore può definire le soglie, che una volta raggiunte, qualificheranno i clienti per la spedizione scontata o gratuita. Ad esempio, spendere $35 per una "spedizione in due giorni" gratuita per tutti i clienti del programma di fedeltà. Questa funzionalità utilizza la nuova funzione di addebito automatico avanzato. Consultare la [documentazione sugli addebiti automatici avanzati](https://docs.microsoft.com/dynamics365/unified-operations/retail/omni-auto-charges). Questi addebiti automatici avanzati devono essere abilitati affinché la promozione di spedizione funzioni. Per farlo, attivare "Utilizza spese automatiche avanzate" nella scheda **Ordini cliente** della pagina **Parametri di commercio**. Inoltre, poiché un rivenditore può impostare più tipi di spese, ad esempio gestione o installazione, il rivenditore deve specificare quali spese sono considerate spese di spedizione. Gli sconti di spedizione sono applicati solo alle spese di spedizione. Per specificare le spese come spese di spedizione, passare al modulo **Codici spese** in **Retail e Commerce** \> **Vendita al dettaglio e commercio IT** \> **Impostazione canale** \> **Spese** e selezionare la casella di controllo "Spese di spedizione" per le spese desiderate. A questo punto accedere al modulo **Sconto di soglia spedizione** e impostare lo sconto.

    Come gli sconti prodotto, questo sconto dispone di tutte le funzionalità di sconto standard esistenti, come consentire al rivenditore di limitare gli sconti con coupon di modo che solo i clienti con coupon possano usufruire di tali sconti. Inoltre, tali sconti utilizzano la funzionalità Gruppi di prezzi per determinarne l'idoneità di tali sconti. Ad esempio, il rivenditore può scegliere di rendere accessibili queste promozioni solo nei canali online e/o attraverso canali per determinati gruppi di clienti ad esempio i clienti del programma fedeltà. Quando le righe di ordine con la modalità di consegna specificata soddisfano la soglia definita, lo sconto di spedizione viene applicato e riduce le spese di spedizione in base allo sconto impostato. 

    > [!NOTE]
    > A differenza di altri sconti periodici come sconti quantità, semplici, gamma e di soglia, lo sconto di spedizione non crea righe di sconto, ma piuttosto modifica le spese di spedizione direttamente e aggiunge il nome dello sconto alla descrizione delle spese.


[!INCLUDE[footer-include](../includes/footer-banner.md)]