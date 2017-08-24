--- 
title: Progettare un formato per utilizzare gli intervalli espandibili orizzontalmente per aggiungere colonne in modo dinamico ai report di Excel per la creazione di report elettronici (ER)
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la generazione di report come file di fogli di lavoro (Excel) OPENXML in cui le colonne richieste possono essere create in modo dinamico come intervalli espandibili orizzontalmente."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 94898674f02de72111e131f563b33926dda8ac8e
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="design-a-format-to-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-for-electronic-reporting-er"></a>Progettare un formato per utilizzare gli intervalli espandibili orizzontalmente per aggiungere colonne in modo dinamico ai report di Excel per la creazione di report elettronici (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la generazione di report come file di fogli di lavoro (Excel) OPENXML in cui le colonne richieste possono essere create in modo dinamico come intervalli espandibili orizzontalmente. Questi passaggi possono essere eseguiti in qualsiasi società.

Per effettuare queste operazioni, è necessario completare queste tre guide attività: 

"ER Creare un provider di configurazione e contrassegnarlo come attivo"

"ER Utilizzare le dimensioni finanziarie come origine dati (parte 1: progettare il modello dati)"

"ER Utilizzare le dimensioni finanziarie come origine dati (parte 2: mapping del modello)"

È inoltre necessario scaricare e salvare una copia locale del modello con un report di esempio disponibile qui: http://msdynamics.blob.core.windows.net/media/2016/09/SampleFinDimWsReport.xlsx

Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="create-a-new-report-configuration"></a>Creare una nuova configurazione di report
1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
2. Nella struttura selezionare 'Modello di esempio dimensioni finanziarie'.
3. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
4. Nel campo Nuovo immettere 'Formato basato sul modello dati Modello di esempio dimensioni finanziarie'.
    * Utilizzare il modello creato in anticipo come origine dati per il nuovo report.  
5. Nel campo nome digitare 'Report di esempio con intervalli espandibili orizzontalmente'.
    * Report di esempio con intervalli espandibili orizzontalmente  
6. Nel campo Descrizione, digitare 'Creare l'output Excel con l'aggiunta dinamica di colonne'.
    * Creare l'output Excel con l'aggiunta dinamica di colonne  
7. Selezionare Voce nel campo Definizione modello dati.
8. Fare clic su Crea configurazione.

## <a name="design-the-report-format"></a>Progettare il formato del report
1. Fare clic su Progettazione.
2. Attivare l'interruttore 'Mostra dettagli'.
3. Nel Riquadro azioni fare clic su Importa.
4. Fare clic su Importa da Excel.
5. Fare clic su Allegati.
    * Importare il modello di report. Usare il file di Excel di utilizzo scaricato allo scopo.  
6. Fare clic su Nuovo.
7. Fare clic su File.
8. Chiudere la pagina.
9. Nel campo Modello immettere o selezionare un valore.
    * Selezionare il modello scaricato.  
10. Fare clic su OK.
    * Aggiungere un nuovo intervallo per creare in modo dinamico l'output di Excel con il numero di colonne selezionato (nel modulo di dialogo utente) per le dimensioni finanziarie. Ogni cella per ciascuna colonna rappresenterà il nome di una singola dimensione finanziaria.  
11. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
12. Nella struttura selezionare 'Excel\Intervallo'.
13. Nel campo Intervallo Excel, digitare 'DimNames'.
    * DimNames  
14. Selezionare 'Orizzontale' nel campo Direzione replica.
15. Fare clic su OK.
16. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<DimNames>: Orizzontale'.
17. Fare clic su Sposta su.
18. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Cella<DimNames>.
19. Fare clic su Taglia.
20. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<DimNames>: Orizzontale'.
21. Fare clic su Incolla.
22. Nella struttura espandere 'Excel = "SampleFinDimWsReport"\Intervallo<DimNames>: Orizzontale'.
23. Nella struttura espandere 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale'.
24. Nella struttura espandere 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale'.
25. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale'.
    * Aggiungere un nuovo intervallo per creare in modo dinamico l'output di Excel con il numero di colonne selezionato (nel modulo di dialogo utente) per le dimensioni finanziarie. Ogni cella per ciascuna colonna rappresenterà il valore di una singola dimensione finanziaria per ogni transazione nel report.  
26. Fare clic su Aggiungi intervallo.
27. Nel campo Intervallo Excel, digitare 'DimValues'.
    * DimValues  
28. Selezionare 'Orizzontale' nel campo Direzione replica.
29. Fare clic su OK.
30. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Cella<DimValues>'.
31. Fare clic su Taglia.
32. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Intervallo<DimValues>: Orizzontale'.
33. Fare clic su Incolla.
34. Nella struttura espandere 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Intervallo<DimValues>: Orizzontale'.

## <a name="map-format-elements-to-data-sources"></a>Mappare gli elementi di formato alle origini dati
1. Fare clic sulla scheda Mapping.
2. Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie'.
3. Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record'.
4. Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record'.
5. Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record'.
6. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Intervallo<DimValues>: Orizzontale\Cella<DimValues>'.
7. Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Codice: Stringa'.
8. Fare clic su Associa.
9. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Intervallo<DimValues>: Orizzontale'.
10. Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record'.
11. Fare clic su Associa.
12. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Cella<Credit>'.
13. Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Avere: Reale'.
14. Fare clic su Associa.
15. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Cella<Debit>'.
16. Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dare: Reale'.
17. Fare clic su Associa.
18. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Cella<Currency>'.
19. Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Valuta: Stringa'.
20. Fare clic su Associa.
21. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Cella<TransDate>'.
22. Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Data: Data'.
23. Fare clic su Associa.
24. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Cella<TransVoucher>'.
25. Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Giustificativo: Stringa'.
26. Fare clic su Associa.
27. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale\Cella<TransBatch>'.
28. Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Batch: Stringa'.
29. Fare clic su Associa.
30. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Intervallo<TransactionLine>: Verticale'.
31. Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record'.
32. Fare clic su Associa.
33. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale\Cella<Batch>'.
34. Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Batch: Stringa'.
35. Fare clic su Associa.
36. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<JournalLine>: Verticale'.
37. Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record'.
38. Fare clic su Associa.
39. Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Impostazione dimensioni: Elenco di record'.
40. Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Impostazione dimensioni: Elenco di record\Codice: Stringa'.
41. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<DimNames>: Orizzontale\Cella<DimNames>'.
42. Fare clic su Associa.
43. Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Impostazione dimensioni: Elenco di record'.
44. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Intervallo<DimNames>: Orizzontale'.
45. Fare clic su Associa.
46. Nella struttura selezionare 'Excel = "SampleFinDimWsReport"\Cella<CompanyName>.
47. Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Società: Stringa'.
48. Fare clic su Associa.
49. Fare clic su Salva.
50. Chiudere la pagina.


