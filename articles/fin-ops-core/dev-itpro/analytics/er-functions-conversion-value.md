---
title: Funzione ER VALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione VALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 7cdaa302e757b54858e36c3716167593383d7071
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561448"
---
# <a name="value-er-function"></a>Funzione ER VALUE

[!include [banner](../includes/banner.md)]

La funzione `VALUE` restituisce un valore *Reale* che viene convertito dalla stringa specificata.

## <a name="syntax"></a>Sintassi

```vb
VALUE (text)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore stringa che deve essere convertito in un valore numerico.

## <a name="return-values"></a>Valori restituiti

*Reale*

Il valore numerico risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Le virgole e i caratteri punto (). vengono considerati separatori decimali e un trattino iniziale (-) viene utilizzato come negativo. Viene generata un'eccezione in fase di runtime se la stringa specificata contiene altri caratteri non numerici.

## <a name="example-1"></a>Esempio 1

`VALUE ("1 234,56")` genera un'eccezione.

## <a name="example-2"></a>Esempio 2

`VALUE ("1234,56")` restituisce **1234.56**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di conversione di tipo](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]