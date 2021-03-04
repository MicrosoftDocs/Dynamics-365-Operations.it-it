---
title: Funzione ER NOW
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NOW della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 0c3cfefd36db44608f05225746704aa3fbe4fc2c
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682367"
---
# <a name="now-er-function"></a>Funzione ER NOW

[!include [banner](../includes/banner.md)]

La funzione `NOW` restituisce un valore *DateTime* che rappresenta la data e l'ora correnti del server delle applicazioni.

## <a name="syntax"></a>Sintassi

```vb
NOW ()
```

## <a name="return-values"></a>Valori restituiti

*Data/Ora*

Il valore di data/ora risultante.

## <a name="example"></a>Esempio

`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` restituisce il valore data/ora del server di applicazioni, 24 dicembre 2015, come **"24-12-2015"**, in base al formato personalizzato specificato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]