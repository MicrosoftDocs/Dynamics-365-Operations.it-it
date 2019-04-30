---
title: Impostare e generare file pagamenti sicuri
description: In questo argomento viene descritto come impostare un pagamento sicuro e generare file pagamenti sicuri.
author: abruer
manager: AnnBe
ms.date: 03/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: a5579eae5117a7a3ca517bbcc235c2ed2d925d7f
ms.sourcegitcommit: dd1e1636d351a15f9c1b6808bea359417a9bd690
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "896720"
---
# <a name="set-up-and-generate-positive-pay-files"></a>Impostare e generare file pagamenti sicuri

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come impostare un pagamento sicuro e generare file pagamenti sicuri. 

Impostare il pagamento sicuro per generare l'elenco elettronico degli assegni che viene fornito alla banca. Quando si presenta un assegno alla banca, la banca lo confronta con l'elenco degli assegni. Se l'assegno corrisponde a uno presente nell'elenco, la banca lo liquida. Se l'assegno non corrisponde a un assegno nell'elenco, la banca lo trattiene per esaminarlo.

## <a name="security-for-positive-pay-files"></a>Sicurezza dei file pagamenti sicuri
I file pagamenti sicuri possono contenere dati riservati sui beneficiari e sugli importi dell'assegno. Di conseguenza, assicurarsi di utilizzare le misure di sicurezza appropriate dalla generazione dei file fino alla loro ricezione da parte della banca. I file pagamenti sicuri vengono scaricati nel percorso specificato dal Web browser. Poiché i file pagamenti sicuri possono contenere informazioni riservate, è importante che solo gli utenti autorizzati abbiano accesso per generare e visualizzare queste informazioni in Microsoft Dynamics 365 for Finance and Operations. Utilizzare la seguente tabella per determinare i privilegi necessari.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attività</th>
<th>Privilegio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Generare i file pagamenti sicuri dalla pagina elenco <strong>Conti bancari</strong> o dalla pagina <strong>Conti bancari</strong>.</td>
<td><ul>
<li><strong>Gestisci informazioni su pagamenti sicuri bancari</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="even">
<td>Generare file pagamenti sicuri per più persone giuridiche e conti bancari dalla pagina <strong>Genera un file pagamenti sicuri</strong>.</td>
<td><ul>
<li><strong>Gestisci informazioni su pagamenti sicuri bancari</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Visualizzare i file pagamenti sicuri nella pagina <strong>Riepilogo file pagamenti sicuri</strong>.</td>
<td><strong>Visualizza le informazioni sui pagamenti sicuri per più persone giuridiche</strong> (BankPositivePayView)</td>
</tr>
<tr class="even">
<td>Confermare un file pagamenti sicuri nella pagina <strong>Riepilogo file pagamenti sicuri</strong>.</td>
<td><strong>Conferma file pagamenti sicuri</strong> (BankPositivePayConfirm)</td>
</tr>
<tr class="odd">
<td>Richiamare un file pagamenti sicuri nella pagina <strong>Riepilogo file pagamenti sicuri</strong>.</td>
<td><strong>Richiama file pagamenti sicuri</strong> (BankPositivePayRecall)</td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a>Impostare un formato pagamenti sicuri
Questi file vengono creati tramite entità di dati. Prima di generare un file pagamenti sicuri, è necessario impostare un formato di input trasformazione da utilizzare per convertire le informazioni sull'assegno in un formato interpretabile dalla banca. Nella pagina **Formato pagamenti sicuri** è possibile creare un identificatore di formato file e una descrizione. Il formato di input trasformazione deve essere del tipo XML. Il formato specifico dipende dal file di trasformazione in uso. Ad esempio, il file di esempio XSLT (Extensible Stylesheet Language Transformations) fornito usa il formato **XML-Element**. Utilizzare l'azione **Carica file utilizzati per la trasformazione** per specificare il percorso del file di trasformazione per il formato richiesto dalla banca.

## <a name="example-xslt-file-for-positive-pay-file"></a>Esempio: file XSLT per il file pagamenti sicuri
    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl xslthelper" xmlns="urn:iso:std:iso:20022:tech:xsd:pain.001.001.02" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xslthelper="http://schemas.microsoft.com/BizTalk/2003/xslthelper">
      <xsl:output method="xml" omit-xml-declaration="no" version="1.0" encoding="utf-8"/>
      <xsl:template match="/">
        <xsl:value-of select="'
    '" />
        <Document>
          <xsl:value-of select="'
    '" />
          <!--Header Begin-->
          <xsl:value-of select='string("Vendor ID,Vendor Name,Voided,Document Type,Check Date,Check Number,Check Amount,Checkbook ID,Vendor Class ID,Posted Date")'/>
          <xsl:value-of select="'
    '" />
          <!--Header End-->
          <xsl:for-each select="Document/BANKPOSITIVEPAYEXPORTENTITY">
            <!--Cheque Detail begin-->
            <xsl:value-of select='RECIPIENTACCOUNTNUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='BANKNEGINSTRECIPIENTNAME/text()'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Void") or CHEQUESTATUS/text()=normalize-space("Rejected") or CHEQUESTATUS/text()=normalize-space("Cancelled")'>
                <xsl:value-of select='string("Yes")'/>
              </xsl:when>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Payment")'>
                <xsl:value-of select='string("No")'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='string(" ")'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("Payment")'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='CHEQUENUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='AMOUNTCUR/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("BOA-#1812")'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='RECIPIENTTYPE/text()=normalize-space("Vend")'>
                <xsl:value-of select='VENDGROUP/text()'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='CUSTGROUP/text()'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="'
    '" />
          </xsl:for-each>
        </Document>
      </xsl:template>
    </xsl:stylesheet>

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a>Assegnare il formato pagamenti sicuri a un conto bancario
Per ogni conto bancario per il quale generare le informazioni pagamenti sicuri, è necessario assegnare il formato pagamenti sicuri specificato nella sezione precedente. Nella pagina **Conti bancari** selezionare il formato pagamenti sicuri che corrisponde al conto bancario. Nel campo **Data di inizio pagamenti sicuri** immettere la prima data per generare i file pagamenti sicuri. È importante immettere una data in questo campo. In caso contrario, il file pagamenti sicuri generato includerà tutti gli assegni creati per questo conto bancario.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>Assegnare una sequenza numerica per i file pagamenti sicuri
Ogni file pagamenti sicuri deve essere dotato di un numero univoco. Utilizzare la scheda **Sequenze numeriche** nella pagina **Parametri di gestione cassa e banche** per creare una sequenza numerica per i file pagamenti sicuri.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>Generare un file pagamenti sicuri per un singolo conto bancario
È possibile generare un file pagamenti sicuri per una singola persona giuridica e un singolo conto bancario. Per informazioni su come generare contemporaneamente file pagamenti sicuri per più persone giuridiche e conti bancari, vedere la sezione successiva. Per generare un file pagamenti sicuri per una singola persona giuridica e un singolo conto bancario, aprire la finestra di dialogo **Genera un file pagamenti sicuri** dalla pagina **Conti bancari**. Nel campo **Data limite** immettere l'ultima data dell'assegno da includere nel file pagamenti sicuri. Tutti gli assegni che non sono stati inclusi in un file pagamenti sicuri entro questa data vengono inclusi nel file.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>Generare un file pagamenti sicuri per più conti bancari
Per generare un file pagamenti sicuri per più conti bancari, utilizzare l'attività periodica **Genera un file pagamenti sicuri**. Selezionare il formato pagamenti sicuri per il file e specificare se generare il file per tutte le persone giuridiche o per una persona giuridica selezionata. È anche possibile generare il file pagamenti sicuri per tutti i conti bancari che utilizzano il formato specificato o per un conto bancario selezionato. Nel campo **Data limite** immettere l'ultima data dell'assegno da includere nel file pagamenti sicuri. Tutti gli assegni che non sono stati inclusi in un file pagamenti sicuri entro questa data vengono inclusi nel file.

## <a name="view-the-results-of-positive-pay-file-generation"></a>Visualizzare i risultati della generazione del file pagamenti sicuri
Dopo che il file pagamenti sicuri è stato generato, è possibile visualizzare i risultati nella pagina **Riepilogo file pagamenti sicuri**. Per visualizzare i dettagli dei singoli assegni, utilizzare la pagina dei dettagli **File pagamenti sicuri**.

## <a name="confirm-a-positive-pay-file"></a>Conferma un file pagamenti sicuri
Dopo aver pagato gli assegni elencati in un file pagamenti sicuri, viene visualizzato un numero di conferma dalla banca. È quindi possibile confermare il file pagamenti sicuri. Nella pagina **Riepilogo file pagamenti sicuri**, selezionare un file pagamenti sicuri con stato **Creato**, quindi selezionare l'azione **Immetti conferma**. Quando si conferma un file pagamenti sicuri, viene registrato il numero di conferma ricevuto dalla banca.

## <a name="recall-a-positive-pay-file"></a>Richiamare un file pagamenti sicuri
Per modificare un file pagamenti sicuri, è possibile richiamarlo. Nella pagina **Riepilogo file pagamenti sicuri**, selezionare un file pagamenti sicuri con stato **Creato**, quindi selezionare l'azione **Immetti conferma**. Per ogni assegno nel file pagamenti sicuri, viene reimpostato il campo che indica se l'assegno è stato incluso in un file pagamenti sicuri. È quindi possibile creare un nuovo file pagamenti sicuri che includa l'assegno richiamato.



