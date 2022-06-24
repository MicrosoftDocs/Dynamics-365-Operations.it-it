---
title: 'ER Utilizzare intervalli espandibili orizzontalmente per aggiungere dinamicamente le colonne in report di Excel (Parte 1: progettare il formato)'
description: Questo articolo descrive come configurare un formato di creazione di report elettronici (ER) per generare report come file di fogli di lavoro OPENXML (Excel). (Parte 1)
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 157a486252d9447c2509fe5e05b02cf1684683fd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886735"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-1---design-format"></a>ER Utilizzare intervalli espandibili orizzontalmente per aggiungere dinamicamente le colonne in report di Excel (Parte 1: progettare il formato)

[!include [banner](../../includes/banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la generazione di report come file di fogli di lavoro (Excel) OPENXML in cui le colonne richieste possono essere create in modo dinamico come intervalli espandibili orizzontalmente. Questi passaggi possono essere eseguiti in qualsiasi società.

Per effettuare queste operazioni, è necessario completare queste tre guide attività:

"ER Creare un provider di configurazione e contrassegnarlo come attivo"

"ER Utilizzare le dimensioni finanziarie come origine dati (Parte 1: progettare il modello dati)"

"ER Utilizzare le dimensioni finanziarie come origine dati (Parte 2: mapping del modello)"

È inoltre necessario scaricare e salvare una copia locale del modello con un report di esempio disponibile qui, [Report servizio Web dimensioni finanziarie di esempio](https://download.microsoft.com/download/3/1/3/313e2090-bc0a-421f-bf96-c58da9bc0dea/SampleFinDimWsReport.xlsx).

Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.

## <a name="create-a-new-report-configuration"></a>Creare una nuova configurazione di report

1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
2. Nella struttura selezionare `Financial dimensions sample model`.
3. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
4. Nel campo Nuovo, immettere `Format based on data model Financial dimensions sample model`.
    * Utilizzare il modello creato in anticipo come origine dati per il nuovo report.  
5. Nel campo Nome, digitare `Sample report with horizontally expandable ranges`.
    * Report di esempio con intervalli espandibili orizzontalmente  
6. Nel campo Descrizione, digitare `To make Excel output with dynamically adding columns`.
    * Creare l'output Excel con l'aggiunta dinamica di colonne  
7. Selezionare Voce nel campo Definizione modello dati.
8. Fare clic su Crea configurazione.

## <a name="design-the-report-format"></a>Progettare il formato del report

1. Fare clic su Progettazione.
2. Attivare l'interruttore `Show details`.
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
12. Nella struttura selezionare `Excel\Range`.
13. Nel campo Intervallo Excel, digitare `DimNames`.
    * DimNames  
14. Selezionare `Horizontal` nel campo Direzione replica.
15. Fare clic su OK.
16. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
17. Fare clic su Sposta su.
18. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Cell<DimNames>`.
19. Fare clic su Taglia.
20. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
21. Fare clic su Incolla.
22. Nella struttura espandere `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
23. Nella struttura espandere `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical`.
24. Nella struttura espandere `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`.
25. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`.
    * Aggiungere un nuovo intervallo per creare in modo dinamico l'output di Excel con il numero di colonne selezionato (nel modulo di dialogo utente) per le dimensioni finanziarie. Ogni cella per ciascuna colonna rappresenterà il valore di una singola dimensione finanziaria per ogni transazione nel report.  
26. Fare clic su Aggiungi intervallo.
27. Nel campo Intervallo Excel, digitare `DimValues`.
    * DimValues  
28. Selezionare `Horizontal` nel campo Direzione replica.
29. Fare clic su OK.
30. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<DimValues>`.
31. Fare clic su Taglia.
32. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`.
33. Fare clic su Incolla.
34. Nella struttura espandere `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`.

## <a name="map-format-elements-to-data-sources"></a>Mappare gli elementi di formato alle origini dati

1. Fare clic sulla scheda Mapping.
2. Nella struttura espandere `model: Data model Financial dimensions sample model`.
3. Nella struttura espandere `model: Data model Financial dimensions sample model\Journal: Record list`.
4. Nella struttura espandere `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list`.
5. Nella struttura espandere `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list`.
6. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal\Cell<DimValues>`.
7. Nella struttura selezionare `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String`.
8. Fare clic su Associa.
9. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`.
10. Nella struttura selezionare `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list`.
11. Fare clic su Associa.
12. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Credit>`.
13. Nella struttura selezionare `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real`.
14. Fare clic su Associa.
15. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Debit>`.
16. Nella struttura selezionare `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real`.
17. Fare clic su Associa.
18. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Currency>`.
19. Nella struttura selezionare `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String`.
20. Fare clic su Associa.
21. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransDate>`.
22. Nella struttura selezionare `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date`.
23. Fare clic su Associa.
24. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransVoucher>`.
25. Nella struttura selezionare `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String`.
26. Fare clic su Associa.
27. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransBatch>`.
28. Nella struttura selezionare `model: Data model Financial dimensions sample model\Journal: Record list\Batch: String`.
29. Fare clic su Associa.
30. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`.
31. Nella struttura selezionare `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list`.
32. Fare clic su Associa.
33. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Cell<Batch>`.
34. Nella struttura selezionare `model: Data model Financial dimensions sample model\Journal: Record list\Batch: String`.
35. Fare clic su Associa.
36. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical`.
37. Nella struttura selezionare `model: Data model Financial dimensions sample model\Journal: Record list`.
38. Fare clic su Associa.
39. Nella struttura espandere `model: Data model Financial dimensions sample model\Dimensions setting: Record list`.
40. Nella struttura selezionare `model: Data model Financial dimensions sample model\Dimensions setting: Record list\Code: String`.
41. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal\Cell<DimNames>`.
42. Fare clic su Associa.
43. Nella struttura selezionare `model: Data model Financial dimensions sample model\Dimensions setting: Record list`.
44. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
45. Fare clic su Associa.
46. Nella struttura selezionare `Excel = "SampleFinDimWsReport"\Cell<CompanyName>`.
47. Nella struttura selezionare `model: Data model Financial dimensions sample model\Company: String`.
48. Fare clic su Associa.
49. Fare clic su Salva.
50. Chiudere la pagina.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
