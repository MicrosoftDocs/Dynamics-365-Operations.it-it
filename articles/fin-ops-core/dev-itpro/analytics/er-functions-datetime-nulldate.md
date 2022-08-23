---
title: Funzione ER NULLDATE
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione NULLDATE della creazione di report elettronici (ER).
author: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 276ad99303a4e88ecb1c83e9518e06bfd7afaa45
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272654"
---
# <a name="nulldate-er-function"></a>Funzione ER NULLDATE

[!include [banner](../includes/banner.md)]

La funzione `NULLDATE` restituisce un valore *Data* che rappresenta la data **null** (1 gennaio 1900).

## <a name="syntax"></a>Sintassi

```vb
NULLDATE () as 
```

## <a name="return-values"></a>Valori restituiti

*Data*

Il valore di data risultante.

## <a name="example-1"></a>Esempio 1

`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` restituisce la data **null**, 1 gennaio 1900, come **"1900-01-01"**, basata sul formato personalizzato specificato.

## <a name="example-2"></a>Esempio 2

L'espressione `IF( Invoice.DocumentDate = NULLDATE(), true, false)` restituisce **True** quando il valore del campo **DocumentDate** equivale alla data **null**. In questo esempio, **Invoice** è l'origine dati della creazione di report elettronici (ER) del tipo **Finance and Operations/Tabella** e fa riferimento alla tabella CustInvoiceJour.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
