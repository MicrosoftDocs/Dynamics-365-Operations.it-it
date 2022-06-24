---
title: Funzione ER FA_BALANCE
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione FA_BALANCE della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/17/2019
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3dd44f0d5ff143189b2c55c4df80847c2161231
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902685"
---
# <a name="fa_balance-er-function"></a>Funzione ER FA_BALANCE

[!include [banner](../includes/banner.md)]

La funzione `FA_BALANCE` restituisce un valore *Contenitore (record)* costituito dai dati per il saldo cespiti per l'articolo dei cespiti specificato, il codice del modello di valore, l'anno di dichiarazione e la data di dichiarazione.

## <a name="syntax"></a>Sintassi

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a>Argomenti

`fixed asset code`: *Stringa*

Un valore *Stringa* che rappresenta il codice di un articolo dei cespiti per il quale viene calcolato il saldo.

`value model code`: *Stringa*

Un valore *Stringa* che rappresenta il codice di un modello di valore per il quale viene calcolato il saldo.

`reporting year`: *Valore enumerazione*

Un valore di enumerazione dell'enumerazione dell'applicazione **AssetYear** che definisce un periodo per il calcolo del saldo.

`reporting date`: *Data*

Un valore *Data* che definisce una data per il calcolo del saldo.

## <a name="return-values"></a>Valori restituiti

*Contenitore (record)*

Il valore del record risultante.

## <a name="example"></a>Esempio

`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` restituisce il contenitore dati dei saldi del cespite **COMP-000001** che è stato preparato per il modello di valore **Current** sulla data della sessione corrente dell'applicazione.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]