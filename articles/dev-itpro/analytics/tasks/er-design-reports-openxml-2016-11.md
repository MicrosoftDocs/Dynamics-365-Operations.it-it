--- 
title: Progettare una configurazione per la generazione di report in formato OpenXML per la creazione di report elettronici (ER)
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) che contiene un modello per la generazione di documenti elettronici in formato OPENXML."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 04def14ddf9b079005bf11acbcaf64b21aa80fdb
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="design-a-configuration-for-generating-reports-in-openxml-format-for-electronic-reporting-er"></a>Progettare una configurazione per la generazione di report in formato OpenXML per la creazione di report elettronici (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) che contiene un modello per la generazione di documenti elettronici in formato OPENXML. La configurazione verrà utilizzata per elaborare i pagamenti fornitore.



In questo esempio verrà creata una configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite nella società GBSI.



Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo". È inoltre necessario disporre di un file Excel che verrà importato in fase di creazione del modello. Questo file è accessibile in: https://msdynamics.blob.core.windows.net/media/2016/04/SampleVendPaymWsReport.xlsx


## <a name="upload-the-payments-data-model-configuration"></a>Caricare la configurazione del modello dati Pagamenti
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare il provider di configurazione per la società di esempio Litware, Inc. Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".  
3. Fare clic su Imposta attivo.
4. Fare clic su Archivi.
    * Selezionare un archivio per il tipo Risorse Operations, se disponibile. Se è disponibile, ignorare i passaggi seguenti che riguardano la creazione di un nuovo archivio.  
5. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
6. Nel campo Tipo di archivio di configurazioni immettere 'Risorse operative'.
7. Fare clic su Crea archivio.
8. Fare clic su OK.
9. Fare clic su Apri.
10. Nella struttura selezionare "Modello di pagamento".
11. Fare clic su Importa.
    * Importare questo modello dati. Verrà utilizzato come origine dati in nuova configurazione del formato. Ignorare questo passaggio se la configurazione è già stata importata.  
12. Fare clic su Sì.
13. Chiudere la pagina.
14. Chiudere la pagina.

## <a name="create-a-new-format-configuration"></a>Creare una nuova configurazione di formato
1. Fare clic su Configurazioni report.
2. Nella struttura selezionare "Modello di pagamento".
3. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
4. Nel campo Nuovo immettere "Formato in base al modello dati PaymentModel".
    * Creare un formato basato sul modello dati PaymentModel.  
5. Nel campo Nome digitare "Report foglio di lavoro di esempio".
    * Report foglio di lavoro di esempio  
6. Nel campo Descrizione immettere “Report foglio di lavoro per i pagamenti dei fornitori".
    * Report foglio di lavoro per i pagamenti dei fornitori.  
7. Nel campo Definizione modello dati immettere o selezionare un valore.
    * Selezionare la definizione "CustomerCreditTransferInitiation".  
8. Fare clic su Crea configurazione.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>Progettare un nuovo documento nel formato foglio di lavoro OPENXML
1. Nella struttura selezionare "Modello di pagamento\Report foglio di lavoro di esempio".
2. Fare clic su Progettazione.
3. Nel Riquadro azioni fare clic su Importa.
4. Fare clic su Importa da Excel.
5. Fare clic su Allegati.
    * Collegare il documento di Excel esistente come modello.  
6. Fare clic su Nuovo.
7. Fare clic su File.
    * Puntare al file di Excel esistente.  
8. Chiudere la pagina.
9. Nel campo Modello immettere o selezionare un valore.
    * Selezionare il file di Excel allegato da utilizzare come modello.  
10. Fare clic su OK.
    * I componenti del formato ER sono stati creati nel formato di progettazione basato sulla struttura del documento MS Excel di riferimento (intervalli denominati).  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>Creare una nuova origine dati per calcolare i totali dei codici valuta
1. Fare clic sulla scheda Mapping.
2. Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.
3. Nella struttura selezionare "Funzioni\Raggruppa per".
4. Nel campo Nome digitare "PaymentByCurrency".
    * PaymentByCurrency  
5. Fare clic su Modifica gruppo per.
6. Nella struttura , espandere il "modello".
7. Nella struttura selezionare "modello\Pagamenti".
8. Fare clic su Aggiungi campo a.
9. Fare clic su Informazioni da raggruppare.
10. Nella struttura espandere "modello\Pagamenti".
11. Nella struttura selezionare "modello\Pagamenti\Valuta".
12. Fare clic su Aggiungi campo a.
13. Fare clic su Campi raggruppati.
14. Nella struttura selezionare "modello\Pagamenti\Importo istruito(InstructedAmount)".
15. Fare clic su Aggiungi campo a.
16. Fare clic su Campi di aggregazione.
17. Selezionare un'opzione nel campo Metodo.
    * Selezionare la funzione di aggregazione SOMMA.  
18. Nel campo Nome digitare "TotalInstructuredAmount".
    * TotalInstructuredAmount  
19. Fare clic su Salva.
20. Chiudere la pagina.
21. Fare clic su OK.

## <a name="map-format-components-to-data-sources"></a>Eseguire il mapping dei componenti del formato alle origini dati
1. Nella struttura , espandere il "modello".
2. Nella struttura espandere "modello\Pagamenti".
3. Nella struttura espandere "modello\Pagamenti\Parte che inizia la transazione(InitiatingParty)".
4. Nella struttura selezionare "modello\Pagamenti\Parte che inizia la transazione(InitiatingParty)\Nome".
5. Nella struttura espandere 'Excel\ReportHeader'.
6. Nella struttura selezionare 'Excel\ReportHeader\CompanyName'.
7. Fare clic su Associa.
8. Nella struttura espandere "modello\Pagamenti\Creditore".
9. Nella struttura espandere "modello\Pagamenti\Creditore\Identificazione".
10. Nella struttura selezionare "modello\Pagamenti\Creditore\Identificazione\ID origine(SourceID)".
11. Nella struttura espandere 'Excel\PaymLines'.
12. Nella struttura selezionare 'Excel\PaymLines\VendAccountName'.
13. Fare clic su Associa.
14. Nella struttura selezionare "modello\Pagamenti\Creditore\Nome".
15. Nella struttura selezionare 'Excel\PaymLines\VendName'.
16. Fare clic su Associa.
17. Nella struttura espandere "modello\Pagamenti\Agente creditore(CreditorAgent)".
18. Nella struttura selezionare "modello\Pagamenti\Agente creditore(CreditorAgent)\Nome".
19. Nella struttura selezionare 'Excel\PaymLines\Banca'.
20. Fare clic su Associa.
21. Nella struttura selezionare "modello\Pagamenti\Agente creditore(CreditorAgent)\Numero di registrazione(RoutingNumber)".
22. Nella struttura selezionare 'Excel\PaymLines\RoutingNumber'.
23. Fare clic su Associa.
24. Nella struttura, espandere "modello\Pagamenti\Conto creditore(CreditorAccount)".
25. Nella struttura, espandere "modello\Pagamenti\Conto creditore(CreditorAccount)\Identificazione".
26. Nella struttura selezionare "modello\Pagamenti\Conto creditore(CreditorAccount)\Identificazione\Numero".
27. Nella struttura selezionare 'Excel\PaymLines\AccountNumber'.
28. Fare clic su Associa.
29. Nella struttura selezionare "modello\Pagamenti\Importo istruito(InstructedAmount)".
30. Nella struttura selezionare 'Excel\PaymLines\Debit'.
31. Fare clic su Associa.
32. Nella struttura espandere "modello\Pagamenti\Creditore".
33. Nella struttura, espandere "modello\Pagamenti\Conto creditore(CreditorAccount)".
34. Nella struttura espandere "modello\Pagamenti\Agente creditore(CreditorAgent)".
35. Nella struttura selezionare "modello\Pagamenti\Valuta".
36. Nella struttura selezionare 'Excel\PaymLines\Valuta'.
37. Fare clic su Associa.
38. Nella struttura espandere "PaymentByCurrency".
39. Nella struttura espandere "PaymentByCurrency\raggruppato".
40. Nella struttura selezionare "PaymentByCurrency\raggruppato\Valuta".
41. Nella struttura espandere 'Excel\SummaryLines'.
42. Nella struttura selezionare 'Excel\SummaryLines\SummaryCurrency'.
43. Fare clic su Associa.
44. Nella struttura espandere "PaymentByCurrency\aggregato".
45. Nella struttura selezionare "PaymentByCurrency\aggregato\TotalInstructuredAmount".
46. Nella struttura selezionare 'Excel\SummaryLines\SummaryAmount'.
47. Fare clic su Associa.
48. Nella struttura selezionare "PaymentByCurrency".
49. Nella struttura selezionare 'Excel\SummaryLines'.
50. Fare clic su Associa.
51. Nella struttura selezionare "modello\Pagamenti".
52. Nella struttura selezionare 'Excel\PaymLines'.
53. Fare clic su Associa.
54. Fare clic su Salva.
55. Chiudere la pagina.

## <a name="use-the-created-configuration-for-payments-processing"></a>Utilizzare la configurazione creata per l'elaborazione di pagamenti
1. Fare clic su Cambia stato.
2. Fare clic su Completa.
3. Fare clic su OK.
4. Chiudere la pagina.
5. Chiudere la pagina.
6. Andare a Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento.
7. Utilizzare il filtro rapido per filtrare il campo Metodo di pagamento in base a un valore di 'Electronic'.
    * elettroniche  
8. Fare clic su Modifica.
9. Espandere la sezione Formati file.
10. Selezionare Sì nel campo Report elettronici generici.
11. Nel campo Esporta configurazione formato immettere o selezionare un valore.
    * Selezionare la configurazione "Report foglio di lavoro di esempio".  
12. Fare clic su Salva.
13. Chiudere la pagina.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>Utilizzare la configurazione creata per testare l'elaborazione dei giornali di registrazione pagamenti
1. Andare a Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti.
2. Fare clic su Nuovo.
    * Creare un nuovo giornale di registrazione pagamenti.  
3. Digitare 'VendPay' nel campo Nome.
    * VendPay  
4. Fare clic su Righe.
5. Nel campo Conto specificare i valori "GB_SI_000001".
    * GB_SI_000001  
6. Impostare Dare su "1000".
7. Fare clic su Nuovo.
8. Nel campo Conto specificare i valori "GB_SI_000005".
    * GB_SI_000005  
9. Impostare Dare su "2000".
10. Digitare "EUR" nel campo Valuta.
    * EUR  
11. Nel campo Conto di contropartita specificare i valori "GBSI OPER".
    * GBSI OPER  
12. Digitare "Elettronico" nel campo Metodo di pagamento.
    * elettroniche  
13. Fare clic su Salva.
14. Fare clic su Genera pagamenti.
15. Digitare "Elettronico" nel campo Metodo di pagamento.
    * elettroniche  
16. Digitare 'Payments' nel campo Nome file.
    * Ad esempio, digitare Pagamenti.  
17. Nel campo Conto bancario digitare "GBSI OPER".
    * GBSI OPER  
18. Fare clic su OK.
19. Fare clic su OK.
    * Verificare il foglio di lavoro creato, inclusi i dettagli delle righe di pagamento, nonché i totali per ciascun codice valuta utilizzato nel messaggio di pagamento.  


