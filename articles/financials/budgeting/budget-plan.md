---
title: Pianificazione del budget
description: "L'obiettivo dell'esercitazione è quello di fornire una visualizzazione guidata degli aggiornamenti alle funzionalità di Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition nell'area di pianificazione del budget. Lo scopo dell'esercitazione è quello di illustrare esempio rapido di configurazione del modulo di pianificazione del budget e di mostrare il modo in cui la pianificazione budget può essere completata tramite la configurazione.  Questa esercitazione si concentrerà in modo specifico sui processi o sulle attività seguenti -    - Creazione della gerarchia organizzativa per la pianificazione del budget e configurazione della sicurezza utente   - Definizione di scenari di piano di budget, colonne di piano del budget, layout e modelli di Excel   - Creazione e attivazione del processo di pianificazione del budget   - Creazione dei documenti di piano di budget inserendo i valori effettivi dalla contabilità generale   - Utilizzo delle allocazioni per rettificare i dati dei documenti del piano di budget   - Modifica dei dati dei documenti del piano di budget in Excel"
author: twheeloc
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c6440591f847cbbb6be352270e3629a49d71598e
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="budget-planning"></a>Pianificazione del budget

[!include[banner](../includes/banner.md)]


L'obiettivo dell'esercitazione è quello di fornire una visualizzazione guidata degli aggiornamenti alle funzionalità di Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition nell'area di pianificazione del budget. Lo scopo dell'esercitazione è quello di illustrare esempio rapido di configurazione del modulo di pianificazione del budget e di mostrare il modo in cui la pianificazione budget può essere completata tramite la configurazione.  Questa esercitazione si concentrerà in modo specifico sui processi o sulle attività seguenti -    - Creazione della gerarchia organizzativa per la pianificazione del budget e configurazione della sicurezza utente   - Definizione di scenari di piano di budget, colonne di piano del budget, layout e modelli di Excel   - Creazione e attivazione del processo di pianificazione del budget   - Creazione dei documenti di piano di budget inserendo i valori effettivi dalla contabilità generale   - Utilizzo delle allocazioni per rettificare i dati dei documenti del piano di budget   - Modifica dei dati dei documenti del piano di budget in Excel 

<a name="prerequisites"></a>Prerequisiti 
------------------

Per questa esercitazione sarà necessario accedere all'ambiente Finance and Operations con dati dimostrativi Contoso ed eseguire il provisioning come amministratore sull'istanza. Non utilizzare la modalità privata del browser per questo lab. Se necessario, uscire da qualsiasi altro account nel browser e accedere con le credenziali amministratore di Finance and Operations. Quando si accede a Finance and Operations, è **NECESSARIO** selezionare la casella di controllo "Mantieni l'accesso". In questo modo viene creato un cookie permanente attualmente necessario per l'applicazione Excel. Se si accede a Finance and Operations utilizzando un browser diverso da Internet Explorer, verrà richiesto di accedere all'applicazione Excel. Quando si fa clic su "Accedi" nell'applicazione Excel, verrà visualizzata una finestra popup di Internet Explorer e, una volta effettuato l'accesso, è **NECESSARIO** selezionare la casella di controllo "Mantieni l'accesso". Se, quando si fa clic su "Accedi" nell'applicazione Excel, non appare alcuna informazione, è necessario cancellare la memoria cache dei cookie di Internet Explorer.

## <a name="scenario-overview"></a>**Panoramica dello scenario**
Julia lavora come responsabile finanziario presso la società Contoso Entertainment Systems in Germania (DEMF). All'avvicinarsi dell'anno fiscale 2016, Julia deve lavorare all'impostazione del budget della società per l'anno successivo. La preparazione del budget viene effettuata come segue:

1.  Julia utilizza gli importi effettivi dell'anno precedente come punto di partenza per creare il budget.
2.  In base ai valori effettivi dell'anno precedente, Julia crea le stime per i 12 mesi dell'anno successivo.
3.  Julia esamina il budget con il responsabile finanziario. Una volta effettuata tale operazione, Julia procede ad apportare le rettifiche necessarie per il piano di budget e finalizza la preparazione del budget.

Lo schema di configurazione del piano di budget per lo scenario appare nel seguente modo:

![Scema di configurazione della pianificazione del budget](./media/screenshot1-300x152.png)

Julia utilizza il seguente modello Excel per preparare il budget:

[![Modello di Excel](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

<a name="exercise-1-configuration"></a>Esercizio 1: configurazione
=========================

## <a name="task-1-create-organizational-hierarchy"></a>**Attività 1: creare una gerarchia organizzativa**
Poiché tutto il processo di creazione del budget si verifica nel reparto finanziario, Julia deve creare una gerarchia organizzativa molto semplice costituita esclusivamente dal reparto finanziario. 1.1. Accedere alle gerarchie organizzative (Amministrazione organizzazione &gt; Organizzazioni &gt; Gerarchie organizzative) e fare clic sul pulsante Nuovo

![Gerarchia organizzativa](./media/screenshot3.png) 

1.2. Immettere il nome per la gerarchia organizzativa e fare clic sul pulsante Assegna scopo

[![Nome](./media/screenshot4.png)](./media/screenshot4.png) 

1.3. Selezionare lo scopo di pianificazione del budget, fare clic sul pulsante Aggiungi e assegnare la gerarchia organizzativa appena creata: 

[![Assegna scopo](./media/screenshot5.png)](./media/screenshot5.png)

1.4. Ripetere il passaggio precedente per lo scopo organizzativo di sicurezza. Al termine, chiudere il modulo.

[![Organizzazione di sicurezza](./media/screenshot6.png)](./media/screenshot6.png)

1.5. Nel modulo Gerarchie organizzative, fare clic sul pulsante Visualizza. Fare clic su Modifica nella finestra di progettazione della gerarchia e creare una gerarchia facendo clic sul pulsante Inserisci.

[![Inserisci](./media/screenshot7.png)](./media/screenshot7.png) 

1.6. Selezionare il reparto finanziario per la gerarchia di creazione del budget. 

[![Dati finanziari](./media/screenshot8.png)](./media/screenshot8.png)

1.7. Al termine, fare clic sul pulsante Pubblica e chiudi. Selezionare 1/1/2015 come data di validità per la pubblicazione della gerarchia.

[![Data di validità](./media/screenshot9.png)](./media/screenshot9.png)

## <a name="task-2-configure-user-security"></a>Attività 2: configurare la sicurezza degli utenti
La pianificazione del budget utilizza criteri di sicurezza per configurare l'accesso ai dati dei piani di budget. Julia deve assegnare l'accesso ai piani di budget finanziari a se stessa. 

2.1. Passare al contesto relativo alla persona giuridica DEMF. 


2.2. Accedere a Budget &gt; Impostazioni &gt; Pianificazione del budget &gt; Configurazione di pianificazione del budget. Nella scheda Parametri, impostare il valore del Modello di sicurezza su In base alle organizzazioni di sicurezza 

[![Parametri](./media/screenshot11.png)](./media/screenshot11.png) 

2.3. Accedere ad Amministrazione sistema &gt; Utenti &gt; Utenti. Assegnare all'utente amministratore (Julia Funderburk) il ruolo di responsabile budget. 

[![Responsabile budget](./media/screenshot12.png)](./media/screenshot12.png) 

2.4. Selezionare il ruolo utente e fare clic su Assegna organizzazioni 

[![Assegna organizzazioni](./media/screenshot13.png)](./media/screenshot13.png)

2.5. Selezionare "Concedi accesso a organizzazioni specifiche". Selezionare la gerarchia organizzativa creata nel primo passaggio. Selezionare il nodo Dati finanziari e fare clic sul pulsante Concedi con figli 

***Importante*** *Quando si esegue questa attività, assicurarsi di essere nel contesto della persona giuridica DEMF poiché la sicurezza organizzativa viene applicata per la persona giuridica* 

[![Concedi accesso](./media/screenshot14.png)](./media/screenshot14.png)

## <a name="task-3-create-scenarios"></a>Attività 3: creare scenari
3.1. Accedere a Budget &gt; Impostazioni &gt; Pianificazione del budget &gt; Configurazione di pianificazione del budget. Nella pagina Scenari, prendere nota degli scenari che verranno utilizzati in seguito in questo lab: Valori effettivi dell'anno precedente e In budget. 

*Nota: se si desidera, è possibile creare nuovi scenari per questo esercizio e utilizzare quelli.* 

[![Nuovi scenari](./media/screenshot15.png)](./media/screenshot15.png) 

*Nota: poiché Julia non utilizza il processo di approvazione formale per la preparazione del budget, in questo lab ignoreremo l'impostazione dei flussi di lavoro, delle fasi e delle fasi del flusso di lavoro e utilizzeremo l'impostazione esistente per l'approvazione automatica del flusso di lavoro. Vedere l'appendice per questa configurazione del flusso di lavoro.*

## <a name="task-4-create-budget-plan-columns"></a>Attività 4: creare le colonne del piano di budget
Le colonne del piano di budget sono colonne basate sulla liquidità o sulla quantità che possono essere utilizzate nel layout del documento del piano di budget. Nel nostro esempio dobbiamo creare una colonna per Valori effettivi dell'anno precedente e 12 colonne per rappresentare ogni mese dell'anno di riferimento del budget. Le colonne possono essere create semplicemente facendo clic sul pulsante Aggiungi e inserendo i valori o con una guida relativa all'Entità di dati. In questo lab utilizzeremo Entità di dati per inserire i valori. 

4.1. Aprire la pagina Colonne in Budget &gt; Impostazioni &gt; Pianificazione del budget &gt; Configurazione di pianificazione del budget. Fare clic sul pulsante Office nell'angolo superiore destro del modulo e selezionare Colonne (filtro non applicato) 

[![Colonne non filtrate](./media/screenshot16.png)](./media/screenshot16.png) 

4.2. Il sistema aprirà la cartella di lavoro Excel da utilizzare per l'inserimento dei valori. Se richiesto, fare clic su Abilita modifica e Considera affidabile questa applicazione 

[![Abilita modifica](./media/screenshot18.png)](./media/screenshot18.png) 

[![Considera affidabile questa applicazione](./media/screenshot17.png)](./media/screenshot17.png)

4.3. Saranno necessarie più colonne per inserire i valori. Fare clic su Progettazione nel riquadro laterale destro per aggiungere le colonne alla griglia: 

[![Progetto](./media/screenshot19.png)](./media/screenshot19.png) 

4.4. Fare clic sul pulsante della piccola matita accanto a PlanColumns per vedere le colonne disponibili da aggiungere alla griglia 

[![Modifica](./media/screenshot20.png)](./media/screenshot20.png) 

4.5. Fare doppio clic su ogni campo disponibile per aggiungerlo ai campi selezionati, quindi fare clic su Aggiorna 

![Aggiornamento](./media/screenshot21.png)](./media/screenshot21.png) 

4.6. Nella tabella Excel, aggiungere tutte le colonne da creare. Utilizzare la funzionalità di compilazione automatica in Excel per aggiungere le righe rapidamente. Verificare che le righe vengano aggiunte come parte della tabella (quando si utilizza la barra di scorrimento verticale, vengono visualizzate le intestazioni di colonna sulla parte superiore della griglia) 

[![Compilazione automatica](./media/screenshot22.png)](./media/screenshot22.png) 

4.7. Tornare a Finance and Operations e aggiornare la pagina. I valori pubblicati verranno visualizzati in Finance and Operations. 

[![Aggiornamento](./media/screenshot23.png)](./media/screenshot23.png)

## <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>Attività 5: creare modelli e layout del documento del piano di budget
Il layout determina l'aspetto della griglia delle righe del documento del piano di budget quando l'utente apre il suddetto documento. È inoltre possibile passare al layout per il documento del piano di budget per visualizzare gli stessi dati in angolazioni diverse. Quindi, dopo aver creato le colonne definite da utilizzare con il documento del piano di budget, Julia deve creare un layout del documento del piano di budget, il cui aspetto sarà simile alla tabella Excel che utilizza per creare i dati di budget (vedere la sezione Panoramica dello scenario di questo lab) 

5.1. Aprire la pagina Layout in Budget &gt; Impostazioni &gt; Pianificazione del budget &gt; Configurazione di pianificazione del budget. Creare un nuovo layout per la voce Budget mensile:

-   Selezionare il set di dimensioni MA+BU per includere i conti principali e le Business Unit al layout.
-   Elencare tutte le colonne del piano di budget create nel passaggio precedente nella sezione Elementi. Rendere modificabili tutti i valori effettivi dell'anno precedente.
-   Fare clic sul pulsante Descrizioni per selezionare le dimensioni finanziarie per cui visualizzare le descrizioni nella griglia.

[![Descrizioni](./media/screenshot24.png)](./media/screenshot24.png) 

In base alla definizione del layout del piano di budget, è possibile creare un modello Excel da utilizzare come metodo alternativo per la modifica dei dati di budget. Poiché il modello Excel deve corrispondere alla definizione del layout del piano di budget, non sarà possibile modificare il layout del piano di budget dopo la generazione del modello Excel; pertanto, è necessario effettuare questa attività dopo aver definito tutti i componenti del layout. 

5.2. Per il layout creato nel passaggio 5.1., fare clic sul pulsante Modello &gt; Genera. Confermare il messaggio di avviso. Per visualizzare il modello, fare clic su Modello &gt; Visualizza. 

*Nota: assicurarsi di selezionare "Salva con nome" e selezionare il luogo in cui il modello deve essere archiviato per modificarlo. Se l'utente seleziona "Apri" nella finestra di dialogo senza salvare, alla chiusura del file le modifiche apportate al file non verranno mantenute.* 
[![Visualizzazione modello](./media/screenshot25.png)](./media/screenshot25.png) 

5.3. &lt; Passaggio facoltativo&gt; Modificare il modello Excel per renderlo più facile e intuitivo: aggiungere formule totali, campi di intestazione, formattazione e così via. Salvare le modifiche e caricare il file nel piano di budget facendo clic su Layout &gt; Carica [![Carica](./media/screenshot26.png)](./media/screenshot26.png)

## <a name="task-6-create-a-budget-planning-process"></a>Attività 6: creare un processo di pianificazione del budget
Julia deve creare e attivare un nuovo processo di pianificazione del budget che combina tutte le impostazioni illustrate in precedenza per iniziare a immettere i piani di budget. Il processo di pianificazione del budget definisce quali organizzazioni di impostazione del budget, flussi di lavoro, layout e modelli verranno utilizzati per la creazione dei piani di budget. 

6.1. Accedere a Budget &gt; Impostazioni &gt; Pianificazione del budget &gt; Processo di pianificazione del budget e creare un nuovo record.

-   Processo di pianificazione del budget - Impostazione del budget DEMF per l'anno fiscale 2016
-   Ciclo di budget - Anno fiscale 2016
-   Contabilità generale - DEMF
-   Struttura dei conti predefinita - Produzione P&L
-   Gerarchia organizzativa - Selezionare la gerarchia creata all'inizio del lab
-   Flusso di lavoro di pianificazione del budget - Assegnare l'approvazione automatica del flusso di lavoro per il reparto finanziario
-   Nelle regole e nei modelli della fase di pianificazione del budget, per ogni fase di pianificazione del budget del flusso di lavoro selezionare se le funzioni di aggiunta e modifica delle righe sono consentite e il tipo di layout da utilizzare per impostazione predefinita

*Nota: è possibile creare layout di documento aggiuntivi e assegnarli per renderli disponibili nella fase del flusso di lavoro di pianificazione del budget facendo clic sul pulsante Layout alternativi.* 

[![Layout alternativi](./media/screenshot27.png)](./media/screenshot27.png) 

6.2. Selezionare Azioni &gt; Attiva per attivare questo flusso di lavoro di pianificazione del budget 

[![Attiva](./media/screenshot28.png)](./media/screenshot28.png)

<a name="exercise-2-process-simulation"></a>Esercizio 2: simulazione del processo
==============================

## <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>Attività 7: generare i dati iniziali per il piano di budget da Contabilità generale
7.1. Accedere a Budget &gt; Periodico &gt; Genera piano di budget da contabilità generale. Inserire i parametri del processo periodico e fare clic sul pulsante Genera. 

[![Genera](./media/screenshot29.png)](./media/screenshot29.png) 

7.2. Accedere a Budget &gt; Piani di budget per cercare un piano di budget creato da Genera processo. 

[![Piano di budget](./media/screenshot30.png)](./media/screenshot30.png) 

7.3. Aprire i dettagli del documento facendo clic sul collegamento ipertestuale Numero di documento. Il piano di budget viene visualizzato come definito nel layout creato in questo lab 

[![Visualizzazione del piano di budget](./media/screenshot31.png)](./media/screenshot31.png)

## <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>Attività 8: creare il budget dell'anno corrente in base ai valori effettivi dell'anno precedente
I metodi di allocazione possono essere utilizzati nel piano di budget per copiare facilmente le informazioni per i piani di budget da uno scenario all'altro, distribuirle su periodi, allocarle in dimensioni. Utilizzeremo le allocazioni per creare il budget dell'anno corrente dai valori effettivi dell'anno precedente. 

8.1. Selezionare tutte le righe nella griglia del documento del piano di budget e fare clic sul pulsante Allocare budget 

[![Tutte le righe](./media/screenshot32.png)](./media/screenshot32.png) 

8.2. Selezionare il metodo di allocazione, Chiave periodo, Origine e gli scenari di destinazione e fare clic su Alloca 

[![Alloca](./media/screenshot33.png)](./media/screenshot33.png)

Gli importi effettivi dell'anno precedente verranno copiati sul budget per l'anno corrente e verranno allocati sui periodi utilizzando la chiave del periodo della curva delle vendite. 

[![Curva di vendita](./media/screenshot34.png)](./media/screenshot34.png)

## <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>Attività 9: rettificare il documento del piano di budget utilizzando Excel e finalizzare il documento
9.1. Fare clic sul pulsante della cartella di lavoro per aprire i contenuti del documento in Excel

[![Excel](./media/screenshot35.png)](./media/screenshot35.png)

9.2. All'apertura della cartella di lavoro Excel, rettificare i numeri nel documento del piano di budget e fare clic sul pulsante Pubblicazione.

[![Pubblicazione](./media/screenshot36.png)](./media/screenshot36.png)

9.3. Tornare al documento del piano di budget in Finance and Operations. Fare clic sul pulsante Flusso di lavoro &gt; Invia per l'approvazione automatica del documento

[![Approvazione automatica](./media/screenshot37.png)](./media/screenshot37.png) 

Una volta completato il flusso di lavoro, la fase del documento del piano di budget viene modificata in Approvata. [![Approvato](./media/screenshot38.png)](./media/screenshot38.png)

<a name="appendix"></a>Appendice
========

### <a name="auto-approve-workflow-configuration"></a>Configurazione dell'approvazione automatica del flusso di lavoro

A. Budget &gt; Impostazioni &gt; Pianificazione del budget &gt; Flussi di lavoro impostazione budget - Creare un nuovo flusso di lavoro utilizzando il modello Flussi di lavoro di pianificazione del budget:

[![Creare un nuovo flusso di lavoro](./media/screenshot39.png)](./media/screenshot39.png)

Questo flusso di lavoro conterrà una sola attività - Transizione di fase piano di budget 

[![Transizione di fase piano di budget](./media/screenshot40.png)](./media/screenshot40.png) 

Salvare e attivare il flusso di lavoro. 

B. Accedere a Budget &gt; Impostazioni &gt; Pianificazione del budget &gt; Configurazione di pianificazione del budget. Nella scheda Fasi creare 2 fasi - Iniziale e Inviata 

[![Iniziale e inviato](./media/screenshot41.png)](./media/screenshot41.png)

C. Accedere a Budget &gt; Impostazioni &gt; Pianificazione del budget &gt; Configurazione di pianificazione del budget. Nella scheda Fasi flusso di lavoro associare il flusso di lavoro di approvazione automatica creato nel passaggio A alle fasi Iniziale e Inviata 

[![Pianificazione del budget e controllo del budget](./media/screenshot42.png)](./media/screenshot42.png)  




