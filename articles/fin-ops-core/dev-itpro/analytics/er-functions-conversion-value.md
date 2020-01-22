---
title: Funzione ER VALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione VALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 160dd81baa43702b2deea1e3eea20080fca122ca
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917628"
---
# <a name="VALUE">Funzione ER VALUE</a>

[!include [banner](../includes/banner.md)]

La funzione `VALUE` restituisce un valore *Reale* che viene convertito dalla stringa specificata.

## <a name="syntax"></a>Sintassi

```
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
