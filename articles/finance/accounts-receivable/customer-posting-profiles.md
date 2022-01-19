---
title: Profili di registrazione cliente
description: Questo argomento descrive i profili di registrazione cliente che controllano la registrazione delle transazioni cliente nella contabilità generale.
author: JodiChristiansen
ms.date: 12/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: roschlom
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91432a401a8f8a499e9f5e2bbe7157408faac822
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/10/2022
ms.locfileid: "7952573"
---
# <a name="customer-posting-profiles"></a>Profili di registrazione cliente

[!include [banner](../includes/banner.md)]

Questo argomento descrive i profili di registrazione cliente che controllano la registrazione delle transazioni cliente nella contabilità generale.

## <a name="customer-posting-profiles"></a>Profili di registrazione cliente

I profili registrazione del cliente ti consentono di assegnare i conti CoGe e le impostazioni del documento a tutti i clienti, a un gruppo di clienti o a un singolo cliente. Queste impostazioni verranno utilizzate quando si creano ordini cliente, fatture, fatture a testo libero, fatture di progetto, giornali di registrazione pagamenti, pagamenti in contanti, lettere di sollecito e note d'interesse. 

Il profilo di registrazione predefinito viene definito nella scheda dettaglio **Contabilità generale e IVA** nella pagina dei **parametri Contabilità clienti**. Viene quindi automaticamente incluso nell'intestazione dei nuovi documenti. Puoi cambiarlo se è richiesto un profilo di pubblicazione diverso. 

Le organizzazioni che accettano pagamenti anticipati dai clienti spesso configurano un secondo profilo di registrazione per i pagamenti anticipati e lo collegano nei parametri come profilo di registrazione predefinito per i pagamenti anticipati. Per ulteriori informazioni, vedi [Pagamenti anticipati dei clienti](customer-prepayments.md).

È inoltre possibile associare le definizioni di registrazione ai tipi di registrazione transazioni nella pagina **Definizioni di registrazione transazioni**. Le definizioni di registrazione vengono usate per controllare la registrazione delle transazioni cliente nella contabilità generale al posto dei profili registrazione. Per ulteriori informazioni, vedere [Definizioni di registrazione](../general-ledger/posting-definitions.md).

## <a name="creating-a-posting-profile"></a>Creazione di un profilo registrazione
Specificare i conti CoGe utilizzati nella registrazione delle transazioni che utilizzano il profilo registrazione selezionato. Selezionare un codice conto e, quando possibile, un numero di conto o di gruppo per il profilo registrazione selezionato. Durante il processo di registrazione, il profilo registrazione più appropriato per ciascuna transazione si trova cercando il codice conto, il numero di conto o la combinazione gruppo e numero più specifica in base alla seguente priorità:

| Codice conto - valore del campo | Numero conto/gruppo - valore del campo                | Priorità ricerca |
|--------------------------|-------------------------------------------------|-----------------|
| Tabella                    | Conto cliente specifico                       | 1               |
| Gruppo                    | Gruppo di clienti assegnato al cliente | 2               |
| Tutte                      | Vuoto                                           | 3               |

Se si desidera assegnare lo stesso profilo registrazione a tutte le transazioni clienti, impostare un solo profilo registrazione con il valore **Tutti** immesso nel campo **Codice conto**. Specificare i valori seguenti per impostare il profilo registrazione.

<table>
<thead>
<tr>
<th>Campo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr>
<td>Profilo registrazione</td>
<td>Immettere un codice per il profilo registrazione. Ad esempio, è possibile creare due profili registrazione per ottenere un conto per i saldi cliente in valuta nazionale e un altro conto per i saldi cliente in valuta estera. È possibile chiamare un conto Nazionale e l'altro Estero.</td>
</tr>
<tr>
<td>Description</td>
<td>Immettere una descrizione del profilo registrazione. Viene utilizzato solo per identificare meglio il profilo registrazione quando viene visualizzato in questa pagina.</td>
</tr>
<tr>
<td>Codice conto</td>
<td>Specificare se il profilo registrazione è applicabile a un singolo cliente, a un gruppo di clienti o a tutti i clienti:
<ul>
<li><b>Tabella</b>: il profilo registrazione viene utilizzato per un singolo cliente. Seleziona il conto cliente nel campo <b>Numero conto/gruppo</b>.</li>
<li><b>Gruppo</b>: il profilo registrazione viene utilizzato per un gruppo di clienti. Seleziona il gruppo di clienti nel campo <b>Numero conto/gruppo</b>.</li>
<li><b>Tuti</b>: il profilo registrazione viene utilizzato per tutti i clienti. Lasciare vuoto il campo <b>Numero conto/gruppo</b>.</li>
</ul>
</td>
</tr>
<tr>
<td>Numero conto/gruppo</td>
<td>Se si seleziona <b>Tabella</b> nel campo <b>Codice conto</b>, seleziona il numero di conto del cliente associato al profilo registrazione. Se è stato selezionato <b>Gruppo</b>, seleziona il gruppo di clienti. Se si seleziona <b>Tutti</b>, lasciare vuoto questo campo.</td>
</tr>
<tr>
<td>Conto riepilogativo</td>
<td>Selezionare il conto principale che sarà utilizzato come conto commerciale Contabilità clienti per i clienti associati al profilo registrazione. Questo conto è il conto per il tipo di registrazione <b>Saldo cliente</b>.</td>
</tr>
<tr>
<td>Conto liquidità per i pagamenti</td>
<td>Selezionare il conto CoGe liquidità utilizzato per le previsioni di cassa. Questo campo verrà visualizzato solo se le previsioni di cassa sono abilitate.</td>
</tr>
<tr>
<td>Pagamenti anticipati IVA</td>
<td><p>Selezionare il conto dell'IVA per i pagamenti incassati in anticipo.</p>
<p><strong>Nota:</strong> Usa la pagina <b>Parametri contabilità clienti</b> per specificare il profilo registrazione da utilizzare quando un pagamento viene contrassegnato come pagamento anticipato.</p>
</td>
</tr>
<tr>
<td>Conto per passività di sconto</td>
<td>Selezionare il conto CoGe per le passività di sconto.</td>
</tr>
<tr>
<td>Sequenza lettere di sollecito</td>
<td>Selezionare l'identificatore della sequenza lettere di sollecito da utilizzare per i clienti a cui viene assegnato il profilo registrazione.</td>
</tr>
<tr>
<td>Codice interessi</td>
<td>Selezionare il codice interessi da utilizzare per il calcolo degli interessi per i clienti a cui viene assegnato il profilo registrazione.</td>
</tr>
</tbody>
</table>

## <a name="posting-examples"></a>Esempi di registrazione

La tabella seguente mostra esempi dei tipi di registrazione predefiniti con conti principali e descrizioni di esempio. La colonna **Debito/Credito** indica se la transazione in genere viene addebitata o accreditata o in alcuni casi può essere registrata. La colonna **Conto di compensazione** indica che il tipo di registrazione è un conto di compensazione. Ciò significa che l'importo registrato in questo conto viene automaticamente stornato quando viene registrata una transazione successiva. 

| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | Description |
|--------------|----------------------|---------------------------|--------------|--------------|------------------|-------------|
| Saldo cliente | 130100 | Commercio contabilità clienti | AttivitÃ  | Entrambi | No | Nel campo **Conto riepilogativo** specifica il conto.|
| Nessuna | 110110 | Conto bancario | AttivitÃ  | Entrambi | No | Specifica il conto principale nel campo **Conto di liquidità per pagamenti**. Questo account non viene utilizzato per la registrazione. Viene utilizzato solo per la previsione del flusso di cassa. |
| Pagamenti anticipati IVA | 202900 | Cancellazione IVA | Passività | Entrambi | Sì | Selezionare il conto dell'IVA per i pagamenti incassati in anticipo. |
| Conto per passività di sconto | 250600 | Ricavi differiti e sconti | Passività | Entrambi | Sì | Seleziona il conto CoGe per le passività di sconto.|     

### <a name="table-restrictions"></a>Restrizioni tabella

Per le transazioni con il profilo registrazione selezionato, specificare se le transazioni verranno liquidate automaticamente, gli interessi verranno calcolati e le lettere di sollecito verranno emesse. È inoltre possibile selezionare il conto utilizzato quando le transazioni con il profilo registrazione selezionato vengono chiuse.

Specificare i valori seguenti per impostare il profilo registrazione:

| Campo                 | Descrizione                                           |
|-----------------------|-------------------------------------------------------|
| Insediamento        | Selezionare questa opzione di controllo per abilitare la liquidazione automatica delle transazioni con questo profilo registrazione. Se l'opzione è deselezionata, è necessario liquidare manualmente le transazioni utilizzando la pagina **Liquida transazioni aperte** o la pagina **Pagamenti cliente**. |
| Interessi          | Selezionare questa opzione se gli interessi devono essere calcolati sui saldi residui per i conti cliente che utilizzano questo profilo. Se questa opzione è deselezionata, gli interessi non verranno calcolati per tali clienti.                                           |
| Lettera di sollecito | Selezionare questa opzione se le lettere di sollecito devono essere generate per i conti cliente che utilizzano questo profilo. Se questa opzione è deselezionata, le lettere di sollecito non verranno generate per tali clienti.                                                 |
| Chiusi             | Selezionare un profilo registrazione da applicare quando le transazioni con il profilo registrazione specificato vengono chiuse. È considerata chiusa una transazione liquidata completamente.             |



Per ulteriori informazioni, vedere [Panoramica pagamenti cliente](../cash-bank-management/tasks/customer-payment-overview.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
