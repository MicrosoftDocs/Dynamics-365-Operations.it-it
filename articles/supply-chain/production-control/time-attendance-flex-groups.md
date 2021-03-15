---
title: Gruppi flessibilità
description: In questo argomento viene descritto come vengono utilizzati i gruppi flessibilità in Orario e presenze.
author: johanhoffmann
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgFlexGroup, JmgFlexCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 1e12874e3395ec47a6b76809b92c26e20fb14197
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980908"
---
# <a name="flex-groups"></a>Gruppi flessibilità

[!include[banner](../includes/banner.md)]

L'orario flessibile delle società consente di ridurre al minimo la retribuzione di ore straordinarie offrendo ai lavoratori tempo libero aggiuntivo durante i periodi in cui il carico di lavoro è ridotto. Questa funzionalità è rilevante, ad esempio, nei segmenti con variazioni stagionali nel carico di lavoro.

È possibile utilizzare i gruppi flessibilità per impostare i seguenti principi e regole per le ore di flessibilità di un lavoratore:

- Regole per i regolamenti flessibili
- Principio per il calcolo del saldo flessibile del lavoratore

## <a name="set-up-flexible-working-hours-in-flex-groups"></a>Impostare orari di lavoro flessibili in gruppi flessibili

- Selezionare **Orario e presenze** \> **Impostazione** \> **Gruppi** \> **Gruppi flessibilità** per impostare i gruppi flessibilità per l'orario flessibile.

## <a name="associate-workers-with-flex-groups"></a>Associare i lavoratori ai gruppi flessibilità

- Selezionare **Orario e presenze** \> **Impostazione** \> **Lavoratori per registrazione ore**.

## <a name="rules-for-flex-regulations"></a>Regole per i regolamenti flessibili

È possibile utilizzare le regole per i regolamenti flessibili per definire i limiti di flessibilità o il numero minimo e massimo di ore consentite nell'account flessibile del lavoratore. I limiti di flessibilità vengono impostati nel gruppo flessibilità. Quando vengono superati i limiti di flessibilità, è possibile rettificare il saldo flessibile e la retribuzione di un lavoratore.

Se viene superato il limite di flessibilità consentito di un lavoratore (ovvero se il numero di ore nel conto di flessibilità è inferiore al minimo specificato), è possibile utilizzare questi metodi per rettificare il saldo flessibilità del lavoratore mediante un regolamento flessibile:

- Il conto di flessibilità del lavoratore può essere rettificato al minimo consentito specificato, ma senza dedurre la retribuzione del lavoratore per il numero di ore per cui l'account flessibile è inferiore al minimo consentito.
- La retribuzione del lavoratore può essere applicata una detrazione per il numero di ore per cui il conto di flessibilità è inferiore al minimo consentito. La detrazione viene effettuata generando elementi retributivi per un tipo di retribuzione specifico con un'unità retributiva negativa o positiva.

Se il massimo consentito flessibilità del lavoratore viene superato, è possibile utilizzare questi metodi per rettificare il saldo flessibilità del lavoratore mediante un regolamento flessibile:

- Il conto di flessibilità del lavoratore può essere rettificato di nuovo al massimo consentito specificato, ma senza compensare la retribuzione del lavoratore per il numero di ore per cui il lavoratore ha lavorato al di sopra del massimo consentito.
- Il numero di ore in cui il lavoratore ha lavorato al di sopra del massimo consentito può essere convertito in retribuzione. Questa conversione viene effettuata generando elementi retributivi per un tipo di retribuzione specifico.

È possibile rettificare un saldo di flessibilità nei seguenti momenti:

- Quando un file di pagamento basato sui dati retributivi viene esportato utilizzando il processo **Trasferisci retribuzione**. I dati di retribuzione vengono generati quando si trasferiscono la registrazione del lavoratore dalla pagina **Approva**.
- Quando il processo **Rettifica saldo flessibilità** viene elaborato.

> [!NOTE]
> I regolamenti flessibili non si verificano durante l'approvazione giornaliera e il trasferimento delle registrazioni dei lavoratori nella pagina **Approva**.

## <a name="principle-for-calculating-a-workers-flex-balance"></a>Principio per il calcolo di un saldo flessibile del lavoratore

Il principio per calcolare le ore per cui il saldo flessibile del lavoratore viene rettificato è impostato nel gruppo flessibile Selezionare **Orario e presenze** \> **Impostazione** \> **Gruppi** \> **Gruppi flessibilità**. 

È possibile utilizzare i seguenti due principi:

- **Orario**: le ore flessibili del lavoratore vengono calcolate solo dall'orario registrato dal lavoratore per quel giorno. Quando vengono calcolate le registrazioni giornaliere del lavoratore, il numero di ore di flessibilità in eccesso e in difetto per il giorno vengono calcolate dalle zone Flessibilità in eccesso e Flessibilità in difetto definite nel profilo orario del lavoratore.
- **Tipi di retribuzione**: le ore flessibili del lavoratore vengono calcolate in base ai redditi dei tipi di retribuzione per Flessibilità in eccesso e Flessibilità in difetto definiti nel contratto di retribuzione del lavoratore. L'accordo salariale è associato al lavoratore per registrazione ore. È possibile utilizzare i tipi di retribuzione per gestire i conti di flessibilità se, ad esempio, si desidera aumentare il conto di flessibilità di un lavoratore in base a un fattore specifico in una o più zone flessibili.

### <a name="scenario-1-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-minimum-is-exceeded"></a>Scenario 1: rettifica della retribuzione e del conto di flessibilità di un lavoratore in quanto viene superato il limite minimo consentito

Un lavoratore che può lavorare con orari flessibili ha un conto di flessibilità negativo.

- **Conto di flessibilità:** -4

Il lavoratore è associato a un gruppo flessibilità con la seguente configurazione:

- **Flessibilità minima:** -0,5
- **Tipo di retribuzione minima:** 1302
- **Fattore tipo di retribuzione:** -1,00

Come indica la differenza tra il conto di flessibilità del lavoratore e il minimo flessibile, il lavoratore ha superato il limite minimo consentito di 3,5 ore.

Quando l'amministratore retribuzioni trasferisce i dati retributivi del lavoratore eseguendo il processo **Trasferisci al sistema di retribuzione** o **Rettifica flessibilità**, vengono apportate le seguenti rettifiche:

- Il conto di flessibilità del lavoratore viene rettificato di 3,5 ore. Pertanto, il saldo flessibile di -4,0 ore viene rettificato al minimo consentito del lavoratore di -0,5 ore.
- Viene creato un elemento retributivo per il tipo di retribuzione 1302. Questo elemento è associato a una retribuzione di -3,5 ore che verrà detratta dalla retribuzione del lavoratore. In questo caso, l'unità retributiva è un numero negativo, poiché la rettifica positiva di 3,5 ore viene moltiplicata per il fattore di tipo di retribuzione negativa di -1,0 definito nel gruppo flessibile. Questo elemento retributivo farà parte del file di pagamento generato dal processo **Trasferisci al sistema di retribuzione**.

### <a name="scenario-2-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-maximum-is-exceeded"></a>Scenario 2: rettifica della retribuzione e del conto di flessibilità di un lavoratore in quanto viene superato il limite massimo consentito

Un lavoratore che può lavorare con orari flessibili ha un conto di flessibilità positivo.

- **Conto di flessibilità:** 6

Il lavoratore è associato a un gruppo flessibilità con la seguente configurazione:

- **Flessibilità massima:** 2,0
- **Tipo di retribuzione minima:** 1302
- **Fattore tipo di retribuzione:** -1,0

Come indica la differenza tra il conto di flessibilità del lavoratore e il massimo flessibili, il lavoratore ha superato il limite massimo consentito di 4,0 ore.

Quando l'amministratore retribuzioni trasferisce i dati retributivi del lavoratore eseguendo il processo **Trasferisci al sistema di retribuzione** o **Rettifica flessibilità**, vengono apportate le seguenti rettifiche:

- Il conto di flessibilità del lavoratore viene rettificato di -4,0 ore. Pertanto, il saldo flessibile di 6,0 ore viene rettificato al massimo consentito del lavoratore di 2,0 ore.
- Viene creato un elemento retributivo per il tipo di retribuzione 1302. Questo elemento è associato a una retribuzione di 4,0 ore che verrà aggiunta dalla retribuzione del lavoratore. In questo caso, l'unità retributiva è un numero positivo, poiché la rettifica negativa di 4,0 ore viene moltiplicata per il fattore di tipo di retribuzione negativa di -1,0 definito nel gruppo flessibile. Questo elemento retributivo farà parte del file di pagamento generato dal processo **Trasferisci al sistema di retribuzione**.

### <a name="scenario-3-managing-a-workers-flex-balance-based-on-pay-types"></a>Scenario 3: gestione del saldo flessibilità di un lavoratore in base ai tipi di retribuzione

Come descritto in precedenza, i conti di flessibilità possono essere gestiti in base alle ore registrate nelle zone Flessibilità in difetto e Flessibilità in eccesso definite nel profilo orario del lavoratore o nei tipi di retribuzione definiti negli accordi salariali del lavoratore. Se vengono utilizzati tipi di retribuzione, il conto di flessibilità di un lavoratore viene rettificato dagli elementi retributivi generati quando si trasferisce la registrazione del lavoratore dalla pagina **Approva**. È possibile utilizzare i tipi di retribuzione per gestire i conti di flessibilità se, ad esempio, si desidera aumentare il conto di flessibilità di un lavoratore in base a un fattore specifico in una o più zone flessibili.

Questo scenario utilizza il seguente profilo flessibile che rappresenta un giorno lavorativo.

| Tipo profilo  | Avvio    | Fine periodo      |
|---------------|----------|----------|
| Flessibilità in eccesso         | 12:00 | 08:00 |
| Entrata      | 08:00 | 08:00 |
| Flessibilità in difetto-         | 08:00 | 09:00 |
| Orario standard | 09:00 | 11:30 |
| Pausa retribuita    | 11:30 | 12:00 |
| Flessibilità in difetto-         | 12:00 | 04:00 |
| Uscita     | 04:00 | 04:00 |
| Flessibilità in eccesso         | 04:00 | 12:00 |

In questo caso, si desidera essere in grado di gestire il saldo flessibilità del lavoratore in base ai tipi di retribuzione. Di conseguenza, è necessario impostare l'opzione **Basato sui tipi di retribuzione** su **Sì** nel gruppo flessibilità del lavoratore.

Per tenere conto delle ore di flessibilità, è necessario definire anche un nuovo tipo di retribuzione. Per questo scenario, il tipo di retribuzione viene denominato **FlexCnt**.

| Tipo di retribuzione | descrizione  |
|----------|--------------|
| FlexCnt  | Contatore flessibilità |

Quindi, seguire questi passaggi per impostare un tipo di retribuzione e aggiungere righe del nuovo tipo a un profilo di pagamento.

1. Selezionare **Orario e presenze** \> **Impostazione** \> **Gruppi** \> **Gruppi flessibilità** e quindi **Nuovo**.
2. Nel campo **Flessibilità in eccesso** e nel campo **Flessibilità in difetto** specificare il nuovo tipo di retribuzione **FlexCnt**.
3. Selezionare **Orario e presenze** \> **Impostazione** \> **Accordi salariali** e quindi **Righe contratto**.
4. Per **Lunedì**, per il tipo di profilo **Flessibilità in eccesso**, aggiungere le seguenti tre righe.

    | Tipo di retribuzione | descrizione  | Dalle ore | Alle ore  | Minimo | Massimo | Fattore |
    |----------|--------------|-----------|----------|---------|---------|--------|
    | FlexCnt  | Contatore flessibilità | 12:00  | 06:00 | 00.00   | 00.00   | 1,00   |
    | FlexCnt  | Contatore flessibilità | 06:00  | 12:00 | 00.00   | 02.00   | 1.50   |
    | FlexCnt  | Contatore flessibilità | 06:00  | 12:00 | 02.00   | 06.00   | 2.00   |

    > [!NOTE]
    > Ogni riga viene utilizzata per un intervallo di tempo diverso e ha un fattore diverso. Le ore flessibili in cui il lavoratore lavora in un intervallo di tempo vengono moltiplicate per il fattore per quella riga. Ad esempio, le ore lavorate dalle 18:00 alle 20:00 vengono moltiplicate per 1,50. Il fattore viene specificato nel campo **Fattore** della scheda **Generale** della pagina **Righe accordo salariale**.

Il lavoratore inserisce le seguenti registrazioni per il giorno:

| Tipo di registrazione giornale | Avvio    | Fine periodo      |
|---------------------------|----------|----------|
| Entrata                  | 07:00 | 07:00 |
| Processo di produzione            | 07:00 | 09:00 |
| Uscita                 | 09:00 | 09:00 |

L'importo che deve essere pagato viene calcolato nella pagina **Approva**, in base alla registrazione del lavoratore. Dopo aver calcolato la registrazione, è possibile visualizzare il risultato nella scheda **Tempi**. Per questo scenario, sono rilevanti i seguenti campi.

| Flessibilità in eccesso | Flessibilità in difetto | Tempo  | Tempo retribuito |
|--------|--------|-------|----------|
| 6,00   | 0,00   | 13.50 | 08.00    |

La quantità delle ore di flessibilità in eccesso è di sei ore e il calcolo è basato sulle aree di flessibilità nel profilo orario. Tale importo include un'ora di flessibilità in eccesso dalle 07:00 alle 08:00 e cinque ore di flessibilità in eccesso dalle 16:00 alle 21:00.

Quando si trasferiscono le registrazioni, si noterà che la quantità di ore di flessibilità in eccesso viene modificata da 6,0 a 8,0 ore.

| Flessibilità in eccesso | Flessibilità in difetto | Tempo  | Tempo retribuito |
|--------|--------|-------|----------|
| 8,00   | 0,00   | 13.50 | 08.00    |

Questo cambiamento si verifica dopo il trasferimento perché le ore flessibili sono state calcolate in base ai tipi di retribuzione anziché al tempo. La seguente tabella mostra come vengono calcolate le otto ore.

| Da     | A       | Tempo | Fattore    | Conto di flessibilità |
|----------|----------|------|-----------|--------------|
| 07:00 | 08:00 | 1    | 1         | 1            |
| 04:00 | 06:00 | 2    | 1         | 2            |
| 06:00 | 08:00 | 2    | 1.5       | 3            |
| 08:00 | 09:00 | 1    | 2         | 2            |
|          |          |      | **Totale** | **8**        |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]