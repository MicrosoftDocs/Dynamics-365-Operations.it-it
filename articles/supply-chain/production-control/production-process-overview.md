---
title: Panoramica del processo di produzione
description: Questo argomento fornisce una panoramica dei processi di produzione. Descrive le varie fasi degli ordini di produzione, degli ordini batch e dei kanban, dalla creazione dell'ordine alla chiusura del periodo finanziario.
author: cvocph
manager: tfehr
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, Kanban, ProdTable, ProdTableOverview, EcoResProductDiscreteManufacturingWorkspace, KanbanPrepareProductForLeanWorkspace, EcoResProductProcessManufacturingWorkspace, OpResLifecycleManagementWorkspace, ProdParmCostEstimation, ProdParmRelease, ProdSchedule, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19832
ms.assetid: 0e83c7ea-feba-4ed6-8717-8b48a3b8804a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a9d6893531ec4386ea7c6101aa9368019e2a0946
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826168"
---
# <a name="production-process-overview"></a>Panoramica del processo di produzione

[!include [banner](../includes/banner.md)]

Questo argomento fornisce una panoramica dei processi di produzione. Descrive le varie fasi degli ordini di produzione, degli ordini batch e dei kanban, dalla creazione dell'ordine alla chiusura del periodo finanziario. 

La produzione degli articoli, processo talvolta detto anche ciclo di vita della produzione, segue passaggi specifici necessari per completare la realizzazione di un articolo. Il ciclo di vita inizia alla creazione dell'ordine di produzione, di un ordine batch o di un processo kanban. Termina con un articolo completato che è pronto per un cliente o un'altra fase di produzione. Ogni fase del ciclo di vita richiede diversi tipi di informazioni per il completamento del processo. L'ordine di produzione, l'ordine batch o il processo kanban riflette il completamento di ogni passaggio, mostrando una modifica nello stato della produzione. I diversi tipi di prodotti richiedono processi di produzione diversi.  

Il modulo **Controllo produzione** è collegato ad altri moduli, ad esempio **Gestione informazioni sul prodotto**, **Gestione articoli**, **Contabilità generale**, **Gestione magazzino**, **Contabilità progetti**  e **Amministrazione organizzazione**. Grazie a tale integrazione, viene garantito il supporto del flusso di informazioni necessario per completare la produzione di un articolo finito.  

Il processo di produzione in genere è influenzato dalla contabilità industriale e dai metodi di valutazione del magazzino scelti per un processo di produzione specifico. Supply Chain Management supporta sia i metodi di costo effettivo (\[FIFO\], \[LIFO\], media mobile e media ponderata periodica) che i metodi di costo standard. La produzione snella è implementata in base al principio di determinazione costi di tipo backflush.  

La scelta dei metodi di misurazione dei costi consente inoltre di definire i requisiti per le dichiarazione sul consumo di materiale e risorse durante il processo di produzione. In genere, i metodi di costo effettivo necessitano di dichiarazioni accurate a livello di processo, mentre i metodi di determinazione costi periodici consentono una dichiarazione meno granulare del consumo di materiali e risorse.

## <a name="mixed-mode-manufacturing"></a>Produzione in modalità mista
Le topologie di produzione e i prodotti diversi richiedono l'applicazione di tipi di ordine diversi. Supply Chain Management può applicare i diversi tipi di ordine in modalità mista. In altre parole, tutti i tipi di ordine possono verificarsi durante il processo di produzione end-to-end di un prodotto finito.

-   **Ordine di produzione**: classico tipo di ordine per realizzare un prodotto o una variante prodotto specifico in una determinata quantità in una data specifica. Gli ordini di produzione si basano sulle distinte base (DBA) e sui cicli di lavorazione.
-   **Ordine batch**: il tipo di ordine viene utilizzato per settori di trasformazione e processi discreti in cui la conversione di produzione è basata su una formula o in cui co-prodotti e sottoprodotti possono essere prodotti finiti, in aggiunta o in sostituzione del prodotto principale. Gli ordini batch utilizzano DBA e cicli di lavorazione di tipo **Formula**.
-   **Kanban**: i processi kanban vengono utilizzati per segnalare i processi di produzione snella ripetitivi basati su flussi di produzione, le regole kanban e DBA.
-   **Progetto**: un progetto di produzione combina prodotti e servizi con una programmazione e un budget specifici. La parte di produzione di un progetto può essere consegnata tramite uno qualsiasi degli altri tipi di ordine.

## <a name="manufacturing-principles"></a>Principi di produzione
Per selezionare il principio di produzione meglio applicabile a un prodotto specifico e al mercato correlato, è necessario considerare i requisiti di produzione e logistica, nonché le aspettative cliente sui lead time di consegna.

-   **Produzione per scorte**: questo è il principio classico di produzione, in cui i prodotti sono realizzati per scorte, in base a un ricarico scorte previste o minime (nel secondo caso il calcolo viene fatto in genere in base alla previsione o al consumo storico).
-   **Produzione per ordine**: i prodotti standard vengono realizzato o completati in base all'ordine. Sebbene la pre-produzione possa essere effettuata tramite il principio di produzione per scorte, i passaggi costosi della catena di valore o i passaggi che creano le varianti, vengono avviati da un ordine cliente o da un ordine di trasferimento.
-   **Configurazione su ordine**: come per il principio di produzione per ordine, le operazioni finali della catena di valore vengono effettuate in base all'ordine. La variante prodotto effettiva realizzata non è predefinita, ma viene creata al momento della registrazione ordine, in base al modello di configurazione del prodotto di vendita. Il principio di configurazione all'ordine richiede un determinato livello di unificazione dei processi per una riga di prodotto specificata.
-   **Progettazione su ordine**: i processi di progettazione su ordine sono in genere utilizzati da un progetto e iniziano con la fase di progettazione. Durante la fase di progettazione, i prodotti effettivi che devono soddisfano l'ordine vengono progettati e descritti. Ordini di produzione, ordini batch o processi kanban possono quindi essere creati per realizzare i prodotti.

## <a name="overview-of-the-production-life-cycle"></a>Panoramica del ciclo di produzione
Le seguenti operazioni nel ciclo di vita della produzione possono verificarsi per tutti i tipi di ordine di produzione in modalità mista. Tuttavia, non tutti sono rappresentati come stato dell'ordine esplicito.

1.  **Creato**: è possibile creare un ordine di produzione, un ordine batch o un processo kanban manualmente o è possibile configurare il sistema per generarli in base a diversi segnali della domanda. La pianificazione generale crea ordini di produzione, ordini batch o processi kanban consolidando gli ordini pianificati. Altri segnali della domanda sono ordini cliente o segnali di fornitura sottoposti a pegging da altri ordini di produzione o processi kanban. Per i kanban a quantità fissa, i segnali della domanda vengono generati quando i kanban vengono registrati come vuoti.
2.  **Stimato**: è possibile calcolare le stime per il consumo di materiali e risorse. La stima genera operazioni di magazzino per le materie prime con stato **In ordinazione**. Le entrate dei prodotti principali, co-prodotti e sottoprodotti sono generate quando gli ordini di produzione o gli ordini batch vengono stimati. Se la DBA contiene le righe di tipo **Fornitura sottoposta a pegging**, gli ordini fornitore per i materiali o servizi in conto lavoro vengono generati e sottposti a pegging nell'ordine di produzione o ordine batch. Gli articoli o gli ordini vengono prenotati in base alla strategia di prenotazione dell'ordine di produzione e il prezzo dei prodotti finiti viene calcolato in base alle impostazioni dei parametri.
3.  **Programmato**: è possibile programmare la produzione in base alle operazioni, ai singoli processi o a entrambi.
    -   **Programmazione operazioni**: questo metodo di programmazione fornisce un piano approssimativo a lungo termine. questo metodo di programmazione consente di definire un piano approssimativo a lungo termine e pertanto di assegnare date di inizio e fine agli ordini di produzione. Se tali ordini sono collegati a operazioni del ciclo di lavorazione, sarà possibile assegnarli a gruppi di centri di costo.
    -   **Programmazione processo**: questo metodo di programmazione fornisce un piano dettagliato. Ciascuna operazione viene suddivisa in singoli processi con date, orari e risorse operative assegnate. Se si utilizza la capacità limitata, i processi vengono assegnati alle risorse operative in base alla disponibilità. È possibile visualizzare e modificare la programmazione in un diagramma di Gantt.
    -   **Programmazione kanban**: i processi kanban vengono programmati nella bacheca di programmazione kanban oppure automaticamente in base alla configurazione di pianificazione automatica delle regole kanban.

4.  **Rilasciato**: è possibile rilasciare un ordine di produzione o batch quando la programmazione è stata completata e il materiale è disponibile per essere prelevato o preparato. Il controllo della disponibilità del materiale consente al supervisore dello shop floor di valutare se per gli ordini di produzione o gli ordini batch il materiale è disponibile. È inoltre possibile stampare i documenti dell'ordine di produzione, ad esempio distinte di prelievo, scheda processo, scheda del ciclo di lavorazione e processo del ciclo di lavorazione. Quando l'ordine di produzione viene rilasciato, lo stato dell'ordine cambia a indicare che la produzione può iniziare. Quando viene utilizzata la gestione magazzino, il rilascio dell'ordine di produzione o dell'ordine batch rilascia le righe DBA di produzione alla gestione magazzino. Le ondata di magazzino e il lavoro del magazzino vengono generati in base all'impostazione di magazzino.
5.  **Preparat**/**Prelevato**: se tutti i materiali e risorse sono stati organizzati nell'ubicazione di produzione, le righe DBA di produzione o le righe kanban vengono aggiornate allo stato **Prelevato**. Gli ordini di fornitura sottoposti a pegging e il lavoro di magazzino relativo vengono in genere completati in questa fase. Le schede kanban o le schede processo necessarie per dichiarare lo stato di avanzamento della produzione devono essere assegnate e stampate.
6.  **Avviato**: se un ordine di produzione, un ordine batch o un kanban viene avviato, è possibile dichiarare il consumo di materiale e di risorse a fronte dell'ordine. Il sistema può essere configurato per registrare automaticamente il consumo dei materiali e dei risorse allocati all'ordine quando quest'ultimo viene avviato. Questa allocazione è definita preflush, foreflush o consumo automatico. È possibile allocare manualmente i materiali agli ordini di produzione o agli ordini batch creando giornali di registrazione per distinte di prelievo aggiuntivi. È inoltre possibile allocare manualmente all'ordine i costi della manodopera e di altro tipo relativi al ciclo di lavorazione, Se si utilizza la programmazione delle operazioni, tali costi possono essere allocati mediante la creazione di un giornale di registrazione delle schede cicli di lavorazione, mentre se si utilizza la programmazione dei processi, è possibile allocarli creando un giornale di registrazione delle schede processi. Gli ordini di produzione o gli ordini batch possono essere avviati in batch della quantità finale richiesta. In un ordine di produzione, un ordine batch o un kanban, i processi creati possono essere avviati separatamente e dichiarati tramite i giornali di registrazione, il terminale di esecuzione produzione (terminale MES) o le schede kanban.
7.  Segnala stato processi/**Completato**: utilizzare il terminale MES, i giornali di produzione, le bacheche kanban o le funzionalità di scansione mobile per segnalare lo stato di avanzamento di produzione in base al processo o alla risorsa. Il consumo di materiale e di risorse verrà registrato e lo stato dei processi kanban, degli ordini di produzione e degli ordini batch correlati può essere aggiornato su **Ricevuto** o **Dichiarato finito**. Il lavoro di stoccaggio per il magazzino può essere creato, a seconda della configurazione di magazzino.
8.  **Dichiarato finito** (entrata prodotto): quando un ordine di produzione o un ordine batch viene dichiarato finito, la quantità di prodotti finiti che sono stati completati viene aggiornata in magazzino. Questa quantità include la quantità di co-prodotti e sottoprodotti rilevanti. Se si utilizza la contabilità WIP (Work In Process), viene generato un giornale di registrazione contabile per ridurre i conti WIP e aumentare le scorte dei prodotti finiti. Quando si calcola il costo di un ordine di produzione, viene registrato il costo effettivo della produzione. Se i costi relativi ai materiali e alla manodopera associati alla produzione non sono già stati allocati in un giornale di registrazione o tramite preflush, possono essere allocati automaticamente tramite backflush, L'allocazione tramite backflush include la detrazione successiva di processi di operazioni di magazzino. Se l'ordine di produzione è completo, selezionare la casella di controllo **Processo finale** per modificare lo stato delle rimanenze in **Finito**. In caso contrario, lasciare vuoto tale campo per consentire la dichiarazione di quantità aggiuntive prodotte.
9.  **Valutazione della qualità**: un'entrata prodotti può avviare la creazione di ordini di controllo qualità, a seconda della configurazione dei processi di test e delle regole di qualità che vengono stabilite per i prodotti specifici. Poiché un ordine di controllo qualità può aggiornare lo stato delle scorte o gli attributi batch dei prodotti testati, la valutazione di qualità è un processo obbligatorio in molti settori.
10. **Stoccaggio** e **Spedizione su ordine**: dopo l'entrata prodotti e la valutazione della qualità, il lavoro di stoccaggio facoltativo indirizza i prodotti ricevuti al punto di consumo successivo, a un magazzino di prodotti finiti oppure a una zona di spedizione se sono presenti requisiti di spedizione su ordine.
11. **Finito**: prima che la produzione termini, vengono calcolati i costi effettivi per la quantità prodotta. Tutti i costi stimati in termini di materiali, manodopera e gestione generale vengono annullati e sostituiti con i costi effettivi. Se si seleziona la casella di controllo **Processo finale** quando si esegue il calcolo dei costi, lo stato dell'ordine di produzione viene impostato su **Finito**. Tale stato impedisce che vengano registrati ulteriori costi per un ordine di produzione completato.
12. **Chiusura periodo**: alcuni principi della contabilità industriale, ad esempio media periodica, determinazione costi di tipo backflush, FIFO o LIFO, richiedono attività periodiche per chiudere l'inventario o il periodo finanziario. Prima della chiusura dei periodi il sistema tenta in genere di dichiarare qualsiasi consumo di materiale e risorse, nonché di correzioni delle scorte e di scarto. La dichiarazione viene in genere eseguita utilizzando i giornali di registrazione movimenti scorte o di rettifica. L'obiettivo è quello di valutare le prestazioni economiche di unità operative per periodo. In alcuni casi, quando vengono utilizzati ordini di produzione di lunga durata che coprono i periodi di report finanziari, i giornali di registrazione produzione vengono utilizzati per dichiarare lo stato di avanzamento di produzione e il consumo di risorse entro la fine del periodo.


<a name="additional-resources"></a>Risorse aggiuntive
--------

[Riscontro di produzione](production-feedback.md)

[Panoramica sui modelli di configurazione prodotto](../pim/product-configuration-models.md)

[Panoramica del lean manufacturing](lean-manufacturing-overview.md)



