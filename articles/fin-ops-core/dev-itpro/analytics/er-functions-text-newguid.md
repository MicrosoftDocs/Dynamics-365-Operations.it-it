---
title: Funzione ER NEWGUID
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NEWGUID della creazione di report elettronici (ER).
author: NickSelin
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-09-08
ms.dyn365.ops.version: AX 10.0.23
ms.openlocfilehash: 5856a4d765f5136ecb11a34e0255c1ba88818f2c
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647942"
---
# <a name="newguid-er-function"></a>Funzione ER NEWGUID

[!include [banner](../includes/banner.md)]

La funzione `NEWGUID` genera un nuovo identificatore univoco globale (GUID) e lo restituisce come valore *[GUID](er-formula-supported-data-types-primitive.md#guid)*.

## <a name="syntax"></a>Sintassi

```vb
NEWGUID ()
```

## <a name="return-values"></a>Valori restituiti

*GUID*

Il valore GUID risultante.

## <a name="example"></a>Esempio

`NEWGUID()` restituisce sempre un nuovo valore *GUID*: **3afcf7ff-af10-ec11-b6e6-000d3a13209e**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
