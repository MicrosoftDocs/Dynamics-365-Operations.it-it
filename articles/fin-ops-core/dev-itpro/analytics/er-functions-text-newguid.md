---
title: Funzione ER NEWGUID
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione NEWGUID della creazione di report elettronici (ER).
author: kfend
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-09-08
ms.dyn365.ops.version: AX 10.0.23
ms.custom: ''
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 381dbcbe816c189c1966ffe962020d5aa2b1f3eb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274774"
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
