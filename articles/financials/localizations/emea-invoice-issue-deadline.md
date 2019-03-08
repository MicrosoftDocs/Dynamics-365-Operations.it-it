---
title: Scadenza emissione fattura
description: In questo articolo viene illustrato come impostare i parametri per calcolare le date di scadenza per l'emissione di fatture cliente e fatture fornitore nell'Unione Europea (UE).
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, LedgerInvoiceIssueDueDateSetup_W
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 10923
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Iceland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 942b48170d7c164e16d2b8f5544b8777668adab3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "370978"
---
# <a name="invoice-issue-deadline"></a>Scadenza emissione fattura

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrato come impostare i parametri per calcolare le date di scadenza per l'emissione di fatture cliente e fatture fornitore nell'Unione Europea (UE).

La direttiva 45/2010 dell'Unione Europea (EU) e altre direttive richiedono che le spedizioni nell'UE (spedizioni intracomunitarie) debbano essere fatturate entro il quindicesimo giorno del mese dopo la consegna. Contemporaneamente, ogni paese UE può avere scadenze di fatturazione diverse per le consegne nazionali. La funzionalità della data di scadenza emissione fattura consente di allineare l'intervallo di date al tipo di paese. Quindi, per tutte le spedizioni a e da un paese di tipo specifico, la data di scadenza emissione fattura viene calcolata utilizzando le regole stabilite nell'intervallo di date specificato. Inoltre, è possibile ottenere tutti i documenti di trasporto con una data di scadenza emissione fattura specifica, filtrare in base alla data di scadenza emissione fattura durante la fatturazione di vendite periodiche e controllare la data di emissione fattura delle vendite durante la registrazione della fattura. È possibile impostare un codice intervallo date, quindi una regola di calcolo per la data di emissione della fattura assegnando il codice intervallo date a un tipo di paese. La regola di calcolo viene utilizzata per calcolare la data di scadenza per l'emissione delle fatture per le seguenti transazioni:

-   Spedizioni all'interno dell'UE
-   Spedizioni nazionali all'interno di uno stato membro dell'UE

È inoltre possibile impostare i controlli di data per assicurarsi che le fatture cliente e le note di accredito per le transazioni cliente vengano generate entro il periodo specificato successivo alla consegna.

## <a name="prerequisites"></a>Prerequisiti
Nella seguente tabella vengono visualizzati i prerequisiti necessari per poter utilizzare la funzionalità della data di scadenza emissione fattura.

| Categoria            | Prerequisito                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Paese      | L'indirizzo principale della persona giuridica deve essere uno stato membro UE.                                                                                                                                                                                                                                                                                                                    |
| Operazioni di configurazione correlate | Nella pagina **Intervalli date** impostare un intervallo di date utilizzato per calcolare la data di scadenza emissione fattura. Fare clic su **Contabilità generale** &gt; **Impostazione contabilità generale** &gt; **Intervalli date**). Nella pagina **Parametri per il commercio estero**, impostare le proprietà del commercio estero per i vari paesi. (Fare clic su **Imposta** &gt; **Impostazione** &gt; **Commercio estero** &gt; **Parametri per il commercio estero**.) |

## <a name="invoice-issue-due-date-calculation-rule"></a>Regola calcolo data di scadenza per l'emissione delle fatture
Utilizzare la pagina **Imposta il calcolo per la data di scadenza emissione fattura** per impostare una regola di calcolo per la data di emissione della fattura assegnando un codice intervallo date a un tipo di paese.

## <a name="date-control-parameters-for-customer-invoices-and-credit-notes"></a>Parametri di controllo data per le fatture cliente e le note di accredito
È possibile impostare i parametri di controllo data per assicurarsi che le fatture cliente e le note di accredito per le transazioni cliente vengano generate entro il periodo specificato successivo alla consegna. È possibile individuare i parametri nell'area **Controllo date fatture** della pagina **Parametri contabilità clienti**.

## <a name="example"></a>Esempio
Per impostare Microsoft Dynamics 365 for Finance and Operations in modo da calcolare le date di scadenza emissione fattura per le spedizioni intracomunitarie il quindicesimo giorno del mese successivo alla consegna, creare un codice intervallo date e una regola di calcolo con le seguenti impostazioni.

### <a name="date-interval-code"></a>Codice intervallo date

| Campo                                                           | Valore                           |
|-----------------------------------------------------------------|---------------------------------|
| Codice intervallo date                                              | 15-NM                           |
| Descrizione                                                     | Quindicesimo giorno del mese successivo |
| Prima (nel gruppo di campi **Data finale**)                         | Mese                           |
| Inizio/Fine (nel gruppo di campi **Data finale**)                      | Fine periodo                             |
| Giorni di tolleranza (nel gruppo di campi **Data finale**)                            | 15                              |
| Giorni, mesi, anni o periodi (nel gruppo di campi **Data finale**) | Giorni                            |

### <a name="invoice-issue-due-date-calculation-rule"></a>Regola calcolo data di scadenza per l'emissione delle fatture

| Campo               | Valore                                                     |
|---------------------|-----------------------------------------------------------|
| Tipo di paese | **UE**                                                    |
| Data di inizio          | Immettere la data quando la riga di impostazione corrente diventa valida. |
| Codice intervallo date  | **15-NM**                                                 |

## <a name="next-steps"></a>Passaggi successivi
Dopo aver completato l'impostazione dei parametri per calcolare le date di scadenza emissione fattura, è possibile creare e registrare le seguenti transazioni per calcolare automaticamente e aggiornare le date di scadenza per l'emissione delle fatture:

-   **Ordini cliente**: quando si crea un ordine cliente e si registra un documento di trasporto, la data di scadenza per l'emissione della fattura viene calcolata e aggiornata nel documento di trasporto. La data di scadenza viene calcolata in base all'intervallo di date associato al paese specificato nell'indirizzo di consegna dell'ordine cliente. Dopo aver registrato il documento di trasporto, è possibile verificare la data di scadenza emissione fattura nel campo **Data di scadenza emissione fattura** della pagina **Giornale di registrazione documenti di trasporto**. Fare clic su **Vendite e marketing** &gt; **Ordine cliente** &gt; **Spedizione ordine** &gt; **Ddocumento di trasporto**). È possibile visualizzare tutti i documenti di trasporto che non sono fatturati e le relative date di scadenza emissione fattura nella pagina **Documenti di trasporto non fatturati**. (Fare clic su **Vendite e marketing** &gt; **Ordine cliente** &gt; **Spedizione ordine** &gt; **Documenti di trasporto non fatturati**).
-   **Ordini acquisto**: quando si crea un ordine acquisto e si registra un'entrata prodotti, la data di scadenza per l'emissione della fattura viene calcolata e aggiornata all'entrata prodotti. La data di scadenza viene calcolata in base all'intervallo di date associato al paese specificato nell'indirizzo principale del fornitore. Dopo aver registrato l'entrata prodotti, è possibile verificare la data di scadenza emissione fattura nel campo **Data di scadenza emissione fattura** della pagina **Giornale di registrazione entrata prodotti**. Fare clic su **Approvvigionamento** &gt; **Ordini fornitore** &gt; **Ricezione di prodotti** &gt; **Entrata prodotti**). È possibile visualizzare tutte le entrate prodotti non fatturate e le relative date di scadenza emissione fattura nella pagina **Entrate prodotti non fatturate** . (Fare clic su **Approvvigionamento** &gt; **Ordini fornitore** &gt; **Ricezione di prodotti** &gt; **Entrate prodotti non fatturate**).

## <a name="technical-information-for-system-administrators"></a>Informazioni tecniche per gli amministratori di sistema
Se non si ha accesso alle pagine utilizzate per completare le attività menzionate in questo articolo, contattare l'amministratore di sistema e fornire le informazioni indicate nella tabella che segue.

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
<td>Chiavi di configurazione</td>
<td>Fare clic su <strong>Amministrazione sistema</strong> &gt; <strong>Impostazione</strong> &gt; <strong>Licenze</strong> &gt; <strong>Configurazione licenza</strong>. Fare clic sulla chiave di configurazione <strong>Contabilità generale</strong>.</td>
</tr>
<tr class="even">
<td>Ruoli di sicurezza e compiti</td>
<td>Per eseguire questa attività, è necessario essere un membro del ruolo di sicurezza che include i seguenti compiti:
<ul>
<li><strong>CustInvoiceInvoiceAndCashProcessEnable</strong> (Abilitare il processo fattura e cassa)</li>
<li><strong>VendInvoiceInvoicePaymentProcessEnable</strong> (Abilitare il processo fattura e pagamento)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Ruoli e privilegi di sicurezza</td>
<td>Per eseguire questa attività, è necessario essere un membro del ruolo di sicurezza che include i seguenti compiti:
<ul>
<li><strong>CustPackingSlipJournalView</strong> (Visualizzare l'elenco di documenti di trasporto vendite )</li>
<li><strong>VendPackingSlipJournalView</strong> (Visualizzare il giornale di registrazione dell'entrata prodotti dall'ordine acquisto)</li>
<li><strong>LedgerInvoiceIssueDueDateSetupMaintain_W</strong> (Calcolare le date di scadenza per l'emissione della fattura)</li>
</ul></td>
</tr>
</tbody>
</table>





