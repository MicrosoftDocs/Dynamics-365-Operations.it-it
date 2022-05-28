---
title: Risoluzione dei problemi di importazione di file di rendiconto bancario
description: Questo articolo spiega come correggere i problemi causati da piccole differenze nel file di rendiconto bancario.
author: panolte
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: kfend
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 422b2df6c4de3a948b0e62bfb70f99b12e04a8f9
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711175"
---
# <a name="bank-statement-file-import-troubleshooting"></a>Risoluzione dei problemi di importazione di file di rendiconto bancario

[!include [banner](../includes/banner.md)]

È importante che il file di rendiconto bancario della banca corrisponda al layout supportato da Microsoft Dynamics 365 Finance. A causa dei rigorosi standard per i rendiconti bancari, la maggior parte delle integrazioni funzionerà correttamente. Tuttavia, talvolta il file di rendiconto non può essere importato o contiene risultati non corretti. In genere, questi ultimi problemi sono provocati da piccole differenze nel file di rendiconto bancario. In questo articolo viene descritto come risolvere tali differenze e risolvere i problemi.

## <a name="what-is-the-error"></a>Qual è l'errore?

Dopo aver tentato di importare un file di rendiconto bancario, passare allo storici processi della gestione dati e ai dettagli di esecuzione per individuare l'errore. L'errore potrà aiutare a indicare il rendiconto, il saldo o la riga del rendiconto. Tuttavia, è improbabile che tali informazioni siano sufficienti per identificare il campo o l'elemento che causa il problema.

> [!NOTE]
> Gli estratti conto bancari importati possono sovrapporsi solo per un singolo punto nel tempo.  Ad esempio, se un rendiconto termina alle 12:00 AM del 1° gennaio 2021, la data di inizio del rendiconto successivo può essere 12:00 AM del 1° gennaio, 2021 12:00:00 AM.

## <a name="what-are-the-differences"></a>Quali sono le differenze?
Confrontare la definizione del layout del file bancario con la definizione di importazione di Finance e osservare tutte le differenze nei campi e le voci. Confrontare il file di rendiconto bancario al file di esempio di Finance correlato. Nei file ISO20022, tutte le differenze dovrebbero essere semplici da visualizzare.

## <a name="time-zone-differences-on-imported-bank-statements"></a>Differenze di fuso orario nei rendiconti bancari importati
I valori di data e ora nel file di importazione possono variare in base ai valori di data e ora visualizzati in Finance and Operations. Per impedire questa discrepanza, immettere una preferenze di fuso orario nella pagina **Configura origine dati**. Per ulteriori informazioni sull'immissione di una preferenze di fuso orario, vedi [Impostare il processo di importazione della riconciliazione estratti conto avanzata](set-up-advanced-bank-reconciliation-import-process.md).

## <a name="transformations"></a>Trasformazioni
In genere, la modifica deve essere eseguita in una delle tre trasformazioni. Ogni trasformazione viene scritta per uno specifico standard.

| Nome risorsa                                         | Nome file                          |
|-------------------------------------------------------|------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt            | BAI2CSV-to-BAI2XML.xslt            |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt | ISO20022XML-to-Reconciliation.xslt |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt          | MT940TXT-to-MT940XML.xslt          |

## <a name="debugging-transformations"></a>Debug delle trasformazioni
### <a name="adjust-the-bai2-and-mt940-files"></a>Modificare i file BAI2 e MT940

I file BAI2 e MT940 sono file di testo e richiedono una modifica per attivare il debug del linguaggio XSLT (Extensible Stylesheet Language Transformation). La modifica viene eseguita automaticamente quando un file viene importato.

1.  Creare un file XML e copiare il testo seguente.

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  Copiare il contenuto del file di rendiconto bancario e incollarlo nel file XML in modo da sostituire **PASTESTATEMENTFILEHERE**.

### <a name="debug-the-xslt"></a>Debug di XSLT

Per ulteriori informazioni, vedere <https://msdn.microsoft.com/library/ms255605.aspx>.

1.  Avviare Microsoft Visual Studio.
2.  Creare un'applicazione console.
3.  Aprire l'elemento XSLT appropriato.
4.  Fare clic sull'elemento XLST e la relativa pagina delle proprietà.
5.  Impostare l'input sul percorso del file di rendiconto bancario.
6.  Definire un percorso il nome file per l'output.
7.  Impostare i punti di interruzione necessari.
8.  Nel menu fare clic su **XML** &gt; **Avvia debug XSLT**.

### <a name="format-the-xslt-output"></a>Formattare l'output XSLT

Quando la trasformazione viene eseguita, creare un file di output da visualizzare in Visual Studio. Utilizzare CTRL+A, CTRL+K e CTRL+D per formattare rapidamente il file di output.

### <a name="adjust-the-transformation"></a>Modificare la trasformazione

Modificare la trasformazione per ottenere il campo o l'elemento appropriato nel file di rendiconto bancario. Quindi mappare il campo o l'elemento all'elemento appropriato di Finance.

### <a name="debitcredit-indicator"></a>Indicatore Dare/Avere

Talvolta, importi Dare potrebbero essere importati come voci Avere e viceversa. Per risolvere questo problema, è necessario modificare la trasformazione XSLT appropriata. Se i rendiconti bancari provengono da banche diverse, verificare che utilizzino tutti lo stesso approccio in termini di importi Dare/Avere o creare trasformazioni separate.

-   Modello BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator
-   Modello ISO20022XML-to-Reconcilation.xslt GetCreditDebit
-   Modello MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Esempi di formati di rendiconto bancario e di layout tecnici
Nella tabella seguente vengono elencati esempi di definizioni di layout tecnici per file di importazione di riconciliazione bancaria e tre file di esempio di rendiconti bancari correlati. È possibile scaricare i file di esempio e layout tecnici qui: [Importare file di esempio](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Definizione di layout tecnico                             | File di esempio di rendiconto bancario          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| DynamicsAXISO20022Layout                                | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout                                    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
