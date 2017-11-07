---
title: Effetti di ammortamento con storni
description: In questo articolo vengono illustrate le implicazioni potenziali dello storno di una transazione cespiti.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7309cb3175f65bc6b806edb875ac9406a8faaf66
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="depreciation-effects-with-reversals"></a>Effetti di ammortamento con storni

[!include[banner](../includes/banner.md)]


In questo articolo vengono illustrate le implicazioni potenziali dello storno di una transazione cespiti. 

È possibile stornare le transazioni cespiti e le transazioni associate a un cespite. Una transazione stornata può anche essere revocata. 

È possibile stornare o revocare una transazione se non è la più recente registrata nel libro per il cespite. È innanzitutto necessario determinare se sono state registrate transazioni di ammortamento dopo la transazione da stornare. Ciò è dovuto al fatto che l'ammortamento non viene ricalcolato quando si storna una transazione. Pertanto, l'ammortamento viene spesso sopravvalutato o sottovalutato dopo lo storno, come illustrato negli esempi. 

Per assicurarsi che l'ammortamento sia corretto quando si storna una transazione, sospendere l'operazione di storno se si riceve un messaggio in cui viene segnalato che l'ammortamento non verrà ricalcolato. Sarà necessario prima stornare la transazione di ammortamento registrata dopo la transazione che si è tentato di stornare, quindi procedere con lo storno. Non verrà visualizzato alcun avviso relativo al ricalcolo dell'ammortamento e sarà possibile procedere con lo storno. 

Negli esempi riportati di seguito vengono illustrati i calcoli che verranno eseguiti se si sceglie di continuare nonostante il messaggio di avviso senza stornare prima le transazioni di ammortamento.

## <a name="example-1-depreciation-is-overstated"></a>Esempio 1: ammortamento sopravvalutato
Un cespite viene impostato con una vita utile di 5 anni e un ammortamento a quote costanti (60 periodi di ammortamento). In questo esempio l'ammortamento è sopravvalutato.
#### <a name="asset-transaction-history"></a>Storico transazioni cespiti

| Data       | Tipo di transazione                                                          | Importo                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| 1 gennaio  | Acquisizione                                                               | 59.000,00                                 |
| 1 gennaio  | Rettifica acquisizione                                                    | 1.000,00                                  |
| 31 gennaio | Ammortamento (creato mediante una proposta per un periodo di ammortamento) | 1.000,00Calcolo: Valore contabile (59.000 + 1.000) / Numero di periodi di ammortamento rimanenti (60) |

#### <a name="reversal-action"></a>Azione di storno

| Data      | Tipo di transazione                | Importo    |
|-----------|---------------------------------|-----------|
| 1 gennaio | Storno rettifica acquisizione | –1.000,00 |

#### <a name="depreciation-effect"></a>Effetto dell'ammortamento

| Data        | Tipo di transazione        | Importo                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| 28 febbraio | Ammortamento (proposta) | 983,05Calcolo: Valore contabile (59.000 - 1.000 ammortamento) / Numero di periodi di ammortamento rimanenti (59) |

L'ammortamento è sopravvalutato di 16,95 (1000 - 983,05).

## <a name="example-2-depreciation-is-understated"></a>Esempio 2: ammortamento sottovalutato
Un cespite viene impostato con una vita utile di 5 anni e un ammortamento a quote costanti (60 periodi di ammortamento). In questo esempio l'ammortamento è sottovalutato.
#### <a name="asset-transaction-history"></a>Storico transazioni cespiti

| Data       | Tipo di transazione                                                          | Importo                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| 1 gennaio  | Acquisizione                                                               | 59.000,00                                   |
| 1 gennaio  | Rettifica di svalutazione                                                     | 1.000,00                                    |
| 31 gennaio | Ammortamento (creato mediante una proposta per un periodo di ammortamento) | 966,67Calcolo: Valore contabile (59.000 - 1.000) / Numero di periodi di ammortamento rimanenti (60) |

#### <a name="reversal-action"></a>Azione di storno

| Data      | Tipo di transazione               | Importo    |
|-----------|--------------------------------|-----------|
| 1 gennaio | Storno rettifica di svalutazione | –1.000,00 |

#### <a name="depreciation-effect"></a>Effetto dell'ammortamento

| Data        | Tipo di transazione        | Importo                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| 28 febbraio | Ammortamento (proposta) | 983,62Calcolo: Valore contabile (59.000 - 966,67 ammortamento) / Numero di periodi di ammortamento rimanenti (59) |

L'ammortamento è sottovalutato di 16,95 (983,62 - 966,67).



<a name="see-also"></a>Vedere anche
--------

[Ammortamento cespiti](fixed-asset-depreciation.md)




