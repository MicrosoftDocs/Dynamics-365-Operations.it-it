---
title: Genera righe fattura quando importi fatture fornitore
description: Questo articolo descrive la funzionalità per la generazione automatica delle righe fattura sulle fatture fornitore quando le fatture vengono importate.
author: sunfzam
ms.date: 09/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5cb2c1234de03e9777921c18e4cbb81eec7feef9
ms.sourcegitcommit: 9c637bcf4e2eb8f711290a861492f038feaf1568
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2022
ms.locfileid: "9462276"
---
# <a name="generate-invoice-lines-when-you-import-vendor-invoices"></a>Genera righe fattura quando importi fatture fornitore

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo articolo descrive la funzionalità per la generazione automatica delle righe fattura sulle fatture fornitore quando le fatture vengono importate.

A volte, le fatture fornitore contengono informazioni limitate, come le informazioni sul destinatario e i subtotali. Tuttavia, non contengono informazioni per le voci. Quando si importano le fatture, le righe fattura vengono automaticamente generate, in base alle informazioni sull'ordine d'acquisto corrispondente.

Per abilitare la creazione automatica di righe fattura, segui questi passaggi.

1.  Passare a **Contabilità fornitori \> Impostazioni \> Parametri contabilità fornitori**.
2.  Nella scheda **Automazione fattura fornitore**, in **Creazione automatica riga per fatture importate**, impostare l'opzione **Crea automaticamente righe fattura** su **Sì**. 
4.  Nel campo **Scegliere la quantità predefinita per la creazione automatica delle righe fattura**, selezionare la quantità da utilizzare per generare automaticamente le righe fattura:

    - **Quantità ordinata**: le righe verranno generate dalle righe dell'ordine fornitore. Questo valore è il valore predefinito.
    - **Quantità entrata prodotti**: il numero dell'ordine fornitore verrà utilizzato per trovare le ricevute dei prodotti pertinenti. Utilizzerà quindi le quantità delle ricevute dei prodotti per generare righe fattura.

## <a name="data-entity-changes"></a>Modifiche all'entità di dati

Per supportare la funzionalità descritta in questo articolo, l'entità di dati **Intestazione fattura fornitore** è stata migliorata. Sono stati aggiunti tre campi:

- **HeaderOnlyImport**: questo campo deve essere impostato su **Sì** per generare righe per le intestazioni delle fatture.
- **PurchIdRange**: l'elenco dei numeri dell'ordine fornitore. I numeri di fattura possono essere un intervallo, ad esempio **PO0001..PO0009** (dove due punti separano l'inizio e la fine dell'intervallo) o valori discreti, come **PO0001, PO0003, PO0006**. Tutti gli ordini fornitore devono appartenere allo stesso conto fornitore nell'intestazione della fattura. In caso contrario, riceverai il seguente messaggio di errore: "Impossibile generare righe fattura. Gli ordini fornitore hanno account fornitore diversi".
- **PackingslipRange**: l'elenco dei numeri di ricevuta dei prodotti. Le righe della fattura fornitore possono essere create dalle ricevute dei prodotti. Tuttavia, i numeri di ricevuta dei prodotti non sono generalmente inclusi nelle fatture fornitore. Immettere i numeri della ricevuta dei prodotti in questo campo solo se è possibile identificare chiaramente quali sono le entrate prodotti per quali fatture specifiche. Le righe della fattura possono essere create in base alle ricevute dei prodotti. Se viene utilizzata per questo campo, l'impostazione del campo **Scegliere la quantità predefinita per la creazione automatica delle righe fattura** nella pagina **Parametri contabilità fornitori** viene ignorata. 

**Limitazione**: se si immettono più numeri di ricevuta dei prodotti, verranno create diverse fatture fornitore in sospeso con lo stesso numero di fattura. È necessario consolidarli manualmente prima di elaborare ulteriormente la fattura. Nelle versioni future, prevediamo di consolidare automaticamente le fatture, quindi la limitazione verrà rimossa.

Tutte le ricevute dei prodotti devono appartenere allo stesso conto fornitore nell'intestazione della fattura.

## <a name="result"></a>Risultato

Se la generazione delle righe viene completata, nella cronologia dell'automazione delle fatture fornitore viene registrato il seguente messaggio: "Crea automaticamente righe fattura: operazione riuscita".

Se le righe non vengono generate, viene registrato il seguente messaggio di errore: "Crea automaticamente righe fattura: operazione non riuscita".
