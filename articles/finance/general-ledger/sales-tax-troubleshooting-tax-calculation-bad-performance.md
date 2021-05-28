---
title: Le prestazioni di calcolo delle imposte influiscono sulle transazioni
description: In questo argomento vengono fornite informazioni sulla risoluzione dei problemi relativi alle prestazioni del calcolo delle imposte e al relativo effetto sulle transazioni.
author: shtao
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 6fce4e2cb8c5507769533a875e23ccc4531abf51
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020141"
---
# <a name="tax-calculation-performance-affects-transactions"></a>Le prestazioni di calcolo delle imposte influiscono sulle transazioni

[!include [banner](../includes/banner.md)]

A volte, una transazione è influenzata da problemi di prestazioni dovuti al calcolo delle imposte. Per risolvere questo problema, seguire i passaggi nelle sezioni seguenti come richiesto.

## <a name="review-the-transaction-line-count"></a>Esaminare il numero di righe della transazione

Determina se la transazione ha un numero elevato di righe (ad esempio, più di diverse centinaia). In caso contrario, passa alla sezione successiva. Se la transazione ha diverse centinaia di righe, differire il calcolo delle imposte. Per ulteriori informazioni, vedere [Abilitare il calcolo IVA differito nei giornali di registrazione](enable-delayed-tax-calculation.md). 

Successivamente, puoi determinare se una delle seguenti condizioni è soddisfatta:

- Sono presenti transazioni di importazione da file di grandi dimensioni.
- Più sessioni elaborano lo stesso calcolo dell'imposta sulle transazioni contemporaneamente.
- La transazione ha più righe e le visualizzazioni vengono aggiornate in tempo reale. Ad esempio, il campo **Importo IVA calcolato** nella pagina **Giornale di registrazione generale** viene aggiornato in tempo reale quando vengono modificati i campi di una riga.

   [![Campo dell'importo IVA calcolato nella pagina del giustificativo giornale di registrazione](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)

Se una di queste condizioni è soddisfatta, differire il calcolo dell'imposta.

## <a name="review-the-call-stack"></a>Esaminare lo stack di chiamate

Esamina lo stack di chiamate per determinare se il calcolo delle imposte viene richiamato più volte. In caso contrario, passa alla sezione successiva. Se lo stack di chiamate viene chiamato più volte, attenersi alla seguente procedura per ridurre i tempi di calcolo delle imposte.

1. Se il giornale di registrazione ha considerato la transazione, differire il calcolo dell'imposta. Per ulteriori informazioni, vedere [Abilitare il calcolo IVA differito nei giornali di registrazione](enable-delayed-tax-calculation.md).
2. Se la transazione è un ordine fornitore e la versione dell'applicazione è successiva alla 10.0.15, è possibile differire il calcolo delle imposte fino al calcolo finale abilitando la versione di anteprima per **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.

## <a name="review-the-call-stack-timeline"></a>Esaminare la sequenza temporale dello stack di chiamate

Esaminare la sequenza temporale dello stack di chiamate per determinare se esistono i seguenti problemi. Se esistono, abilita la versione di anteprima per **TaxUncommittedDoIsolateScopeFlighting** per risolvere il problema.

- La transazione fa sì che il sistema smetta di rispondere fino al termine della sessione. Pertanto, la transazione non può calcolare il risultato fiscale. La figura seguente mostra la finestra di messaggio "Sessione terminata" ricevuta.

    [![Messaggio di sessione termimata](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)

- I metodi **TaxUncommitted** richiedono più tempo rispetto ad altri metodi. Ad esempio, nella figura seguente, il metodo **TaxUncommitted::updateTaxUncommitted()** richiede 43.347,42 secondi, ma gli altri metodi richiedono 0,09 secondi.

    [![Durata dei metodi](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)

## <a name="customizing-and-calling-tax-calculation"></a>Personalizzare e chiamare il calcolo delle imposte

Quando personalizzi, non chiamare il calcolo delle imposte nel metodo **insert()** o **update()** per ogni riga. Il calcolo delle imposte dovrebbe essere chiamato a livello di transazione.

## <a name="determine-whether-customization-exists"></a>Determinare se esiste la personalizzazione

Se hai completato i passaggi nelle sezioni precedenti ma non hai riscontrato alcun problema, determina se esiste la personalizzazione. Se non esiste alcuna personalizzazione, creare una richiesta di assistenza Microsoft per ulteriore supporto.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
