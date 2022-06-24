---
title: Arrotondamento e calcolo dell'IVA
description: Questo articolo fornisce una panoramica del calcolo e dell'arrotondamento dell'IVA e spiega i parametri del calcolo dell'IVA e dell'impostazione dell'arrotondamento.
author: wangchen
ms.date: 06/01/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom:
- "13111"
- intro-internal
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2022-05-31
ms.dyn365.ops.version: AX 10.0.28
ms.openlocfilehash: aa3564f0fcf4a958637ba4a5cdcc497bffc50000
ms.sourcegitcommit: 8b716849707ec96d1cb4cac85b9e782dc25f5a70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2022
ms.locfileid: "8939235"
---
# <a name="sales-tax-calculation-and-rounding"></a>Arrotondamento e calcolo dell'IVA

[!include [banner](../includes/banner.md)]

Questo articolo fornisce una panoramica del calcolo dell'IVA e dell'arrotondamento per eccesso in Microsoft Dynamics 365 Finance. Spiega inoltre i parametri utilizzati nell'impostazione per il calcolo e l'arrotondamento dell'IVA e il modo in cui tali parametri interagiscono.

## <a name="parameters"></a>Parametri

Diversi parametri controllano il calcolo e l'arrotondamento dell'IVA:

- **Metodo di calcolo** – Questo parametro è impostato nella pagina **Parametri di contabilità generale** e definisce se l'importo della base imponibile viene calcolato per documento o per riga. Se il parametro **Imponibile marginale** per il codice IVA è impostato su **Importo netto del saldo fattura**, l'importo della base imponibile viene sempre calcolato per documento, indipendentemente dall'impostazione di questo parametro.
- **Arrotondamento per** – Questo parametro è impostato per la fascia IVA e definisce se l'importo dell'IVA viene arrotondato per codice IVA o per combinazione di codici IVA.
- **Origine** – Questo parametro è impostato per il codice IVA e definisce come viene calcolato l'importo dell'imposta. Per ulteriori informazioni, vedi [Metodi di calcolo IVA nel campo Origine](sales-tax-calculation-methods-origin-field.md).
- **Imponibile marginale** – Questo parametro è impostato per il codice IVA e determina quale importo viene utilizzato per selezionare le aliquote fiscali appropriate sulla pagina **Valori del codice IVA**. Per ulteriori informazioni, vedere [Aliquote IVA basate su Imponibile marginale e Metodo di calcolo](marginal-base-field.md).
- **Regola di arrotondamento dell'IVA** – Questo parametro viene impostato per il codice IVA e definisce come viene arrotondato l'importo IVA determinato, inclusa la precisione di arrotondamento e il metodo di arrotondamento.

Il resto di questo articolo presenta alcuni esempi tipici di calcolo e arrotondamento dell'IVA che utilizzano una combinazione dei parametri precedenti.

## <a name="scenario-for-the-examples"></a>Scenario per gli esempi

- Ci sono due righe nel documento imponibile e l'importo della base imponibile per ciascuna riga è 42,42.
- Per ogni riga sono definiti due codici IVA: codice IVA 1 e codice IVA 2.
- L'aliquota fiscale sia del codice fiscale 1 che del codice fiscale 2 è del 10%.
- Il prezzo non include le imposte.
- La precisione di arrotondamento è 0,01.
- Il metodo di arrotondamento è **Arrotondamento**.

## <a name="example-1"></a>Esempio 1

### <a name="parameter-values"></a>Valori parametro

| Metodo di calcolo | Arrotondamento per    | Origine                   | Imponibile marginale       |
| ------------------ | -------------- | ------------------------ | ------------------- |
| Riga               | Codice IVA | Percentuale dell'importo netto | Importo netto per riga |

### <a name="calculation-and-rounding-behavior"></a>Comportamento del calcolo e dell'arrotondamento

| Numero riga | Codice IVA | Origine importo | Importo IVA |
| ------------| ---------------| --------------| -----------------|
| 1           | Codice 1         | 42.42         | 4.25             |
| 1           | Codice 2         | 42.42         | 4.25             |
| 2           | Codice 1         | 42.42         | 4.25             |
| 2           | Codice 2         | 42.42         | 4.25             |

L'importo della base imponibile è calcolato per riga:

- **Riga 1:** 42,42
- **Riga 2:** 42,42

L'importo dell'imposta viene calcolato per codice IVA:

- **Riga 1:**

    - Importo dell'imposta per codice IVA 1 = 42,42 &times; 10% = 4,242
    - Importo dell'imposta per codice IVA 2 = 42,42 &times; 10% = 4,242

- **Riga 2:**

    - Importo dell'imposta per codice IVA 1 = 42,42 &times; 10% = 4,242
    - Importo dell'imposta per codice IVA 2 = 42,42 &times; 10% = 4,242

L'importo dell'imposta viene arrotondato per codice IVA:

- **Riga 1:**

    - Importo dell'imposta arrotondato per codice IVA 1 = 4,25
    - Importo dell'imposta arrotondato per codice IVA 2 = 4,25

- **Riga 2:**

    - Importo dell'imposta arrotondato per codice IVA 1 = 4,25
    - Importo dell'imposta arrotondato per codice IVA 2 = 4,25

## <a name="example-2"></a>Esempio 2

### <a name="parameter-values"></a>Valori parametro

| Metodo di calcolo | Arrotondamento per    | Origine                   | Imponibile marginale                 |
| ------------------ | -------------- | ------------------------ | ----------------------------- |
| Riga/Totale         | Codice IVA | Percentuale dell'importo netto | Importo netto del saldo fattura |

### <a name="calculation-and-rounding-behavior"></a>Comportamento del calcolo e dell'arrotondamento

| Numero riga | Codice IVA | Origine importo | Importo IVA |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Codice 1         | 42.42         | 4.25             |
| 1           | Codice 2         | 42.42         | 4.25             |
| 2           | Codice 1         | 42.42         | 4.24             |
| 2           | Codice 2         | 42.42         | 4.24             |

L'importo della base imponibile è calcolato per documento:

- Importo imponibile = 42,42 + 42,42 = 84,84

L'importo dell'imposta viene calcolato per codice IVA:

- Importo dell'imposta per codice IVA 1 = 84,84 &times; 10% = 8,484
- Importo dell'imposta per codice IVA 2 = 84,84 &times; 10% = 8,484

L'importo dell'imposta viene arrotondato per codice IVA:

- Importo dell'imposta arrotondato per codice IVA 1 = 8,49
- Importo dell'imposta arrotondato per codice IVA 2 = 8,49

L'importo arrotondato dell'imposta viene allocato a ciascuna riga per codice IVA:

- Assegna l'importo arrotondato dell'imposta per il codice IVA 1 (8,49) alla riga 1 (4,25) e alla riga 2 (4,24).
- Assegna l'importo arrotondato dell'imposta per il codice IVA 2 (8,49) alla riga 1 (4,25) e alla riga 2 (4,24).

## <a name="example-3"></a>Esempio 3

### <a name="parameter-values"></a>Valori parametro

| Metodo di calcolo | Arrotondamento per    | Origine                              | Imponibile marginale       |
| ------------------ | -------------- | ----------------------------------- | ------------------- |
| Riga               | Codice IVA | Percentuale calcolata dell'importo netto | Importo netto per riga |

### <a name="calculation-and-rounding-behavior"></a>Comportamento del calcolo e dell'arrotondamento

| Numero riga | Codice IVA | Origine importo | Importo IVA |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Codice 1         | 42.42         | 4.72             |
| 1           | Codice 2         | 42.42         | 4.72             |
| 2           | Codice 1         | 42.42         | 4.72             |
| 2           | Codice 2         | 42.42         | 4.72             |

L'importo della base imponibile è calcolato per riga:

- **Riga 1:** 42,42
- **Riga 2:** 42,42

L'importo dell'imposta viene calcolato per codice IVA:

- **Riga 1:**

    - Importo dell'imposta per codice IVA 1 = 42,42 &times; 10% &divide; (1 – 10%) = 4,7133
    - Importo dell'imposta per codice IVA 2 = 42,42 &times; 10% &divide; (1 – 10%) = 4,7133

- **Riga 2:**

    - Importo dell'imposta per codice IVA 1 = 42,42 &times; 10% &divide; (1 – 10%) = 4,7133
    - Importo dell'imposta per codice IVA 2 = 42,42 &times; 10% &divide; (1 – 10%) = 4,7133

L'importo dell'imposta viene arrotondato per codice IVA:

- **Riga 1:**

    - Importo dell'imposta arrotondato per codice IVA 1 = 4,72
    - Importo dell'imposta arrotondato per codice IVA 2 = 4,72

- **Riga 2:**

    - Importo dell'imposta arrotondato per codice IVA 1 = 4,72
    - Importo dell'imposta arrotondato per codice IVA 2 = 4,72

## <a name="example-4"></a>Esempio 4

### <a name="parameter-values"></a>Valori parametro

| Metodo di calcolo | Arrotondamento per    | Origine                              | Imponibile marginale                 |
| ------------------ | -------------- | ----------------------------------- | ----------------------------- |
| Riga/Totale         | Codice IVA | Percentuale calcolata dell'importo netto | Importo netto del saldo fattura |

### <a name="calculation-and-rounding-behavior"></a>Comportamento del calcolo e dell'arrotondamento

| Numero riga | Codice IVA | Origine importo | Importo IVA |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Codice 1         | 42.42         | 4.72             |
| 1           | Codice 2         | 42.42         | 4.72             |
| 2           | Codice 1         | 42.42         | 4.71             |
| 2           | Codice 2         | 42.42         | 4.71             |

L'importo della base imponibile è calcolato per documento:

- Importo imponibile = 42,42 + 42,42 = 84,84

L'importo dell'imposta viene calcolato per codice IVA:

- Importo dell'imposta per codice IVA 1 = 84,84 &times; 10% &divide; (1 – 10%) = 9,4267
- Importo dell'imposta per codice IVA 2 = 84,84 &times; 10% &divide; (1 – 10%) = 9,4267

L'importo dell'imposta viene arrotondato per codice IVA:

- Importo dell'imposta arrotondato per codice IVA 1 = 9,43
- Importo dell'imposta arrotondato per codice IVA 2 = 9,43

L'importo arrotondato dell'imposta viene allocato a ciascuna riga per codice IVA:

- Assegna l'importo dell'imposta per il codice IVA 1 (9,43) alla riga 1 (4,72) e alla riga 2 (4,71).
- Assegna l'importo dell'imposta per il codice IVA 2 (9,43) alla riga 1 (4,72) e alla riga 2 (4,71).

## <a name="example-5"></a>Esempio 5

### <a name="parameter-values"></a>Valori parametro

| Metodo di calcolo | Arrotondamento per                | Origine                   | Imponibile marginale       |
| ------------------ | -------------------------- | ------------------------ | ------------------- |
| Riga               | Combinazione codici IVA | Percentuale dell'importo netto | Importo netto per riga |

### <a name="calculation-and-rounding-behavior"></a>Comportamento del calcolo e dell'arrotondamento

| Numero riga | Codice IVA | Origine importo | Importo IVA |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Codice 1         | 42.42         | 4.25             |
| 1           | Codice 2         | 42.42         | 4.24             |
| 2           | Codice 1         | 42.42         | 4.24             |
| 2           | Codice 2         | 42.42         | 4.24             |

L'importo della base imponibile è calcolato per riga:

- **Riga 1:** 42,42
- **Riga 2:** 42,42

L'importo dell'imposta viene calcolato per codice IVA:

- **Riga 1:**

    - Importo dell'imposta per codice IVA 1 = 42,42 &times; 10% = 4,242
    - Importo dell'imposta per codice IVA 2 = 42,42 &times; 10% = 4,242

- **Riga 2:**

    - Importo dell'imposta per codice IVA 1 = 42,42 &times; 10% = 4,242
    - Importo dell'imposta per codice IVA 2 = 42,42 &times; 10% = 4,242

L'importo dell'imposta viene arrotondato per combinazione di codici IVA:

- Importo totale dell'IVA = 4,242 + 4,242 + 4,242 + 4,242 = 16,968, che viene arrotondato a 16,97

L'importo arrotondato dell'imposta viene allocato a ciascuna riga per codice IVA:

- Assegna l'importo dell'IVA (16,97) alla riga 1 e alla riga 2:

    - **Riga 1:**

        - Importo dell'imposta per codice IVA 1 = 4,25
        - Importo dell'imposta per codice IVA 2 = 4,24

    - **Riga 2:**

        - Importo dell'imposta per codice IVA 1 = 4,24
        - Importo dell'imposta per codice IVA 2 = 4,24

## <a name="example-6"></a>Esempio 6

### <a name="parameter-values"></a>Valori parametro

| Metodo di calcolo | Arrotondamento per                | Origine                   | Imponibile marginale                 |
| ------------------ | -------------------------- | ------------------------ | ----------------------------- |
| Riga/Totale         | Combinazione codici IVA | Percentuale dell'importo netto | Importo netto del saldo fattura |

### <a name="calculation-and-rounding-behavior"></a>Comportamento del calcolo e dell'arrotondamento

| Numero riga | Codice IVA | Origine importo | Importo IVA |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Codice 1         | 42.42         | 4.25             |
| 1           | Codice 2         | 42.42         | 4.24             |
| 2           | Codice 1         | 42.42         | 4.24             |
| 2           | Codice 2         | 42.42         | 4.24             |

L'importo della base imponibile è calcolato per documento:

- Importo imponibile = 42,42 + 42,42 = 84,84

L'importo dell'imposta viene calcolato per codice IVA:

- Importo dell'imposta per codice IVA 1 = 84,84 &times; 10% = 8,484
- Importo dell'imposta per codice IVA 2 = 84,84 &times; 10% = 8,484

L'importo dell'imposta viene arrotondato per combinazione di codici IVA:

- Importo totale dell'IVA = 8,484 + 8,484 = 16,968, che viene arrotondato a 16,97

L'importo arrotondato dell'imposta viene allocato a ciascuna riga per codice IVA:

- Assegna l'importo dell'IVA (16,97) alla riga 1 e alla riga 2:

    - **Riga 1:**

        - Importo dell'imposta per codice IVA 1 = 4,25
        - Importo dell'imposta per codice IVA 2 = 4,24

    - **Riga 2:**

        - Importo dell'imposta per codice IVA 1 = 4,24
        - Importo dell'imposta per codice IVA 2 = 4,24

## <a name="example-7"></a>Esempio 7

### <a name="parameter-values"></a>Valori parametro

| Metodo di calcolo | Arrotondamento per                | Origine                              | Imponibile marginale       |
| ------------------ | -------------------------- | ----------------------------------- | ------------------- |
| Riga               | Combinazione codici IVA | Percentuale calcolata dell'importo netto | Importo netto per riga |

### <a name="calculation-and-rounding-behavior"></a>Comportamento del calcolo e dell'arrotondamento

| Numero riga | Codice IVA | Origine importo | Importo IVA |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Codice 1         | 42.42         | 4.72             |
| 1           | Codice 2         | 42.42         | 4.71             |
| 2           | Codice 1         | 42.42         | 4.71             |
| 2           | Codice 2         | 42.42         | 4.72             |

L'importo della base imponibile è calcolato per riga:

- **Riga 1:** 42,42
- **Riga 2:** 42,42

L'importo dell'imposta viene calcolato per codice IVA:

- **Riga 1:**

    - Importo dell'imposta per codice IVA 1 = 42,42 &times; 10% &divide; (1 – 10%) = 4,7133
    - Importo dell'imposta per codice IVA 2 = 42,42 &times; 10% &divide; (1 – 10%) = 4,7133

- **Riga 2:**

    - Importo dell'imposta per codice IVA 1 = 42,42 &times; 10% &divide; (1 – 10%) = 4,7133
    - Importo dell'imposta per codice IVA 2 = 42,42 &times; 10% &divide; (1 – 10%) = 4,7133

L'importo dell'imposta viene arrotondato per combinazione di codici IVA:

- Importo totale dell'IVA = 4,7133 + 4,7133 + 4,7133 + 4,7133 = 18,8532, che viene arrotondato a 18,86

L'importo arrotondato dell'imposta viene allocato a ciascuna riga per codice IVA:

- Assegna l'importo dell'IVA (18,86) alla riga 1 e alla riga 2:

    - **Riga 1:**

        - Importo dell'imposta per codice IVA 1 = 4,72
        - Importo dell'imposta per codice IVA 2 = 4,71

    - **Riga 2:**

        - Importo dell'imposta per codice IVA 1 = 4,71
        - Importo dell'imposta per codice IVA 2 = 4,72

## <a name="example-8"></a>Esempio 8

### <a name="parameter-values"></a>Valori parametro

| Metodo di calcolo | Arrotondamento per                | Origine                              | Imponibile marginale                 |
| ------------------ | -------------------------- | ----------------------------------- | ----------------------------- |
| Riga/Totale         | Combinazione codici IVA | Percentuale calcolata dell'importo netto | Importo netto del saldo fattura |

### <a name="calculation-and-rounding-behavior"></a>Comportamento del calcolo e dell'arrotondamento

| Numero riga | Codice IVA | Origine importo | Importo IVA |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Codice 1         | 42.42         | 4.72             |
| 1           | Codice 2         | 42.42         | 4.71             |
| 2           | Codice 1         | 42.42         | 4.71             |
| 2           | Codice 2         | 42.42         | 4.72             |

L'importo della base imponibile è calcolato per documento:

- Importo imponibile = 42,42 + 42,42 = 84,84

L'importo dell'imposta viene calcolato per codice IVA:

- Importo dell'imposta per codice IVA 1 = 84,84 &times; 10% &divide; (1 – 10%) = 9,4267
- Importo dell'imposta per codice IVA 2 = 84,84 &times; 10% &divide; (1 – 10%) = 9,4267

L'importo dell'imposta viene arrotondato per combinazione di codici IVA:

- Importo totale dell'IVA = 9,4267 + 9,4267 = 18,8534, che viene arrotondato a 18,86

L'importo arrotondato dell'imposta viene allocato a ciascuna riga per codice IVA:

- Assegna l'importo dell'IVA (18,86) alla riga 1 e alla riga 2:

    - **Riga 1:**

        - Importo dell'imposta per codice IVA 1 = 4,72
        - Importo dell'imposta per codice IVA 2 = 4,71

    - **Riga 2:**

        - Importo dell'imposta per codice IVA 1 = 4,71
        - Importo dell'imposta per codice IVA 2 = 4,72

## <a name="additional-resources"></a>Risorse aggiuntive

- [Metodi di calcolo IVA nel campo Origine](sales-tax-calculation-methods-origin-field.md)
- [Aliquote IVA basate su Imponibile marginale e Metodo di calcolo](marginal-base-field.md)
- [Opzioni importo totale e intervallo per i codici IVA](whole-amount-interval-options-sales-tax-codes.md)
