---
title: Funzione ER NOW
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NOW della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: cffb23afa4cb347d2840b099b0b49a71150d87d8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917559"
---
# <a name="NOW">Funzione ER NOW</a>

[!include [banner](../includes/banner.md)]

La funzione `NOW` restituisce un valore *DateTime* che rappresenta la data e l'ora correnti del server delle applicazioni.

## <a name="syntax"></a>Sintassi

```
NOW ()
```

## <a name="return-values"></a>Valori restituiti

*Data/Ora*

Il valore di data/ora risultante.

## <a name="example"></a>Esempio

`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` restituisce il valore data/ora del server di applicazioni, 24 dicembre 2015, come **"24-12-2015"**, in base al formato personalizzato specificato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)
