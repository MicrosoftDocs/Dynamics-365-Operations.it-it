---
title: Profili di registrazione cliente
description: I profili di registrazione cliente controllano la registrazione delle transazioni cliente nella contabilità generale.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dff786d6e872e48f9605f9a472b7bffd409c5b3f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444646"
---
# <a name="customer-posting-profiles"></a>Profili di registrazione cliente

[!include [banner](../includes/banner.md)]

I profili di registrazione cliente controllano la registrazione delle transazioni cliente nella contabilità generale.

<a name="customer-posting-profiles"></a>Profili di registrazione cliente
-------------------------

I profili registrazione del cliente consentono di assegnare i conti CoGe e le impostazioni del documento a tutti i clienti, a un gruppo di clienti o a un singolo cliente. Queste impostazioni verranno utilizzate quando si creano ordini cliente, fatture a testo libero, pagamenti in contanti, lettere di sollecito e note d'interesse. Per alcune transazioni, è possibile selezionare un profilo registrazione diverso a cui verrà accordata precedenza sui profili registrazione impostati per le transazioni in questa pagina. 

Il profilo di registrazione predefinito viene definito nella scheda dettaglio Contabilità generale e IVA nella pagina dei parametri Contabilità clienti. Il profilo di registrazione predefinito verrà incluso automaticamente nell'intestazione di nuovi documenti in cui è possibile modificarlo in un profilo registrazione diverso se necessario.

È inoltre possibile associare le definizioni di registrazione ai tipi di registrazione transazioni nella pagina Definizioni di registrazione transazioni. Le definizioni di registrazione controllano la registrazione delle transazioni cliente nella contabilità generale invece dei profili registrazione.

## <a name="creating-a-posting-profile"></a>Creazione di un profilo registrazione
Specificare i conti CoGe utilizzati nella registrazione delle transazioni che utilizzano il profilo registrazione selezionato. Selezionare un codice conto e, quando possibile, un numero di conto o di gruppo per il profilo registrazione selezionato. Durante il processo di registrazione, il profilo registrazione più appropriato per ciascuna transazione si trova cercando il codice conto, il numero di conto o la combinazione gruppo e numero più specifica in base alla seguente priorità:

| **Codice conto** - valore del campo | **Numero conto/gruppo** - valore del campo            | Priorità ricerca |
|------------------------------|-------------------------------------------------|-----------------|
| **Tabella**                    | Conto cliente specifico                       | 1               |
| **Gruppo**                    | Gruppo di clienti assegnato al cliente | 2               |
| **Tutti**                      | Vuoto                                           | 3               |

Se si desidera assegnare lo stesso profilo registrazione a tutte le transazioni cliente, impostare un solo profilo registrazione con il valore Tutti nel campo Codice conto. Specificare i valori seguenti per impostare il profilo registrazione:

<table>
<thead>
<tr class="header">
<th>Campo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Profilo registrazione</strong></td>
<td>Immettere un codice per il profilo registrazione. Ad esempio, è possibile creare due profili registrazione per ottenere un conto per i saldi cliente in valuta nazionale e un altro conto per i saldi cliente in valuta estera. È possibile chiamare un conto Nazionale e l'altro Estero.</td>
</tr>
<tr class="even">
<td><strong>Descrizione</strong></td>
<td>Immettere una descrizione del profilo registrazione. Viene utilizzato solo per identificare meglio il profilo registrazione quando viene visualizzato in questa pagina.</td>
</tr>
<tr class="odd">
<td><strong>Codice conto</strong></td>
<td>Specificare se il profilo registrazione è applicabile a un singolo cliente, a un gruppo di clienti o a tutti i clienti:
<ul>
<li><strong>Tabella</strong>: il profilo registrazione viene utilizzato per un singolo cliente. Selezionare il conto cliente nel campo Numero conto/gruppo.</li>
<li><strong>Gruppo</strong>: il profilo registrazione viene utilizzato per un gruppo di clienti. Selezionare il gruppo di clienti nel campo Numero conto/gruppo.</li>
<li><strong>Tuti</strong>: il profilo registrazione viene utilizzato per tutti i clienti. Lasciare vuoto il campo Numero conto/gruppo.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Numero conto/gruppo</strong></td>
<td>Se si seleziona Tabella nel campo Codice conto, selezionare il numero di conto del cliente associato al profilo registrazione. Se è stato selezionato Gruppo, selezionare il gruppo di clienti. Se si seleziona Tutti, lasciare vuoto questo campo.</td>
</tr>
<tr class="odd">
<td><strong>Conto riepilogativo</strong></td>
<td>Selezionare il conto CoGe che sarà utilizzato come conto riepilogativo per i clienti associati al profilo registrazione.</td>
</tr>
<tr class="even">
<td><strong>Conto di liquidazione</strong></td>
<td>Selezionare il conto CoGe liquidità utilizzato per le previsioni di cassa. Questo campo verrà visualizzato solo se le previsioni di cassa sono abilitate.</td>
</tr>
<tr class="odd">
<td><strong>Pagamenti anticipati IVA</strong></td>
<td>Selezionare il conto dell'IVA per i pagamenti incassati in anticipo.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Nota" alt="Note" id="alert_note" class="cl_IC101471" /><strong>Nota</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Utilizzare la pagina Parametri contabilità clienti per specificare il profilo registrazione da utilizzare quando un pagamento viene contrassegnato come pagamento anticipato.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><strong>Conto per passività di sconto</strong></td>
<td>Selezionare il conto CoGe per le passività di sconto.</td>
</tr>
<tr class="odd">
<td><strong>Sequenza lettere di sollecito</strong></td>
<td>Selezionare l'identificatore della sequenza lettere di sollecito da utilizzare per i clienti a cui viene assegnato il profilo registrazione.</td>
</tr>
<tr class="even">
<td><strong>Codice interessi</strong></td>
<td>Selezionare il codice interessi da utilizzare per il calcolo degli interessi per i clienti a cui viene assegnato il profilo registrazione.</td>
</tr>
</tbody>
</table>

### 

### <a name="table-restrictions"></a>**Restrizioni tabella**

Per le transazioni con il profilo registrazione selezionato, specificare se le transazioni verranno liquidate automaticamente, gli interessi verranno calcolati e le lettere di sollecito verranno emesse. È inoltre possibile selezionare il conto utilizzato quando le transazioni con il profilo registrazione selezionato vengono chiuse.

Specificare i valori seguenti per impostare il profilo registrazione:

| Campo                 | Descrizione                                                                                                                                                                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Liquidazione**        | Selezionare questa opzione di controllo per abilitare la liquidazione automatica delle transazioni con questo profilo registrazione. Se l'opzione è deselezionata, è necessario liquidare manualmente le transazioni utilizzando la pagina Liquida transazioni aperte o la pagina Pagamenti cliente. |
| **Interessi**          | Selezionare questa opzione se gli interessi devono essere calcolati sui saldi residui per i conti cliente che utilizzano questo profilo. Se questa opzione è deselezionata, gli interessi non verranno calcolati per tali clienti.                                           |
| **Lettera di sollecito** | Selezionare questa opzione se le lettere di sollecito devono essere generate per i conti cliente che utilizzano questo profilo. Se questa opzione è deselezionata, le lettere di sollecito non verranno generate per tali clienti.                                                 |
| **Chiudi**             | Selezionare un profilo registrazione da applicare quando le transazioni con il profilo registrazione specificato vengono chiuse. È considerata chiusa una transazione liquidata completamente.                                                                           |



Per ulteriori informazioni, vedere [Panoramica pagamenti cliente](../cash-bank-management/tasks/customer-payment-overview.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]