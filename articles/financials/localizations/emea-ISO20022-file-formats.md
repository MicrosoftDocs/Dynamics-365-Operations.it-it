<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="emea-ISO20022-file-formats.md" target-language="it-IT">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>emea-ISO20022-file-formats.35e138.d91e937c62d4d498e67d753e39676514835f4161.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>d91e937c62d4d498e67d753e39676514835f4161</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/15/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\financials\localizations\emea-ISO20022-file-formats.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>ISO20022 files import</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importazione di file ISO20022</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic explains how to import payment files of the ISO 20022 camt.054 and pain.002 formats into Microsoft Dynamics 365 for Finance and Operations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo argomento viene descritto come importare file di pagamento dei formati camt.054 e pain.002 ISO 20022 Microsoft Dynamics 365 for Finance and Operations.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Import ISO20022 files</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importare file ISO20022</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>You can import payment files that have the following formats:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">È possibile importare file di pagamento con i seguenti formati:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source><bpt id="p1">**</bpt>ISO20022 camt.054 credit advice<ept id="p1">**</ept> – Import incoming payments from a file in this format into the Customer payment journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Avviso di accredito ISO20022 camt.054<ept id="p1">**</ept>: importare pagamenti ricevuti da un file in questo formato nel giornale di registrazione pagamenti del cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source><bpt id="p1">**</bpt>ISO20022 pain.002 status return<ept id="p1">**</ept> and <bpt id="p2">**</bpt>ISO20022 camt.054 debit advice<ept id="p2">**</ept> – Import return files in these formats into the AP Payment transfer journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Reso con stato ISO20022 pain.002<ept id="p1">**</ept> e <bpt id="p2">**</bpt>Avviso di addebito ISO20022 camt.054<ept id="p2">**</ept>: importare file di rimborso in questi formati nel giornale di registrazione trasferimenti pagamenti di contabilità fornitori.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Prerequisites for importing the camt.054 credit advice file</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prerequisiti per importare il file di avviso di accredito camt.054</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>You must complete the following prerequisites to import bank notification messages in the camt.054.001.002 format into the Customer payment journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">È necessario completare i seguenti prerequisiti per importare i messaggi di notifica della banca nel formato camt.054.001.002 nel giornale di registrazione pagamenti del cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Import the <bpt id="p1">**</bpt>ISO20022 camt.054<ept id="p1">**</ept> Electronic reporting (ER) configuration from Microsoft Dynamics Lifecycle Services (LCS).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importare la configurazione di reporting elettronica (ER) <bpt id="p1">**</bpt>ISO20022 camt.054<ept id="p1">**</ept> da Microsoft Dynamics Lifecycle Services (LCS).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Then, on the <bpt id="p1">**</bpt>Customer method of payment<ept id="p1">**</ept> page, in the <bpt id="p2">**</bpt>Import format configuration<ept id="p2">**</ept> field, select that configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quindi, nella pagina <bpt id="p1">**</bpt>Metodo di pagamento cliente<ept id="p1">**</ept>, nel campo <bpt id="p2">**</bpt>Configurazione formato di importazione<ept id="p2">**</ept>, selezionare la configurazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>For more information, see <bpt id="p1">[</bpt>File formats for methods of payment<ept id="p1">](emea-select-file-formats-for-the-method-of-payments.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per ulteriori informazioni, vedere <bpt id="p1">[</bpt>Formati di file per i metodi di pagamento<ept id="p1">](emea-select-file-formats-for-the-method-of-payments.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>On the <bpt id="p1">**</bpt>All customers<ept id="p1">**</ept> page, enter a name and organization number for each customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nella pagina <bpt id="p1">**</bpt>Tutti i clienti<ept id="p1">**</ept> immettere un nome e un numero di organizzazione per ogni cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>On the <bpt id="p1">**</bpt>Customer bank account<ept id="p1">**</ept> page, set up a customer bank account record by entering the following information: IBAN or bank account number, and SWIFT code or routing number.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nella pagina <bpt id="p1">**</bpt>Conto bancario cliente<ept id="p1">**</ept> impostare un record di conto bancario del cliente immettendo le seguenti informazioni: IBAN o numero di conto bancario e codice SWIFT o numero di registrazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>On the <bpt id="p1">**</bpt>Bank accounts<ept id="p1">**</ept> page, set up legal entity bank accounts by entering the following information: IBAN or bank account number, SWIFT code or routing number, currency, and address.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nella pagina <bpt id="p1">**</bpt>Conti bancari<ept id="p1">**</ept> impostare i conti bancari della persona giuridica immettendo le seguenti informazioni: IBAN o numero di conto bancario, codice SWIFT o numero di registrazione, valuta e indirizzo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>If you plan to use Advanced bank reconciliation, on the <bpt id="p1">**</bpt>Reconciliation<ept id="p1">**</ept> FastTab, set the <bpt id="p2">**</bpt>Advanced bank reconciliation<ept id="p2">**</ept> option to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se si prevede di utilizzare la riconciliazione degli estratti conto avanzata, nella scheda dettaglio <bpt id="p1">**</bpt>Riconciliazione<ept id="p1">**</ept> impostare l'opzione <bpt id="p2">**</bpt>Riconciliazione estratti conto avanzata<ept id="p2">**</ept> su <bpt id="p3">**</bpt>Sì<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>If you plan to reconcile unposted imported payments, set the <bpt id="p1">**</bpt>Use bank statements as confirmation of electronic payments<ept id="p1">**</ept> option to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se si prevede di riconciliare i pagamenti importati non registrati, impostare l'opzione <bpt id="p1">**</bpt>Utilizza rendiconti bancari come conferma di pagamenti elettronici<ept id="p1">**</ept> su <bpt id="p2">**</bpt>Sì<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Optional: On the <bpt id="p1">**</bpt>Transaction code mapping<ept id="p1">**</ept> page, set up the mapping between bank transaction codes in the file and bank transaction types.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Facoltativo: nella pagina <bpt id="p1">**</bpt>Mapping dei codici transazione<ept id="p1">**</ept> impostare il mapping tra codici di transazione bancaria nel file e tipi di transazioni bancarie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>If the file contains transaction charges that you want to post together with the incoming payment, create a payment fee on the <bpt id="p1">**</bpt>Customer payment fee<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se il file contiene spese di transazione che si desidera registrare insieme al pagamento ricevuto, creare una commissione di pagamento nella pagina <bpt id="p1">**</bpt>Commissione pagamento cliente<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Then, on the <bpt id="p1">**</bpt>Methods of payment<ept id="p1">**</ept> page, associate the payment fee with the bank account in the payment fee setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quindi, nella pagina <bpt id="p1">**</bpt>Metodi di pagamento<ept id="p1">**</ept> associare la commissione di pagamento al conto bancario nell'impostazione della commissione di pagamento.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>If ESR payments will be imported and will contain ISR references (applicable for legal entities in Switzerland), complete the following setup:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se i pagamenti PVR verranno importati e conterranno i riferimenti ISR (applicabili alle persone giuridiche in Svizzera), completare la seguente configurazione:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>In the <bpt id="p1">**</bpt>Customer payments, account lengths<ept id="p1">**</ept> field, enter the length of the customer code that is used in ISR references or for automatic identification of the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nel campo <bpt id="p1">**</bpt>Pagamenti clienti, lunghezza conto<ept id="p1">**</ept> immettere la lunghezza del codice cliente utilizzato nei riferimenti ISR o per l'identificazione automatica del cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Make sure that the customer number and invoice number (number sequences) contain only digits.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Verificare che il numero di fattura e il numero cliente (sequenze numeriche) contengano solo cifre.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>They must contain no other characters.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Non devono contenere altri caratteri.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>The invoice number must not have leading zeros.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il numero di fattura non deve avere zeri iniziali.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Enter the ESR, BESR, and routing number for the legal entity bank account.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Immettere i numeri ESR, BESR e di registrazione del conto bancario della persona giuridica.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>For more information, see <bpt id="p1">[</bpt>legacy ESR feature<ept id="p1">](emea-che-esr-customer-payments-import.md)</ept>, because similar settings are required.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per ulteriori informazioni, vedere <bpt id="p1">[</bpt>funzionalità PVR precedenti<ept id="p1">](emea-che-esr-customer-payments-import.md)</ept>, poiché impostazioni simili sono necessarie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Import the camt.054 credit advice file into the Customer payment journal</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importare il file di avviso di accredito camt.054 nel giornale di registrazione pagamenti cliente</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>On the <bpt id="p1">**</bpt>Customer payment journal lines<ept id="p1">**</ept> page, click <bpt id="p2">**</bpt>Functions<ept id="p2">**</ept><ph id="ph1"> &gt; </ph><bpt id="p3">**</bpt>Import payments<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nella pagina <bpt id="p1">**</bpt>Righe giornale di registrazione pagamenti cliente<ept id="p1">**</ept> fare clic su <bpt id="p2">**</bpt>Funzioni<ept id="p2">**</ept><ph id="ph1"> &gt; </ph><bpt id="p3">**</bpt>Importa pagamenti<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Select the method of payment that has the required settings for the ISO20022 camt.054 format.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Selezionare il metodo di pagamento con le impostazioni richieste per il formato ISO20022 camt.054.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>Specify the required parameters and the path of the file, and then click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Specificare i parametri necessari e il percorso del file, quindi fare clic su <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>The file is imported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il file viene importato.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Prerequisites for importing files in the pain.002 status return and camt.054 debit advice formats into the AP Payment transfer journal</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prerequisiti per l'importazione di file nel reso con stato pain.002 e di formati di avviso di addebito camt.054 nel giornale di registrazione trasferimenti pagamenti di contabilità fornitori.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>You must complete the following prerequisites to import bank messages in the following ISO20022 formats to the <bpt id="p1">**</bpt>Vendor payment transfer<ept id="p1">**</ept> page: pain.002.001.003 status return messages and camt.054.001.002 debit advice.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">È necessario completare i seguenti prerequisiti per importare messaggi bancari nei seguenti formati ISO20022 nella pagina <bpt id="p1">**</bpt>Trasferimento pagamenti fornitore<ept id="p1">**</ept> : messaggi di reso con stato pain.002.001.003 e avviso di addebito camt.054.001.002.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>Import the <bpt id="p1">**</bpt>ISO20022 camt.054<ept id="p1">**</ept> and <bpt id="p2">**</bpt>ISO20022 pain.002<ept id="p2">**</ept> ER configurations from LCS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importare le configurazioni ER <bpt id="p2">**</bpt>ISO20022 camt.054<ept id="p2">**</ept> e <bpt id="p1">**</bpt>ISO20022 pain.002<ept id="p1">**</ept> da LCS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>On the <bpt id="p1">**</bpt>Vendor method of payment<ept id="p1">**</ept> page, in the <bpt id="p2">**</bpt>Return format configuration<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Return format secondary configuration<ept id="p3">**</ept> fields, select the ER configurations that you imported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nella pagina <bpt id="p1">**</bpt>Metodo di pagamento fornitore<ept id="p1">**</ept>, nei campi <bpt id="p3">**</bpt>Configurazione formato risposta<ept id="p3">**</ept> e <bpt id="p2">**</bpt>Configurazione secondaria formato risposta<ept id="p2">**</ept>, selezionare le configurazioni ER importate.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>You will have to activate the generic electronic return format for the selected method of payment.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sarà necessario attivare il formato di risposta elettronica generica per il metodo di pagamento selezionato.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>On the <bpt id="p1">**</bpt>Return format status mapping<ept id="p1">**</ept> page, set up the mapping of status codes between pain.002 statuses and Vendor payment journal statuses.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nella pagina <bpt id="p1">**</bpt>Mapping dello stato formato risposta<ept id="p1">**</ept> impostare il mapping dei codici stato tra gli stati pain.002 e gli stati del giornale di registrazione pagamenti fornitore.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>Here is an example of a status setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Di seguito è riportato un esempio di impostazione dello stato.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Return status</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Stato di reso</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Payment status</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Stato pagamenti</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>RJCT</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">RJCT</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Rejected</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rifiutato</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>ACCP</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">ACCP</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>Accepted</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Accettato</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>ACSP</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">ACSP</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>Received</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ricevuti</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>On the <bpt id="p1">**</bpt>Return format error codes<ept id="p1">**</ept> page, set up pain.002 error codes and descriptions in accordance with external ISO20022 status reason codes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nella pagina <bpt id="p1">**</bpt>Codici di errore formato risposta<ept id="p1">**</ept> impostare i codici di errore pain.002 e le descrizioni in conformità ai codici motivo esterni dello stato ISO20022.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>Here is an example of part of an error code setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Di seguito è riportato un esempio della parte dell'impostazione di un codice di errore.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Code</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Codice</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Name</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nome</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>AC01</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC01</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>IncorrectAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">IncorrectAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>AC02</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC02</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>InvalidDebtorAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">InvalidDebtorAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>AC03</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC03</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>InvalidCreditorAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">InvalidCreditorAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>AC04</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC04</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>ClosedAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">ClosedAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>AC05</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC05</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>ClosedDebtorAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">ClosedDebtorAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>AC06</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC06</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>BlockedAccount</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">BlockedAccount</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>If the camt.054 file contains transaction charges that you want to post together with the incoming payment, create a payment fee on the <bpt id="p1">**</bpt>Vendor payment fee<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se il file camt.054 contiene spese di transazione che si desidera registrare insieme al pagamento ricevuto, creare una commissione di pagamento nella pagina <bpt id="p1">**</bpt>Commissione pagamento fornitore<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Then, on the <bpt id="p1">**</bpt>Methods of payment<ept id="p1">**</ept> page, associate the payment fee with the bank account in the payment fee setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quindi, nella pagina <bpt id="p1">**</bpt>Metodi di pagamento<ept id="p1">**</ept> associare la commissione di pagamento al conto bancario nell'impostazione della commissione di pagamento.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>Import the pain.002 status return or camt.054 debit advice files into the Vendor payment journal</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importare i file con avviso di addebito camt.054 o di reso con stato pain.002 nel giornale di registrazione pagamenti fornitore</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Open the <bpt id="p1">**</bpt>Payment transfers<ept id="p1">**</ept> page in Accounts Payable menu.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aprire la pagina <bpt id="p1">**</bpt>Trasferimenti di pagamento<ept id="p1">**</ept> dal menu della Contabilità fornitori.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>On the <bpt id="p1">**</bpt>Payment transfers<ept id="p1">**</ept> page, click <bpt id="p2">**</bpt>Return file - vendor<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nella pagina <bpt id="p1">**</bpt>Trasferimenti di pagamento<ept id="p1">**</ept> fare clic su <bpt id="p2">**</bpt>Archivio resi - Fornitore<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>Select the method of payment that has the required settings for ISO20022 files, and then click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Selezionare il metodo di pagamento con le impostazioni richieste per i file ISO20022, quindi fare clic su <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>Select the file format that you plan to import, and then click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Selezionare il formato di file che si prevede di importare e fare clic su <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>Specify the required parameters and the path of the file, and then click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Specificare i parametri necessari e il percorso del file, quindi fare clic su <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>If you're importing the pain.002 file, the status of vendor payment lines is updated, based the information in the imported file.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se si importa il file pain.002, lo stato delle righe di pagamento fornitore viene aggiornato in base alle informazioni incluse nel file importato.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>If you're importing the camt.054 file, you should specify the following additional parameters:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se si importa il file camt.054, è necessario specificare i parametri aggiuntivi seguenti:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source><bpt id="p1">**</bpt>Fee ID<ept id="p1">**</ept> – Enter the Fee ID which will define new payment fee lines, which will be created on the Vendor payment journal line if a charge amount is present in the camt.054 file.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>ID commissione<ept id="p1">**</ept>: immettere l'ID della commissione che definirà le nuove righe della commissione di pagamento, che verranno create nella riga del giornale di registrazione pagamenti fornitore se l'importo dell'addebito è presente nel file camt.054.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source><bpt id="p1">**</bpt>New journal name<ept id="p1">**</ept> and <bpt id="p2">**</bpt>New journal description<ept id="p2">**</ept> – Enter the name and description of the journal that processed transactions will be transferred to.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Nuovo nome giornale di registrazione<ept id="p1">**</ept> e <bpt id="p2">**</bpt>Descrizione nuovo giornale di registrazione<ept id="p2">**</ept>: immettere il nome e la descrizione del giornale di registrazione nel quale verranno trasferite le transazioni elaborate.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>After the transfer, new voucher numbers should be assigned in the new journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dopo il trasferimento i nuovi numeri dei giustificativi devono essere assegnati nel nuovo giornale di registrazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source><bpt id="p1">**</bpt>Import direct debit transactions<ept id="p1">**</ept> – Set this option to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept> if outgoing direct debits must be imported into the Vendor payment journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Importa transazioni di addebito diretto<ept id="p1">**</ept>: impostare questa opzione su <bpt id="p2">**</bpt>Sì<ept id="p2">**</ept> se gli addebiti diretti in uscita devono essere importati nel giornale di registrazione pagamenti fornitore.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source><bpt id="p1">**</bpt>Journal name<ept id="p1">**</ept> – Define a new journal name for the imported direct debit transactions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Nome giornale di registrazione<ept id="p1">**</ept>: definire un nuovo nome di giornale di registrazione per le transazioni di addebito diretto importate.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source><bpt id="p1">**</bpt>Settle transactions<ept id="p1">**</ept> – Set this option to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept> if imported vendor payments must be settled with invoices that are found in the system.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Liquida transazioni<ept id="p1">**</ept>: impostare questa opzione su <bpt id="p2">**</bpt>Sì<ept id="p2">**</ept> se i pagamenti fornitore importati devono essere liquidati con fatture presenti nel sistema.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>You can view the imported information on the <bpt id="p1">**</bpt>Payment transfers<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">È possibile visualizzare le informazioni importate nella pagina <bpt id="p1">**</bpt>Trasferimenti di pagamento<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Additional details</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dettagli aggiuntivi</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>When you import a format configuration from LCS, you import the whole configuration tree which means that the Model and Model mapping configurations are included.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando si importa una configurazione di formato da LCS, si importa l'intera struttura di configurazione, di conseguenza anche il modello e le configurazioni di mapping di modello.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>In the Payment model starting from version 8, the mappings are located in separate ER configurations in the solution tree (Payment model mapping 1611, Payment model mapping to destination ISO20022, etc).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nel modello di pagamento a partire dalla versione 8, i mapping si trovano in configurazioni ER distinte nella struttura della soluzione (mapping di modello di pagamento 1611, mapping di modello di pagamento alla destinazione ISO20022 e così via).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>There are many different payment formats under one model (Payment model), thus separate mapping handling is a key for easy solution maintenance.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In un modello (modello di pagamento) vi sono molti formati di pagamento differenti, pertanto la gestione distinta di mapping è fondamentale per gestire facilmente la soluzione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>For example, consider this scenario: you use ISO20022 payments to generate credit transfer files and then you import the return messages from the bank.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ad esempio, in uno scenario in cui si utilizzano pagamenti ISO20022 per generare file di bonifico e quindi si importano i messaggi di reso dalla banca,</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>In this scenario, you should use the following configurations:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">si utilizzerebbero le configurazioni seguenti:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source><bpt id="p1">**</bpt>Payment model<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Modello di pagamento<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source><bpt id="p1">**</bpt>Payment model mapping 1611<ept id="p1">**</ept> – this mapping will be used to generate the export file</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Mapping di modello di pagamento 1611<ept id="p1">**</ept> - il mapping utilizzato per generare il file di esportazione</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source><bpt id="p1">**</bpt>Payment model mapping to destination ISO20022<ept id="p1">**</ept> – this configuration includes all mappings which will be used to import the data (“to destination” mapping direction)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Mapping di modello di pagamento alla destinazione ISO20022<ept id="p1">**</ept> - questa configurazione include tutti i mapping utilizzati per l'importazione dei dati (direzione del mapping "alla destinazione")</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source><bpt id="p1">**</bpt>ISO20022 Credit transfer<ept id="p1">**</ept> – this configuration includes a format component that is responsible for export file generation (pain.001) based on the Payment model mapping 1611, as well as a format to model mapping component which will be used together with Payment model mapping to destination ISO20022 to register exported payments in the system for further import purposes (import in CustVendProcessedPayments technical table)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Bonifico ISO20022<ept id="p1">**</ept> - questa configurazione include un componente di formato responsabile della generazione del file di esportazione (pain.001) in base al mapping di modello di pagamento 1611; include inoltre un formato per il componente del mapping di modello utilizzato insieme al mapping di modello di pagamento alla destinazione ISO20022 per registrare i pagamenti esportati nel sistema per ulteriori scopi di importazione (importazione nella tabella tecnica CustVendProcessedPayments)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source><bpt id="p1">**</bpt>ISO20022 Credit transfer (CE)<ept id="p1">**</ept>, where CE correspond to country extension – derived format to the ISO20022 Credit transfer with the same structure and with certain country-specific differences</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Bonifico ISO20022 (CE)<ept id="p1">**</ept>, dove CE è il codice del paese - il formato derivato per il bonifico ISO20022 con la stessa struttura e con differenze specifiche del paese</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source><bpt id="p1">**</bpt>Pain.002<ept id="p1">**</ept> – this format will be used together with the Payment model mapping to destination ISO20022 in order to import the pain.002 file into vendor payments transfers journal</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Pain.002<ept id="p1">**</ept> - il formato utilizzato insieme al mapping di modello di pagamento alla destinazione ISO20022 per importare il file pain.002 nel giornale di registrazione dei trasferimenti relativi ai pagamenti fornitore</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source><bpt id="p1">**</bpt>Camt.054<ept id="p1">**</ept> – this format will be used together with the Payment model mapping to destination ISO20022 to import the camt.054 file into vendor payments transfers journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Camt.054<ept id="p1">**</ept> - il formato utilizzato insieme al mapping di modello di pagamento alla destinazione ISO20022 per importare il file camt.054 nel giornale di registrazione dei trasferimenti relativi ai pagamenti fornitore</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>The same format configuration will be used in customer payments import functionality, but the different mapping will be used in the Payment model mapping to destination ISO20022 configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La stessa configurazione di formato è utilizzata nella funzionalità di importazione dei pagamenti cliente, ma nella configurazione del mapping di modello di pagamento alla destinazione ISO20022 viene utilizzato un mapping differente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>For more information about Electronic reporting, refer to <bpt id="p1">[</bpt>Electronic reporting overview<ept id="p1">](../../dev-itpro/analytics/general-electronic-reporting.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per ulteriori informazioni sui report elettronici, vedere <bpt id="p1">[</bpt>Panoramica dei report elettronici<ept id="p1">](../../dev-itpro/analytics/general-electronic-reporting.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>Additional resources</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Risorse aggiuntive</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source><bpt id="p1">[</bpt>Create and export vendor payments using ISO20022 payment format<ept id="p1">](./tasks/create-export-vendor-payments-iso20022-payment-format.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Creare ed esportare i pagamenti fornitore usando il formato di pagamento ISO20022<ept id="p1">](./tasks/create-export-vendor-payments-iso20022-payment-format.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source><bpt id="p1">[</bpt>Import ISO20022 credit transfer configuration<ept id="p1">](./tasks/import-iso20022-credit-transfer-configuration.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Importare la configurazione di bonifico ISO20022<ept id="p1">](./tasks/import-iso20022-credit-transfer-configuration.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source><bpt id="p1">[</bpt>Import ISO20022 direct debit configuration<ept id="p1">](./tasks/import-iso20022-direct-debit-configuration.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Importare la configurazione di addebito diretto ISO20022<ept id="p1">](./tasks/import-iso20022-direct-debit-configuration.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source><bpt id="p1">[</bpt>Set up company bank accounts for ISO20022 credit transfers<ept id="p1">](./tasks/set-up-company-bank-accounts-iso20022-credit-transfers.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Impostare i conti bancari della società per i bonifici ISO20022<ept id="p1">](./tasks/set-up-company-bank-accounts-iso20022-credit-transfers.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source><bpt id="p1">[</bpt>Set up company bank accounts for ISO20022 direct debits<ept id="p1">](./tasks/set-up-company-bank-accounts-iso20022-direct-debits.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Impostare i conti bancari della società per gli addebiti diretti ISO20022<ept id="p1">](./tasks/set-up-company-bank-accounts-iso20022-direct-debits.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source><bpt id="p1">[</bpt>Set up customers and customer bank accounts for ISO20022 direct debits<ept id="p1">](./tasks/set-up-bank-accounts-iso20022-direct-debits.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Impostare i clienti e i conti bancari dei clienti per gli addebiti diretti ISO20022<ept id="p1">](./tasks/set-up-bank-accounts-iso20022-direct-debits.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source><bpt id="p1">[</bpt>Set up method of payment for ISO20022 credit transfer<ept id="p1">](./tasks/set-up-method-payment-iso20022-credit-transfer.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Impostare un metodo di pagamento per bonifico ISO20022<ept id="p1">](./tasks/set-up-method-payment-iso20022-credit-transfer.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source><bpt id="p1">[</bpt>Set up method of payment for ISO20022 direct debit<ept id="p1">](./tasks/setup-method-payment-iso20022-direct-debit.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Impostare un metodo di pagamento per addebito diretto ISO20022<ept id="p1">](./tasks/setup-method-payment-iso20022-direct-debit.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source><bpt id="p1">[</bpt>Set up vendors and vendor bank accounts for ISO20022 credit transfers<ept id="p1">](./tasks/set-up-vendor-iso20022-credit-transfers.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Impostare i fornitori e i conti bancari dei fornitori per i bonifici ISO20022<ept id="p1">](./tasks/set-up-vendor-iso20022-credit-transfers.md)</ept></target></trans-unit>
      </group>
    </body>
  </file>
</xliff>