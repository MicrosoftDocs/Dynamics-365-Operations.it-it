---
title: Panoramica dei bonifici SEPA
description: "L&quot;articolo prevede di visualizzare informazioni generali sui bonifici ISO 20022, ad esempio i bonifici SEPA (Single Euro Payments Area (SEPA) e tutti gli altri pagamenti elettronici per i fornitori. Un bonifico SEPA si un tipo di pagamento in euro da una società o persona in un&quot;altra società o persona. Vengono inoltre viene descritto come impostare e trasmettere un file di pagamento tramite bonifico."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11124
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 848df5e3898f37284d7746c59bff8b38d35ac883
ms.lasthandoff: 03/31/2017


---

# <a name="sepa-credit-transfer-overview"></a>Panoramica dei bonifici SEPA

L'articolo prevede di visualizzare informazioni generali sui bonifici ISO 20022, ad esempio i bonifici SEPA (Single Euro Payments Area (SEPA) e tutti gli altri pagamenti elettronici per i fornitori. Un bonifico SEPA si un tipo di pagamento in euro da una società o persona in un'altra società o persona. Vengono inoltre viene descritto come impostare e trasmettere un file di pagamento tramite bonifico.

## <a name="what-is-a-credit-transfer-message"></a>Cosa si un messaggio di bonifico?
Messaggio di bonifico viene inviata da una parte di inizio (la società) invia i fondi di movimento del proprio conto di un creditore. È presente un paese implementazioni a specifiche e banca- specifiche dei messaggi di bonifico. Alcuni di essi sono utilizzati all'interno di un paese e alcuni sono diventanti standard. Standard globale è affermato ISO 20022 e i relativi messaggi di inizio, ad esempio EFT. La figura di seguito mostra le relazioni e la copertura per i messaggi relativi al bonifico. 
messaggi\[/caption\]di bonifico](./media/credit-transfer.jpg) tansfer di credito![ 

## <a name="what-are-iso-20022-and-sepa-payments"></a>Le operazioni costituiscono pagamenti ISO 20022 e SEPA?
SEPA (Single Euro Payments Area) viene impostata dalla Commissione Europea e stabilisce che tutti i pagamenti elettronici vengono considerati nazionali, indipendentemente dal paese in cui si trovano i singoli individui, le aziende o l'organizzazione e la banca. Non esiste alcuna differenza tra i pagamenti nazionali e i pagamenti di frontiera. Il SEPA include i 28 stati membri dell'Unione Europea (EU) nonché l'Islanda il, Liechtenstein, Norvegia, Svizzera, il Monaco e San Marino. SEPA consente di formare un singolo mercato per le transazioni di pagamento all'interno dell'Area Economica Europea. Infine, SEPA prevede di ridurre il numero dei formati di pagamento con cui lavorano le banche, le aziende e i singoli individui. La Commissione Europea ha stabilito la base legale per i pagamenti SEPA nella direttiva relativa ai servizi di pagamento. L'European Payment Council (EPC) supporta SEPA nelle seguenti attività:

-   Stabilisce gli standard per i pagamenti elettronici SEPA utilizzando il nuovo formato standard europeo UNIFI (Universal Financial Industry) ISO-20022 XML.
-   Stabilisce le regole e linee guida sulla gestione di pagamenti nell'area euro.

L'EPC, che è costituito dalle banche europee, sviluppa i framework commerciali e tecnici per gli strumenti di pagamento SEPA. Sono utilizzati tre tipi di pagamenti SEPA:

-   Bonifici
-   Addebiti diretti
-   Carte

## <a name="what-is-a-sepa-credit-transfer"></a>Cos è un bonifico SEPA?
Un bonifico SEPA è un pagamento effettuato da un individuo o una società a un'altra società o un altro individuo. I pagamenti devono essere in Euro e devono includere il numero IBAN (International Bank Account Number) e il codice BIC (Bank Identifier Code) di entrambe le parti. È anche BIC è detto anche la società per il codice \[il SWIFT\] Interbank Financial Telecommunications). Inoltre, i costi di transazioni deve essere condivisi tra entrambe le direzioni. I bonifici effettuati tra le parti devono utilizzare file XML conformi agli standard di elaborazione di pagamento ISO 20022 e il formato XML, come specificato dalla EPC.

## <a name="how-is-a-credit-transfer-implemented"></a>Applicazione di un bonifico è implementato?
Il formato di pagamento con bonifico per i paesi europei è implementato (ER) e utilizza la funzionalità di reporting di modalità di pagamento in Dynamics 365 per le operazioni. Alcuni formati di bonifico utilizzati ancora in altre aree utilizzano il framework di pagamento precedenti. In molti altri formati, sono presenti dodici formati di file di bonifico ISO 20022 disponibili. I formati di esportazione conformi allo standard XML SEPA ISO 20022. Vengono utilizzati per generare i trasferimenti di pagamento con anziché in euro per i paesi in cui vengono utilizzati e pagamenti in euro specificato nella versione 8.2 della normativa schema di bonifico SEPA in cui EPC pubblico. Prima di poter implementare i trasferimenti, è necessario contattare la banca del software necessario per caricare i file di e-banking. Verrà utilizzata tale software per trasferire i file XML contenenti gli ordini di pagamento alla banca.

## <a name="what-credit-transfer-formats-are-currently-supported-in-dynamics-365-for-operations"></a>Per formattare bonifico attualmente è supportato in Dynamics 365 per le operazioni?
È necessario passare alla libreria della risorsa condivisa i servizi (LCS) del ciclo di vita di Microsoft Dynamics e visualizzare l'elenco sempre più aggiornato dei file disponibili di tipo cespite ** di configurazione GER **. La sezione successiva, in quanto devo impostare? ", fornire un collegamento all'argomento che illustra come creare un file delle LC per esaminare le configurazioni disponibili e le configurazioni si seleziona importazione.

## <a name="what-do-i-have-to-set-up"></a>Cosa devo impostare?
-   Prima di creare i file di bonifico, almeno una configurazione attiva di bonifico deve essere inclusa nelle configurazioni di ER. Per istruzioni, vedere [configurazioni elettroniche di download da Servizi] del ciclo di vita (https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).
-   Quando si configura la modalità di pagamento della contabilità fornitori, selezionare ** reporting elettronica generica ** la casella di controllo e selezionare il formato di bonifico appropriato, ad esempio ** bonifico ISO 20022 (A) **) come configurazione di formato.
-   È inoltre necessario impostare le informazioni sui conti bancari e della persona giuridica in Dynamics 365 per le operazioni.
-   I numeri di conto bancario, IBANs e talvolta i codici SWIFT () o BIC altri ID sono necessari per creare i pagamenti tramite bonifico validi. Di conseguenza, è necessario impostarli per il conto bancario del fornitore e la rimessa e l'organizzazione che richiede il trasferimento.
-   Ulteriori informazioni potrebbe essere necessario, ad esempio i numeri (VAT) dell'imposta sul valore aggiunto per le parti che fanno riferimento al messaggio di bonifico. Tali informazioni devono essere impostate per i fornitori e per la persona giuridica se hanno richiesto.
-   In modalità di pagamento della contabilità fornitori, principalmente al codice ISO 20022 in base alla modalità di pagamento, potrebbe richiedere definire ulteriori impostazioni per ** diversi codici di formato di pagamento **, ad esempio ** tipo di servizio ** = ** SLEV **. Tali codici utilizzati come tag aggiuntivo per le transazioni di pagamento durante l'elaborazione dei pagamenti. I valori predefiniti dei codici di pagamento, ad esempio ** scopo di categoria **, ** portatore di spese varie **, ** strumento ** locale e ** livelli di servizio ** possono essere impostati in due cifre. Il primo luogo è ** intestazione del giornale pagamenti della contabilità fornitori ** e il secondo è ** metodi di contabilità fornitori per i pagamenti **. Al giornale pagamenti della creazione, i valori dei codici di pagamento impostati nell'intestazione del giornale di registrazione pagamenti vengono trasferiti in una riga del giornale di registrazione, se non impostati, i valori dalla modalità di pagamento vengono utilizzati.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>I parametri sono disponibili per la generazione di pagamenti tramite bonifico?
L'elenco dei parametri specifici dipende dal formato di bonifico. Nella seguente tabella sono riportati i parametri disponibili quando si genera un file di pagamento con bonifico ISO 20022 per la Germania in un giornale di registrazione pagamenti fornitore. Utilizzando le opzioni disponibili ** funzioni in background ** nella scheda, è possibile eseguire la generazione di pagamento lotto.

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
<li><strong>Strd</strong> - Selezionare questa opzione per utilizzare il formato strutturato quando una riga di pagamento viene liquidata a fronte di una fattura. Questa opzione non è disponibile per i formati di esportazione specifici per la Francia, Germania, o i Paesi Bassi.</li>
<li><strong>Non strutturato</strong> Selezionare questa opzione per utilizzare il formato non strutturato quando il pagamento viene liquidato a fronte di più fatture. I numeri di fattura per le fatture liquidate sono concatenati e utilizzati come informazioni di rimessa. Conformemente alle linee guida ISO 20022, le informazioni non strutturato di rimessa vengono limitate a 140 caratteri.</li>
</ul></td>
</tr>
<tr class="even">
<td>Numero di fatture</td>
<td>Immettere il numero di fatture da cui <strong>Avviso di pagamento</strong> verrà stampato il report.</td>
</tr>
<tr class="odd">
<td>Numero progressivo</td>
<td>Immettere un numero progressivo per identificare il file. Numero progressivo viene <strong>Assistere alla nota</strong> visualizzato nel report.</td>
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
Numero di conto bancario internazionale (IBAN) e il codice BIC (Bank Identifier Code (BIC) vengono utilizzati per identificare un conto in molti paesi in tutto il mondo. Sono incluse le 34 paesi SEPA. Registrare il BIC in ** codice SWIFT ** il campo e IBAN ** IBAN ** nel campo. Sia il conto bancario del creditore che il conto bancario del cliente, questi campi sono posizionati ** identificazione aggiuntive ** clic ** conto bancario ** nella scheda ** conti bancari ** della pagina. L'utilizzo di BIC per i pagamenti SEPA non verrà più applicato.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>Come si trasmette un file di pagamento alla banca?
Quando vengono generati i pagamenti, il file di pagamento generato e viene chiesto di salvarla dal Web browser in una posizione disponibile. Il passaggio successivo consiste di inviare il file XML alla banca. Questo processo varia in base alla banca. Seguire le istruzioni dalla banca per inviare i file alla banca per l'elaborazione.


