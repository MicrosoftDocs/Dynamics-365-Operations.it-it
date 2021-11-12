---
title: Genera righe fattura quando importi fatture fornitore
description: Questo argomento descrive la funzionalità per la generazione automatica delle righe fattura sulle fatture fornitore quando le fatture vengono importate.
author: sunfzam
ms.date: 09/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 87dec3c142ae296975ab98432421be4548085c80
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647895"
---
# <a name="generate-invoice-lines-when-you-import-vendor-invoices"></a>Genera righe fattura quando importi fatture fornitore

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento descrive la funzionalità per la generazione automatica delle righe fattura sulle fatture fornitore quando le fatture vengono importate.

A volte, le fatture fornitore contengono informazioni limitate, come le informazioni sul destinatario e i subtotali. Tuttavia, non contengono informazioni per le voci. Quando si importano le fatture, il sistema può generare automaticamente righe fattura, in base alle informazioni sull'ordine d'acquisto corrispondente.

Per abilitare la creazione automatica di righe fattura, segui questi passaggi.

1.  Passare a **Contabilità fornitori \> Impostazioni \> Parametri contabilità fornitori**.
2.  Nella scheda **Automazione fattura fornitore**, in **Creazione automatica riga per fatture importate**, impostare l'opzione **Crea automaticamente righe fattura** su **Sì**. 
4.  Nel campo **Scegliere la quantità predefinita per la creazione automatica delle righe fattura**, selezionare la quantità che il sistema deve utilizzare per generare automaticamente le righe fattura:

    - **Quantità ordinata**: il sistema genererà righe dalle righe dell'ordine fornitore. Questo valore è il valore predefinito.
    - **Quantità entrata prodotti**: il sistema utilizzerà i numeri dell'ordine fornitore per trovare le ricevute dei prodotti pertinenti. Utilizzerà quindi le quantità delle ricevute dei prodotti per generare righe fattura.

## <a name="data-entity-changes"></a>Modifiche all'entità di dati

Per supportare la funzionalità descritta in questo argomento, l'entità di dati **Intestazione fattura fornitore** è stata migliorata. Sono stati aggiunti tre campi:

- **HeaderOnlyImport**: questo campo deve essere impostato su **Sì** affinché il sistema generi righe per le intestazioni delle fatture.
- **PurchIdRange**: l'elenco dei numeri dell'ordine fornitore. I numeri di fattura possono essere un intervallo, ad esempio **INV0001..INV0009** (dove due punti separano l'inizio e la fine dell'intervallo) o valori discreti, come **INV0001, INV0003, INV0006**. Tutti gli ordini fornitore devono appartenere allo stesso conto fornitore nell'intestazione della fattura. In caso contrario, riceverai il seguente messaggio di errore: "Impossibile generare righe fattura. Gli ordini fornitore hanno account fornitore diversi".
- **PackingslipRange**: l'elenco dei numeri di ricevuta dei prodotti. Le righe della fattura fornitore possono essere create dalle ricevute dei prodotti. Tuttavia, i numeri di ricevuta dei prodotti non sono generalmente inclusi nelle fatture fornitore. Immettere i numeri della ricevuta dei prodotti in questo campo solo se è possibile identificare chiaramente quali sono le entrate prodotti per quali fatture specifiche. Le righe della fattura possono essere create in base alle ricevute dei prodotti. E se viene utilizzata per questo campo, l'impostazione del campo **Scegliere la quantità predefinita per la creazione automatica delle righe fattura** nella pagina **Parametri contabilità fornitori** viene ignorata. 

**Limitazione**: se si immettono più numeri di ricevuta dei prodotti, verranno create diverse fatture fornitore in sospeso con lo stesso numero di fattura. È necessario consolidarli manualmente prima di elaborare ulteriormente la fattura. Nelle versioni future, prevediamo di consentire al sistema di consolidare automaticamente le fatture, quindi la limitazione verrà rimossa.

Tutte le ricevute dei prodotti devono appartenere allo stesso conto fornitore nell'intestazione della fattura.

## <a name="result"></a>Risultato

Se il sistema genera correttamente le righe, nella cronologia dell'automazione delle fatture fornitore viene registrato il seguente messaggio: "Crea automaticamente righe fattura: operazione riuscita".

Se il sistema non riesce a generare righe, viene registrato il seguente messaggio di errore: "Crea automaticamente righe fattura: operazione non riuscita".
