---
title: Funzione ER SESSIONTODAY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione SESSIONTODAY della creazione di report elettronici (ER).
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
ms.openlocfilehash: bcfb36d6e3fb8475546f7cfb420c4aca848ac896
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917467"
---
# <a name="SESSIONTODAY">Funzione ER SESSIONTODAY</a>

[!include [banner](../includes/banner.md)]

La funzione `SESSIONTODAY` restituisce un valore *Data* che rappresenta la data corrente della sessione dell'applicazione.

## <a name="syntax"></a>Sintassi

```
SESSIONTODAY ()
```

## <a name="return-values"></a>Valori restituiti

*Data*

Il valore di data risultante.

## <a name="example"></a>Esempio

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` restituisce la data della sessione dell'applicazione corrente, il 24 dicembre 2015, come stringa **"24-12-2015"**, basata sulla cultura tedesca selezionata e sul formato specificato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)
