---
title: Principi di riduzione degli sconti
description: In questo argomento viene descritto come impostare i principi di riduzione. I principi di riduzione controllano il comportamento quando più sconti si applicano allo stesso articolo o transazione.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e6b178704fde18036d526e7a645cb9b4f8bd66c7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579066"
---
# <a name="rebate-reduction-principles"></a>Principi di riduzione degli sconti

[!include [banner](../includes/banner.md)]

Puoi raggruppare le transazioni di gestione degli sconti in *principi di riduzione* per ridurre altri accantonamenti associati a un articolo e/o ridurre i valori risultanti dei calcoli degli sconti. Dopo aver impostato i principi di riduzione degli sconti, è possibile facoltativamente assegnarli, come richiesto, alle righe delle transazioni di gestione degli sconti.

Le regole dei principi di riduzione degli sconti si applicano solo quando le transazioni di sconto si sovrappongono. Pertanto, potrebbero concedere più sconti in situazioni in cui non sono dovuti più sconti.

## <a name="manage-rebate-reduction-principles"></a>Gestire i principi di riduzione degli sconti

Per lavorare con i principi di riduzione degli sconti, vai a **Gestione degli sconti \> Impostazioni \> Principi di riduzione degli sconti**. Quindi utilizza i pulsanti nel riquadro azioni per aggiungere e rimuovere i principi di riduzione secondo necessità. Per ogni principio imposta i campi come descritto nella tabella seguente.

| Campo | descrizione |
|---|---|
| Principio di riduzione degli sconti | Immetti un nome univoco per il principio di riduzione dello sconto. |
| descrizione | Immetti una descrizione del principio di riduzione dello sconto. |
| Applicare la riduzione | Seleziona questa casella di controllo per applicare una base di riduzione agli sconti che appartengono a questo principio di riduzione dello sconto. |
| Base di riduzione | Se hai selezionato la casella di controllo **Applica riduzione** seleziona la base di riduzione (*Accantonamento*, *Sconti*, o *Entrambi*). Se selezioni *Entrambi* e se per una transazione precedente sono stati registrati sia un accantonamento che uno sconto, verrà applicato solo lo sconto. |
| Escludere dalla riduzione | Se questa casella di controllo è selezionata, gli accantonamenti e gli sconti che appartengono a questo principio di riduzione degli sconti saranno esclusi dalle riduzioni successive. L'impostazione del campo **Base di riduzione** non si applica a questa impostazione. |

## <a name="examples-of-rebate-reduction-principle-setups"></a>Esempi di configurazioni del principio di riduzione dello sconto

La tabella seguente mostra alcuni esempi tipici di impostazioni del principio di riduzione dello sconto. Per ciascuno di questi principi di riduzione dello sconto, il valore del campo **Descrizione** descrive lo scopo del principio di riduzione dello sconto.

| Principio di riduzione degli sconti | descrizione | Applicare la riduzione | Base di riduzione | Escludere dalla riduzione |
|---|---|---|---|---|
| Differito | Riduci sconto | Sì | Entrambi | No |
| Exclreb | Escludi sconto | Sì | Sconto | Sì |
| Multiplo | Sconti multipli | Sì | Entrambi | Sì |
| Nessuno | Solo accantonamento e sconto | No | Entrambi | Sì |
| Esegui provisioning | Solo accantonamento | Sì | Esegui provisioning | No |
| Sconto | Solo sconto | Sì | Sconto | Sì |

## <a name="examples-of-rebate-reduction-principle-calculations"></a>Esempi di calcoli del principio di riduzione dello sconto

Hai un ordine cliente con una singola riga. Questa riga ha un valore di $1.000. All'ordine si applicano le seguenti transazioni:

- **Transazione 1:** 10 percento su $1.000
- **Transazione 2:** 15 percento su $1.000
- **Transazione 3:** 20 percento su $1.000
- **Transazione 4:** 25 percento su $1.000

L'ordine di elaborazione è molto importante. L'ordine di elaborazione si basa sul modo in cui lavori, come descritto in [Elaborare, rivedere e registrare gli sconti](process-review-post.md).

Ad esempio, la tabella seguente riepiloga il risultato se si utilizza l'ordine *1, 2, 3, 4* e se elabori solo gli accantonamenti.

| Accordo | Descrizione e impostazioni | Risultato dell'accantonamento |
|---|---|---|
| 1 | <p>La classificazione non controlla altre transazioni per sconti. Il controllo viene effettuato sia per gli accantonamenti che per gli sconti.</p><ul><li>**Applica riduzione:** *No*</li><li>**Base di riduzione:** *Entrambi*</li><li>**Escludere dalla riduzione:** *No*</li></ul> | $1.000 × 10% = $100 |
| 2 | <p>La classificazione controlla le altre transazioni per le riduzioni, ma viene contrassegnata in modo che venga ignorata. Il controllo viene effettuato solo per gli sconti.</p><ul><li>**Applica riduzione:** *Sì*</li><li>**Base di riduzione:** *Sconto*</li><li>**Escludere dalla riduzione:** *Sì*</li></ul> | $1.000 × 15% = $150 |
| 3 | <p>La classificazione controlla altre transazioni per sconti. Il controllo viene effettuato sia per gli accantonamenti che per gli sconti.</p><ul><li>**Applica riduzione:** *Sì*</li><li>**Base di riduzione:** *Entrambi*</li><li>**Escludere dalla riduzione:** *No*</li></ul> | ($1.000 – Transazione 1) × 20% = $180 |
| 4 | <p>La classificazione controlla altre transazioni per sconti. Il controllo viene effettuato sia per gli accantonamenti che per gli sconti.</p><ul><li>**Applica riduzione:** *Sì*</li><li>**Base di riduzione:** *Entrambi*</li><li>**Escludere dalla riduzione:** *No*</li></ul> | ($1.000 – Transazione 1 – Transazione 3) × 25% = $180 |

La tabella seguente mostra alcuni esempi in cui l'accantonamento viene elaborato in ordini diversi e in cui vengono quindi raggiunti totali diversi. La varianza degli accantonamenti dipende dall'ordine in cui il sistema elabora le transazioni. È importante comprendere in che modo l'ordine di elaborazione influisce sull'importo dello sconto finale.

| Sequenza | Calcolo |
|---|---|
| 1<br>(1, 2, 3, 4) | <ul><li>**Transazione 1:** $1.000 × 10% = $100</li><li>**Transazione 2:** $1.000 × 15% = $150</li><li>**Transazione 3:** ($1.000 – Transazione 1) × 20% = $180</li><li>**Transazione 4:** ($1.000 – Transazione 1 – Transazione 2) × 25% = $180</li><li>**Totale accantonamento:** $610</li></ul> |
| 2<br>(4, 3, 2, 1) | <ul><li>**Transazione 4:** $1.000 x 25% = $250</li><li>**Transazione 3:** ($1.000 – Transazione 4) × 20% = $150</li><li>**Transazione 2:** $1.000 x 15% = $150</li><li>**Transazione 1:** $1.000 x 10% = $100</li><li>**Totale accantonamento:** $650</li></ul> |
| 3<br>(3, 2, 1, 4) | <ul><li>**Transazione 3:** $1.000 x 20% = $200</li><li>**Transazione 2:** $1.000 x 15% = $150</li><li>**Transazione 1:** $1.000 x 10% = $100</li><li>**Transazione 4:** ($1.000 – Transazione 3 – Transazione 1) × 25% = $175</li><li>**Totale accantonamento:** $625</li></ul> |
| 4<br>(2, 4, 1, 3) | <ul><li>**Transazione 2:** $1.000 × 15% = $150</li><li>**Transazione 4:** $1.000 × 25% = $250</li><li>**Transazione 1:** $1.000 × 10% = $100</li><li>**Transazione 3:** ($1.000 – Transazione 4 – Transazione 1) × 20% = $130</li><li>**Totale accantonamento:** $630</li></ul> |
