---
title: Ricalcolare gli importi netti di riga durante l'importazione di ordini cliente, offerte e resi
description: Questo articolo descrive se e come il sistema ricalcola gli importi netti di riga quando vengono importati ordini cliente, offerte e resi. Descrive inoltre come controllare il comportamento in diverse versioni di Microsoft Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 06/08/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2022-06-08
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: ce34a6be7bc3d14e23bdd8769aa71dc035b983b3
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220629"
---
# <a name="recalculate-line-net-amounts-when-importing-sales-orders-quotations-and-returns"></a>Ricalcolare gli importi netti di riga durante l'importazione di ordini cliente, offerte e resi

[!include [banner](../includes/banner.md)]

Questo articolo descrive se e come il sistema ricalcola gli importi netti di riga quando vengono importati ordini cliente, offerte e resi. Descrive inoltre come controllare il comportamento in diverse versioni di Microsoft Dynamics 365 Supply Chain Management.

## <a name="how-updates-to-net-line-amounts-are-calculated-on-import"></a>Calcolo degli aggiornamenti degli importi netti di riga durante l'importazione

Supply Chain Management versione 10.0.23 ha introdotto l'[aggiornamento rapido 604418](https://fix.lcs.dynamics.com/issue/results/?q=604418). Questo aggiornamento rapido ha modificato le condizioni alle quali il campo **Importo netto** di una riga può essere aggiornato o ricalcolato quando vengono importati gli aggiornamenti di ordini cliente, resi e offerte esistenti. Nella versione 10.0.29, puoi sostituire questo aggiornamento rapido attivando la funzionalità *Calcola importo netto riga all'importazione*. Questa funzionalità ha un effetto simile, ma fornisce un'impostazione globale che ti consente di ripristinare il comportamento precedente se necessario. Sebbene il nuovo comportamento renda il sistema più intuitivo, può produrre risultati imprevisti in specifici scenari in cui vengono soddisfatte tutte le seguenti condizioni:

- I dati che aggiornano i record esistenti vengono importati tramite l'entità *Righe ordine cliente V2*, *Righe di offerta di vendita V2* o *Righe ordine di reso* utilizzando Open Data Protocol (OData), incluse le situazioni in cui utilizzi la doppia scrittura, l'importazione/esportazione tramite Excel e alcune integrazioni di terze parti.
- I [criteri di valutazione degli accordi commerciali](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper) in vigore stabiliscono i criteri di modifica che limitano gli aggiornamenti al campo **Importo netto** nelle righe di ordine cliente, di offerta di vendita e/o di ordine di reso.
- I dati importati includono modifiche al campo **Importo netto** delle righe oppure modifiche (come prezzo unitario, quantità o sconto) che determineranno il valore del campo **Importo netto** delle righe da ricalcolare per uno o più record di riga esistenti.

In questi scenari specifici, i criteri di valutazione degli accordi commerciali limitano gli aggiornamenti al campo **Importo netto** della riga. Questo limite è noto come *criteri di modifica*. A causa di questi criteri, quando utilizzi l'interfaccia utente per modificare o ricalcolare il campo, il sistema ti chiede di confermare se intendi apportare la modifica. Tuttavia, quando importi un record, è il sistema che deve effettuare la scelta. Prima della versione 10.0.23, il sistema lasciava sempre invariato l'importo netto della riga, a meno che l'importo netto della riga in entrata non fosse 0 (zero). Tuttavia, nelle versioni più recenti, il sistema aggiorna o ricalcola sempre l'importo netto come necessario, a meno che non venga espressamente indicato di non farlo. Sebbene il nuovo comportamento sia più logico, potrebbe causare problemi se stai già eseguendo processi o integrazioni che usano il comportamento precedente. In questo articolo viene descritto come ripristinare il comportamento precedente, se necessario.

## <a name="control-calculations-of-line-net-amounts-in-versions-10029-and-later"></a>Controllare i calcoli degli importi netti delle righe nelle versioni 10.0.29 e successive

Supply Chain Management 10.0.29 ha introdotto una funzionalità denominata *Calcola importo netto riga all'importazione*. Questa funzionalità aggiunge un'opzione denominata **Calcola importo netto riga** alla pagina **Parametri contabilità clienti**. Questa opzione ti consente di selezionare tra il comportamento nuovo e quello precedente per il calcolo degli importi netti delle righe all'importazione.

### <a name="turn-the-calculate-line-net-amount-on-import-feature-on-or-off"></a>Attivare o disattivare la funzionalità Calcola importo netto riga all'importazione

Quando esegui l'aggiornamento alla versione 10.0.29, la funzionalità *Calcola importo netto riga all'importazione* è attivata per impostazione predefinita e la nuova opzione **Calcola importo netto riga** è inizialmente impostata su *Sì*. L'impostazione *Sì* corrisponde al nuovo comportamento standard. Corrisponde al comportamento del sistema quando la funzionalità è disattivata, salvo nel caso della funzionalità del [parametro CalculateLineAmount](#CalculateLineAmount), come descritto più avanti in questo articolo. L'impostazione *No* corrisponde al comportamento del sistema prima della versione 10.0.23 e viene fornita principalmente per supportare gli scenari di integrazione legacy.

Gli amministratori possono attivare o disattivare la funzionalità *Calcola importo netto riga all'importazione* utilizzando l'[area di lavoro Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="set-the-calculate-line-net-amount-option"></a>Impostare l'opzione Calcola importo netto riga

Quando la funzionalità *Calcola importo netto riga all'importazione* è attivata, puoi impostare l'opzione **Calcola importo netto riga** procedendo come segue.

1. Andare a **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.
1. Nella scheda **Prezzi**, nella Scheda dettaglio **Calcolo dell'importo netto riga tramite integrazione**, imposta l'opzione **Calcola importo netto riga** su uno dei seguenti valori:

    - *Sì*: il sistema ricalcolerà e aggiornerà sempre gli importi delle righe quando necessario (pertanto, ignorerà i criteri di valutazione degli accordi commerciali).
    - *No*: se l'importo netto esistente o in entrata per qualsiasi riga è 0 (zero), il valore di tale riga viene ricalcolato in base ad altri valori (come il prezzo unitario, la quantità e lo sconto). Se l'importo netto esistente o in entrata è diverso da 0 (zero) e vengono impostati criteri di modifica nel campo **Importo netto** della riga, il campo non viene ricalcolato o aggiornato, anche quando le modifiche in entrata a prezzo, quantità e/o sconto della riga implicherebbero il ricalcolo del totale della riga. Questo comportamento corrisponde a quello della versione 10.0.22.

### <a name="how-the-calculate-line-net-amount-on-import-feature-affects-the-calculatelineamount-parameter"></a><a name="CalculateLineAmount"></a>Come la funzionalità Calcola importo netto riga all'importazione influisce sul parametro CalculateLineAmount

Quando la funzionalità *Calcola importo netto riga all'importazione* è attivata, il valore del parametro `CalculateLineAmount` per le tabelle `SalesLine` e `SalesQuotationLine` non ha alcun effetto. Il comportamento è invece controllato globalmente dall'opzione **Calcola importo netto riga** descritta nella sezione precedente. Pertanto, quando la funzionalità è attivata, non devi assumere alcuna dipendenza in relazione al valore `CalculateLineAmount`.

Quando la funzionalità *Calcola importo netto riga all'importazione* è disattivata, il parametro `CalculateLineAmount` per le tabelle `SalesLine` e `SalesQuotationLine` funziona come nelle versioni da 10.0.23 a 10.0.28 di Supply Chain Management, come descritto nella sezione successiva.

## <a name="control-line-net-amount-calculations-in-versions-10028-and-earlier"></a>Controllare i calcoli degli importi netti delle righe nelle versioni 10.0.28 e precedenti

Quando l'[aggiornamento rapido 604418](https://fix.lcs.dynamics.com/issue/results/?q=604418) è stato introdotto nella versione 10.0.23, è diventato possibile selezionare il modo in cui ogni entità di dati pertinente deve comportarsi quando un importo netto di riga viene modificato o ricalcolato a causa di altre modifiche (come il prezzo di un articolo aggiornato). Puoi controllare questo comportamento impostando il nuovo parametro `CalculateLineAmount` per ogni riga su uno dei seguenti valori nel file importato:

- **`CalculateLineAmount` = *1***: il campo **Importo netto** della riga viene sempre ricalcolato e aggiornato, indipendentemente dal fatto che siano stati impostati criteri di modifica per il campo e dal valore dell'importo netto della riga in entrata o esistente.
- **`CalculateLineAmount` = *0***: se l'importo netto esistente o in entrata per qualsiasi riga è 0 (zero), il valore di tale riga viene ricalcolato in base ad altri valori (come il prezzo unitario, la quantità e lo sconto). Se l'importo netto esistente o in entrata è diverso da 0 (zero) e vengono impostati criteri di modifica nel campo **Importo netto** della riga, il campo non viene ricalcolato o aggiornato.  

Il comportamento del sistema dipende dalla versione di Supply Chain Management in uso:

- Nella versione 10.0.22 e precedenti, il sistema si comporta sempre come se `CalculateLineAmount` fosse impostato su *0* e non è possibile fare in modo che si comporti come se `CalculateLineAmount` fosse impostato su *1*.
- Nelle versioni da 10.0.23 a 10.0.28, il sistema si comporta come se `CalculateLineAmount` fosse impostato su *1* per tutte le righe in cui non è impostato in modo esplicito su *0* nel file di importazione.
