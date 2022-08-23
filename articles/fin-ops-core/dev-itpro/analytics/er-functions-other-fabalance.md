---
title: Funzione ER FA_BALANCE
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione FA_BALANCE della creazione di report elettronici (ER).
author: kfend
ms.date: 12/17/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: f9bb52643b60fd1b9423d798c08d731565c70f81
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285247"
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
