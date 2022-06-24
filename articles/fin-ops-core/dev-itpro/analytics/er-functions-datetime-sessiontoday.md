---
title: Funzione ER SESSIONTODAY
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione SESSIONTODAY della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 755dc867d518da9cb4511b2daeb4832a3c6d90f9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888232"
---
# <a name="sessiontoday-er-function"></a>Funzione ER SESSIONTODAY

[!include [banner](../includes/banner.md)]

La funzione `SESSIONTODAY` restituisce un valore *Data* che rappresenta la data corrente della sessione dell'applicazione.

## <a name="syntax"></a>Sintassi

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a>Valori restituiti

*Data*

Il valore di data risultante.

## <a name="example"></a>Esempio

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` restituisce la data della sessione dell'applicazione corrente, il 24 dicembre 2015, come stringa **"24-12-2015"**, basata sulla cultura tedesca selezionata e sul formato specificato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]