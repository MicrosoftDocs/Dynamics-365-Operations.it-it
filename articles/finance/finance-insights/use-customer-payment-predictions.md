---
title: Utilizzare previsioni di pagamento del cliente (anteprima)
description: In questo argomento vengono illustrati i prerequisiti e i passaggi generali necessari per utilizzare una versione di valutazione di Informazioni dettagliate finanziarie.
author: ShivamPandey-msft
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-11-16
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 51cd69563a7a5b30e932f1aad828d095cc55b075
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827220"
---
# <a name="use-customer-payment-predictions-preview"></a>Utilizzare previsioni di pagamento del cliente (anteprima)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento spiega come utilizzare le previsioni di pagamento del cliente. Prima di utilizzare questa funzionalità, assicurati di aver completato la procedura di configurazione. Per ulteriori informazioni, vedi [Abilitare le previsioni di pagamento cliente](enable-cust-paymnt-prediction.md).

Puoi visualizzare le previsioni di pagamento del cliente nell'area di lavoro **Gestisci crediti e riscossioni cliente** e su due nuove pagine elenco, **Previsione pagamento per transazione** e **Previsione pagamento per cliente**.

### <a name="manage-customer-credit-and-collections-workspace"></a>Area di lavoro Gestisci crediti e riscossioni cliente

L'area di lavoro **Gestisci crediti e riscossioni cliente** include due nuovi riquadri, **Previsione pagamento per transazione** e **Clienti con saldi in ritardo elevati previsti**.

- Il riquadro **Previsione pagamento per transazione** mostra il numero di transazioni del cliente aperte con una probabilità di pagamento inferiore al 50% nel bucket **Puntuale**. Puoi selezionare questo riquadro per aprire la pagina elenco **Previsione pagamento per transazione**.
- Il riquadro **Clienti con saldi in ritardo elevati previsti** mostra il numero di clienti per i quali si prevede che più della metà (50 percento) del saldo totale verrà pagato in ritardo e/o molto in ritardo. Puoi selezionare questo riquadro per aprire la pagina elenco **Previsione pagamento per cliente**.

[![Area di lavoro Gestisci crediti e riscossioni cliente](./media/manage-customer-credit-collections.png)](./media/manage-customer-credit-collections.png)

### <a name="payment-predictions-per-transaction-list-page"></a>Pagina elenco Previsioni pagamento per transazione

Nella pagina elenco **Previsioni pagamento per transazione** puoi visualizzare la probabilità di pagamento per le transazioni aperte nei bucket **Puntuale**, **In ritardo** e **Molto in ritardo**. Per ogni transazione nella griglia, la colonna **Probabilità puntuale** mostra la probabilità che la fattura venga pagata entro la data di scadenza. Se la probabilità di un pagamento puntuale è inferiore al 50%, viene visualizzato un cerchio rosso accanto alla percentuale nella colonna **Probabilità puntuale** per indicare il rischio di pagamento in ritardo.

[![Pagina Previsione pagamento per transazione](./media/payment-predictions-per-transaction.png)](./media/payment-predictions-per-transaction.png)

Il riquadro **Informazioni correlate** sul lato destro della pagina mostra altri dettagli sulle previsioni:

- Per la transazione selezionata nella griglia, la Scheda dettaglio **Previsione pagamento** mostra i dettagli delle previsioni di pagamento nei bucket **Puntuale**, **In ritardo** e **Molto in ritardo**. La sezione **Fattori principali** mostra i principali fattori che hanno influenzato le previsioni. I fattori principali sono gli attributi della transazione selezionata e/o del cliente per quella transazione.
- La Scheda dettaglio **Informazioni dettagliate sul cliente** mostra le statistiche correnti di fatture, pagamenti e incassi per il cliente per la transazione selezionata.
- La Scheda dettaglio **Storico cliente** mostra la cronologia dei pagamenti del cliente nei bucket **Puntuale**, **In ritardo** e **Molto in ritardo**.

I dati nella sezione **Fattori principali** e nelle Schede dettaglio **Informazioni dettagliate sul cliente** e **Storico cliente** aiutano a spiegare le previsioni di pagamento. Posso contribuire ad aumentare la tua fiducia nell'efficacia delle previsioni.

[![Indicatori grafici per le previsioni di pagamento nel riquadro Informazioni correlate](./media/payment-prediction-gauges.png)](./media/payment-prediction-gauges.png)

### <a name="payment-prediction-per-customer-list-page"></a>Pagina elenco Previsione pagamento per cliente

La pagina elenco **Previsione pagamento per cliente** mostra il saldo totale aperto e l'importo che si prevede verrà pagato nei bucket **Puntuale**, **In ritardo** e **Molto in ritardo**.

[![Pagina Previsioni pagamento per cliente](./media/payment-predictions-per-transaction-02.png)](./media/payment-predictions-per-transaction-02.png)

L'importo del pagamento in ciascun bucket viene calcolato come la somma della media ponderata del saldo della transazione. Questo importo viene calcolato in base alle probabilità di pagamento in ciascun bucket.

Ad esempio, un cliente ha tre transazioni aperte che hanno le seguenti probabilità di pagamento in ogni bucket.

| Transazione | Periodo | Probabilità di pagamento puntuale | Probabilità di pagamento in ritardo | Probabilità di pagamento molto in ritardo |
|-------------|--------|-----------------------------|--------------------------|-------------------------------|
| T1          | 100    | 10 per cento                  | 50 per cento               | 40 per cento                    |
| T2          | 1.000  | 50 per cento                  | 30 per cento               | 20 per cento                    |
| T3          | 10,000 | 1 per cento                   | 4 per cento                | 95 per cento                    |

In questo caso, viene effettuata la proiezione dei pagamenti per ciascun bucket nel modo seguente.

| Bucket   | Transazione T1      | Transazione T2         | Transazione T3            | Totale |
|-----------|---------------------|------------------------|---------------------------|-------|
| Puntuale   | 100 × 10 ÷ 100 = 10 | 1.000 × 50 ÷ 100 = 500 | 10.000 × 1 ÷ 100 = 100    | 610   |
| In ritardo      | 100 × 50 ÷ 100 = 50 | 1.000 × 30 ÷ 100 = 300 | 10.000 × 4 ÷ 100 = 400    | 750   |
| Molto in ritardo | 100 × 40 ÷ 100 = 40 | 1.000 × 20 ÷ 100 = 200 | 10.000 × 95 ÷ 100 = 9.500 | 9,740 |

La sezione **Informazioni correlate** sul lato destro della pagina mostra altri dettagli sulle previsioni:

- Per la transazione selezionata nella griglia, la Scheda dettaglio **Previsioni pagamento** mostra i dettagli delle previsioni di pagamento nei bucket **Puntuale**, **In ritardo** e **Molto in ritardo**. La sezione **Fattori principali** mostra i principali fattori che hanno influenzato i pagamenti. I fattori principali sono gli attributi della transazione selezionata e/o del cliente per quella transazione.
- La Scheda dettaglio **Informazioni dettagliate sul cliente** mostra le statistiche correnti di fatture, pagamenti e incassi per il cliente per la transazione selezionata.
- La Scheda dettaglio **Storico cliente** mostra la cronologia dei pagamenti del cliente nei bucket **Puntuale**, **In ritardo** e **Molto in ritardo**.

I dati nella sezione **Fattori principali** e nelle Schede dettaglio **Informazioni dettagliate sul cliente** e **Storico cliente** aiutano a spiegare le previsioni di pagamento. Posso contribuire ad aumentare la tua fiducia nell'efficacia delle previsioni.

## <a name="improving-the-accuracy-of-payment-predictions"></a>Miglioramento dell'accuratezza delle previsioni di pagamento

Puoi visualizzare l'accuratezza delle previsioni di pagamento accedendo a **Credito e riscossion \> Imposta\> Informazioni dettagliate finanziarie \> Parametri di Informazioni dettagliate finanziarie**. Nella scheda **Informazioni dettagliate sui pagamenti dei clienti**, la sezione **Modello di previsione** mostra l'accuratezza del modello di previsione come percentuale.

[![Accuratezza delle previsioni di pagamento](./media/finance-insights-parameters-accuracy-2nd.png)](./media/finance-insights-parameters-accuracy-2nd.png)

Se non sei soddisfatto dell'accuratezza, seleziona il collegamento **Migliora la precisione del modello** per aprire l'esperienza dell'estensione AI Builder. Nell'esperienza dell'estensione AI Builder, puoi selezionare o annullare la selezione dei campi finché non hai selezionato i campi che ritieni più importanti per prevedere con precisione le probabilità di pagamento. Al termine, puoi facilmente eseguire nuovamente il training del modello di previsione e pubblicare le modifiche. Il modello di previsione il cui training è stato appena completato verrà automaticamente selezionato per le previsioni in Dynamics 365 Finance.

[![Esperienza di estensione di AI Builder](./media/ai-builder.png)](./media/ai-builder.png)

## <a name="release-details"></a>Dettagli del rilascio

È disponibile un'anteprima pubblica di Informazioni dettagliate finanziarie da provare per le distribuzioni negli Stati Uniti, in Europa e nel Regno Unito. Microsoft sta aggiungendo in modo incrementale il supporto per più aree geografiche.

Le funzionalità di anteprima pubblica possono e devono essere attivate solo negli ambienti sandbox di livello 2. I modelli di configurazione e intelligenza artificiale creati in un ambiente sandbox non possono essere migrati in un ambiente di produzione. Per ulteriori informazioni, vedi [Condizioni integrative per le versioni di anteprima di Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).

## <a name="privacy-notice"></a>Informativa sulla privacy

Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]