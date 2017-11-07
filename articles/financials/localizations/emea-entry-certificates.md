---
title: Certificati di entrata UE
description: Vengono fornite le informazioni sui certificati di entrata dell'Unione Europea (UE).
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustEntryCertificateJour_W, CustParameters, CustTable, SalesTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 11464
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6856a52ce85d31c4ef8225e56159e8a7ec698fd7
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="eu-entry-certificates"></a>Certificati di entrata UE

[!include[banner](../includes/banner.md)]


Vengono fornite le informazioni sui certificati di entrata dell'Unione Europea (UE).

È possibile completare le seguenti attività per un certificato di entrata UE (Unione Europea):

-   Creare ed emettere un certificato di entrata UE insieme a un documento di trasporto o una fattura cliente per la consegna di articoli o servizi ai paesi UE.
-   Ricevere il certificato di entrata UE assegnato da un cliente UE.
-   Caricare il certificato di entrata UE ricevuto dal cliente o da un fornitore di terze parti responsabile della consegna di articoli al cliente.
-   Associare il certificato di entrata UE caricato con una fattura cliente.
-   Aggiornare lo stato del certificato di entrata UE caricato.

## <a name="prerequisites"></a>Prerequisiti
Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoria</th>
<th>Prerequisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Paese</td>
<td>L'indirizzo principale della persona giuridica deve essere uno stato membro UE.</td>
</tr>
<tr class="even">
<td>Operazioni di configurazione correlate</td>
<td><ul>
<li>Nella pagina <strong>Parametri contabilità clienti</strong> selezionare le opzioni <strong>Abilita gestione certificati di entrata</strong> e <strong>Abilita rilascio certificato di entrata</strong>.</li>
<li>Nella pagina <strong>Clienti</strong> nella Scheda dettaglio <strong>Fattura e consegna</strong>, selezionare l'opzione <strong>Certificato di entrata obbligatorio</strong> per indicare che un certificato di entrata UE è obbligatorio per il cliente. Selezionare l'opzione <strong>Rilascia certificato di entrata</strong> per rilasciare un certificato di entrata UE della persona giuridica al cliente.</li>
<li>Nella pagina <strong>Parametri contabilità clienti</strong> selezionare un codice di sequenza numerica per il riferimento <strong>Certificato di entrata</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Transazioni correlate</td>
<td><ul>
<li>Creare un conto cliente.</li>
<li>Creare un ordine cliente.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="creating-registering-and-uploading-an-eu-entry-certificate"></a>Creazione, registrazione e caricamento di un certificato di entrata UE
È possibile creare un certificato di entrata UE automaticamente o manualmente. Un certificato di entrata UE viene creato e stampato automaticamente quando si registra un documento di trasporto o una fattura per un cliente utilizzando la pagina **Registrazione documento di trasporto** o la pagina **Registrazione fattura**. Per creare o ristampare manualmente un certificato di entrata UE per una fattura cliente, utilizzare la pagina **Giornale di registrazione fatture**. Inoltre, è possibile utilizzare la pagina **Giornale di registrazione certificati di entrata** per immettere i dettagli relativi a un certificato di entrata UE emesso da una terza parte.

### <a name="creating-an-eu-entry-certificate-automatically-or-manually"></a>Creazione di un certificato di entrata UE automaticamente o manualmente

È possibile creare un certificato di entrata UE automaticamente utilizzando un documento di trasporto nella pagina **Tutti gli ordini cliente** o tramite una fattura nella pagina **Ordine cliente**. Per creare manualmente un certificato di entrata UE, è possibile utilizzare una fattura nella pagina **Giornale di registrazione fatture**. È tuttavia necessario modificare lo stato del certificato della fattura prima di creare manualmente un certificato di entrata UE.

### <a name="registering-an-eu-entry-certificate"></a>Registrazione di un certificato di entrata UE

Se è necessaria la registrazione, è possibile utilizzare la pagina **Giornale di registrazione certificati di entrata** per registrare un certificato di entrata UE emesso da una terza parte.

### <a name="uploading-a-received-eu-entry-certificate"></a>Caricamento di un certificato di entrata UE ricevuto

Utilizzare la pagina **Allegati** per caricare un certificato di entrata UE ricevuto firmato da un cliente UE. Dopo aver caricato il certificato, è possibile associarlo a una fattura come prova della consegna di articoli. La prova è obbligatoria se è necessario emettere una fattura che non include l'imposta sul valore aggiunto (IVA) e verrà utilizzata durante il controllo.

### <a name="optional-updating-the-certification-status-and-printing-status-of-an-invoice"></a>Facoltativo: aggiornamento dello stato del certificato e dello stato di stampa di una fattura

È possibile aggiornare lo stato del certificato di entrata e lo stato di stampa di una fattura cliente utilizzando la pagina **Giornale di registrazione fatture**.

## <a name="technical-information-for-system-administrators"></a>Informazioni tecniche per gli amministratori di sistema
Se non si ha accesso alle pagine utilizzate per completare questa attività, contattare l'amministratore di sistema e fornire le informazioni indicate nella tabella che segue.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoria</th>
<th>Prerequisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ruoli di sicurezza e compiti</td>
<td>Per creare e impostare i certificati di entrata UE per articoli o servizi, è necessario essere membri di un ruolo di sicurezza che include le funzioni seguenti:
<ul>
<li><strong>Addetto alla contabilità clienti</strong> (CustInvoiceAccountsReceivableClerk)</li>
<li><strong>Rappresentante assistenza clienti</strong> (TradeCustomerServiceRepresentative)</li>
<li><strong>Addetto vendite</strong> (TradeSalesClerk)</li>
<li><strong>Addetto spedizione</strong> (InventShippingClerk)</li>
</ul></td>
</tr>
</tbody>
</table>






