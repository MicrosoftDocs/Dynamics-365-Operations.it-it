---
title: Funzione ER GETCURRENTCOMPANY
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione GETCURRENTCOMPANY della creazione di report elettronici (ER).
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
ms.openlocfilehash: b5f5f7d7c884000f59b93e10875f78289a879779
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280187"
---
# <a name="getcurrentcompany-er-function"></a>Funzione ER GETCURRENTCOMPANY

[!include [banner](../includes/banner.md)]

La funzione `GETCURRENTCOMPANY` restituisce un valore *Stringa* che rappresenta il codice della persona giuridica (società) a cui un utente è attualmente connesso.

## <a name="syntax"></a>Sintassi

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

`GETCURRENTCOMPANY ()` restituisce **USMF** per un utente collegato alla società **Contoso Entertainment System USA**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
