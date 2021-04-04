---
title: Risoluzione dei problemi di importazione di file di rendiconto bancario
description: È importante che il file di rendiconto bancario della banca corrisponda al layout supportato da Microsoft Dynamics 365 Finance. A causa dei rigorosi standard per i rendiconti bancari, la maggior parte delle integrazioni funzionerà correttamente. Tuttavia, talvolta il file di rendiconto non può essere importato o contiene risultati non corretti. In genere, questi ultimi problemi sono provocati da piccole differenze nel file di rendiconto bancario. In questo articolo viene descritto come risolvere tali differenze e risolvere i problemi.
author: panolte
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac82a269e8f7773c58517ef017576c82c52039cb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253965"
---
# <a name="bank-statement-file-import-troubleshooting"></a>Risoluzione dei problemi di importazione di file di rendiconto bancario

[!include [banner](../includes/banner.md)]

È importante che il file di rendiconto bancario della banca corrisponda al layout supportato da Microsoft Dynamics 365 Finance. A causa dei rigorosi standard per i rendiconti bancari, la maggior parte delle integrazioni funzionerà correttamente. Tuttavia, talvolta il file di rendiconto non può essere importato o contiene risultati non corretti. In genere, questi ultimi problemi sono provocati da piccole differenze nel file di rendiconto bancario. In questo articolo viene descritto come risolvere tali differenze e risolvere i problemi.

<a name="what-is-the-error"></a>Qual è l'errore?
------------------

Dopo aver tentato di importare un file di rendiconto bancario, passare allo storici processi della gestione dati e ai dettagli di esecuzione per individuare l'errore. L'errore potrà aiutare a indicare il rendiconto, il saldo o la riga del rendiconto. Tuttavia, è improbabile che tali informazioni siano sufficienti per identificare il campo o l'elemento che causa il problema.

## <a name="what-are-the-differences"></a>Quali sono le differenze?
Confrontare la definizione del layout del file bancario con la definizione di importazione di Finance e osservare tutte le differenze nei campi e le voci. Confrontare il file di rendiconto bancario al file di esempio di Finance correlato. Nei file ISO20022, tutte le differenze dovrebbero essere semplici da visualizzare.

## <a name="time-zone-differences-on-imported-bank-statements"></a>Differenze di fuso orario nei rendiconti bancari importati
I valori di data e ora nel file di importazione possono variare in base ai valori di data e ora visualizzati in Finance and Operations. Per impedire questa discrepanza, immettere una preferenze di fuso orario nella pagina **Configura origine dati**. Per ulteriori informazioni sull'immissione di una preferenze di fuso orario, vedere [Impostare il processo di importazione della riconciliazione estratti conto avanzata](set-up-advanced-bank-reconciliation-import-process.md).

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
Nella tabella seguente vengono elencati esempi di definizioni di layout tecnici per file di importazione di riconciliazione bancaria e tre file di esempio di rendiconti bancari correlati. È possibile scaricare i file di esempio e layout tecnici qui: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  


| Definizione di layout tecnico                             | File di esempio di rendiconto bancario          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]