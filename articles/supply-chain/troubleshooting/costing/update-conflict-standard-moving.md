---
title: Conflitto di aggiornamento quando il metodo di valutazione dell'inventario è costo standard o media mobile
description: Si verifica un conflitto di aggiornamento quando il metodo di valutazione dell'inventario è costo standard o media mobile
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 920d20d19843ce0cac678c5426c00ec99aa61c61
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476798"
---
# <a name="an-update-conflict-occurs-when-the-inventory-valuation-method-is-either-standard-cost-or-moving-average"></a>Si verifica un conflitto di aggiornamento quando il metodo di valutazione dell'inventario è costo standard o media mobile

## <a name="symptoms"></a>Sintomi

Quando si registrano documenti come giornali di registrazione magazzino, fatture di ordini fornitore o fatture di ordini cliente in parallelo per scalabilità e prestazioni, è possibile che venga visualizzato un messaggio di errore relativo a un conflitto di aggiornamento e alcuni documenti potrebbero non essere registrati. Il problema può verificarsi quando il metodo di valutazione dell'inventario è *Costo standard* o *Media mobile*. Entrambi questi metodi sono metodi di determinazione dei costi perpetui. In altre parole, il costo finale viene determinato al momento della registrazione.

Se stai usando il metodo *Media mobile*, il messaggio di errore è simile a questo esempio:

> Il valore dell'inventario xx.xx non è previsto dopo il calcolo della spesa proporzionale

Se stai usando il metodo *Costo standard*, il messaggio di errore è simile a questo esempio:

> Il costo standard non corrisponde al valore dell'inventario finanziario dopo l'aggiornamento. Valore = xx.xx, Qtà = yy.yy, Costo standard = zz.zz

## <a name="workaround"></a>Soluzione alternativa

Fino a quando Microsoft non rilascerà una soluzione per risolvere il problema, prendere in considerazione l'utilizzo delle seguenti soluzioni alternative per evitare o ridurre questi errori:

- Registrare nuovamente i documenti con errore.
- Creare documenti con meno righe.
- Evitare i valori decimali nel costo standard. Provare a definire il costo standard in modo che il campo **Quantità di prezzo** sia impostato su *1*. Se devi specificare un valore **Quantità di prezzo** maggiore di *1*, prova a ridurre al minimo il numero di cifre decimali nel costo standard unitario. (Idealmente, dovrebbero esserci meno di due cifre decimali.) Ad esempio, evitare di definire impostazioni di costo standard come **Prezzo** = *10* e **Quantità di prezzo** = *3*, perché produrranno un costo standard unitario di 3,333333 (dove si ripete il valore decimale).
- Nella maggior parte dei documenti, evitare di avere più righe che contengono la stessa combinazione di dimensioni di inventario finanziario e prodotto.
- Riduci il grado di parallelizzazione. (In questo caso, il sistema potrebbe diventare più veloce, perché si verificano meno conflitti di aggiornamento e nuovi tentativi.)
