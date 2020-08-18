---
title: Panoramica sulla creazione di report finanziari
description: In questo argomento viene descritto dove accedere ai report finanziari in Microsoft Dynamics 365 Finance e come utilizzare le funzionalità dei report finanziari. Include una descrizione dei report finanziari predefiniti forniti.
author: aprilolson
manager: AnnBe
ms.date: 07/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86022b662c265b4b98f6df86647f61ea35d31432
ms.sourcegitcommit: f5200f37c6c436183b4ee5711026ef92a7cb9538
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "3618040"
---
# <a name="financial-reporting-overview"></a>Panoramica sulla creazione di report finanziari

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto dove accedere ai report finanziari e come utilizzare le funzionalità dei report finanziari. Include anche una descrizione dei report finanziari predefiniti forniti.

<a name="accessing-financial-reporting"></a>Accesso ai report finanziari
-----------------------------

È possibile trovare il menu **Report finanziari** nelle seguenti posizioni:

-   **Contabilità generale** &gt; **Richieste di informazioni e report**
-   **Impostazione budget** &gt; **Richieste di informazioni e report** &gt; **Impostazione budget di base**
-   **Impostazione budget** &gt; **Richieste di informazioni e report** &gt; **Pianificazione del budget**
-   **Impostazione budget** &gt; **Richieste di informazioni e report** &gt; **Controllo del budget**
-   Consolidamenti

Per creare e generare i report finanziari per una persona giuridica, è necessario impostare le seguenti informazioni per la persona giuridica:

-   Calendario fiscale
-   Ledger
-   Piano dei conti
-   Valuta

## <a name="granting-security-access-to-financial-reporting"></a>Concessione dell'accesso di sicurezza a Financial Reporting
Le funzioni di report finanziari disponibili per gli utenti con i privilegi e i compiti appropriati assegnati loro nei rispettivi ruoli di sicurezza. Nelle sezioni seguenti vengono elencati tali compiti e privilegi, insieme ai ruoli associati.

### <a name="duties"></a>Compiti

| Etichetta del compito                            | Descrizione                                                             | Nome AOT                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Gestisci sicurezza dei report finanziari | Gestisci la sicurezza dei report finanziari ed esegui attività amministrative. | FinancialReportsSecurityMaintain |
| Gestisci report finanziari            | Progetta e gestisci i report finanziari.                                  | FinancialReportsMaintain         |
| Genera report finanziari            | Genera e aggiorna i report finanziari.                                 | FinancialReportsGenerate         |
| Esamina prestazioni finanziarie          | Esamina e analizza le prestazioni finanziarie.                               | FinancialReportsPerfReview       |

### <a name="privileges"></a>Privilegi

| Etichetta di privilegio                       | Descrizione                                                             | Nome AOT                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Gestisci sicurezza dei report finanziari | Gestisci la sicurezza dei report finanziari ed esegui attività amministrative. | FinancialReportsSecuritySystemMaintain |
| Gestisci report finanziari            | Progetta e gestisci i report finanziari.                                  | FinancialReportsMaintainReports  |
| Genera report finanziari            | Genera e aggiorna i report finanziari.                                 | FinancialReportsGenerateReports  |
| Visualizza report finanziari                | Visualizza report finanziari.                                                 | FinancialReportsView             |

### <a name="roles"></a>Ruoli

| Etichetta di privilegio                       | Imposta                                  | Ruoli                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Gestisci sicurezza dei report finanziari | Gestisci sicurezza dei report finanziari | Amministratore sicurezza                                                          |
| Gestisci report finanziari            | Gestisci report finanziari            | Direttore amministrativo, Supervisore contabile, Supervisore finanziario, Responsabile budget |
| Genera report finanziari            | Genera report finanziari            | CEO, CFO, Contabile                                                            |
| Visualizza report finanziari                | Esamina prestazioni finanziarie          | Nessuno assegnato                                                                   |

Dopo che un utente viene aggiunto o un ruolo viene modificato, l'utente deve poter accedere ai report finanziari in alcuni minuti. 

> [!NOTE]
> Il ruolo sysadmin viene aggiunto a tutti i ruoli nella creazione di report finanziari.

## <a name="report-deletions-and-expirations"></a>Report di eliminazioni e scadenze
Gli utenti che generano un report possono eliminare i propri report. Gli utenti con i diritti **Gestisci sicurezza dei report finanziari** possono eliminare i report di altri. 

Nella versione 10.0.8 è stato introdotto il concetto di date di scadenza. Una nuova funzione richiesta è abilitata nella pagina **Tutti** all'interno dell'area di lavoro Gestione funzionalità. La funzionalità **Criteri di conservazione dei report finanziari** contiene le seguenti modifiche:
* I report appena generati verranno automaticamente contrassegnati come aventi una data di scadenza di 90 giorni da quando sono stati generati
* In tutti i report esistenti precedenti all'installazione della funzionalità verrà assegnato un periodo di scadenza di 90 giorni. La data può apparire vuota per un breve periodo di tempo fino a quando il servizio di Financial Reporting è in esecuzione, viene generato un report e il servizio esegue l'aggiornamento ai report esistenti con una data di scadenza vuota. 
* Gli utenti con **Gestisci sicurezza dei report finanziari** avranno accesso a questa funzionalità. Tutti gli utenti nei diritti **Gestisci report finanziari** a cui è concesso il privilegio **Gestisci scadenza dei report finanziari** avranno anche la possibilità di modificare il periodo di scadenza. Attualmente sono disponibili due opzioni di ritenuta: 
  * Una scadenza di 90 giorni.
  * Un'opzione per impostare il report in modo che non scada mai.
  
Quando viene selezionata una scadenza, ad esempio 90 giorni, viene applicata tra 90 giorni a partire da oggi. Si tratta di un comportamento diverso rispetto ai 90 giorni dalla data di generazione originale impostata al momento della generazione del report. 
  
Ulteriori opzioni saranno prese in considerazione in future funzionalità. La scadenza di 90 giorni sarà quella predefinita e gli utenti con appropriate autorizzazioni potranno sovrascrivere il valore predefinito sulla pagina elenco **Report finanziari**.    

## <a name="default-reports"></a>Report predefiniti
Report finanziari fornisce 22 report finanziari predefiniti. Ogni report utilizza le categorie di conti principali predefinite. È possibile utilizzare questi report come sono o come punto di partenza per i report finanziari necessari. Oltre ai rendiconti finanziari tradizionali, ad esempio il conto economico e lo stato patrimoniale, questi report predefiniti includono report che illustrano i diversi tipi di report finanziari che è possibile creare. 

<!--Each report in the following table links to an Office Mix presentation about the report.-->

| Report predefinito                                                                                         | Descrizione                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Conto economico a colonna singola per 12 mesi – Predefinito | Consente di visualizzare la redditività di un'organizzazione per gli ultimi 12 mesi in una singola colonna.                                                                                                                                                                                                                                      |
| Conto economico tendenza 12 mesi – Predefinito                 | Consente di visualizzare la redditività di un'organizzazione per ciascuno degli ultimi 12 mesi. Questi 12 mesi possono si possono estendere per più di un anno fiscale.                                                                                                                                                                                             |
| Effettivi rispetto al budget - Predefinito                                | Consente di visualizzare le informazioni sul saldo per tutti i conti per il budget originale e di confrontare il budget rivisto ai valori effettivi con uno scostamento.                                                                                                                                                                          |
| Dettagli controllo - Predefinito                                  | Consente di visualizzare le informazioni sul saldo per tutti i conti. Questo report mostra i saldi in dare e in avere nella valuta di dichiarazione e nella valuta locale, insieme a ulteriori informazioni sulle transazioni, ad esempio ID utente, utente che ha apportato l'ultima modifica ai dati, la data di ultima modifica e l'ID del giornale di registrazione. |
| Elenco saldi - Predefinito                                   | Consente di visualizzare le informazioni sul saldo per tutti i conti. Questo report mostra i saldi di chiusura e di apertura e i saldi in dare e in avere per il periodo corrente e l'anno a oggi, insieme a ulteriori informazioni sulle transazioni, ad esempio il giustificativo.                                                                    |
| Stato patrimoniale - Predefinito                                   | Consente di visualizzare la posizione finanziaria dell'organizzazione per l'anno.                                                                                                                                                                                                                                                             |
| Stato patrimoniale e conto economico affiancati- Predefinito | Consente di visualizzare in modalità affiancata la posizione finanziaria e la redditività dell'organizzazione per l'anno.                                                                                                                                                                                                                              |
| Flusso di cassa - Predefinito                                       | Consente di visualizzare informazioni dettagliate sui contanti in entrata e in uscita dell'organizzazione.                                                                                                                                                                                                                                   |
| Revisione dettagliata TB e JE – Predefinito                      | Consente di visualizzare informazioni su bilancio di apertura e attività per tutti i conti.                                                                                                                                                                                                                                                      |
| Bilancio di verifica dettagliato - Predefinito                         | Consente di visualizzare informazioni sul saldo per tutti i conti con saldi in Avere e in Dare e l'importo netto di questi saldi, insieme alla data della transazione, al giustificativo e alla descrizione del giornale di registrazione.                                                                                                                                  |
| Tendenza trimestrale spese triennale – Predefinito             | Consente di visualizzare informazioni dettagliate sulle spese per i 12 trimestri dei tre anni precedenti.                                                                                                                                                                                                                                   |
| Revisione dettagliata TB e JE voci finanziarie – Predefinito            | Consente di ottenere una panoramica dei saldi e delle attività per le voci finanziare relative a cespite, passività, capitale netto del proprietario, ricavi, spese, guadagni o perdite.                                                                                                                                                                           |
| Conto economico - Predefinito                                | Consente di visualizzare la redditività dell'organizzazione per il periodo corrente e da inizio anno.                                                                                                                                                                                                                                   |
| Elenco transazioni contabili - Predefinito                        | Consente di visualizzare le informazioni sul saldo per tutti i conti. Questo report mostra i saldi in dare e in avere, insieme a ulteriori informazioni sulle transazioni, quali la data della transazione, il numero del giornale di registrazione, il giustificativo, il tipo di registrazione e il numero di traccia.                                                                            |
| Rapporti – Predefinita                                          | Consente di visualizzare i rapporti di solvibilità, redditività ed efficienza dell'organizzazione per l'anno.                                                                                                                                                                                                                           |
| Spese mensili 12 mesi - Predefinito                       | Consente di visualizzare informazioni dettagliate sulle spese per ciascuno degli ultimi 12 mesi. Questi 12 mesi possono si possono estendere per più di un anno fiscale.                                                                                                                                                                                                       |
| Conto economico trimestre – Predefinito               | Consente di visualizzare la redditività dell'organizzazione su base trimestrale per l'anno precedente e per l'anno a oggi.                                                                                                                                                                                                                   |
| Stato patrimoniale affiancato – Predefinito                      | Consente di visualizzare la posizione finanziaria dell'organizzazione per l'anno. Questo report mostra i cespiti e le passività e il capitale netto dell'azionista in modalità affiancata.                                                                                                                                                                                |
| Bilancio di verifica riepilogativo - Predefinito                          | Consente di visualizzare informazioni sul saldo per tutti i conti con saldi di chiusura e di apertura e saldi in Avere e in Dare, insieme alle differenze nette.                                                                                                                                                                  |
| Bilancio di verifica riepilogativo annuale - Predefinito           | Consente di visualizzare informazioni sul saldo per tutti i conti con saldi di chiusura e di apertura e saldi in Avere e in Dare, insieme alle differenze nette per l'anno corrente e l'anno precedente.                                                                                                                           |
| Vendite e sconti settimanali - Predefinito                     | Consente di visualizzare informazioni dettagliate su vendite e sconti per ogni settimana del mese. Questo report include un totale di quattro settimane.                                                                                                                                                                                                              |
| Fondi budget disponibili - Predefinito                         | Consente di visualizzare un confronto dettagliato del budget rivisto, delle spese effettive, delle prenotazioni budget e dei fondi budget disponibili per tutti i conti                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Apertura report finanziari
Quando si seleziona il menu **Report finanziari**, l'elenco dei report finanziari predefiniti per la società viene visualizzato. È quindi possibile aprire o modificare un report. Per aprire uno dei report predefiniti, selezionare il nome del report. La prima volta che un report viene aperto, viene generato automaticamente per il mese precedente. Ad esempio, se si apre un report per la prima volta nell'agosto 2019, il report viene generato per il 31 luglio 2019. Dopo l'apertura di un report, puoi iniziare a esplorarlo eseguendo il drill-down su parti specifiche di dati e modificando le opzioni di report.

## <a name="creating-and-modifying-financial-reports"></a>Creazione e modifica di report finanziari
Nell'elenco dei report finanziari, è possibile creare un nuovo report o modificare un report esistente. Se si dispone delle autorizzazioni appropriate, è possibile creare un nuovo report finanziario selezionando **Nuovo** nel riquadro azioni. Viene scaricato un programma di progettazione nel dispositivo. Dopo aver avviato la progettazione report, è possibile creare il nuovo report. Dopo aver salvato il nuovo report, verrà visualizzato nell'elenco dei report finanziari. Nell'elenco vengono visualizzati solo i report creati per la società utilizzata in Dynamics 365 Finance. 

## <a name="troubleshooting-issues-opening-report-designer"></a>Risoluzione dei problemi di apertura di Progettazione report
Esistono alcuni problemi comuni che possono causare problemi quando si apre Progettazione report. Tali problemi e i passaggi per risolverli sono riportati di seguito.

Problema 1: Progettazione report non si avvia quando si seleziona **Nuovo** o **Modifica**.

* In Internet Explorer, selezionare **Impostazioni**, quindi selezionare **Opzioni Internet**. Selezionare la scheda **Sicurezza**. Selezionare Siti attendibili e quindi **Siti**. In **Aggiungi questo sito Web alla zona**, immettere "\*\.dynamics.com" (senza virgolette), quindi selezionare **Aggiungi**. 
* In Internet Explorer, selezionare **Impostazioni**, quindi selezionare **Opzioni Internet**. Selezionare la scheda **Sicurezza**. Selezionare Siti attendibili. Nell'area denominata Livello di sicurezza per questa zona, impostare l'opzione in **Medio-basso**.
* Disabilitare il blocco popup nel browser.
* Le workstation sono necessarie per l'installazione di Visual Studio .NET 4.6.2 o versione successiva.

È possibile scaricare e installare questa versione di Microsoft .NET Framework nell'[Area download Microsoft](https://www.microsoft.com/download/details.aspx?id=53345).
* Se si utilizza il browser Chrome, è necessario installare l'estensione ClickOnce per scaricare il client Progettazione report. Se si utilizza la modalità in incognito, assicurarsi che l'estensione ClickOnce sia attiva in tale modalità. Se non si è grado di accedere con Chrome, provare a seguire la procedura di installazione descritta in Problema 1 utilizzando Internet Explorer o Edge. 

Problema 2: all'utente non sono state assegnate le autorizzazioni necessarie per utilizzare Financial Reporting. 

* Per verificare se l'utente non dispone dell'autorizzazione, selezionare **Sì** nell'errore "Impossibile connettersi al server di Financial Reporting. Selezionare Sì se si desidera continuare e specificare un indirizzo server diverso." Quindi selezionare **Test connessione**. Se non si dispone dell'autorizzazione, verrà visualizzato il messaggio "Tentativo di connessione non riuscito. L'utente non dispone delle autorizzazioni appropriate per connettersi al server. Contattare l'amministratore di sistema."
* Le autorizzazioni necessarie sono elencate sopra in [Concessione dell'accesso di sicurezza a Financial Reporting](#granting-security-access-to-financial-reporting). La sicurezza in Financial Reporting è basata su questi privilegi. Non si avrà accesso se non si hanno questi privilegi (o un altro ruolo di sicurezza che include questi privilegi). 
* L'attività di integrazione **Provider utenti azienda a azienda** (che corrisponde anche all'integrazione dell'utente) viene eseguita con un intervallo di 5 minuti. Potrebbero essere necessari fino a 10 minuti affinché le modifiche alle autorizzazioni diventino effettive in Financial Reporting. 
  Se un altro utente può aprire Progettazione report, selezionare **Strumenti**, quindi selezionare **Stato integrazione**. Verificare che la mappa di integrazione "Provider di utenti della società alla società" sia stata eseguita correttamente in quanto si dispone dell'autorizzazione per utilizzare Financial Reporting. 
* È possibile che un altro errore abbia impedito la conclusione di **Integrazione tra utenti Dynamics e utenti Financial Reporting**. Oppure è possibile che sia stato avviato e non ancora completato un ripristino del datamart o che si sia verificato un altro errore di sistema. Provare a eseguire nuovamente il processo più tardi. Se il problema persiste, contattare l'amministratore di sistema.

Problema 3: è possibile procedere oltre la pagina di accesso di Progettazione report ClickOnce, ma non è possibile completare l'accesso in Progettazione report. 

* L'ora impostata sul computer locale quando si immettono le credenziali di accesso non deve essere sfalsata di cinque minuti rispetto all'ora del server Financial Reporting. Se la differenza è superiore a cinque minuti, il sistema non consentirà l'accesso. 
* In questo caso, è consigliabile abilitare l'opzione Windows per impostare automaticamente l'ora del PC. 

## <a name="additional-resources"></a>Risorse aggiuntive
- [Visualizza report finanziari](view-financial-reports.md)
