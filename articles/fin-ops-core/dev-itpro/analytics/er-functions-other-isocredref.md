---
title: Funzione ER ISOCREDREF
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione ISOCREDREF della creazione di report elettronici (ER).
author: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 189843d608cc00ac51a284b163553da6d821150e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277588"
---
# <a name="isocredref-er-function"></a>Funzione ER ISOCREDREF

[!include [banner](../includes/banner.md)]

La funzione `ISOCREDREF` restituisce un valore *Stringa* che rappresenta un riferimento creditore International Organization for Standardization (ISO), in base alle cifre e ai simboli alfabetici del numero di fattura specificato.

## <a name="syntax"></a>Sintassi

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a>Argomenti

`invoice number digits`: *Stringa*

Un valore di testo che rappresenta le cifre di un numero di fattura.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

> [!NOTE] 
> Per eliminare i simboli da alfabeti che non sono conformi ISO, l'argomento `invoice number digits` deve essere tradotto prima di passarlo alla funzione.

## <a name="example"></a>Esempio

`ISOCredRef ("VEND-200002")` restituisce **"RF23VEND-200002"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
