---
title: Creazione di report finanziari
description: "In questo argomento viene descritto dove accedere ai report finanziari in Microsoft Dynamics 365 per le operazioni e come utilizzare le funzionalità dei report finanziari. Include una descrizione dei report finanziari predefiniti forniti."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d13747f17b5f382b3a530b1f166681eeec0b9d73
ms.lasthandoff: 03/31/2017


---

# <a name="financial-reporting"></a>Creazione di report finanziari

In questo argomento viene descritto dove accedere ai report finanziari in Microsoft Dynamics 365 per le operazioni e come utilizzare le funzionalità dei report finanziari. Include una descrizione dei report finanziari predefiniti forniti.

<a name="accessing-financial-reporting"></a>Accesso ai report finanziari
-----------------------------

Per i report finanziari ** ** il menu dei seguenti posizioni in Dynamics 365 per le operazioni:

-   ** Contabilità generale ** &gt; ** richieste di informazioni e report **
-   ** Impostazione del budget ** &gt; ** domanda e report statistici ** &gt; ** il budget di base **
-   ** ** ** &gt; Richieste di informazioni e report di budget ** &gt; ** pianificazione del budget **
-   ** ** ** &gt; Richieste di informazioni e report di budget ** &gt; ** controllo del budget **
-   Consolidamenti

Per creare e generare i report finanziari per una persona giuridica, è necessario impostare le seguenti informazioni per la persona giuridica:

-   Calendario fiscale
-   Contabilità generale
-   Piano dei conti
-   Valuta

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
| Gestisci sicurezza dei report finanziari | Gestisci la sicurezza dei report finanziari ed esegui attività amministrative. | FinancialReportsSecurityMaintain |
| Gestisci report finanziari            | Progetta e gestisci i report finanziari.                                  | FinancialReportsMaintainReports  |
| Genera report finanziari            | Genera e aggiorna i report finanziari.                                 | FinancialReportsGenerateReports  |
| Visualizza report finanziari                | Visualizza report finanziari.                                                 | FinancialReportsView             |

### <a name="roles"></a>Ruoli

| Etichetta di privilegio                       | Imposta                                  | Ruoli                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Gestisci sicurezza dei report finanziari | Gestisci sicurezza dei report finanziari | Amministratore sicurezza                                                          |
| Gestisci report finanziari            | Gestisci report finanziari            | Gestione della contabilità, supervisore di controllo contabile, finanziario, responsabile budget |
| Genera report finanziari            | Genera report finanziari            | Direttore generale, CFO, contabile                                                            |
| Visualizza report finanziari                | Esamina prestazioni finanziarie          | Nessuno assegnato                                                                   |

Dopo che un utente viene aggiunto o un ruolo viene modificato, l'utente deve poter accedere ai report finanziari in alcuni minuti. ** Nota: ** Il ruolo sysadmin viene aggiunto a tutti i ruoli nei report finanziari.

## <a name="default-reports"></a>Report predefiniti
Report finanziari fornisce 22 report finanziari predefiniti. Ogni report utilizza le categorie di conti principali predefinito in Dynamics 365 per le operazioni. È possibile utilizzare questi report come sono o come punto di partenza per i report finanziari necessari. Oltre ai rendiconti finanziari tradizionali, ad esempio il conto economico e lo stato patrimoniale, questi report predefiniti includono report che illustrano i diversi tipi di report finanziari che è possibile creare. Ogni report nei seguenti collegamenti della tabella a una presentazione batch di Office sul report.

| Report predefinito                                                                                         | descrizione                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [12 Month Rolling Single Column Income Statement – Default](https://mix.office.com/watch/76kc7bm3wnt1) | Consente di visualizzare la redditività di un'organizzazione per gli ultimi 12 mesi in una singola colonna.                                                                                                                                                                                                                                      |
| [12 Month Trend Income Statement – Default](https://mix.office.com/watch/12brmfge5p8r)                 | Consente di visualizzare la redditività di un'organizzazione per ciascuno degli ultimi 12 mesi. Questi 12 mesi possono si possono estendere per più di un anno fiscale.                                                                                                                                                                                             |
| [Actual vs Budget – Default](https://mix.office.com/watch/fi439lkwr0no)                                | Consente di visualizzare le informazioni sul saldo per tutti i conti per il budget originale e di confrontare il budget rivisto ai valori effettivi con uno scostamento.                                                                                                                                                                          |
| [Audit Details – Default](https://mix.office.com/watch/1i15nzd3nwkyh)                                  | Consente di visualizzare le informazioni sul saldo per tutti i conti. Questo report mostra i saldi in dare e in avere nella valuta di dichiarazione e nella valuta locale, insieme a ulteriori informazioni sulle transazioni, ad esempio ID utente, utente che ha apportato l'ultima modifica ai dati, la data di ultima modifica e l'ID del giornale di registrazione. |
| [Balance List – Default](https://mix.office.com/watch/1kezwu2a10fq4)                                   | Consente di visualizzare le informazioni sul saldo per tutti i conti. Questo report mostra i saldi di chiusura e di apertura e i saldi in dare e in avere per il periodo corrente e l'anno a oggi, insieme a ulteriori informazioni sulle transazioni, ad esempio il giustificativo.                                                                    |
| [Balance Sheet – Default](https://mix.office.com/watch/zkgq0u7visw9)                                   | Consente di visualizzare la posizione finanziaria dell'organizzazione per l'anno.                                                                                                                                                                                                                                                             |
| [Balance Sheet and Income Statement Side by Side - Default](https://mix.office.com/watch/zkgq0u7visw9) | Consente di visualizzare in modalità affiancata la posizione finanziaria e la redditività dell'organizzazione per l'anno.                                                                                                                                                                                                                              |
| [Cash Flow – Default](https://mix.office.com/watch/jd3go9pz6390)                                       | Consente di visualizzare informazioni dettagliate sui contanti in entrata e in uscita dell'organizzazione.                                                                                                                                                                                                                                   |
| [Detailed JE and TB Review – Default](https://mix.office.com/watch/1sw9fmtwgjb1f)                      | Consente di visualizzare informazioni su bilancio di apertura e attività per tutti i conti.                                                                                                                                                                                                                                                      |
| [Detailed Trial Balance - Default](https://mix.office.com/watch/1ewwgbpv0iwrl)                         | Consente di visualizzare informazioni sul saldo per tutti i conti con saldi in Avere e in Dare e l'importo netto di questi saldi, insieme alla data della transazione, al giustificativo e alla descrizione del giornale di registrazione.                                                                                                                                  |
| [Expenses Three Year Quarterly Trend – Default](https://mix.office.com/watch/gwm4zu7tmtj8)             | Consente di visualizzare informazioni dettagliate sulle spese per i 12 trimestri dei tre anni precedenti.                                                                                                                                                                                                                                   |
| [Financial Captions JE and TB Review – Default](https://mix.office.com/watch/1sw9fmtwgjb1f)            | Consente di ottenere una panoramica dei saldi e delle attività per le voci finanziare relative a cespite, passività, capitale netto del proprietario, ricavi, spese, guadagni o perdite.                                                                                                                                                                           |
| [Income Statement – Default](https://mix.office.com/watch/sbuhgl5hzuhi)                                | Consente di visualizzare la redditività dell'organizzazione per il periodo corrente e da inizio anno.                                                                                                                                                                                                                                   |
| [Ledger Transaction List – Default](https://mix.office.com/watch/19h9v2rmh48vy)                        | Consente di visualizzare le informazioni sul saldo per tutti i conti. Questo report mostra i saldi in dare e in avere, insieme a ulteriori informazioni sulle transazioni, quali la data della transazione, il numero del giornale di registrazione, il giustificativo, il tipo di registrazione e il numero di traccia.                                                                            |
| [Ratios – Default](https://mix.office.com/watch/b08hfc5h92me)                                          | Consente di visualizzare i rapporti di solvibilità, redditività ed efficienza dell'organizzazione per l'anno.                                                                                                                                                                                                                           |
| [Rolling 12 Month Expenses – Default](https://mix.office.com/watch/iywod5qmqhz7)                       | Consente di visualizzare informazioni dettagliate sulle spese per ciascuno degli ultimi 12 mesi. Questi 12 mesi possono si possono estendere per più di un anno fiscale.                                                                                                                                                                                                       |
| [Rolling Quarter Income Statement – Default](https://mix.office.com/watch/1k4yl6a6oyxqc)               | Visualizza la redditività di organizzazione su base trimestrale per l'anno precedente e Data di fine anno.                                                                                                                                                                                                                   |
| [Side by Side Balance Sheet – Default](https://mix.office.com/watch/zkgq0u7visw9)                      | Consente di visualizzare la posizione finanziaria dell'organizzazione per l'anno. Questo report mostra i cespiti e le passività e il capitale netto dell'azionista in modalità affiancata.                                                                                                                                                                                |
| [Summary Trial Balance – Default](https://mix.office.com/watch/1ewwgbpv0iwrl)                          | Consente di visualizzare informazioni sul saldo per tutti i conti con saldi di chiusura e di apertura e saldi in Avere e in Dare, insieme alle differenze nette.                                                                                                                                                                  |
| [Summary Trial Balance Year Over Year – Default](https://mix.office.com/watch/1ewwgbpv0iwrl)           | Consente di visualizzare le informazioni del saldo per tutti i conti con saldi di chiusura e di apertura e Dare e conti in Avere insieme alla differenza netto per l'anno corrente e quello precedente.                                                                                                                           |
| [Weekly Sales and Discounts - Default](https://mix.office.com/watch/112ng0hy5de0j)                     | Consente di visualizzare informazioni dettagliate su vendite e sconti per ogni settimana del mese. Questo report include un totale di quattro settimane.                                                                                                                                                                                                              |
| [Prenotano fondi budget disponibili - standard (https://mix.office.com/watch/15hcpezcbx7tv)]                         | Consente di visualizzare un confronto dettagliato del budget rivisto, alle spese effettive, delle prenotazioni budget e dei fondi budget disponibili per tutti i conti                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Apertura report finanziari
Quando si fa clic sul menu **Report finanziari**, l'elenco dei report finanziari predefiniti per la società viene visualizzato. È quindi possibile aprire o modificare un report. Per aprire uno dei report predefiniti, selezionare il nome del report. La prima volta che un report viene aperto, viene generato automaticamente per il mese precedente. Ad esempio, se si aprono per la prima volta nell'agosto 2016 un report, il report viene generato per il 31 luglio 2016. Dopo l'apertura di un report, puoi iniziare a esplorarlo eseguendo il drill-down su parti specifiche di dati e modificando le opzioni di report.

## <a name="creating-and-modifying-financial-reports"></a>Creazione e modifica di report finanziari
Nell'elenco dei report finanziari, è possibile creare un nuovo report o modificare un report esistente. Se si dispone delle autorizzazioni appropriate, è possibile creare un nuovo report finanziario utilizzando ** nuovo ** nel riquadro azioni. Programma di Progettazione report viene scaricato all'unità. Dopo aver Progettazione report inizia è possibile creare il nuovo dichiarate. Dopo aver salvato il nuovo report, verrà visualizzato nell'elenco dei report finanziari. L'elenco visualizza solo i report creati per la società in uso in Dynamics 365 per le operazioni. Per ulteriori informazioni sul processo di creazione e della modifica dei report finanziari in Dynamics 365 per le operazioni, fare riferimento a questi [] di registrazione (blog https://blogs.msdn.microsoft.com/dynamics_financial_reporting/tag/learning/) da blog di reporting finanziario di Dynamics. ** Nota: ** Il computer su cui si scaricando il client Progettazione report su deve essere 4.6.2 versione di Microsoft .NET Framework impostato su. Questa versione di Microsoft .NET Framework può essere impostata e scaricata da qui [] (https://www.microsoft.com/en-us/download/details.aspx?id=53345). Se si utilizza Cromato, è necessario impostare un'estensione ClickOnce per scaricare il client di Progettazione report. Se vengono utilizzate in incognito in modalità, verificare che la proroga ClickOnce sia attivata per incognito nella modalità. È anche possibile modificare un report che viene visualizzato nell'elenco dei report finanziari. Quando l'area attorno al nome del report è selezionata, fare clic si **Modifica** nel Riquadro azioni. Il programma di progettazione report viene avviato.

<a name="see-also"></a>Vedere anche
--------

[View financial reports](view-financial-reports.md)

[Glog sui report finanziari di Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)


