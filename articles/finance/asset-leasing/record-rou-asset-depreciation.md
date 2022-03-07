---
title: Registrare l'ammortamento asset Right of use (anteprima)
description: In questo argomento viene illustrato come creare la scrittura contabile per l'ammortamento richiesto per i leasing rilevati nello stato patrimoniale di un'organizzazione.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: c64f19d4cf334a6cbcacaaa3753dbafe8cbf1ffe
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823073"
---
# <a name="record-right-of-use-asset-depreciation-preview"></a>Registrare l'ammortamento asset Right of use (anteprima)

[!include [banner](../includes/banner.md)]

Per i leasing rilevati nello stato patrimoniale un'organizzazione, l'Asset Right of use (ROU) viene ammortizzato mensilmente. In questo argomento viene illustrato come creare la scrittura contabile per l'ammortamento. L'ammortamento addebita il conto CoGe delle spese e accredita il conto CoGe degli ammortamenti accumulati, in base all'impostazione del profilo di registrazione e al tipo di leasing. Queste voci possono essere create per ogni leasing oppure possono essere create per più leasing utilizzando la funzionalità di giornale di registrazione batch.

## <a name="asset-depreciation-schedule"></a>Programmazione di ammortamento cespite

1. Nella pagina **Riepilogo leasing**, seleziona un leasing. Quindi seleziona **Libri \> Piano di ammortamento cespite** per aprire la pagina **Piano di ammortamento cespite**.

    La scrittura contabile delle spese di ammortamento dell'asset ROU si basa sull'importo nella colonna **Spesa di ammortamento**. Per un esempio della guida per la conformità ai principi contabili, vedi la sezione [Calcolo della spesa di ammortamento dell'asset ROU per leasing finanziari](#calculation-of-rou-asset-amortization-expense-for-finance-leases) più avanti in questo argomento.

2. Seleziona il periodo di ammortamento, quindi seleziona **Crea giornale di registrazione**. Viene visualizzato un messaggio che informa che è stato creato il giornale di registrazione che verrà utilizzato per registrare l'ammortamento.
3. Seleziona **Giornali di registrazione \> Giornali di registrazione leasing di cespiti** per aprire la pagina **Giornale di registrazione leasing cespite**, in cui è possibile visualizzare la scrittura contabile delle spese di ammortamento creata.
4. Seleziona la scrittura contabile, quindi seleziona **registra** per registrare il movimento di ammortamento nella contabilità generale.

## <a name="calculation-of-rou-asset-amortization-expense-for-operating-leases"></a>Calcolo della spesa di ammortamento dell'asset ROU per leasing operativi

La spesa dell'ammortamento di un leasing operativo viene calcolata come la differenza tra il costo del leasing a quote costanti mensile e gli interessi passivi mensili sull'obbligazione sul leasing, in conformità con Accounting Standards Codification Topic 842 (ASC 842), che è lo standard in Generally Accepted Accounting Principles negli Stati Uniti (US GAAP). Il costo del leasing a quote costanti è calcolato come la somma di tutti i canoni di leasing diviso per il termine del leasing in mesi. (La somma dei canoni di leasing include eventuali pagamenti anticipati, costi diretti iniziali, costi di smantellamento e incentivi per il leasing). La tabella seguente mostra un esempio di spesa di ammortamento per un leasing operativo.

### <a name="example-of-rou-asset-amortization-expense-for-operating-leases"></a>Esempio di spesa di ammortamento dell'asset ROU per leasing operativi

| Campo                                          | Valore       |
|------------------------------------------------|-------------|
| Importo pagamento                                 | 1.000       |
| Frequenza pagamenti                              | Ogni mese     |
| Termine del leasing (mesi)                            | 24          |
| Totale canoni di leasing                           | 24,000      |
| Tasso incrementale di prestito                     | 5%          |
| Tipo di rendita finanziaria                                   | Rendita finanziaria anticipata |
| Intervallo interessi composti                           | Ogni mese     |
| Valore attuale dei canoni di leasing minimi futuri | 22,888.87   |

Come già illustrato in precedenza, il costo del leasing a quote costanti è calcolato come la somma di tutti i pagamenti diviso per il termine del leasing. Il sistema calcola automaticamente gli interessi passivi mensili sul piano di ammortamento della passività. Gli interessi passivi sono calcolati utilizzando il metodo del tasso di interesse effettivo. Il sistema utilizzerà il costo del leasing a quote costanti per sottrarre gli interessi passivi per ogni mese. Il valore viene utilizzato per ridurre l'asset ROU.

| Mese | Costo del leasing a quote costanti | Interessi passivi                        | Calcolo della spesa di ammortamento dell'asset ROU |
|-------|--------------------------|-----------------------------------------|-----------------------------------------------|
| 1     | (24.000 ÷ 24) = 1.000,00 | (22.888,87 – 1.000) × (5% ÷ 12) = 91,20 | 1.000 – 91,20 = 908,80                        |
| 2     | (24.000 ÷ 24) = 1.000,00 | (21.980,08 – 1.000) × (5% ÷ 12) = 87,42 | 1.000 – 87,42 = 912,58                        |
| 3     | (24.000 ÷ 24) = 1.000,00 | (21.067,49 – 1.000) × (5% ÷ 12) = 83,62 | 1.000 – 83,62 = 916,39                        |

> [!NOTE]
> Secondo ASC 842, l'ammortamento dell'asset ROU per un leasing operativo è classificato come costo del leasing nel conto economico. Per maggiore visibilità, Leasing cespite descrive la voce come l'ammortamento dell'asset ROU. Tuttavia, la voce di addebito dovrebbe essere assegnata a un conto spese di leasing operativo e la voce di accredito dovrebbe essere assegnata direttamente all'asset ROU per il leasing operativo. Tuttavia, nei parametri di leasing, è possibile specificare che i movimenti di accredito devono essere effettuati in un conto di ammortamento accumulato per gli asset ROU operativi.

## <a name="calculation-of-rou-asset-amortization-expense-for-finance-leases"></a>Calcolo della spesa di ammortamento dell'asset ROU per leasing finanziari

Per i leasing che hanno una classificazione finanziaria, il sistema calcola l'ammortamento dell'asset ROU su quote costanti. Pertanto, la spesa di ammortamento sarà la stessa per ogni mese.

In conformità con l'International Financial Reporting Standard 16 (IFRS 16) e ASC 842, l'asset sarà ammortizzato sul termine del leasing o sulla vita utile dell'asset, a seconda di quale sia inferiore. Inoltre, se il parametro **Trasferimento di proprietà** è attivato per il leasing, il leasing sarà automaticamente ammortizzato lungo la vita utile del bene.

### <a name="example-of-rou-asset-amortization-expense-for-finance-leases"></a>Esempio di spesa di ammortamento dell'asset ROU per leasing finanziari

| Campo                                | Valore                                   |
|--------------------------------------|-----------------------------------------|
| Saldo dell'asset Right of use iniziale | 22,889.87                               |
| Termine del leasing (mesi)                  | 24                                      |
| Vita utile cespite (mesi)           | 36                                      |
| Mese                                | Spesa di ammortamento per asset Right of use |
| 1                                    | 22.889,87 ÷ 24 = 953,74                 |
| 2                                    | 22.889,87 ÷ 24 = 953,74                 |
| 3                                    | 22.889,87 ÷ 24 = 953,74                 |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]