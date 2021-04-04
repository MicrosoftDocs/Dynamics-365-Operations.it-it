---
title: Funzione ER TEXT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione TEXT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 5da7375020be827f432ba97740da37abe48962fc
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560063"
---
# <a name="text-er-function"></a>Funzione ER TEXT

[!include [banner](../includes/banner.md)]

La funzione `TEXT` restituisce il numero specificato come un valore *Stringa* dopo che è stato convertito in stringa di testo formattata in base alle impostazioni locali del server dell'istanza corrente dell'applicazione.

## <a name="syntax"></a>Sintassi

```vb
TEXT (number)
```

## <a name="arguments"></a>Argomenti

`number`: *Intero* o *Reale*

Un numero che deve essere convertito in una stringa di testo.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Per i valori di tipo *Reale*, la conversione di stringhe è limitata a due posizioni decimali.

## <a name="example"></a>Esempio

Se le impostazioni locali server dell'istanza di Microsoft Dynamics 365 Finance sono definite come **EN-US**, `TEXT (NOW ())` restituisce la data della sessione di Finance corrente, 17 dicembre 2015, come stringa di testo **"12/17/2015 07:59:23 AM"**. `TEXT (1/3)` restituisce **"0.33"**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]