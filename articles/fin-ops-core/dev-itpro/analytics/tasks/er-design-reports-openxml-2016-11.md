---
title: ER Progettare una configurazione per la creazione di report nel formato OPENXML (novembre 2016)
description: In questo argomento viene descritto come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) che contiene un modello per la generazione di documenti elettronici in formato OPENXML.
author: NickSelin
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERModelGroupByFunctionEditor, VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fcceb0e4d5f3bec54598515da0a5cbd8d11def3d
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769857"
---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a>ER Progettare una configurazione per la creazione di report nel formato OPENXML (novembre 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questo argomento viene descritto come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) che contiene un modello per la generazione di documenti elettronici in formato OPENXML. La configurazione verrà utilizzata per elaborare i pagamenti fornitore.

In questo esempio verrà creata una configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite nella società GBSI.

Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo". È inoltre necessario disporre di un file Excel che verrà importato in fase di creazione del modello. È possibile accedere a questo file dal [Modello di Report di pagamento](https://go.microsoft.com/fwlink/?linkid=862266).


## <a name="upload-the-payments-data-model-configuration"></a>Caricare la configurazione del modello dati Pagamenti
1. Nel pannello di navigazione andare a **Moduli > Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici**.
2. Nell'elenco, contrassegnare il provider di configurazione per la società di esempio Litware, Inc. Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi della procedura [Creare fornitori di configurazioni e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md).
3. Selezionare **Imposta come attivo**.
4. Selezionare **Archivi**. Selezionare un archivio per il tipo Risorse Operations, se disponibile. Se è disponibile, ignorare i passaggi seguenti che riguardano la creazione di un nuovo archivio.  
5. Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.
6. Nel campo **Tipo di archivio di configurazioni**, immettere `Operations resourcesdd`.
7. Selezionare **Crea archivio**.
8. Selezionare **OK**.
9. Selezionare **Apri**.
10. Nella struttura selezionare **Modello di pagamento**.
11. Selezionare **Importa**. Importare questo modello dati. Verrà utilizzato come origine dati in nuova configurazione del formato. Ignorare questo passaggio se la configurazione è già stata importata.  
12. Selezionare **Sì**.
13. Chiudere le pagine fino a che non viene visualizzata di nuovo la pagina Creazione di report elettronici.

## <a name="create-a-new-format-configuration"></a>Creare una nuova configurazione di formato
1. Selezionare **Configurazioni report**.
2. Nella struttura selezionare **Modello di pagamento**.
3. Selezionare **Crea configurazione** per aprire la finestra di dialogo a discesa.
4. Nel campo **Nuovo** immettere `Format based on data model PaymentModel`. Creare un formato basato sul modello dati PaymentModel.
5. Nel campo **Nome**, digitare `Sample worksheet report`. Report foglio di lavoro di esempio  
6. Nel campo **Descrizione**, digitare `Sample worksheet report for vendors’ payments`. Report foglio di lavoro per i pagamenti dei fornitori.  
7. Nel campo **Definizione modello dati** immettere o selezionare un valore. Selezionare la definizione **CustomerCreditTransferInitiation**.  
8. Selezionare **Crea configurazione**.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>Progettare un nuovo documento nel formato foglio di lavoro OPENXML
1. Nella struttura selezionare **Modello di pagamento\Report foglio di lavoro di esempio**.
2. Selezionare **Progettazione**.
3. Nel riquadro azioni, selezionare **Importa**.
4. Selezionare **Importa da Excel**.
5. Selezionare **Allegati**. Collegare il documento di Excel esistente come modello.  
6. Selezionare **Nuovo**.
7. Selezionare **File**. Puntare al file di Excel esistente.  
8. Chiudere la pagina.
9. Nel campo **Modello** immettere o selezionare un valore. Selezionare il file di Excel allegato da utilizzare come modello.  
10. Selezionare **OK**. I componenti del formato ER sono stati creati nel formato di progettazione basato sulla struttura del documento MS Excel di riferimento (intervalli denominati).  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>Creare una nuova origine dati per calcolare i totali dei codici valuta
1. Selezionare la scheda **Mapping**.
2. Selezionare **Aggiungi radice** per aprire la finestra di dialogo a discesa.
3. Nella struttura selezionare **Funzioni\Raggruppa per**.
4. Nel campo **Nome**, digitare `PaymentByCurrency`.
5. Selezionare **Modifica gruppo per**.
6. Nella struttura espandere **model**, quindi selezionare **model\Payments**.
7. Selezionare **Aggiungi campo a**.
8. Selezionare **Informazioni da raggruppare**.
9. Nella struttura espandere **model\Payments**, quindi selezionare **model\Payments\Currency**.
10. Selezionare **Aggiungi campo a**.
11. Selezionare **Campi raggruppati**.
12. Nella struttura selezionare **model\Payments\Instructed Amount(InstructedAmount)**.
13. Selezionare **Aggiungi campo a**, quindi selezionare **Campi di aggregazione**.
14. Selezionare un'opzione nel campo **Metodo**. Selezionare la funzione **Aggregazione SOMMA**.  
15. Nel campo **Nome**, digitare `TotalInstructuredAmount`.
16. Selezionare **Salva**.
17. Chiudere la pagina.
18. Selezionare **OK**.

## <a name="map-format-components-to-data-sources"></a>Eseguire il mapping dei componenti del formato alle origini dati
1. Nella struttura selezionare **model\Payments\Initiating Party(InitiatingParty)\Name** e **Excel\ReportHeader\CompanyName**.
2. Selezionare **Associa**.
3. Nella struttura selezionare **model\Payments\Creditor\Identification\Source ID(SourceID)** e **Excel\PaymLines\VendAccountName**.
4. Selezionare **Associa**.
5. Nella struttura selezionare **model\Payments\Creditor\Name** e **Excel\PaymLines\VendName**.
6. Selezionare **Associa**.
7. Nella struttura selezionare **model\Payments\Creditor Agent(CreditorAgent)\Name** e **Excel\PaymLines\Bank**.
8. Selezionare **Associa**.
9. Nella struttura selezionare **model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)** e **Excel\PaymLines\RoutingNumber**.
10. Selezionare **Associa**.
11. Nella struttura selezionare **model\Payments\Creditor Account(CreditorAccount)\Identification\Number** e **Excel\PaymLines\AccountNumber**.
12. Selezionare **Associa**.
13. Nella struttura selezionare **model\Payments\Instructed Amount(InstructedAmount)** e **Excel\PaymLines\Debit**.
14. Selezionare **Associa**.
15. Nella struttura selezionare **model\Payments\Currency** e **Excel\PaymLines\Currency**.
16. Selezionare **Associa**.
17. Nella struttura selezionare **PaymentByCurrency\grouped\Currency** e **Excel\SummaryLines\SummaryCurrency**.
18. Selezionare **Associa**.
19. Nella struttura selezionare **PaymentByCurrency\aggregated\TotalInstructuredAmount** e **Excel\SummaryLines\SummaryAmount**.
20. Selezionare **Associa**.
21. Nella struttura selezionare **PaymentByCurrency** e **Excel\SummaryLines**.
22. Selezionare **Associa**.
23. Nella struttura selezionare **model\Payments** e **Excel\PaymLines**.
24. Selezionare **Associa**.
25. Selezionare **Salva**, quindi chiudere la pagina.

## <a name="use-the-created-configuration-for-payments-processing"></a>Utilizzare la configurazione creata per l'elaborazione di pagamenti
1. Selezionare **Cambia stato**.
2. Selezionare **Completa**.
3. Selezionare **OK**.
4. Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento**.
5. Utilizzare il filtro rapido per filtrare il campo **Metodo di pagamento** in base a un valore di **Electronic**.
6. Selezionare **Modifica**.
7. Espandere la sezione **Formati file**.
8. Selezionare **Sì** nel campo **Report elettronici generici**.
9. Nel campo **Esporta configurazione formato** immettere o selezionare un valore. Selezionare la configurazione **Report foglio di lavoro di esempio**.  
10. Selezionare **Salva**.
11. Chiudere la pagina.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>Utilizzare la configurazione creata per testare l'elaborazione dei giornali di registrazione pagamenti
1. Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti**.
2. Selezionare **Nuovo** per creare un nuovo giornale di registrazione pagamenti.
3. Digitare **VendPay** nel campo **Nome**.
4. Selezionare **Righe**.
5. Nel campo **Account** specificare i valori `GB_SI_000001`.
6. Impostare **Dare** su `1000`.
7. Selezionare **Nuovo**.
8. Nel campo **Account** specificare i valori `GB_SI_000005`.
9. Impostare **Dare** su `2000`.
10. Digitare `EUR` nel campo **Valuta**.
11. Nel campo **Conto di contropartita** specificare i valori `GBSI OPER`.
12. Nel campo **Metodo di pagamento**, digitare `Electronic`.
13. Selezionare **Salva**.
14. Selezionare **Genera pagamenti**.
15. Nel campo **Metodo di pagamento**, digitare `Electronic`.
16. Nel campo **Nome file** digitare `Payments`.
17. Nel campo **Conto bancario** digitare `GBSI OPER`.
18. Selezionare **OK** e quindi di nuovo **OK**. Verificare il foglio di lavoro creato, inclusi i dettagli delle righe di pagamento, nonché i totali per ciascun codice valuta utilizzato nel messaggio di pagamento.  

