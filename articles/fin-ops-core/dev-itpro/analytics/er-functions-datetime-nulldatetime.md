---
title: Funzione ER NULLDATETIME
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NULLDATETIME della creazione di report elettronici (ER).
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
ms.openlocfilehash: f7282b7c161b6e183186ba81e6bcf7b34ce6e612
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746821"
---
# <a name="nulldatetime-er-function"></a>Funzione ER NULLDATETIME

[!include [banner](../includes/banner.md)]

La funzione `NULLDATETIME` restituisce un valore *DateTime* che rappresenta il valore data/ora **null** (1 gennaio 1900) in Coordinated Universal Time (Ora di Greenwich \[GMT\]).

## <a name="syntax"></a>Sintassi

```vb
NULLDATETIME ()
```

## <a name="return-values"></a>Valori restituiti

*Data/Ora*

Il valore di data/ora risultante.

## <a name="example"></a>Esempio

`DATETIMEFORMAT( NULLDATETIME(), "O")` restituisce il valore della stringa **1900-01-01T00:00:00.0000000+00:00** quando viene richiamato durante un processo avviato da un utente dell'applicazione che ha il valore del fuso orario **(GMT) Coordinated Universal Time** nella sezione **Preferenze di lingua e paese**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]