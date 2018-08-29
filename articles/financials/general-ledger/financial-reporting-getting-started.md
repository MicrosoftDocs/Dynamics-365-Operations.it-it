---
title: Creazione di report finanziari
description: "In questo argomento viene descritto dove accedere ai report finanziari in Microsoft Dynamics 365 for Finance and Operations e come utilizzare le funzionalità dei report finanziari. Include una descrizione dei report finanziari predefiniti forniti."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 83648a93f367510d7b04bbd04a9f37689ecfaa59
ms.openlocfilehash: 613fcf941576b9fb05f5c059699e4cc9c4cabe3e
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---

# <a name="financial-reporting"></a>Creazione di report finanziari

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto dove accedere ai report finanziari in Microsoft Dynamics 365 for Finance and Operations e come utilizzare le funzionalità dei report finanziari. Include una descrizione dei report finanziari predefiniti forniti.

<a name="accessing-financial-reporting"></a>Accesso ai report finanziari
-----------------------------

È possibile trovare il menu **Report finanziari** nei seguenti percorsi in Finance and Operations:

-   **Contabilità generale** &gt; **Richieste di informazioni e report**
-   **Impostazione budget** &gt; **Richieste di informazioni e report** &gt; **Impostazione budget di base**
-   **Impostazione budget** &gt; **Richieste di informazioni e report** &gt; **Pianificazione del budget**
-   **Impostazione budget** &gt; **Richieste di informazioni e report** &gt; **Controllo del budget**
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
| Gestisci report finanziari            | Gestisci report finanziari            | Direttore amministrativo, Supervisore contabile, Supervisore finanziario, Responsabile budget |
| Genera report finanziari            | Genera report finanziari            | CEO, CFO, Contabile                                                            |
| Visualizza report finanziari                | Esamina prestazioni finanziarie          | Nessuno assegnato                                                                   |

Dopo che un utente viene aggiunto o un ruolo viene modificato, l'utente deve poter accedere ai report finanziari in alcuni minuti. **Nota:** il ruolo sysadmin viene aggiunto a tutti i ruoli nella creazione di report finanziari.

## <a name="default-reports"></a>Report predefiniti
Report finanziari fornisce 22 report finanziari predefiniti. Ogni report utilizza le categorie di conti principali predefinite in Finance and Operations. È possibile utilizzare questi report come sono o come punto di partenza per i report finanziari necessari. Oltre ai rendiconti finanziari tradizionali, ad esempio il conto economico e lo stato patrimoniale, questi report predefiniti includono report che illustrano i diversi tipi di report finanziari che è possibile creare. 

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
Quando si fa clic sul menu **Report finanziari**, l'elenco dei report finanziari predefiniti per la società viene visualizzato. È quindi possibile aprire o modificare un report. Per aprire uno dei report predefiniti, selezionare il nome del report. La prima volta che un report viene aperto, viene generato automaticamente per il mese precedente. Ad esempio, se si apre un report per la prima volta nell'agosto 2016, il report viene generato per il 31 luglio 2016. Dopo l'apertura di un report, puoi iniziare a esplorarlo eseguendo il drill-down su parti specifiche di dati e modificando le opzioni di report.

## <a name="creating-and-modifying-financial-reports"></a>Creazione e modifica di report finanziari
Nell'elenco dei report finanziari, è possibile creare un nuovo report o modificare un report esistente. Se si dispone delle autorizzazioni appropriate, è possibile creare un nuovo report finanziario facendo clic su **Nuovo** nel riquadro azioni. Viene scaricato un programma di progettazione nel dispositivo. Dopo aver avviato la progettazione report, è possibile creare il nuovo report. Dopo aver salvato il nuovo report, verrà visualizzato nell'elenco dei report finanziari. Nell'elenco vengono visualizzati solo i report creati per la società utilizzata in Finance and Operations. Per ulteriori informazioni sul processo di creazione e di modifica dei report finanziari in Finance and Operations, fare riferimento a questi [post di blog](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/tag/learning/) nel blog della funzionalità di report finanziari di Dynamics. **Nota:** nel computer su cui si scarica il client per la progettazione di report è necessario che sia installata la versione 4.6.2 di Microsoft .NET Framework. È possibile scaricare e installare questa versione di Microsoft .NET Framework da [qui](https://www.microsoft.com/en-us/download/details.aspx?id=53345). Se si utilizza Chrome, è necessario installare l'estensione ClickOnce per scaricare il client per la progettazione di report. Se si utilizza la modalità in incognito, assicurarsi che l'estensione ClickOnce sia attiva in tale modalità. È anche possibile modificare un report che viene visualizzato nell'elenco dei report finanziari. Quando l'area attorno al nome del report è selezionata, fare clic si **Modifica** nel Riquadro azioni. Il programma di progettazione report viene avviato.

## <a name="additional-resources"></a>Risorse aggiuntive
- [Visualizzare i report finanziari](view-financial-reports.md)
- [Glog sui report finanziari di Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)




