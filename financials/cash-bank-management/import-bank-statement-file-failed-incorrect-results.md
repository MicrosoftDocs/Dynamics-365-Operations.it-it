---
title: Risoluzione per l&quot;importazione di file di rendiconto bancario
description: "È importante che il file di rendiconto bancario dalla corrispondenza della banca il layout di Microsoft Dynamics 365 per le operazioni sono supportati. A causa dei rigorosi standard per i rendiconti bancari, la maggior parte delle integrazioni funzionerà correttamente. Tuttavia, talvolta il file di rendiconto non può essere importato o contiene risultati non corretti. In genere, questi ultimi problemi sono provocati da piccole differenze nel file di rendiconto bancario. In questo articolo viene descritto come risolvere tali differenze e risolvere i problemi."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eab840b2974f4e9e8cf542c146482ba8e4239079
ms.openlocfilehash: 9717cf2f36033efe8465906324966242977c6eb2
ms.lasthandoff: 03/31/2017


---

# <a name="bank-statement-file-import-troubleshooting"></a>Risoluzione per l'importazione di file di rendiconto bancario

È importante che il file di rendiconto bancario dalla corrispondenza della banca il layout di Microsoft Dynamics 365 per le operazioni sono supportati. A causa dei rigorosi standard per i rendiconti bancari, la maggior parte delle integrazioni funzionerà correttamente. Tuttavia, talvolta il file di rendiconto non può essere importato o contiene risultati non corretti. In genere, questi ultimi problemi sono provocati da piccole differenze nel file di rendiconto bancario. In questo articolo viene descritto come risolvere tali differenze e risolvere i problemi.

<a name="what-is-the-error"></a>Qual è l'errore?
------------------

Dopo aver tentato di importare un file di rendiconto bancario, passare allo storici processi della gestione dati e ai dettagli di esecuzione per individuare l'errore. L'errore potrà aiutare a indicare il rendiconto, il saldo o la riga del rendiconto. Tuttavia, è improbabile che tali informazioni siano sufficienti per identificare il campo o l'elemento che causa il problema.

## <a name="what-are-the-differences"></a>Quali sono le differenze?
Confrontare la definizione del layout di file bancari a Microsoft Dynamics 365 per la definizione di importazione delle operazioni e osservare tutte le differenze nei campi e le voci. Confrontare il file di rendiconto bancario correlato a campione Dynamics 365 per il file delle operazioni. Nei file ISO20022, tutte le differenze devono essere semplice da visualizzare.

## <a name="transformations"></a>Trasformazioni
In genere, la modifica deve essere eseguita in una delle tre trasformazioni. Ogni trasformazione viene scritta per uno specifico standard.

| Nome risorsa                                         | Nome file                          |
|-------------------------------------------------------|------------------------------------|
| BankStmtImport\_BAI2CSV xslt\_a\_BAI2XML\_            | BAI2CSV-to-BAI2XML.xslt            |
| BankStmtImport\_ISO20022XML xslt\_a\_di riconciliazione\_ | ISO20022XML-to-Reconciliation.xslt |
| BankStmtImport\_MT940TXT xslt\_a\_MT940XML\_          | MT940TXT-to-MT940XML.xslt          |

## <a name="debugging-transformations"></a>Debug delle trasformazioni
### <a name="adjust-the-bai2-and-mt940-files"></a>Modificare i file BAI2 e MT940

I file BAI2 e MT940 sono file di testo e richiedono una modifica per attivare il debug del linguaggio XSLT (Extensible Stylesheet Language Transformation). La modifica viene eseguita automaticamente quando un file viene importato.

1.  Creare un file XML e copiare il testo seguente.

        <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>

2.  Copiare il contenuto del file di rendiconto bancario e incollarlo nel file XML in modo da sostituire **PASTESTATEMENTFILEHERE**.

### <a name="debug-the-xslt"></a>Debug di XSLT

Per ulteriori informazioni, vedere <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.

1.  Avviare Microsoft Visual Studio.
2.  Creare un'applicazione console.
3.  Aprire l'elemento XSLT appropriato.
4.  Fare clic sull'elemento XLST e la relativa pagina delle proprietà.
5.  Impostare l'input sul percorso del file di rendiconto bancario.
6.  Definire un percorso il nome file per l'output.
7.  Impostare i punti di interruzione necessari.
8.  Nel menu, fare clic su XML ** ** &gt; ** avviare la ricerca degli errori XSLT **.

### <a name="format-the-xslt-output"></a>Formattare l'output XSLT

Quando la trasformazione viene eseguita, creare un file di output da visualizzare in Visual Studio. Utilizzare CTRL+A, CTRL+K e CTRL+D per formattare rapidamente il file di output.

### <a name="adjust-the-transformation"></a>Modificare la trasformazione

Modificare la trasformazione per ottenere il campo o l'elemento appropriato nel file di rendiconto bancario. In base a un campo o elemento in Dynamics 365 appropriato per l'elemento delle operazioni.

### <a name="debitcredit-indicator"></a>Indicatore Dare/Avere

Talvolta, importi Dare potrebbero essere importati come voci Avere e viceversa. Per risolvere questo problema, è necessario modificare la trasformazione XSLT appropriata. Se i rendiconti bancari provengono da banche diverse, verificare che utilizzino tutti lo stesso approccio in termini di importi Dare/Avere o creare trasformazioni separate.

-   Modello BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator
-   Modello ISO20022XML-to-Reconcilation.xslt GetCreditDebit
-   Modello MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Esempi di formati di rendiconto bancario e di layout tecnici
Nella tabella seguente vengono elencati esempi di definizioni di layout tecnici per file di importazione di riconciliazione bancaria e tre file di esempio di rendiconti bancari correlati. È possibile scaricare i file di esempio e layout di seguito: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  


| Definizione di layout tecnico                             | File di esempio di rendiconto bancario          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |




