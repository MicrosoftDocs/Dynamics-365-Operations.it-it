---
title: Impostare il processo di importazione di riconciliazione bancaria avanzata
description: "La funzionalità di riconciliazione bancaria avanzata consente di importare rendiconti bancari elettronici e riconciliarli automaticamente con le transazioni bancarie in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. In questo articolo viene spiegato come impostare le funzionalità di importazione dei rendiconti bancari."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 106853
ms.assetid: 45dae275-ea45-4c7e-b38f-89297c7b5352
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4d7bb0fc5abedcce973632434a5cc174449cdc22
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-the-advanced-bank-reconciliation-import-process"></a>Impostare il processo di importazione di riconciliazione bancaria avanzata

[!include[banner](../includes/banner.md)]


La funzionalità di riconciliazione bancaria avanzata consente di importare rendiconti bancari elettronici e riconciliarli automaticamente con le transazioni bancarie in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. In questo articolo viene spiegato come impostare le funzionalità di importazione dei rendiconti bancari. 

L'impostazione dell'importazione dei rendiconti bancari varia a seconda del formato del rendiconto bancario elettronico. Finance and Operations supporta tre formati di rendiconto bancario predefiniti: ISO20022, MT940 e BAI2.

## <a name="sample-files"></a>File di esempio
Per tutti e tre i formati, è necessario disporre di file che convertono il rendiconto bancario elettronico dal formato originale in un formato che è possibile utilizzare in Finance and Operations. È possibile trovare i file di risorse necessari nel nodo **Risorse** in Application Explorer in Microsoft Visual Studio. Dopo avere individuato i file, copiarli in un'unica posizione nota in modo che sia possibile caricarli più facilmente durante il processo di impostazione.

| Nome risorsa                                           | Nome file                            |
|---------------------------------------------------------|--------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt              | BAI2CSV-to-BAI2XML.xslt              |
| BankStmtImport\_BAI2XML\_to\_Reconciliation\_xslt       | BAI2XML-to-Reconciliation.xslt       |
| BankStmtImport\_BankReconciliation\_to\_Composite\_xslt | BankReconciliation-to-Composite.xslt |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt   | ISO20022XML-to-Reconciliation.xslt   |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt            | MT940TXT-to-MT940XML.xslt            |
| BankStmtImport\_MT940XML\_to\_Reconciliation\_xslt      | MT940XML-to-Reconciliation.xslt      |
| BankStmtImport\_SampleBankCompositeEntity\_xml          | SampleBankCompositeEntity.xml        |

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Esempi di formati di rendiconto bancario e di layout tecnici
Di seguito sono inclusi esempi di definizioni avanzate di layout tecnici dei file di importazione di riconciliazione bancaria e tre file di esempio di rendiconto bancario: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  

| Definizione di layout tecnico                             | File di esempio di rendiconto bancario          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |

 

## <a name="set-up-the-import-of-iso20022-bank-statements"></a>Impostare l'importazione di rendiconti bancari ISO20022
Innanzitutto, è necessario definire il gruppo di elaborazione formati rendiconti bancari per i rendiconti bancari ISO20022 utilizzando il framework di entità di dati.

1.  Passare a **Aree di lavoro** &gt; **Gestione dati**.
2.  Fare clic su **Importa**.
3.  Immettere un nome per il formato, ad esempio **ISO20022**.
4.  Impostare il campo **Formato dati di origine** su **XML-Element**.
5.  Impostare il campo **Nome entità** su **Rendiconti bancari**.
6.  Per caricare i file di importazione, fare clic su **Carica** e quindi individuare per selezionare il file **SampleBankCompositeEntity.xml** salvato in precedenza.
7.  Dopo avere caricato l'entità Rendiconti bancari e il mapping è stato completato, scegliere l'azione **Visualizza mapping** per l'entità.
8.  L'entità Rendiconti bancari è un'entità composita costituita da quattro entità separate. Nell'elenco, selezionare **BankStatementDocumentEntity**, quindi scegliere l'azione **Visualizza mapping**.
9.  Nella scheda **Trasformazioni** , fare clic su **Nuovo**.
10. Per il numero di sequenza 1, fare clic su **Carica file** e selezionare il file **ISO20022XML-to-Reconciliation.xslt** salvato in precedenza. **Nota:** i file di trasformazione di Finance and Operations vengono generati per il formato standard. Poiché le banche spesso divergono da questo formato, potrebbe essere necessario aggiornare il file di trasformazione per eseguire il mapping allo specifico formato del rendiconto bancario. <!-- For details about the expected format for ISO20022, see [Dynamics AX ISO20022 Layout](./media/dynamicsaxiso20022layout1.xlsx).-->
11. Fare clic su **Nuovo**.
12. Per il numero di sequenza 2, fare clic su **Carica file** e selezionare il file **BankReconciliation-to-Composite.xslt** salvato in precedenza.
13. Fare clic su **Applica trasformazioni**.

Dopo aver impostato il gruppo di elaborazione formati, il passaggio successivo consiste nel definire le regole di formato rendiconti bancari relative ai rendiconti bancari ISO20022.

1.  Andare a **Gestione cassa e banche** &gt; **Impostazioni** &gt; **Impostazione riconciliazione bancaria avanzata** &gt; **Formato rendiconto bancario**.
2.  Fare clic su **Nuovo**.
3.  Specificare un formato di rendiconto, ad esempio **ISO20022**.
4.  Immettere un nome per il formato.
5.  Impostare il campo **Gruppo di elaborazione** sul gruppo definito in precedenza, ad esempio **ISO20022**.
6.  Selezionare la casella di controllo **File XML**.

L'ultimo passaggio consiste nell'attivare la riconciliazione bancaria avanzata e impostare il formato di rendiconto sul conto bancario.

1.  Andare a **Gestione cassa e banche** &gt; **Conti bancari**.
2.  Selezionare il conto bancario e aprirlo per visualizzare i dettagli.
3.  Nella scheda **Riconciliazione**, impostare l'opzione **Riconciliazione bancaria avanzata** su **Sì**.
4.  Impostare il campo **Formato rendiconto** sul formato creato in precedenza, ad esempio **ISO20022**.

## <a name="set-up-the-import-of-mt940-bank-statements"></a>Impostare l'importazione di rendiconti bancari MT940
Innanzitutto, è necessario definire il gruppo di elaborazione formati rendiconti bancari per i rendiconti bancari MT940 utilizzando il framework di entità di dati.

1.  Passare a **Aree di lavoro** &gt; **Gestione dati**.
2.  Fare clic su **Importa**.
3.  Immettere un nome per il formato, ad esempio **MT940**.
4.  Impostare il campo **Formato dati di origine** su **XML-Element**.
5.  Impostare il campo **Nome entità** su **Rendiconti bancari**.
6.  Per caricare i file di importazione, fare clic su **Carica** e quindi individuare per selezionare il file **SampleBankCompositeEntity.xml** salvato in precedenza.
7.  Dopo avere caricato l'entità Rendiconti bancari e il mapping è stato completato, scegliere l'azione **Visualizza mapping** per l'entità.
8.  L'entità Rendiconti bancari è un'entità composita costituita da quattro entità separate. Nell'elenco, selezionare **BankStatementDocumentEntity**, quindi scegliere l'azione **Visualizza mapping**.
9.  Nella scheda **Trasformazioni** , fare clic su **Nuovo**.
10. Per il numero di sequenza 1, fare clic su **Carica file** e selezionare il file **MT940TXT-to-MT940XML.xslt** salvato in precedenza.
11. Fare clic su **Nuovo**.
12. Per il numero di sequenza 2, fare clic su **Carica file** e selezionare il file **MT940XML-to-Reconciliation.xslt** salvato in precedenza. **Nota:** i file di trasformazione di Finance and Operations vengono generati per il formato standard. Poiché le banche spesso divergono da questo formato, potrebbe essere necessario aggiornare il file di trasformazione per eseguire il mapping allo specifico formato del rendiconto bancario. <!--- For details about the expected format for MT940, see [Dynamics AX MT940 Layout](./media/dynamicsaxmt940layout1.xlsx)-->
13. Fare clic su **Nuovo**.
14. Per il numero di sequenza 3, fare clic su **Carica file** e selezionare il file **BankReconciliation-to-Composite.xslt** salvato in precedenza.
15. Fare clic su **Applica trasformazioni**.

Dopo aver impostato il gruppo di elaborazione formati, il passaggio successivo consiste nel definire le regole di formato rendiconti bancari relative ai rendiconti bancari MT940.

1.  Andare a **Gestione cassa e banche** &gt; **Impostazioni** &gt; **Impostazione riconciliazione bancaria avanzata** &gt; **Formato rendiconto bancario**.
2.  Fare clic su **Nuovo**.
3.  Specificare un formato di rendiconto, ad esempio **MT940**.
4.  Immettere un nome per il formato.
5.  Impostare il campo **Gruppo di elaborazione** sul gruppo definito in precedenza, ad esempio **MT940**.
6.  Impostare il campo **Tipo di file** su **txt**.

L'ultimo passaggio consiste nell'attivare la riconciliazione bancaria avanzata e impostare il formato di rendiconto sul conto bancario.

1.  Andare a **Gestione cassa e banche** &gt; **Conti bancari**.
2.  Selezionare il conto bancario e aprirlo per visualizzare i dettagli.
3.  Nella scheda **Riconciliazione**, impostare l'opzione **Riconciliazione bancaria avanzata** su **Sì**.
4.  Quando viene chiesto di confermare la selezione e attivare Riconciliazione bancaria avanzata, fare clic su **OK**.
5.  Impostare il campo **Formato rendiconto** sul formato creato in precedenza, ad esempio **MT940**.

## <a name="set-up-the-import-of-bai2-bank-statements"></a>Impostare l'importazione di rendiconti bancari BAI2
Innanzitutto, è necessario definire il gruppo di elaborazione formati rendiconti bancari per i rendiconti bancari BAI2 utilizzando il framework di entità di dati.

1.  Passare a **Aree di lavoro** &gt; **Gestione dati**.
2.  Fare clic su **Importa**.
3.  Immettere un nome per il formato, ad esempio **BAI2**.
4.  Impostare il campo **Formato dati di origine** su **XML-Element**.
5.  Impostare il campo **Nome entità** su **Rendiconti bancari**.
6.  Per caricare i file di importazione, fare clic su **Carica** e quindi individuare per selezionare il file **SampleBankCompositeEntity.xml** salvato in precedenza.
7.  Dopo avere caricato l'entità Rendiconti bancari e il mapping è stato completato, scegliere l'azione **Visualizza mapping** per l'entità.
8.  L'entità Rendiconti bancari è un'entità composita costituita da quattro entità separate. Nell'elenco, selezionare **BankStatementDocumentEntity**, quindi scegliere l'azione **Visualizza mapping**.
9.  Nella scheda **Trasformazioni** , fare clic su **Nuovo**.
10. Per il numero di sequenza 1, fare clic su **Carica file** e selezionare il file **BAI2CSV-to-BAI2XML.xslt** salvato in precedenza.
11. Fare clic su **Nuovo**.
12. Per il numero di sequenza 2, fare clic su **Carica file** e selezionare il file **BAI2XML-to-Reconciliation.xslt** salvato in precedenza. **Nota:** i file di trasformazione di Finance and Operations vengono generati per il formato standard. Poiché le banche spesso divergono da questo formato, potrebbe essere necessario aggiornare il file di trasformazione per eseguire il mapping allo specifico formato del rendiconto bancario. <!--- For details about the expected format for BAI2, see [Dynamics AX BAI2 Layout](./media/dynamicsaxbai2layout1.xlsx).-->
13. Fare clic su **Nuovo**.
14. Per il numero di sequenza 3, fare clic su **Carica file** e selezionare il file **BankReconciliation-to-Composite.xslt** salvato in precedenza.
15. Fare clic su **Applica trasformazioni**.

Dopo aver impostato il gruppo di elaborazione formati, il passaggio successivo consiste nel definire le regole di formato rendiconti bancari relative ai rendiconti bancari BAI2.

1.  Andare a **Gestione cassa e banche** &gt; **Impostazioni** &gt; **Impostazione riconciliazione bancaria avanzata** &gt; **Formato rendiconto bancario**.
2.  Fare clic su **Nuovo**.
3.  Specificare un formato di rendiconto, ad esempio **BAI2**.
4.  Immettere un nome per il formato.
5.  Impostare il campo **Gruppo di elaborazione** sul gruppo definito in precedenza, ad esempio **BAI2**.
6.  Impostare il campo **Tipo di file** su **txt**.

L'ultimo passaggio consiste nell'attivare la riconciliazione bancaria avanzata e impostare il formato di rendiconto sul conto bancario.

1.  Andare a **Gestione cassa e banche** &gt; **Conti bancari**.
2.  Selezionare il conto bancario e aprirlo per visualizzare i dettagli.
3.  Nella scheda **Riconciliazione**, impostare l'opzione **Riconciliazione bancaria avanzata** su **Sì**.
4.  Quando viene chiesto di confermare la selezione e attivare Riconciliazione bancaria avanzata, fare clic su **OK**.
5.  Impostare il campo **Formato rendiconto** sul formato creato in precedenza, ad esempio **BAI2**.

## <a name="test-the-bank-statement-import"></a>Testare l'importazione rendiconto bancario
Il passaggio finale consiste nel verificare che è possibile importare il rendiconto bancario.

1.  Andare a **Gestione cassa e banche** &gt; **Conti bancari**.
2.  Selezionare il conto bancario per cui è abilitata la funzionalità Riconciliazione bancaria avanzata.
3.  Nella scheda **Riconcilia** , fare clic su **Rendiconti bancari**.
4.  Nella pagina **Rendiconto bancario** fare clic su **Importa rendiconto**.
5.  Impostare il campo **Conto bancario** sul conto bancario selezionato. Il campo **Formato rendiconto** verrà impostato automaticamente, in base all'impostazione del conto bancario.
6.  Fare clic su **Sfoglia** e selezionare il file di rendiconto bancario elettronico.
7.  Fare clic su **Carica**.
8.  Scegliere **OK**.

Se l'importazione ha esito positivo, riceverai un messaggio che informa che il rendiconto è stato importato. Se l'importazione non è stata completata correttamente, nell'area di lavoro **Gestione dati**, sezione **Storico processi**, trovare il processo. Fare clic su **Dettagli esecuzione** per il processo per aprire la pagina **Riepilogo esecuzione** e quindi fare clic su **Visualizza registro di esecuzione** per visualizzare gli errori di importazione.




