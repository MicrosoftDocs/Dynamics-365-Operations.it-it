---
title: Panoramica sulla creazione di report finanziari
description: In questo argomento viene descritto dove accedere ai report finanziari in Microsoft Dynamics 365 Finance e come utilizzare le funzionalità dei report finanziari.
author: aprilolson
ms.date: 03/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "10444"
- intro-internal
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8a209390a8424e2ec3d6654b54b36e36fcd349b3
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2022
ms.locfileid: "8721901"
---
# <a name="get-started-with-financial-reporting"></a>Introduzione alla creazione di report finanziari 

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto dove accedere a Financial Reporting e come utilizzare le funzionalità di Financial Reporting. Include anche una descrizione dei report finanziari predefiniti forniti.

## <a name="accessing-financial-reporting"></a>Accesso ai report finanziari

È possibile trovare il menu **Report finanziari** nelle seguenti posizioni:

- **Contabilità generale** &gt; **Richieste di informazioni e report**
- **Impostazione budget** &gt; **Richieste di informazioni e report** &gt; **Impostazione budget di base**
- **Impostazione budget** &gt; **Richieste di informazioni e report** &gt; **Pianificazione del budget**
- **Impostazione budget** &gt; **Richieste di informazioni e report** &gt; **Controllo del budget**
- Consolidamenti

Per creare e generare i report finanziari per una persona giuridica, è necessario impostare le seguenti informazioni per la persona giuridica:

- Calendario fiscale
- Ledger
- Piano dei conti
- Valuta
- Registrare una transazione su almeno un conto
- MainAccount è elencato nella colonna **Selezionati** nella pagina **Impostazione report finanziari** (**Contabilità generale > Impostazioni contabilità generale > Impostazione report finanziari**)

## <a name="granting-security-access-to-financial-reporting"></a>Concessione dell'accesso di sicurezza a Financial Reporting

Le funzioni di report finanziari disponibili per gli utenti con i privilegi e i compiti appropriati assegnati loro nei rispettivi ruoli di sicurezza. Nelle sezioni seguenti vengono elencati tali compiti e privilegi, insieme ai ruoli associati.

### <a name="duties"></a>Compiti

| Etichetta del compito                            | descrizione                                                             | Nome AOT                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Gestisci sicurezza dei report finanziari | Gestisci la sicurezza di Financial Reporting ed esegui attività amministrative. | FinancialReportsSecurityMaintain |
| Gestisci report finanziari            | Progetta e gestisci i report finanziari.                                  | FinancialReportsMaintain         |
| Genera report finanziari            | Genera e aggiorna i report finanziari.                                 | FinancialReportsGenerate         |
| Esamina prestazioni finanziarie          | Esamina e analizza le prestazioni finanziarie.                               | FinancialReportsPerfReview       |

### <a name="privileges"></a>Privilegi

| Etichetta di privilegio                       | descrizione                                                             | Nome AOT                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Gestisci sicurezza dei report finanziari | Gestisci la sicurezza di Financial Reporting ed esegui attività amministrative. | FinancialReportsSecuritySystemMaintain |
| Gestisci report finanziari            | Progetta e gestisci i report finanziari.                                  | FinancialReportsMaintainReports  |
| Genera report finanziari            | Genera e aggiorna i report finanziari.                                 | FinancialReportsGenerateReports  |
| Visualizza report finanziari                | Visualizza report finanziari.                                                 | FinancialReportsView             |

### <a name="roles"></a>Ruoli

| Etichetta di privilegio                       | Compito                                  | Ruoli                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Gestisci sicurezza dei report finanziari | Gestisci sicurezza di Financial Reporting. | Amministratore sicurezza                                                          |
| Gestisci report finanziari            | Gestisci report finanziari            | Direttore amministrativo, Supervisore contabile, Supervisore finanziario, Responsabile budget |
| Genera report finanziari            | Genera report finanziari            | CEO, CFO, Contabile                                                            |
| Visualizza report finanziari                | Esamina prestazioni finanziarie          | Nessuno assegnato                                                                   |

Dopo che un utente viene aggiunto o un ruolo viene modificato, l'utente deve poter accedere a Financial Reporting in alcuni minuti. 

> [!NOTE]
> Il ruolo sysadmin viene aggiunto a tutti i ruoli nella creazione di report finanziari.

## <a name="report-deletions-and-expirations"></a>Report di eliminazioni e scadenze

Gli utenti che generano un report possono eliminare i propri report. Gli utenti con i diritti **Gestisci sicurezza dei report finanziari** possono eliminare i report di altri. 

Nella versione 10.0.8 è stato introdotto il concetto di date di scadenza. Una nuova funzione richiesta è abilitata nella pagina **Tutti** all'interno dell'area di lavoro Gestione funzionalità. La funzionalità **Criteri di conservazione dei report finanziari** contiene le seguenti modifiche:
* I report appena generati verranno automaticamente contrassegnati come aventi una data di scadenza di 90 giorni da quando sono stati generati.
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
| [Bilancio di verifica dettagliato - Predefinito](trial-balance-financial-reports.md)| Consente di visualizzare informazioni sul saldo per tutti i conti con saldi in Avere e in Dare e l'importo netto di questi saldi, insieme alla data della transazione, al giustificativo e alla descrizione del giornale di registrazione.                                                                                                                                  |
| Tendenza trimestrale spese triennale – Predefinito             | Consente di visualizzare informazioni dettagliate sulle spese per i 12 trimestri dei tre anni precedenti.                                                                                                                                                                                                                                   |
| Revisione dettagliata TB e JE voci finanziarie – Predefinito            | Consente di ottenere una panoramica dei saldi e delle attività per le voci finanziare relative a cespite, passività, capitale netto del proprietario, ricavi, spese, guadagni o perdite.                                                                                                                                                                           |
| [Conto economico - Predefinito](income-statement-financial-report.md)| Consente di visualizzare la redditività dell'organizzazione per il periodo corrente e da inizio anno.                                                                                                                                                                                                                                   |
| Elenco transazioni contabili - Predefinito                        | Consente di visualizzare le informazioni sul saldo per tutti i conti. Questo report mostra i saldi in dare e in avere, insieme a ulteriori informazioni sulle transazioni, quali la data della transazione, il numero del giornale di registrazione, il giustificativo, il tipo di registrazione e il numero di traccia.                                                                            |
| Rapporti – Predefinita                                          | Consente di visualizzare i rapporti di solvibilità, redditività ed efficienza dell'organizzazione per l'anno.                                                                                                                                                                                                                           |
| Spese mensili 12 mesi - Predefinito                       | Consente di visualizzare informazioni dettagliate sulle spese per ciascuno degli ultimi 12 mesi. Questi 12 mesi possono si possono estendere per più di un anno fiscale.                                                                                                                                                                                                       |
| Conto economico trimestre – Predefinito               | Consente di visualizzare la redditività dell'organizzazione su base trimestrale per l'anno precedente e per l'anno a oggi.                                                                                                                                                                                                                   |
| Stato patrimoniale affiancato – Predefinito                      | Consente di visualizzare la posizione finanziaria dell'organizzazione per l'anno. Questo report mostra i cespiti e le passività e il capitale netto dell'azionista in modalità affiancata.                                                                                                                                                                                |
| [Bilancio di verifica riepilogativo - Predefinito](trial-balance-financial-reports.md)| Consente di visualizzare informazioni sul saldo per tutti i conti con saldi di chiusura e di apertura e saldi in Avere e in Dare, insieme alle differenze nette.                                                                                                                                                                  |
| [Bilancio di verifica riepilogativo annuale - Predefinito](trial-balance-financial-reports.md)| Consente di visualizzare informazioni sul saldo per tutti i conti con saldi di chiusura e di apertura e saldi in Avere e in Dare, insieme alle differenze nette per l'anno corrente e l'anno precedente.                                                                                                                           |
| Vendite e sconti settimanali - Predefinito                     | Consente di visualizzare informazioni dettagliate su vendite e sconti per ogni settimana del mese. Questo report include un totale di quattro settimane.                                                                                                                                                                                                              |
| Fondi budget disponibili - Predefinito                         | Consente di visualizzare un confronto dettagliato del budget rivisto, delle spese effettive, delle prenotazioni budget e dei fondi budget disponibili per tutti i conti                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Apertura report finanziari

Quando si seleziona il menu **Report finanziari**, l'elenco dei report finanziari predefiniti per la società viene visualizzato. È quindi possibile aprire o modificare un report. Per aprire uno dei report predefiniti, selezionare il nome del report. La prima volta che un report viene aperto, viene generato automaticamente per il mese precedente. Ad esempio, se si apre un report per la prima volta nell'agosto 2019, il report viene generato per il 31 luglio 2019. Dopo l'apertura di un report, puoi iniziare a esplorarlo eseguendo il drill-down su parti specifiche di dati e modificando le opzioni di report.

## <a name="creating-and-modifying-financial-reports"></a>Creazione e modifica di report finanziari

Nell'elenco dei report finanziari, è possibile creare un nuovo report o modificare un report esistente. Se si dispone delle autorizzazioni appropriate, è possibile creare un nuovo report finanziario selezionando **Nuovo** nel riquadro azioni. Viene scaricato un programma di progettazione nel dispositivo. Dopo aver avviato la progettazione report, è possibile creare il nuovo report. Dopo aver salvato il nuovo report, verrà visualizzato nell'elenco dei report finanziari. Nell'elenco vengono visualizzati solo i report creati per la società utilizzata in Dynamics 365 Finance. 

## <a name="reporting-tree-definitions"></a>Definizioni di albero gerarchico

Uno dei componenti utilizzati per creare report finanziari è una definizione dell'albero dei report. Una definizione di albero gerarchico consente di definire la struttura e la gerarchia dell'organizzazione. Si tratta di una struttura gerarchica interdimensionale basata sulle relazioni dimensionali nei dati finanziari. Fornisce informazioni a livello di unità gerarchica e a livello di riepilogo per tutte le unità dell'albero.

È possibile creare un numero illimitato di alberi gerarchici per visualizzare i dati dell'organizzazione in vari modi. Ogni albero di reporting può contenere qualsiasi combinazione di reparti e unità di riepilogo, ma una definizione di report può collegarsi a un solo albero di reporting alla volta. 

## <a name="update-the-financial-reporting-version-through-slipstreaming"></a>Aggiornare la versione di Financial Reporting tramite slipstreaming

Le app Finance and Operations vengono aggiornate ogni mese. Tuttavia, Financial Reporting non è necessariamente aggiornato con la stessa cadenza. Inoltre, i clienti hanno più opzioni disponibili per implementare gli aggiornamenti per le app Finance and Operations. Gli aggiornamenti di Financial Reporting vengono installati automaticamente. Financial Reporting ha una versione designata che viene utilizzata in un ambiente del cliente quando viene implementato un aggiornamento del servizio, quando viene avviato un tempo di inattività o quando l'ambiente di un cliente è in modalità di manutenzione. Questo processo è noto come *slipstreaming* o *true-up*, perché tutte le implementazioni del cliente sono impostate sulla stessa versione di Financial Reporting.

Le modifiche rilasciate in ciascuna versione possono essere trovate in [Novità o modifiche in Dynamics 365 Finance](../../finance/get-started/whats-new-home-page.md). Gli aggiornamenti della piattaforma e le correzioni di bug sono disponibili nella sezione "Risorse aggiuntive" nella parte inferiore della pagina per ogni versione.

La versione slipstream selezionata è una versione revisionata e convalidata del Financial Reporting pronta per la produzione. È compatibile con qualsiasi versione precedente o futura di Dynamics 365 Finance. Ad esempio, Financial Reporting può essere sull'ultima build 10.0.19 mentre il cliente è ancora sulla versione dell'applicazione 10.0.16.

> [!NOTE]
> L'unica circostanza in cui i clienti possono passare a una versione precedente (uno scenario di downgrade) si verifica se Microsoft interrompe un rollout true-up a causa di un problema. Non appena una correzione è disponibile, verrà applicata automaticamente.

Il processo slipstream è completamente automatizzato e non richiede alcuna azione da parte del cliente. Tre topologie usano slipstream, ciascuna in modo leggermente diverso:

- **Locale** – Le distribuzioni locali non supportano slipstream e true-up.
- **Infrastructure as a service (IaaS)** – La logica slipstream viene applicata durante qualsiasi operazione che tenti di aggiornare Financial Reporting. Include aggiornamenti binari o trasmissioni che contengono aggiornamenti binari.
- **Self service** – Qualsiasi operazione che richieda tempi di inattività di Financial Reporting applica la logica slipstream:

    - Aggiornamenti binari o trasmissioni che contengono aggiornamenti binari
    - Applicazione di patch o altri tempi di inattività dell'infrastruttura
    - Distribuzioni di pacchetti AOT

## <a name="troubleshooting-issues-opening-report-designer"></a>Risoluzione dei problemi di apertura di Progettazione report

Esistono alcuni problemi comuni che possono causare problemi quando si apre Progettazione report. Tali problemi e i passaggi per risolverli sono riportati di seguito.

Problema 1: Progettazione report non si avvia quando si seleziona **Nuovo** o **Modifica**.

* In Internet Explorer, selezionare **Impostazioni**, quindi selezionare **Opzioni Internet**. Selezionare la scheda **Sicurezza**. Selezionare Siti attendibili e quindi **Siti**. In **Aggiungi questo sito Web alla zona**, immettere "\*\.dynamics.com" (senza virgolette) quindi selezionare **Aggiungi**. 
* In Internet Explorer, selezionare **Impostazioni**, quindi selezionare **Opzioni Internet**. Selezionare la scheda **Sicurezza**. Selezionare Siti attendibili. Nell'area denominata Livello di sicurezza per questa zona, impostare l'opzione in **Medio-basso**.
* Disabilitare il blocco popup nel browser.
* Le workstation sono necessarie per l'installazione di Microsoft .NET Fremework 4.7.2 o versione successiva. È possibile scaricare e installare questa versione di Microsoft .NET Framework nell'[Area download Microsoft](https://dotnet.microsoft.com/download/dotnet-framework/net472).
* Se stai utilizzando il browser Chrome, è necessario installare l'estensione ClickOnce per scaricare il client Progettazione report. Se si utilizza Chrome in modalità in incognito, assicurarsi che l'estensione ClickOnce sia attiva in tale modalità. Per ulteriori informazioni sull'estensione ClickOnce di Chrome, vedere [Requisiti di sistema per le distribuzioni cloud](../../fin-ops-core/fin-ops/get-started/system-requirements.md).
* Se stai utilizzando Microsoft Edge con un browser Chrome, non è necessario installare un'estensione ClickOnce per Edge Chromium. Tuttavia, è necessario abilitare l'opzione ClickOnce per scaricare il client Report Designer. Se si utilizza la modalità in incognito, assicurarsi che l'estensione ClickOnce sia attiva in tale modalità.

    1. Apri un nuovo browser in Microsoft Edge.
    2. Immetti **edge://flags** e premi **INVIO**.
    3. Cerca l'opzione **Supporto ClickOnce** o utilizza questo collegamento diretto: **edge://flags/#edge-click-once**.
    4. Impostare l'opzione del menu a discesa su **Abilitato**.
    5. Selezionare **Riavvia browser**.

Problema 2: all'utente non sono state assegnate le autorizzazioni necessarie per utilizzare Financial Reporting. 

* Per verificare se l'utente non dispone dell'autorizzazione, selezionare **Sì** nell'errore "Impossibile connettersi al server di Financial Reporting. Selezionare Sì se si desidera continuare e specificare un indirizzo server diverso". Quindi selezionare **Test connessione**. Se non si dispone dell'autorizzazione, verrà visualizzato il messaggio "Tentativo di connessione non riuscito. L'utente non dispone delle autorizzazioni appropriate per connettersi al server. Contattare l'amministratore di sistema".
* Le autorizzazioni necessarie sono elencate sopra in [Concessione dell'accesso di sicurezza a Financial Reporting](#granting-security-access-to-financial-reporting). La sicurezza in Financial Reporting è basata su questi privilegi. Non si avrà accesso se non si hanno questi privilegi (o un altro ruolo di sicurezza che include questi privilegi). 
* L'attività di integrazione **Provider utenti azienda a azienda** (che corrisponde anche all'integrazione dell'utente) viene eseguita con un intervallo di 5 minuti. Potrebbero essere necessari fino a 10 minuti affinché le modifiche alle autorizzazioni diventino effettive in Financial Reporting. 

    Se un altro utente può aprire Progettazione report, selezionare **Strumenti**, quindi selezionare **Stato integrazione**. Verificare che la mappa di integrazione "Provider di utenti della società alla società" sia stata eseguita correttamente in quanto si dispone dell'autorizzazione per utilizzare Financial Reporting. 

* È possibile che un altro errore abbia impedito la conclusione di **Integrazione tra utenti Dynamics e utenti Financial Reporting**. Oppure è possibile che sia stato avviato e non ancora completato un ripristino del datamart o che si sia verificato un altro errore di sistema. Provare a eseguire nuovamente il processo più tardi. Se il problema persiste, contattare l'amministratore di sistema.

Problema 3: è possibile procedere oltre la pagina di accesso di **ClickOnce Report Designer**, ma non è possibile completare l'accesso in Report Designer. 

* L'ora impostata sul computer locale quando si immettono le credenziali di accesso non deve essere sfalsata di cinque minuti rispetto all'ora del server Financial Reporting. Se la differenza è superiore a cinque minuti, il sistema non consentirà l'accesso. 
* Se l'ora sul tuo computer è diversa dall'ora del server Financial Reporting, ti consigliamo di abilitare l'opzione di Windows per impostare automaticamente l'ora del computer. 

## <a name="troubleshoot-report-designer-issues-with-event-viewer"></a>Risolvere i problemi di Report Designer con il visualizzatore eventi

Puoi utilizzare il visualizzatore eventi per analizzare alcuni dei problemi che sorgono durante l'utilizzo di Financial Reporting. 

### <a name="what-happens-when-you-have-connections-issues-with-financial-reporting"></a>Cosa succede in caso di problemi di connessione con Financial Reporting? 

Di seguito sono riportati alcuni passaggi che puoi eseguire per rendere più efficace la conversazione con il supporto tecnico Microsoft e ottenere una risoluzione più rapida. 
 
I passaggi seguenti illustrano il processo di attivazione dei messaggi del visualizzatore eventi per Financial Reporting. I registri generati dal visualizzatore eventi aiuteranno i tecnici del supporto tecnico a identificare rapidamente l'origine del problema di connessione. Invia copie di questi registri insieme al ticket quando contatti il supporto.


1. Copia il file RegisterETW.zip nella workstation client (preferibilmente il desktop) ed estrai [RegistratiETW.zip](https://mbs2.microsoft.com/fileexchange/?fileID=60b1106b-d5f8-4e0f-8041-039102505122).
2. Assicurati che il visualizzatore eventi di Windows sia chiuso.
3. Apri un prompt dei comandi di PowerShell per amministratori e accedi alla directory in cui si trova RegisterETW.ps1.
4. Esegui il comando seguente: .\RegisterETW.ps1

    Un output riuscito in PowerShell verrà verificato con il messaggio **Script RegisterETW completato**.

    Riapri il Visualizzatore eventi e ora vedrai questi registri sotto **Microsoft > Dynamics**:

    * MR-Client
    * MR-DVT
    * MR-Integration
    * MR-Logger
    * MR-Reporting
    * MR_SchedulerTasks
    * MR-Sql
    * MR-TraceManager

5. Riproduci il problema in Report Designer.
6. Esporta gli eventi MR-Logger utilizzando il visualizzatore eventi.

## <a name="troubleshoot-issues-connecting-to-financial-reporting"></a>Risolvere i problemi di connessione a Financial Reporting

Problema: viene visualizzato l'errore "Impossibile connettersi al server di Financial Reporting".

* Determina se il problema si verifica nei browser Internet Chrome e Edge.
* Se il problema si verifica solo in un browser, potrebbe trattarsi di un problema ClickOnce. 
* Quando ricevi il messaggio di errore relativo alla connessione, seleziona **Test** per testare la connessione e vedere quale messaggio appare. 
* Il problema potrebbe essere dovuto a un altro utente che non ha accesso a Financial Reporting. Se un utente non ha accesso, riceverà un messaggio indicante che non dispone dell'autorizzazione.
* Se il problema si verifica con più browser, assicurati che l'orologio della workstation sia impostato su Auto.
* Lavora con un utente che dispone dei diritti di amministratore della sicurezza in Dynamics 365 Finance e dei diritti di amministratore per il dominio di rete per accedere alla workstation e determinare se riesce a connettersi. Se riesce a connettersi, il problema potrebbe essere correlato alle autorizzazioni di rete.
* Nella workstation, disabilita temporaneamente il firewall. Se sei quindi in grado di connetterti a Report Designer, il problema riguarda il firewall. Collabora con il reparto IT dell'organizzazione per risolvere il problema.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Visualizza report finanziari](view-financial-reports.md)
- [Definizioni di albero gerarchico nei report finanziari](../../fin-ops-core/dev-itpro/analytics/financial-reporting-tree-definitions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
