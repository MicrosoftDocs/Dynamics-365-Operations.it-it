---
title: Regole di arrotondamento per il calcolo delle tasse
description: Questo articolo fornisce informazioni sulle regole di arrotondamento nei parametri di calcolo delle tasse del servizio di calcolo delle tasse.
author: kailiang
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 0f6182ab18a5a408a6e526feec7014ccdfce8af0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858303"
---
# <a name="tax-calculation-rounding-rules"></a>Regole di arrotondamento per il calcolo delle tasse

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni su come funzionano le regole di arrotondamento nei parametri di calcolo delle tasse del servizio di calcolo delle tasse.

> [!NOTE] 
> Quando il servizio di calcolo dell'imposta è abilitato, le regole di arrotondamento nelle pagine **Codice dell'imposta sulle vendite** e **Gruppo dell'imposta sulle vendite** non sono efficaci.

Puoi visualizzare la configurazione delle regole di arrotondamento per il servizio di calcolo delle imposte nella sezione **Regola di arrotondamento dell'imposta sulle vendite** nella FastTab di **Calcolo** nella scheda **Generale** della pagina dei **parametri di calcolo delle imposte** **(Imposta** \> **Impostazione** \> **Configurazione delle imposte** \> **Parametri di calcolo delle imposte**).

[![Configurazione della regola di arrotondamento nella pagina dei parametri di calcolo delle tasse](./media/tax-calculation-parameters-calculation-1.png)](./media/tax-calculation-parameters-calculation-1.png)

I campi **Precisione arrotondamento** e **Metodo arrotondamento** determinano come gli importi calcolati nel payload dal servizio di calcolo delle tasse sono arrotondati.

## <a name="rounding-precision"></a>Precisione di arrotondamento

I campi di **precisione di arrotondamento** supportano un valore che ha fino a sei cifre decimali. Per esempio, se si imposta il campo **Precisione di arrotondamento** a **0.000000**, gli importi calcolati sono arrotondati a sei cifre decimali e poi inviati a Microsoft Dynamics 365 Finance. Per esempio, se viene usato il metodo di arrotondamento **Normale** , l'importo **987.1234567** viene arrotondato a **987.123457**.

> [!NOTE]
> Finance arrotonda gli importi secondo le regole di arrotondamento della valuta. Pertanto, gli importi delle tasse che sono mostrati e registrati nelle transazioni sono influenzati sia dalle regole di arrotondamento del calcolo delle tasse che dalle regole di arrotondamento della valuta.

## <a name="rounding-method"></a>Metodo di arrotondamento

Il metodo di arrotondamento per il calcolo delle tasse può essere configurato per ogni entità giuridica. Nel campo **Metodo di arrotondamento** si può scegliere tra tre opzioni: **Normale**, **in discesa** e in **arrotondamento**.

### <a name="rounding-example"></a>Esempio di arrotondamento

La seguente tabella fornisce un esempio che mostra come l'importo **987,345** viene arrotondato per diverse combinazioni di precisioni di arrotondamento e metodi di arrotondamento.

<table>
<thead>
<tr>
<th rowspan="2">Metodo di arrotondamento</th>
<th colspan="8">Precisione di arrotondamento</th>
</tr>
<tr>
<th>0,00</th>
<th>0.01</th>
<th>0.10</th>
<th>1.00</th>
<th>10.00</th>
<th>0.02</th>
<th>0.05</th>
<th>0.25</th>
</tr>
</thead>
<tbody>
<tr>
<td>Normale</td>
<td>987.35</td>
<td>987.35</td>
<td>987.30</td>
<td>987.00</td>
<td>990.00</td>
<td>987.34</td>
<td>987.35</td>
<td>987.25</td>
</tr>
<tr>
<td>Arrotondamento per difetto</td>
<td>987.00</td>
<td>987.34</td>
<td>987.30</td>
<td>987.00</td>
<td>980.00</td>
<td>987.34</td>
<td>987.30</td>
<td>987.25</td>
</tr>
<tr>
<td>Arrotondamento per eccesso</td>
<td>988.00</td>
<td>987.35</td>
<td>987.40</td>
<td>988.00</td>
<td>990.00</td>
<td>987.36</td>
<td>987.35</td>
<td>987.50</td>
</tr>
</tbody>
</table>

La logica di calcolo e di arrotondamento degli importi fiscali può essere configurata secondo le regole di tassazione.

## <a name="rounding-by"></a>Arrotondamento per 

Nel campo **Arrotondamento per** , seleziona il principio di arrotondamento che si applica alle tasse. Di seguito vengono illustrate le opzioni disponibili.

- **Codici fiscali** - Arrotonda l'importo dell'imposta all'interno di ogni codice fiscale.
- **Combinazioni di codici** fiscali - Arrotonda l'importo dell'imposta all'interno della combinazione di codici fiscali sulla linea.

## <a name="calculation-method"></a>Metodo di calcolo

Nel campo **Metodo di calcolo** , seleziona se le tasse sulle fatture sono calcolate per ogni riga o per tutte le righe. Di seguito vengono illustrate le opzioni disponibili.

- **Linea** - Calcola l'importo dell'imposta linea per linea. L'importo dell'imposta su ogni riga non è influenzato dall'importo dell'imposta su altre righe.
- **Totale** - Calcola l'importo dell'imposta su tutte le righe di un documento.

### <a name="rounding-calculation-example"></a>Esempio di calcolo dell'arrotondamento

Questo esempio mostra i diversi calcoli che possono essere fatti per una fattura, per diverse combinazioni di valori di **Arrotondamento per** e **Metodo di calcolo** . Per questo esempio, c'è la seguente configurazione:

- La fattura ha quattro righe.
- Ci sono due codici fiscali: **IVA1** (10%) e **IVA2** (10%).
- La precisione di arrotondamento è impostata su **0,01**.
- Il metodo di arrotondamento è impostato su **Arrotondamento**.

#### <a name="rounding-by--tax-codes-and-calculation-method--line"></a>Arrotondamento per = Codici fiscali e Metodo di calcolo = Linea

| Numero riga | Importo netto riga | Codici fiscali determinati | Importo dell'imposta prima dell'arrotondamento | Importo arrotondato dell'imposta |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | IVA1                 | 1.111                      | 1.12               |
| 2           | 22.22           | IVA1; IVA2           | 2.222; 2.222               | 2.23; 2.23         |
| 3           | 33.33           | IVA1                 | 3.333                      | 3.34               |
| 4           | 44.44           | IVA1; IVA2           | 4.444; 4;444               | 4.45; 4.45         |

#### <a name="rounding-by--tax-code-combinations-and-calculation-method--line"></a>Arrotondamento per = combinazioni di codici fiscali e Metodo di calcolo = Linea

| Numero riga | Importo netto riga | Codici fiscali determinati | Importo dell'imposta prima dell'arrotondamento | Importo arrotondato dell'imposta |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | IVA1                 | 1.111                      | 1.12               |
| 2\*         | 22.22           | IVA1; IVA2           | 2.222; 2.222               | 2.23; 2.22         |
| 3           | 33.33           | IVA1                 | 3.333                      | 3.34               |
| 4\*\*       | 44.44           | IVA1; IVA2           | 4.444; 4;444               | 4.45; 4.44         |

\* Linea 2 = Rotonda\[22,22 × (10 per cento + 10 per cento)\] = 2,23 + 2,22

\*\* Linea 4 = Rotonda\[44.44 × (10% + 10%)\] = 4.45 + 4.44

#### <a name="rounding-by--tax-codes-and-calculation-method--total"></a>Arrotondamento per = Codici fiscali e Metodo di calcolo = Totale

| Numero riga | Importo netto riga | Codici fiscali determinati | Importo dell'imposta prima dell'arrotondamento | Importo arrotondato dell'imposta |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | IVA1\*               | 1.111                      | 1.12               |
| 2           | 22.22           | IVA1\*; IVA2\*\*     | 2.222; 2.222               | 2.22; 2.23         |
| 3           | 33.33           | IVA1\*               | 3.333                      | 3.33               |
| 4           | 44.44           | IVA1\*; IVA2\*\*     | 4.444; 4;444               | 4.44; 4.44         |

\* IVA1(Linea 1, Linea 2, Linea 3, Linea 4) = Round\[(11,11 + 22,22 + 33,33 + 44,44) × 10 per cento\] = 1,12 + 2,22 + 3,33 + 4,44

\*\* IVA2(Linea 2, Linea 4) = Round\[(22,22 + 44,44) × 10 per cento\] = 2,23 + 4,44

#### <a name="rounding-by--tax-code-combinations-and-calculation-method--total"></a>Arrotondamento per = combinazioni di codici fiscali e Metodo di calcolo = Totale

| Numero riga | Importo netto riga | Codici fiscali determinati | Importo dell'imposta prima dell'arrotondamento | Importo arrotondato dell'imposta |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1\*         | 11.11           | IVA1                 | 1.111                      | 1.12               |
| 2\*\*       | 22.22           | IVA1; IVA2           | 2.222; 2.222               | 2.23; 2.22         |
| 3\*         | 33.33           | IVA1                 | 3.333                      | 3.33               |
| 4\*\*       | 44.44           | IVA1; IVA2           | 4.444; 4;444               | 4.44; 4.45         |

\* Linea 1, Linea 3 = Round\[(11,11 + 33,33) × 10 per cento\] = 1,12 + 3,33

\*\* Linea 2, Linea 4 = Round\[(22,22 + 44,44) × (10 per cento + 10 per cento)\] = 2,23 + 2,22 + 4,44 + 4,45

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
