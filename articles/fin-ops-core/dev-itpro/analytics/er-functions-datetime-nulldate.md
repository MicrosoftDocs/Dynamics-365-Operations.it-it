---
title: Funzione ER NULLDATE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NULLDATE della creazione di report elettronici (ER).
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
ms.openlocfilehash: 6ac8da3f18c7793512685d52dd64a9bd55bfb8fc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746845"
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