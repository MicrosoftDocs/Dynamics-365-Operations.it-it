---
title: La quantità supera la percentuale di limite minimo di fornitura durante la generazione del documento di trasporto
description: Quando si genera un documento di trasporto, il carico in uscita contiene una quantità che supera la percentuale di limite minimo di fornitura.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ecdd377d12faf40f64736e93671dcf42ff132403
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249122"
---
# <a name="quantity-exceeds-under-delivery-percentage-during-packing-slip-generation"></a>La quantità supera la percentuale di limite minimo di fornitura durante la generazione del documento di trasporto

Codice errore: SYS24921

## <a name="symptoms"></a>Sintomi

Quando si genera un documento di trasporto, il carico in uscita contiene una quantità che supera la percentuale di limite minimo di fornitura.

Quando si tenta di generare il documento di trasporto, il sistema mostra il seguente messaggio di errore:

> Il limite minimo di fornitura della riga è pari al %1 percento, mentre quello consentito è solo del %2 percento.

Pertanto, non è possibile generare il documento di trasporto per il carico.

## <a name="cause"></a>Causa

La quantità prelevata per il carico o la spedizione è minore della quantità ordinata e non rientra nell'intervallo della percentuale di limite minimo di fornitura.

## <a name="resolution"></a>Risoluzione

Il carico o la spedizione si trova attualmente in uno stato in cui la generazione del documento di trasporto non riesce. Per risolvere il problema, completare una o più delle attività seguenti:

- Rettifica la percentuale di limite minimo di fornitura.
- Storna e apporta rettifiche.

### <a name="adjust-the-under-delivery-percentage"></a>Rettifica la percentuale di limite minimo di fornitura

Utilizza la seguente procedura per rettificare la percentuale di limite minimo di fornitura.

1. Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini**.
1. Selezionare l'ordine cliente per il quale non è possibile registrare un documento di trasporto per il carico.
1. Nella scheda  **Righe ordine cliente**, seleziona la riga ordine cliente dell'articolo che supera la percentuale di limite minimo di fornitura.
1. Nella scheda  **Dettagli riga** seleziona **Consegna**.
1. Imposta il campo **Limite minimo di fornitura** su una percentuale maggiore che tiene conto della quantità prelevata rispetto alla quantità di carico, in modo che possa procedere la generazione del documento di trasporto.

### <a name="reverse-and-make-adjustments"></a>Storna e apporta rettifiche

Storna tutto ciò che è stato registrato per il carico (ad esempio, documento di trasporto, conferma di spedizione e lavoro), apporta le rettifiche all'ordine di vendita, rilascia nuovamente l'ordine al magazzino e completa la procedura di spedizione.

Utilizza la seguente procedura per annullare un documento di trasporto.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Nel riquadro azioni, nella scheda  **Spedisci e ricevi** nel gruppo  **Storna** seleziona  **Annulla documenti di trasporto**.

Utilizza la seguente procedura per stornare una conferma di spedizione.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Nel riquadro azioni, nella scheda  **Spedisci e ricevi** nel gruppo  **Storna** seleziona  **Storna conferma spedizione**.

Utilizza la seguente procedura per stornare il lavoro.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Nella scheda  **Lavoro** del riquadro azioni, nel gruppo  **Carichi**, seleziona  **Storna lavoro**.
