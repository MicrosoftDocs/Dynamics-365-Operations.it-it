---
title: Dismettere un cespito come scarto
description: Questo argomento descrive il processo di eliminazione delle transazioni per un cespite dismesso come scarto.
author: moaamer
ms.date: 08/14/2019
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
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 413847d350ca6b2bdd6153a598ea5b3f34a33818
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826277"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a>Dismettere un cespito come scarto

[!include [banner](../includes/banner.md)]

Questo argomento descrive il processo di eliminazione delle transazioni per un cespite dismesso come scarto. I tipi di transazioni che possono essere eliminati includono le transazioni di acquisizione e di ammortamento accumulato di un cespite e altre transazioni relativi ai cespiti. L'eliminazione di queste transazioni altera i conti dello stato patrimoniale, ad esempio conti di rettifica acquisizione, rettifica ammortamento, rivalutazione e svalutazione.

| Transazione                                         | Dare (dr.) | Avere (cr.) |
|-----------------------------------------------------|-------------|--------------|
| Ammortamento accumulato dr.                        | X           |              |
| Profitti/perdite cespiti cr.                          |             | X            |
| Profitti/perdite cespiti dr.                          | X           |              |
| Conti di acquisizione cespiti cr.                 |             | X            |
| Profitti/perdite cespiti dr. (valore contabile \[netto\]) | X           |              |
| Profitti/perdite cespiti cr. (valore contabile netto)                    |             | X            |

> [!NOTE]
> Si consiglia di cooperare strettamente con il responsabile o il supervisore finanziario della società per identificare i conti corretti da utilizzare per ogni tipo di transazione nonché verificare che il processo di dismissione e le transazioni che genera aggiornino correttamente quei conti.

Prima di dismettere un cespite come scarto, è necessario creare conti CoGe associati a valore di acquisizione, ammortamento per l'anno corrente, ammortamento per gli anni precedenti e valore contabile netto del cespite. I tipi di transazione cespiti sono elencati nella pagina **Profili di registrazione cespiti**. Selezionare **Cespiti \> Impostazione \> Profili registrazione cespiti**, quindi nella Scheda dettaglio **Dismissione**, selezionare **Scarto** nel campo sopra la griglia. Nell'illustrazione seguente viene visualizzato l'elenco dei tipi di transazione cespiti nella pagina **Profili registrazione cespiti**.


[![Dismissione di un cespite come scarto, Fig. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)

Per l'esempio seguente, un cespite è stato acquisito il 1° gennaio 2018 e verrà scartato il 31 marzo 2019.

- **Prezzo di acquisizione:** 24.000 dollari USA (USD)
- **Vita utile:** due anni
- **Metodo di ammortamento:** Vita utile a quote costanti
- **Importo di ammortamento:** 1.000 USD per mese

Il valore contabile netto di un cespite viene calcolato utilizzando la seguente formula:

Valore contabile netto = Prezzo di acquisizione - Ammortamento

In questo esempio, il cespite è stato acquisito e ammortizzato per 15 mesi, dal gennaio 2018 al marzo 2019. Di conseguenza, il valore contabile netto del cespite è 9.000 USD (24.000 USD - 15.000 USD).

[![Esempio di ammortamento dei cespiti](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)


Per creare un giornale di registrazione di dismissioni, passare a **Cespiti \> Scritture contabili \> Giornale di registrazione cespiti** e selezionare **Righe** nel riquadro azioni. Selezionare **Dismissione - scarto** e selezionare un ID cespite. Per dismettere completamente il cespite, non immettere un valore nel campo **Dare** o nel campo **Avere**.

[![Giornale di registrazione cespiti](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)

La transazione di tipo Dismissione - scarto modifica i valori per il libro cespiti nei seguenti modi:

- Nella sezione **Saldo**, il campo **Stato** diventa **Scartato**.
- Nella sezione **Uscita**, il campo **Data di dismissione** è impostato sulla data in cui il cespite è stato scartato.

[![Dettaglio del giornale di registrazione cespiti](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)

L'illustrazione seguente mostra il saldo cespiti.

[![Saldo cespiti](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)

L'illustrazione seguente mostra il giustificativo registrato.

[![Valore contabile netto](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]