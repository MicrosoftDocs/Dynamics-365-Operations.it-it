---
title: Funzione ER SESSIONNOW
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SESSIONNOW della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/04/2019
ms.topic: article
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
ms.openlocfilehash: 47b88a1ca0ea9fd09c2a82963901d9ace78891bb
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746796"
---
# <a name="sessionnow-er-function"></a>Funzione ER SESSIONNOW

[!include [banner](../includes/banner.md)]

La funzione `SESSIONNOW` restituisce un valore *DateTime* che rappresenta la data e l'ora correnti della sessione dell'applicazione.

## <a name="syntax"></a>Sintassi

```vb
SESSIONNOW ()
```

## <a name="return-values"></a>Valori restituiti

*Data/Ora*

Il valore di data/ora risultante.

## <a name="example"></a>Esempio

`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` restituisce la data/ora della sessione dell'applicazione corrente, il 24 dicembre 2015, come **"24.12.2015"**, basata sulla cultura tedesca selezionata e sul formato specificato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]