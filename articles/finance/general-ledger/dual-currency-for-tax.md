---
title: Supporto a doppia valuta per le imposte
description: Questo argomento spiega come estendere la funzionalità di contabilità a doppia valuta nel dominio fiscale e l'impatto sul calcolo e sulla registrazione delle imposte
author: EricWang
ms.date: 12/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 449ebe55b8be7ee7ea22b4be7c44162d83fc3c2affbd4d20f4cad235ddb0f772
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742206"
---
# <a name="dual-currency-support-for-sales-tax"></a>Supporto a doppia valuta per l'IVA
[!include [banner](../includes/banner.md)]

Questo argomento spiega come estendere la contabilità a doppia valuta per l'IVA e l'impatto sul calcolo, sulla registrazione e sulla liquidazione dell'IVA.

La funzione di doppia valuta per Dynamics 365 Finance è stata introdotta nella versione 8.1 (ottobre 2018). Cambia il modo in cui vengono calcolate le voci contabili nella valuta di dichiarazione.

Nelle versioni precedenti, le transazioni venivano convertite nella valuta di dichiarazione nella seguente sequenza: 

- Il totale della transazione è stato calcolato nella valuta della transazione > L'importo della transazione è stato convertito nella valuta contabile > L'importo della valuta contabile è stato convertito nella valuta di dichiarazione

Dopo aver abilitato la funzione di doppia valuta, le transazioni sono state convertite nella valuta di dichiarazione nella seguente sequenza:

- Importo valuta transazione > Importo valuta dichiarazione

Per ulteriori informazioni sulla doppia valuta, fare riferimento a [Doppia valuta](dual-currency.md).

Come conseguenza del supporto per la doppia valuta, sono disponibili due nuove funzionalità nella gestione delle funzionalità: 

- Conversione IVA (novità nella versione 10.0.13)
- Immettere le dimensioni finanziarie nei conti profitti/perdite della rettifica valutaria realizzati per la liquidazione dell'imposta sulle vendite (nuovo nella versione 10.0.17)

Il supporto per doppia valuta per l'IVA garantisce che le imposte vengano calcolate accuratamente nella valuta fiscale e che il saldo della liquidazione IVA sia calcolato con precisione sia nella valuta contabile che nella valuta di dichiarazione.

## <a name="sales-tax-conversion"></a>Conversione IVA

Il parametro **Conversione IVA** fornisce due opzioni per convertire l'importo fiscale dalla valuta di transazione alla valuta imposte. 

- Valuta di contabilizzazione: il percorso sarà "Importo in valuta di transazione > Importo in valuta di contabilizzazione > Importo in valuta imposte". Per la conversione della valuta verrà utilizzato il tipo di tasso di cambio della valuta contabile (configurato in Impostazione contabilità generale).
- Valuta dichiarazione: il percorso sarà "Importo in valuta di transazione > Importo in valuta di dichiarazione > Importo in valuta imposte". Per la conversione della valuta verrà utilizzato il tipo di tasso di cambio della valuta dichiarazione (configurato in Impostazione contabilità generale).

### <a name="example"></a>Esempio

Un semplice esempio per dimostrare questa funzionalità è:

Impostazione valuta per contabilità generale e imposte

| Valuta transazione | Valuta di contabilizzazione | Valuta dichiarazione | Valuta imposte |
| -------------------- | ------------------- | ------------------ | ------------ |
| EUR                  | GBP                 | GBP                | GBP          |

Tasso di cambio

| Dalla valuta | Alla valuta | Fattore | Tasso di cambio |
| ------------- | ----------- | ------ | ------------- |
| EUR           | GBP         | 1      | 1.11          |
| EUR           | GBP         | 1      | 0.83          |
| GBP           | GBP         | 1      | 0.75          |

Calcolo dell'importo imposte in diverse opzioni di parametro

Importo imposte = 100 EUR

| Parametri di conversione IVA | Valuta transazione (EUR) | Valuta contabile (USD) | Valuta di dichiarazione (GBP) | Valuta imposte (GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| Valuta di contabilizzazione             | 100                        | 111                       | 83                       | **83.25**          |
| Valuta dichiarazione              | 100                        | 111                       | 83                       | **83**             |

Questo parametro può essere configurato in base alle esigenze di conformità dell'ufficio tributario.


### <a name="upgrade-consideration"></a>Considerazione sull'aggiornamento

Questa funzione si applica solo alle nuove transazioni. Per le transazioni imposte già salvate nella tabella TAXTRANS ma non ancora regolate, il sistema non ricalcolerà l'importo delle imposte in valuta fiscale perché il tasso di cambio al momento della registrazione delle imposte è già mancante.

Per evitare lo scenario precedente, si consiglia di modificare questo valore di parametro in un nuovo periodo di liquidazione delle imposte (pulito) che non contenga alcuna transazione fiscale non liquidata. Per modificare questo valore nel mezzo di un periodo di dichiarazione fiscale, eseguire il programma "Liquida e registra IVA" per il periodo di liquidazione imposte corrente prima di modificare questo valore di parametro.

Questa funzionalità aggiungerà voci contabili che chiariscono i guadagni e le perdite dagli scambi di valuta. Le registrazioni verranno effettuate nei conti profitti e perdite di rettifica della valuta quando la rivalutazione viene effettuata durante la liquidazione dell'imposta sulle vendite. Per ulteriori informazioni, vedi la sezione [Saldo automatico della liquidazione imposte nella valuta di dichiarazione](#tax-settlement-auto-balance-in-reporting-currency) più avanti in questo argomento.

> [!NOTE]
> Durante la liquidazione, le informazioni per le dimensioni finanziarie vengono prese dai conti IVA, che sono conti di stato patrimoniale, e inserite nei conti profitti e perdite di rettifica valutaria, che sono conti di conto profitti e perdite. Poiché le restrizioni sul valore delle dimensioni finanziarie differiscono tra i conti dello stato patrimoniale e i conti del conto profitti e perdite, può verificarsi un errore durante il processo di liquidazione e post IVA. Per evitare di dover modificare le strutture dei conti, è possibile attivare la funzione "Compila dimensioni finanziarie nei conti profitti/perdite di rettifica valutaria realizzati per la liquidazione delle imposte sulle vendite". Questa funzionalità costringerà la derivazione delle dimensioni finanziarie ai conti profitti/perdite di aggiustamento valutario. 

## <a name="track-reporting-currency-tax-amount"></a>Tracciare l'importo delle imposte in valuta di dichiarazione

Tre nuovi campi sono stati aggiunti alle tabelle relative alle imposte per tenere traccia degli importi nella valuta di dichiarazione. Questi campi si trovano nelle tabelle TAXUNCOMMITTED e TAXTRANS:

- TaxAmountRep: importo imposte in valuta di dichiarazione
- TaxBaseAmountRep: importo base in valuta di dichiarazione
- TaxInCostPriceRep: importo non deducibile in valuta di dichiarazione

Per le imposte salvate solo nella tabella TAXUNCOMMITTED ma non ancora registrate, il sistema ricalcolerà l'importo delle imposte nella valuta di dichiarazione al momento della registrazione e salverà nella tabella TAXTRANS.

Questa versione non includerà le modifiche ai report e ai moduli che mostrano l'importo delle imposte nella valuta di dichiarazione. Le modifiche a report e moduli verranno offerte nella versione futura.



## <a name="tax-settlement-auto-balance-in-reporting-currency"></a>Saldo automatico della liquidazione imposte nella valuta di dichiarazione

Se la liquidazione imposte non è inclusa nel saldo nella valuta di dichiarazione per determinati motivi, ad esempio il percorso di conversione dell'IVA è "Valuta contabile" o la variazione del tasso di cambio in un singolo periodo di liquidazione imposte, il sistema genererà automaticamente voci contabili per adeguare lo scostamento dell'importo dell'imposta e compensarlo con il conto profitti/perdite di cambio realizzato, che è impostato nella configurazione della contabilità generale.

Utilizzando l'esempio precedente per dimostrare questa funzionalità, si supponga che i dati nella tabella TAXTRANS al momento della registrazione siano i seguenti.

| Parametri di conversione IVA | Valuta transazione (EUR) | Valuta contabile (USD) | Valuta di dichiarazione (GBP) | Valuta imposte (GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| Valuta di contabilizzazione             | 100                        | 111                       | 83                       | **83.25**          |
| Valuta dichiarazione              | 100                        | 111                       | 83                       | **83**             |

Quando si esegue il programma di liquidazione dell'IVA alla fine del mese, la voce contabile sarà la seguente.
#### <a name="scenario-sales-tax-conversion--accounting-currency"></a>Scenario: conversione IVA = "valuta di contabilizzazione"

| Conto principale           | Valuta transazione (GBP) | Valuta contabile (USD) | Valuta di dichiarazione (GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| Imposta a debito/credito | -83,25                     | -111                      | -83,25                   |
| Liquidazione imposte         | 83.25                      | 111                       | 83.25                    |
| Perdita/profitto realizzato     | 0                          | 0                         | -0,25                    |
| Imposta a debito/credito | 0                          | 0                         | 0.25                     |

#### <a name="scenario-sales-tax-conversion--reporting-currency"></a>Scenario: conversione IVA = "valuta di dichiarazione"


| Conto principale           | Valuta transazione (GBP) | Valuta contabile (USD) | Valuta di dichiarazione (GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| Imposta a debito/credito | -83                        | -110,67                   | -83                      |
| Liquidazione imposte         | 83                         | 110.67                    | 83                       |
| Perdita/profitto realizzato     | 0                          | 0.33                      | 0                        |
| Imposta a debito/credito | 0                          | -0,33                     | 0                        |



Per ulteriori informazioni, vedere gli argomenti seguenti:

- [Doppia valuta](dual-currency.md)
- [Panoramica dell'IVA](indirect-taxes-overview.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
