---
title: Profili registrazione fornitori
description: I profili di registrazione fornitore controllano la registrazione delle transazioni fornitore nella contabilità generale.
author: abruer
ms.date: 06/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.form: VendPosting
ms.openlocfilehash: 922612e536164c7985f0be107f67ad8bbaef7898
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272980"
---
# <a name="vendor-posting-profiles"></a>Profili registrazione fornitori

[!include [banner](../includes/banner.md)]

I profili di registrazione fornitore controllano la registrazione delle transazioni fornitore nella contabilità generale.

## <a name="vendor-posting-profiles"></a>Profili registrazione fornitori

I profili registrazione del fornitore consentono di assegnare i conti CoGe e le impostazioni del documento a tutti i fornitori, a un gruppo di fornitori o a un singolo fornitore. Queste impostazioni verranno utilizzate quando si creano ordini fornitore, fatture fornitore e pagamenti in contanti. Per alcune transazioni, è possibile selezionare un profilo registrazione diverso a cui verrà accordata precedenza sui profili registrazione impostati per le transazioni in questa pagina. Il profilo di registrazione predefinito viene definito nella scheda dettaglio **Contabilità generale e IVA** nella pagina **Parametri contabilità fornitori**. Il profilo di registrazione predefinito verrà incluso automaticamente nell'intestazione di nuovi documenti in cui è possibile modificarlo in un profilo registrazione diverso se necessario.

È inoltre possibile associare le definizioni di registrazione ai tipi di registrazione transazioni nella pagina **Definizioni di registrazione transazioni**. Le definizioni di registrazione controllano la registrazione delle transazioni fornitore nella contabilità generale invece dei profili registrazione.

## <a name="creating-a-posting-profile"></a>Creazione di un profilo registrazione
### <a name="setup"></a>**Impostazioni**

Specificare i conti CoGe utilizzati nella registrazione delle transazioni che utilizzano il profilo registrazione selezionato. Selezionare un codice conto e, quando possibile, un numero di conto o di gruppo per il profilo registrazione selezionato. Durante il processo di registrazione, il profilo registrazione più appropriato per ciascuna transazione si trova cercando il codice conto, il numero di conto o la combinazione gruppo e numero più specifica in base alla seguente priorità.

| **Codice conto** - valore del campo | **Numero conto/gruppo** - valore del campo        | Priorità ricerca |
|------------------------------|---------------------------------------------|-----------------|
| **Tabella**                    | Conto specifico del fornitore.                     | 1               |
| **Raggruppa**                    | Gruppo di fornitori assegnato al fornitore | 2               |
| **Tutte**                      | Vuoto                                       | 3               |

Se si desidera assegnare lo stesso profilo registrazione a tutte le transazioni fornitore, impostare un solo profilo registrazione con il valore **Tutti** nel campo **Codice conto**. Specificare i valori seguenti per impostare il profilo registrazione.

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
<td>Immettere un codice per il profilo registrazione. Ad esempio, è possibile creare due profili registrazione per ottenere un conto per i saldi fornitore in valuta nazionale e un altro conto per i saldi fornitore in valuta estera. È possibile chiamare un conto Nazionale e l'altro Estero.</td>
</tr>
<tr class="even">
<td><strong>Descrizione</strong></td>
<td>Immettere una descrizione del profilo registrazione.</td>
</tr>
<tr class="odd">
<td><strong>Codice conto</strong></td>
<td>Specificare se il profilo registrazione è valido per uno specifico fornitore, un gruppo di fornitori o tutti i fornitori.
<ul>
<li><strong>Tabella</strong>: il profilo registrazione viene utilizzato per un singolo fornitore. Selezionare il conto fornitore nel campo <strong>Numero conto/gruppo</strong>.</li>
<li><strong>Gruppo</strong>: il profilo registrazione viene utilizzato per un gruppo di fornitori. Selezionare il gruppo fornitori nel campo <strong>Numero conto/gruppo</strong>.</li>
<li><strong>Tutti</strong>: il profilo registrazione viene utilizzato per tutti i fornitori. Lasciare vuoto il campo <strong>Numero conto/gruppo</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Numero conto/gruppo</strong></td>
<td>Se si seleziona <strong>Tabella</strong> nel campo <strong>Codice conto</strong>, selezionare il numero di conto del fornitore associato al profilo registrazione. Se è selezionata l'opzione <strong>Gruppo</strong>, indicare un gruppo di fornitori. Se si seleziona <strong>Tutti</strong>, lasciare vuoto questo campo.</td>
</tr>
<tr class="odd">
<td><strong>Conto riepilogativo</strong></td>
<td>Selezionare il conto CoGe da utilizzare come conto riepilogativo per i fornitori a cui fa riferimento il profilo registrazione. Il parametro <strong>Non consentire immissione manuale</strong> per questo conto principale verrà contrassegnato. Se successivamente si rimuove questo conto dal profilo di registrazione, convalidare l'impostazione <strong>Non consentire immissione manuale</strong> nella pagina <strong>Conti principali</strong>. 
<p><strong>Nota:</strong> se è selezionata l'opzione <strong>Usa definizioni di registrazione</strong> della pagina <strong>Parametri di contabilità generale</strong>, viene utilizzata la definizione di registrazione transazioni per le fatture fornitore anziché il conto riepilogativo.</p>
</td>
</tr>
<tr class="even">
<td><strong>Conto di liquidazione</strong></td>
<td>Selezionare il conto CoGe liquidità utilizzato per le previsioni di cassa. Questo campo è disponibile solo quando le previsioni di cassa sono abilitate.</td>
</tr>
<tr class="odd">
<td><strong>Pagamenti anticipati IVA</strong></td>
<td>Selezionare il conto per i pagamenti IVA incassati in anticipo.
<p><strong>Nota:</strong> il profilo registrazione utilizzato quando il pagamento viene contrassegnato come pagamento anticipato è selezionato nel profilo <strong>Registrazione</strong> con il campo <strong>Giustificativo giornale di registrazione per pagamento anticipato</strong> nell'area <strong>Contabilità generale e IVA</strong> della pagina <strong>Parametri contabilità fornitori</strong>.</p>
</td>
</tr>
<tr class="even">
<td><strong>Arrivo</strong></td>
<td>Selezionare il conto CoGe in cui devono essere registrate le informazioni sulle fatture fornitore non approvate. Le informazioni vengono immesse nel giornale di registrazione del registro fatture. Si supponga ad esempio che un utente immetta informazioni molto generali sulle fatture fornitore non appena queste vengono inserite nel registro fatture. Alla registrazione del registro fatture, le transazioni verranno registrate nel conto immesso in questo campo e nel campo <strong>Conto di contropartita</strong>. Una volta approvate le fatture, il debito verrà trasferito dal conto Arrivi al conto riepilogativo del fornitore.</td>
</tr>
<tr class="odd">
<td><strong>Conto di contropartita</strong></td>
<td>Selezionare il conto CoGe da utilizzare per la registrazione in contropartita delle fatture fornitore aggiornate mediante il registro fatture. Il conto di contropartita funge da contropartita per le transazioni registrate nei conti arrivi. Di conseguenza, il conto contiene gli acquisti fornitore non ancora approvati.</td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a>**Restrizioni tabella**

Per le transazioni con il profilo registrazione selezionato, specificare se le transazioni verranno liquidate automaticamente, gli interessi verranno calcolati e le lettere di sollecito verranno emesse. È inoltre possibile selezionare il conto utilizzato quando le transazioni con il profilo registrazione selezionato vengono chiuse.

Specificare i valori seguenti per impostare il profilo registrazione

| Campo          | Descrizione                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Liquidazione** | Selezionare questa opzione per attivare la liquidazione automatica delle transazioni con questo profilo registrazione. Se questa opzione è deselezionata, è necessario liquidare manualmente le transazioni utilizzando la pagina **Liquida transazioni aperte**. |
| **Annulla**     | Selezionare questa opzione per poter annullare le transazioni con questo profilo registrazione.                                                                                                               |
| **Chiudi**      | Selezionare un profilo registrazione da applicare quando le transazioni con il profilo registrazione specificato vengono chiuse. È considerata chiusa una transazione liquidata completamente.                                       |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
