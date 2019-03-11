---
title: Panoramica dei bonifici SEPA
description: Questo articolo fornisce informazioni generali sui bonifici ISO 20022, che includono i bonifici SEPA (Single Euro Payments Area) e qualsiasi altro pagamento elettronico per i fornitori. Un bonifico SEPA è un tipo di pagamento specifico in Euro effettuato da un individuo o una società a un'altra società o un altro individuo. Nell'argomento viene inoltre illustrato come impostare e trasmettere un file di pagamento di bonifico.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 11124
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6081c12ea65812a15b50c627330b4566ab4c679
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "363777"
---
# <a name="sepa-credit-transfer-overview"></a>Panoramica dei bonifici SEPA

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni generali sui bonifici ISO 20022, che includono i bonifici SEPA (Single Euro Payments Area) e qualsiasi altro pagamento elettronico per i fornitori. Un bonifico SEPA è un tipo di pagamento specifico in Euro effettuato da un individuo o una società a un'altra società o un altro individuo. Nell'argomento viene inoltre illustrato come impostare e trasmettere un file di pagamento di bonifico.

## <a name="what-is-a-credit-transfer-message"></a>Che cos'è un messaggio di bonifico?
Il messaggio di bonifico è una richiesta inviata dalla parte che inizia la transazione (la società) per spostare fondi dal proprio conto a quello di un creditore. Esistono molte implementazioni specifiche per banca e per paese di messaggi di bonifico. Alcune di tali implementazioni sono utilizzate all'interno di un paese e alcune stanno diventando standard. Uno standard globale affermato è ISO 20022 e i relativi messaggi di inizio della transazione, ad esempio Bonifico. La figura riportata di seguito mostra le relazioni e la copertura per messaggi di bonifico selezionati. 
![Bonifico](./media/credit-transfer.jpg) Messaggi di bonifico 

## <a name="what-are-iso-20022-and-sepa-payments"></a>Che cosa sono i pagamenti ISO 20022 e SEPA?
SEPA (Single Euro Payments Area) viene impostata dalla Commissione Europea e stabilisce che tutti i pagamenti elettronici vengono considerati nazionali, indipendentemente dal paese in cui si trovano i singoli individui, le aziende o l'organizzazione e la banca. Non c'è differenza tra i pagamenti nazionali e quelli transfrontalieri. Il SEPA include i 28 stati membri dell'Unione Europea (UE) oltre all'Islanda, il Liechtenstein, la Norvegia, la Svizzera, Monaco e San Marino. SEPA consente di formare un singolo mercato per le transazioni di pagamento all'interno dell'Area Economica Europea. Infine, SEPA prevede di ridurre il numero dei formati di pagamento con cui lavorano le banche, le aziende e i singoli individui. La Commissione Europea ha stabilito la base legale per i pagamenti SEPA nella direttiva relativa ai servizi di pagamento. L'European Payment Council (EPC) supporta SEPA nelle seguenti attività:

-   Stabilisce gli standard per i pagamenti elettronici SEPA utilizzando il nuovo formato standard europeo UNIFI (Universal Financial Industry) ISO-20022 XML.
-   Stabilisce le regole e linee guida sulla gestione di pagamenti nell'area euro.

L'EPC, che è costituito dalle banche europee, sviluppa i framework commerciali e tecnici per gli strumenti di pagamento SEPA. Sono utilizzati tre tipi di pagamenti SEPA:

-   Bonifici
-   Addebiti diretti
-   Carte

## <a name="what-is-a-sepa-credit-transfer"></a>Cos è un bonifico SEPA?
Un bonifico SEPA è un pagamento effettuato da un individuo o una società a un'altra società o un altro individuo. I pagamenti devono essere in Euro e devono includere il numero IBAN (International Bank Account Number) e il codice BIC (Bank Identifier Code) di entrambe le parti. Il codice BIC è detto anche codice Society for Worldwide Interbank Financial Telecommunication \[SWIFT\]. Inoltre, i costi della transazione devono essere condivisi da entrambe le parti. I bonifici effettuati tra le parti devono utilizzare file XML conformi agli standard di elaborazione di pagamento ISO 20022 e il formato XML, come specificato dalla EPC.

## <a name="how-is-a-credit-transfer-implemented"></a>Come viene implementato un bonifico?
Il formato di pagamento dei bonifici per i paesi europei è implementato utilizzando la creazione di report elettronici (ER, Electronic reporting) e la funzionalità Metodi di pagamento in Microsoft Dynamics 365 for Finance and Operations. Alcuni formati di bonifico utilizzati in altre aree utilizzano ancora il framework di pagamento precedente. Tra i molti altri formati, sono disponibili dodici formati di file di bonifico ISO 20022. Questi formati di esportazione sono conformi allo standard XML ISO 20022 SEPA. Vengono utilizzati per generare bonifici in valuta diversa dall'euro per i paesi in cui vengono utilizzati e pagamenti in euro come specificato nella versione 8.2 del documento SEPA Credit Transfer Scheme Rulebook rilasciato dall'EPC. Prima di poter implementare i bonifici, è necessario contattare la banca per ottenere il software necessario per caricare i file di E-banking. Verrà utilizzato tale software per trasferire i file XML contenenti gli ordini di pagamento alla banca.

## <a name="what-credit-transfer-formats-are-currently-supported-in-finance-and-operations"></a>Quali formati di bonifico sono attualmente supportati in Finance and Operations?
È necessario passare alla libreria Risorsa condivisa in Microsoft Dynamics Lifecycle Services (LCS) e visualizzare l'elenco più aggiornato di file disponibili con tipo di risorsa **Configurazione GER**. La sezione successiva, "Cosa devo impostare?", fornisce un collegamento all'argomento che illustra come creare un archivio LCS per esaminare le configurazioni disponibili e importare quelle selezionate.

## <a name="what-do-i-have-to-set-up"></a>Cosa devo impostare?
-   Prima di poter creare file di bonifico, almeno una configurazione attiva di bonifico deve essere importata nelle configurazioni ER. Per istruzioni, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).
-   Quando si configurano i metodi di pagamento per la contabilità fornitori, selezionare la casella di controllo **Report elettronici generici**, quindi selezionare il formato di bonifico appropriato (ad esempio **Bonifico ISO 20022 (AT)**) come configurazione del formato di esportazione.
-   È inoltre necessario impostare la persona giuridica e le informazioni sul conto bancario in Finance and Operations.
-   I numeri di conto bancario, IBAN, e talvolta i codici SWIFT (BIC) o altri ID sono necessari per creare pagamenti tramite bonifico validi. Di conseguenza, è necessario impostarli per il conto bancario del fornitore e il conto bancario per l'organizzazione che richiede il trasferimento.
-   Potrebbero essere necessarie ulteriori informazioni, ad esempio i numeri di partita IVA per le parti a cui si fa riferimento nel messaggio di bonifico. Tali informazioni devono essere impostate per i fornitori e per la persona giuridica quando richieste.
-   Alcuni metodi di pagamento per la contabilità fornitori, principalmente quelli basati su ISO 20022, potrebbero richiedere impostazioni aggiuntive per **Set di codici del formato di pagamento**, ad esempio il **Tipo di servizio** = **SLEV**. Tali codici sono utilizzati come tag aggiuntivi per le transazioni di pagamento durante l'elaborazione dei pagamenti. I valori predefiniti dei codici di pagamento, ad esempio **Scopo categoria**, **Portatore addebito**, **Titolo locale** e **Livello servizio** possono essere impostati in due posizioni. La prima posizione è **Intestazione giornale di registrazione contabilità fornitori** e il secondo è **Metodi di pagamento contabilità fornitori**. Al momento della creazione delle righe del giornale di registrazione pagamenti, i valori del codice di pagamento impostati nell'intestazione del giornale di registrazione pagamenti vengono trasferiti in una riga del giornale di registrazione; se non impostati, vengono utilizzati i valori dei Metodi di pagamento.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>Quali parametri sono disponibili per la generazione di pagamenti tramite bonifico?
L'elenco dei parametri specifici dipende dal formato di bonifico. Nella tabella riportata di seguito sono elencati i parametri disponibili quando si genera un file di pagamento tramite bonifico ISO 20022 per la Germania in un giornale di registrazione pagamenti fornitore. Utilizzando le opzioni disponibili nella scheda **Esecuzione in background**, è possibile eseguire la generazione dei pagamenti in modalità batch.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Prenotazione in batch</td>
<td>Selezionare questa casella di controllo per includere il tag di prenotazione in batch nel file XML.</td>
</tr>
<tr class="even">
<td>Data di elaborazione</td>
<td>Immettere la data in cui la banca deve elaborare i pagamenti.</td>
</tr>
<tr class="odd">
<td>Formatta</td>
<td>Selezionare il formato per le informazioni sulle rimesse, in base ai requisiti del paese o della banca:
<ul>
<li><strong>Strutturato</strong> - Selezionare questa opzione per utilizzare il formato strutturato quando una riga di pagamento viene liquidata a fronte di una fattura. Questa opzione non è disponibile per i formati di esportazione specifici del paese per Francia, Germania o Paesi Bassi.</li>
<li><strong>Non strutturato</strong> Selezionare questa opzione per utilizzare il formato non strutturato quando il pagamento viene liquidato a fronte di più fatture. I numeri di fattura per le fatture liquidate sono concatenati e utilizzati come informazioni di rimessa. In conformità alle linee guida ISO 20022, le informazioni non strutturate di rimessa sono limitate a 140 caratteri.</li>
</ul></td>
</tr>
<tr class="even">
<td>Numero di fatture</td>
<td>Immettere il numero di fatture da cui il report <strong>Avviso di pagamento</strong> viene stampato.</td>
</tr>
<tr class="odd">
<td>Numero progressivo</td>
<td>Immettere un numero progressivo per identificare il file. Il numero progressivo viene visualizzato nel report <strong>Nota di partecipazione</strong>.</td>
</tr>
<tr class="even">
<td>Stampa nota di partecipazione</td>
<td>Selezionare questa casella di controllo per stampare il report <strong>Nota di partecipazione</strong>.</td>
</tr>
<tr class="odd">
<td>Stampa report controllo</td>
<td>Selezionare questa casella di controllo per stampare un report che contiene informazioni sul pagamento.</td>
</tr>
<tr class="even">
<td>Stampa lettera di accompagnamento</td>
<td>Selezionare questa casella di controllo per stampare il report <strong>Avviso di pagamento</strong>.</td>
</tr>
</tbody>
</table>

## <a name="what-are-ibans-and-bics"></a>Cosa sono IBAN e BIC?
I codici IBAN (International Bank Account Number) e BIC (Bank Identifier Code) sono utilizzati per identificare qualsiasi conto in molti paesi del mondo. Sono inclusi i 34 paesi SEPA. Immettere il codice BIC nel campo **Codice SWIFT** e l'IBAN nel campo **IBAN**. Per il conto bancario del creditore e il conto bancario del cliente, questi campi si trovano nella Scheda dettaglio **Identificazione aggiuntiva** nella scheda **Conto bancario** della pagina **Conti bancari**. L'utilizzo del codice BIC per i pagamenti SEPA non è più applicato.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>Come si trasmette un file di pagamento alla banca?
Quando si generano pagamenti, viene generato il file di pagamento e viene richiesto di salvarlo dal Web browser in uso in qualsiasi posizione disponibile. Il passaggio successivo è quello di inviare il file XML alla banca. Questo processo varia in base alla banca. Seguire le istruzioni dalla banca per inviare i file alla banca per l'elaborazione.



