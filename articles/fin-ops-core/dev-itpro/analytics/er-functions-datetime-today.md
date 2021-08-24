---
title: Funzione ER TODAY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione TODAY della creazione di report elettronici (ER).
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
ms.openlocfilehash: 12c4489751e9e0c06d4b628e7c297eee472054369f7cfacee048622cbc39d074
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755828"
---
# <a name="today-er-function"></a>Funzione ER TODAY

[!include [banner](../includes/banner.md)]

La funzione `TODAY` restituisce un valore *Data* che rappresenta la data corrente del server applicazioni.

## <a name="syntax"></a>Sintassi

```xpp
TODAY ()
```

## <a name="return-values"></a>Valori restituiti

*Data*

Il valore di data risultante.

## <a name="example"></a>Esempio

`DATEFORMAT (TODAY (), "dd-MM-yyyy")` restituisce il valore data/ora del server di applicazioni, 24 dicembre 2015, come stringa **"24-12-2015"**, in base al formato personalizzato specificato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]