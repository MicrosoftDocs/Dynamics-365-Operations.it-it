---
title: Pianificazione del budget
description: "Destinatario di laboratorio questo è di immettere una visualizzazione Guida di Microsoft Dynamics 365 per gli aggiornamenti delle funzionalità delle operazioni nell&quot;area soggetta alla pianificazione del budget. Lo scopo dell&quot;esercitazione è quello di illustrare esempio rapido di configurazione del modulo di pianificazione del budget e di mostrare il modo in cui la pianificazione budget può essere completata tramite la configurazione.  Questo laboratorio metterà l&quot;attenzione nei seguenti processi aziendali o attività che consente di creare la gerarchia organizzativa per il processo di pianificazione del budget A e all&quot;attivazione di protezione dell&quot;utente di pianificazione e di configurazione Budget - definendo gli scenari del piano di budget, le colonne del piano di budget, i layout e modelli di Excel - - creando il piano di budget recuperando i numeri effettivi da Contabilità generale - utilizzando le allocazioni per rettificare i dati del documento piano di budget - modificare i dati del documento piano di budget in Excel"
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 81b44aa7af3a05ebc28963f406fab98bfbbb340d
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning"></a>Pianificazione del budget

Destinatario di laboratorio questo è di immettere una visualizzazione Guida di Microsoft Dynamics 365 per gli aggiornamenti delle funzionalità delle operazioni nell'area soggetta alla pianificazione del budget. Lo scopo dell'esercitazione è quello di illustrare esempio rapido di configurazione del modulo di pianificazione del budget e di mostrare il modo in cui la pianificazione budget può essere completata tramite la configurazione.  Questo laboratorio metterà l'attenzione nei seguenti processi aziendali o attività che consente di creare la gerarchia organizzativa per il processo di pianificazione del budget A e all'attivazione di protezione dell'utente di pianificazione e di configurazione Budget - definendo gli scenari del piano di budget, le colonne del piano di budget, i layout e modelli di Excel - - creando il piano di budget recuperando i numeri effettivi da Contabilità generale - utilizzando le allocazioni per rettificare i dati del documento piano di budget - modificare i dati del documento piano di budget in Excel 

<a name="prerequisites"></a>Prerequisiti 
------------------

Per questa esercitazione, sarà necessario accedere a Dynamics 365 per l'ambiente delle operazioni con i dati dimostrativi di Contoso e provisioned come amministratore l'istanza. Non inserire in modalità privata del browser per il segno di laboratorio non da qualsiasi altro conto nel browser e se necessario segno in Dynamics 365 per le credenziali dell'amministratore delle operazioni. Nella firma in Dynamics 365 per le operazioni, ** DEBBA ** controllate "mi di firma" nella casella di controllo. In questo modo viene creato un cookie permanente attualmente necessario per l'applicazione Excel. Se in accesso a Dynamics 365 per le operazioni mediante un browser diverso da dell'IE, quindi verrà chiesto di firma nell'intervallo di App di Excel. Quando si fa clic su "Accedi" nell'applicazione Excel, verrà visualizzata una finestra popup di Internet Explorer e, una volta effettuato l'accesso, è **NECESSARIO** selezionare la casella di controllo "Mantieni l'accesso". Se, quando si fa clic su "Accedi" nell'applicazione Excel, non appare alcuna informazione, è necessario cancellare la memoria cache dei cookie di Internet Explorer.

## <a name="scenario-overview"></a>**Scenario overview**
Julia lavora come responsabile finanziario presso la società Contoso Entertainment Systems in Germania (DEMF). All'avvicinarsi dell'anno fiscale 2016, Julia deve lavorare all'impostazione del budget della società per l'anno successivo. La preparazione del budget viene effettuata come segue:

1.  Julia utilizza gli importi effettivi dell'anno precedente come punto di partenza per creare il budget.
2.  In base ai valori effettivi dell'anno precedente, Julia crea le stime per i 12 mesi dell'anno successivo.
3.  Julia esamina il budget con il responsabile finanziario. Una volta effettuata tale operazione, Julia procede ad apportare le rettifiche necessarie per il piano di budget e finalizza la preparazione del budget.

Numero dello schema di configurazione pianificazione per gli sguardi allo scenario nel seguente modo:

![Schermata di 1](./media/screenshot1-300x152.png)

Julia viene utilizzato il seguente modello Excel per preparare il budget:

[![](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

<a name="exercise-1-configuration"></a>Esercizio 1: configurazione
=========================

## <a name="task-1-create-organizational-hierarchy"></a>** Attività 1: Consente di creare la gerarchia organizzativa **
Poiché tutto il processo di creazione del budget si verifica nel reparto finanziario, Julia deve creare una gerarchia organizzativa molto semplice costituita esclusivamente dal reparto finanziario. 1.1. Spostarsi alle gerarchie organizzative (gerarchie &gt; organizzative di organizzazioni &gt; di Amministrazione organizzazione) e clic su Nuovo pulsante

![Schermata di 3](./media/screenshot3.png) 

1.2. Digitare il nome della gerarchia e quindi fare clic su assegna lo scopo

![[] (Screenshot4. schermata di 4.png /media/screen)](. schermata di 4.png /media/screen) 

1.3. Lo scopo di pianificazione budget selezionato, fare clic clic su Aggiungi e assegna la gerarchia organizzativa appena creato: 

![[] (Screenshot5. schermata di 5.png /media/screen)](. schermata di 5.png /media/screen)

1.4. Ripetere il passaggio precedente per lo scopo organizzativo di sicurezza. Al termine, chiudere il modulo.

![[] (Screenshot6. schermata di 6.png /media/screen)](. schermata di 6.png /media/screen)

1.5. Nel modulo Gerarchie organizzative, fare clic sul pulsante Visualizza. Fare clic su Modifica nella finestra di progettazione della gerarchia e creare una gerarchia facendo clic sul pulsante Inserisci.

![[] (Screenshot7. schermata di 7.png /media/screen)](. schermata di 7.png /media/screen) 

1.6. Selezionare il reparto finanziario per la gerarchia di creazione del budget. 

![[] (Screenshot8. schermata di 8.png /media/screen)](. schermata di 8.png /media/screen)

1.7. Al termine, fare clic sul pulsante Pubblica e chiudi. Selezionare 1/1/2015 come data di validità per la pubblicazione della gerarchia.

![[] (Screenshot9. schermata di 9.png /media/screen)](. schermata di 9.png /media/screen)

## <a name="task-2-configure-user-security"></a>Attività 2: configurare la sicurezza degli utenti
La pianificazione del budget utilizza criteri di sicurezza per configurare l'accesso ai dati dei piani di budget. Julia deve assegnare l'accesso ai piani di budget finanziari a se stessa. 2.1. Passare al contesto della persona giuridica di DEMF:![[] (Screenshot10. schermata di 10.png /media/screen)](. (2.2) 10.png di /media/screen. Spostarsi nella configurazione &gt; del &gt; budget di pianificazione del &gt; budget di pianificazione del budget di impostazione. Nei parametri cataloghi, impostare il valore del modello di sicurezza basato sulle organizzazioni di protezione![[] (Screenshot11. schermata di 11.png /media/screen)](. (2.3) 11.png di /media/screen. Accedere agli utenti degli utenti &gt; di &gt; Amministrazione sistema. Assegnare all'utente amministratore (Julia Funderburk) il ruolo di responsabile budget. ![[] (Screenshot12. schermata di 12.png /media/screen)](. (2.4) 12.png di /media/screen. Il ruolo e scegliere di dialogo di prelievo sono previste le organizzazioni![[] (Screenshot13. schermata di 13.png /media/screen)](. (2.5) 13.png di /media/screen. Selezionare "Concedi accesso a organizzazioni specifiche". Selezionare la gerarchia organizzativa creata nel primo passaggio. Selezionare il nodo di mora e fare clic sulla sovvenzione con il *** il pulsante degli eventuali figli importante! *** * Consente di verificare di aver effettuato il contesto della persona giuridica di DEMF quando eseguire questa attività, ad esempio protezione organizzativa viene applicata per entity* legale![[] (Screenshot14. schermata di 14.png /media/screen)](. schermata di 14.png /media/screen)

## <a name="task-3-create-scenarios"></a>Attività 3: creare scenari
3.1. Spostarsi nella configurazione&gt;&gt; di pianificazione del budget &gt; di pianificazione del budget di BudgetingSetup. Nella pagina Scenari, prendere nota degli scenari che verranno utilizzati in seguito in questo lab: Valori effettivi dell'anno precedente e In budget. *Nota: se si desidera, è possibile creare nuovi scenari per questo esercizio e utilizzare quelli.* ![[] (Screenshot15. schermata di 15.png /media/screen)](. *Note di 15.png di (/media/screen): poiché Julia non vengono utilizzati il processo di approvazione formale per la preparazione di budget, salteremo impostazione delle fasi di flussi di lavoro di fasi, ad esempio in questo useremo laboratorio e la configurazione esistente per il ricevimento automatico consente di approvare il flusso di lavoro. Per informazioni su appendice per il flusso di lavoro configuration.*

## <a name="task-4-create-budget-plan-columns"></a>Attività 4: creare le colonne del piano di budget
Le colonne del piano di budget sono colonne basate sulla liquidità o sulla quantità che possono essere utilizzate nel layout del documento del piano di budget. Nel nostro esempio dobbiamo creare una colonna per Valori effettivi dell'anno precedente e 12 colonne per rappresentare ogni mese dell'anno di riferimento del budget. Le colonne possono essere create semplicemente facendo clic sul pulsante Aggiungi e inserendo i valori o con una guida relativa all'Entità di dati. In questo lab utilizzeremo Entità di dati per inserire i valori. 4.1. Nella pianificazione&gt;&gt; del budget di budget BudgetingSetup &gt; la pagina delle colonne aperte di configurazione pianificazione. Fare clic sul pulsante di Office nell'angolo superiore destro del modulo e selezionare le colonne (non filtrate![) [] (Screenshot16. schermata di 16.png /media/screen)](. (4.2) 16.png di /media/screen. Il sistema aprirà la cartella di lavoro Excel da utilizzare per l'inserimento dei valori. Se necessario, fare clic su consente di modificare e si fida dell'app Approvazioni![[] (Screenshot18. schermata di 18.png /media/screen)](. (18.png) []![Screenshot17 di (/media/screen. schermata di 17.png /media/screen)](. (4.3) 17.png di /media/screen. Avremo necessari più colonne di immettere i valori. Fare clic sulla progettazione nel riquadro di destra per aggiungere colonne nella griglia:![[] (Screenshot19. schermata di 19.png /media/screen)](. (4.4) 19.png di /media/screen. Fare clic su pulsante o a matita accanto a PlanColumns per visualizzare le colonne disponibili da aggiungere alla griglia![[] (Screenshot20. schermata di 20.png /media/screen)](. (4.5) 20.png di /media/screen. Fare doppio clic su ciascun campo disponibile per aggiungerli ai campi selezionati e fare clic sull'aggiornamento![[] (Screenshot21. schermata di 21.png /media/screen)](. (4.6) 21.png di /media/screen. Nella tabella Excel, aggiungere tutte le colonne da creare. Utilizzare la funzionalità di compilazione automatica in Excel per aggiungere le righe rapidamente. Verificare che le righe da aggiungere come parte della tabella (quando si utilizza il rollup verticale, dovrebbe essere possibile visualizzare le intestazioni di colonna nella parte superiore della griglia![) [] (Screenshot22. schermata di 22.png /media/screen)](. (4.7) 22.png di /media/screen. Tornare a Dynamics 365 per le operazioni e aggiornare la pagina. I valori verranno pubblicati in Dynamics 365 per le operazioni. ![[] (Screenshot23. schermata di 23.png /media/screen)](. schermata di 23.png /media/screen)

## <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>Attività 5: creare modelli e layout del documento del piano di budget
Il layout determina l'aspetto della griglia delle righe del documento del piano di budget quando l'utente apre il suddetto documento. È inoltre possibile passare al layout per il documento del piano di budget per visualizzare gli stessi dati in angolazioni diverse. Quindi, dopo aver creato le colonne definite da utilizzare con il documento del piano di budget, Julia deve creare un layout del documento del piano di budget, il cui aspetto sarà simile alla tabella Excel che utilizza per creare i dati di budget (vedere la sezione Panoramica dello scenario di questo lab) 5.1. Nella&gt;&gt; configurazione di pianificazione del &gt; budget di pianificazione del budget di BudgetingSetup aprire la pagina dei layout. Creare un nuovo layout per la voce Budget mensile:

-   Selezionare il set di dimensioni MA+BU per includere i conti principali e le Business Unit al layout.
-   Elencare tutte le colonne del piano di budget create nel passaggio precedente nella sezione Elementi. Rendere modificabili tutti i valori effettivi dell'anno precedente.
-   Fare clic sul pulsante Descrizioni per selezionare le dimensioni finanziarie per cui visualizzare le descrizioni nella griglia.

![[] (Screenshot24. schermata di 24.png /media/screen)](. /media/screen ha sparato) 24.png base alla definizione del layout del piano di budget possiamo creare un modello Excel da utilizzare come metodo alternativo modificare i dati di budget. Poiché il modello Excel deve corrispondere alla definizione del layout del piano di budget, non sarà possibile modificare il layout del piano di budget dopo la generazione del modello Excel; pertanto, è necessario effettuare questa attività dopo aver definito tutti i componenti del layout. 5.2. Per il layout creato in 5.1. il passaggio modello, è possibile fare &gt; clic genera. Confermare il messaggio di avviso. Per visualizzare il modello, fare &gt; clic su Visualizzazione di modelli. *Note: Verificare i "selezionare Salva come" e selezionare la posizione in cui il modello dovrà essere archiviato per modificarla. Se l'utente seleziona "per" nella finestra di dialogo, senza salvare le modifiche apportate al file non verranno mantenute che il file è closed.* ![[] (Screenshot25. schermata di 25.png /media/screen)](. (5.3) 25.png di /media/screen. &lt; Il passaggio facoltativo&gt; modifica del modello Excel affinché risultare più semplice utilizzare consente di aggiungere le formule totali, i campi di intestazione, formattazione, e così via. salva le modifiche e caricamento del file nel layout del piano di budget facendo clic sul layout &gt; si caricano![[] (Screenshot26. schermata di 26.png /media/screen)](. schermata di 26.png /media/screen)

## <a name="task-6-create-a-budget-planning-process"></a>Attività 6: creare un processo di pianificazione del budget
Julia deve creare e attivare un nuovo processo di pianificazione del budget che combina tutte le impostazioni illustrate in precedenza per iniziare a immettere i piani di budget. Il processo di pianificazione del budget definisce quali organizzazioni di impostazione del budget, flussi di lavoro, layout e modelli verranno utilizzati per la creazione dei piani di budget. 6.1. Accedere al processo &gt; di pianificazione del budget del &gt; budget di pianificazione del &gt; budget di attrezzaggio e di creare un nuovo record.

-   Processo di pianificazione del budget - Impostazione del budget DEMF per l'anno fiscale 2016
-   Ciclo di budget - Anno fiscale 2016
-   Contabilità generale - DEMF
-   Struttura dei conti predefinita - Produzione P&L
-   Gerarchia organizzativa - Selezionare la gerarchia creata all'inizio del lab
-   Flusso di lavoro di pianificazione del budget - Assegnare l'approvazione automatica del flusso di lavoro per il reparto finanziario
-   Nelle regole e nei modelli della fase di pianificazione del budget, per ogni fase di pianificazione del budget del flusso di lavoro selezionare se le funzioni di aggiunta e modifica delle righe sono consentite e il tipo di layout da utilizzare per impostazione predefinita

*Nota: è possibile creare layout di documento aggiuntivi e assegnarli per renderli disponibili nella fase del flusso di lavoro di pianificazione del budget facendo clic sul pulsante Layout alternativi.* ![[] (Screenshot27. schermata di 27.png /media/screen)](. (6.2) 27.png di /media/screen. Le azioni selezionate &gt; attivano per attivare il flusso di lavoro di pianificazione del budget![[] (Screenshot28. schermata di 28.png /media/screen)](. schermata di 28.png /media/screen)

<a name="exercise-2-process-simulation"></a>Esercizio 2: simulazione del processo
==============================

## <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>Attività 7: generare i dati iniziali per il piano di budget da Contabilità generale
7.1. Spostarsi all'&gt; impostazione del budget che &gt; generano il piano di budget dalla contabilità generale. Inserire i parametri del processo periodico e fare clic sul pulsante Genera. ![[] (Screenshot29. schermata di 29.png /media/screen)](. (7.2) 29.png di /media/screen. Spostarsi ai &gt; piani di budget del piano di budget trovare un piano di budget creato dal processo Generare. ![[] (Screenshot30. schermata di 30.png /media/screen)](. (7.3) 30.png di /media/screen. Aprire i dettagli del documento facendo clic sul collegamento ipertestuale Numero di documento. Il piano di budget viene visualizzato come definito nel layout creato durante questo laboratorio![[] (Screenshot31. schermata di 31.png /media/screen)](. schermata di 31.png /media/screen)

## <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>Attività 8: creare il budget dell'anno corrente in base ai valori effettivi dell'anno precedente
I metodi di allocazione possono essere utilizzati nel piano di budget per copiare facilmente le informazioni per i piani di budget da uno scenario all'altro, distribuirle su periodi, allocarle in dimensioni. Utilizzeremo le allocazioni per creare il budget dell'anno corrente dai valori effettivi dell'anno precedente. 8.1. Consente di selezionare tutte le righe della griglia del documento piano di budget e quindi fare clic su assegna il budget![[] (Screenshot32. schermata di 32.png /media/screen)](. (8.2) 32.png di /media/screen. Il metodo di allocazione, la chiave periodo, origine e gli scenari e fare clic su selezionati di destinazione sono previste 

![[] (Screenshot33. schermata di 33.png /media/screen)](. schermata di 33.png /media/screen)

Gli importi effettivi dell'anno precedente verranno copiati nel budget dell'anno corrente e assegnarli ai periodi utilizzando la chiave periodo della curva di vendita. 

![[] (Screenshot34. schermata di 34.png /media/screen)](. schermata di 34.png /media/screen)

## <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>Attività 9: rettificare il documento del piano di budget utilizzando Excel e finalizzare il documento
9.1. Fare clic sul foglio di lavoro dei pulsanti al contenuto del documento aperto in Excel

![[] (Screenshot35. schermata di 35.png /media/screen)](. schermata di 35.png /media/screen)

9.2. All'apertura della cartella di lavoro Excel, rettificare i numeri nel documento del piano di budget e fare clic sul pulsante Pubblicazione.

![[] (Screenshot36. schermata di 36.png /media/screen)](. schermata di 36.png /media/screen)

9.3. Tornare al documento piano di budget in Dynamics 365 per le operazioni. Flusso di lavoro con clic &gt; su Invia per approvare il documento

![[] (Screenshot37. schermata di 37.png /media/screen)](. schermata di 37.png /media/screen) 

Al termine del flusso di lavoro completato, la fase del documento piano di budget viene modificato in approvato. ![[] (Screenshot38. schermata di 38.png /media/screen)](. schermata di 38.png /media/screen)

<a name="appendix"></a>Appendice
========

### <a name="auto-approve-workflow-configuration"></a>Configurazione dell'approvazione automatica del flusso di lavoro

A. I flussi &gt; di lavoro impostazione &gt; budget del budget di pianificazione &gt; del budget di attrezzaggio creare un nuovo flusso di lavoro utilizzando i flussi di lavoro di pianificazione del budget del modello:

![[] (Screenshot39. schermata di 39.png /media/screen)](. schermata di 39.png /media/screen)

Questo flusso di lavoro contiene unicamente un'attività - fase Approntato il piano di budget della transizione 

![[] (Screenshot40. schermata di 40.png /media/screen)](. schermata di 40.png /media/screen) 

Salvare e attivare il flusso di lavoro. 

B. Spostarsi nella configurazione &gt; del &gt; budget di pianificazione del &gt; budget di pianificazione del budget di impostazione. Nella scheda di fasi creare fasi 2 - iniziali e si inviano 

![[] (Screenshot41. schermata di 41.png /media/screen)](. schermata di 41.png /media/screen)

C. Spostarsi nella configurazione &gt; del &gt; budget di pianificazione del &gt; budget di pianificazione del budget di impostazione. Nel punto della scheda di fasi del flusso di lavoro il ricevimento automatico del flusso di lavoro consente di approvare creato nel passaggio A all'apertura di fasi e inviato 

![[] (Screenshot42. schermata di 42.png /media/screen)](. schermata di 42.png /media/screen)  


